---
title: Compatible LED strips
hide:
  # - navigation
  # - toc
---

WLED supports two types of LED strips: the so-called digital addressable LED strips and the so-called analog non-addressable LED strips.

## Addressable LED Strips

Addressable LED Strips allows to control individual LEDs separately. This enables you to use many effects. The supported types are listed below. There are sometimes new types coming onto the market that have a compatible control protocol.

Sorting: 5v data only, 5v Data + Clock, 12v data only

| Type | Voltage | Comments |
|---|---|---|
SK6812 | 5v/12v | RGBW
WS2811 | 5v | usually found in IP68 sealed 12mm pixel strings
WS2812B | 5v |
WS2813 | 5v | has a backup data line
APA102 | 5v | using 2 data pins, Clock and Data
LPD8806 | 5v | using 2 data pins, Clock and Data
WS2801 | 5v | using 2 data pins, Clock and Data
SK9822 | 5v | using 2 data pins, Clock and Data
UCS8903 | 5v |
GS8208 | 12v |
TM1814 | 12v | RGBW
WS2811 | 12v | usually 3-LED segments, has data-line resistor
WS2814 | 12v/24v | RGBW, 3-LED groups (12V) / 6-LED groups (24V) as one logical LED. Must be controlled as SK6812 type, color order: BRG, swap W and G (this option is available since WLED 0.14.0-b1) 
WS2815 | 12v | has a backup data line
LPD6803 | 12v |
P9813 | 5-24 v |
TM1829 | 5-24 v |
UCS8904 | 5-24 v | RGBW

## Non-Addressable LED Strips

WLED supports non-addressable LED strips as well. Unlike addressable strips, non-addressable strips require a pin for each "color" channel and all LEDs are controlled the same way. To drive these strips, additional circuits (MOSFETs) are required. A basic circuit diagram is shown here. You need one MOSFET and one GPIO per color. It should be noted that the MOSFETs are destroyed very quickly in the event of an overload. To reduce the risk of fire and prevent personal injury, additional circuit elements should be implemented to protect MOSFETs from overtemperature and overload. Depending on the type, fuses are too slow for this! You might consider using self-protected MOSFETs too or the entire MOSFET circuit can be packed into a fire-retardant (e.g. metallic) housing.
![Controlling analog LED strios](../assets/images/content/pic29.jpg)

As of v0.13.1, WLED supports single color, CCT, RGB, RGBW and RGBCCT strips. These strips are commonly found at 12 or 24 volts.
The default PWM frequency for dimming is 880 Hz on ESP8266 and 19531 Hz for ESP32.
The commercially available so-called RGB(W) LED amplifiers can also be used (also called repeaters/boosters). These typically include optocouplers and MOSFET circuitry (1 to 5 channels) and can be used, for example, as follows:
![Controlling analog LED strios](../assets/images/content/pic44.jpg)

Note that there is no GND connection between the controller and the amplifier. And this despite the fact that with all other WLED circuits it is always said that all GNDs must be connected to each other. This special feature is due to the fact that the inputs of the amplifier are galvanically decoupled from the outputs by optocouplers and the amplifier in this circuit is used slightly differently than its usual application.

You can connect the GPIOs directly (3.3V signal level) to the input of the amplifier or, if you use a ready-made WLED controller, you can also use the data outputs (of the level shifter, i.e. 5 V signal level). You can also use both at the same time:
![Controlling analog LED strios](../assets/images/content/pic46.jpg)

The amplifier shown in the picture is a cheap product. Its advantage is a metal case. However, its circuit is very simple:
![Controlling analog LED strios](../assets/images/content/pic48.jpg)

The simple structure means that the duty cycle of the PWM signal (the ratio between pulse and period duration) at the output is slightly distorted compared to the input. In many cases this is not critical, but it does result in the color composition of an RGB strip being slightly distorted. A significantly better (and slightly more expensive) version is described in <a href="https://files2.elv.com/public/14/1431/143195/Internet/143195_led_rgbw_repeater.pdf" target="_blank">this article (in German, includes schematics)</a>. Here the MOSFETs are controlled with push-pull drivers. This and some other measures in the circuit mean that the PWM signal is reproduced very accurately at the output. There are also other variants on the market (e.g. MiBoxer RGBW amplifiers and similar ones) that promise very accurate PWM reproduction.
