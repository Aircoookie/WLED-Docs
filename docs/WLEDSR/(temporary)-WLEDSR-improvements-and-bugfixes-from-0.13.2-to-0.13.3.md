### User Interface and generic features
* Info Page: status info for soundreactive (similar to upstream 0.14.0)
* Info Page: basic hardware info added (similar to MoonModules 0.14.0)
* 4 Line Display and 4LD_alt usermod: always use fast I2C hardware driver


### Audio Processing
* Analog input: Some improvements - might help in case you could not get analog input to work in SR 0.13.2
* New sound processing core (ArduinoFFT) is 10 times faster!
* * improves performance of both analog and I2S digital audio input
* * NB: This also improves co-existence with other usermods and with additional features like MQTT


### UDP sound sync
* improve performance/reliability of UDP sound sync
* Support for receiving "V2" format, which is sent by upstream 0.14.0 


### Effects
* Minor bugfixes, like missed pixels in "Stream" effects, and a few speedups
* Sanity check added in setPixelColor(), to avoid memory errors due to negative pixel index
* * NB: this change also affects realtime modes (DDP, DMX, E13.1, LedFx, ...)


### Custom Effects, 2D/3D, live preview

* Liveviewws2D: show playlist / preset id (for HB playlist animations)
* Custom Effects 3.0.1: add rgbw, sPC for 2D, colorFromPalette out of sPC
* Peek1D for strip repaired. Peek3D for cubes added (experimental)
* Fix setPixelColor when using grid+Serpentine


## misc. bugfixes, and fixes from upstream WLED 0.14.0
* auto-reboot after cfg.json restore (to avoid that WLED directly overwrites them after upload)
* Time Zones: added PKT (Pakistan), fixed NZ and AEST (Australia) time zones
* buttons: fix for ShortPressAction; ensure that buttons remain responsive also with _long_ LED strings
* analog buttons: don't do analogRead() when the GPIO does not support analog input
* udp driver(udp.cpp): small bugfixes
* PlatformIO.ini: upgrade to fixed ESPAsyncWebServer (>= 2.0.7); 
* PlatformIO.ini: use 80MHz FLASH speed for all "Sondreactive" build environments.


## Changes from upstream v0.13.3
* Fixed flickering
* Fixed boot issues on new installs
* Added support for LPD6803
* experimental: optional watchdog feature, to auto-reboot a "hung" device. Compile with `-D WLED_WATCHDOG_TIMEOUT=30` to activate
