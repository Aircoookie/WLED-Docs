---
title: Usermod global pins
hide:
  # - navigation
  # - toc
---

This page is work in progress

🌜

## I2C and SPI

<img width="350" alt="image" src="https://user-images.githubusercontent.com/91013628/212864986-6d76bce7-0032-4624-b9a3-bb30af2e81d7.png">

WLED MM has implemented a more intuitive way of dealing with i2c and spi pins accross usermods. Main changes:

* Do not reset ui variables if something is wrong (e.g. 4ld/type, enabled)
* Use errorMessage instead and show errormessage in settings ui
* If global pins are -1/undefined, then there is no initialization of spi/i2c in usermods using global pins
* HW_PIN_* variables are used in platformio to specify defaults for global pins, HW_PIN variables not used in usermods, there only global pin variabes are used
* HW_PIN_DATASPI and HW_PIN_MOSISPI both existed but is one pin, merged to HW_PIN_MOSISPI as MOSI and MISO is both data
* i2c_scl (etc) variables are used in usermods without if -1 then HW_PIN check, i2c_scl (etc) most be proper initialized before it can be used.
* No hijacking of global vars (giving them a value) in usermods
* Don't register pins if usermod is not enabled

## Pin dropdowns
ESP32 <img width="130" alt="classic ESP32 GPIO" src="https://user-images.githubusercontent.com/91013628/212557801-0329826a-9d00-4c85-abd9-049c73c5a773.png"> &nbsp;ESP32-S3 <img width="100" alt="ESP32-S3 GPIO" src="https://user-images.githubusercontent.com/91013628/212862709-95f150fd-42b8-4191-bbf4-d525ab8978a2.png"> &nbsp;ESP32-S2 <img width="100" alt="ESP32-S2 GPIO" src="https://user-images.githubusercontent.com/91013628/212862773-1e330fb8-2f7d-47a7-989c-3791c2fec416.png"> 
<br> <br> 
ESP32-C3 <img width="100" alt="ESP32-C3 GPIO" src="https://user-images.githubusercontent.com/91616163/213477428-ce9825a8-843e-4423-983b-42e7131f8c0f.png"> 
&nbsp;ESP8266 <img width="130" alt="ESP8266 GPIO" src="https://user-images.githubusercontent.com/91616163/213484502-e3d84f63-a25b-40fa-a2db-7fc83d53911d.png">


Nr of pins and functionality is depending on the board chosen (esp8266, esp32, esp32-c2, esp32-c3, esps32-s3)

* First option is undefined or use global (global pin)
* 🔴 pin used by other usermod / global pins, cannot be selected
* 🟠 read only pin: will be disabled for signals which write
* 🟣 reserved pin: cannot be selected
* ⍼ pin defined by board (e.g. default I2C on esp32 is 21/22)
* ⎌ pin defined by bin / platformio entry

## Pin allocation
* 8266: default I2C pins for most esp8266 variants are SDA=4 and SCL=5 (and one i2c instance only). So you can have 0 or 1 I2C bus.
* esp32: has two "I2C hardware units" that can attach to any pin.  So you could have 0 or 1, or 2 I2C buses.
* currently WLED only uses "i2c unit 0" on esp32. So in reality you can have 0 or 1 I2C bus.
* WLED does not support "software I2C" on esp32 - that's a common misunderstanding because people see they can freely chose pins on esp32.
* once the I2C bus pins are set, all usermods have to use these pins for I2C. Changing I2C pins requires a reboot.
* four-line-display is an exception, because the driver library has its own "software I2C" - slow, but can always be used with any availeable pin.

* on both esp32 and 8266, you can decide to not use I2C, and use pins for something else. For example (on 8266), attach some buttons or rotary encoder to gpio 4+5. 
* similar for SPI - if you want SPI, the pins are fixed on 8266. If you don't need SPI, the pins can be used for something else.
* on esp32 its a bit more complicated even, because the fastest SPI modes are only possible on certains pins. But still if people don't want SPI, the pins can be used for something different.

## Serial pin overview
After booting WLED MM an overview of allocated pins and possible conflicts is send to Serial output:

<img width="454" alt="image" src="https://user-images.githubusercontent.com/91013628/212862122-06dca5b1-0c37-4e5b-a43d-4a0b372d1698.png">


## Fork specific info

### WLED SR
Pin drop downs not supported

### WLED AC
Pin drop downs not supported

