---
title: Digital Microphone Hookup
hide:
  # - navigation
  # - toc
---

## Welcome to the WLED wiki!

!!! info "Version Info"
    Unless noted otherwise, all information applies to the latest release (vx.y.z.a.b).

### Quick start guide

**1.** bla vla
**Note:** more bla vla

![Connection schematics](https://i.ibb.co/k9Jgr8S/connections.jpg)

bla bla


### Wifi Setup

bla bla

!!! info "These are only defaults"
    All pins can be changed in the Hardware section of LED settings. Please note that these are GPIO numbers, please consult a pinout for your board to find the labeled pin (e.g `D4` = `GPIO2` on most ESP8266 boards). When using an ESP8266 board, it's recommended to use pins `GPIO1`, `GPIO2`, or `GPIO3` for LED Data; using other pins will require _bit-banging_ and may cause slow performance and/or issues elsewhere (such as with IR decoding).

| Function | GPIO | Suggested pin |
|---|---|---|
LED Data | 2 | ESP8266: 1, 2 (3 if <= 100 LEDs), ESP32: 1, 2, 3, 4, 16
Button | 0 | 
IR Remote| None | 4
Relay | None | 12

### Software update procedure

Method 1: Reflashing the new update like a new install (see above).

Method 2: The software has an integrated _OTA software update_ capability.
First you have to enable it by typing in the correct OTA passphrase (default: "wledota") in the settings menu.
Remove the tick in the checkbox "OTA locked". Then save settings and reboot the ESP.
Then you can select "Manual OTA update" in Security settings and upload a [release binary](https://github.com/Aircoookie/WLED/releases).
After you are done, it is recommended to lock the OTA function again.
To do so, tick the checkbox again (you can change the passphrase by typing in a new one now). Reboot.
If you try to access the update page now, you should see the message "OTA lock active".

Method 3: ArduinoOTA is also supported.

!!! info "If you own multiple devices and want to update them"
    Since v0.13 of WLED source code includes shell/command prompt scripts which is allow you to update multiple devices with a single command. Please check `tools` subfolder for `multi-update` scripts (.cmd or .sh). You will need to modify them to include IP addresses of your WLED devices and assign firmware binary file for each device. If you are using Windows, make sure you install `curl` utility somewhere in your `PATH` (curl is included with Windows 10 since build 17063). This will only work if "OTA Lock" is disabled.
