## I2S Digital Audio
I2S digital sound modules utilize the industry-standard 24-bit [I²S interface](https://en.m.wikipedia.org/wiki/I%C2%B2S). The I²S interface allows to connect them directly to an ESP32 (but NOT an ESP8266). The IMNP441, and also the recently tested ICS-43434 (thanks to Serg74) work very well with SR WLED, and they perform much better than any analog device at a comparable price.

<br/>

| from INMP441, ICS-43434 | from PDM (e.g. SPM1423) | from Other | to ESP32 GPIO | |
| --- | --- | -- | --- | --- |
| L/R | SEL | SEL | Gnd | ground => left channel
| SD | DATA | DOUT | 32 | serial data
| WS | CLK | LRCK | 15 | left right clock
| SCK | -- | BCLK | 14 | serial clock
| -- | -- | MCLK | 0  | master clock (if needed)
| VDD | 3V3 | VDD | 3.3V | power don't use 5V!
| GND | GND | GND | Gnd | ground, 0V


See also &rArr; [Sound setting examples for common microphones](https://moonmodules.github.io/WLED-Docs/WLEDSR/First-Time-Setup#sound-settings-getting-started-with-common-microphones)

<br/>

**Microphone type** ([SR-WLED sound settings](https://moonmodules.github.io/WLED-Docs/WLEDSR/Sound-Settings#i2s-digital-input))
* use `Generic I2S` for INMP441, ICS-43434, and other non-PDM devices
* use `Generic I2S PDM` for PDM microphones like SPM1423
* use `SPH0645` for adafruit SPH0645
* use `ES7243` for Lyra-T mini, and other board that have the ES7243 chip
* use `Generic I2S with Mclk` only for devices that have an addition pin for 'master clock'


**Important**: please make sure that your I2S device provides sound input on the **LEFT audio channel**! For the INMP441 this is achieved by wiring the 'L/R' connection to GND (ground). Only exception is the "ES7243" driver, which is always using the _RIGHT_ audio channel.

<br/>

Since 0.12.0, you can change I2S GPIO pins in the [Sound Settings](https://moonmodules.github.io/WLED-Docs/WLEDSR/Sound-Settings) interface; on ESP32 **any** available GPIO can be used for I²S. The 'SD' signal could also be mapped to an input-only (GPI) pin _(*)_, if you are low on GPIO pins. You'll need to reboot when done with pin assignment - don't forget to "save". To reboot, please press 'reset' on your ESP32. Unfortunately a restart by software ("soft reboot") is not always sufficient to activate new driver settings.

In addition to I2S microphones, there are solutions available for line-in via I2S. We already have driver support for Boards/Shields with "es7243" chip, and we're investigating "es8388". 

Other I2S ADC (analog-to-digital-converter) devices and microphones that have a [standard I2S interface](https://en.m.wikipedia.org/wiki/I%C2%B2S) may already work with WLED-SR, by using one of the I2S "Generic" drivers (`Generic I2S`, `Generic I2S PDM`, or `Generic I2S with Mclk`). It is important however that sound input comes on the **LEFT audio channel**. Please keep in mind that this is a spare-time open source project - we do our best to make generic drivers but we cannot test with all available devices.

### Notes for older releases of SR WLED (before 0.13.2)

* _(*)_ Due to a problem that was fixed very recently, its not possible to use input-only GPI pins in older releases of SR WLED. There will be no warning if you try to do so. This problem is solved in the [latest release version of SR WLED](https://github.com/atuline/WLED/releases).

* In old releases, you need to change GPIO pins used by defining `I2S_WS`, `I2S_SD`, and `I2S_SCK` in your PlatformIO config, or by editing the values in audio_reactive.h. 


### Still having problems?

We do not have these digital microphones running on an ESP8266.

Having problems getting the INMP441 running with WLED? Here's a test sketch (which you can compile with the Arduino IDE): https://pastebin.com/Ua7s7LYF
. If you are still having a problem with that sketch, change the line with ONLY_LEFT to ONLY_RIGHT. If that works, you'll need to go into audio_source.h and change that line.

Initial I2S support by @spedione

<hr/>

## Some I2S audio modules and boards


### IMNP441 
This is the IMNP441; you can find it in many shops including Amazon and Aliexpress. It works very well with SR WLED. 

<img src="https://user-images.githubusercontent.com/91616163/193432850-70c37da6-a295-4bb2-ad7c-e975fcca7c87.jpg" width="20%" height="20%" />
 &nbsp; 
<img src="https://user-images.githubusercontent.com/91616163/193670167-79d4d54d-0226-428d-b010-5c0c4c2d6703.jpg" width="15%" height="15%" />

<p> &nbsp; </p>

### ICS-43434
Here's the first board I've seen with the ICS-43434 at: https://www.tindie.com/products/serg74/digital-i2s-microphone-ics-43434-add-on/ 

 <img src="https://user-images.githubusercontent.com/91616163/193432714-fba36bde-72b3-4f0b-b66d-32f7dd7e5ee4.jpg" width="20%" height="20%" />

<p> &nbsp; </p>

### I2S ADC for Line-In
Looking to add line-in with I2S support? You might want to try I2S ADC boards that use one of these chips: 
* [CirrusLogic WM8782](https://www.cirrus.com/products/wm8782/)
* [CirrusLogic CS5343](https://www.cirrus.com/products/cs5343-44/)
* [AKM AK5720](https://www.akm.com/eu/en/products/audio/audio-adc/ak5720et/) ([datasheet](https://www.akm.com/content/dam/documents/products/audio/audio-adc/ak5720vt/ak5720vt-en-datasheet.pdf))
* [Ti PCM1808](https://www.ti.com/product/PCM1808) or [Ti PCM1802](https://www.ti.com/product/PCM1802)

<p> &nbsp; </p>

<img src="https://user-images.githubusercontent.com/91616163/193432571-fb48bbff-e611-4235-bb47-5418f88c2c8d.jpg" width="20%" height="20%" />   &nbsp; &nbsp;
 <img src="https://user-images.githubusercontent.com/91616163/193432590-176d20e8-2432-4eca-86f9-86cda91aa873.jpg" width="40%" height="40%" /> &nbsp; &nbsp; 
<img src="https://user-images.githubusercontent.com/91616163/197608486-cafcdf75-8039-4cb9-9d96-182d835c52c3.JPG" width="24%" height="24%" /> 


Many I2S ADC boards expect an additional MCLK signal ("Main Clock" aka "System Clock" aka "Master Clock" aka "Memory Clock").  MCLK is sometimes labelled SCLK for "system clock". For these boards with 4 data pins, use our `Generic I2S with MCLK` input driver, and connect MCLK pin to GPIO pin 0, 1, or 3 on ESP32.

<p> &nbsp; </p>

### ES7243 based boards
* [ESP32 Lyra-T mini V1.2](https://docs.espressif.com/projects/esp-adf/en/latest/design-guide/dev-boards/board-esp32-lyrat-mini-v1.2.html#esp32-lyrat-mini-v1-2-hardware-reference)

 
<img src="https://user-images.githubusercontent.com/91616163/193413316-00bc6d61-ec7a-4bc4-83a4-59071e71db57.png" width="40%" height="40%" />

<p> &nbsp; </p>

### ES8388 based boards - not yet supported
with I2S on-board microphone and I2S Line-In (**SR WLED support not available yet**, but being developed)

* [ESP32 Lyra-T V4.3](https://docs.espressif.com/projects/esp-adf/en/latest/design-guide/dev-boards/board-esp32-lyrat-v4.3.html) 
<img src="https://user-images.githubusercontent.com/91616163/193413089-6f71193c-d8db-4185-9de3-c8b4005431c1.jpg" width="40%" height="40%" />


* [Ai-Thinker ESP32 Audio Kit v2.2](https://docs.ai-thinker.com/en/esp32-audio-kit) 
<img src="https://user-images.githubusercontent.com/91616163/193413239-e3fd9567-a64d-464c-bdc6-2a2ce69c0df5.png" width="40%" height="40%" />


<p> &nbsp; </p>


## Other Ideas (needs some work to make it work)


### use a second esp32 as bluetooth audio to I2S device

In principle, its possible to have a second ESP32 that provides sound input to WLED via I2S.

* some interesting explanations on the I2S bus: https://diyi0t.com/i2s-sound-tutorial-for-esp32

<img src="https://diyi0t.com/wp-content/uploads/2020/08/I2S-Network-Components.png" width="50%" height="50%" />

* pschatzmann has created [A Simple Arduino Bluetooth Music Receiver and Sender for the ESP32](https://github.com/pschatzmann/ESP32-A2DP)
* the library from pschatzmann has examples for how to connect an I2S DAC for playing music from Bluetooth on a speaker. The main difference for SR-WLED should be to put the "bluetooth ESP" into "I2S slave" mode (instead of being the "I2S Master"). There is some information on this website: https://www.eevblog.com/forum/microcontrollers/esp32-as-i2s-(audio)-slave

* make sure the "I2S slave" device is sending 24bit or 16bit *Phillips Standard* data format.


