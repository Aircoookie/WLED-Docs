---
title: Control a Relay
hide:
  # - navigation
  # - toc
---

LED strips still use power when seemingly switched off. In case you want to prevent that, you have several ways of totally switching off power (including manually switching off the power), one of which is adding a relay to your circuit. GPIO12 (Pin D6 on many devices) is toggled by WLED when WLED is turned on/off (in the UI, or through other interfaces). This lets you control a relay through your WLED flashed controller.
GPIO12 can be easily changed to any other available GPIO pin in LED Preferences page.

When you decide that you want WLED to control a relay, make sure you buy a suitable relay. Check what voltage you can supply from your controller to relay (available 3.3V or 5V pin or different voltage from external power source), and make sure the relay can be controlled by voltage level your board is providing  (3.3V CMOS, 5V TTL). Note, some relays come with a jumper that lets you configure whether the relay switches at high or low level of signal, giving you maximum flexibility.

[This page](https://www.geekering.com/?p=187) gives a clear description using a light bulb instead of a LED strip. And instead of the D1 mentioned in that story, with WLED, you use GPIO12.

The default WLED behavior is to turn GPIO12 on (high) when the LEDs are on and off (low) when the LEDs are off. This behaviour can be changed in the LED Preferences page. Many relays are powered when the signal is LOW. See [this thread](https://github.com/Aircoookie/WLED/issues/631#issuecomment-605512524).

Sometimes people ask whether they can control more than one relay through WLED, including controlling this all via Alexa. Controlling an extra relay separately from the RGB lights is not something WLED is designed to do, however you can modify the code to add that functionality. For that, make sure you can compile WLED from source unmodified first. Then, change #define ESPALEXA_MAXDEVICES 1 in line 71 of the wled.h file to 2. After that, just follow the API documentation on https://github.com/Aircoookie/Espalexa to add a new EspalexaDevice to the alexa.cpp file

Second option for controlling multiple relays is using a Multi Relay usermod. As with Alexa you will need to compile WLED from source an include Multi Relay usermod either by including `-D USERMOD_MULTI_RELAY` in PlatformIO.ini or adding `#define USERMOD_MULTI_RELAY` in `wled.h` or `my_config.h`. You can also override default number of relays by defining `MULTI_RELAY_MAX_RELAYS`. Configuring usermod is done using Usermod settings page where you can define GPIO pins used, wether relay activates on HIGH or LOW logic, if the activation has any delay and if the relay can be controlled from the outside using MQTT message (external).
MQTT topic for controlling relays is `wled/[device]/relay/[relay_id]/command` and accepts `on`, `off` and `toggle` messages. When the relay changes state a message with `on` or `off` is sent with the topic `wled/[device]/relay/[relay_id]`.
