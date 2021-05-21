---
title: ESP32 Recovery
hide:
  # - navigation
  # - toc
---

In Platformio IDE open a new terminal and type: **pio run -v -t upload**<br>
When you see the "**Connecting........**" abort the upload.

Below you can see Esptool commands, that was used by Platformio. Now you able to find all files that we need to build the binary (screenshot for visualization):
<img src="https://cdn.discordapp.com/attachments/718943978636050542/791636213692891136/unknown.png">

- Download the official **ESP Flash Download Tool**: https://www.espressif.com/en/support/download/other-tools
- Start it and select **Developer Mode > ESP32 Download Tool**.
- Prepare files and memory addresses according picture below:
<img src="https://cdn.discordapp.com/attachments/718943978636050542/791636249999310848/unknown.png" height="750px">

- Click button “**CombineBin**”.<br>
Now you have your binary file with **Bootloader**.