---
title: Compatible Hardware
hide:
  # - navigation
  # - toc
---

!!! note ""
    Still under construction, feel free to add to the list!

This page lists some third-party hardware and/or tools that are working with WLED!

Please use a decent and neutral description when adding things to this list.

## Addressable LED Strips

| Type | Voltage | Comments |
|---|---|---|
WS2812B | 5v |
WS2813 | 5v |
SK6812 | 5v | RGBW
APA102 | 5v | C/D
WS2801 | 5v | C/D
LPD8806 | 5v | C/D
TM1814 | 12v | RGBW
WS2811 | 12v | 3-LED segments, has data-line resistor
WS2815 | 12v |
GS8208 | 12v |

## ESP8266/ESP32 boards

| Name | Chip | Description |
|---|---|---|
[Wemos D1 mini](https://docs.wemos.cc/en/latest/d1/d1_mini.html) | ESP8266 | An affordable ESP8266 development board. Aircoookie's recommendation for running WLED. Current version: 3.1.0
[Wemos D1 mini Pro](https://docs.wemos.cc/en/latest/d1/d1_mini_pro.html) | ESP8266 | A newer development board with an external antenna connector. Works very well with WLED. Recommended if your signal strength is too low with another board. Current version: 2.0.0. Version 1.0.0 has the same form factor as the D1 mini.
[NodeMCU](https://github.com/nodemcu/nodemcu-devkit-v1.0) | ESP8266 | Another popular ESP8266 development board. A bit bigger than the D1 and has pins pre-soldered. There are multiple versions with slight differences, not all are tested.
[Heltec WiFi Kit 8](https://heltec.org/project/wifi-kit-8/) | ESP8266 | Another alternative of ESP8266 board. OLED display 128X32 pixel, battery charger on board. Almost the same functionality and price as the Wemos board. Plus it can be used in projects with external batteries.
ESP-01 | ESP8266 | One of the first and cheapest ESP8266 boards available. **_Not recommended for WLED_** (needs external USB/serial chip, voltage converter, only has 1mb of flash, so soon no wireless updates possible)
[Shelly RGBW2](https://shelly.cloud/wifi-smart-shelly-rgbw-2/) | ESP8266 | For "analog" LED use only! Runs on 12-24VDC. One button and one input. Pins: R=12, G=15, B=14, W=4. _Finished, commercial product that can be flashed._ [Binary code fork is here](https://github.com/srg74/WLED/tree/ShellyRGBW2) and [firmware is here](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/Shelly_RGBW2)
[H803 WiFi](https://github.com/srg74/WLED/wiki/H803WiFi) | ESP8266 | ESP8266EX based controller with level shifter inside. Data pin GPIO1 Clock pin GPIO14. Tested with WS2813 strip and [Firmware fork is here](https://github.com/srg74/WLED/tree/H803WF).
[D1 mini-style ESP32](https://acrobotic.com/products/acr-00024) | ESP32 | A nice compact ESP32 development board. D1 mini compatible layout.
[ESP32 DevKitC v4](https://www.digikey.com/product-detail/en/espressif-systems/ESP32-DEVKITC-32D/1965-1000-ND/9356990) | ESP32 | The original ESP32 Development Board made by Espressif Systems.
NodeMCU-32s | ESP32 | The most common ESP32 development board. Works well, depending on the board you might have to press the "Boot" button while USB flashing
[Olimex ESP32 POE](https://www.olimex.com/Products/IoT/ESP32/ESP32-POE) | ESP32 | Ethernet (PoE) and WiFi, though usage of the ethernet port requires a custom compile. The PoE should not be used to power LEDs due to a maximum throughput of 4W. For most installations, standard ethernet should be used, supplying power through the 5V pin.
[WT32-ETH01](https://www.aliexpress.com/wholesale?&SearchText=wt32-eth01) | ESP32 | **Under development!** Ethernet (non-PoE) and WiFi enabled alternative to the Olimex boards, for 1/4 the cost. Features no PoE, and requires initial flashing of a custom compiled image using a FTDI or similar USB to serial converter.
[Merkury MI-BW210-999W](https://www.walmart.com/ip/Merkury-Innovations-A21-Smart-Light-Bulb-75W-Color-LED-2-Pack/669037420) | ESP8285 | Tuya Style WiFi Led light bulb, Warm White + RGB. There are two versions of this same bulb sold in the same packaging only way to check is to look at the bulb, EBEQPW92 uses PWM led control and is compatible with WLED however EBEQPW06 uses an SM16716 chip and is not currently compatible with WLED. Managed to flash using tuya-convert and a custom WLED build with the following analog pinout: B:4, G:5, R:13, W:14. Extras disabled to allow OTA, OTA only way to flash this, programming headers are not internally available.
[Adafruit Feather Huzzah](https://learn.adafruit.com/adafruit-feather-huzzah-esp8266) | ESP8266 | General-purpose ESP8266 Board with USB, battery connector, etc.
[SP501e](https://www.amazon.com/RGBZONE-Controller-Compatible-Addressable-WS2812bB/dp/B07S3Z8GSH) | ESP8285 | 8285-based 1M Controller that supports both Addressable and PWM-based RGBWW LED strips. _Note that recent versions have 2M._ 5-24v DC input, 55mm x 26mm, sold under BTF lighting, RGBZone, etc. Vendors all list 'Fairynest' as the supporting mobile application. Board is silk screened with 'SP5XXe' but no other markings. RS232 pads are exposed on the back-side of the board with GND and GPIO0 right next to each other and thus Flash access fairly straight forward. GPIO 0 must be pulled to GND at boot and throughout the flashing process.  I/O configuration: LEDPIN is 'GPIO03' for Addressable, BTNPIN is GPIO 1. PWM pin out for RGBWW: CW: 14, WW: 12, B: 13, R: 15 and G: GPIO04. Flashed via PlatformIO, ESPHome and Tasmotizer. Pics of board here: <https://github.com/Operation760/SP501e-RGB-LED-Controller-/blob/master/SP501e_top_bottom_traced.jpg>  Flashing Connections: <https://github.com/tonyn0/sp501e-flashing/blob/main/sp501e%20flash.png>
[SP108e v2](https://www.amazon.de/dp/B07KW1W68R) | ESP8285 | Hardware-Modification required and different versions exists! 8285-based 2M Controller that supports addressable RGBWW LED strips, also with CLK line (like ATA102). 5-24v DC input, 85mm x 45mm x 23mm. Vendors list spledapps 'Led Shop' as the supporting mobile application. Board is silk screened with 'SP108e'. No pads are exposed and a second processor is used to control the LEDs. Pin7 of that processor needs to be grounded to hold it in reset state. Then you can connect GPIO0 to GND and TX, RX, VCC, GND for flashing. Connect GPIO2 to R4 for DATA out and GPIO13 to R3 for CLK out. Flashed via PlatformIO, esptool. OTA updates work. Pics of pinout here: <https://github.com/psxde/sp108e-led-controller/raw/main/sp108ev2_inside.png>
[RE5V1C](https://www.itead.cc/sonoff-re5v1c.html) | ESP8285 | 5v DC input - onboard 10A relay
[TwilightLord-ESP32](https://www.tindie.com/products/22968/)| ESP32 | ESP32 Dev Board with latest WROOM-32E module, USB Type-C, 800mA LDO, 8MB flash and PTC fused. D1 Mini32 form factor and compatible pin out.[16MB Flash version also available](https://www.tindie.com/products/23037/)
[TwilightLord-ESP32 Ethernet Shield](https://www.tindie.com/products/23050/)| Ethernet Shield (10/100Mbps) for ESP32 boards. Stackable with D1 Mini32 form factor boards.
[QuinLED-ESP32](https://quinled.info/quinled-esp32/)| Custom design D1 Mini32 formfactor ESP32 module | Fed up with the bad quality of generic ESP32 modules on the market, designed my own "beefed up" version.

Available in multiple versions:

* QuinLED-ESP32-AB (Antenna Board)
* QuinLED-ESP32-AE (Antenna External)
* QuinLED-ESP32-ABE (Antenna Board + Ethernet)

## Useful boards and addons

| Name | Description |
|---|---|
[QuinLED Dig-Uno](https://quinled.info/2018/09/15/quinled-dig-uno/) | **2021 updated version!** DIY/Pre-Assembled board for digital LED driving. Integrated level shifters, temperature sensor option, Auto 5v-24v compatibility, pull-up/down GPIO and safety features such as a onboard fuse. Recommended to use (and comes with) with [custom QuinLED-ESP32](https://quinled.info/quinled-esp32/).
Pre-assembled and pre-flashed with WLED [available to buy!](https://quinled.info/pre-assembled-quinled-dig-uno/)
[QuinLED Dig-Quad](https://quinled.info/2020/06/17/quinled-dig-quad/) | **2021 updated version!** DIY/Pre-Assembled board for 4 (5) channel digital LED driving. Integrated level shifters, temperature sensor option, Auto 5v-24v compatibility, pull-up/down GPIO and power distribution terminals with 5x onboard fuses for easy LED power injection. Recommended to use (and comes with) with [custom QuinLED-ESP32](https://quinled.info/quinled-esp32/).
Pre-assembled and pre-flashed with WLED [available to buy!](https://quinled.info/pre-assembled-quinled-dig-quad/)
[WLAN Pixel Controller](https://shop.codm.de/automation/pixel/30/wlan-pixel-controller) | Fully completed and control PCB with level shifter pre-flashed with WLED!
[WLED Wemos shield](https://github.com/srg74/WLED-wemos-shield) | DIY board, 100% compatible with WLED project and WLED [sound reactive fork](https://github.com/atuline/WLED). Integrated level shifter, 4 outputs for LEDs strips, 1 fused out for LED strip, resettable fuse for the development board, exposed I2C interface for display or sensors, relay for energy-saving and 1-wire temperature sensor. Exposed pins for Analog and Digital microphones. Works with Wemos D1 mini and D1-style ESP32 boards. [Firmware is here](https://github.com/srg74/WLED/tree/WLED_wemos_shield).
[WLED waterproof controller with external antenna](https://github.com/srg74/Controller-for-WLED-firmware) | DIY board, designed for use outside permanently and for longer range Wi-Fi connection. No SMD components means it is easier to solder for DIYers. 100% compatible with WLED project. Level shifter, fuse for LED strip, resettable fuse for Wi-Fi module, exposed I2C interface for display or sensors, relay for energy-saving and 1-wire temperature sensor. Build around ESP-07S module. [Firmware is here](https://github.com/srg74/WLED/tree/ESP-07S)
[Wemos D1 mini Level Shifter Shield](https://www.tindie.com/products/jasoncoon/wemos-d1-mini-esp8266-level-shifter-mini-shield/) | A level shifter shield (74HCT125) - by Evil Genius Labs LLC.
[WLAN Pixel Controller](https://shop.codm.de/automation/pixel/30/wlan-pixel-controller) | Fully completed and control PCB with level shifter pre-flashed with WLED!
[Simple WLED Board](https://github.com/wladwnt/wled) | Very simple DIY board, minimum of required components, option for 5V/12V LEDs. Easy to solder (no SMT components). Simple to understand connection schematics and pictures. Can be used with ESP8266 or ESP32 in D1 mini Format.
[IOT4WLED](https://iot4.eu/product/iot4wled/) | Ready to use hardware for WLED!
[ESPthings.io ET-AL01](https://www.espthings.io/AL01) | DIY board for 5 Analog channels and/or up to 5 Digital LED channels (or a combination of the latter as required), Integrated level shifter, 5v/12/24v compatibility, 4x pull-up/down GPIO, serial interface and power distribution terminals. Can be used with Wemos D1-style ESP8266 or ESP32 boards.
[Cadsbi Motion Smart](https://www.cadsbi-shop.de/shop/led-beleuchtungscontroller/cadsbi-motion-smart/) | Ready to use solution with 3 output ports, an external antenna, in a high quality metal enclosure
[WiFi Controlled Desk Lamp](https://github.com/stanoba/wifi-desk-lamp) | Open source PCB for WLED
[My Baby's Got LED](https://tindie.com/products/mcqn_ltd/my-babys-got-led/)| [Certified open hardware](https://certification.oshwa.org/uk000030.html). Easy plug-and-play WLED board for those that don't want to figure out the hardware - you won't even need a screwdriver to get started. PC power supply ([ATX](https://en.wikipedia.org/wiki/ATX#:~:text=An%20ATX%20power%20supply%20provides,the%20original%2020-pin%20version.)) powers three 5V injection points on 8A fuses.
For sale now on [Tindie](https://tindie.com/products/mcqn_ltd/my-babys-got-led/)! Full details on [the github repo](https://github.com/mcqn/my-babys-got-led) and [maker's website](https://mcqn.com/ibal223/).
[Luminxa v2.2.2](https://luminxa.com/product/luminxa-2-2-2/) | ESP32 | ESP32 Based board with 12 WS2812 LEDs Onboard (6 on each side) + Gyro Sensor (Business project)
[LedBox V2](https://stanleyprojects.com/projects/ledbox_v2/) | ESP32 | LedBox V2 by StanleyProjects is a small ESP32 based module for controlling 5-12V addressable LED strips (WS2812, SK6812, etc.), including digital MEMS microphone, button and IR control, safety resettable fuse, and a 3D printable case. It is fully compatible with [WLED](https://github.com/Aircoookie/WLED) and [sound reactive WLED fork](https://github.com/atuline/WLED).

## Levelshifters

| Name | Description |
|---|---|
SN74AHCT125N | Aircoookie's recommended levelshifter. Used on the QuinLed Dig-Uno and [WLED Wemos shield](https://github.com/srg74/WLED-wemos-shield).
SN74HCT125N | Slower, cheaper version. Works just as well for WS2812, but not recommended for APA102.
TXS0102 | A bidirectional levelshifter that works well with WLED.

NB: I2C shifters are too slow for wled, so don't use them.

## USB/TTL adapters

| Name | Description |
|---|---|
[CH340](https://www.aliexpress.com/item/32761423124.html) | CH340 module instead of CP2102, PL2303 or FTDI/FTDT. The CH340 can deliver more current which is needed while the flash process depending on the board type. The timing is also much more stable. **For boards with an USB/TTL adapter onboard this is NOT needed**
[ESP uploader](https://github.com/srg74/ESP-uploader) |  CP2102N module. Same USB to UART converter as many recent Dev boards using. Featuring latest USB-C connector. For use with many ESP32, ESP8266, ESP8255 and Tuya based modules. 3.3V logic and 5V power pass through for custom boards.
