---
title: JSON API
hide:
  # - navigation
  # - toc
---
!!! info "Version Info"
    Starting from version 0.8.4, WLED implements a powerful JSON API over HTTP.	
    It is accessible using the `/json` subpage.	

### Obtaining light information	
Sending a GET request will return an object similar to the sample below.	
The response consists of four objects:	
- `state` contains the current state of the light. All values may be modified by the client (see below)	
- `info` contains general information about the device. No value can be modified using this API.	
- `effects` contains an array of the effect mode names	
- `palettes` contains an array of the palette names	

You may also obtain those objects individually using the URLs `/json/state` `/json/info` `/json/eff`, and `/json/pal`	

### Setting new values	
Sending a POST request to `/json` or `/json/state` with (parts of) the state object will update the respective values.	
Example: `{"on":true,"bri":255}` sets the brightness to maximum. `{"seg":[{"col":[[0,255,200]]}]}` sets the color of the first segment to teal.	

Sample JSON API response (v0.8.4):	

```json	
{	
  "state": {	
    "on": true,	
    "bri": 127,	
    "transition": 7,	
    "ps": -1,	
    "pl": -1,	
    "nl": {	
      "on": false,	
      "dur": 60,	
      "fade": true,	
      "tbri": 0	
    },	
    "udpn": {	
      "send": false,	
      "recv": true	
    },	
    "seg": [{	
      "start": 0,	
      "stop": 20,	
      "len": 20,	
      "col": [	
        [255, 160, 0, 0],	
        [0, 0, 0, 0],	
        [0, 0, 0, 0]	
      ],	
      "fx": 0,	
      "sx": 127,	
      "ix": 127,	
      "pal": 0,	
      "sel": true,	
      "rev": false,	
      "cln": -1	
    }]	
  },	
  "info": {	
    "ver": "0.8.4",	
    "vid": 1903252,	
    "leds": {	
      "count": 20,	
      "rgbw": true,	
      "pin": [2],	
      "pwr": 0,	
      "maxpwr": 65000,	
      "maxseg": 1	
    },	
    "name": "WLED Light",	
    "udpport": 21324,	
    "live": false,	
    "fxcount": 80,	
    "palcount": 47,	
    "arch": "esp8266",	
    "core": "2_4_2",	
    "freeheap": 13264,	
    "uptime": 17985,	
    "opt": 127,	
    "brand": "WLED",	
    "product": "DIY light",	
    "btype": "src",	
    "mac": "60019423b441"	
  },	
  "effects": [	
    "Solid", "Blink", "Breathe", "Wipe", "Wipe Random", "Random Colors", "Sweep", "Dynamic", "Colorloop", "Rainbow",	
    "Scan", "Dual Scan", "Fade", "Chase", "Chase Rainbow", "Running", "Saw", "Twinkle", "Dissolve", "Dissolve Rnd",	
    "Sparkle", "Dark Sparkle", "Sparkle+", "Strobe", "Strobe Rainbow", "Mega Strobe", "Blink Rainbow", "Android", "Chase", "Chase Random",	
    "Chase Rainbow", "Chase Flash", "Chase Flash Rnd", "Rainbow Runner", "Colorful", "Traffic Light", "Sweep Random", "Running 2", "Red & Blue", "Stream",	
    "Scanner", "Lighthouse", "Fireworks", "Rain", "Merry Christmas", "Fire Flicker", "Gradient", "Loading", "In Out", "In In",	
    "Out Out", "Out In", "Circus", "Halloween", "Tri Chase", "Tri Wipe", "Tri Fade", "Lightning", "ICU", "Multi Comet",	
    "Dual Scanner", "Stream 2", "Oscillate", "Pride 2015", "Juggle", "Palette", "Fire 2012", "Colorwaves", "BPM", "Fill Noise", "Noise 1",	
    "Noise 2", "Noise 3", "Noise 4", "Colortwinkle", "Lake", "Meteor", "Smooth Meteor", "Railway", "Ripple"	
  ],	
  "palettes": [	
    "Default", "Random Cycle", "Primary Color", "Based on Primary", "Set Colors", "Based on Set", "Party", "Cloud", "Lava", "Ocean",	
    "Forest", "Rainbow", "Rainbow Bands", "Sunset", "Rivendell", "Breeze", "Red & Blue", "Yellowout", "Analogous", "Splash",	
    "Pastel", "Sunset 2", "Beech", "Vintage", "Departure", "Landscape", "Beach", "Sherbet", "Hult", "Hult 64",	
    "Drywet", "Jul", "Grintage", "Rewhi", "Tertiary", "Fire", "Icefire", "Cyane", "Light Pink", "Autumn",	
    "Magenta", "Magred", "Yelmag", "Yelblu", "Orange & Teal", "Tiamat", "April Night"	
  ]	
}	
```	

