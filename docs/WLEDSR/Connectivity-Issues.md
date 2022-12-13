We've sometimes been unable to connect to one or more of our WLED enabled devices. Here are some things to try:

* Wipe (using [pyflasher](https://github.com/marcelstoer/nodemcu-pyflasher/releases/latest) or [esptool.py](https://github.com/espressif/esptool)) and re-flash your device.
  * **NOTE:** For ESP32 you must write flash at 0x10000. There are great [instructions here](https://github.com/Aircoookie/WLED/wiki/Install-WLED-binary).
* For more reliable connectivity on Android, go into WiFi advanced settings (press the 3 dots at the top right of the WiFi page) and disable 'Switch to mobile data' as well as 'Wi-Fi power saving mode'.
* In the WIFI Setup settings page of WLED, uncheck 'Disable WiFi sleep'.
* Ensure you have a strong signal to the device.
* When compiling, make sure you have selected Flash Size as 4MB (FS:2MB OTA:~1019KB)

**Note:** This page has been brought to you by our Discord friend **@tuantrung2905**. Thanks for your continued and persistent testing efforts!