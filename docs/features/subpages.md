---
title: Web GUI Sitemap
hide:
  # - navigation
  # - toc
---

This is the sitemap of the module server.
Access with \<ESP-IP\>/path (Example: **192.168.8.4/settings**)

| Path | Description | OTA rights required | Since version |
| --- | --- | --- | --- |
/ | Default UI, index page | No | 0.2
/update | Upload new firmware | Yes | 0.3
/win | HTTP Request API (since 0.3) | No | 0.3
/json | JSON API | No | 0.8.4
/json/state | JSON state object | No | 0.8.4
/json/info | JSON information | No | 0.8.4
/json/eff | Effect name list | No | 0.8.4
/json/pal | Palette name list | No | 0.8.4
/json/live | Current colors of LEDs | No | 0.9.0
/liveview | Live preview of current LEDs | No | 0.9.0
/settings | Settings index page | No | 0.2
/settings/wifi | WiFi Settings page | Cnfg | 0.5.0
/settings/led | LED Settings page | No | 0.5.0
/settings/ui | UI Settings page | No | 0.5.0
/settings/sync | Sync Settings page | No | 0.5.0
/settings/time | Time Settings page | No | 0.5.0
/settings/sec | Security Settings page | Yes | 0.5.0
/welcome | New User Welcome page | No | 0.5.0
/sliders | UI, index page | No | 0.5.0
/reset | Reboot module | No | 0.3
/version | Returns build version | No | 0.3
/uptime | Returns runtime in ms | No | 0.4
/freeheap | Returns free memory | No | 0.4
/favicon.ico | Page icon | No | 0.2
/teapot | :) | No | 0.5.0
/edit | Filesystem editor | Yes | 0.2
/u | Custom usermod page | 0.8.4 (?)
/cpal.htm | Custom palette editor | 0.14.0-b3
/pixart.htm | 2D Pixel Art converter (not compiled by default) | 0.14.0-b3
/pxmagic.htm | 2D Image converter | 0.14.0-b4

#### Removed sites

| Path | Description | OTA rights required | Versions |
| --- | --- | --- | --- |
/list | Lists SPIFFS contents (if USEFS) | Yes | 0.2-0.8.3
/easter | Joke page | No | 0.6.2 only
/power | Returns an estimate of used LED current | No | 0.5.0-0.8.3
/build | Returns details about the build | No | 0.5.0-0.8.3
/cleareeprom | Resets to factory defaults | Yes | 0.3-0.6.4
/down | Kills software. Hard reset required. | Yes | 0.3-0.6.4
/url | Returns current light setup API url | No | 0.9.1-0.14.0-b3
