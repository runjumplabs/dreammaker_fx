---
layout: extra_naked
title: Docs
---

# Building a Basic Echo Effect
------

Effects and synth code is coded in the Arduino IDE and coded in the C++ programming language.  However, one doesn't have to be a programmer to use this platform.  The coding patterns for creating various effect and synth components, wiring them together and controlling their parameters is straight forward.


## Basic Arduino anatomy
------
With the Arduino app open, go to File->New.  You'll see a new text editor window appear with a new "sketch" (aka a program in Arduino-speak).  This sketch will come pre-populated with two *functions*. One is called `setup()` and another is called `loop()`.  

When the sketch is downloaded to our hardware, it will run any commands in the `setup()` function first.  And then it will run the `loop()` function indefinitely. 

``` C
void setup() {
  // put your setup code here, to run once:

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

So when creating effects, we will define how the effects connect together in the `setup()` function and we will then (optionally) adjust the parameters for these effects in the `loop()` routine.

Let's start by creating a simple echo effect to see how the pieces fit together.

## 1. Add the effects library of functions
------

At the top of the file, we'll add a line that will link in all of the functions, variables and objects that you'll use to create your effects.  At the very top of the file, add `#include "dreammakerfx.h"`.  You'll add this line to the top of every Arduino sketch you create for this platform.

```
// Include DreamMaker FX library of effects routines
#include <dreammakerfx.h>
```


## 2. Add any effects or synthesis *objects*
------

Above the setup routine, we will add (aka *declare*) any effect and synth *objects* that we'll be using.  When we add an object, in many cases we will also provide the initial parameters.  

In this case, we are going to create a single echo / delay effect object and name it `my_echo_1`.  When we initialize an echo object, it takes two *arguments* or initial parameters.  The first is how long the echo is in milliseconds (1000th of a second).  And the second is the *feedback* ratio (between 0.0 and 1.0) which determines how much audio is fed back into the echo and thus how long the echo lasts.  If feedback is set to 1.0, it will echo forever.  And if feedback is set to 0.0, it won't echo at all.  Let's set the echo length to be 1 second (or 1000 milliseconds) and the feedback ratio at 0.7.

Add the following code after your `#include "dm_fx.h"` line.  


```
// Create/declare one echo effect and configure it
fx_delay   my_echo_1(1000.0,  // 1 second echo
                     0.7);    // 0.7 feedback ratio
```

## 3. Route the effect into our pedal
------

Next, in the `setup()` routine, we need to initialize our effects `pedal` and route the audio from the pedal in and out jacks through the various effects and synth objects we're using.  
``` C
void setup() {

  pedal.init(true);   // Initialize the system and enable debug mode

  // Connect our effect(s) to input and output jacks
  pedal.route_audio(pedal.instr_in, my_echo_1.input);		// Instr in -> echo in
  pedal.route_audio(my_echo_1.output, pedal.amp_out);		// Echo out -> Amp out

  pedal.run();    // Run the effect

}
```

Let's deconstruct what we just did here.

First, we *called* the `pedal.init(true);` function to set up our system.  By passing a true to this function, we're also enabling debug mode and the pedal will output status infomation.

Next, we connected the audio from the input jack of our pedal (aka `instr_in`) to the input of our echo object (aka `my_echo_1.input`) using the `route_audio()` function.  

Each effect and synthesis object has a set of input and outputs that can "routed" or virtually "wired" together.  There are also some inputs and outputs that are part of the pedal itself.  Presently, there is an `instr_in` input (audio in from our instrument) and `amp_out` output (audio out towards our amp).

In this case, we just have one object.  We routed / wired the instr_in to the input of our `my_echo_1` object.  And then we routed / wired the output of our `my_echo_1` object to the pedal output.

And finally, we call `pedal.run();` which takes our effect configuration, performs the magic, sends it over to the DSP where the effects are run.

## 4. Add service function to our loop
------

The last thing we need to do is add the `pedal.service();` function call in our `loop()` function.  This function basically checks in the with the DSP, updates any parameters that need to be updated, and retrieves information from the DSP.

``` C
void loop() {
  // put your main code here, to run repeatedly:

  // sweet nothings to/from DSP
  pedal.service();
}
```

## Bringing it all together
------
Let's now look at the whole echo effect:

``` C
// Include our library of effects routines
#include <dreammakerfx.h>

// Create/declare one echo effect and configure it
fx_delay   my_echo_1(1000.0,  // 1 second echo
                     0.7);    // 0.7 feedback ratio

void setup() {

  pedal.init(true);   // Initialize the system and enable debug mode

  // Connect our effect(s) to input and output jacks
  pedal.route_audio(pedal.instr_in, my_echo_1.input);		// Instr in -> echo in
  pedal.route_audio(my_echo_1.output, pedal.amp_out);		// Echo out -> Amp out

  pedal.run();    // Run the effect

}

void loop() {
  // put your main code here, to run repeatedly:

  // sweet nothings to/from DSP
  pedal.service();
}

```

## Running the effect on hardware
------

As discussed in the installation section, be sure the LED near the USB jack is fading in / fading out.  This means the platform is in bootloader mode and is ready to accept a new effect.  If the LED is not doing this, press the reset button twice in quick succession.

Click the __Upload__ button in the upper-left hand side of the Arduino IDE (it's the arrow pointing to the right).  Your code will compile and then download to the board.  After a second or two, you'll hear the echo effect applied to any audio you send through the pedal!

Once you have downloaded an effect, it is stored in memory on the pedal.  If you disconnect the pedal and plug it in later, it will start up running the same effect.  To overwrite the effect currently stored in the pedal, just press the reset button twice in quick success to upload a new effect.

Navigate to Tools -> Serial Monitor.  This will bring up the console log.  When your effect configuration is processed on the Arduino processor, some information will be sent to the console letting you know how things were routed and everything is okay.  You'll also see the telemtry data from the DSP too so you can see if any effect failed to initialize or something went wrong.
