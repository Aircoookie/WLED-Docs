---
title: Usermod global pins
hide:
  # - navigation
  # - toc
---

I2C and SPI

This page is work in progress

## pin allocation
* on 8266 the pins for I2C are fixed (and one i2c unit only). So you can have 0 or 1 I2C bus.
* on esp32 there are two "I2C units" that can attach to any pin.  So you could have 0 or 1, or 2 I2C buses.
* currently WLED only uses "i2c unit 0" on esp32. So in reality you can have 0 or 1 I2C bus.
* WLED does not support "software I2C" - that's a common misunderstanding because people see they can freely chose pins on esp32.
* Once the I2C bus pins are set on ESP32, all usermods have to use these pins for I2C. Changing I2C pins requires a reboot.
* four-line-display is an exception, because the driver library has its own "software I2C" - slow but can always be used

* On both esp32 ans 8266, you can decide to not use I2C, and use pins for something else. For example (on 8266), attach some buttons or rotary encoder to gpio 4+5. 
* similar for SPI - if you want SPI, the pins are fixed on 8266. If you don't need SPI, the pins can be used for something else.
* on esp32 its a bit more complicated even, because the fastest SPI modes are only possible on certains pins. But still if people don't want SPI, the pins can be used for something different.

## Fork specific info

### WLED SR

