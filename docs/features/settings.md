---
title: Settings
hide:
  # - navigation
  # - toc
---

All web configurable settings are split in 5 sub-pages.
This page is meant to clarify the purpose of each setting.
This documentation applies to WLED 0.8.5.

## Settings overview

### WiFi Settings

This sub-page offers options to connect the ESP to different WiFi/WLAN devices.

| Setting name | Value Range | Description |
|---|---|---|
Network Name | String 0..32 | The name (SSID) of your home WiFi. Spaces and some other characters are not supported.
Network password | String 0..64 | The password of your home WiFi
Static IP | 4x 0..256 | An optional static IPv4 address
Static gateway | 4x 0..255 | In a static config, your gateway's IPv4 address
Static subnet | 4x 0..255 | In a static config, this normally is 255.255.255.0
mDNS address | String 0..32 | Name of your device for the Bonjour/Zeroconf protocol
Client IP | - | The current IP of the ESP in the home network
AP SSID | String 0..32 | The name of the ESPs internal WiFi hotspot (Access Point)
Hide AP name | Y/N | The ESPs Access Point won't appear in WiFi lists of other devices
AP password | String 0..64 | The password of the ESPs WiFi Access Point
AP WiFi channel | 1..13 | The 2.4G WiFi band of the AP. For advanced users
AP opens | select | Condition on when to open the AP
AP IP | - | The Access Point IPv4 address of the ESP (is 192.168.4.1 in most cases)
WiFi sleep | Y/N | Disabling WiFi sleep can increase reliability, but increases power consumption

### LED settings

This sub-page configures the state of your lights.

