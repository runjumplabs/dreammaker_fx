---
layout: extra_naked
title: Docs
---

# Buttons and Knobs (aka Pots)
------

The DreamMakerFX platform has a few buttons and knobs on it.  Each of these is completely programmable.

## Configuring the Buttons (aka Footswitches)
------

The buttons can be set up to do the following:
 1. Bypass the entire effect like a typical bypass switch on a pedal
 1. Tap in a tempo or delay lenght
 1. Behave as a momentary effect (i.e. while button is held down, do one thing and when it is release, do something else)
 1. Behave as a toggle for an effect (i.e. tap it once to turn something on, tap it again to turn it off).

** 1. Configuring the button as a pedal bypass switch **

To configure either the left or right footswtich to become the bypass button for the effect, we use the `pedal.add_bypass_button()` function while defining our pedal routes in `setup()`.  When we __call__ the `pedal.add_bypass_button()` function, we tell it which footswtich to use as the bypass button by using either `FOOTSWITCH_LEFT` or `FOOTSWITCH_RIGHT` as the __argument__.  

Let's revisit our delay function and set it up to use the left footswitch as the bypass button.  If you don't add a bypass switch, the effect will just start running out of the gate.

``` C

void setup() {

  pedal.init();   // Initialize the system 

  // Connect our effect(s) to input and output jacks
  pedal.route_audio(pedal.instr_in, my_echo_1.input);		// Instr in -> echo in
  pedal.route_audio(my_echo_1.output, pedal.amp_out);		// Echo out -> Amp out

  // Left foot switch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  pedal.run();    // Run the effect

}
```


** 2. Configuring the button to be a tap delay/tempo button **

A tap function allows you to tap the switch at a certain tempo/rate.  The Arduino will lock onto this tap rate and it can be used to update things like the rate of a tremelo and the length/time of an echo effect.

To configure either of the footswitches to be a tap delay/tempo button, we use the `pedal.add_tap_interval_button()` function.  Just like the pedal bypass function, we can use either footswitch as our tap delay/tempo input.  We just can't use the same footswitch that we're using for bypass.  The `pedal.add_tap_interval_button()` takes two arguments.  The first is the foot switch we want to use (either `FOOTSWITCH_LEFT` or `FOOTSWITCH_RIGHT`).  The second argument determines if we want the LED next to the footswitch to flash at the same rate.  Setting the second argument to `true` will enable the LED strobe and setting it `false` will disable the LED strobe.

Let's again revisit the delay function and add the ability to "tap in" a new delay length using the right footswitch.

``` C

void setup() {

  pedal.init();   // Initialize the system 

  // Connect our effect(s) to input and output jacks
  pedal.route_audio(pedal.instr_in, my_echo_1.input);		// Instr in -> echo in
  pedal.route_audio(my_echo_1.output, pedal.amp_out);		// Echo out -> Amp out

  // Left foot switch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Right foot switch is our tap delay lenght input and turn on LED strobe
  pedal.add_tap_interval_button(FOOTSWITCH_RIGHT, true);

  pedal.run();    // Run the effect

}
```

In our `loop()` function, we call `pedal.new_tap_interval()` to determine if the user has tapped in a new tempo and if so, what we want to do about it.  If the user has just tapped in a new tempo/delay lenght, this function will __return__ `true` and if this user has not, it will return `false`.  

We then have two options in terms of how we read the tap interval.  Some effects take a period of time (tyically in milliseconds) as an argument like fx_delay.  Other effects that use an oscillator take a rate (typically cycles per second).  

If we are reading the newly tapped interval for a function that uses time in milliseconds, we use `pedal.get_tap_interval_ms()`.  And if we are reading the newly tapped interval for a function that uses rate in Hertz, we use `pedal.get_tap_freq_hz()`.  

In this case, we are using a delay function so when we detect that we have a new tap interval from the user, we're going to update the length of the delay effect using the tap interval in milliseconds (e.g. using `pedal.get_tap_interval_ms()`).

``` C

loop() {
  // If new delay time has been tapped in, use that
  if (pedal.new_tap_interval()) { 

  	// Update delay length with new tap interval
    my_delay.set_length_ms(pedal.get_tap_interval_ms());
  } 

  // Service pedal
  pedal.service();

}

```

So with just a few lines of code, we've added the ability to tap in a tempo into the pedal to control the rate of LFOs (flangers, phasers, tremelos, vibratos, etc.) or the length of our delays.
 


