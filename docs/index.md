---
layout: extra_naked
title: API Documentation
---
# Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`class `[`fx_adsr_envelope`](#classfx__adsr__envelope) | Effect: Envelope generator.
`class `[`fx_amplitude_mod`](#classfx__amplitude__mod) | Effect: Amplitude modulator for creating tremelo-like effects.
`class `[`fx_audio_node`](#classfx__audio__node) | Class for effects audio node.
`class `[`fx_biquad_filter`](#classfx__biquad__filter) | Effect: Biquad filter for implementing various types of filters (low pass, high pass, band pass, etc.)
`class `[`fx_compressor`](#classfx__compressor) | Effect: Compressor/Limiter.
`class `[`fx_control_node`](#classfx__control__node) | Class for effects control node.
`class `[`fx_delay`](#classfx__delay) | Effect: Delay/echo.
`class `[`fx_destructor`](#classfx__destructor) | Effect: Destructor - provides various types of hard and soft destructors for creating different types of distortions.
`class `[`fx_envelope_tracker`](#classfx__envelope__tracker) | Effect: Envelope tracker.
`class `[`fx_gain`](#classfx__gain) | Effect: Gain - used to increase or decrease the volume of an audio signal.
`class `[`fx_looper`](#classfx__looper) | Effect: Looper - capture and playback loops.
`class `[`fx_mixer_2`](#classfx__mixer__2) | Utility: 2 channel mixer.
`class `[`fx_mixer_3`](#classfx__mixer__3) | Utility: 3 channel mixer.
`class `[`fx_mixer_4`](#classfx__mixer__4) | Utility: 4 channel mixer.
`class `[`fx_octave`](#classfx__octave) | Effect: - chops up audio in the time domain and pipes to different effects.
`class `[`fx_oscillator`](#classfx__oscillator) | Utility: Oscillator that can has both audio and control outputs.
`class `[`fx_phase_shifter`](#classfx__phase__shifter) | Effect: Phase shifter for creating rich phase shifts.
`class `[`fx_pitch_shift`](#classfx__pitch__shift) | Effect: Pitch shifter - shifts audio up or down in pitch.
`class `[`fx_ring_mod`](#classfx__ring__mod) | Effect: Ring modulator - frequency modulates the audio - crazy sounding.
`class `[`fx_slicer`](#classfx__slicer) | Effect: Slicer - chops up audio in the time domain and pipes to different effects.
`class `[`fx_variable_delay`](#classfx__variable__delay) | Effect: Variable delay - foundational block of flangers and choruses.

# class `fx_adsr_envelope` {#classfx__adsr__envelope}

```
class fx_adsr_envelope
  : public fx_effect
```  

Effect: Envelope generator.

An envelope generator creates a volume envelope that can applied to either the audio from the instrument or an oscillator.

Here's a good explanation of what ADSR means. <iframe width="560" height="315" src="https://www.youtube.com/embed/JT6rixgu4s4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__adsr__envelope_1aa8413d27edd9d165fda5b54a20fbcc9f) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__adsr__envelope_1a77decae0c991138a2d6124c45ecf1768) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`attack_ms`](#classfx__adsr__envelope_1a8755a83229b0613181c6b967e656683d) | Control routing node [input]: envelope attack in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`decay_ms`](#classfx__adsr__envelope_1a95f3ec921f735408c042981442071bd0) | Control routing node [input]: envelope decay in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`sustain_ms`](#classfx__adsr__envelope_1a356007e4c07a711605921859b50d1e10) | Control routing node [input]: envelope sustain in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`release_ms`](#classfx__adsr__envelope_1a1e346c77984b262a02b941210cd72bca) | Control routing node [input]: envelope release in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`peak_ratio`](#classfx__adsr__envelope_1aa3c412db728213b42ef53cadb78ede10) | Control routing node [input]: relative volume after attack (0.0 to 1.0) - will be scaled by output volume
`public `[`fx_control_node`](#classfx__control__node)` * `[`sustain_ratio`](#classfx__adsr__envelope_1aa9a3053c74f419a8b74933f5771da34d) | Control routing node [input]: relative volume during sustain (0.0 to 1.0) - will be scaled by output volume
`public `[`fx_control_node`](#classfx__control__node)` * `[`gain_out`](#classfx__adsr__envelope_1a4e0eb91c963904e693f0916bac693e2c) | Control routing node [input]: output pain
`public `[`fx_control_node`](#classfx__control__node)` * `[`playing`](#classfx__adsr__envelope_1a0b3aeec90d68e3d8e29e6756915ede81) | Control routing node [input]: playing - continuously set to non-zero to during play and zero to stop
`public `[`fx_control_node`](#classfx__control__node)` * `[`value`](#classfx__adsr__envelope_1ae138d6a98e84e3790feb24750fbc82ad) | Control routing node [output]: value of the envelope
`public inline  `[`fx_adsr_envelope`](#classfx__adsr__envelope_1a9a0d60c5a0311bec34f9243c7e699c14)`(float attack_ms,float decay_ms,float sustain_ms,float release_ms,float gain_out)` | Constructs a new instance of the envelope.
`public inline void `[`enable`](#classfx__adsr__envelope_1ac132a4a318fd9e90d683ddbf1a27a1e9)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__adsr__envelope_1af33ba71099aa662fa4f559449f044545)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`print_params`](#classfx__adsr__envelope_1ac647da40810a3c82b9ded89709ad1cc2)`(void)` | Prints the parameters for the delay effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__adsr__envelope_1aa8413d27edd9d165fda5b54a20fbcc9f) {#classfx__adsr__envelope_1aa8413d27edd9d165fda5b54a20fbcc9f}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__adsr__envelope_1a77decae0c991138a2d6124c45ecf1768) {#classfx__adsr__envelope_1a77decae0c991138a2d6124c45ecf1768}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`attack_ms`](#classfx__adsr__envelope_1a8755a83229b0613181c6b967e656683d) {#classfx__adsr__envelope_1a8755a83229b0613181c6b967e656683d}

Control routing node [input]: envelope attack in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`decay_ms`](#classfx__adsr__envelope_1a95f3ec921f735408c042981442071bd0) {#classfx__adsr__envelope_1a95f3ec921f735408c042981442071bd0}

Control routing node [input]: envelope decay in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`sustain_ms`](#classfx__adsr__envelope_1a356007e4c07a711605921859b50d1e10) {#classfx__adsr__envelope_1a356007e4c07a711605921859b50d1e10}

Control routing node [input]: envelope sustain in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`release_ms`](#classfx__adsr__envelope_1a1e346c77984b262a02b941210cd72bca) {#classfx__adsr__envelope_1a1e346c77984b262a02b941210cd72bca}

Control routing node [input]: envelope release in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`peak_ratio`](#classfx__adsr__envelope_1aa3c412db728213b42ef53cadb78ede10) {#classfx__adsr__envelope_1aa3c412db728213b42ef53cadb78ede10}

Control routing node [input]: relative volume after attack (0.0 to 1.0) - will be scaled by output volume

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`sustain_ratio`](#classfx__adsr__envelope_1aa9a3053c74f419a8b74933f5771da34d) {#classfx__adsr__envelope_1aa9a3053c74f419a8b74933f5771da34d}

Control routing node [input]: relative volume during sustain (0.0 to 1.0) - will be scaled by output volume

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`gain_out`](#classfx__adsr__envelope_1a4e0eb91c963904e693f0916bac693e2c) {#classfx__adsr__envelope_1a4e0eb91c963904e693f0916bac693e2c}

Control routing node [input]: output pain

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`playing`](#classfx__adsr__envelope_1a0b3aeec90d68e3d8e29e6756915ede81) {#classfx__adsr__envelope_1a0b3aeec90d68e3d8e29e6756915ede81}

Control routing node [input]: playing - continuously set to non-zero to during play and zero to stop

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`value`](#classfx__adsr__envelope_1ae138d6a98e84e3790feb24750fbc82ad) {#classfx__adsr__envelope_1ae138d6a98e84e3790feb24750fbc82ad}

Control routing node [output]: value of the envelope

#### `public inline  `[`fx_adsr_envelope`](#classfx__adsr__envelope_1a9a0d60c5a0311bec34f9243c7e699c14)`(float attack_ms,float decay_ms,float sustain_ms,float release_ms,float gain_out)` {#classfx__adsr__envelope_1a9a0d60c5a0311bec34f9243c7e699c14}

Constructs a new instance of the envelope.

#### Parameters
* `attack_ms` The attack in milliseconds 

* `decay_ms` The decay in milliseconds 

* `sustain_ms` The sustain in milliseconds 

* `release_ms` The release in milliseconds 

* `gain_out` The gain out (linear: 0.0 to 1.0)

#### `public inline void `[`enable`](#classfx__adsr__envelope_1ac132a4a318fd9e90d683ddbf1a27a1e9)`()` {#classfx__adsr__envelope_1ac132a4a318fd9e90d683ddbf1a27a1e9}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__adsr__envelope_1af33ba71099aa662fa4f559449f044545)`()` {#classfx__adsr__envelope_1af33ba71099aa662fa4f559449f044545}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`print_params`](#classfx__adsr__envelope_1ac647da40810a3c82b9ded89709ad1cc2)`(void)` {#classfx__adsr__envelope_1ac647da40810a3c82b9ded89709ad1cc2}

Prints the parameters for the delay effect.

# class `fx_amplitude_mod` {#classfx__amplitude__mod}

```
class fx_amplitude_mod
  : public fx_effect
```  

Effect: Amplitude modulator for creating tremelo-like effects.

An amplitude modulator will change the volume or "amplitude" of the audio to create various types of tremelo effects. Here's a video demonstrating how amplitude modulators work:

[https://www.youtube.com/watch?v=AxZVMyIFqcA](https://www.youtube.com/watch?v=AxZVMyIFqcA)

<iframe width="560" height="315" src="https://www.youtube.com/embed/AxZVMyIFqcA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

Example: 
```
/**
 * This is an implementation of a typical delay / echo pedal.
 *
 * Left pot: depth - the depth of the tremelo effect
 * Center pot: delay time - modulation rate
 * Right pot: type of modulation - from counterclockwise to clockwise is sine -> triangle -> square -> random
 *
 * Left footswitch: bypass - turns on and off the effect
 * Right footswitch: tap - tap it a few times at a set interval to update the vibrato modulation rate
 *
 * This effect uses a tiny amount of the available processing power and memory.
 * It's provided as an example of how to use the various features of the fx_amplitude_mod block
 *
 *
 */
#include <dreammakerfx.h>

fx_amplitude_mod  tremy(1.0,       // Rate is 1.0Hz (1 cycle per second)
                        0.5,       // Initial depth is 0.5 (50% volume reduction)
                        0.0,       // Initial phase is 0 degrees
                        OSC_SINE,  // Sine oscillator
                        false);    // Not using an external oscillator

void setup() {

  // Initialize the pedal!
  pedal.init();

  // Route audio from instrument -> fx_amplitude_mod -> amp
  pedal.route_audio(pedal.instr_in, tremy.input);
  pedal.route_audio(tremy.output, pedal.amp_out);

  // left footswitch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Right foot switch is tap loop length
  pedal.add_tap_interval_button(FOOTSWITCH_RIGHT, true);

  // Run this effect
  pedal.run();

}

void loop() {

  // If new tempo has been tapped in, use that to control tremelo rate
  if (pedal.new_tap_interval()) {
    tremy.set_rate_hz(pedal.get_tap_freq_hz());
  }

  // Left pot controls depth
  if (pedal.pot_left.has_changed()) {
    tremy.set_depth(pedal.pot_left.val);
  }

  // Center pot controls rate
  if (pedal.pot_center.has_changed()) {
    float rate_hz = pedal.pot_center.val* 10.0;
    pedal.set_tap_blink_rate_hz(rate_hz);
    tremy.set_rate_hz(rate_hz);
  }

  // Right pot sets the oscillator type
  if (pedal.pot_right.has_changed()) {
    if (pedal.pot_right.val < 0.25) {
      tremy.set_lfo_type(OSC_SINE);
    } else if (pedal.pot_right.val < 0.5) {
      tremy.set_lfo_type(OSC_TRIANGLE);
    } else if (pedal.pot_right.val < 0.75) {
      tremy.set_lfo_type(OSC_SQUARE_SOFT);
    } else {
      tremy.set_lfo_type(OSC_RANDOM);
    }
  }

   // Run pedal service to take care of stuff
  pedal.service();

}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__amplitude__mod_1a52c5dce1e56a9efbceb9f0aa572e35d4) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__amplitude__mod_1a3ffb0f78f55a24d56ad40ed71b9c3655) | Audio routing node: primary audio output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`ext_mod_in`](#classfx__amplitude__mod_1aeedd96b1c4e5e8e1cbf93fb4e134362b) | Audio routing node: external modulator audio input
`public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__amplitude__mod_1a25ef00aa85c14e895710a505a9c6e0bd) | Control routing node: amplifude modulator depth (should be between 0.0 and 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__amplitude__mod_1ad85024759667cd9decc11e4fb24461ef) | Control routing node: amplitide modulator rate (Hz) (i.e. 1.0 = once per second)
`public inline  `[`fx_amplitude_mod`](#classfx__amplitude__mod_1acfe6780b005b6b34ba58e82b9b64cf50)`(float rate_hz,float depth)` | Basic constructor/initializer for amplitude modulator.
`public inline  `[`fx_amplitude_mod`](#classfx__amplitude__mod_1a354b528d3a59d766b7fc3e1ed74427f9)`(float rate_hz,float depth,float initial_phase_deg,OSC_TYPES modulation_type,bool use_ext_modulator)` | Advanced constructor for the amplitude modulator.
`public inline void `[`enable`](#classfx__amplitude__mod_1a4c21c0e9725c1dd515a2bf0b2fb8f99e)`()` | Enable the amplitude modululator (it is enabled by default)
`public inline void `[`bypass`](#classfx__amplitude__mod_1a5d5ef5ff79e9c553a9ee5116c3dfa516)`()` | Bypass the amplitude modululator (will just pass clean audio through)
`public inline void `[`set_depth`](#classfx__amplitude__mod_1ac0c2c2ab77761c961cd569d36e26ab17)`(float depth)` | Sets the depth of the amplitude modululator.
`public inline void `[`set_rate_hz`](#classfx__amplitude__mod_1a90b19e7b942c13979bddeba8579813a4)`(float rate_hz)` | Sets the rate of the modulator in Hertz (cycles per second)
`public inline void `[`set_lfo_type`](#classfx__amplitude__mod_1a2561e4ad01e6a629409b59d73a86caf3)`(OSC_TYPES new_type)` | Sets the the type of oscillator used as the LFO.
`public inline void `[`print_params`](#classfx__amplitude__mod_1a62563870f85a17142b545e1e8b718fdf)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__amplitude__mod_1a52c5dce1e56a9efbceb9f0aa572e35d4) {#classfx__amplitude__mod_1a52c5dce1e56a9efbceb9f0aa572e35d4}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__amplitude__mod_1a3ffb0f78f55a24d56ad40ed71b9c3655) {#classfx__amplitude__mod_1a3ffb0f78f55a24d56ad40ed71b9c3655}

Audio routing node: primary audio output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`ext_mod_in`](#classfx__amplitude__mod_1aeedd96b1c4e5e8e1cbf93fb4e134362b) {#classfx__amplitude__mod_1aeedd96b1c4e5e8e1cbf93fb4e134362b}

Audio routing node: external modulator audio input

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__amplitude__mod_1a25ef00aa85c14e895710a505a9c6e0bd) {#classfx__amplitude__mod_1a25ef00aa85c14e895710a505a9c6e0bd}

Control routing node: amplifude modulator depth (should be between 0.0 and 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__amplitude__mod_1ad85024759667cd9decc11e4fb24461ef) {#classfx__amplitude__mod_1ad85024759667cd9decc11e4fb24461ef}

Control routing node: amplitide modulator rate (Hz) (i.e. 1.0 = once per second)

#### `public inline  `[`fx_amplitude_mod`](#classfx__amplitude__mod_1acfe6780b005b6b34ba58e82b9b64cf50)`(float rate_hz,float depth)` {#classfx__amplitude__mod_1acfe6780b005b6b34ba58e82b9b64cf50}

Basic constructor/initializer for amplitude modulator.

#### Parameters
* `modulation_rate` The amp modifier rate in Hertz (cycles / second) 

* `modulation_depth` The amp modifier depth (0.0 is no modulation -> 1.0 is full modulation)

#### `public inline  `[`fx_amplitude_mod`](#classfx__amplitude__mod_1a354b528d3a59d766b7fc3e1ed74427f9)`(float rate_hz,float depth,float initial_phase_deg,OSC_TYPES modulation_type,bool use_ext_modulator)` {#classfx__amplitude__mod_1a354b528d3a59d766b7fc3e1ed74427f9}

Advanced constructor for the amplitude modulator.

#### Parameters
* `rate_hz` The amp modifier rate in Hertz (cycles / second) 

* `depth` The amp modifier depth (0.0 is no modulation -> 1.0 is full modulation) 

* `initial_phase_deg` The initial phase of the oscillator in degrees (0-360)

* `modulation_type` The amp modifier type - see the definition of OSC_TYPES to see the different waveform options 

* `use_ext_modulator` Whether or not to use an externally generated waveform as the modulation source

#### `public inline void `[`enable`](#classfx__amplitude__mod_1a4c21c0e9725c1dd515a2bf0b2fb8f99e)`()` {#classfx__amplitude__mod_1a4c21c0e9725c1dd515a2bf0b2fb8f99e}

Enable the amplitude modululator (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__amplitude__mod_1a5d5ef5ff79e9c553a9ee5116c3dfa516)`()` {#classfx__amplitude__mod_1a5d5ef5ff79e9c553a9ee5116c3dfa516}

Bypass the amplitude modululator (will just pass clean audio through)

#### `public inline void `[`set_depth`](#classfx__amplitude__mod_1ac0c2c2ab77761c961cd569d36e26ab17)`(float depth)` {#classfx__amplitude__mod_1ac0c2c2ab77761c961cd569d36e26ab17}

Sets the depth of the amplitude modululator.

#### Parameters
* `depth` The depth fom 0.0 -> 1.0. 0.0 is no modulation at all, 1.0 is full modulation.

#### `public inline void `[`set_rate_hz`](#classfx__amplitude__mod_1a90b19e7b942c13979bddeba8579813a4)`(float rate_hz)` {#classfx__amplitude__mod_1a90b19e7b942c13979bddeba8579813a4}

Sets the rate of the modulator in Hertz (cycles per second)

#### Parameters
* `rate_hz` The rate hz

#### `public inline void `[`set_lfo_type`](#classfx__amplitude__mod_1a2561e4ad01e6a629409b59d73a86caf3)`(OSC_TYPES new_type)` {#classfx__amplitude__mod_1a2561e4ad01e6a629409b59d73a86caf3}

Sets the the type of oscillator used as the LFO.

#### Parameters
* `new_type` The new type of LFO (OSC_TYPES)

#### `public inline void `[`print_params`](#classfx__amplitude__mod_1a62563870f85a17142b545e1e8b718fdf)`(void)` {#classfx__amplitude__mod_1a62563870f85a17142b545e1e8b718fdf}

Print the parameters for this effect.

# class `fx_audio_node` {#classfx__audio__node}

Class for effects audio node.

Audio nodes are audio inputs and outputs. Audio nodes can exist on an effect (i.e. effect inputs and outputs). Audio nodes can also exist on the canvas (i.e. ADC and DAC channels that are part of the hardware).

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public NODE_DIRECTION `[`node_direction`](#classfx__audio__node_1a1aa7834fa5a1997e77fd98da8f2f1da6) | 
`public bool `[`connected`](#classfx__audio__node_1aebe824913f558d68e6aba6e302c98600) | 
`public char `[`node_name`](#classfx__audio__node_1a2b50a50d563bfe0cfc3dd2136be7f8c4) | 
`public inline  `[`fx_audio_node`](#classfx__audio__node_1ac675c266ef77ec9a6f7422e6486fc4ec)`(NODE_DIRECTION dir,const char * name,fx_effect * p)` | 
`public inline  `[`fx_audio_node`](#classfx__audio__node_1a87c39a22d61b0b6ad358145e87eef6cc)`(NODE_DIRECTION dir,const char * name,fx_canvas * p)` | 
`protected fx_effect * `[`parent_effect`](#classfx__audio__node_1add150e4631e707ba9deb8c2b169e5894) | 
`protected fx_canvas * `[`parent_canvas`](#classfx__audio__node_1a6ac90ff70e761950927b0194b22ef18a) | 

## Members

#### `public NODE_DIRECTION `[`node_direction`](#classfx__audio__node_1a1aa7834fa5a1997e77fd98da8f2f1da6) {#classfx__audio__node_1a1aa7834fa5a1997e77fd98da8f2f1da6}

#### `public bool `[`connected`](#classfx__audio__node_1aebe824913f558d68e6aba6e302c98600) {#classfx__audio__node_1aebe824913f558d68e6aba6e302c98600}

#### `public char `[`node_name`](#classfx__audio__node_1a2b50a50d563bfe0cfc3dd2136be7f8c4) {#classfx__audio__node_1a2b50a50d563bfe0cfc3dd2136be7f8c4}

#### `public inline  `[`fx_audio_node`](#classfx__audio__node_1ac675c266ef77ec9a6f7422e6486fc4ec)`(NODE_DIRECTION dir,const char * name,fx_effect * p)` {#classfx__audio__node_1ac675c266ef77ec9a6f7422e6486fc4ec}

#### `public inline  `[`fx_audio_node`](#classfx__audio__node_1a87c39a22d61b0b6ad358145e87eef6cc)`(NODE_DIRECTION dir,const char * name,fx_canvas * p)` {#classfx__audio__node_1a87c39a22d61b0b6ad358145e87eef6cc}

#### `protected fx_effect * `[`parent_effect`](#classfx__audio__node_1add150e4631e707ba9deb8c2b169e5894) {#classfx__audio__node_1add150e4631e707ba9deb8c2b169e5894}

#### `protected fx_canvas * `[`parent_canvas`](#classfx__audio__node_1a6ac90ff70e761950927b0194b22ef18a) {#classfx__audio__node_1a6ac90ff70e761950927b0194b22ef18a}

# class `fx_biquad_filter` {#classfx__biquad__filter}

```
class fx_biquad_filter
  : public fx_effect
```  

Effect: Biquad filter for implementing various types of filters (low pass, high pass, band pass, etc.)

The biquad filter can be used to create static filters such as equalizers and dynamic filters such as auto-wahs and other interesting swept filtering effects.

Here's a nice video about three different parameters of a biquad: f: cutoff/center frequency, q: filter width, and g: filter gain

<iframe width="560" height="315" src="https://www.youtube.com/embed/uTGU9jkkYwk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__biquad__filter_1a4a9f3a5ff4eac9f44e1378ee23e3211c) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__biquad__filter_1ac4fe4851b422f991882f0f47be3773ab) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__biquad__filter_1a3f44ee6d1f9dbc892a22cecbc63eddd4) | Control routing node: center/critical frequency of the filter in Hz (i.e. 800.0 for 800Hz)
`public `[`fx_control_node`](#classfx__control__node)` * `[`q`](#classfx__biquad__filter_1a4a4821b7190483d41339969237612c04) | Control routing node: width of the filter
`public `[`fx_control_node`](#classfx__control__node)` * `[`gain`](#classfx__biquad__filter_1a76aa6221915b88905f3b45f1cc0f7929) | Control routing node: gain of the filter (used in shelving filters)
`public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1aea807f35dde115fe6897cf96900d2926)`(float filt_freq,float filt_resonance,BIQUAD_FILTER_TYPE filt_type)` | Basic constructor for biquad filter.
`public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1a05c86bf75f906d74fb22d00c42f858e7)`(float filt_freq,float filt_resonance,BIQUAD_FILTER_TYPE filt_type,BIQUAD_FILTER_ORDER order)` | Basic constructor for biquad filter.
`public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1ae0b02c6616a737417bb0037cab6af05c)`(float filt_freq,float filt_resonance,float filter_gain,BIQUAD_FILTER_TYPE filt_type,EFFECT_TRANSITION_SPEED trans_speed)` | Advanced constructor for biquad filter.
`public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1ab8ff8e47928ea9a5df9063ef2686d4aa)`(float filt_freq,float filt_resonance,float filter_gain_db,BIQUAD_FILTER_TYPE filt_type,EFFECT_TRANSITION_SPEED trans_speed,BIQUAD_FILTER_ORDER order)` | Advanced constructor for biquad filter.
`public inline void `[`enable`](#classfx__biquad__filter_1aaf296f748135cba4ec2dcb8eb72ae229)`()` | Enable the biquad filter (it is enabled by default)
`public inline void `[`bypass`](#classfx__biquad__filter_1ae1df4e211ed2861d1dd1c11e88f7af7a)`()` | Bypass the biquad filter (will just pass clean audio through)
`public inline void `[`set_freq`](#classfx__biquad__filter_1ad25d7d137c74ba15ff8aae13772f7691)`(float freq)` | Sets a new cutoff/critical frequency (Hz).
`public inline void `[`set_q`](#classfx__biquad__filter_1aac3600fefd3941a6d829647bdbdbb860)`(float q)` | Sets a new Q factor for the filter. For more information on Q factor, read this: [https://en.wikipedia.org/wiki/Q_factor](https://en.wikipedia.org/wiki/Q_factor).
`public inline void `[`set_resonance`](#classfx__biquad__filter_1a359396b823b55ba5d1f6311e354aaccd)`(float filt_resonance)` | Sets the resonance; 1.0 is none (0.7071)
`public inline void `[`set_gain`](#classfx__biquad__filter_1acb0375ac0044f5938c79868ac0cd4b1d)`(float gain)` | Sets the filter gain. This is only used in shelving filters.
`public inline void `[`print_params`](#classfx__biquad__filter_1a50f5ec518d1656ebcc3bde26b2735a75)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__biquad__filter_1a4a9f3a5ff4eac9f44e1378ee23e3211c) {#classfx__biquad__filter_1a4a9f3a5ff4eac9f44e1378ee23e3211c}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__biquad__filter_1ac4fe4851b422f991882f0f47be3773ab) {#classfx__biquad__filter_1ac4fe4851b422f991882f0f47be3773ab}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__biquad__filter_1a3f44ee6d1f9dbc892a22cecbc63eddd4) {#classfx__biquad__filter_1a3f44ee6d1f9dbc892a22cecbc63eddd4}

Control routing node: center/critical frequency of the filter in Hz (i.e. 800.0 for 800Hz)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`q`](#classfx__biquad__filter_1a4a4821b7190483d41339969237612c04) {#classfx__biquad__filter_1a4a4821b7190483d41339969237612c04}

Control routing node: width of the filter

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`gain`](#classfx__biquad__filter_1a76aa6221915b88905f3b45f1cc0f7929) {#classfx__biquad__filter_1a76aa6221915b88905f3b45f1cc0f7929}

Control routing node: gain of the filter (used in shelving filters)

#### `public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1aea807f35dde115fe6897cf96900d2926)`(float filt_freq,float filt_resonance,BIQUAD_FILTER_TYPE filt_type)` {#classfx__biquad__filter_1aea807f35dde115fe6897cf96900d2926}

Basic constructor for biquad filter.

#### Parameters
* `filt_freq` The filter critical/cutoff frequency 

* `filt_resonance` The filter resonance, 1.0 is standard resonance, > 1.0 is more resonant, < 1.0 is less resonant 

* `filt_type` The filter type, see BIQUAD_FILTER_TYPE for options

#### `public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1a05c86bf75f906d74fb22d00c42f858e7)`(float filt_freq,float filt_resonance,BIQUAD_FILTER_TYPE filt_type,BIQUAD_FILTER_ORDER order)` {#classfx__biquad__filter_1a05c86bf75f906d74fb22d00c42f858e7}

Basic constructor for biquad filter.

#### Parameters
* `filt_freq` The filter critical/cutoff frequency 

* `filt_resonance` The filter resonance, 1.0 is standard resonance, > 1.0 is more resonant, < 1.0 is less resonant 

* `filt_type` The filter type, see BIQUAD_FILTER_TYPE for options 

* `order` The order of the filter (higher = tighter)

#### `public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1ae0b02c6616a737417bb0037cab6af05c)`(float filt_freq,float filt_resonance,float filter_gain,BIQUAD_FILTER_TYPE filt_type,EFFECT_TRANSITION_SPEED trans_speed)` {#classfx__biquad__filter_1ae0b02c6616a737417bb0037cab6af05c}

Advanced constructor for biquad filter.

#### Parameters
* `filt_freq` The filter critical/cutoff frequency 

* `filt_resonance` The filter resonance, 1.0 is standard resonance (0.7071), > 1.0 is more resonant, < 1.0 is less resonant 

* `filter_gain` The filter gain in dB 

* `filt_type` The filter type, see BIQUAD_FILTER_TYPE for options 

* `trans_speed` The transaction speed when new filter parameters are suppliued, see EFFECT_TRANSITION_SPEED for options

#### `public inline  `[`fx_biquad_filter`](#classfx__biquad__filter_1ab8ff8e47928ea9a5df9063ef2686d4aa)`(float filt_freq,float filt_resonance,float filter_gain_db,BIQUAD_FILTER_TYPE filt_type,EFFECT_TRANSITION_SPEED trans_speed,BIQUAD_FILTER_ORDER order)` {#classfx__biquad__filter_1ab8ff8e47928ea9a5df9063ef2686d4aa}

Advanced constructor for biquad filter.

#### Parameters
* `filt_freq` The filter critical/cutoff frequency 

* `filt_resonance` The filter resonance, 1.0 is standard resonance (0.7071), > 1.0 is more resonant, < 1.0 is less resonant 

* `filter_gain_db` The filter gain in dB 

* `filt_type` The filter type, see BIQUAD_FILTER_TYPE for options 

* `trans_speed` The transaction speed when new filter parameters are suppliued, see EFFECT_TRANSITION_SPEED for options 

* `order` The order of the filter (higher = tighter)

#### `public inline void `[`enable`](#classfx__biquad__filter_1aaf296f748135cba4ec2dcb8eb72ae229)`()` {#classfx__biquad__filter_1aaf296f748135cba4ec2dcb8eb72ae229}

Enable the biquad filter (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__biquad__filter_1ae1df4e211ed2861d1dd1c11e88f7af7a)`()` {#classfx__biquad__filter_1ae1df4e211ed2861d1dd1c11e88f7af7a}

Bypass the biquad filter (will just pass clean audio through)

#### `public inline void `[`set_freq`](#classfx__biquad__filter_1ad25d7d137c74ba15ff8aae13772f7691)`(float freq)` {#classfx__biquad__filter_1ad25d7d137c74ba15ff8aae13772f7691}

Sets a new cutoff/critical frequency (Hz).

#### Parameters
* `freq` The new center frequency for the filter in Hz (must be lower than 24000.0)

#### `public inline void `[`set_q`](#classfx__biquad__filter_1aac3600fefd3941a6d829647bdbdbb860)`(float q)` {#classfx__biquad__filter_1aac3600fefd3941a6d829647bdbdbb860}

Sets a new Q factor for the filter. For more information on Q factor, read this: [https://en.wikipedia.org/wiki/Q_factor](https://en.wikipedia.org/wiki/Q_factor).

#### Parameters
* `q` The Q factor (must be between 0.01 and 100.0)

#### `public inline void `[`set_resonance`](#classfx__biquad__filter_1a359396b823b55ba5d1f6311e354aaccd)`(float filt_resonance)` {#classfx__biquad__filter_1a359396b823b55ba5d1f6311e354aaccd}

Sets the resonance; 1.0 is none (0.7071)

#### Parameters
* `resonance` The resonance (must be between 0.01 and 100.0)

#### `public inline void `[`set_gain`](#classfx__biquad__filter_1acb0375ac0044f5938c79868ac0cd4b1d)`(float gain)` {#classfx__biquad__filter_1acb0375ac0044f5938c79868ac0cd4b1d}

Sets the filter gain. This is only used in shelving filters.

#### Parameters
* `gain` The gain in dB

#### `public inline void `[`print_params`](#classfx__biquad__filter_1a50f5ec518d1656ebcc3bde26b2735a75)`(void)` {#classfx__biquad__filter_1a50f5ec518d1656ebcc3bde26b2735a75}

Print the parameters for this effect.

# class `fx_compressor` {#classfx__compressor}

```
class fx_compressor
  : public fx_effect
```  

Effect: Compressor/Limiter.

Here's a nice primer on how compressors work:

<iframe width="560" height="315" src="https://www.youtube.com/embed/8nM5GsNNbyA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

Example: 
```
/**
 * This is an implementation of a typical compressor pedal
 *
 * Left pot: depth - the threshold where compression kicks in
 * Center pot: delay time - the amount to compress after threshold crossed
 * Right pot: type of modulation - output gain
 *
 * Left footswitch: bypass - turns on and off the effect
 * Right footswitch: gain boost - press to double instrument volume when effect engaged
 *
 * This effect uses a tiny amount of the available processing power and memory.
 * It's provided as an example of how to use the various features of the fx_compressor block
 *
 */
#include <dreammakerfx.h>

fx_compressor compressor( -30.0,    // Threshold in dB
                          8,        // Ratio (1:8)
                          10.0,     // Attack (10ms)
                          100.0,    // Release (100ms)
                          2.0);     // Output gain (2x);

void setup() {

  // Initialize the pedal!
  pedal.init();

  // Route audio from instrument -> fx_compressor -> amp
  pedal.route_audio(pedal.instr_in, compressor.input);
  pedal.route_audio(compressor.output, pedal.amp_out);

  // left footswitch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Run this effect
  pedal.run();

}

// Use this to save our gain setting for when gain boost footswitched released
float pot_gain_setting = 0;


void loop() {

  // The right footswitch is being used as a momentary gain boost of 2x
  if (pedal.button_pressed(FOOTSWITCH_RIGHT, true)) {
    compressor.set_output_gain(pot_gain_setting*2.0);
  }
  if (pedal.button_released(FOOTSWITCH_RIGHT, true)) {
    compressor.set_output_gain(pot_gain_setting);
  }

  // Left pot changes threshold from -12dB to -72dB
  if (pedal.pot_left.has_changed()) {
      compressor.set_threshold(-12.0 - (pedal.pot_left.val*60));
  }

  // Center pot sets compression ratio
  if (pedal.pot_center.has_changed()) {
    compressor.set_ratio(pedal.pot_center.val_log*100.0);
  }

  // Right pot controls compressor output gain
  if (pedal.pot_right.has_changed()) {
    pot_gain_setting = pedal.pot_right.val*6;
    compressor.set_output_gain(pot_gain_setting);
  }

  // Service
  pedal.service();

}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__compressor_1a2c22d60ca1e0c7e6f2c45f3e8e8dd437) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__compressor_1a35ca7aaa8bbe1c70112fe9069d35b3d6) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`threshold`](#classfx__compressor_1a42928cf2614b69066cd1ed73d21d80f1) | Control routing node [input]: Compressor/limiter threshold in dB (i.e. -30.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`ratio`](#classfx__compressor_1a15fecdddd6b8410d5ae03779651c0fcf) | Control routing node [input]: Compressor/limiter compression ratio (a value of 100.0 would be a ratio of 1:100)
`public `[`fx_control_node`](#classfx__control__node)` * `[`attack`](#classfx__compressor_1afb966172a248750454f3480bb9d488b7) | Control routing node [input]: Compressor/limiter attack rate in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`release`](#classfx__compressor_1a1197bdfd89e0d4bb9a184a56f40e834e) | Control routing node [input]: Compressor/limiter release rate in milliseconds
`public `[`fx_control_node`](#classfx__control__node)` * `[`out_gain`](#classfx__compressor_1ae7a36bbef9491c451d94d11ff973b1e4) | Control routing node [input]: Compressor/limiter output gain (linear value so a value of 2.0 would double the signal amplitude)
`public inline  `[`fx_compressor`](#classfx__compressor_1a74243ee589778514f32e7b71c30e9ce4)`(float thresh,float ratio,float attack,float release,float gain_out)` | 
`public inline void `[`enable`](#classfx__compressor_1aeba0ed24a0ef7b44fe98a0e23137b638)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__compressor_1ada718d7f67f7ad3632e3ff938cd52fdc)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`set_threshold`](#classfx__compressor_1a4f31a53de17275b2c2e28c285c38a363)`(float threshold)` | 
`public inline void `[`set_ratio`](#classfx__compressor_1a3c369e147e311baeff7e519bfb9f1040)`(float ratio)` | 
`public inline void `[`set_attack`](#classfx__compressor_1a88b69c8c2e6bd7d73ef18f883027102a)`(float attack)` | 
`public inline void `[`set_release`](#classfx__compressor_1aa7c6b0dad11f29b33c307639e9d0781a)`(float release)` | 
`public inline void `[`set_output_gain`](#classfx__compressor_1a475a80b206024c87f6a38c4bf898d6f6)`(float gain_out)` | 
`public inline void `[`print_params`](#classfx__compressor_1aae183cb59a7d0299438a65196d91b213)`(void)` | 

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__compressor_1a2c22d60ca1e0c7e6f2c45f3e8e8dd437) {#classfx__compressor_1a2c22d60ca1e0c7e6f2c45f3e8e8dd437}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__compressor_1a35ca7aaa8bbe1c70112fe9069d35b3d6) {#classfx__compressor_1a35ca7aaa8bbe1c70112fe9069d35b3d6}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`threshold`](#classfx__compressor_1a42928cf2614b69066cd1ed73d21d80f1) {#classfx__compressor_1a42928cf2614b69066cd1ed73d21d80f1}

Control routing node [input]: Compressor/limiter threshold in dB (i.e. -30.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`ratio`](#classfx__compressor_1a15fecdddd6b8410d5ae03779651c0fcf) {#classfx__compressor_1a15fecdddd6b8410d5ae03779651c0fcf}

Control routing node [input]: Compressor/limiter compression ratio (a value of 100.0 would be a ratio of 1:100)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`attack`](#classfx__compressor_1afb966172a248750454f3480bb9d488b7) {#classfx__compressor_1afb966172a248750454f3480bb9d488b7}

Control routing node [input]: Compressor/limiter attack rate in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`release`](#classfx__compressor_1a1197bdfd89e0d4bb9a184a56f40e834e) {#classfx__compressor_1a1197bdfd89e0d4bb9a184a56f40e834e}

Control routing node [input]: Compressor/limiter release rate in milliseconds

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`out_gain`](#classfx__compressor_1ae7a36bbef9491c451d94d11ff973b1e4) {#classfx__compressor_1ae7a36bbef9491c451d94d11ff973b1e4}

Control routing node [input]: Compressor/limiter output gain (linear value so a value of 2.0 would double the signal amplitude)

#### `public inline  `[`fx_compressor`](#classfx__compressor_1a74243ee589778514f32e7b71c30e9ce4)`(float thresh,float ratio,float attack,float release,float gain_out)` {#classfx__compressor_1a74243ee589778514f32e7b71c30e9ce4}

#### `public inline void `[`enable`](#classfx__compressor_1aeba0ed24a0ef7b44fe98a0e23137b638)`()` {#classfx__compressor_1aeba0ed24a0ef7b44fe98a0e23137b638}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__compressor_1ada718d7f67f7ad3632e3ff938cd52fdc)`()` {#classfx__compressor_1ada718d7f67f7ad3632e3ff938cd52fdc}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`set_threshold`](#classfx__compressor_1a4f31a53de17275b2c2e28c285c38a363)`(float threshold)` {#classfx__compressor_1a4f31a53de17275b2c2e28c285c38a363}

#### `public inline void `[`set_ratio`](#classfx__compressor_1a3c369e147e311baeff7e519bfb9f1040)`(float ratio)` {#classfx__compressor_1a3c369e147e311baeff7e519bfb9f1040}

#### `public inline void `[`set_attack`](#classfx__compressor_1a88b69c8c2e6bd7d73ef18f883027102a)`(float attack)` {#classfx__compressor_1a88b69c8c2e6bd7d73ef18f883027102a}

#### `public inline void `[`set_release`](#classfx__compressor_1aa7c6b0dad11f29b33c307639e9d0781a)`(float release)` {#classfx__compressor_1aa7c6b0dad11f29b33c307639e9d0781a}

#### `public inline void `[`set_output_gain`](#classfx__compressor_1a475a80b206024c87f6a38c4bf898d6f6)`(float gain_out)` {#classfx__compressor_1a475a80b206024c87f6a38c4bf898d6f6}

#### `public inline void `[`print_params`](#classfx__compressor_1aae183cb59a7d0299438a65196d91b213)`(void)` {#classfx__compressor_1aae183cb59a7d0299438a65196d91b213}

# class `fx_control_node` {#classfx__control__node}

Class for effects control node.

Control nodes are controller inputs and outputs. Control nodes can exist on effects like an amplitude measurement outupt or delay lenght input. They can also exist in the canvas like a MIDI input or a POT connected to an ADC.

Control nodes are updated at the block level

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public uint8_t `[`param_id`](#classfx__control__node_1a286f2e92d2f6bef439b621db7c767712) | 
`public NODE_DIRECTION `[`node_direction`](#classfx__control__node_1abaf7ac2b3199d83d8bb98298892bca07) | 
`public CTRL_NODE_TYPE `[`node_type`](#classfx__control__node_1a0be42540e1e5c17ffbf21f7c58cd9a1f) | 
`public char `[`node_name`](#classfx__control__node_1aef710a77536a268c4897617475430378) | 
`public bool `[`connected`](#classfx__control__node_1a332ab53d6d5ee80df55d5a59d99e687d) | 
`public inline  `[`fx_control_node`](#classfx__control__node_1a6eeaf3b33ed1c20f104b35763e625faf)`(NODE_DIRECTION dir,CTRL_NODE_TYPE type,const char * name,fx_effect * p,uint8_t ctrl_param_id)` | 
`public inline  `[`fx_control_node`](#classfx__control__node_1a0ae8af9a07689cdbd850dcd9cca3ff63)`(NODE_DIRECTION dir,CTRL_NODE_TYPE type,const char * name,fx_canvas * p,uint8_t ctrl_param_id)` | 
`protected fx_effect * `[`parent_effect`](#classfx__control__node_1acbbacde24b1fca07b855c6ef226dc00e) | 
`protected fx_canvas * `[`parent_canvas`](#classfx__control__node_1a375a038dadc665c4604a72d5c30448a5) | 

## Members

#### `public uint8_t `[`param_id`](#classfx__control__node_1a286f2e92d2f6bef439b621db7c767712) {#classfx__control__node_1a286f2e92d2f6bef439b621db7c767712}

#### `public NODE_DIRECTION `[`node_direction`](#classfx__control__node_1abaf7ac2b3199d83d8bb98298892bca07) {#classfx__control__node_1abaf7ac2b3199d83d8bb98298892bca07}

#### `public CTRL_NODE_TYPE `[`node_type`](#classfx__control__node_1a0be42540e1e5c17ffbf21f7c58cd9a1f) {#classfx__control__node_1a0be42540e1e5c17ffbf21f7c58cd9a1f}

#### `public char `[`node_name`](#classfx__control__node_1aef710a77536a268c4897617475430378) {#classfx__control__node_1aef710a77536a268c4897617475430378}

#### `public bool `[`connected`](#classfx__control__node_1a332ab53d6d5ee80df55d5a59d99e687d) {#classfx__control__node_1a332ab53d6d5ee80df55d5a59d99e687d}

#### `public inline  `[`fx_control_node`](#classfx__control__node_1a6eeaf3b33ed1c20f104b35763e625faf)`(NODE_DIRECTION dir,CTRL_NODE_TYPE type,const char * name,fx_effect * p,uint8_t ctrl_param_id)` {#classfx__control__node_1a6eeaf3b33ed1c20f104b35763e625faf}

#### `public inline  `[`fx_control_node`](#classfx__control__node_1a0ae8af9a07689cdbd850dcd9cca3ff63)`(NODE_DIRECTION dir,CTRL_NODE_TYPE type,const char * name,fx_canvas * p,uint8_t ctrl_param_id)` {#classfx__control__node_1a0ae8af9a07689cdbd850dcd9cca3ff63}

#### `protected fx_effect * `[`parent_effect`](#classfx__control__node_1acbbacde24b1fca07b855c6ef226dc00e) {#classfx__control__node_1acbbacde24b1fca07b855c6ef226dc00e}

#### `protected fx_canvas * `[`parent_canvas`](#classfx__control__node_1a375a038dadc665c4604a72d5c30448a5) {#classfx__control__node_1a375a038dadc665c4604a72d5c30448a5}

# class `fx_delay` {#classfx__delay}

```
class fx_delay
  : public fx_effect
```  

Effect: Delay/echo.

This is basically an echo effect.

<iframe width="560" height="315" src="https://www.youtube.com/embed/E36AkCAzGWo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

Example: 
```
/**
 * This is an implementation of a typical delay / echo pedal.   
 * 
 * Left pot: "feedback" - basically how long the echo lasts before dying out
 * Center pot: delay time - how far apart the echos are (0.1 to 3 seconds)
 * Right pot: wet/dry mix - the mix of clean audio and the echo effect
 * 
 * Left footswitch: bypass - turns on and off the effect
 * Right footswitch: tap - tap it a few times at a set interval and the delay will lock on
 * 
 * This effect uses a tiny amount of the available processing power and memory.
 * It's provided as an example of how to use the various features of the fx_delay block
 * 
 * 
 */
#include <dreammakerfx.h>

fx_delay    my_delay(3000.0,  // 3000 ms / 3 seconds
                     0.6);    // 0.6 feedback ratio

void setup() {
  // put your setup code here, to run once:

  // Initialize the pedal!
  pedal.init();

  // Route audio from instrument -> my_delay -> amp
  pedal.route_audio(pedal.instr_in, my_delay.input);
  pedal.route_audio(my_delay.output, pedal.amp_out);

  // left footswitch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Right foot switch is tap delay length
  pedal.add_tap_interval_button(FOOTSWITCH_RIGHT, true);

  pedal.run();
}

void loop() {

  // If new delay time has been tapped in, use that
  if (pedal.new_tap_interval()) { 
    my_delay.set_length_ms(pedal.get_tap_interval_ms());
  } 

  // Left pot changes the feedback of the delay (determining how long the echoes last)
  if (pedal.pot_left.has_changed()) {
    my_delay.set_feedback(pedal.pot_left.val);
  }
  
  // Right pot changes the wet / dry mix
  if (pedal.pot_right.has_changed()) {
    my_delay.set_dry_mix(1.0 - pedal.pot_right.val);
    my_delay.set_wet_mix(pedal.pot_right.val);
  }  
  
  // Center pot can also be used to change the delay length 
  // from 100ms to 3000ms
  if (pedal.pot_center.has_changed()) {
    float new_length_ms = 100.0 + pedal.pot_center.val*2900.0;
    my_delay.set_length_ms(new_length_ms);
    pedal.set_tap_blink_rate_ms(new_length_ms);
  }    
  
  // Service pedal
  pedal.service();
}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__delay_1a07652b9b855e12f74705811f65670068) | Audio routing node [input]: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__delay_1aa247832fc523f7a1d82dcd94e0c46757) | Audio routing node [output]: primary audio output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`fx_send`](#classfx__delay_1a47d0604757c9fae775e9dc1d0c8e0c43) | Audio routing node [output]: effect loop send before entering delay line of this effect
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`fx_receive`](#classfx__delay_1a48f73cc2af7f37afde7a96e885961d4a) | Audio routing node [output]: effect loop return before entering delay line of this effect
`public `[`fx_control_node`](#classfx__control__node)` * `[`length_ms`](#classfx__delay_1ab3ab27196c40eaae2fc8f874642eca50) | Control routing node [input]: Length of delay line in milliseconds (1/1000s of a second)
`public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__delay_1a632917c322f068445ab1772877b24661) | Control routing node [input]: Feedback ratio (between 0.0 and 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`dry_mix`](#classfx__delay_1a38c230d5672d588c699b514f2dcbac39) | Control routing node [input]: Dry mix (between 0.0 and 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`wet_mix`](#classfx__delay_1a6f3bbdd01c6153ad211f12b122fe05bb) | Control routing node [input]: Wet mix (between 0.0 and 1.0)
`public inline  `[`fx_delay`](#classfx__delay_1aac7eb3b50aeb93b9938456ca659e7cd4)`(float delay_len_ms,float feedback)` | Basic constructor for delay effect.
`public inline  `[`fx_delay`](#classfx__delay_1ae7412fb1c040a2b1b2b515d32cf3513a)`(float delay_len_ms,float delay_len_max_ms,float feedback,float mix_dry,float mix_wet,bool enable_ext_fx)` | Advanced constructor for delay effect.
`public inline void `[`enable`](#classfx__delay_1aa2b2f620ddfa1b85800aadc764a07f6f)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__delay_1a01012a63d6c8ea4536f6b3dfbab32e73)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`set_length_ms`](#classfx__delay_1ad2712b329a719dad80041f63cd5c39e1)`(float len_ms)` | Update the length of the delay.
`public inline void `[`set_feedback`](#classfx__delay_1a27d2959ee0ad5ec9abfce93df89c865c)`(float feedback)` | Updates the feedback parameter of the delay.
`public inline void `[`set_dry_mix`](#classfx__delay_1a21441b57577d8996d5500a5d15a79afc)`(float dry_mix)` | Updates the dry / clean mix of the delay (0.0 to 1.0)
`public inline void `[`set_wet_mix`](#classfx__delay_1a0e7a8f0f8276ff4b0c1cfad589bd30b5)`(float wet_mix)` | Updates the wet / delay mix of the delay (0.0 to 1.0)
`public inline void `[`print_params`](#classfx__delay_1a0982e31da3096ac3d850e71eca18f6fc)`(void)` | Prints the parameters for the delay effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__delay_1a07652b9b855e12f74705811f65670068) {#classfx__delay_1a07652b9b855e12f74705811f65670068}

Audio routing node [input]: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__delay_1aa247832fc523f7a1d82dcd94e0c46757) {#classfx__delay_1aa247832fc523f7a1d82dcd94e0c46757}

Audio routing node [output]: primary audio output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`fx_send`](#classfx__delay_1a47d0604757c9fae775e9dc1d0c8e0c43) {#classfx__delay_1a47d0604757c9fae775e9dc1d0c8e0c43}

Audio routing node [output]: effect loop send before entering delay line of this effect

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`fx_receive`](#classfx__delay_1a48f73cc2af7f37afde7a96e885961d4a) {#classfx__delay_1a48f73cc2af7f37afde7a96e885961d4a}

Audio routing node [output]: effect loop return before entering delay line of this effect

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`length_ms`](#classfx__delay_1ab3ab27196c40eaae2fc8f874642eca50) {#classfx__delay_1ab3ab27196c40eaae2fc8f874642eca50}

Control routing node [input]: Length of delay line in milliseconds (1/1000s of a second)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__delay_1a632917c322f068445ab1772877b24661) {#classfx__delay_1a632917c322f068445ab1772877b24661}

Control routing node [input]: Feedback ratio (between 0.0 and 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`dry_mix`](#classfx__delay_1a38c230d5672d588c699b514f2dcbac39) {#classfx__delay_1a38c230d5672d588c699b514f2dcbac39}

Control routing node [input]: Dry mix (between 0.0 and 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`wet_mix`](#classfx__delay_1a6f3bbdd01c6153ad211f12b122fe05bb) {#classfx__delay_1a6f3bbdd01c6153ad211f12b122fe05bb}

Control routing node [input]: Wet mix (between 0.0 and 1.0)

#### `public inline  `[`fx_delay`](#classfx__delay_1aac7eb3b50aeb93b9938456ca659e7cd4)`(float delay_len_ms,float feedback)` {#classfx__delay_1aac7eb3b50aeb93b9938456ca659e7cd4}

Basic constructor for delay effect.

#### Parameters
* `delay_len_ms` The length of the delay in milliseconds (1/1000s of a second) 

* `feedback` The feedback ration (between 0.0 and 1.0)

#### `public inline  `[`fx_delay`](#classfx__delay_1ae7412fb1c040a2b1b2b515d32cf3513a)`(float delay_len_ms,float delay_len_max_ms,float feedback,float mix_dry,float mix_wet,bool enable_ext_fx)` {#classfx__delay_1ae7412fb1c040a2b1b2b515d32cf3513a}

Advanced constructor for delay effect.

#### Parameters
* `delay_len_ms` The length of the delay in milliseconds (1/1000s of a second) 

* `delay_len_max_ms` The maximum length of the delay (if the delay length is modified) 

* `feedback` The feedback ration (between 0.0 and 1.0) 

* `feedthrough` The delay feed through ratio (between 0.0 and 1.0) 

* `enable_ext_fx` Enable the send/receive FX loop

#### `public inline void `[`enable`](#classfx__delay_1aa2b2f620ddfa1b85800aadc764a07f6f)`()` {#classfx__delay_1aa2b2f620ddfa1b85800aadc764a07f6f}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__delay_1a01012a63d6c8ea4536f6b3dfbab32e73)`()` {#classfx__delay_1a01012a63d6c8ea4536f6b3dfbab32e73}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`set_length_ms`](#classfx__delay_1ad2712b329a719dad80041f63cd5c39e1)`(float len_ms)` {#classfx__delay_1ad2712b329a719dad80041f63cd5c39e1}

Update the length of the delay.

Note, if you used the simple constructor, the length of the delay needs to be less than or equal to the initial delay value. If you want the ability to set a longer delay than the initial value, use the advanced constructor as this will allow you to also specify the total amount of delay space to allocate which is then the maximum length of a delay.

#### `public inline void `[`set_feedback`](#classfx__delay_1a27d2959ee0ad5ec9abfce93df89c865c)`(float feedback)` {#classfx__delay_1a27d2959ee0ad5ec9abfce93df89c865c}

Updates the feedback parameter of the delay.

#### `public inline void `[`set_dry_mix`](#classfx__delay_1a21441b57577d8996d5500a5d15a79afc)`(float dry_mix)` {#classfx__delay_1a21441b57577d8996d5500a5d15a79afc}

Updates the dry / clean mix of the delay (0.0 to 1.0)

#### `public inline void `[`set_wet_mix`](#classfx__delay_1a0e7a8f0f8276ff4b0c1cfad589bd30b5)`(float wet_mix)` {#classfx__delay_1a0e7a8f0f8276ff4b0c1cfad589bd30b5}

Updates the wet / delay mix of the delay (0.0 to 1.0)

#### `public inline void `[`print_params`](#classfx__delay_1a0982e31da3096ac3d850e71eca18f6fc)`(void)` {#classfx__delay_1a0982e31da3096ac3d850e71eca18f6fc}

Prints the parameters for the delay effect.

# class `fx_destructor` {#classfx__destructor}

```
class fx_destructor
  : public fx_effect
```  

Effect: Destructor - provides various types of hard and soft destructors for creating different types of distortions.

Here's a nice summary of clipping using polynomials to create various types of distortions topic: [http://sites.music.columbia.edu/cmc/music-dsp/FAQs/guitar_distortion_FAQ.html](http://sites.music.columbia.edu/cmc/music-dsp/FAQs/guitar_distortion_FAQ.html)

Example: 
```
/**
 * This is an implementation of a basic distortion pedal
 *
 * Left pot: depth - the threshold where compression kicks in
 * Center pot: delay time - the amount to compress after threshold crossed
 * Right pot: type of modulation - output gain
 *
 * Left footswitch: bypass - turns on and off the effect
 * Right footswitch: drive boost - hold down to set drive to max
 *
 * This effect uses a tiny amount of the available processing power and memory.
 * It's provided as an example of how to use the various features of the fx_compressor block
 *
 */
#include <dreammakerfx.h>

fx_destructor       destruct(0.1,           // Clipping level (from 0 to 1.0) - lower is heavier distortion
                             4.0,           // Input drive
                             SMOOTH_CLIP);  // Distortion function = fuzz

fx_biquad_filter    tone_filter(800.0,              // Initial filter cutoff freq
                                1.0,                // Standard resonance
                                BIQUAD_TYPE_BPF);   // Filter type is bandpass


fx_gain             out_gain(1.0);
void setup() {
  // put your setup code here, to run once:

  // Initialize the pedal!
  pedal.init(true, true);

  // Route audio through distortion, tone filter and then output gain
  pedal.route_audio(pedal.instr_in, destruct.input);
  pedal.route_audio(destruct.output, tone_filter.input);
  pedal.route_audio(tone_filter.output, out_gain.input);
  pedal.route_audio(out_gain.output, pedal.amp_out);

  // left footswitch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Run this effect
  pedal.run();

}

float pot_drive = 1.0;
void loop() {

  // When right footswitch is pressed, max drive!
  if (pedal.button_pressed(FOOTSWITCH_RIGHT, true)) {
    destruct.set_param_2(16);
  }
  if (pedal.button_released(FOOTSWITCH_RIGHT, true)) {
    destruct.set_param_2(pot_drive);
  }

  // Left pot is distortion drive
  if (pedal.pot_left.has_changed()) {
    pot_drive = 1 + pedal.pot_left.val_log*16.0;
    destruct.set_param_2(pot_drive);
  }

  // Center pot is tone knob from 200 to 1200Hz
  if (pedal.pot_center.has_changed()) {
    tone_filter.set_freq(200.0 + pedal.pot_center.val*1400.0);
  }

  // Right pot is out gain
  if (pedal.pot_right.has_changed()) {
    out_gain.set_gain(0.3333 + pedal.pot_right.val*3.0);
  }

  // Run pedal service to take care of stuff
  pedal.service();

}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__destructor_1acfe69ee1186777714f16434dba235f51) | Audio routing node [input]: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__destructor_1a158a2d7421fa46d57cc4ede297a5437e) | Audio routing node [output]: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`param_1`](#classfx__destructor_1a12a568312921f87d35a0dd3f4f8e0bc6) | Control routing node [input]: clipping threshold (0.0 -> 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`param_2`](#classfx__destructor_1af0f29b6db5fa74a39ce5d6562555acb3) | Control routing node [input]: input drive multiplier before destructor (up to 64.0)
`public inline  `[`fx_destructor`](#classfx__destructor_1a4e0e00623681636a95b1533fa4a9753d)`(float param_1,float param_2,DESTRUCTOR_TYPE clip_type)` | Basic constructor for the destructor.
`public inline  `[`fx_destructor`](#classfx__destructor_1a18bf3bcfe2a035859b01e201c2240859)`(float param_1,float param_2,DESTRUCTOR_TYPE clip_type,bool upsample)` | Advanced constructor for the destructor.
`public inline void `[`enable`](#classfx__destructor_1ae6508408f362e499ef10e38d4d717b9e)`()` | Enable the destructor (it is enabled by default)
`public inline void `[`bypass`](#classfx__destructor_1a055f88b1889bba2f78b641fda272d96a)`()` | Bypass the destructor (will just pass clean audio through)
`public inline void `[`set_param_1`](#classfx__destructor_1a4b6f0afb22d356a234b4ec9f5f663af7)`(float new_param_1)` | Sets the clipping threshold.
`public inline void `[`set_param_2`](#classfx__destructor_1ab59713631500f1d26b32eed43d56b758)`(float new_param_2)` | Sets the input drive before the destructor.
`public inline void `[`print_params`](#classfx__destructor_1afad28fe3b74e9866b03558bcfa6b9bb6)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__destructor_1acfe69ee1186777714f16434dba235f51) {#classfx__destructor_1acfe69ee1186777714f16434dba235f51}

Audio routing node [input]: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__destructor_1a158a2d7421fa46d57cc4ede297a5437e) {#classfx__destructor_1a158a2d7421fa46d57cc4ede297a5437e}

Audio routing node [output]: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`param_1`](#classfx__destructor_1a12a568312921f87d35a0dd3f4f8e0bc6) {#classfx__destructor_1a12a568312921f87d35a0dd3f4f8e0bc6}

Control routing node [input]: clipping threshold (0.0 -> 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`param_2`](#classfx__destructor_1af0f29b6db5fa74a39ce5d6562555acb3) {#classfx__destructor_1af0f29b6db5fa74a39ce5d6562555acb3}

Control routing node [input]: input drive multiplier before destructor (up to 64.0)

#### `public inline  `[`fx_destructor`](#classfx__destructor_1a4e0e00623681636a95b1533fa4a9753d)`(float param_1,float param_2,DESTRUCTOR_TYPE clip_type)` {#classfx__destructor_1a4e0e00623681636a95b1533fa4a9753d}

Basic constructor for the destructor.

#### Parameters
* `param_1` The first parameter of the destructor (varies by destructor type) 

* `param_2` The second parameter of the destructor (varies by destructor type) 

* `clip_type` Destructor function; See `DESTRUCTOR_TYPE` in Special parameters and constants

#### `public inline  `[`fx_destructor`](#classfx__destructor_1a18bf3bcfe2a035859b01e201c2240859)`(float param_1,float param_2,DESTRUCTOR_TYPE clip_type,bool upsample)` {#classfx__destructor_1a18bf3bcfe2a035859b01e201c2240859}

Advanced constructor for the destructor.

#### Parameters
* `param_1` The first parameter of the destructor (varies by destructor type) 

* `param_2` The second parameter of the destructor (varies by destructor type) 

* `clip_type` Destructor function; See `DESTRUCTOR_TYPE` in Special parameters and constants 

* `upsample` When set to true, the input signal is upsampled to 192kHz before clipping to reduce aliasing of harmonics. This increases the CPU load required but results in a slightly higher quality clipping function

#### `public inline void `[`enable`](#classfx__destructor_1ae6508408f362e499ef10e38d4d717b9e)`()` {#classfx__destructor_1ae6508408f362e499ef10e38d4d717b9e}

Enable the destructor (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__destructor_1a055f88b1889bba2f78b641fda272d96a)`()` {#classfx__destructor_1a055f88b1889bba2f78b641fda272d96a}

Bypass the destructor (will just pass clean audio through)

#### `public inline void `[`set_param_1`](#classfx__destructor_1a4b6f0afb22d356a234b4ec9f5f663af7)`(float new_param_1)` {#classfx__destructor_1a4b6f0afb22d356a234b4ec9f5f663af7}

Sets the clipping threshold.

#### Parameters
* `threshold` The threshold for clipping should be between 0.1 and 1.0. A value of 0.1 will provide aggressive clipping where as a value of 0.8 will provide more gentle clipping.

#### `public inline void `[`set_param_2`](#classfx__destructor_1ab59713631500f1d26b32eed43d56b758)`(float new_param_2)` {#classfx__destructor_1ab59713631500f1d26b32eed43d56b758}

Sets the input drive before the destructor.

#### Parameters
* `drive` The drive a value that the incoming signal will get multiplied by before entering the destructor.

#### `public inline void `[`print_params`](#classfx__destructor_1afad28fe3b74e9866b03558bcfa6b9bb6)`(void)` {#classfx__destructor_1afad28fe3b74e9866b03558bcfa6b9bb6}

Print the parameters for this effect.

# class `fx_envelope_tracker` {#classfx__envelope__tracker}

```
class fx_envelope_tracker
  : public fx_effect
```  

Effect: Envelope tracker.

Here's a nice tutorial on one effect that can be created with an envelope tracker

<iframe width="560" height="315" src="https://www.youtube.com/embed/gFltSCZVqx0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__envelope__tracker_1a90a1db3263c82aa7b59e7292b777bd82) | 
`public `[`fx_control_node`](#classfx__control__node)` * `[`decay_speed_ms`](#classfx__envelope__tracker_1ae8aae7e2034e97ac804e26f7cfa9bfbe) | 
`public `[`fx_control_node`](#classfx__control__node)` * `[`attack_speed_ms`](#classfx__envelope__tracker_1aecc2a5c2cb85119e7120e7e1c1dfa3e5) | 
`public `[`fx_control_node`](#classfx__control__node)` * `[`envelope`](#classfx__envelope__tracker_1a067a4942058fd43727d9c3575bc44eb2) | 
`public inline  `[`fx_envelope_tracker`](#classfx__envelope__tracker_1ae5d434f970e66fb028d6955e4feb5904)`(float attack_speed_ms,float decay_speed_ms,bool triggered)` | 
`public inline void `[`set_attack_speed_ms`](#classfx__envelope__tracker_1adcb2549d59d71a39dff1b39854a3d045)`(float attack_speed_ms)` | 
`public inline void `[`set_decay_speed_ms`](#classfx__envelope__tracker_1a4d6f81bda9887bb96aaa14b974d5d19a)`(float decay_speed_ms)` | 
`public inline void `[`print_params`](#classfx__envelope__tracker_1a7b51364941f46e57860cfbaae1d315db)`(void)` | 

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__envelope__tracker_1a90a1db3263c82aa7b59e7292b777bd82) {#classfx__envelope__tracker_1a90a1db3263c82aa7b59e7292b777bd82}

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`decay_speed_ms`](#classfx__envelope__tracker_1ae8aae7e2034e97ac804e26f7cfa9bfbe) {#classfx__envelope__tracker_1ae8aae7e2034e97ac804e26f7cfa9bfbe}

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`attack_speed_ms`](#classfx__envelope__tracker_1aecc2a5c2cb85119e7120e7e1c1dfa3e5) {#classfx__envelope__tracker_1aecc2a5c2cb85119e7120e7e1c1dfa3e5}

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`envelope`](#classfx__envelope__tracker_1a067a4942058fd43727d9c3575bc44eb2) {#classfx__envelope__tracker_1a067a4942058fd43727d9c3575bc44eb2}

#### `public inline  `[`fx_envelope_tracker`](#classfx__envelope__tracker_1ae5d434f970e66fb028d6955e4feb5904)`(float attack_speed_ms,float decay_speed_ms,bool triggered)` {#classfx__envelope__tracker_1ae5d434f970e66fb028d6955e4feb5904}

#### `public inline void `[`set_attack_speed_ms`](#classfx__envelope__tracker_1adcb2549d59d71a39dff1b39854a3d045)`(float attack_speed_ms)` {#classfx__envelope__tracker_1adcb2549d59d71a39dff1b39854a3d045}

#### `public inline void `[`set_decay_speed_ms`](#classfx__envelope__tracker_1a4d6f81bda9887bb96aaa14b974d5d19a)`(float decay_speed_ms)` {#classfx__envelope__tracker_1a4d6f81bda9887bb96aaa14b974d5d19a}

#### `public inline void `[`print_params`](#classfx__envelope__tracker_1a7b51364941f46e57860cfbaae1d315db)`(void)` {#classfx__envelope__tracker_1a7b51364941f46e57860cfbaae1d315db}

# class `fx_gain` {#classfx__gain}

```
class fx_gain
  : public fx_effect
```  

Effect: Gain - used to increase or decrease the volume of an audio signal.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__gain_1a292efdc7356082aaacf2a79bef496390) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__gain_1adac79db68119e32509a27ee24d1d7c6e) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`gain`](#classfx__gain_1a68685d3f20555db915e64c8a869fcfa7) | Control routing node: gain value input - you can then link the envelope filter to this to create slow swell effects
`public inline  `[`fx_gain`](#classfx__gain_1a2300b426bb620f6197ff600ff5745b00)`(float gain_val)` | Basic constructor/initializer for gain.
`public inline  `[`fx_gain`](#classfx__gain_1ad1818cd57161ec431908add185673057)`(float gain_val,EFFECT_TRANSITION_SPEED gain_trans_speed)` | Advanced constructor for the gain.
`public inline void `[`enable`](#classfx__gain_1ac1432865de90f7dad9e5457c422058b7)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__gain_1a871e0d71dddc9000a26aea56caf2daf6)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`set_gain`](#classfx__gain_1a889982b1829aeea799e2df228363fe81)`(float new_gain)` | Sets the gain multiplier. For example, a value of 2 will double the volume/amplitude and a value of 0.5 will halve the volume/amplitude.
`public inline void `[`set_gain_db`](#classfx__gain_1acd185cb59c54347a8dff85df08c5e749)`(float new_gain_db)` | Sets the gain multiplier using decibles. For example, a value of 0 will keep volume the same, a value of 6 will double the amplitude/volume, a value of -6 will halve the amplitude/volume.
`public inline void `[`print_params`](#classfx__gain_1a6f25cf909faf42ab9b543be6abe780ca)`(void)` | Prints the parameters for the delay effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__gain_1a292efdc7356082aaacf2a79bef496390) {#classfx__gain_1a292efdc7356082aaacf2a79bef496390}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__gain_1adac79db68119e32509a27ee24d1d7c6e) {#classfx__gain_1adac79db68119e32509a27ee24d1d7c6e}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`gain`](#classfx__gain_1a68685d3f20555db915e64c8a869fcfa7) {#classfx__gain_1a68685d3f20555db915e64c8a869fcfa7}

Control routing node: gain value input - you can then link the envelope filter to this to create slow swell effects

#### `public inline  `[`fx_gain`](#classfx__gain_1a2300b426bb620f6197ff600ff5745b00)`(float gain_val)` {#classfx__gain_1a2300b426bb620f6197ff600ff5745b00}

Basic constructor/initializer for gain.

#### Parameters
* `gain_val` The gain value

#### `public inline  `[`fx_gain`](#classfx__gain_1ad1818cd57161ec431908add185673057)`(float gain_val,EFFECT_TRANSITION_SPEED gain_trans_speed)` {#classfx__gain_1ad1818cd57161ec431908add185673057}

Advanced constructor for the gain.

#### Parameters
* `gain_val` The gain value (typically between 0.0->1.0 to make a signal quiter and > 1.0 to make a signal louder) 

* `gain_trans_speed` The gain transaction speed based on `EFFECT_TRANSITION_SPEED` defined above (i.e. slow -> fast)

#### `public inline void `[`enable`](#classfx__gain_1ac1432865de90f7dad9e5457c422058b7)`()` {#classfx__gain_1ac1432865de90f7dad9e5457c422058b7}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__gain_1a871e0d71dddc9000a26aea56caf2daf6)`()` {#classfx__gain_1a871e0d71dddc9000a26aea56caf2daf6}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`set_gain`](#classfx__gain_1a889982b1829aeea799e2df228363fe81)`(float new_gain)` {#classfx__gain_1a889982b1829aeea799e2df228363fe81}

Sets the gain multiplier. For example, a value of 2 will double the volume/amplitude and a value of 0.5 will halve the volume/amplitude.

#### Parameters
* `new_gain` The new gain value (0.0 -> 4.0)

#### `public inline void `[`set_gain_db`](#classfx__gain_1acd185cb59c54347a8dff85df08c5e749)`(float new_gain_db)` {#classfx__gain_1acd185cb59c54347a8dff85df08c5e749}

Sets the gain multiplier using decibles. For example, a value of 0 will keep volume the same, a value of 6 will double the amplitude/volume, a value of -6 will halve the amplitude/volume.

#### Parameters
* `new_gain_db` The new gain value (dB)

#### `public inline void `[`print_params`](#classfx__gain_1a6f25cf909faf42ab9b543be6abe780ca)`(void)` {#classfx__gain_1a6f25cf909faf42ab9b543be6abe780ca}

Prints the parameters for the delay effect.

# class `fx_looper` {#classfx__looper}

```
class fx_looper
  : public fx_effect
```  

Effect: Looper - capture and playback loops.

Here's a nice tutorial on how looper pedals work in general <iframe width="560" height="315" src="https://www.youtube.com/embed/Gd0NhglZWtw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>=""></iframe>

Example: 
```
 #include "dreammmakerfx.h"

/*
This is a basic looper pedal that uses the route_control() function to pass the tapped
loop length along to an echo effect. The echo effect is set to 1/4 the lenght of the loop
so each time a new loop is set, the echo time is updated to.

                +--------+    +-----------+
                |        |    |           |
                |        |    |           |
Instr In +----->+ Looper +--->+   Delay   +-----> Amp Out
                |        |    |           |
                |        |    |           |
                +---+----+    +------+----+
                    |                ^
                    +----------------+
                        loop length

 */
#include <dreammakerfx.h>

fx_looper   loopy( 0.8,   // Dry mix
                   0.8,   // Looped audio mix
                   12,    // Max loop length in seconds
                   false); // Disable FX processing as audio enters the loop

fx_delay    echo(3000,    // Max lenght of 3 seconds
                 0.7 );   // Feedback of 0.7

void setup() {

  // put your setup code here, to run once:
  pedal.init();

  // for template, just pass audio from input to output jack
  pedal.route_audio(pedal.instr_in, loopy.input);
  pedal.route_audio(loopy.output, echo.input);
  pedal.route_audio(echo.output, pedal.amp_out);

  // Connect the tapped loop length of our looper to the delay size and divide by 1/4 and convert to milliseconds (so four echoes per loop)
  pedal.route_control(loopy.loop_length_seconds,
                      echo.length_ms,
                      250.0,        // Scale by 1000 * 1/4 (convert to ms and then divide by 4 so we get four echoes)
                      0);           // Offset = 0


  // Run this effect
  pedal.run();

}

void loop() {


  // Service
  pedal.service();
}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__looper_1a8546e55ec37dbff4aa1f6c6f2dcf8b60) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__looper_1a9fa368775267435ce6d15b566f8cc199) | Audio routing node: primary audio output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`preproc_send`](#classfx__looper_1aac75ac7e57037d128831bff2bcb68513) | Audio routing node: pre-loop effects send (process audio before it ends up in the loop)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`preproc_receive`](#classfx__looper_1aee08a93da19655a0e7c344d0249a49ea) | Audio routing node: pre-loop effects receive (process audio before it ends up in the loop)
`public `[`fx_control_node`](#classfx__control__node)` * `[`start`](#classfx__looper_1ab84b9fa507e67afe22da6a53bc0ff66f) | Control routing node: Trigger to start loop recording
`public `[`fx_control_node`](#classfx__control__node)` * `[`stop`](#classfx__looper_1a9bbdaecb62b28c955f479bd7c6e79bda) | Control routing node: Trigger to stop loop recording
`public `[`fx_control_node`](#classfx__control__node)` * `[`playback_rate`](#classfx__looper_1a597a390c7ef64c1c71a79a0727f1a3ea) | Control routing node: Loop playback rate (1.0 is recorded rate, > 1.0 is faster / higher pitch, < 1.0 is slower, <0 is reverse)
`public `[`fx_control_node`](#classfx__control__node)` * `[`dry_mix`](#classfx__looper_1ad7b7d16ac156eed0178d498870c35801) | Control routing node: clean/dry mix
`public `[`fx_control_node`](#classfx__control__node)` * `[`loop_mix`](#classfx__looper_1ac2d6a671a7a74f01112a632fd5d871a6) | Control routing node: clean/dry mix
`public `[`fx_control_node`](#classfx__control__node)` * `[`loop_length_seconds`](#classfx__looper_1a445745ac04fa40f9a2aa1fd447a65897) | Control routing node: [output] loop length - can be tied to things like delay length to create delay lines that are synced to the loop length
`public `[`fx_control_node`](#classfx__control__node)` * `[`loop_length_seconds_set`](#classfx__looper_1ad4b220fbde6c9ce3803a31aac0c856a3) | Control routing node: [input] loop length - used to set loop length before a loop is recorded (to sync with other loops)
`public inline  `[`fx_looper`](#classfx__looper_1aa2e8fed242f70089c0da68f5867e7006)`(float looper_dry_mix,float looper_loop_mix,float looper_max_length_seconds,bool looper_enable_loop_preprocessing)` | Constructor/initializer for amplitude modulator.
`public inline void `[`enable`](#classfx__looper_1a9c21dc8e4b7407b636c6b46f6072245b)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__looper_1a3d10b14e14d00b4fcad30b9a78fa0468)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`start_loop_recording`](#classfx__looper_1ad554b506c7981908af1eafdf0238ef68)`()` | 
`public inline void `[`stop_loop_recording`](#classfx__looper_1a7ead4d6a0f9e8abf21525c2203e41234)`()` | 
`public inline void `[`stop_loop_playback`](#classfx__looper_1aa09814d95654004c1007c33044652e59)`()` | 
`public inline void `[`set_playback_rate`](#classfx__looper_1af02b19a5487fa9c049cc789ff239d1df)`(float playback_rate)` | 
`public inline void `[`set_loop_mix`](#classfx__looper_1a2b0208ff650d9a78cff1febbe33c552a)`(float new_loop_mix)` | Sets the loop mix.
`public inline void `[`set_dry_mix`](#classfx__looper_1a02af876345bd7dc26a4a0f17fe6facc6)`(float new_dry_mix)` | Sets the dry mix.
`public inline void `[`print_params`](#classfx__looper_1a7f16134ea6c25fcde6d1e2fab601cf37)`(void)` | Prints the parameters for the delay effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__looper_1a8546e55ec37dbff4aa1f6c6f2dcf8b60) {#classfx__looper_1a8546e55ec37dbff4aa1f6c6f2dcf8b60}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__looper_1a9fa368775267435ce6d15b566f8cc199) {#classfx__looper_1a9fa368775267435ce6d15b566f8cc199}

Audio routing node: primary audio output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`preproc_send`](#classfx__looper_1aac75ac7e57037d128831bff2bcb68513) {#classfx__looper_1aac75ac7e57037d128831bff2bcb68513}

Audio routing node: pre-loop effects send (process audio before it ends up in the loop)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`preproc_receive`](#classfx__looper_1aee08a93da19655a0e7c344d0249a49ea) {#classfx__looper_1aee08a93da19655a0e7c344d0249a49ea}

Audio routing node: pre-loop effects receive (process audio before it ends up in the loop)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`start`](#classfx__looper_1ab84b9fa507e67afe22da6a53bc0ff66f) {#classfx__looper_1ab84b9fa507e67afe22da6a53bc0ff66f}

Control routing node: Trigger to start loop recording

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`stop`](#classfx__looper_1a9bbdaecb62b28c955f479bd7c6e79bda) {#classfx__looper_1a9bbdaecb62b28c955f479bd7c6e79bda}

Control routing node: Trigger to stop loop recording

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`playback_rate`](#classfx__looper_1a597a390c7ef64c1c71a79a0727f1a3ea) {#classfx__looper_1a597a390c7ef64c1c71a79a0727f1a3ea}

Control routing node: Loop playback rate (1.0 is recorded rate, > 1.0 is faster / higher pitch, < 1.0 is slower, <0 is reverse)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`dry_mix`](#classfx__looper_1ad7b7d16ac156eed0178d498870c35801) {#classfx__looper_1ad7b7d16ac156eed0178d498870c35801}

Control routing node: clean/dry mix

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`loop_mix`](#classfx__looper_1ac2d6a671a7a74f01112a632fd5d871a6) {#classfx__looper_1ac2d6a671a7a74f01112a632fd5d871a6}

Control routing node: clean/dry mix

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`loop_length_seconds`](#classfx__looper_1a445745ac04fa40f9a2aa1fd447a65897) {#classfx__looper_1a445745ac04fa40f9a2aa1fd447a65897}

Control routing node: [output] loop length - can be tied to things like delay length to create delay lines that are synced to the loop length

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`loop_length_seconds_set`](#classfx__looper_1ad4b220fbde6c9ce3803a31aac0c856a3) {#classfx__looper_1ad4b220fbde6c9ce3803a31aac0c856a3}

Control routing node: [input] loop length - used to set loop length before a loop is recorded (to sync with other loops)

#### `public inline  `[`fx_looper`](#classfx__looper_1aa2e8fed242f70089c0da68f5867e7006)`(float looper_dry_mix,float looper_loop_mix,float looper_max_length_seconds,bool looper_enable_loop_preprocessing)` {#classfx__looper_1aa2e8fed242f70089c0da68f5867e7006}

Constructor/initializer for amplitude modulator.

#### Parameters
* `looper_dry_mix` The looper dry mix 

* `looper_loop_mix` The looper loop mix 

* `looper_max_length_seconds` The looper maximum length seconds 

* `looper_enable_loop_preprocessing` The looper enable loop preprocessing

#### `public inline void `[`enable`](#classfx__looper_1a9c21dc8e4b7407b636c6b46f6072245b)`()` {#classfx__looper_1a9c21dc8e4b7407b636c6b46f6072245b}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__looper_1a3d10b14e14d00b4fcad30b9a78fa0468)`()` {#classfx__looper_1a3d10b14e14d00b4fcad30b9a78fa0468}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`start_loop_recording`](#classfx__looper_1ad554b506c7981908af1eafdf0238ef68)`()` {#classfx__looper_1ad554b506c7981908af1eafdf0238ef68}

#### `public inline void `[`stop_loop_recording`](#classfx__looper_1a7ead4d6a0f9e8abf21525c2203e41234)`()` {#classfx__looper_1a7ead4d6a0f9e8abf21525c2203e41234}

#### `public inline void `[`stop_loop_playback`](#classfx__looper_1aa09814d95654004c1007c33044652e59)`()` {#classfx__looper_1aa09814d95654004c1007c33044652e59}

#### `public inline void `[`set_playback_rate`](#classfx__looper_1af02b19a5487fa9c049cc789ff239d1df)`(float playback_rate)` {#classfx__looper_1af02b19a5487fa9c049cc789ff239d1df}

#### `public inline void `[`set_loop_mix`](#classfx__looper_1a2b0208ff650d9a78cff1febbe33c552a)`(float new_loop_mix)` {#classfx__looper_1a2b0208ff650d9a78cff1febbe33c552a}

Sets the loop mix.

#### Parameters
* `new_loop_mix` The new loop mix value (0.0 -> 1.0)

#### `public inline void `[`set_dry_mix`](#classfx__looper_1a02af876345bd7dc26a4a0f17fe6facc6)`(float new_dry_mix)` {#classfx__looper_1a02af876345bd7dc26a4a0f17fe6facc6}

Sets the dry mix.

#### Parameters
* `new_dry_mix` The new dry mix value (0.0 -> 1.0)

#### `public inline void `[`print_params`](#classfx__looper_1a7f16134ea6c25fcde6d1e2fab601cf37)`(void)` {#classfx__looper_1a7f16134ea6c25fcde6d1e2fab601cf37}

Prints the parameters for the delay effect.

# class `fx_mixer_2` {#classfx__mixer__2}

```
class fx_mixer_2
  : public fx_effect
```  

Utility: 2 channel mixer.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__2_1ac3dd5da659c05886d30025ba81254da8) | Audio routing node [input]: audio input (mixer channel 1)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__2_1a2d60c8289760967e746f43bf3aeddfec) | Audio routing node [input]: audio input (mixer channel 2)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__2_1ac9594cf89c58c8c1e566f4b9efdf9a26) | Audio routing node [output]: mixer output
`public inline  `[`fx_mixer_2`](#classfx__mixer__2_1a7b0f04dd3f2a94ce14b6f1bb4e0c5a02)`(void)` | Simple constructor takes no arguments.
`public inline void `[`print_params`](#classfx__mixer__2_1a223e33aa4ccc94da38b9e43a7e171c1b)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__2_1ac3dd5da659c05886d30025ba81254da8) {#classfx__mixer__2_1ac3dd5da659c05886d30025ba81254da8}

Audio routing node [input]: audio input (mixer channel 1)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__2_1a2d60c8289760967e746f43bf3aeddfec) {#classfx__mixer__2_1a2d60c8289760967e746f43bf3aeddfec}

Audio routing node [input]: audio input (mixer channel 2)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__2_1ac9594cf89c58c8c1e566f4b9efdf9a26) {#classfx__mixer__2_1ac9594cf89c58c8c1e566f4b9efdf9a26}

Audio routing node [output]: mixer output

#### `public inline  `[`fx_mixer_2`](#classfx__mixer__2_1a7b0f04dd3f2a94ce14b6f1bb4e0c5a02)`(void)` {#classfx__mixer__2_1a7b0f04dd3f2a94ce14b6f1bb4e0c5a02}

Simple constructor takes no arguments.

#### `public inline void `[`print_params`](#classfx__mixer__2_1a223e33aa4ccc94da38b9e43a7e171c1b)`(void)` {#classfx__mixer__2_1a223e33aa4ccc94da38b9e43a7e171c1b}

Print the parameters for this effect.

# class `fx_mixer_3` {#classfx__mixer__3}

```
class fx_mixer_3
  : public fx_effect
```  

Utility: 3 channel mixer.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__3_1a517758169a6ef1e81720c9329503bb7a) | Audio routing node [input]: audio input (mixer channel 1)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__3_1a4c5d017dc79d7a30be6600f4a07e5cac) | Audio routing node [input]: audio input (mixer channel 2)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_3`](#classfx__mixer__3_1a189f7d11234f4f3954fdb95a1cafab0c) | Audio routing node [input]: audio input (mixer channel 3)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__3_1aa2f1daf0e3add17a6fa64767842f6ce8) | Audio routing node [output]: mixer output
`public inline  `[`fx_mixer_3`](#classfx__mixer__3_1ae66a67fdf041059f82b28bdd05235402)`(void)` | Simple constructor takes no arguments.
`public inline void `[`print_params`](#classfx__mixer__3_1a0593fdf1d54570a4b719151823e080a5)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__3_1a517758169a6ef1e81720c9329503bb7a) {#classfx__mixer__3_1a517758169a6ef1e81720c9329503bb7a}

Audio routing node [input]: audio input (mixer channel 1)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__3_1a4c5d017dc79d7a30be6600f4a07e5cac) {#classfx__mixer__3_1a4c5d017dc79d7a30be6600f4a07e5cac}

Audio routing node [input]: audio input (mixer channel 2)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_3`](#classfx__mixer__3_1a189f7d11234f4f3954fdb95a1cafab0c) {#classfx__mixer__3_1a189f7d11234f4f3954fdb95a1cafab0c}

Audio routing node [input]: audio input (mixer channel 3)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__3_1aa2f1daf0e3add17a6fa64767842f6ce8) {#classfx__mixer__3_1aa2f1daf0e3add17a6fa64767842f6ce8}

Audio routing node [output]: mixer output

#### `public inline  `[`fx_mixer_3`](#classfx__mixer__3_1ae66a67fdf041059f82b28bdd05235402)`(void)` {#classfx__mixer__3_1ae66a67fdf041059f82b28bdd05235402}

Simple constructor takes no arguments.

#### `public inline void `[`print_params`](#classfx__mixer__3_1a0593fdf1d54570a4b719151823e080a5)`(void)` {#classfx__mixer__3_1a0593fdf1d54570a4b719151823e080a5}

Print the parameters for this effect.

# class `fx_mixer_4` {#classfx__mixer__4}

```
class fx_mixer_4
  : public fx_effect
```  

Utility: 4 channel mixer.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__4_1a3736146eb3b471875b3af416c32a7acc) | Audio routing node [input]: audio input (mixer channel 1)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__4_1ab4b2f4f9850b67626970e9ee11397f07) | Audio routing node [input]: audio input (mixer channel 2)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_3`](#classfx__mixer__4_1ac87286a9ae9a4ba82fb1380c642cdb03) | Audio routing node [input]: audio input (mixer channel 3)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_4`](#classfx__mixer__4_1a4d9758b6bf556cf1895b7444ae4dd9e7) | Audio routing node [input]: audio input (mixer channel 4)
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__4_1ac3dc79fb05062a982e2335dbee8a9f99) | Audio routing node [output]: mixer output
`public inline  `[`fx_mixer_4`](#classfx__mixer__4_1aaa5d6dc5d83074dda5a1ce6f00d45c67)`(void)` | Simple constructor takes no arguments.
`public inline void `[`print_params`](#classfx__mixer__4_1a3f5586bcf1bddd567c41c2fae7ecabdf)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_1`](#classfx__mixer__4_1a3736146eb3b471875b3af416c32a7acc) {#classfx__mixer__4_1a3736146eb3b471875b3af416c32a7acc}

Audio routing node [input]: audio input (mixer channel 1)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_2`](#classfx__mixer__4_1ab4b2f4f9850b67626970e9ee11397f07) {#classfx__mixer__4_1ab4b2f4f9850b67626970e9ee11397f07}

Audio routing node [input]: audio input (mixer channel 2)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_3`](#classfx__mixer__4_1ac87286a9ae9a4ba82fb1380c642cdb03) {#classfx__mixer__4_1ac87286a9ae9a4ba82fb1380c642cdb03}

Audio routing node [input]: audio input (mixer channel 3)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input_4`](#classfx__mixer__4_1a4d9758b6bf556cf1895b7444ae4dd9e7) {#classfx__mixer__4_1a4d9758b6bf556cf1895b7444ae4dd9e7}

Audio routing node [input]: audio input (mixer channel 4)

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__mixer__4_1ac3dc79fb05062a982e2335dbee8a9f99) {#classfx__mixer__4_1ac3dc79fb05062a982e2335dbee8a9f99}

Audio routing node [output]: mixer output

#### `public inline  `[`fx_mixer_4`](#classfx__mixer__4_1aaa5d6dc5d83074dda5a1ce6f00d45c67)`(void)` {#classfx__mixer__4_1aaa5d6dc5d83074dda5a1ce6f00d45c67}

Simple constructor takes no arguments.

#### `public inline void `[`print_params`](#classfx__mixer__4_1a3f5586bcf1bddd567c41c2fae7ecabdf)`(void)` {#classfx__mixer__4_1a3f5586bcf1bddd567c41c2fae7ecabdf}

Print the parameters for this effect.

# class `fx_octave` {#classfx__octave}

```
class fx_octave
  : public fx_effect
```  

Effect: - chops up audio in the time domain and pipes to different effects.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__octave_1afaf86d517e4c1df846c65878e5eb8286) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__octave_1a78e79bf1b3e4f5585a53d4376783fceb) | Audio routing node: primary audio output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`synth_output`](#classfx__octave_1a68f34f8f493ba10b98c0bfa8683645a8) | Audio routing node: synth only raw output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`oct_1_output`](#classfx__octave_1ae3b2f1e055e6c5c30b7f3fe42c7ef75e) | Audio routing node: octave 1 raw output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`oct_2_output`](#classfx__octave_1a2943cab28eecb0eac3f3ec4bb63c951e) | Audio routing node: octave 2 raw output
`public `[`fx_control_node`](#classfx__control__node)` * `[`clean_mix`](#classfx__octave_1adc2d6b1da1af82b46622a72dc084f232) | Control routing node: Clean mix (0.0 -> 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`octave_mix`](#classfx__octave_1ae9fbe75c4c6076219f91eaec1a178844) | Control routing node: Shaper mix (0.0 -> 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`oct_1_mix`](#classfx__octave_1af2f99541ecdf6b798d29f574b3ca9bbf) | Control routing node: Octave below mix (0.0 -> 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`oct_2_mix`](#classfx__octave_1a989bbf38060257de6df644ae2908dca3) | Control routing node: Two octaves below mix (0.0 -> 1.0)
`public inline  `[`fx_octave`](#classfx__octave_1a3eeb7dc1b3e91b6c35a1f21d64ef53a3)`(OSC_TYPES type,float clean_mix,float oct_0_mix,float oct_1_mix,float oct_2_mix)` | Constructor for the octave.
`public inline void `[`enable`](#classfx__octave_1abca5ff95385e0721f8ab2267d7ee3b0d)`()` | Enable the amplitude modululator (it is enabled by default)
`public inline void `[`bypass`](#classfx__octave_1a10164ff7320aa607ce847a8f40bd4292)`()` | Bypass the amplitude modululator (will just pass clean audio through)
`public inline void `[`set_clean_mix`](#classfx__octave_1a22543217b05834576aa61058b9ef913b)`(float clean_mix)` | Sets clean / instrument mix.
`public inline void `[`set_oct_0_mix`](#classfx__octave_1a0d8f8c5669cd8d63e34dcc460c92ee8f)`(float octave_mix)` | Sets the octave 0 (same frequency as incoming signal) mix.
`public inline void `[`set_oct_1_mix`](#classfx__octave_1a1f40b222d1f06a0adb5295e64eb45557)`(float oct_1_mix)` | Sets mix of one octave down.
`public inline void `[`set_oct_2_mix`](#classfx__octave_1a79513b818e794826b7c54e637787e5cb)`(float oct_2_mix)` | Sets mix of two octaves down.
`public inline void `[`set_semitone_shift`](#classfx__octave_1af5493c55f2f654a14dee61ac02180559)`(int semitones_up)` | Sets the semitone shift for all three octave outputs.
`public inline void `[`print_params`](#classfx__octave_1a8952f3107bf0003550fdc5a86ffaab76)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__octave_1afaf86d517e4c1df846c65878e5eb8286) {#classfx__octave_1afaf86d517e4c1df846c65878e5eb8286}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__octave_1a78e79bf1b3e4f5585a53d4376783fceb) {#classfx__octave_1a78e79bf1b3e4f5585a53d4376783fceb}

Audio routing node: primary audio output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`synth_output`](#classfx__octave_1a68f34f8f493ba10b98c0bfa8683645a8) {#classfx__octave_1a68f34f8f493ba10b98c0bfa8683645a8}

Audio routing node: synth only raw output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`oct_1_output`](#classfx__octave_1ae3b2f1e055e6c5c30b7f3fe42c7ef75e) {#classfx__octave_1ae3b2f1e055e6c5c30b7f3fe42c7ef75e}

Audio routing node: octave 1 raw output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`oct_2_output`](#classfx__octave_1a2943cab28eecb0eac3f3ec4bb63c951e) {#classfx__octave_1a2943cab28eecb0eac3f3ec4bb63c951e}

Audio routing node: octave 2 raw output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`clean_mix`](#classfx__octave_1adc2d6b1da1af82b46622a72dc084f232) {#classfx__octave_1adc2d6b1da1af82b46622a72dc084f232}

Control routing node: Clean mix (0.0 -> 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`octave_mix`](#classfx__octave_1ae9fbe75c4c6076219f91eaec1a178844) {#classfx__octave_1ae9fbe75c4c6076219f91eaec1a178844}

Control routing node: Shaper mix (0.0 -> 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`oct_1_mix`](#classfx__octave_1af2f99541ecdf6b798d29f574b3ca9bbf) {#classfx__octave_1af2f99541ecdf6b798d29f574b3ca9bbf}

Control routing node: Octave below mix (0.0 -> 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`oct_2_mix`](#classfx__octave_1a989bbf38060257de6df644ae2908dca3) {#classfx__octave_1a989bbf38060257de6df644ae2908dca3}

Control routing node: Two octaves below mix (0.0 -> 1.0)

#### `public inline  `[`fx_octave`](#classfx__octave_1a3eeb7dc1b3e91b6c35a1f21d64ef53a3)`(OSC_TYPES type,float clean_mix,float oct_0_mix,float oct_1_mix,float oct_2_mix)` {#classfx__octave_1a3eeb7dc1b3e91b6c35a1f21d64ef53a3}

Constructor for the octave.

#### Parameters
* `clean_mix` The clean mix (0.0 -> 1.0) 

* `octave_mix` The octave mix (0.0 -> 1.0) 

* `oct_1_mix` The octal 1 mix (0.0 -> 1.0) 

* `oct_2_mix` The octal 2 mix (0.0 -> 1.0)

#### `public inline void `[`enable`](#classfx__octave_1abca5ff95385e0721f8ab2267d7ee3b0d)`()` {#classfx__octave_1abca5ff95385e0721f8ab2267d7ee3b0d}

Enable the amplitude modululator (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__octave_1a10164ff7320aa607ce847a8f40bd4292)`()` {#classfx__octave_1a10164ff7320aa607ce847a8f40bd4292}

Bypass the amplitude modululator (will just pass clean audio through)

#### `public inline void `[`set_clean_mix`](#classfx__octave_1a22543217b05834576aa61058b9ef913b)`(float clean_mix)` {#classfx__octave_1a22543217b05834576aa61058b9ef913b}

Sets clean / instrument mix.

#### Parameters
* `clean_mix` The clean mix (0.0 to 1.0)

#### `public inline void `[`set_oct_0_mix`](#classfx__octave_1a0d8f8c5669cd8d63e34dcc460c92ee8f)`(float octave_mix)` {#classfx__octave_1a0d8f8c5669cd8d63e34dcc460c92ee8f}

Sets the octave 0 (same frequency as incoming signal) mix.

#### Parameters
* `octave_mix` The octave mix (0.0 to 1.0)

#### `public inline void `[`set_oct_1_mix`](#classfx__octave_1a1f40b222d1f06a0adb5295e64eb45557)`(float oct_1_mix)` {#classfx__octave_1a1f40b222d1f06a0adb5295e64eb45557}

Sets mix of one octave down.

#### Parameters
* `oct_1_mix` The octal 1 mix (0.0 to 1.0)

#### `public inline void `[`set_oct_2_mix`](#classfx__octave_1a79513b818e794826b7c54e637787e5cb)`(float oct_2_mix)` {#classfx__octave_1a79513b818e794826b7c54e637787e5cb}

Sets mix of two octaves down.

#### Parameters
* `oct_2_mix` The octal 2 mix (0.0 to 1.0)

#### `public inline void `[`set_semitone_shift`](#classfx__octave_1af5493c55f2f654a14dee61ac02180559)`(int semitones_up)` {#classfx__octave_1af5493c55f2f654a14dee61ac02180559}

Sets the semitone shift for all three octave outputs.

#### Parameters
* `semitones_up` Number of semitones to shift up or down

#### `public inline void `[`print_params`](#classfx__octave_1a8952f3107bf0003550fdc5a86ffaab76)`(void)` {#classfx__octave_1a8952f3107bf0003550fdc5a86ffaab76}

Print the parameters for this effect.

# class `fx_oscillator` {#classfx__oscillator}

```
class fx_oscillator
  : public fx_effect
```  

Utility: Oscillator that can has both audio and control outputs.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__oscillator_1ad443f83c5e49e2a849e44fadef36bd9f) | Audio routing node: primary audio oscillator output
`public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__oscillator_1aeeb44f7cd3b37d8426de735d765ad992) | Control routing node: frequency of the oscillator in Hz
`public `[`fx_control_node`](#classfx__control__node)` * `[`amplitude`](#classfx__oscillator_1aee2c66fe29de2ec4f47bce0ed77b2445) | Control routing node: amplitude of the oscillator (linear, typically between 0.0 and 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`offset`](#classfx__oscillator_1a97089210c8bfbb4bbd1071699289ad76) | Control routing node: The DC offset of the amplifier. Useful if you're using this to control parameters in ranges not centered around 0.0.
`public `[`fx_control_node`](#classfx__control__node)` * `[`value`](#classfx__oscillator_1a80c56e026c17bea6c0b00b83338e1982) | Control routing node: The current value of the oscillator. Connect this node to external oscillator nodes for effects.
`public inline  `[`fx_oscillator`](#classfx__oscillator_1af7cd903dc9cc687017083aa6abbd24d3)`(OSC_TYPES osc_type,float freq,float amplitude)` | Basic constructor for an oscillator when used as an audio source.
`public inline  `[`fx_oscillator`](#classfx__oscillator_1a6f60a4769a531aca7030a97586d8e6b4)`(OSC_TYPES osc_type,float freq,float amplitude,float initial_phase)` | Basic constructor for an oscillator used as a control source.
`public inline void `[`enable`](#classfx__oscillator_1af8097f269a5e90da896abd8f7e6ef5e2)`()` | Enable the oscillator (it is enabled by default)
`public inline void `[`bypass`](#classfx__oscillator_1a7af21ed9e597c2c00d85dac8d0fc7346)`()` | Bypass the oscillator (it will provide just a constant value)
`public inline void `[`set_frequency`](#classfx__oscillator_1a70f61ffee6744da72ecc8ea3cda9e1ad)`(float freq)` | Upates the frequency in Hz of the current oscillator.
`public inline void `[`set_amplitude`](#classfx__oscillator_1abd4b26763cbf698b21293ebff30d03a2)`(float amplitude)` | Updates the amplitude for the current oscillator.
`public inline void `[`set_oscillator_type`](#classfx__oscillator_1abf8c1deb5e5aebf8243f2712e2613115)`(OSC_TYPES new_type)` | Sets the oscillator type.
`public inline void `[`print_params`](#classfx__oscillator_1a630f9545124147322faea04790240e61)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__oscillator_1ad443f83c5e49e2a849e44fadef36bd9f) {#classfx__oscillator_1ad443f83c5e49e2a849e44fadef36bd9f}

Audio routing node: primary audio oscillator output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__oscillator_1aeeb44f7cd3b37d8426de735d765ad992) {#classfx__oscillator_1aeeb44f7cd3b37d8426de735d765ad992}

Control routing node: frequency of the oscillator in Hz

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`amplitude`](#classfx__oscillator_1aee2c66fe29de2ec4f47bce0ed77b2445) {#classfx__oscillator_1aee2c66fe29de2ec4f47bce0ed77b2445}

Control routing node: amplitude of the oscillator (linear, typically between 0.0 and 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`offset`](#classfx__oscillator_1a97089210c8bfbb4bbd1071699289ad76) {#classfx__oscillator_1a97089210c8bfbb4bbd1071699289ad76}

Control routing node: The DC offset of the amplifier. Useful if you're using this to control parameters in ranges not centered around 0.0.

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`value`](#classfx__oscillator_1a80c56e026c17bea6c0b00b83338e1982) {#classfx__oscillator_1a80c56e026c17bea6c0b00b83338e1982}

Control routing node: The current value of the oscillator. Connect this node to external oscillator nodes for effects.

#### `public inline  `[`fx_oscillator`](#classfx__oscillator_1af7cd903dc9cc687017083aa6abbd24d3)`(OSC_TYPES osc_type,float freq,float amplitude)` {#classfx__oscillator_1af7cd903dc9cc687017083aa6abbd24d3}

Basic constructor for an oscillator when used as an audio source.

#### Parameters
* `osc_type` The osc type (see OSC_TYPES) 

* `freq` The frequency in Hz 

* `amplitude` The amplitude (linear scale e.g. 0.0 -> 1.0 typically)

#### `public inline  `[`fx_oscillator`](#classfx__oscillator_1a6f60a4769a531aca7030a97586d8e6b4)`(OSC_TYPES osc_type,float freq,float amplitude,float initial_phase)` {#classfx__oscillator_1a6f60a4769a531aca7030a97586d8e6b4}

Basic constructor for an oscillator used as a control source.

#### Parameters
* `osc_type` The osc type (see OSC_TYPES) 

* `freq` The frequency in Hz 

* `amplitude` The amplitude (linear scale e.g. 0.0 -> 1.0 typically) 

* `initial` phase The initial phase of the oscillator in degrees (0-360)

#### `public inline void `[`enable`](#classfx__oscillator_1af8097f269a5e90da896abd8f7e6ef5e2)`()` {#classfx__oscillator_1af8097f269a5e90da896abd8f7e6ef5e2}

Enable the oscillator (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__oscillator_1a7af21ed9e597c2c00d85dac8d0fc7346)`()` {#classfx__oscillator_1a7af21ed9e597c2c00d85dac8d0fc7346}

Bypass the oscillator (it will provide just a constant value)

#### `public inline void `[`set_frequency`](#classfx__oscillator_1a70f61ffee6744da72ecc8ea3cda9e1ad)`(float freq)` {#classfx__oscillator_1a70f61ffee6744da72ecc8ea3cda9e1ad}

Upates the frequency in Hz of the current oscillator.

#### Parameters
* `freq` The frequency in Hz

#### `public inline void `[`set_amplitude`](#classfx__oscillator_1abd4b26763cbf698b21293ebff30d03a2)`(float amplitude)` {#classfx__oscillator_1abd4b26763cbf698b21293ebff30d03a2}

Updates the amplitude for the current oscillator.

#### Parameters
* `amplitude` The amplitude (linear)

#### `public inline void `[`set_oscillator_type`](#classfx__oscillator_1abf8c1deb5e5aebf8243f2712e2613115)`(OSC_TYPES new_type)` {#classfx__oscillator_1abf8c1deb5e5aebf8243f2712e2613115}

Sets the oscillator type.

#### Parameters
* `new_type` The new type of oscillator (OSC_TYPES)

#### `public inline void `[`print_params`](#classfx__oscillator_1a630f9545124147322faea04790240e61)`(void)` {#classfx__oscillator_1a630f9545124147322faea04790240e61}

Print the parameters for this effect.

# class `fx_phase_shifter` {#classfx__phase__shifter}

```
class fx_phase_shifter
  : public fx_effect
```  

Effect: Phase shifter for creating rich phase shifts.

Example: **phase_shifter_1.c**

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__phase__shifter_1a6b3c2e7b30e37e8f39f4ea74edcc1da8) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__phase__shifter_1a1516ae9bc8081a37bd4b587cc8cbdbdf) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__phase__shifter_1a09af8400b1ee18ceb91eb0def1d6d58d) | Control routing node: phase shifter depth (should be between 0.0 and 1.0)
`public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__phase__shifter_1aee41f77d8694d6267ae46aff7bafe052) | Control routing node: phase shifter rate (Hz) (i.e. 1.0 = once per second)
`public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__phase__shifter_1ad024eec3755afff22c3d79899a443370) | Control routing node: phase shifter feedback (should be between -1.0 and 1.0)
`public inline  `[`fx_phase_shifter`](#classfx__phase__shifter_1a3a121772ae94e0f4821bbc67349881d3)`(float rate_hz,float depth,float feedback)` | Basic constructor/initializer for the phase shifter.
`public inline  `[`fx_phase_shifter`](#classfx__phase__shifter_1a4acc2b17739a801a72623dd645b1b32c)`(float rate_hz,float depth,float feedback,float inital_phase,OSC_TYPES mod_type)` | Constructs a new instance.
`public inline void `[`enable`](#classfx__phase__shifter_1a02b925c2b19530efcda28486ff7d286a)`()` | Enable the phase shifter (it is enabled by default)
`public inline void `[`bypass`](#classfx__phase__shifter_1a361a5bd72a429333d3e1a0120332c19f)`()` | Bypass the phase shifter (will just pass clean audio through)
`public inline void `[`set_depth`](#classfx__phase__shifter_1a5775686b16e0adf4f44cfc7701a02b68)`(float depth)` | Sets the depth of the phase shifter.
`public inline void `[`set_rate_hz`](#classfx__phase__shifter_1acfdf8c4124e0e95cbaa3e5fbf6b23a9f)`(float rate_hz)` | Sets the rate of the phase shifter in Hertz (cycles per second)
`public inline void `[`set_feedback`](#classfx__phase__shifter_1a48317de95377711857ba1d660bbc4bd7)`(float feedback)` | Sets the feedback of the phase shifter.
`public inline void `[`set_lfo_type`](#classfx__phase__shifter_1a7089c1b4c3fc15c7f274835c345d3abc)`(OSC_TYPES new_type)` | Sets the the type of oscillator used as the LFO.
`public inline void `[`print_params`](#classfx__phase__shifter_1a4bd5e5a813c8b07fba88fb1b689fc25f)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__phase__shifter_1a6b3c2e7b30e37e8f39f4ea74edcc1da8) {#classfx__phase__shifter_1a6b3c2e7b30e37e8f39f4ea74edcc1da8}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__phase__shifter_1a1516ae9bc8081a37bd4b587cc8cbdbdf) {#classfx__phase__shifter_1a1516ae9bc8081a37bd4b587cc8cbdbdf}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__phase__shifter_1a09af8400b1ee18ceb91eb0def1d6d58d) {#classfx__phase__shifter_1a09af8400b1ee18ceb91eb0def1d6d58d}

Control routing node: phase shifter depth (should be between 0.0 and 1.0)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__phase__shifter_1aee41f77d8694d6267ae46aff7bafe052) {#classfx__phase__shifter_1aee41f77d8694d6267ae46aff7bafe052}

Control routing node: phase shifter rate (Hz) (i.e. 1.0 = once per second)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__phase__shifter_1ad024eec3755afff22c3d79899a443370) {#classfx__phase__shifter_1ad024eec3755afff22c3d79899a443370}

Control routing node: phase shifter feedback (should be between -1.0 and 1.0)

#### `public inline  `[`fx_phase_shifter`](#classfx__phase__shifter_1a3a121772ae94e0f4821bbc67349881d3)`(float rate_hz,float depth,float feedback)` {#classfx__phase__shifter_1a3a121772ae94e0f4821bbc67349881d3}

Basic constructor/initializer for the phase shifter.

#### Parameters
* `rate_hz` The rate hz of the LFO modulating the phase shifter 

* `depth` The depth of the phase shifter 

* `feedback` The feedback of the phase shifter

#### `public inline  `[`fx_phase_shifter`](#classfx__phase__shifter_1a4acc2b17739a801a72623dd645b1b32c)`(float rate_hz,float depth,float feedback,float inital_phase,OSC_TYPES mod_type)` {#classfx__phase__shifter_1a4acc2b17739a801a72623dd645b1b32c}

Constructs a new instance.

#### Parameters
* `rate_hz` The rate hz of the LFO modulating the phase shifter 

* `depth` The depth of the phase shifter (0.0 -> 1.0) 

* `feedback` The feedback of the phase shifter (-1.0 -> 1.0) 

* `inital_phase` The inital phase in degrees of the LFO 

* `mod_type` The modifier type (OSC_TYPES)

#### `public inline void `[`enable`](#classfx__phase__shifter_1a02b925c2b19530efcda28486ff7d286a)`()` {#classfx__phase__shifter_1a02b925c2b19530efcda28486ff7d286a}

Enable the phase shifter (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__phase__shifter_1a361a5bd72a429333d3e1a0120332c19f)`()` {#classfx__phase__shifter_1a361a5bd72a429333d3e1a0120332c19f}

Bypass the phase shifter (will just pass clean audio through)

#### `public inline void `[`set_depth`](#classfx__phase__shifter_1a5775686b16e0adf4f44cfc7701a02b68)`(float depth)` {#classfx__phase__shifter_1a5775686b16e0adf4f44cfc7701a02b68}

Sets the depth of the phase shifter.

#### Parameters
* `depth` The depth fom 0.0 -> 1.0. 0.0 is no modulation at all, 1.0 is full modulation.

#### `public inline void `[`set_rate_hz`](#classfx__phase__shifter_1acfdf8c4124e0e95cbaa3e5fbf6b23a9f)`(float rate_hz)` {#classfx__phase__shifter_1acfdf8c4124e0e95cbaa3e5fbf6b23a9f}

Sets the rate of the phase shifter in Hertz (cycles per second)

#### Parameters
* `rate_hz` The rate hz

#### `public inline void `[`set_feedback`](#classfx__phase__shifter_1a48317de95377711857ba1d660bbc4bd7)`(float feedback)` {#classfx__phase__shifter_1a48317de95377711857ba1d660bbc4bd7}

Sets the feedback of the phase shifter.

#### Parameters
* `feedback` Feedback value (between -1.0 and 1.0)

#### `public inline void `[`set_lfo_type`](#classfx__phase__shifter_1a7089c1b4c3fc15c7f274835c345d3abc)`(OSC_TYPES new_type)` {#classfx__phase__shifter_1a7089c1b4c3fc15c7f274835c345d3abc}

Sets the the type of oscillator used as the LFO.

#### Parameters
* `new_type` The new type of LFO (OSC_TYPES)

#### `public inline void `[`print_params`](#classfx__phase__shifter_1a4bd5e5a813c8b07fba88fb1b689fc25f)`(void)` {#classfx__phase__shifter_1a4bd5e5a813c8b07fba88fb1b689fc25f}

Print the parameters for this effect.

# class `fx_pitch_shift` {#classfx__pitch__shift}

```
class fx_pitch_shift
  : public fx_effect
```  

Effect: Pitch shifter - shifts audio up or down in pitch.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__pitch__shift_1aa1388ecdbad1942b8c69e21d4c99ab53) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__pitch__shift_1ae66bfa5587f5e89beba7d94a91f56d75) | Audio routing node: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`freq_shift`](#classfx__pitch__shift_1a969643a1782ac23c0ac6ee4f008f37b8) | 
`public inline  `[`fx_pitch_shift`](#classfx__pitch__shift_1af4f1d9ebd16d16e642d054b46451edea)`(float pitch_shift_freq)` | 
`public inline void `[`enable`](#classfx__pitch__shift_1a6cd1950a881800230a91e35c42419d6d)`()` | Enable the pitch shifter (it is enabled by default)
`public inline void `[`bypass`](#classfx__pitch__shift_1a61e2586e46a2699b9117cd4883027cfd)`()` | Bypass the pitch shifter (will just pass clean audio through)
`public inline void `[`set_freq_shift`](#classfx__pitch__shift_1a63ca200680620c062c66ee065f3a4299)`(float freq_shift)` | Update the pitch shifter value. A freq_shift of 0.5 will drop down one octave. A value of 2.0 will go up one octave. A value of 1.0 will play at current pitch (no shift).
`public inline void `[`print_params`](#classfx__pitch__shift_1aa91b1d28891296a2a4199e8d94c871f3)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__pitch__shift_1aa1388ecdbad1942b8c69e21d4c99ab53) {#classfx__pitch__shift_1aa1388ecdbad1942b8c69e21d4c99ab53}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__pitch__shift_1ae66bfa5587f5e89beba7d94a91f56d75) {#classfx__pitch__shift_1ae66bfa5587f5e89beba7d94a91f56d75}

Audio routing node: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`freq_shift`](#classfx__pitch__shift_1a969643a1782ac23c0ac6ee4f008f37b8) {#classfx__pitch__shift_1a969643a1782ac23c0ac6ee4f008f37b8}

#### `public inline  `[`fx_pitch_shift`](#classfx__pitch__shift_1af4f1d9ebd16d16e642d054b46451edea)`(float pitch_shift_freq)` {#classfx__pitch__shift_1af4f1d9ebd16d16e642d054b46451edea}

#### `public inline void `[`enable`](#classfx__pitch__shift_1a6cd1950a881800230a91e35c42419d6d)`()` {#classfx__pitch__shift_1a6cd1950a881800230a91e35c42419d6d}

Enable the pitch shifter (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__pitch__shift_1a61e2586e46a2699b9117cd4883027cfd)`()` {#classfx__pitch__shift_1a61e2586e46a2699b9117cd4883027cfd}

Bypass the pitch shifter (will just pass clean audio through)

#### `public inline void `[`set_freq_shift`](#classfx__pitch__shift_1a63ca200680620c062c66ee065f3a4299)`(float freq_shift)` {#classfx__pitch__shift_1a63ca200680620c062c66ee065f3a4299}

Update the pitch shifter value. A freq_shift of 0.5 will drop down one octave. A value of 2.0 will go up one octave. A value of 1.0 will play at current pitch (no shift).

#### Parameters
* `freq_shift` The frequency shift

#### `public inline void `[`print_params`](#classfx__pitch__shift_1aa91b1d28891296a2a4199e8d94c871f3)`(void)` {#classfx__pitch__shift_1aa91b1d28891296a2a4199e8d94c871f3}

Print the parameters for this effect.

# class `fx_ring_mod` {#classfx__ring__mod}

```
class fx_ring_mod
  : public fx_effect
```  

Effect: Ring modulator - frequency modulates the audio - crazy sounding.

The following example is a full ring modulator pedal with tone control, wet/dry mix and of course ring modulator.


```
#include <dreammakerfx.h>


fx_ring_mod      ring_mod_1(200.0, // Carrier frequency in Hz
                            0.7);  // Depth 
fx_gain          wet_mix(0.5);
fx_gain          dry_mix(0.5);
fx_biquad_filter ring_mod_tone(500.0, FILTER_WIDTH_MEDIUM, BIQUAD_TYPE_LPF);
fx_mixer_2       wet_dry_mxer;


void setup() {
  
  // Init the effects system
  pedal.init();

  // Route audio through wet channel (ring mod->tone control)
  pedal.route_audio(pedal.instr_in, ring_mod_1.input);
  pedal.route_audio(ring_mod_1.output, ring_mod_tone.input);
  pedal.route_audio(ring_mod_tone.output, wet_dry_mxer.input_1);
  
  // Route audio through dry channel
  pedal.route_audio(pedal.instr_in, dry_mix.input);
  pedal.route_audio(dry_mix.output, wet_dry_mxer.input_2);

  // Mix wet and dry to output
  pedal.route_audio(wet_dry_mxer.output, pedal.amp_out);

  // Run it!
  pedal.run();

}
  
void loop() {

  // Connect Pot 0 to wet dry mix
  if (pedal.pot_0.has_changed()) { 
    wet_mix.set_gain(pedal.pot_0.val);
    dry_mix.set_gain(1.0 - pedal.pot_0.val);
  } 

  // Connect Pot 1 to carrier rate (Hz) from 50.0 to 1000.0Hz
  if (pedal.pot_1.has_changed()) { 
    ring_mod_1.set_freq(950.0 * pedal.pot_1.val+50.0);
  } 

  // Connect Pot 2 to tone
  if (pedal.pot_2.has_changed()) { 
    ring_mod_tone.set_freq((2000 * pedal.pot_2.val) + 500.0);
  } 

  // Service 
  pedal.service();
}


void sw1_pressed() { } 
void sw2_pressed() { }
void sw3_pressed() { }
void sw4_pressed() { }
```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__ring__mod_1aaca095dddcc3928c199203636a5a0b70) | Audio routing node [input]: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__ring__mod_1aef3f3aa115f4f9dc1e553c44c9acd0fd) | Audio routing node [output]: primary audio output
`public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__ring__mod_1a852138ed03580c9783182ad97b203cdf) | Control routing node [input]: the carrier frequency of the ring moduator (Hz)
`public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__ring__mod_1acccb5350e46d71105a62f7339af23c60) | Control routing node [input]: modulation depth
`public inline  `[`fx_ring_mod`](#classfx__ring__mod_1ab06ae2bc1226aee0af243fdb94756d93)`(float ring_mod_freq,float ring_mod_depth)` | 
`public inline void `[`enable`](#classfx__ring__mod_1a10937c8528a0a03bd11bba5ec8589cd0)`()` | Enable the ring modulator (it is enabled by default)
`public inline void `[`bypass`](#classfx__ring__mod_1aa859265613b119a8c1a697ab31e674f5)`()` | Bypass the ring modulator (will just pass clean audio through)
`public inline void `[`set_freq`](#classfx__ring__mod_1afeddeb6ba118f1fcf3b4387b07ef9e59)`(float new_freq)` | Sets the carrier frequency of the ring moduator (Hz)
`public inline void `[`set_depth`](#classfx__ring__mod_1a960d140ad93acf973dd57e3fd5055b5e)`(float new_depth)` | Sets the depth of the ring modulator (0.0 -> 1.0)
`public inline void `[`print_params`](#classfx__ring__mod_1a5fbb19b69e4fa7ebd16b22e541a664cd)`(void)` | Prints the parameters for the delay effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__ring__mod_1aaca095dddcc3928c199203636a5a0b70) {#classfx__ring__mod_1aaca095dddcc3928c199203636a5a0b70}

Audio routing node [input]: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__ring__mod_1aef3f3aa115f4f9dc1e553c44c9acd0fd) {#classfx__ring__mod_1aef3f3aa115f4f9dc1e553c44c9acd0fd}

Audio routing node [output]: primary audio output

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`freq`](#classfx__ring__mod_1a852138ed03580c9783182ad97b203cdf) {#classfx__ring__mod_1a852138ed03580c9783182ad97b203cdf}

Control routing node [input]: the carrier frequency of the ring moduator (Hz)

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__ring__mod_1acccb5350e46d71105a62f7339af23c60) {#classfx__ring__mod_1acccb5350e46d71105a62f7339af23c60}

Control routing node [input]: modulation depth

#### `public inline  `[`fx_ring_mod`](#classfx__ring__mod_1ab06ae2bc1226aee0af243fdb94756d93)`(float ring_mod_freq,float ring_mod_depth)` {#classfx__ring__mod_1ab06ae2bc1226aee0af243fdb94756d93}

#### `public inline void `[`enable`](#classfx__ring__mod_1a10937c8528a0a03bd11bba5ec8589cd0)`()` {#classfx__ring__mod_1a10937c8528a0a03bd11bba5ec8589cd0}

Enable the ring modulator (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__ring__mod_1aa859265613b119a8c1a697ab31e674f5)`()` {#classfx__ring__mod_1aa859265613b119a8c1a697ab31e674f5}

Bypass the ring modulator (will just pass clean audio through)

#### `public inline void `[`set_freq`](#classfx__ring__mod_1afeddeb6ba118f1fcf3b4387b07ef9e59)`(float new_freq)` {#classfx__ring__mod_1afeddeb6ba118f1fcf3b4387b07ef9e59}

Sets the carrier frequency of the ring moduator (Hz)

#### Parameters
* `new_freq` The new frequency

#### `public inline void `[`set_depth`](#classfx__ring__mod_1a960d140ad93acf973dd57e3fd5055b5e)`(float new_depth)` {#classfx__ring__mod_1a960d140ad93acf973dd57e3fd5055b5e}

Sets the depth of the ring modulator (0.0 -> 1.0)

#### Parameters
* `new_depth` The new depth

#### `public inline void `[`print_params`](#classfx__ring__mod_1a5fbb19b69e4fa7ebd16b22e541a664cd)`(void)` {#classfx__ring__mod_1a5fbb19b69e4fa7ebd16b22e541a664cd}

Prints the parameters for the delay effect.

# class `fx_slicer` {#classfx__slicer}

```
class fx_slicer
  : public fx_effect
```  

Effect: Slicer - chops up audio in the time domain and pipes to different effects.

Example: 
```
/*

 The slicer switches between output channels at a predefined rate.  It is 
 great for creating interesting rhymic effects.  This effect sends each channel
 of the slicer through band-pass filters that are tuned to different center
 frequencies.  The outputs of the filters are then mixed together using a 
 simple 4 channel mixer.
  
               +------------+   +-------------+   +---------+
               |            +-->+ BPF @ 200Hz +-->+         |
               |            |   +-------------+   |         |
               |            |   +-------------+   |         |
               |            +-->+ BPF @ 1200Hz+-->+         |
Instr In +---->+ Slicer x 4 |   +-------------+   | Mixer4  +----> Amp Out
               |            |   +-------------+   |         |
               |            +-->+ BPF @ 500Hz +-->+         |
               |            |   +-------------+   |         |
               |            |   +-------------+   |         |
               |            +-->+ BPF @ 800Hz +-->+         |
               +------------+   +-------------+   +---------+

 */
#include  <dreammakerfx.com>

      
// Set up a slicer for four channels
fx_slicer   slice4(1000.0, 4);

// Instances of the four bandpass (BPF) filters at different frequencies
fx_biquad_filter  filt1(200, FILTER_WIDTH_NARROW, BIQUAD_TYPE_BPF);
fx_biquad_filter  filt2(1000, FILTER_WIDTH_NARROW, BIQUAD_TYPE_BPF);
fx_biquad_filter  filt3(500, FILTER_WIDTH_NARROW, BIQUAD_TYPE_BPF);
fx_biquad_filter  filt4(800, FILTER_WIDTH_NARROW, BIQUAD_TYPE_BPF);
fx_mixer_4 mix4;

bool go = false;
bool running = false;

void setup() {

  pedal.init();

  pedal.route_audio(pedal.instr_in, slice4.input);
  
  pedal.route_audio(slice4.output_1, filt1.input);
  pedal.route_audio(slice4.output_2, filt2.input);
  pedal.route_audio(slice4.output_3, filt3.input);
  pedal.route_audio(slice4.output_4, filt4.input);

  pedal.route_audio(filt1.output, mix4.input_1);
  pedal.route_audio(filt2.output, mix4.input_2);
  pedal.route_audio(filt3.output, mix4.input_3);
  pedal.route_audio(filt4.output, mix4.input_4);
  
  pedal.route_audio(mix4.output, pedal.amp_out);

  // Optional code to print out the routing details to console
  if (true) {
    pedal.print_instance_stack();
    pedal.print_routing_table();
    pedal.print_param_tables();
  }

  // Run this effect
  pedal.run(); 

}

void loop() {

  static int now = millis();

  // Run pedal service to take care of stuff
  pedal.service();

  // Set period of slicer from 100ms through 3 seconds
  if (pedal.pot_0.has_changed()) {
    slice4.set_period_ms(100.0 + 3000.0 * (1.0 - pedal.pot_0.val));
  }

  if (pedal.pot_1.has_changed()) {
  }
  
  if (pedal.pot_2.has_changed()) {
  }

}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__slicer_1aea4aac4005bfc584929e4db2df9c9556) | Audio routing node: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_1`](#classfx__slicer_1ae4c1b8d328e228319cd19bff6332930c) | Audio routing node: audio output for slicer channel 0
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_2`](#classfx__slicer_1aa8520e74bfd31d81ac4cdbcd916160c9) | Audio routing node: audio output for slicer channel 1
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_3`](#classfx__slicer_1a83ee17093e2ddeb58dd4dbf7ec669f9d) | Audio routing node: audio output for slicer channel 2
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_4`](#classfx__slicer_1ab1370ec62022c6e3c51a5aef4dfe50a1) | Audio routing node: audio output for slicer channel 3
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_5`](#classfx__slicer_1a655bf347bcdf202b866aa3e0f68e9fb6) | Audio routing node: audio output for slicer channel 4
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_6`](#classfx__slicer_1a39a01c6579266750f91aeac02f8f7acc) | Audio routing node: audio output for slicer channel 5
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_7`](#classfx__slicer_1a45c086598cfae96f1b205e0cde1cb68f) | Audio routing node: audio output for slicer channel 6
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_8`](#classfx__slicer_1a25eb7888a44e6766c518b916bc30f8a8) | Audio routing node: audio output for slicer channel 7
`public `[`fx_control_node`](#classfx__control__node)` * `[`period`](#classfx__slicer_1ac2267c3fca1786200fac8e1327cd13a7) | Control routing node: period in in milliseconds
`public inline  `[`fx_slicer`](#classfx__slicer_1aa58475e7abee046901e228b6d6befdfe)`(float period_ms,int32_t channels)` | Basic constructor/initializer for the slicer.
`public inline void `[`enable`](#classfx__slicer_1a0005ae49c5345637e329d5bdb9b59994)`()` | Enable the slicer (it is enabled by default)
`public inline void `[`bypass`](#classfx__slicer_1a4c84f21952fb3830fb1b9e9cff115c6b)`()` | Bypass the slicer (will just pass clean audio through)
`public inline void `[`set_period_ms`](#classfx__slicer_1a67e16609c920a9ab8ca5cc08e5776d21)`(float period)` | Upates the period in milliseconds for the slicer.
`public inline void `[`print_params`](#classfx__slicer_1ab7bcfb6dbe69577d7a060ba2cfdf83a7)`(void)` | Print the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__slicer_1aea4aac4005bfc584929e4db2df9c9556) {#classfx__slicer_1aea4aac4005bfc584929e4db2df9c9556}

Audio routing node: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_1`](#classfx__slicer_1ae4c1b8d328e228319cd19bff6332930c) {#classfx__slicer_1ae4c1b8d328e228319cd19bff6332930c}

Audio routing node: audio output for slicer channel 0

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_2`](#classfx__slicer_1aa8520e74bfd31d81ac4cdbcd916160c9) {#classfx__slicer_1aa8520e74bfd31d81ac4cdbcd916160c9}

Audio routing node: audio output for slicer channel 1

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_3`](#classfx__slicer_1a83ee17093e2ddeb58dd4dbf7ec669f9d) {#classfx__slicer_1a83ee17093e2ddeb58dd4dbf7ec669f9d}

Audio routing node: audio output for slicer channel 2

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_4`](#classfx__slicer_1ab1370ec62022c6e3c51a5aef4dfe50a1) {#classfx__slicer_1ab1370ec62022c6e3c51a5aef4dfe50a1}

Audio routing node: audio output for slicer channel 3

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_5`](#classfx__slicer_1a655bf347bcdf202b866aa3e0f68e9fb6) {#classfx__slicer_1a655bf347bcdf202b866aa3e0f68e9fb6}

Audio routing node: audio output for slicer channel 4

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_6`](#classfx__slicer_1a39a01c6579266750f91aeac02f8f7acc) {#classfx__slicer_1a39a01c6579266750f91aeac02f8f7acc}

Audio routing node: audio output for slicer channel 5

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_7`](#classfx__slicer_1a45c086598cfae96f1b205e0cde1cb68f) {#classfx__slicer_1a45c086598cfae96f1b205e0cde1cb68f}

Audio routing node: audio output for slicer channel 6

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output_8`](#classfx__slicer_1a25eb7888a44e6766c518b916bc30f8a8) {#classfx__slicer_1a25eb7888a44e6766c518b916bc30f8a8}

Audio routing node: audio output for slicer channel 7

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`period`](#classfx__slicer_1ac2267c3fca1786200fac8e1327cd13a7) {#classfx__slicer_1ac2267c3fca1786200fac8e1327cd13a7}

Control routing node: period in in milliseconds

#### `public inline  `[`fx_slicer`](#classfx__slicer_1aa58475e7abee046901e228b6d6befdfe)`(float period_ms,int32_t channels)` {#classfx__slicer_1aa58475e7abee046901e228b6d6befdfe}

Basic constructor/initializer for the slicer.

#### Parameters
* `period_ms` The period in milliseconds 

* `channels` The number of channels to slice between during the period

#### `public inline void `[`enable`](#classfx__slicer_1a0005ae49c5345637e329d5bdb9b59994)`()` {#classfx__slicer_1a0005ae49c5345637e329d5bdb9b59994}

Enable the slicer (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__slicer_1a4c84f21952fb3830fb1b9e9cff115c6b)`()` {#classfx__slicer_1a4c84f21952fb3830fb1b9e9cff115c6b}

Bypass the slicer (will just pass clean audio through)

#### `public inline void `[`set_period_ms`](#classfx__slicer_1a67e16609c920a9ab8ca5cc08e5776d21)`(float period)` {#classfx__slicer_1a67e16609c920a9ab8ca5cc08e5776d21}

Upates the period in milliseconds for the slicer.

#### Parameters
* `period` The period in milliseconds (thousands of a second)

#### `public inline void `[`print_params`](#classfx__slicer_1ab7bcfb6dbe69577d7a060ba2cfdf83a7)`(void)` {#classfx__slicer_1ab7bcfb6dbe69577d7a060ba2cfdf83a7}

Print the parameters for this effect.

# class `fx_variable_delay` {#classfx__variable__delay}

```
class fx_variable_delay
  : public fx_effect
```  

Effect: Variable delay - foundational block of flangers and choruses.

The variable delay effect is the basis for a number of time-varying delay effects like chorus, flanger, phaser, vibrato, Leslie simulator, etc.

Here's a nice tutorial on how variable delays work in these various building blocks: [https://www.dsprelated.com/freebooks/pasp/Time_Varying_Delay_Effects.html](https://www.dsprelated.com/freebooks/pasp/Time_Varying_Delay_Effects.html)

Example: 
```
/**
 * This is an implementation of a typical flanger pedal.   
 * 
 * Left pot: depth - the depth of the flanger effect
 * Center pot: delay time - modulation rate
 * Right pot: feedback - the feedback has a big impact on the sound.  Full counter-clockwise is -1.0
 *                       center is 0.0, and full clock-wise is 1.0.
 * 
 * Left footswitch: bypass - turns on and off the effect
 * Right footswitch: tap - tap it a few times at a set interval to update the flanger modulation rate
 * 
 * This effect uses a tiny amount of the available processing power and memory.
 * It's provided as an example of how to use the various features of the fx_variable_delay block
 * 
 */
#include <dreammakerfx.h>

fx_variable_delay flangey(1.0,            // Initial oscillator rate of 1Hz (1 cycle / second)
                          0.5,            // Initial depth of 0.5
                          0.4,            // Initial feedback of 0.4
                          OSC_TRIANGLE);  // Use a triangle oscillator

void setup() {
  
  // Initialize the pedal!
  pedal.init();

  // Route audio from instrument -> my_variable_delay -> amp
  pedal.route_audio(pedal.instr_in, flangey.input);
  pedal.route_audio(flangey.output, pedal.amp_out);  

  // left footswitch is bypass
  pedal.add_bypass_button(FOOTSWITCH_LEFT);

  // Right foot switch is tap loop length
  pedal.add_tap_interval_button(FOOTSWITCH_RIGHT, true);

  // Run this effect
  pedal.run();

}


void loop() {

  // If new tempo has been tapped in, use that to control flange rate
  if (pedal.new_tap_interval()) { 
    flangey.set_rate_hz(pedal.get_tap_freq_hz());
  } 

  // Left pot controls depth of the effect
  if (pedal.pot_left.has_changed()) { 
    flangey.set_depth(pedal.pot_left.val);     
  } 

  // Center pot controls rate
  if (pedal.pot_center.has_changed()) { 
    float rate_hz = pedal.pot_center.val* 6.0;
    pedal.set_tap_blink_rate_hz(rate_hz);
    flangey.set_rate_hz(rate_hz);     
  } 

  // Right pot controls the feedback (-1.0 to 1.0)
  if (pedal.pot_right.has_changed()) {
   flangey.set_feedback(1.0 - pedal.pot_right.val*2.0);
  }

   // Run pedal service to take care of stuff
  pedal.service();  
}

```


## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__variable__delay_1adfe9817234303c0a7a3447391e882af6) | Audio routing node [input]: primary audio input
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__variable__delay_1a34e31eab5e3d155aafa553a5fa66c369) | Audio routing node [output]: primary audio output
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`ext_mod_in`](#classfx__variable__delay_1aeb3230729a9af6c6112e90350fe869e6) | Audio routine node [input]: use another signal as the modulator source such as an [fx_oscillator](#classfx__oscillator). The oscillator can be run though the clipper for example to create new types of waveforms.
`public `[`fx_audio_node`](#classfx__audio__node)` * `[`modulated_out`](#classfx__variable__delay_1ad4379f17a31b9b270b3a1c8f3beb3d81) | Audio routing node [output]: just the pitch modulated signal without mixing in the original signal
`public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__variable__delay_1a6d200c4f53d486513be7c18fc7d948d6) | Control routing node [input]: modulation depth
`public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__variable__delay_1a4b8417112ba1196b03f0d29b8998ce9f) | Control routing node [input]: modulation rate in Hz
`public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__variable__delay_1a8d402d84f9415c711d72d72c4a92c77b) | Control routing node [input]: feedback
`public `[`fx_control_node`](#classfx__control__node)` * `[`mix_clean`](#classfx__variable__delay_1a096fd463ac9e92608bcdc825efcfabe9) | Control routing node [input]: clean signal mix
`public `[`fx_control_node`](#classfx__control__node)` * `[`mix_delayed`](#classfx__variable__delay_1a04c53cceef811141829a7c3a4ceeb780) | Control routing node [input]: delayed signal mix
`public inline  `[`fx_variable_delay`](#classfx__variable__delay_1a217641554df3b9eec906c3ee1d0e4f78)`(float rate_hz,float depth,float feedback,OSC_TYPES mod_type)` | Basic constructor/initializer for variable delay.
`public inline  `[`fx_variable_delay`](#classfx__variable__delay_1abcd127b2061165c91cebb9b15ce302ad)`(float rate_hz,float depth,float feedback,float buf_size_ms,float mix_clean,float mix_delayed,OSC_TYPES mod_type,bool ext_mod)` | Basic constructor/initializer for variable delay.
`public inline  `[`fx_variable_delay`](#classfx__variable__delay_1a9477d5ff572a08f4e8cfe6be7208c97a)`(float rate_hz,float depth,float feedback,float buf_size_ms,float mix_clean,float mix_delayed,OSC_TYPES mod_type,bool ext_mod,float initial_phase)` | Basic constructor/initializer for variable delay.
`public inline void `[`enable`](#classfx__variable__delay_1ad40a88ff09f879bcb21a6ee55d8771e8)`()` | Enable the **this_effect** (it is enabled by default)
`public inline void `[`bypass`](#classfx__variable__delay_1a2b5aa0e4bdba02a38397a8d58fe9882a)`()` | Bypass the **this_effect** (will just pass clean audio through)
`public inline void `[`set_depth`](#classfx__variable__delay_1a3ac8a8f3aae24224158d17e8d8582815)`(float depth)` | Updates the depth of the variable delay.
`public inline void `[`set_rate_hz`](#classfx__variable__delay_1a92efbe931e213229ee52c76ad9ff806b)`(float rate_hz)` | Updates the rate (Hz) of the variable delay.
`public inline void `[`set_feedback`](#classfx__variable__delay_1ad3b9ef61ed0db2e93bd15c01d6f98536)`(float feedback)` | Updates the feedback parameter of the variable delay.
`public inline void `[`set_mix_clean`](#classfx__variable__delay_1afa615e6ee413dd5c4066e798f55df959)`(float mix_clean)` | Updates the clean mix of the variable delay.
`public inline void `[`set_mix_delayed`](#classfx__variable__delay_1ae1faf9d93f2469fa201a2216ad773dfa)`(float mix_delayed)` | Updates the delayed signal mix of the variable delay.
`public inline void `[`set_lfo_type`](#classfx__variable__delay_1ad33df6056fe62e2403c86ae4b5c84757)`(OSC_TYPES new_type)` | Sets the the type of oscillator used as the LFO.
`public inline void `[`print_params`](#classfx__variable__delay_1a69e0bdf848f4f2ab1de57a7f23fb5088)`(void)` | Prints the parameters for this effect.

## Members

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`input`](#classfx__variable__delay_1adfe9817234303c0a7a3447391e882af6) {#classfx__variable__delay_1adfe9817234303c0a7a3447391e882af6}

Audio routing node [input]: primary audio input

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`output`](#classfx__variable__delay_1a34e31eab5e3d155aafa553a5fa66c369) {#classfx__variable__delay_1a34e31eab5e3d155aafa553a5fa66c369}

Audio routing node [output]: primary audio output

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`ext_mod_in`](#classfx__variable__delay_1aeb3230729a9af6c6112e90350fe869e6) {#classfx__variable__delay_1aeb3230729a9af6c6112e90350fe869e6}

Audio routine node [input]: use another signal as the modulator source such as an [fx_oscillator](#classfx__oscillator). The oscillator can be run though the clipper for example to create new types of waveforms.

#### `public `[`fx_audio_node`](#classfx__audio__node)` * `[`modulated_out`](#classfx__variable__delay_1ad4379f17a31b9b270b3a1c8f3beb3d81) {#classfx__variable__delay_1ad4379f17a31b9b270b3a1c8f3beb3d81}

Audio routing node [output]: just the pitch modulated signal without mixing in the original signal

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`depth`](#classfx__variable__delay_1a6d200c4f53d486513be7c18fc7d948d6) {#classfx__variable__delay_1a6d200c4f53d486513be7c18fc7d948d6}

Control routing node [input]: modulation depth

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`rate_hz`](#classfx__variable__delay_1a4b8417112ba1196b03f0d29b8998ce9f) {#classfx__variable__delay_1a4b8417112ba1196b03f0d29b8998ce9f}

Control routing node [input]: modulation rate in Hz

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`feedback`](#classfx__variable__delay_1a8d402d84f9415c711d72d72c4a92c77b) {#classfx__variable__delay_1a8d402d84f9415c711d72d72c4a92c77b}

Control routing node [input]: feedback

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`mix_clean`](#classfx__variable__delay_1a096fd463ac9e92608bcdc825efcfabe9) {#classfx__variable__delay_1a096fd463ac9e92608bcdc825efcfabe9}

Control routing node [input]: clean signal mix

#### `public `[`fx_control_node`](#classfx__control__node)` * `[`mix_delayed`](#classfx__variable__delay_1a04c53cceef811141829a7c3a4ceeb780) {#classfx__variable__delay_1a04c53cceef811141829a7c3a4ceeb780}

Control routing node [input]: delayed signal mix

#### `public inline  `[`fx_variable_delay`](#classfx__variable__delay_1a217641554df3b9eec906c3ee1d0e4f78)`(float rate_hz,float depth,float feedback,OSC_TYPES mod_type)` {#classfx__variable__delay_1a217641554df3b9eec906c3ee1d0e4f78}

Basic constructor/initializer for variable delay.

#### Parameters
* `rate_hz` The modulation rate in Hz 

* `depth` The modulation depth (0.0 -> 1.0) 

* `feedback` The feedback from output to input (-1.0 -> 1.0) 

* `mod_type` The shape of the waveform used to modulate (e.g. OSC_SINE, OSC_TRI, etc.)

#### `public inline  `[`fx_variable_delay`](#classfx__variable__delay_1abcd127b2061165c91cebb9b15ce302ad)`(float rate_hz,float depth,float feedback,float buf_size_ms,float mix_clean,float mix_delayed,OSC_TYPES mod_type,bool ext_mod)` {#classfx__variable__delay_1abcd127b2061165c91cebb9b15ce302ad}

Basic constructor/initializer for variable delay.

#### Parameters
* `rate_hz` The modulation rate in Hz 

* `depth` The modulation depth (0.0 -> 1.0) 

* `feedback` The feedback from output to input (-1.0 ->1.0) 

* `buf_size_ms` The size of the audio in milliseconds (start wtih a value around 30) 

* `mix_clean` The clean mix. If this is set to 0.0, then you'll just get the pitch changing aspect of the wave that can used for tape delay simulators, etc. 

* `mix_delayed` The delayed signal mix. 

* `mod_type` The shape of the waveform used to modulate (e.g. OSC_SINE, OSC_TRI, etc.) 

* `ext_mod` whether to use an external modulation source (set to true or false)

#### `public inline  `[`fx_variable_delay`](#classfx__variable__delay_1a9477d5ff572a08f4e8cfe6be7208c97a)`(float rate_hz,float depth,float feedback,float buf_size_ms,float mix_clean,float mix_delayed,OSC_TYPES mod_type,bool ext_mod,float initial_phase)` {#classfx__variable__delay_1a9477d5ff572a08f4e8cfe6be7208c97a}

Basic constructor/initializer for variable delay.

#### Parameters
* `rate_hz` The modulation rate in Hz 

* `depth` The modulation depth (0.0 -> 1.0) 

* `feedback` The feedback from output to input (-1.0 ->1.0) 

* `buf_size_ms` The size of the audio in milliseconds (start wtih a value around 30) 

* `mix_clean` The clean mix. If this is set to 0.0, then you'll just get the pitch changing aspect of the wave that can used for tape delay simulators, etc. 

* `mix_delayed` The delayed signal mix. 

* `mod_type` The shape of the waveform used to modulate (e.g. OSC_SINE, OSC_TRI, etc.) 

* `ext_mod` whether to use an external modulation source (set to true or false) 

* `initial_phase` Initial phase in degrees

#### `public inline void `[`enable`](#classfx__variable__delay_1ad40a88ff09f879bcb21a6ee55d8771e8)`()` {#classfx__variable__delay_1ad40a88ff09f879bcb21a6ee55d8771e8}

Enable the **this_effect** (it is enabled by default)

#### `public inline void `[`bypass`](#classfx__variable__delay_1a2b5aa0e4bdba02a38397a8d58fe9882a)`()` {#classfx__variable__delay_1a2b5aa0e4bdba02a38397a8d58fe9882a}

Bypass the **this_effect** (will just pass clean audio through)

#### `public inline void `[`set_depth`](#classfx__variable__delay_1a3ac8a8f3aae24224158d17e8d8582815)`(float depth)` {#classfx__variable__delay_1a3ac8a8f3aae24224158d17e8d8582815}

Updates the depth of the variable delay.

#### Parameters
* `depth` The new depth value

#### `public inline void `[`set_rate_hz`](#classfx__variable__delay_1a92efbe931e213229ee52c76ad9ff806b)`(float rate_hz)` {#classfx__variable__delay_1a92efbe931e213229ee52c76ad9ff806b}

Updates the rate (Hz) of the variable delay.

#### Parameters
* `rate_hz` The new rate hz

#### `public inline void `[`set_feedback`](#classfx__variable__delay_1ad3b9ef61ed0db2e93bd15c01d6f98536)`(float feedback)` {#classfx__variable__delay_1ad3b9ef61ed0db2e93bd15c01d6f98536}

Updates the feedback parameter of the variable delay.

#### Parameters
* `feedback` The new feedback value (-1.0->1.0)

#### `public inline void `[`set_mix_clean`](#classfx__variable__delay_1afa615e6ee413dd5c4066e798f55df959)`(float mix_clean)` {#classfx__variable__delay_1afa615e6ee413dd5c4066e798f55df959}

Updates the clean mix of the variable delay.

#### Parameters
* `mix_clean` The new clean mix value

#### `public inline void `[`set_mix_delayed`](#classfx__variable__delay_1ae1faf9d93f2469fa201a2216ad773dfa)`(float mix_delayed)` {#classfx__variable__delay_1ae1faf9d93f2469fa201a2216ad773dfa}

Updates the delayed signal mix of the variable delay.

#### Parameters
* `mix_delayed` The new delayed mix value

#### `public inline void `[`set_lfo_type`](#classfx__variable__delay_1ad33df6056fe62e2403c86ae4b5c84757)`(OSC_TYPES new_type)` {#classfx__variable__delay_1ad33df6056fe62e2403c86ae4b5c84757}

Sets the the type of oscillator used as the LFO.

#### Parameters
* `new_type` The new type of LFO (OSC_TYPES)

#### `public inline void `[`print_params`](#classfx__variable__delay_1a69e0bdf848f4f2ab1de57a7f23fb5088)`(void)` {#classfx__variable__delay_1a69e0bdf848f4f2ab1de57a7f23fb5088}

Prints the parameters for this effect.

Generated by [Moxygen](https://sourcey.com/moxygen)