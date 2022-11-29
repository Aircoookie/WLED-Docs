---
title: Platformio entries
hide:
  # - navigation
  # - toc
---

To reuse settings in a consistent way, MoonModules platformio entries conform to the following standard:

## Overview

Brown: existing platform specifiek entries
Blue: MoonModules common settings: build flags and lib deps (move settings here if possible)
Orange: Base entries: only minimal settings, where possible move to common settings (blue), used by environment settings
Green: Environment entries => use to generate bins using WLED_RELEASE_NAME

Remark: build flags cannot be overwritten in entries using extends. Example is WLED_RELEASE_NAME: only defined in environment entries, not in base (orange) or common settings (blue).

## To do
Remove / evaluate (commented) settings from base entries and move to common settings:
  -D WLED_USE_MY_CONFIG 
  -D WLED_WATCHDOG_TIMEOUT=0 #-D WLED_DISABLE_BROWNOUT_DET
  -D ARDUINO_USB_CDC_ON_BOOT=0 ; needed for arduino-esp32 >=2.0.4; avoids errors on startup
  ; -D WLED_DISABLE_LOXONE
  ; -D WLED_DISABLE_ALEXA
  ; -D WLED_DISABLE_HUESYNC
  ; -D WLED_DISABLE_MQTT
  ; -D WLED_DISABLE_INFRARED
  ; -D WLED_ENABLE_DMX
  ; -D WLED_DEBUG
  ; -D SR_DEBUG
  ; -D MIC_LOGGER

Cleanup / convert old entries

## Fork specific info

### WLED SR
This is also ported to WLEDSR.

### WLED AC
No plans yet
