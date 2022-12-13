## Introduction
The sound reactive version of WLED provides all of the functionality of WLED with a few caveats:

* #### Some of the default services supported by WLED such as IR, Alexa and Blynk are disabled by default. To enable them, update the definitions in wled.h and re-compile.
* Spurious noise and spikes have been problematic during the development of SR WLED. See 'Noise and Spikes' below for further discussion on this topic.
* We recommend using SR WLED in STA mode, instead of the standalone AP mode (aka WLED-AP). It generates more noise.
* If you have problems with the LED's, make sure you can successfully run the latest version of standard WLED.
* Start out with a small strip of ~30 LED's before setting up a large installation.


* Grounding may also be a problem. For example, my line-in setup picked up a lot of noise when my ESP32 board was connected to the USB port on my PC, but NO noise when powered by a USB power bank.
* Connectors!! Dupont connectors are notoriously flaky. I use JST-SM connectors for the LED's and (so far) just soldered the microphones.


## First Steps
#### First Contact (after uploading)
After uploading WLED to the ESP, use your phone and connect to the WLED-AP using the password 'wled1234'.
Click 'Login to network' when the notification about this shows up. You are then transfered to the WLED's start page, and here we should click "WIFI SETTINGS" to connect to the local network. Fill in the settings for your local Wifi network, and then click 'Save & Connect'. The device will reboot and if everything worked it will now be connected to the local network. Finding it's IP-address can be done via the network routers administration page, or via an mobile app like Fing were you can find a new device called "wled-WLED". Open this IP in a webbrowser to access WLED's control page.

#### Wifi and LEDs
1. On the WiFi Setup page, it is highly recommended that you connect your SR WLED strip to an existing network.
2. At the bottom of the WiFi Setup page, check on 'Disable WiFi sleep'. This may not be necessary if you're not experiencing noise or UDP Sync lag issues.
3. On the LED Preferences page, configure the length of your led strip.
3. On the LED Preference page, configure the 2D matrix size, i.e. 1x30 or 16x16, etc. If you have not configured this, 2D routines may not work.

#### Sound
4. On the Sound Setting page, set the Squelch setting to '1', the Gain > 200, and AGC = Off.
5. On the Effects page, set the animation to '*Gravcenter' or '*Gravimeter'.
6. Back on the Sound Settings page, increase/save Squelch setting until strip no longer reacts to the ambient noise.
7. On the Sound Settings page, set the Gain to 40. Then reduce/adjust the Gain setting until the leds react reasonably with your voice.
8. You might also want to run a [Pink Noise](https://www.youtube.com/watch?v=ZXtimhT-ff4) video and fine tune the values from there.
<br/>

## Sound Settings: getting started with common microphones

_Disclaimer: The information below is for the [latest release version of SR WLED](https://github.com/atuline/WLED/releases)._ 
_If you use an older release, please divide _Gain_ values by 4._

Here's a starting point table of Squelch and Gain settings for different input types:

| Input (I2S digital) | _Squelch_ | _Gain_ | _Type_ | _comments_
| ------------------- | --------- | ------ | -------| ------
| INMP441 | 6 | 60 | Generic I2S | 
| ICS-43434 | 16 | 30  | Generic I2S | 
| SPM1423 | _tbd_ | _tbd_  | Generic I2S PDM | M5StickC, M5AtomU
| SPH0654 | _tbd_ | _tbd_  | SPH0654 | 
| ES7243 | _tbd_ | _tbd_  | ES7243 | ESP32 Lyra-T Mini
| Line-In CS5343 | _tbd_ | _tbd_  | Generic I2S with Mclk | _MCLK_ to GPIO0


| Input (ADC analog)  | _Squelch_ | _Gain_ | _Type_ 
| ------------------- | --------- | ------ | ------- 
| MAX9814 @40dB | 10 | 80 | Generic Analog
| Line-In | 8 | 120 | Generic Analog
| INMP411 | 20 | 80  | Generic Analog
| MAX4466 | 16 | 120 | Generic Analog

### Analog or I2S Digital?

We recommend using an [I2S digital microphone](https://github.com/atuline/WLED/wiki/Digital-Microphone-Hookup), like INMP441, ICS-43434, or PDM microphones.

Analog input ([Microphone or Line-in](https://github.com/atuline/WLED/wiki/Analog-Audio-Input-Options)) is also possible, however you might have power fluctuation (3.3V) and noise issues when using these. Analog devices are handled by the "ADC1" unit of your ESP32. Problems can be expected when connecting "analog buttons" (Potentiometer) to the same ADC1 unit. 

Finally Analog Microphones often work best when placed very close to the sound source, while digital ones like the INMP441 can easily pick up sound from several meters apart. With the analog MAX4466, we found that 30-50cm is an optimal distance. 

### AGC
Automatic gain control (AGC) is not enabled by default in SR WLED, because of so many different input types and ambient noise in different environments. We don't know what your 'quiet' is. In addition, the LED's should NOT be reacting when it IS quiet, so it's up to you to first make those adjustments. In addition, sensitivity can be further adjusted with either the Intensity or Speed slider in many of the animations.

While an improved autonomous gain control (iAGC) feature is available since [version 0.13.1](https://github.com/atuline/WLED/releases/tag/v0.13.1), it is still very important that you _first_ find a good _Squelch_ setting for your environment. Afterwards you can enable AGC and let the controller adjust input levels automatically. 

## Noise and Spikes
While providing a lot of functionality, the ESP8266 and the ESP32 boards (typical ones) we have been using, have experienced a lot of spurious noise on their ADC pins. This has also been discussed at length on various ESP related forums. Methods that may help remediate this include:

* Use an I2S microphone, such as the INMP441, SPH0645 or ICS-43434.
* Use a separate WiFi antenna.
* Don't use AP mode.
* Disable the WiFi sleep mode.

* Use shielded wiring for your analog sampling pin.
* Isolate the power between the LED strips and the controller.
* Don't power your LED stripe from the ESP32 3.3v or 5v pins.
* Don't use USB power from your PC.
* Some batches of analog microphones are just no good.
