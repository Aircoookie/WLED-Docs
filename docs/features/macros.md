---
title: Macros
hide:
  # - navigation
  # - toc
---
!!! info
    See [Presets](/features/presets) for 0.11.0+.

You are able to set custom actions ("Macros") in Time & Macro settings for the following events:

- Specific time of day
- Button short/long/double press
- HTTP API call executing a macro with "&M="
- Alexa On/Off
- Countdown over
- Timed light duration over
- Device (re)boot (up to 0.10.2, use LED settings `Boot preset` in 0.11)

Each macro has the format of a standard [HTTP API call](/interfaces/http-api) without the IP. Optionally, the "win&" may be omitted.
For example, the macro "A=255" sets the brightness to maximum. "R=255&G=160&B=0" sets the color to orange.
You can specify up to 16 macros. (up to 250 in WLED 0.11 since the Macro functionality has been merged into the Presets feature)

Examples of how to use API-calls and define macros can be found in [this issue](https://github.com/Aircoookie/WLED/issues/801#issuecomment-635600255) and [in this one](https://github.com/Aircoookie/WLED/issues/199#issuecomment-520143239).

The simplest macro example is getting a button to do your bidding.  The default pin to which a button can be connected is GPIO 0 (D3 on NodeMCU, D1 Mini and others).  This pin is ideally pulled high to 3.3V with a 10k resistor and the configured macro executes when the pin is pulled low (grounded). The desired macro is entered on the Time/Macros configuration page and then assigned to a short, long or double press. Like this:
![how to wire a button to D3 and set up a macro](https://user-images.githubusercontent.com/40203361/64235553-e3c41300-cef8-11e9-833f-c5062aaba124.jpg)
The "T=2" macro toggles power to the LEDs (in this case long press).
The "FX=~" macro steps through the effects (in this case short press).

The default (built-in) actions are short-press: toggle on/off and long-press: select random color.