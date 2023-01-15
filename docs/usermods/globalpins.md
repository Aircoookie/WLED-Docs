---
title: Usermod global pins
hide:
  # - navigation
  # - toc
---

I2C and SPI

This page is work in progress

## Pin dropdowns
<img width="170" alt="image" src="https://user-images.githubusercontent.com/91013628/212557801-0329826a-9d00-4c85-abd9-049c73c5a773.png">

Nr of pins and functionality is depending on the board chosen (esp8266, esp32, esp32-c2, esp32-c3, esps32-s3)

* First option is undefined or use global (global pin)
* 🔴 pin used by other usermod / global pins, cannot be selected
* 🟠 read only pin: will be disabled for signals which write
* 🟣 reserved pin: cannot be selected
* ⍼ pin defined by board (e.g. I2C on esp32 is 21/22)
* ⎌ pin defined by bin / platformio entry

## Pin allocation
* 8266: default I2C pins for most esp8266 variants are SDA=4 and SCL=5 (and one i2c instance only). So you can have 0 or 1 I2C bus.
* esp32: has two "I2C hardware units" that can attach to any pin.  So you could have 0 or 1, or 2 I2C buses.
* currently WLED only uses "i2c unit 0" on esp32. So in reality you can have 0 or 1 I2C bus.
* WLED does not support "software I2C" - that's a common misunderstanding because people see they can freely chose pins on esp32.
* once the I2C bus pins are set on ESP32, all usermods have to use these pins for I2C. Changing I2C pins requires a reboot.
* four-line-display is an exception, because the driver library has its own "software I2C" - slow but can always be used

* on both esp32 and 8266, you can decide to not use I2C, and use pins for something else. For example (on 8266), attach some buttons or rotary encoder to gpio 4+5. 
* similar for SPI - if you want SPI, the pins are fixed on 8266. If you don't need SPI, the pins can be used for something else.
* on esp32 its a bit more complicated even, because the fastest SPI modes are only possible on certains pins. But still if people don't want SPI, the pins can be used for something different.

## Fork specific info

### WLED SR
Pin drop downs not supported

### WLED AC
Pin drop downs not supported

