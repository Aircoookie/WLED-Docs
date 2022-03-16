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

!!! tip
    Lists are in alphabetical order. The position of an item in the list does not indicate how good it is or if it will fit your use case.
    Please carefully compare all items in the category you are interested in, and you should find the one that suits your needs best in just a few minutes! 

## Addressable LED Strips

Sorting: 5v data only, 5v Data + Clock, 12v data only, non-addressable analog PWM

| Type | Voltage | Comments |
|---|---|---|
SK6812 | 5v | RGBW
WS2811 | 5v | usually found in IP68 sealed 12mm pixel strings
WS2812B | 5v |
WS2813 | 5v |
APA102 | 5v | needs Clock/Data
LPD8806 | 5v | needs Clock/Data
WS2801 | 5v | needs Clock/Data
SK9822 | 5v | needs Clock/Data
GS8208 | 12v |
TM1814 | 12v | RGBW
WS2811 | 12v | usually 3-LED segments, has data-line resistor
WS2815 | 12v | has a backup data line
Analog PWM | Usually 12v/24v | Needs additional hardware (MOSFETs). Needs 3-4 pins per separately controllable strip

## Controllers with WLED pre-installed

!!! check "Info"
    Unless otherwise noted, controllers feature everything you need for most WLED setups, except a power supply, wiring and fuses, and of course the LEDs themselves!
    
