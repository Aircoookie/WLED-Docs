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

<img width="366" alt="image" src="https://user-images.githubusercontent.com/1737159/207882069-31f2d8cf-6623-4d91-93df-b7f322f5fbbd.png">

e.g.
* WLEDMM_0.14.0.10_wemos_shield_esp32_16MB_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_LineIn_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_SPM1423_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_max.bin

* To do: add more 16MB entries.

#### Wladi
#### wled.me

### Compiling from MS Code / Platform IO

## PlatformIO Environments
* Hardware: Choose the right environment depending on Shield, ESP32 flash size and mic type. Name of the environment reflects this e.g. wemos_shield_esp32_4MB_ICS4343x_max
* Bin aware: name of the binary contains fork (WLED, WLEDSR, WLEDMM), version and environment e.g WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin. This name is shown in the UI when oploading via OTA
* Build or upload: Build only creates the bin (to be uploaded via OTA or ESPTOOL), upload directly loads it into an USB connected ESP32 board.
* Shield environments: Pins for Shield are already preconfigured
* For developers: See [platformio-entries](https://moonmodules.github.io/WLED-Docs/moonmodules/platformio-entries/)

## Fork specific info

### WLED SR
* Also bin aware
* [Bins](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/Sound_reactive). Choose latest version. For Wemos Shield choose WLEDSR_0.13.3.4_wemos_shield_esp32_16MB_max.bin or WLEDSR_0.13.3.4_wemos_shield_esp32_4MB_max.bin (Pins pre-configured)
<img width="351" alt="image" src="https://user-images.githubusercontent.com/1737159/207881294-7fce1b1c-ad4f-4078-a71c-18287420a7df.png">
* To do: add microphones 

### WLED AC
* Not bin aware
* [Bins](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_wemos_shield). Select folder for WLED AC 0.13.3 or 0.14 beta
<img width="338" alt="image" src="https://user-images.githubusercontent.com/1737159/207881529-fb190549-24e7-46ab-8d41-13ddf80d3be7.png">
* For Shields choose wemos_shield_esp32 environment (Pins not pre-configured, not available as bin)
