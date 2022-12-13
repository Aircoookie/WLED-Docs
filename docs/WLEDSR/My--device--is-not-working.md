If you'd like some help with your device, these are the types of things we would be asking:

* If you require support, please engage the Discord community as linked to in the readme.md. Github issues are more for actual bugs in the firmware.
* **When asking for support on Discord or on another forum, please provide details up front and not way down a threaded list of messages. Edit your original question if you have more information to provide.**
* The latest version of SR WLED for the ESP32 has a sound pin configurator. Please review yours.
* Don't forget to check the pin on the LED settings page.
* Please provide a comprehensive, but clear and concise description of the symptoms and your environment.
* That includes things like exactly what board you're using, how many led's, are you using a level shifter
* Also, the exact steps you took to flash a binary and the steps you took after doing so.
* How about posting a crystal clear close-up photo of your wiring, or better yet, a block diagram.
* If something doesn't work as a result of an upgrade, did you roll back to ensure it still works?
* Don't just reboot the device. Actually, cycle the power (reference: IT Crowd).
* If you change the microphone pin/type, you need to reboot. If using an I2S microphone, you need to cycle the power on the device.
* You may need to re-flash/clear the device completely especially after a major update.
* SR WLED had to change from the default 'partition size' because we outgrew the default 1MB. As a result, you need to perform a 'Factory reset' after flashing it.
* Does the regular version of WLED work, while this one doesn't?
* We have disabled (and do not support) additional services such as IR, Alexa, Blynk, MQTT and so on. In order to enable them, you'll need to go into the code (see wled.h), enable the service and then compile/upload. The WLED SR team does not support these services.

* If you are referring to code, please provide a link to the version you are referring to.
* Is it just sound reactivity that doesn't work? Is there a specific animation?
* Is it an ESP32? An ESP8266? Please provide the link that you downloaded the files from.
* How exactly did you flash the device? See https://github.com/atuline/WLED/wiki/Installing-and-Compiling
* Are you compiling from IDE? We are no longer supporting the Arduino IDE.
* Make sure your microphone is powered by the 3V pin and NOT Vin or 5V . . and that your LED's are NOT connected to that 3V pin either (source: experience).
* If you had previously used a 5V pin for your microphone, you may have blown that analog pin.
* Have you gone through [initial settings](https://github.com/atuline/WLED/wiki/Running-Sound-Reactive-WLED)?
* Is your audio all wired up OK? [See here](https://github.com/atuline/WLED/wiki/Analog-Audio-Input-Options).
* Which microphone/input are you using and how is it configured?
* Leave the MAX4466 gain untouched. It works fine out of the box.
* Have you tested that microphone with a [basic analog sound sampling sketch](https://github.com/atuline/WLED/wiki/Analog-Sound-Sampling-Sketch-Example)?
* You have an INMP441 or ICS-43434? Try the [basic digital sound sampling sketch](https://github.com/atuline/WLED/wiki/Digital-Sound-Sampling-Sketch-Example).
* What are the results of that sketch? Does it respond to your speech? A MAX4466 and INMP401 should average about 1875 on an ESP32, a MAX9814 about 1350 for all gain settings.
* Try a different pin when using that sketch if you're still not seeing good results.
* Have spares of everything. They're cheap and they break. (source: experience)
* How about power? Lots of LED's require lots of power and a common ground for everything.
* Does the [latest release from WLED](https://github.com/Aircoookie/WLED/releases/latest) work?
* Are you using our most recent 'MASTER' release?
* Have you tried flashing [our latest release](https://github.com/atuline/WLED/releases/latest)?
* Is your device working in AP mode?

* Got too much noise? Try lowering the current draw/brightness and clean up the wiring.
* If it's a compile error, can you provide the errors?
* Have you made any changes to the source?
* UDP Sync not working? Have you tested WLED's built-in sync? Do you need to enable multicast on your network equipment?
* If your bootloader is broken, the binary may not load. Try the one from wled.me first.
* Can you document the steps to re-create that error?
* Make sure your grounds are all connected together.
* If you're using our 'dev' branch, don't forget to make a fresh 'pull'.
* [See my FastLED support FAQ](http://tuline.com/fastled-support-qa/).

**MAX4466/ESP32 Sampling results - Quiet room**
![MAX4466 in quiet room](https://github.com/atuline/WLED/blob/assets/media/quiet.jpg)

**MAX4466/ESP32 Sampling results - Talking**
![MAX4466 talking](https://github.com/atuline/WLED/blob/assets/media/loud.jpg)

The other analog input options should provide something similar.

## UDP Sound Sync Issues

We received a support request reporting that UDP sound synchronization will take down a Wi-Fi network. The challenge with troubleshooting WiFi is that you need to configure your packet sniffer in monitor mode, something which is very difficult to achieve with most workstations. As a result, we are unable to see a lot of Wi-Fi network traffic.

One setting to change on 'WiFi Setup' is to check on "Disable WiFi sleep" mode.

As for UDP support, this article may shed some light on the challenges:

https://superuser.com/questions/1287485/udp-broadcasting-not-working-on-some-routers

In the meantime, UDP Sound sync has been configured to transmit 50 packets per second.

