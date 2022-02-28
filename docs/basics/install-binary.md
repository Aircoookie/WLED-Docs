---
title: Install WLED Binary
hide:
  # - navigation
  # - toc
---

### Flashing method 1: WLED web installer

!!! tip
    This is by far the easiest and fastest way to get WLED up and running!

Make sure you are running a recent desktop Chrome or Edge browser and head over to the [installer site](https://install.wled.me)!
If you are updating an existing version of WLED, make sure to uncheck "Clean install" so that your settings are kept.
This installer is not yet available for ESPs with flash chips smaller than 4MB (e.g. ESP01)

### Flashing method 2: esptool

- First of all, please follow the steps to install esptool.py [here](https://github.com/espressif/esptool).
- Download the latest [release binary](https://github.com/Aircoookie/WLED/releases) file!
- Make sure only one ESP device/microcontroller is connected to your computer! Otherwise you could accidentally overwrite the wrong one. If you know the serial port, you can also add the `-port COM3` attribute after `write_flash`
- Execute this command:

#### ESP8266

```bash
esptool.py write_flash 0x0 ./WLED_XXX.bin
```

#### ESP32

(you will need to have a bootloader installed)

```bash
esptool.py write_flash 0x10000 ./WLED_XXX.bin 
```

If the ESP32 is new, you will need to flash the bootloader first. This bootloader should be addressed to 0x00000 and the firmware to 0x10000. This is not required if you had an Arduino sketch running on it before. You can find the bootloader file in the assets for the [0.9.1 release](https://github.com/Aircoookie/WLED/releases/tag/v0.9.1).

```bash
esptool.py write_flash 0x0 ./esp32_bootloader.bin
```

When esptool.py says `Connecting...`, some ESP32 boards require you to hold the boot button (to the right of the USB port) for a few seconds  

- If you experience issues, run this command before trying `write_flash` again (Note: this will erase all settings stored on the ESP!)

```bash
esptool.py erase_flash
```

### Flashing method 3: [ESP Home Flasher](https://github.com/esphome/esphome-flasher/releases) tool

!!! warning
    On ESP32, this will make the filesystem very small (61kB), which leads to issues making presets. Please consider using the web installer or esptool.

This is a GUI-based tool recommended by some users as easier to use than esptool.
For some ESP32 boards, you might have to press some buttons after uploading:
> Hold both buttons down, plug it in, start flashing, then when is tries to detect, let go of the button to the left of the USB as you look at it, then when it detects the board type, let go of the other button.

If running windows, you need a driver from here: <https://www.wemos.cc/en/latest/ch340_driver.html> before your computer will show the COM port in ESPhome Flasher. With a Wemos D1 mini you do not need to hold down the reset button while flashing.

### Flashing method 4: OTA update

 You can alternatively use my [basic HTTP OTA updater](https://github.com/Aircoookie/ESP8266MinimalHTTPUpdater) sketch and upload the binary! This requires the Arduino IDE and ESP8266 core installed.
If your device is already running a firmware with built-in OTA capability, you can probably use that as well.

### What binary should I use?

I always recommend to use the latest release. Starting from WLED 0.12.0, pins can be configured in LED settings and specific binaries for different LED pins or types are no longer needed. Please use the following binary for these boards respectively:

| Binary Name | For devices |
| --- | --- |
| WLED_0.x.x_ESP8266.bin | NodeMCU, Wemos D1 mini, ESP-12, all ESP8266 with 4MB flash. Recommended.
| WLED_0.x.x_ESP32.bin | All ESP32 devices (try [this](https://github.com/Aircoookie/WLED/issues/517#issuecomment-571333712) if the WLED-AP doesn't appear after flashing) |
| WLED_0.x.x_ESP32_Ethernet.bin | ESP32 devices with an Ethernet interface. Also works with WiFi only. |
| WLED_0.x.x_ESP01.bin | ESP-01 (black PCB), most Sonoff devices, ESP8265, all ESP8266 with 1MB flash. This binary has the full feature set, but wireless updates will not work. |
| WLED_0.x.x_ESP02.bin | All ESP8266 with 2MB flash, Athom bulbs |
| esp32_bootloader.bin | Not a WLED release. To be flashed to a brand new ESP32 before flashing the WLED binary itself. |

Legacy binary format (up to 0.11.1)

| Binary Name | For devices |
| --- | --- |
| WLED_0.x.x_ESP8266_1M_ota.bin | ESP-01 (black PCB), most Sonoff devices, ESP8265, all ESP8266 with 1MB flash. This binary has some interfaces disabled (Alexa, Blynk, Hue sync, Infrared) in order for wireless updates to continue working. |
| WLED_0.x.x_ESP8266_1M_full.bin | ESP-01 (black PCB), most Sonoff devices, ESP8265, all ESP8266 with 1MB flash. This binary has the full feature set, but wireless updates will not work. |
| WLED_0.x.x_ESP8266_512k.bin | ESP-01 (blue PCB), older Sonoff devices, all ESP8266 with 512kB flash. Interfaces (Alexa, Blynk, Hue sync, Infrared) disabled, no OTA. Support will not be possible in future versions. |
| WLED_0.x.x_ESP8266_ledpinY.bin | Custom build for 4MB flash ESP8266 and WS2812B. LED pin is changed (default is GPIO2). (This is GPIOY and not DY for the D to GPIO mapping, check your boards spec!) |
| WLED_0.x.x_ESP8266_apa102.bin | Custom build for 4MB flash ESP8266 and APA102 LEDs (clock pin GPIO0, data GPIO2).
| WLED_0.x.x_ESP8266_ws2801.bin | Custom build for 4MB flash ESP8266 and WS2801 LEDs (clock pin GPIO0, data GPIO2).
| WLED_0.x.x_ESP32_ledpinY.bin | Custom build for ESP32 and WS2812b. LED pin is changed (default is GPIO2). LED pin 16 is useful for the QuinLed-Dig-Uno board with ESP32. |
