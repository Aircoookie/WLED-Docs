---
title: Fork Comparison
hide:
  # - navigation
  # - toc
---

What are the differences between WLED SR, upstream AC WLED, and MoonModules fork?

| Feature | [WLED SR 0.13](https://github.com/atuline/WLED/tree/dev) | [MoonModules WLED 0.14](https://github.com/MoonModules/WLED/tree/mdev) | [Upstream WLED 0.14](https://github.com/Aircoookie/WLED) |
|---|---|---|---|
0.14 architecture | No | Yes (upstream frequently merged) | Yes
Usermods have own pages in main config menu | Audio Reactive only | Yes | No
Segments 2D aware | No (XY calculated, mirror not working) | Yes | Yes
Audio reactive | Core | Usermod | Usermod
Microphone Profiles | No | Yes | No | 
Audio dynamics limiter | No | Yes | Yes
High Definition audio analysis, 32 channel GEQ | No |  Yes (WIP) for ESP32 and ESP32-S3 | No
Custom Effects | Yes | Yes | No
Expand 1D effects | No | Yes (+ JMap, Circle and Block) | Yes
Extended hw info | basic | Yes | No
JSON Mapping on 1D effects | No | Yes | No
Games usermod (3D to 2D, gyro) | No | Yes (WIP) | No
Weather usermod (syncing internet data) | No | Yes (WIP) | No
HB effects | Fully supported | 80% supported (WIP) | Not supported
classic ESP32 | Yes | Yes | Yes
ESP32-S3 | No | Yes | Experimental
ESP32-S2 and ESP32-C3 | No | Experimental | Experimental
ESP8266 | No | Yes but no Audio Reactive | Yes but no Audio Reactive
Bin Awareness | Yes | Yes | No
Audioreactive palettes | No | Yes | No
Extended mic settings in platformIO | No | Yes | No