### Overview of values	

#### State object	

| JSON key | Value range | Description	
| --- | --- | --- |	
on | bool | On/Off state of the light	
bri | 0 to 255 | Brightness of the light. If _on_ is `false`, contains last brightness when light was on (aka brightness when _on_ is set to true). Setting _bri_ to 0 is supported but it is recommended to use the range 1-255 and use `on: false` to turn off. The state response will never have the value `0` for _bri_.	
transition | 0 to 255 | Duration of the crossfade between different colors/brightness levels. One unit is 100ms, so a value of `4` results in a transition of 400ms.	
tt | 0 to 255 | Similar to transition, but applies to just the current API call. Not included in state response.	
ps | -1 to 65535 | ID of currently set preset.	
pss | 0 to 65535 | Bitwise indication of preset slots (0 - vacant, 1 - written). Always 0 in 0.11. Not changable. _Deprecated, removal in 0.12.0_	
psave | 1 to 16 (250 in 0.11) | Save current light config to specified preset slot. Not included in state response.	
pl | -1 to 0 | ID of currently set playlist. For now, this sets the preset cycle feature, `-1` is off and `0` is on.	
nl.on | bool | Nightlight currently active	
nl.dur | 1 to 255 | Duration of nightlight in minutes	
nl.fade | bool | If `true`, the light will gradually dim over the course of the nightlight duration. If `false`, it will instantly turn to the target brightness once the duration has elapsed. _Deprecated, removal in 0.12.0_ (use mode instead)	
nl.mode | 0 to 3 | Nightlight mode (0: instant, 1: fade, 2: color fade, 3: sunrise) (available since 0.10.2)	
nl.tbri | 0 to 255 | Target brightness of nightlight feature	
udpn.send | bool | Send WLED broadcast (UDP sync) packet on state change	
udpn.recv | bool | Receive broadcast packets	
udpn.nn | bool | Don't send a broadcast packet (applies to just the current API call). Not included in state response.	
v | bool | If set to _true_ in a JSON POST command, the response will contain the full JSON state object. Not included in state response.
rb | bool | If set to _true_, device will reboot immediately. Not included in state response.	
lor | 0, 1, or 2 | Live data override. 0 is off, 1 is override until live data ends, 2 is override until ESP reboot (available since 0.10.0)	
time | uint32 | Set module time to unix timestamp. Not included in state response.	
mainseg | 0 to info.leds.maxseg-1 | Main Segment | Sets which segment ID is the main segment	
seg | Array of segment objects | Segments are individual parts of the LED strip. In 0.9.0 this will enables running different effects on different parts of the strip.	
playlist | object | [Custom preset playlists](#playlists). Not included in state response (available since 0.11.0)	

#### Contents of the segment object	

**Notice:** _start_, _stop_, and _len_ are not changeable in  0.8.4. Any segment with _id_ > 0 is ignored.	
Unless stated otherwise, every value may be changed via an HTTP POST request.	
The tertiary color is not gamma-corrected in 0.8.4, but is in subsequent releases.	

| JSON key | Value range | Description	
| --- | --- | --- |	
id | 0 to info.maxseg -1 | Zero-indexed ID of the segment. May be omitted, in that case the ID will be inferred from the order of the segment objects in the _seg_ array. As such, not included in state response.	
start | 0 to info.leds.count -1 | LED the segment starts at.	
stop | 0 to info.leds.count | LED the segment stops at, not included in range. If _stop_ is set to a lower or equal value than _start_ (setting to `0` is recommended), the segment is invalidated and deleted.	
len | 0 to info.leds.count | Length of the segment (_stop_ - _start_). _stop_ has preference, so if it is included, _len_ is ignored.	
grp | 0 to 255 | Grouping (how many consecutive LEDs of the same segment will be grouped to the same color)  
spc | 0 to 255 | Spacing (how many LEDs are turned off and skipped between each group)  
of | -len+1 to len | Offset (how many LEDs to rotate the virtual start of the segments, available since 0.13.0)  
col | array of colors | Array that has up to 3 color arrays as elements, the primary, secondary (background) and tertiary colors of the segment. Each color is an array of 3 or 4 bytes, which represent an RGB(W) color.	
fx | 0 to info.fxcount -1 | ID of the effect.	
sx | 0 to 255 | Relative effect speed	
ix | 0 to 255 | Effect intensity	
pal | 0 to info.palcount -1 | ID of the color palette	
sel | bool | `true` if the segment is selected. Selected segments will have their state (color/FX) updated by APIs that don't support segments (currently any API except this JSON API). If no segment is selected, the first segment (_id_:`0`) will behave as if selected. WLED will report the state of the first (lowest _id_) segment that is selected to APIs (UDP sync, HTTP, MQTT, Blynk...).	
rev | bool | Flips the segment, causing animations to change direction.	
on | bool | Turns on and off the individual segment. (available since 0.10.0)	
bri | 0 to 255 | Sets the individual segment brightness (available since 0.10.0)	
mi | bool | Mirrors the segment (available since 0.10.2)	
grp | 0 to 255 | Grouping (how many consecutive LEDs of the same segment will be grouped to the same color)  
spc | 0 to 255 | Spacing (how many LEDs are turned off and skipped between each group)  
of | -len+1 to len | Offset (how many LEDs to rotate the virtual start of the segments, available since 0.13.0)  
lx | `BBBGGGRRR`: 0 - 100100100 | Loxone RGB value for primary color. Each color (`RRR`,`GGG`,`BBB`) is specified in the range from 0 to 100%.	
lx | `20bbbtttt`: 200002700 - 201006500 | Loxone brightness and color temperature values for primary color. Brightness `bbb` is specified in the range 0 to 100%. `tttt` defines the color temperature in the range from 2700 to 6500 Kelvin. (available since 0.11.0, not included in state response)	
ly | `BBBGGGRRR`: 0 - 100100100 | Loxone RGB value for secondary color. Each color (`RRR`,`GGG`,`BBB`) is specified in the range from 0 to 100%.	
ly | `20bbbtttt`: 200002700 - 201006500 | Loxone brightness and color temperature values for secondary color. Brightness `bbb` is specified in the range 0 to 100%. `tttt` defines the color temperature in the range from 2700 to 6500 Kelvin. (available since 0.11.0, not included in state response)	
i | array | [Individual LED control](https://github.com/Aircoookie/WLED/wiki/JSON-API#per-segment-individual-led-control). Not included in state response (available since 0.10.2)	

#### Info object	

No value may be changed by means of this API.	

| JSON key | Value range | Description	
| --- | --- | --- |	
ver | string | Version name.	
vid | uint32 | Build ID (YYMMDDB, B = daily build index).	
_leds_ | object | Contains info about the LED setup.	
leds.count | 1 to 1200 | Total LED count.	
leds.fps | 0 to 255 | Current frames per second. (available since 0.12.0)
leds.rgbw | bool | `true` if LEDs are 4-channel (RGBW).	
leds.wv | bool | `true` if a white channel slider should be displayed. (available since at least 0.11.1)
leds.pin | byte array | LED strip pin(s). In 0.8.4, always one element.	
leds.pwr | 0 to 65000 | Current LED power usage in milliamps as determined by the ABL. `0` if ABL is disabled.	
leds.maxpwr | 0 to 65000 | Maximum power budget in milliamps for the ABL. `0` if ABL is disabled.	
leds.maxseg | byte | Maximum number of segments supported by this version.	
str | bool | If `true`, an UI with only a single button for toggling sync should toggle receive+send, otherwise send only	
name | string | Friendly name of the light. Intended for display in lists and titles.	
udpport | uint16 | The UDP port for realtime packets and WLED broadcast.	
live | bool | If `true`, the software is currently receiving realtime data via UDP or E1.31.	
lm | string | Info about the realtime data source	
lip | string | Realtime data source IP address	
ws | -1 to 8 | Number of currently connected WebSockets clients. -1 indicates that WS is unsupported in this build.	
fxcount | byte | Number of effects included.	
palcount | uint16 | Number of palettes configured.	
_wifi_ | object | Info about current signal strength	
wifi.bssid | string | The BSSID of the currently connected network.	
wifi.signal | 0 to 100 | Relative signal quality of the current connection.	
wifi.channel | 1 to 14 | The current WiFi channel.	
_fs_ | object | Info about the embedded LittleFS filesystem (since 0.11.0)	
fs.u | uint32 | Estimate of used filesystem space in kilobytes	
fs.t | uint32 | Total filesystem size in kilobytes	
fs.pmt | uint32 | Unix timestamp for the last modification to the `presets.json` file. Not accurate after boot or after using `/edit`  
ndc | -1 to 255 | Number of other WLED devices discovered on the network. -1 if Node discovery disabled. (since 0.12.0)  
arch | string | Name of the platform.	
core | string | Version of the underlying (Arduino core) SDK.	
freeheap | uint32 | Bytes of heap memory (RAM) currently available. Problematic if <`10k`.	
uptime | uint32 | Time since the last boot/reset in seconds.	
opt | uint16 | Used for debugging purposes only.	
brand | string | The producer/vendor of the light. Always `WLED` for standard installations.	
product | string | The product name. Always `FOSS` for standard installations.	
btype | string | The origin of the build. `src` if a release version is compiled from source, `bin` for an official release image, `dev` for a development build (regardless of src/bin origin) and `exp` for experimental versions. `ogn` if the image is flashed to hardware by the vendor. _Removed as of v0.10_	
mac | string | The hexadecimal hardware MAC address of the light, lowercase and without colons.	
ip | string | The IP address of this instance. Empty string if not connected. (since 0.13.0) 

#### Per-segment individual LED control	

Using the `i` property of the segment object, you can set the LED colors in the segment using the JSON API.	
Keep in mind that this is non-persistent, if the light is turned off the segment will return to effect mode.	
The segment is blanked out when using individual control, the set effect will not run.	
To disable, change any property of the segment or turn off the light.	

To set individual LEDs starting from the beginning, use an array of Color arrays.  	
`{"seg":{"i":[[255,0,0], [0,255,0], [0,0,255]]}}` will set the first LED red, the second green and the third blue.	

To set individual LEDs, use the LED index followed by its Color array.  	
`{"seg":{"i":[0,[255,0,0], 2,[0,255,0], 4,[0,0,255]]}}` is the same as above, but leaves blank spaces between the lit LEDs.	

To set ranges of LEDs, use the LED start and stop index followed by its Color array.  	
`{"seg":{"i":[0,8,[255,0,0], 10,18,[0,0,255]]}}` sets the first eight LEDs to red, leaves out two, and sets another 8 to blue.	

Keep in mind that the LED indices are segment-based, so LED 0 is the first LED of the segment, not of the entire strip.	
Segment features, including Grouping, Spacing, Mirroring and Reverse are functional.	
This feature is available in build 200829 and above.	

#### Playlists	
(beta, available since 0.11.0)	

Sample playlist API call:	
```json	
{	
  "playlist": {	
    "ps": [26, 20, 18, 20],	
    "dur": [30, 20, 10, 50],	
    "transition": 0,	
    "repeat": 10,	
    "end": 21	
  }	
}	
```	
This example applies preset ID 26 for 3 seconds, then preset 20 for 2 seconds, then preset 18 for 1 second, lastly preset 20 again for 5 seconds. This repeats 10 times, then preset 21 is applied.	

Playlist object:	

| JSON key | Description	
| --- | --- |	
ps | Array of preset ID integers to be applied in this order.  	
dur | Array of time each preset should be kept, in tenths of seconds. If only one integer is supplied, all presets will be kept for that time. Defaults to 10 seconds if not provided.	
transition | Array of time each preset should transition to the next one, in tenths of seconds. If only one integer is supplied, all presets will transition for that time. Defaults to the current transition time if not provided.	
repeat | How many times the entire playlist should cycle before finishing. Set to `0` for an indefinite cycle. Default to indefinite if not provided.	
end | Single preset ID to apply after the playlist finished. Has no effect when an indefinite cycle is set. If not provided, the light will stay on the last preset of the playlist.
