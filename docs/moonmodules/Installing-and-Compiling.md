---
title: Installing and Compiling
hide:
  # - navigation
  # - toc
---

## Introduction
MoonModules introduces a new naming convention for bin(ary) files which contains configs and presets for used hardware. It also shows the used hardware in the bin name including shield esp flash memory size, audio input.

### Naming convention:

* WLEDMM_ (to differentiate between WLEDSR and WLEDAC)
* Version used. First 3 numbers are WLEDAC numbering, last is subnumbering within fork e.g. 0.14.0.10
* Hardware config / presets e.g. wemos_shield_esp32_4MB_ICS4343x
* min or max config, use max where possible. 

### Configurations

Min:

* USERMOD_AUDIOREACTIVE
* USERMOD_CUSTOMEFFECTS

Max:

* Min
* USERMOD_DALLASTEMPERATURE
* USERMOD_FOUR_LINE_DISPLAY
* USERMOD_ROTARY_ENCODER_UI
* USERMOD_AUTO_SAVE
* USERMOD_WEATHER
* USERMOD_MPU6050_IMU
* USERMOD_GAMES

### Examples

* WLEDMM_0.14.0.10_wemos_shield_esp32_16MB_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_LineIn_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_SPM1423_max.bin
* WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_max.bin

### Bin awareness

Binaries can be downloaded or compiled yourself. See below.

When uploading binaries in Manual OTA update , MoonModules support bin awareness: the UI shows which binary is installed and this is a recommendation for the binary to upload (should support the same hardware).

## Installing or Compiling
### Installing a bin
There are currently 4 locations where bins can be downloaded.

They can be installed using Manual OTA update from within the WLED UI or use [Sergs ESP_Flasher](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_%20ESP_Flasher)

#### Serg74
<https://github.com/srg74/WLED-wemos-shield/tree/master/resources/experimental/Firmware/AudioReactive>

Updated frequently with dev versions. Go here for latest features

<img width="200" alt="image" src="https://user-images.githubusercontent.com/1737159/207882069-31f2d8cf-6623-4d91-93df-b7f322f5fbbd.png">

#### Wladi
<https://wled-install.github.io/>

Updated periodically with release and dev versions

#### wled.me
<https://install.wled.me>

Releases only

#### MoonModules release page
<https://github.com/MoonModules/WLED/releases>

Releases only

### Compiling from MS Code / Platform IO

## PlatformIO Environments
* Hardware: Choose the right environment depending on Shield, ESP32 flash size and mic type. Name of the environment reflects this e.g. wemos_shield_esp32_4MB_ICS4343x_max
* Bin aware: name of the binary contains fork (WLED, WLEDSR, WLEDMM), version and environment e.g WLEDMM_0.14.0.10_wemos_shield_esp32_4MB_ICS4343x_max.bin. This name is shown in the UI when oploading via OTA
* Build or upload: Build only creates the bin (to be uploaded via OTA or ESPTOOL), upload directly loads it into an USB connected ESP32 board.
* Shield environments: Pins for Shield are already preconfigured
* For developers: See [platformio-entries](https://moonmodules.github.io/WLED-Docs/moonmodules/platformio-entries/)
* In case of brownouts, file system issues etc: erase flash from the PlatformIO Core CLU (find in platformio quick access on the left pane of Code) pio run --target erase

## Fork specific info

### WLED SR
* Also bin aware
* Bins

Serg74: <https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/Sound_reactive>. Choose latest version. For Wemos Shield choose WLEDSR_0.13.3.4_wemos_shield_esp32_16MB_max.bin or WLEDSR_0.13.3.4_wemos_shield_esp32_4MB_max.bin (Pins pre-configured)

<img width="351" alt="image" src="https://user-images.githubusercontent.com/1737159/207881294-7fce1b1c-ad4f-4078-a71c-18287420a7df.png">

* To do: add microphones 

### WLED AC
* Not bin aware
* Bins

Serg74 <https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_wemos_shield>. Select folder for WLED AC 0.13.3 or 0.14 beta

<img width="338" alt="image" src="https://user-images.githubusercontent.com/1737159/207881529-fb190549-24e7-46ab-8d41-13ddf80d3be7.png">

* For Shields choose wemos_shield_esp32 environment (Pins not pre-configured, not available as bin)
