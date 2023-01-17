The WLEDSR help you can find here have been copied from <https://github.com/atuline/WLED/wiki>.
These pages are here temporarily. Aim is to migrate them step by step to 0.14 general and MM specific pages.

# WLED Sound Reactive Introduction
This is a FORK of the original WLED code as found at [wled.me](http://wled.me). It provides basic sound reactivity for both the [ESP8266](https://github.com/atuline/WLED/tree/ESP8266) and [ESP32](https://github.com/atuline/WLED) platforms as well as FFT sound reactivity for the ESP32.

Due to the performance limitations of the ESP8266, we decided to separate the ESP8266 and ESP32 code in order to provide a more stable build for the ESP8266. Beginning with version 0.10.2 and moving forward, ESP8266 support has been removed from the master branch. It receives very limited support and updates and is located at [ESP8266 Branch](https://github.com/atuline/WLED/tree/ESP8266).

We have also disabled functionality for other interfaces, such as Alexa, Blynk, Cronixie, Huesync, Infrared. If you would like to enable them, you will need to modify wled.h, compile and upload to your device. If you have any issues, please engage the Discord community, as we only support functionality for the web interface.

### Features

We do our best to perform upstream merges with the original WLED. Our fork includes:

* Several volume reactive effects.
* Several FFT (frequency) reactive effects.
* Some new non-reactive 1D effects.
* Many 2D effects, including a highly configurable "graphical equalizer" effect.
* UDP sync for volume and FFT reactive effects.
* Additional sliders for controlling effects.
* Multiple panels of 2D led's.
* 2D segments.
* Dynamic naming and visibility of sliders.
* An interpreter - for creating your own custom effects.
* Configuration setting for 2D, panels, noise squelch, gain, and UDP sound synchronization.


### Sound Reactive WLED Fork Team:

* **A bit of everything (mainly FastLED animations):** Andrew Tuline (aka johnny5canuck)
* **Sound reactive ESP32 FFT, 2D:** Andreas Pleschutznig (aka apleschu)
* **General contributor, documentation, versioning, keep us up to date:** Chris Reese (aka THATDONFC)
* **General contributor, UDP Sound Sync, INMP441 I2S:** Chris Hultin (aka spedione)
* **Panels, 2D, segments, animations, custom effects (interpreter) and code cleanup:** Ewoud Wijma (aka ewowi)
* **Sound processing, FFT, and code cleanup:** Frank Möhle (aka softhack007)
* **I2S Sound input and processing:** Florian Heilmann (aka Haribo / FHeilmann)

Other members of the WLED Discord group have provided code and testing support as well. Thanks all!

### Knowledge and Pre-Requisites

Before attempting to compile this fork of WLED with Platform IO (the Arduino IDE is no longer viable for this project), make sure you CAN compile the one from [wled.me](http://wled.me).

If you are unable to compile WLED, please consider flashing your device with binaries instead.


## Hardware used 

Using the WLED 0.10 codebase, our code has been tested with:

* [INMP441](https://www.aliexpress.com/i/32962426410.html) I2S digital microphone
* [MAX9814](https://www.digikey.com/products/en?mpart=1713&v=1528) electret microphone
* [INMP401](https://www.sparkfun.com/products/9868) MEMS microphone
* [MAX4466](https://www.adafruit.com/product/1063) Electret microphone
* 3.5mm Line In
* [LOLIN D32](https://docs.wemos.cc/en/latest/d32/d32.html) and [Lolin D32 lite](https://www.az-delivery.de/en/products/esp32-lolin-lolin32)
* [Espressif ESP32 DevKitC V4](https://www.digikey.com/product-detail/en/espressif-systems/ESP32-DEVKITC-32D/1965-1000-ND/9356990)
* [WeMOS D1 Mini (ESP8266)](https://docs.wemos.cc/en/latest/d1/d1_mini.html)



For more information, see our **[Analog Audio Input Options](https://mm.kno.wled.ge/WLEDSR/Analog-Audio-Input-Options)** or **[Digital Audio Input Options](https://mm.kno.wled.ge/WLEDSR/Digital-Microphone-Hookup)** page.


## Default pins used

* GPIO2 (D4 on WEMOS) for both ESP8266 and ESP32 for WS2812's
* A0 for ESP8266 (audio-in pin)
* GPIO36 (or VP) for the ESP32 (audio-in pin)
* See [[Digital Microphone Hookup]] for pins used
* In SR-WLED 0.12.0 or newer, you can use the web UI to change pins. In older versions, you can change the pins used by adding definitions in your PlatformIO config or editing audio_reactive.h.

## Discussion and Support
Please consider joining the WLED Discord groups where we have dedicated channels to discuss this project, your projects, 
and answer any questions you may have.

<a href="https://discord.gg/4CQRmfR"><img src="https://discordapp.com/api/guilds/700041398778331156/widget.png?style=banner2" width="50%"  align="middle"></a>
Join Discord to discuss beta testing of our [sound reactive fork](https://discord.gg/4CQRmfR) of WLED. 

<a href="https://discord.gg/KuqP7NE"><img src="https://discordapp.com/api/guilds/473448917040758787/widget.png?style=banner2" width="50%" align="middle"></a>
Join Discord to discuss [AirCookie's WLED](https://discord.gg/KuqP7NE).

We can also be found on reddit at [r/soundreactive](https://www.reddit.com/r/soundreactive).


### Support Forums

* [WLED on Reddit](https://reddit.com/r/WLED/)
* [r/soundreactive on Reddit](https://www.reddit.com/r/soundreactive)
* [WLED Discord](https://discordapp.com/channels/473448917040758787/473448917543944193)
* [WLED Discord](https://discordapp.com/channels/473448917040758787/473448917543944193)
* [WLED Soundreactive Discord](https://discord.gg/4CQRmfR)
* [WLED on Discourse](https://wled.discourse.group/)
* [FastLED on Reddit](https://reddit.com/r/FastLED)