| Setting name | Value Range | Description |
|---|---|---|
LED count | 1..1500 | How many LEDs are in your WS2812B strip
Automatic brightness limiter | Y/N | Limit brightness to stay in a given current range
Maximum current | 300..65000 | Current limit im milliamps
LED voltage | select | Voltage/type of LEDs
Custom max. current | 1..255 | Custom current per LED on full white
4-channel LEDs (RGBW) | Y/N | Support for SK6812 LEDs with white channel
Color order | select | If your LEDs display incorrect colors (red and green swapped), try changing it
Auto-calculate white | select | Get white channel from RGB automatically (only applicable for RGBW) [Details](/features/cct/#auto-white-handling)
Turn on after power up | Y/N | Whether the lights should turn on after a reset
Apply preset | 0..16 | Preset to load at boot (0 = none)
Set current preset cycle... | Y/N | The current preset cycle configuration will be used as boot default
Use Gamma for brightness | Y/N | Will correct brightness changes to make it appear more linear. Advised to leave off
Use Gamma for color | Y/N | Will correct colors to match those on a monitor. Strongly advised to keep on
Brightness factor | 1..255 | Factor to change master brightness if it is to dim/bright for a certain configuration
Crossfade | Y/N | Whether to have a smooth fading transitional effect when changing colors/brightness
Transition time | 0..65535 | How many milliseconds the transition lasts
Enable transition for secondary color | Y/N |
Enable Palette transitions | Y/N | Enable transitions for palettes (not affected by transition time)
Timed light duration | 1..255 | How long the nightlight should stay on
Target brightness | 0..255 | What brightness the light should have after time is over. 0=off.
Fade down | Y/N | Gradually fades down the light over the duration instead of turning it off at the end
Palette blending | select | Choose how the palette wraps at the end (seam)
Reverse LED order | Y/N | Mirrors the LEDs (last LED is first)
Skip first LED | Y/N | Will turn off the first LED and shift the remaining by 1 (1st LED used as a signal repeater)

### User Interface settings

This sub-page changes the look of the web interface.

| Setting name | Value Range | Description |
|---|---|---|
Server description | String 1..32 | The name of the device as shown on the top of the UI. Differs from Alexa device name
Sync button toggles... | Y/N | If enabled, both send and receive are toggled by the button in UI. If disabled, only sending is toggled and receiving is kept as configured in Sync settings.

### Sync settings

This sub-page configures external software synchronization interfaces.

| Setting name | Value Range | Description |
|---|---|---|
On/Off button enabled | Y/N | Check if there is a physical pushbutton connected to GPIO0
Infrared receiver type | select | Type of infrared receiver
Broadcast UDP port | 1..65535 | All WLED lights you want to group together must have the same port
Receive Brightness | Y/N | If there is a sync notification, whether its brightness should be applied
Color | Y/N | Whether the color of the synced device should be applied
Effects | Y/N | Whether the effect settings should be applied
Send on direct change | Y/N | Whether to send a sync notification when state changed via web UI or API
Send on button press | Y/N | Whether to send sync when toggled by button or IR
Send Alexa notifications | Y/N | Whether to send sync after changed by Alexa (you may use Alexa groups instead)
Send Hue notifications | Y/N | Whether to send sync after a connected Philips light changed
Send Macro notifications | Y/N | Whether to send sync after a macro was triggered
Send notifications twice | Y/N | Sends notifications twice (if you have issues with UDP packet loss)
Receive UDP realtime | Y/N | Receive live UDP stream data (DRGB, WARLS, ...)
Use E1.31 multicast | Y/N | Listen on multicast IP instead of unicast
E1.31 start universe | 1..63000 | Only applies for multicast. If you want to set different content, set ESPs at least 8 universes apart
Timeout | 100..65000 | Time after which to resume normal mode once stream has stopped. 65000 will keep the data indefinitely
Force max brightness | Y/N | Realtime stream with max. brightness (unless limited by power brightness limiter)
Disable realtime gamma correction | Y/N | Check if your host software does gamma correction already
Realtime LED offset | -255..255 | Shift the realtime input by how many LEDs
Emulate Alexa device | Y/N | Allows you to control the light via the Amazon Echo voice assistant. Requires reboot
Alexa Invocation name | String 1..32 | The name you want the device to have for control via Alexa. Choose something easy she can understand
Device Auth token | String 40 | You will get this in an e-mail during Blynk setup
MQTT Broker | IP or String 0..32 | Connect to this host MQTT broker
Device topic | String 0..32 | MQTT topic unique to this light
Group topic | String 0..32 | MQTT topic for all lights in a group (room, floor, ...)
Hue Bridge IP | 4x 0..255 | Your Hue bridge IPv4 address. Should be static to avoid reassigning
Poll Hue light | 0..99 | The ID of the hue lamp you want to sync WLED to
every x ms | 100..65000 | How often to poll. Smaller numbers decrease lag but might hurt bridge responsiveness
... | Y/N | Turn polling on/off
Receive On/Off | Y/N | Turn on/off like the hue light
Brightness | Y/N | Set brightness to that of the hue light
Color | Y/N | Set color to that of the hue light
Hue status | - | Shows the current connection status to a hue bridge
Baud rate | Various | Set the default Serial connection Baud Rate

### Time settings

This sub-page configures automation tasks.

| Setting name | Value Range | Description |
|---|---|---|
Get time from NTP | Y/N | Whether to get the current time from the internet
Use 24h format | Y/N | Use 24h clock format instead of AM/PM
Time zone | - | Your time zone. Open an issue if yours is unsupported. DST is applied automatically
UTC offset | -65000..65000 | Seconds to offset. If you want e.g. 1h offset, use 3600
Current local time | - | The local time the ESP has acquired. If set up correctly, should equal actual time
Clock overlay | - | The special overlay to use. Allows to display a clock on the strip
Countdown mode | Y/N | Allows to have a visual countdown towards a specific date
API macro fields | 16x String 0..64 | Allows you to define custom API calls which can be triggered by events
Boot Macro | 0..16 | Which macro to trigger after WiFi connected (0 is default action)
Alexa On/Off Macros | 2x 0..16 | Which macros to trigger when turning on/off via Alexa
Button Macro | 0..16 | Macro to trigger if button is short pressed. Default action is on/off toggle.
Long Press | 0..16 | Macro to trigger if button is long pressed (>0.7s).  Default action is random color.
Double press | 0..16 | Macro for double click on button.
Countdown-Over Macro | 0..16 | Macro to trigger when the countdown is over
Timed-Light-Over Macro | 0..16 | Macro to trigger when timed light is done

### Security settings

This sub-page manages permissions and updates.

| Setting name | Value Range | Description |
|---|---|---|
Enable OTA lock | Y/N | If enabled, no firmware updates may be done via WiFi and some settings can't be changed.
Passphrase | String 0..32 | To disable OTA lock, you need a password. The default is "wledota". Change it!
Deny access to WiFi settings | Y/N | Disables changes to WiFi settings while locked
Disable recovery AP | Y/N | If enabled, the module will not open an Access Point if connection to home WiFi failed.
Factory reset | Y/N | Deletes all custom settings data (passwords, configuration, macros, presets)
Manual OTA | - | If OTA is enabled, you can upload new binary firmware
Enable ArduinoOTA | Y/N | Useful for developers. Be careful, can even be left on when OTA locked!

