## Compiling from a fresh install of the Arduino IDE

**Note: Around October 2020, mismatching library version issues made it increasingly difficult to compile WLED with the Arduino IDE. Your best bet is to use VS Code with Platform IO. In the meantime, here's the old Arduino IDE instructions:**

1. Have a read through Aircoookie's compiling documentation at https://github.com/Aircoookie/WLED/wiki/Compiling-WLED
1. Download and install the Arduino IDE from [arduino.cc](https://www.arduino.cc/en/Main/Software). Defaults are OK.
1. Start the Arduino IDE and add ESP8266/ESP32 board support by going to "File | Preferences" ("Arduino | Preferences" for macOS (⌘,))
1. In the "Additional Boards Manager URLs" section, copy these URL's and add: https://arduino.esp8266.com/stable/package_esp8266com_index.json for an ESP8266 and https://dl.espressif.com/dl/package_esp32_index.json for an ESP32. You can add both by separating them with a comma. 
1. Press "OK" to install support for the ESP8266/ESP32 platform
1. Go to "Tools | Board | Boards Manager..."
1. For the ESP8266/32, search for "ESP8266" and/or "ESP32"
1. Click on "Install" for each.
1. As of May 2020, the current version for ESP8266 was 2.7.1
1. As of May 2020, the current version for ESP32 was 1.0.4

If you already have ESP8266/32 drivers installed, please ensure your drivers are recent:

1. Go to "Tools | Board | Boards Manager...".
1. For the ESP8266/32, search for "ESP8266" or "ESP32"
1. As of July 2020, the current version was 2.7.2
1. As of July 2020, the current version was 1.0.4

## Board Settings

### LOLIN D32 (ESP32)
![](https://github.com/atuline/WLED/blob/assets/media/LOLIN_D32.png?raw=true)
### LOLIN WeMOS D1 Mini (ESP8266)
![](https://github.com/atuline/WLED/blob/assets/media/LOLIN_WeMOS_D1_Mini.png?raw=true)


**Note:** Before attempting to compile WLED, make sure you can select your ESP board and compile a basic sketch such as:
"File | Examples | 01.Basics | Blink"


## WLED library pre-requisites:

WLED makes use of a LOT of 3rd party libraries and is NOT easy to compile, especially for anyone new to Arduino. Although the WLED distribution contains several of these libraries, it doesn't include them all. Additional libraries you need to install are:

* NeoPixelBus by Makuna
* FastLED
* IRRemoteESP8266 (ESP8266 Only)
* ArduinoFFT (ESP32 Only)
* ESPAsyncTCP (ESP8266 Only)
* ESPAsyncUDP (ESP8266 Only)
* ESPAsyncWebServer (See notes below)
* AsyncTCP (ESP32 Only)

See the next section to find/install these libraries.

## Install libraries that are included in the Library Manager

1. Navigate to "Tools | Manage Libraries..." or "Sketch | Include Libraries | Manage Libraries..." for macOS (⇧⌘I)
1. Search for and install "NeoPixelBus by Makuna"
1. Search for and install "FastLED by Daniel Garcia"
1. Search for and install "IRremoteESP8266 by Ken Shirriff, etc"
1. Search for and install "arduinoFFT by Enqrique Condes"

## Install libraries that are not included in the Library Manager:

To install libraries that are not in the library manager, you would typically:

1. Download the zip file
1. In the Arduino IDE use "Sketch | Include Library | Add Zip Library"
1. Navigate to where you downloaded the .zipped library.
1. Select it and press OK.
1. Your library should now be included if you go "Sketch | Include Libraries" and navigate down to Contributed libraries.

1. Download and install [ESPAsyncTCP](https://github.com/me-no-dev/ESPAsyncTCP)
1. Download and install [ESPAsyncWebServer](https://github.com/Aircoookie/ESPAsyncWebServer)

1. Download and install [ESPAsyncUDP](https://github.com/me-no-dev/ESPAsyncUDP)
1. For ESP32 Download and install [AsyncTCP](https://github.com/me-no-dev/AsyncTCP)

**Note:** AirCoookie has since created a fork of ESPAsyncWebServer, and the original [ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer) will no longer work with WLED. If you have the original installed, you can edit wled.h and comment out the line as follows:

//  #define WLED_ENABLE_WEBSOCKETS


If you add the library manually or with git you will most likely need to **restart**, yes **restart** the Arduino IDE before it will be recognized. For more information on libraries, see: https://www.arduino.cc/en/Guide/Libraries.

When you are done, if you navigate to 'File | Examples' and scroll all the way down, you should see:

![](https://github.com/atuline/WLED/blob/assets/media/examples.png?raw=true)

### Download WLED
* In a web browser you can navigate to [wled](https://github.com/Aircoookie/WLED) and unzip into a new directory.
* Alternatively, you can download our [Sound Reactive Master](https://github.com/atuline/WLED).
* Make sure you can compile the original WLED before attempting to compile our sound reactive version.
* You can then 'Download' the Zip file.
* Unzip it into a new directory.
* If you have 'git' installed, navigate to where you want to store your project and run:

    `git clone https://github.com/atuline/WLED.git WLED-Reactive`



### Compiling WLED for Arduino IDE (OUTDATED)

Once you have:

* Installed the Arduino IDE.
* Installed support for ESP32/ESP8266.
* Updated the drivers on an existing installation of the IDE.
* Downloaded and installed the library pre-requisites.
* Downloaded and installed WLED.
* Connected your device and ensured it connected to a COM port.
* For previous WLED users, ensure you have modified your Flash settings to support 2MB minimum.

You should now be able to compile and upload WLED to your ESP device.

If this feels like a treasure hunt, it is. Now, imagine what the authors of WLED had to go through just
to get this all working together. We just figured out how to compile it and to get some sound reactive code running.

