---
title: Installing and Compiling
hide:
  # - navigation
  # - toc
---

WIP

## Installing or Compiling
### Installing a bin
#### [Serg](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/experimental/Firmware/AudioReactive)
e.g.
- WLEDMM_0.14.0.10_wemos_shield_esp32_16MB_max.bin
- WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin
- WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_LineIn_max.bin
- WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_SPM1423_max.bin
- WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_max.bin

* To do: add more 16MB entries.

#### Wladi
#### wled.me

### Compiling from MS Code / Platform IO

## PlatformIO Environments
* Hardware: Choose the right environment depending on Shield, ESP32 flash size and mic type. Name of the environment reflects this e.g. wemos_shield_esp32_4MB_ICS4343x_max
* Bin aware: name of the binary contains fork (WLED, WLEDSR, WLEDMM), version and environment e.g WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin. This name is shown in the UI when oploading via OTA
* Build or upload: Build only creates the bin (to be uploaded via OTA or ESPTOOL), upload directly loads it into an USB connected ESP32 board.
* Shield environments: Pins for Shield are already preconfigured
* For developers: See <platformio-entries>

## Fork specific info

### WLED SR
* Also bin aware
* [Bins](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/Sound_reactive). Choose latest version. For Wemos Shield choose WLEDSR_0.13.3.4_wemos_shield_esp32_16MB_max.bin or WLEDSR_0.13.3.4_wemos_shield_esp32_4MB_max.bin (Pins pre-configured)
* To do: add microphones 

### WLED AC
* Not bin aware
* [Bins](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_wemos_shield). Select folder for WLED AC 0.13.3 or 0.14 beta
* For Shields choose wemos_shield_esp32 environment (Pins not pre-configured)
