---
title: Getting Started
hide:
  # - navigation
  # - toc
---

## Welcome to the WLED wiki!

!!! info "Version Info"
    Unless noted otherwise, all information applies to the latest release (v0.12.0).

### Quick start guide

**1.** Connect a  WS2812B-compatible RGB(W) led strip to `GPIO2`. On most ESP8266 based development boards this pin is labeled `D4`, on ESP32 based boards use `IO16` or `G16` or `16`. _If this wire cannot be kept short, use a [level shifter/translator](/basics/compatible-hardware#levelshifters)._ Optionally connect a normally open pushbutton to `GPIO0` (NodeMCU/Wemos pin `D3`, on ESP32 use `IO17`) and ground for [configurable actions](/features/macros).
**Note:** Board pin naming varies depending on the manufacturer. Please use the board pinout from the _specific_ board you purchased and use the GPIO PINS to reference this guide. _Make sure to connect ESP and LED-strip grounds together!_

![Connection schematics](https://i.ibb.co/k9Jgr8S/connections.jpg)

If using an ESP8266 and LEDs that have clock and data, use GPIO1 (TxD) for clock and GPIO2 (D4) for data.

For safe operation it is recommended to dimension your wiring correctly and to integrate fuses.  
To help you out, you may refer to this [LED power, wiring and fuse calculator](https://wled-calculator.github.io/).

For analog use, the IRLZ44N or STP55NF06L is a good MOSFET to use. Partial, example circuit...

![Connection schematics Analog](https://i.ibb.co/86vsym1/image.png)

**2.** Flash the software to your ESP module! There are two options for this step:

[I just want to use WLED! (install release binary)](/basics/install-binary)

[I want to modify WLED (compile from source code)](/basics/compiling-wled)

If everything worked the first thirty LEDs will light up in bright orange to stimulate courage, friendliness and success!

**3.** Use a WiFi device to connect to the access point `WLED-AP` using the default password `wled1234`.
You can also just scan this QR code:

![QR-Code](https://i.ibb.co/h2YswXK/WLED-QR-Connect-WB.png)

Go to the IP `4.3.2.1` in your browser. You should also be able to use the embedded DNS server and connect to `wled.me` if in access point mode.

**4.** Click on the cog icon to edit settings like connecting the module to your home WiFi.

**5.** Check your router device list for the IP of the WLED device inside your local network. For easier discovery, use the WLED app! Have fun with the software!

### Default GPIO Usage

!!! info "These are only defaults"
    All pins can be changed in the Hardware section of LED settings. Please note that these are GPIO numbers, please consult a pinout for your board to find the labeled pin (e.g `D4` = `GPIO2` on most ESP8266 boards). When using an ESP8266 board, it's recommended to use pins `GPIO1`, `GPIO2`, or `GPIO3` for LED Data; using other pins will require _bit-banging_ and may cause slow performance and/or issues elsewhere (such as with IR decoding).

| Function | GPIO | Suggested pin |
|---|---|---|
LED Data | 2 | ESP8266: 1, 2 (3 if <= 100 LEDs), ESP32: 1, 2, 3, 4, 16
Button | 0 | 
IR Remote| None | 4
Relay | None | 12

### Software update procedure

Method 1: Reflash the new update like a new install (see above).

Method 2: The software has an integrated OTA software update capability.
First you have to enable it by typing in the correct OTA passphrase (default: "wledota") in the settings menu.
Remove the tick in the checkbox "OTA locked". Then save settings and reboot the ESP.
Then you can select "Manual OTA update" in Security settings and upload a [release binary](https://github.com/Aircoookie/WLED/releases).
After you are done, it is recommended to lock the OTA function again.
To do so, tick the checkbox again (you can change the passphrase by typing in a new one now). Reboot.
If you try to access the update page now, you should see the message "OTA lock active".

Method 3: ArduinoOTA is also supported.

!!! info "If you own multiple devices and want to update them"
    Since v0.13 of WLED the source code includes shell/command prompt scripts which allow you to update multiple devices with a single command. Please check `tools` subfolder for `multi-update` scripts (.cmd or .sh). You will need to modify them to include IP addresses of your devices and intended firmware binary file for each device. If you are using Windows make sure you install `curl` utility somewhere in your `PATH` (curl is included with Windows 10 since build 17063). This will only work if "OTA Lock" is disabled.
