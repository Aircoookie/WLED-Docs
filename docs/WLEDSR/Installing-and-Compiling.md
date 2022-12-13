

***IMPORTANT:*** _Before attempting to compile this fork of WLED, make sure you can compile the [original WLED](https://github.com/Aircoookie/WLED) - instructions are [here](https://kno.wled.ge/advanced/compiling-wled/). 
If you are unable to compile WLED, please consider flashing your device with [binaries](https://github.com/atuline/WLED/releases/latest) instead._

If you managed to compile original WLED, test your new skills and [compile the soundreactive fork of WLED](https://moonmodules.github.io/WLED-Docs/WLEDSR/Installing-and-Compiling#getting-started).


# Installing pre-built binaries

## Downloading USB Drivers

Download the CH340 drivers at https://www.wemos.cc/en/latest/ch340_driver.html


## Flashing From Binary

The Sound Reactive WLED binaries for ESP32 are located [here.](https://github.com/atuline/WLED/releases)

SR WLED releases are also included in this web-based installer: https://wled-install.github.io
 
## Flashing ESP32 Binaries with esptool

_Warning_: We had to change the partition size on the ESP32 in order to 'fit' all the new features. This means that the 'old way' of upgrading/flashing, no longer work unfortunately. **You cannot use ESPHome Flasher**, and you cannot use OTA from a build prior to v0.13.0-b5.

1. Download [esptool](https://github.com/espressif/esptool).
1. Download the ESP32 bootloader, such as [esp32_bootloader_v4](https://github.com/Aircoookie/WLED/releases/download/v0.13.3/esp32_bootloader_v4.bin)
1. Download the sound reactive binary, such as [Atuline releases](https://github.com/atuline/WLED/releases)
1. Plug the ESP32 board into your computer.
1. Optionally determine which Com port it uses. You could use NodeMCU-PyFlasher to do this, but don't flash the binary with it.
1. Open a Command prompt on your computer.
1. Assuming you copied esptool and both binaries to the same directory, you could clear the contents of the ESP32 with:
    ` esptool.exe erase_flash`
1. Then burn the bootloader with:
    `esptool.exe write_flash 0x0 esp32_bootloader_v4.bin`
1. Once complete, you can now burn the sound reactive binary with:
    `esptool write_flash 0x10000 soundReactive_WLED_0.13.X_ESP32.bin`
1. You can optionally add the port, such as '-p COM6'.
1. In addition, if this is the first time you've used this version, you need to go to the "Security & Updates" settings page and tick the "Factory reset" box, then select "Save & Reboot". Caveat: May not be necessary if you ran 'erase_flash' above.
1. This will reset the EEPROM and remove any settings or presets you may have saved.

Note: If you Flash via another method, you will definitely need to perform a Factory Reset. Cycling the power is also a requirement if you're doing anything with I2S.

### Flashing ESP8266 Binaries

1.  Download for your platform [NodeMCU-PyFlasher](https://github.com/marcelstoer/nodemcu-pyflasher/releases).
1.  Plug the WeMOS D1 Mini (or other ESP8266 device) into your computer.
1.  Run NodeMCU-PyFlasher.
1.  Load the binary.
1.  Select the Com port.
1.  Select 'yes, wipes all data'.
1.  Press Flash NodeMCU.


<br/>

## unofficial development binaries - here be dragons
You can find some unofficial SR WLED binaries, including intermediate development builds for ESP32, here:

### Installation services
* <https://wled-install.github.io>
* <https://install.wled.me>

### Firmware Binaries
* <https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/Sound_reactive>
* <https://github.com/wled-install/wled-install.github.io>

Please keep in mind that these sites are not maintained by the SR WLED team. 
You may find old outdated binaries, or binaries that might not work on generic ESP32 hardware. So please compare build number and dates, and read descriptions before installing one of these.

<br/>


# Compiling from Platform IO

### Getting started

<b>&rAarr; first read https://kno.wled.ge/advanced/compiling-wled/ </b> <br/>
  &rarr; use source code from https://github.com/atuline/WLED/tree/master<br/>
  &rarr; start with one of the sound reactive compile environments, like  [`env:soundReactive_esp32dev`](https://github.com/atuline/WLED/blob/3752b78d3b845f722ba043d92007cc79aa811561/platformio.ini#L444)<br/>
  &rarr; read [`wled00/wled.h`](https://github.com/atuline/WLED/blob/master/wled00/wled.h#L16), add your own settings to [`wled00/my_config.h`](https://github.com/atuline/WLED/blob/master/wled00/my_config_sample.h#L4) <br/>
  &rarr; put your own compile environment(s) into [platformio_override.ini](https://github.com/atuline/WLED/blob/master/platformio_override.ini.sample).

SoundReactive has some additional compile time options - see [`wled00/audio_reactive.h`](https://github.com/atuline/WLED/blob/master/wled00/audio_reactive.h#L27) and [`wled00/audio_source.h`](https://github.com/atuline/WLED/blob/3752b78d3b845f722ba043d92007cc79aa811561/wled00/audio_source.h#L20).


### Additional Compile Guidelines
* If you get .py errors, install Python (wait for the VSCode popup to install Python)
* If you do not install the Arduino IDE (Why should you if you have PlatformIO) and your board is not recognised if you compile to board, install the [USB to UART bridge VSP Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
* For the sound reactive ESP32 firmware, the board type should be env:soundreactive_esp32dev. This is because we have modified the build partitions in order to go beyond the original compile size limits of WLED.

Note: We have long since stopped compiling WLED with the Arduino IDE.

### Disabled Feature of WLED
Some features of "standard WLED" are by default disabled in SR WLED. These extended features have shown negative impacts on performance and stability - we need all available "power" to run sound analysis. For example, they possibly use too much memory (FLASH or RAM), can lead to lags in animations, or may cause slow responses to sound input. 

The same is true for many WLED usermods: they might work (like 4LineDisplay), but could have side-effects on our sound reactive features so we disabled them in our "official" firmware builds.


#### How to Shoot Yourself in the Foot

If you're keen to use a disabled WLED feature, in your personal build of SR-WLED:

1. check if there is a `-D DISABLE_...` flag in your build environment (platformio.ini, or platformio_override.ini), and comment it out or remove it.
2. check if the feature is disabled explicitly in [wled00/wled.h](https://github.com/atuline/WLED/blob/master/wled00/wled.h#L34).
3. If a feature has been disabled explicitly in wled.h, then there is usually a good technical reason for that decision. Please don't write bug reports for feature that were disabled explicitly.

4. If you still want that feature, you can un-disable it like this 

Add to your [wled00/my_config.h](https://github.com/atuline/WLED/blob/master/wled00/my_config_sample.h#L4)
```C++


// re-activate Alexa support. Yes I know this is not supported officially. 
// I don't mind if animations will sometimes "stutter" and lag behind the sound.
#ifdef WLED_DISABLE_ALEXA
  #undef WLED_DISABLE_ALEXA
#endif

// re-activate MQTT support. Yes I know this is not supported officially. 
// I am ready to take good care of my hung, non-responsive device if necessary.
#ifndef WLED_ENABLE_MQTT
  #define WLED_ENABLE_MQTT
  #ifdef WLED_DISABLE_MQTT
  #undef WLED_DISABLE_MQTT
  #endif
#endif

// re-activate IR receiver support. Yes I know this is not supported officially. 
// I can live with my LEDs flickering sometimes, and effects stuttering randomly.
#ifdef WLED_DISABLE_INFRARED
  #undef WLED_DISABLE_INFRARED
#endif


```
