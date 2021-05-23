---
title: Infrared
hide:
  # - navigation
  # - toc
---


!!! info "Version Info"
    Since v0.8.2, infrared control from various IT remotes is supported for ESP8266 and since v0.9.0 for ESP32, too.

A dedicated infrared receiver module is required.
(KY-022 or TSOP38238 are confirmed to work and inexpensive)

The default sensor pin is GPIO4. It can be changed in the Wled settings.

### Supported IR remotes
To use IR remote go to `Settings`, `Sync Interfaces` and change the value for `Infrared receiver type` according to the IR remote type of the following list:
1. white 24-key IR remote with R,G,B + 12 color-tones
2. white 24-key IR remote with CT+ / CT- buttons
3. blue 40-key IR remote with keys for 25%, 50%, 75% and 100%
4. white 44-key IR remote with up/down arrows for the colors R,G and B
5. white 21-key IR remote with R,G,B + 9 color-tones
6. black 6-key IR remote with CH up/down + Vol up/down

### How to add custom codes

Have a random remote laying around? Or a button on your TV remote that does nothing?
You can make these compatible with WLED if they use a 38kHz carrier frequency like most IR remotes do.

Firstly, connect your ESP8266 to a PC and open the Arduino IDE serial monitor.
Try pressing the button(s) you'd like to program. If your receiver is connected correctly, you should see something like this printed to the serial monitor:
```
IR recv
0xFFDE10
```
In this example, `0xFFDE10` is the infrared code in HEX. If you get `0xFFFFFFFF`, the same code was received multiple times - try only tapping the remote button for a very brief time.

Now, open the file `ir_codes.h` and add your IR code by adding (for example) `#define IRCUSTOM_MACRO1 0xFFDE10`.

Almost done! Open `ir.cpp` and add your IR code into the `switch` structure in the `decodeIRCustom()` method. You should be able to follow the existing code to program your desired action. For example, you could do `case IRCUSTOM_MACRO1: bri = 255; break;` to set maximum brightness. 