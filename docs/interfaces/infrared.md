---
title: Infrared
hide:
  # - navigation
  # - toc
---


!!! info "Version Info"
    Since v0.8.2, infrared control from various IR remotes is supported for ESP8266 and since v0.9.0 for ESP32, too.

A dedicated infrared receiver module is required.
(KY-022 or TSOP38238 are confirmed to work and inexpensive)

The default sensor pin is GPIO4. It can be changed in LED settings.

!!! warning
    IR receiving will not work on ESP8266 if you use any LED pin other than GPIO 1, 2, or 3 for _digital_ LED strips.

### Supported IR remotes

To use IR remote go to `Settings`, `Sync Interfaces` and change the value for `Infrared receiver type` according to the IR remote type of the following list:

1. white 24-key IR remote with R,G,B + 12 color-tones  
2. white 24-key IR remote with CT+ / CT- buttons  
3. blue 40-key IR remote with keys for 25%, 50%, 75% and 100%  
4. white 44-key IR remote with up/down arrows for the colors R,G and B  
5. white 21-key IR remote with R,G,B + 9 color-tones  
6. black 6-key IR remote with CH up/down + Vol up/down  
7. [JSON IR remote](json-ir/json_infrared.md) - Easily configure and use any IR remote.  