| Name | Description |
|---|---|
[ABC! WLED Controller / ESP8266](https://shop.myhome-control.de/ABC-WLED-Controller-V31-ESP8266/HW10002) | Commercial controller for 5V LED strips. Based on ESP8266 uC. Two outputs. Ready to use. Additional Relay&Fuse board available. (German shop & shipping only within Germany). A similar one is available at [WLED.SHOP](https://wled.shop/produkt/wladis-wled-controller-v31/)
[ABC! WLED Controller / ESP32](https://shop.myhome-control.de/ABC-WLED-Controller-V41-ESP32/HW10003.1) | Commercial controller for 5V LED strips. Based on ESP32 uC. Two outputs. Option for digital microphone / sound reactive. Ready to use. Additional Relay&Fuse board available. (German shop & shipping only within Germany). A similar one is available at [WLED.SHOP](https://wled.shop/produkt/wladis-wled-controller-v40-esp32/).
[Athom Light Strip Controller](https://www.aliexpress.com/item/1005002198527735.html) | Simple controller with enclosure for reliaby driving 3 pin 5V LEDs. Uses 2M ESP8266.
[Cadsbi Motion Smart](https://www.cadsbi-shop.de/shop/led-beleuchtungscontroller/cadsbi-motion-smart/) | Ready to use solution with 3 output ports, an external antenna, in a high quality metal enclosure
[ESPthings.io ET-AL01](https://www.espthings.io/AL01) | DIY board for 5 Analog channels and/or up to 5 Digital LED channels (or a combination of the latter as required), Integrated level shifter, 5v/12/24v compatibility, 4x pull-up/down GPIO, serial interface and power distribution terminals. Can be used with Wemos D1-style ESP8266 or ESP32 boards.
[IOT4WLED](https://iot4.eu/product/iot4wled/) | Ready to use hardware for WLED!
[Laterna](https://github.com/Planet-Laterna/Laterna) | Based on an ESP32 for digital LED and RBG/RGBW LED strops with support for 5V, 12V and 24V LED strips. (Up to 4 channels)
[Laterna Stick](https://github.com/Planet-Laterna/Laterna_Stick) | USB Stick like ESP32 based controller for digital 5V LED strips.
[LedBox V2](https://stanleyprojects.com/projects/ledbox_v2/) | LedBox V2 by StanleyProjects is a fully contained, sound reactive, ESP32 based module for controlling 5-12V addressable LED strips (WS2812, SK6812, etc.), supporting both 3-(VDD,DAT,GND) and 4-(VDD,DAT,CLK,GND) pin configuration. It includes a digital MEMS microphone, button and IR control, and a safety resettable fuse, all in a compact 3D printable case. The board comes all setup, flashed with <a href=https://github.com/atuline/WLED>sound reactive WLED fork</a>, and can be purchased [here](https://www.tindie.com/products/stanleyprojects/ledbox-v2/).
[Luminxa v2.2.2](https://luminxa.com/product/luminxa-2-2-2/) | ESP32 | ESP32 Based board with 12 WS2812 LEDs Onboard (6 on each side) + Gyro Sensor (Business project)
[My Baby's Got LED](https://tindie.com/products/mcqn_ltd/my-babys-got-led/)| [Certified open hardware](https://certification.oshwa.org/uk000030.html). Easy plug-and-play WLED board for those that don't want to figure out the hardware - you won't even need a screwdriver to get started. PC power supply ([ATX](https://en.wikipedia.org/wiki/ATX#:~:text=An%20ATX%20power%20supply%20provides,the%20original%2020-pin%20version.)) powers three 5V injection points on 8A fuses. For sale now on [Tindie](https://tindie.com/products/mcqn_ltd/my-babys-got-led/)! Full details on [the github repo](https://github.com/mcqn/my-babys-got-led) and [maker's website](https://mcqn.com/ibal223/).
[QuinLED Dig-Uno](https://quinled.info/quinled-dig-uno/) | **2021 updated version!** DIY/Pre-Assembled board for digital LED driving. Integrated level shifters, temperature sensor option, Auto 5v-24v compatibility, pull-up/down GPIO and safety features such as a onboard fuse. Recommended to use (and comes with) with [custom QuinLED-ESP32](https://quinled.info/quinled-esp32/). Pre-assembled and pre-flashed with WLED [available to buy!](https://quinled.info/pre-assembled-quinled-dig-uno/). Aircoookie's personal recommendation for medium-size WLED projects.
[QuinLED Dig-Quad](https://quinled.info/quinled-dig-quad/) | **2021 updated version!** DIY/Pre-Assembled board for 4 (5) channel digital LED driving. Integrated level shifters, temperature sensor option, Auto 5v-24v compatibility, pull-up/down GPIO and power distribution terminals with 5x onboard fuses for easy LED power injection. Recommended to use (and comes with) with [custom QuinLED-ESP32](https://quinled.info/quinled-esp32/). Pre-assembled and pre-flashed with WLED [available to buy!](https://quinled.info/pre-assembled-quinled-dig-quad/). Aircoookie's personal recommendation for large-size WLED projects with advanced power and output requirements.
[Simple WLED Board](https://github.com/wladwnt/wled) | Very simple DIY board, minimum of required components, option for 5V/12V LEDs. Easy to solder (no SMT components). Simple to understand connection schematics and pictures. Can be used with ESP8266 or ESP32 in D1 mini Format.
[WiFi Controlled Desk Lamp](https://github.com/stanoba/wifi-desk-lamp) | Open source PCB for WLED
[WLAN Pixel Controller](https://shop.codm.de/automation/pixel/30/wlan-pixel-controller) | Fully completed and control PCB with level shifter pre-flashed with WLED!
[WLED Wemos shield](https://github.com/srg74/WLED-wemos-shield) | DIY board, 100% compatible with WLED project and WLED [sound reactive fork](https://github.com/atuline/WLED). Integrated level shifter, 4 outputs for LEDs strips, 1 fused out for LED strip, resettable fuse for the development board, exposed I2C interface for display or sensors, relay for energy-saving and 1-wire temperature sensor. Exposed pins for Analog and Digital microphones. Works with Wemos D1 mini and D1-style ESP32 boards. [Firmware is here](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_wemos_shield).
[WLED waterproof controller with external antenna](https://github.com/srg74/Controller-for-WLED-firmware) | DIY board, designed for use outside permanently and for longer range Wi-Fi connection. No SMD components means it is easier to solder for DIYers. 100% compatible with WLED project. Level shifter, fuse for LED strip, resettable fuse for Wi-Fi module, exposed I2C interface for display or sensors, relay for energy-saving and 1-wire temperature sensor. Build around ESP-07S module. [Firmware is here](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_wemos_shield)
[Yet Another WLED Controller](https://github.com/lizardsystems/yawl-controller) | Small and simple device for 5V addressable LED strips with minimum components and fully assembled by PCB manufacturing service in standard case. [Firmware is here](https://github.com/lizardsystems/yawl-controller/tree/main/firmware/WLED)


## Controllers WLED can be installed to

!!! warning
    If the controller does not have a USB port and no firmware supporting wireless updates pre-installed, installing WLED to it requires an FTDI flasher and in some cases, soldering.

| Name | Chip | Description |
|---|---|---|
[ESPixelStick v3](https://forkineye.com/espixelstick-v3/) | ESP8266 | The ESPixelStick V3 is a WiFi Pixel and DMX single output controller built around the ESP8266 platform. It utilizes industry standard E1.31 sACN and DDP protocols for control of up to 680 WS2811 pixels (4 Universes) or 63 GECE Pixels.  The output passes through a built-in RS485 transceiver, allowing for driving DMX and differential Renard inputs (or using a differential receiver for long-distance between board and first pixel). The on board switching regulator allows you to power the ESPixelStick with 5V-24V -- Just match the voltage of the pixels you are using, no voltage configuration is required.  Note: Does _**not**_ come preconfigured with WLED, you must flash the ESP8266 yourself.
[SP108e v2](https://www.amazon.de/dp/B07KW1W68R) | ESP8285 | Hardware-Modification required and different versions exists! 8285-based 2M Controller that supports addressable RGBWW LED strips, also with CLK line (like ATA102). 5-24v DC input, 85mm x 45mm x 23mm. Vendors list spledapps 'Led Shop' as the supporting mobile application. Board is silk screened with 'SP108e'. No pads are exposed and a second processor is used to control the LEDs. Pin7 of that processor needs to be grounded to hold it in reset state. Then you can connect GPIO0 to GND and TX, RX, VCC, GND for flashing. Connect GPIO2 to R4 for DATA out and GPIO13 to R3 for CLK out. Flashed via PlatformIO, esptool. OTA updates work. Pics of pinout here: <https://github.com/psxde/sp108e-led-controller/raw/main/sp108ev2_inside.png>
SP501e | ESP8285 | 8285-based 1M Controller that supports both Addressable and PWM-based RGBWW LED strips. _Note that recent versions have 2M._ 5-24v DC input, 55mm x 26mm, sold under BTF lighting, RGBZone, etc. Vendors all list 'Fairynest' as the supporting mobile application. Board is silk screened with 'SP5XXe' but no other markings. Serial pads are exposed on the back-side of the board with GND and GPIO0 right next to each other and thus Flash access fairly straight forward. GPIO 0 must be pulled to GND at boot and throughout the flashing process.  I/O configuration: LEDPIN is 'GPIO3' for addressable (note this pin is limited to approx. 250 LEDs), BTNPIN is GPIO 1. PWM pin out for RGBWW: CW: 14, WW: 12, B: 13, R: 15 and G: 4. Flashed via PlatformIO, ESPHome and Tasmotizer. Pics of board here: <https://github.com/Operation760/SP501e-RGB-LED-Controller-/blob/master/SP501e_top_bottom_traced.jpg>  Flashing Connections: <https://github.com/tonyn0/sp501e-flashing/blob/main/sp501e%20flash.png>
[SP511e](https://www.aliexpress.com/item/32820185063.html) | ESP8285 | An ESP8285 2MB controller with 3 case buttons, built in mic, IR receiver, 38 key remote, and dual outputs. The dual outputs are connected to the same data pin. There is a step-by-step guide for [Installing WLED on SP511E Controller](https://github.com/scottrbailey/WLED-Utils/blob/gh-pages/sp511e_wled.md).
[ESP LED Strip WIFI Control Board [ESP Version]](https://www.electrodragon.com/product/esp-led-strip-board) | ESP8266 | Controller for addressable or analog LEDs (RGBW), 6-27VDC input, no level shifter, reset and boot buttons, enclosure. NOTE: Although this uses high-current transistors, they used jumpers on two of the connections so you are limited to their current rating (3A?).

## Other products WLED can be installed to

| Name | Chip | Description |
|---|---|---|
[Merkury MI-BW210-999W](https://www.walmart.com/ip/Merkury-Innovations-A21-Smart-Light-Bulb-75W-Color-LED-2-Pack/669037420) | ESP8285 | Tuya Style WiFi Led light bulb, Warm White + RGB. There are two versions of this same bulb sold in the same packaging only way to check is to look at the bulb, EBEQPW92 uses PWM led control and is compatible with WLED however EBEQPW06 uses an SM16716 chip and is not currently compatible with WLED. Managed to flash using tuya-convert and a custom WLED build with the following analog pinout: B:4, G:5, R:13, W:14. Extras disabled to allow OTA, OTA only way to flash this, programming headers are not internally available.
[Shelly RGBW2](https://shelly.cloud/wifi-smart-shelly-rgbw-2/) | ESP8266 | For "analog" LED use only! Runs on 12-24VDC. One button and one input. Pins: R=12, G=15, B=14, W=4. _Finished, commercial product that can be flashed._ [More info and flashing docs](https://tasmota.github.io/docs/devices/Shelly-RGBW2/#serial-connection)
[Athom 15W bulb](https://www.athom.tech/blank-1/15w-color-bulb) | ESP8266 (2M flash) | 15W bulb with RGB, warm white, and cold white LEDs. Compatible with all voltages, available form factors E27, B22 and [GU10](https://www.aliexpress.com/item/1005003512212258.html)

## Raw ESP8266/ESP32 boards

!!! tip
    While these can work like the controllers above without extra hardware, you might get flickering without adding an external levelshifter. Using them without a controller board/shield is only recommended if you like tinkering with electronic projects.

| Name | Chip | Description |
|---|---|---|
[Adafruit Feather Huzzah](https://learn.adafruit.com/adafruit-feather-huzzah-esp8266) | ESP8266 | General-purpose ESP8266 Board with USB, battery connector, etc.
[D1 mini-style ESP32](https://acrobotic.com/products/acr-00024) | ESP32 | A nice compact ESP32 development board. D1 mini compatible layout.
[ESP32 DevKitC v4](https://www.digikey.com/product-detail/en/espressif-systems/ESP32-DEVKITC-32D/1965-1000-ND/9356990) | ESP32 | The original ESP32 Development Board made by Espressif Systems.
[H803 WiFi](https://github.com/srg74/WLED/wiki/H803WiFi) | ESP8266 | ESP8266EX based controller with level shifter inside. Data pin GPIO1 Clock pin GPIO14. Tested with WS2813 strip and [Firmware fork is here](https://github.com/srg74/WLED/tree/H803WF).
NodeMCU-32s | ESP32 | The most common ESP32 development board. Works well, depending on the board you might have to press the "Boot" button while USB flashing
[Heltec WiFi Kit 8](https://heltec.org/project/wifi-kit-8/) | ESP8266 | Another alternative of ESP8266 board. OLED display 128X32 pixel, battery charger on board. Almost the same functionality and price as the Wemos board. Plus it can be used in projects with external batteries.
[NodeMCU](https://github.com/nodemcu/nodemcu-devkit-v1.0) | ESP8266 | Another popular ESP8266 development board. A bit bigger than the D1 and has pins pre-soldered. There are multiple versions with slight differences, not all are tested.
ESP-01 | ESP8266 | One of the first and cheapest ESP8266 boards available. **_Not recommended for general WLED installs_** (needs external USB/serial chip, voltage converter, only has 1mb of flash, so soon no wireless updates possible)
[Olimex ESP32 POE](https://www.olimex.com/Products/IoT/ESP32/ESP32-POE) | ESP32 | Ethernet (PoE) and WiFi, though usage of the ethernet port requires a custom compile. The PoE should not be used to power LEDs due to a maximum throughput of 4W. For most installations, standard ethernet should be used, supplying power through the 5V pin.
[QuinLED-ESP32](https://quinled.info/quinled-esp32/)| Custom design D1 Mini32 formfactor ESP32 module | Fed up with the bad quality of generic ESP32 modules on the market, designed my own "beefed up" version. Available in multiple versions: QuinLED-ESP32-AB (Antenna Board), QuinLED-ESP32-AE (Antenna External), QuinLED-ESP32-ABE (Antenna Board + Ethernet). Aircoookie's recommendation for running WLED.
[RE5V1C](https://www.itead.cc/sonoff-re5v1c.html) | ESP8285 | 5v DC input - onboard 10A relay
[TwilightLord-ESP32](https://www.tindie.com/products/22968/)| ESP32 | ESP32 Dev Board with latest WROOM-32E module, USB Type-C, 800mA LDO, 8MB flash and PTC fused. D1 Mini32 form factor and compatible pin out.[16MB Flash version also available](https://www.tindie.com/products/23037/)
[Wemos D1 mini](https://docs.wemos.cc/en/latest/d1/d1_mini.html) | ESP8266 | An affordable ESP8266 development board. Aircoookie's recommendation for running WLED if you want an ESP8266 board. Current version: 3.1.0
[Wemos D1 mini Pro](https://docs.wemos.cc/en/latest/d1/d1_mini_pro.html) | ESP8266 | A newer development board with an external antenna connector. Works very well with WLED. Recommended if your signal strength is too low with another board. Current version: 2.0.0. Version 1.0.0 has the same form factor as the D1 mini.
[WT32-ETH01](https://www.aliexpress.com/wholesale?&SearchText=wt32-eth01) | ESP32 | **Under development!** Ethernet (non-PoE) and WiFi enabled alternative to the Olimex boards, for 1/4 the cost. Features no PoE, and requires initial flashing of a custom compiled image using a FTDI or similar USB to serial converter.

## Useful boards and addons

| Name | Description |
|---|---|
[TwilightLord-ESP32 Ethernet Shield](https://www.tindie.com/products/23050/)| Ethernet Shield (10/100Mbps) for ESP32 boards. Stackable with D1 Mini32 form factor boards.
[Wemos D1 mini Level Shifter Shield](https://www.tindie.com/products/jasoncoon/wemos-d1-mini-esp8266-level-shifter-mini-shield/) | A level shifter shield (74HCT125) - by Evil Genius Labs LLC.

## Compatible PC RGB Fans and ARGB accessories

| Brand | Model | Comments |
|---|---|---|
Corsair | HD120 Fan | Uses WS2812B, data-in only
PCCOOLER | Moonlight 5-pack Fans | Uses WS2812B, includes Data-out connector to keep each fan uniquely addressable if wired in series like traditional LED strips
Any | 5v 3-pin ARGB for PC | Any PC RGB device that supports the 5v 3-pin ARGB motherboard header should work fine with WLED. All the major motherboard vendors support the Corsair HD120 and PCCOOLER fans listed, so we can safely assume any device that supports motherboard ARGB 5V 3-Pin standard will work with WLED.

## Levelshifters

| Name | Description |
|---|---|
SN74AHCT125N | Aircoookie's recommended levelshifter. Used on the QuinLed Dig-Uno and [WLED Wemos shield](https://github.com/srg74/WLED-wemos-shield).
74AHCT32 | Same pinout as above can be used. This is just an OR gate, but any AHCT gate can be used if inputs are connected appropriately. ;)
SN74HCT125N | Slower, cheaper version. Works just as well for WS2812, but not recommended for APA102.
SN74LVC2T45 | Modern bus transceiver with voltage translation [Yet Another WLED Controller](https://github.com/lizardsystems/yawl-controller)
TXS0102 | A bidirectional levelshifter that works well with WLED.
[F-Amp](https://www.pixelcontroller.com/store/controllers/53-falcon-picap.html) | Level shifter/data booster

!!! warning
    I2C shifters are generally too slow for WLED, so don't use them.

## USB/TTL adapters

| Name | Description |
|---|---|
[CH340](https://www.aliexpress.com/item/32761423124.html) | CH340 module instead of CP2102, PL2303 or FTDI/FTDT. The CH340 can deliver more current which is needed while the flash process depending on the board type. The timing is also much more stable. **For boards with an USB/TTL adapter onboard this is NOT needed**
[ESP uploader](https://github.com/srg74/ESP-uploader) |  CP2102N module. Same USB to UART converter as many recent Dev boards using. Featuring latest USB-C connector. For use with many ESP32, ESP8266, ESP8255 and Tuya based modules. 3.3V logic and 5V power pass through for custom boards.

## Miscellaneous

Sorting: Sensors, Displays, Actuators

| Name | Description |
|---|---|
[HC-SR501](https://www.aliexpress.com/wholesale?catId=0&SearchText=HC-SR501) | PIR sensor with adjustable sensitivity and on time delay (suitable as a button).
[HC-SR602](https://www.aliexpress.com/wholesale?catId=0&SearchText=HC-SR602) | PIR sensor (not suitable as a button but can be used with _PIR sensor_ usermod).
[TSOP38238](https://www.aliexpress.com/item/32834341300.html) | IR receiver compatible with most IR remotes.
[SSD1305](https://www.aliexpress.com/wholesale?catId=0&SearchText=SSD1305) | I2C display, can be used with [_4 Line Display_ usermod](https://github.com/Aircoookie/WLED/tree/master/usermods/usermod_v2_four_line_display).
[SSD1306](https://www.aliexpress.com/wholesale?catId=0&SearchText=SSD1306) | I2C & SPI display, can be used with _4 Line Display_ usermod.
[5V relay](https://www.aliexpress.com/wholesale?catId=0&SearchText=5v+relay+module) | Relay module. Some will require 5V to trigger so you will need level-shifted output (similar as for LEDs) for proper functionality or a circuit with transistor or MOSFET.
DS18B20 | Recommended temperature sensor for use with WLED. Compatible with the [Temperature usermod](https://github.com/Aircoookie/WLED/tree/master/usermods/Temperature)
