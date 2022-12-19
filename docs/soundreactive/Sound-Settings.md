---
title: Work in Progress
hide:
  # - navigation
  # - toc
---

## Introduction

In order to accommodate a wide range of audio inputs, ambient environments and string lengths, we have added user configurable squelch (noise reduction/suppression) and gain controls on the sound settings page that apply to all sound reactive animations.

<img width="368" alt="image" src="https://user-images.githubusercontent.com/91013628/208448097-f0824866-1a9d-4907-8863-6293d2e7e2de.png">

<br/>

### Press reset key after changing sound source
After changing the sound source (either GPIO pins or Microphone type), it is important to press the "reset" (RST) button on your ESP32 - don't forget to "save" first. WLED cannot change the sound input configuration "on the fly", due to a known hardware problem of ESP32. See https://github.com/espressif/esp-idf/issues/7442 "only a hard CPU reset can disconnect the I2S signal from built-in ADC". 

<br/>

## Analog Input Pins

![WLEDSR-Sound-Setings-Analog](https://user-images.githubusercontent.com/91616163/177540059-0fde407b-6740-4ae3-8ae5-6b2cbc09d9ea.png)

We typically recommend using GPIO 36, aka VP or ADC1_CH0 for analog input, however the following pins should also work:

GPIO 32 => ADC1_CH4

GPIO 33 => ADC1_CH5

GPI&nbsp; 34 => ADC1_CH6

GPI&nbsp; 35 => ADC1_CH7

GPI&nbsp; 36 => ADC1_CH0, VP

GPI&nbsp; 37 => ADC1_CH1

GPI&nbsp; 38 => ADC1_CH2

GPI&nbsp; 39 => ADC1_CH3, VN

Do NOT use any of the pins from ADC2, as they will conflict with the WiFi and with I2S sampling.


Remember to [press Reset](https://moonmodules.github.io/WLED-Docs/WLEDSR/Sound-Settings#press-reset-key-after-changing-sound-source) after saving your new analog input configuration.

<br/>

We have observed problems when using "analog buttons" (potentiometer) together with ADC analog sound input. It seems that different drivers (I2S-ADC for sound, analogRead() for potentiometer) are getting into conflict - more details in the related [bug report for espressif software](https://github.com/espressif/arduino-esp32/issues/4782). If you plan to attach a potentiometer to your WLED device, we recommend to use an [I2S digital microphone](https://moonmodules.github.io/WLED-Docs/WLEDSR/Digital-Microphone-Hookup) to avoid these problems.



More information about analog inputs on our [analog microphones](https://moonmodules.github.io/WLED-Docs/WLEDSR/Analog-Audio-Input-Options) page.

<br/>

## Squelch
Adjust this value on the Sound Settings page so that the leds are only activated above a certain 'background noise' level.

In order to accommodate a wide range of audio inputs, ambient environments and string lengths, we have added user configurable squelch (noise reduction/suppression) and gain controls on the LED settings page for the volume reactive animations.

See also 

&rArr; [Squelch and Gain](https://moonmodules.github.io/WLED-Docs/WLEDSR/Squelch-and-Gain)

&rArr; [Sound setting examples for common microphones](https://moonmodules.github.io/WLED-Docs/WLEDSR/First-Time-Setup#sound-settings-getting-started-with-common-microphones)

## Gain
Line-in signals are typically much lower than that of some of the microphones. Rather than use an auto gain function, you can manually adjust the gain from 1 to 255, which translates to 0.1 up to almost 6.5 gain. That's equivalent to a range of _-20dB_ up to _+16dB_.

In addition, the 'Intensity' and "input level" sliders can sometimes adjust an animation to simulate increased gain.

## How To
Here's a method to setup squelch and gain for your SR WLED Device.

1. Start out with the routine '*Gravimeter' with default sliders in the middle.
2. Go to the sound settings configuration page.
3. Increase gain to a high value, let's say 234 (or higher) and set the squelch to '1', AGC off, then save.
4. Depending on your input, you should now see the led's flashing, even when the wind blows.
5. In a quiet environment, increase and occasionally save the "squelch" incrementally until the led's are no longer flashing.
6. Once that's done, set "gain" to 40. Make noise appropriate to your 'noisy' environment and number of led's. Then adjust/save the gain so that the led's are responding appropriately.
7. Note that some of the animations allow further sensitivity adjustment with the 'Intensity' setting.
8. Check out the '[Sound Reactive Animations](https://moonmodules.github.io/WLED-Docs/WLEDSR/Reactive-Animations)' page to see what controls are available for each animation.


## Voltage Fluctuation
From faulty microphones to flaky wiring, to WiFi related issues, particularly in AP mode, getting reliable and spike free sound sampling with WLED and in particular analog sampling has been a challenge. Digital microphones such as the INMP441, the ICS-43434 provide the best results.


## I2S Digital Input

![WLEDSR-Sound-Setings-Part2](https://user-images.githubusercontent.com/91616163/177542281-1a2ab7b7-48db-4e5e-8658-cd68fd8ead38.png)

Currently the following I2S options are available:

![WLEDSR-Sound-Setings-Digital_Part2](https://user-images.githubusercontent.com/91616163/177543015-2e862675-274d-45fa-822e-bea763ad9432.png)

Some more information can be found on our [I2S digital microphones](https://moonmodules.github.io/WLED-Docs/WLEDSR/Digital-Microphone-Hookup) page.

_to be extended soon_

### I2S Line-in
There are solutions available for line-in via I2S. For example, boards/shields with "es7243" chip should work already (we have a special driver for these), and we're investigating "es8388". Please check our [I2S digital microphone hookup - I2S audio boards/modules](https://moonmodules.github.io/WLED-Docs/WLEDSR/Digital-Microphone-Hookup#some-i2s-audio-boards) page for more information.
<br/>

## AGC - improved Autonomous Gain Control
We have recently improved the AGC (automatic gain control) algorithm in WLED-SR. It's not enabled by default, however we encourage you to give it a try - all sound reactive effects now support AGC, including 2D and frequency-reactive effects. The only prerequisite for using AGC is that you first adjust "Squelch" to define 'silence' (ambient noise level) in your environment - [see previous section](https://moonmodules.github.io/WLED-Docs/WLEDSR/Sound-Settings/_edit#how-to).

![WLEDSR-Sound-Setings-AGC_only](https://user-images.githubusercontent.com/91616163/177599946-055ee5f1-34b9-4a23-a408-4d21500c31e7.png)

AGC will automatically perform sound input amplification, based on current sound loudness. 
For example, if you play music and then increase the speaker volume, WLED-SR will adjust internal gain factors to follow your music. Forget about manually changing "gain" settings. Just relax and let WLED-SR do it autonomously.

Currently WLED-SR offers four different AGC presets that can be selected in sound settings:
* **Off**    - AGC off. WLED will strictly use the _Gain_ value from sound input settings, without any adjustments.
* **Normal** - AGC tries to smoothly follow changes in sound input volume. Recommended as a balanced option for general use.
* **Vivid**  - AGC will quickly adjust to changes in sound input volume. Recommended in case you want "more blinken from your LEDs".
* **Lazy**   - AGC will take some more time before internal gain is adjusted. Recommended for GEQ effects, or when listening to music that features strong "dynamics".


_to be extended soon_
