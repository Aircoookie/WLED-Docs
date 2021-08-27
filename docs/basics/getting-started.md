---
title: Getting Started
hide:
  # - navigation
  # - toc
---

# Welcome to the WLED wiki!

!!! info "Version Info"
    Unless noted otherwise, all information applies to the latest release (v0.12.0).

### Quick start guide

**1.** Connect a  WS2812B-compatible RGB(W) led strip to `GPIO2`. On most ESP8266 based development boards this pin is labeled `D4`, on ESP32 based boards use `D2` or `G2` or `2`. _If this wire cannot be kept short, use a [level shifter/translator](/basics/compatible-hardware#levelshifters)._ Optionally connect a normally open pushbutton to `GPIO0` (NodeMCU/Wemos pin `D3`<!-- What pin for ESP32? -->) and ground.  
**Note:** Board pin naming varies depending on the manufacturer. Please use the board pinout from the _specific_ board you purchased and use the GPIO PINS to reference this guide. Make sure to connect ESP and LED-strip grounds together.

![Connection schematics](https://i.ibb.co/WFc797W/connections.jpg)

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
    All pins can be changed in the Hardware section of LED settings. Please note that these are GPIO numbers, please consult a pinout for your board to find the labeled pin (e.g D4 = GPIO2 on most ESP8266 boards)

| Device | GPIO | Notes |
|---|---|---|
LED Data | 2 |
LED Clock | 0 | When used
Button | 0 | Not used when using Clock line
IR Remote| 4 |
Relay | 12 |

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
