---
title: Remote Access / IFTTT
hide:
  # - navigation
  # - toc
---

WLED is open-source, DIY software. This means all services are hosted locally on your ESP8266/32.
Therefore you can only control your lights from within your local (home) network.

If you need to control WLED from anywhere (the public internet) you can do so in multiple ways, some requiring additional hardware:

### 1. Home Automation systems

If you add your WLED device to your Home Automation system (e.g. Home Assistant or ioBroker), you can control WLED remotely if you have set up remote access for your Home Automation system, for example via Nabu Casa.

### 2. Amazon Echo device
If you have set up your Alexa device to control WLED, you can just use the Alexa App or another Echo device linked to your account to control your lights (on/off and brightness only)

### 3. Port Forwarding
**Warning: An insecure HTTP connection is used, please do NOT edit sensitive info like the WiFi settings when connected via port forwarding!**   
This method offers more flexibility, but is also more involved.   
**Keep in mind this causes anyone with your IP address to have access to your ESP8266!**   
Setting up an [OTA lock password](/advanced/security) is a must to prevent attackers from acquiring your WiFi credentials!

To expose WLED to the internet, create a port forwarding rule for your ESP's IP local ip and port (80) in your router configuration. It is not recommended to use port 80 on your public IP address since 80 is scanned constantly by bots good and bad. Use a 5 digit port for better securuty.
If your public IP changes a lot, make sure to also use a dynamic DNS service so your lights are always accessible.
_Unsure what any of this means or how to do it? Google for "[your router model] port forwarding"!_

Additionally, this opens up many new possibilities for automation! You can use a service like [IFTTT](https://ifttt.com/) Webhooks to send automated WLED API calls that can do anything from turning on the lights at a set time to changing their color if you get a new email!

### 4. Hue sync

If you have a Philips hue setup and sync WLED to it, you can control your WLED lights in any way it's possible to control your hue lights (hue App, Alexa (including colors), any other service that uses Philips hue API)
