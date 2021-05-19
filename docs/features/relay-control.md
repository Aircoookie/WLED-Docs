---
title: Control a Relay
hide:
  # - navigation
  # - toc
---

LED strips still use power when seemingly switched off. In case you want to prevent that, you have several ways of totally switching off power (including manually switching off the power), one of which is adding a relay to your circuit. GPIO12 (Pin D6 on many devices) is toggled by WLED when WLED is turned on/off (in the UI, or through other interfaces). This lets you control a relay through your WLED flashed controller.

When you decide you want WLED to control a relay, make sure you buy the right relay. Check what voltage you can supply from your controller (free 3V pin, 5V pin etc), and make sure the relay is suitable to be controlled by the voltage you can supply (3V, 5V or something else). Note, some relays come with a jumper that lets you configure whether the relay switches at high or low signal, giving you maximum flexibility.

[This page](https://www.geekering.com/?p=187) gives a clear description using a light bulb instead of a LED strip. And instead of the D1 mentioned in that story, with WLED, you use GPIO12.

The default WLED behavior is to turn GPIO12 on (high) when the LEDs are on and off (low) when the LEDs are off. It can be changed though with the RLYMDE define in NbpWrapper.h. Many relays are powered when the signal is LOW. See [this thread](https://github.com/Aircoookie/WLED/issues/631#issuecomment-605512524).

Sometimes people ask whether they can control more than one relay through WLED, including controlling this all via Alexa. Controlling an extra relay separately from the RGB lights is not something WLED is designed to do, however you can modify the code to add that functionality. For that, make sure you can compile WLED from source unmodified first. Then, change #define ESPALEXA_MAXDEVICES 1 in line 71 of the wled.h file to 2. After that, just follow the API documentation on https://github.com/Aircoookie/Espalexa to add a new EspalexaDevice to the alexa.cpp file