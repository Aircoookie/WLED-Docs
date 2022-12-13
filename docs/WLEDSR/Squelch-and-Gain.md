## Introduction

In order to accommodate a wide range of audio inputs, ambient environments and string lengths, we have added user configurable squelch (noise reduction/suppression) and gain controls on the LED settings page for the volume reactive animations.

## Squelch
Adjust this value on the LED Settings page so that the leds are only activated above a certain 'background noise' level.

## Gain
Line-in signals are typically much lower than that of some of the microphones. Rather than use an auto gain function, you can manually adjust the gain from 1 to 255, which translate up to almost 6.0 gain.

In addition, the 'Intensity' slider can sometimes adjust an animation to simulate increased gain.

## How To
Here's a method to setup squelch and gain for your SR WLED Device.

1. Start out with the routine '*Gravcenter' with default sliders in the middle.
2. Go to the sound settings configuration page.
3. Increase gain to a high value, let's say 234 (or higher) and set the squelch to '1' , AGC off, and save.
4. Depending on your input, you should now see the led's flashing.
5. In a quiet environment, increase and occasionally save the squelch incrementally until the led's are no longer flashing.
6. Once that's done, make noise appropriate to your 'noisy' environment and number of led's. Then adjust/save the gain so that the led's are responding appropriately.
7. Note that some of the animations allow further sensitivity adjustment with the 'Intensity' setting.
8. Check out the '[Sound Reactive Animations](https://moonmodules.github.io/WLED-Docs/WLEDSR/Reactive-Animations)' page to see what controls are available for each animation.


## Voltage Fluctuation
From faulty microphones to flaky wiring, to WiFi related issues, particularly in AP mode, getting reliable and spike free sound sampling with WLED and in particular analog sampling has been a challenge. Digital microphones such as the INMP441, the ICS-43434 provide the best results.
