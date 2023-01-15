---
title: Merge History
hide:
  # - navigation
  # - toc
---

_history of features added to the mdev branch_

Our latest work can be found here: [mdev](https://github.com/MoonModules/WLED/tree/mdev) and is based upon the latest version of 0.14. You can compile it yourself using PlatformIO.ini entry esp32_4MB_max or get a build from [Serg74](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/experimental/Firmware/AudioReactive) (daily) or [Wladi](https://wled-install.github.io) (periodically). 

## Pin drop downs support read only and reserved pins
January 14, 2023

<img width="144" alt="Screenshot 2023-01-14 at 18 42 14" src="https://user-images.githubusercontent.com/91013628/212558236-50c7da14-6e7c-489e-bc43-778979e9f844.png">

For more information see https://mm.kno.wled.ge/usermods/globalpins/
This page is shown if you press here: 

<img width="200" src="https://user-images.githubusercontent.com/91013628/212558383-fa3f4171-fda7-4d02-b749-bfff03226952.jpeg">

## Generate presets and playlists
January 12, 2023

Generate presets of all effects and group them together in playlists for 1D or 2D, Volume or FFT, combinations or all

<video width="160" autoplay><source src="https://user-images.githubusercontent.com/91013628/212558544-1c42abef-9567-4431-b940-366b7ce3362f.mov" type="video/mp4"></video>

<img width="221" alt="Screenshot 2023-01-13 at 15 29 50" src="https://user-images.githubusercontent.com/91013628/212558671-08aa50bd-4cef-4103-85bc-aeb8b37f8aa6.png">

## I2C and SPI pins make over
Januari 9, 2023

We were not happy how currently pins are managed. It raises questions in discord we could not answer so we decided to refactor it. It's not easy as a lot is interconnected but we made the first steps:

* Drop down for pin variables (see below)
* Rebuild the usermods (pins) settings screen so it works the same
* create _all bin files with a lot of usermods in it so we can test and improve
* do not reset ui variables if something is wrong (e.g. 4ld/type, enabled)
* use errorMessage instead and show errormessage in settings ui
* if global pins are -1, then there is no initialization of spi/i2c if usermods set pins to use global no initialisation
* HLD_PIN_* variables are used in platformio to specify defaults for global pins, no use of the recent introduced new variables I2CSDAPIN (etc) as causes more confusion, HLD_PIN serve these function and is used instead, 
* HW_PIN_DATASPI and HW_PIN_MOSISPI both existed but is one pin, merged to HW_PIN_MOSISPI as MOSI and MISO is both data
* i2c_scl (etc) variables are used in usermods without if -1 then HLD_PIN check, i2c_scl (etc) most be proper initialized before it can be used.
* No hijacking of global vars (giving them a value) in usermods 
* Don't register pins if usermod is not enabled
* create pinManager.joinWire and use as simplified way in usermods

This will be work in progress the coming weeks to implement in usermods (AudioReactive and 4LD working, others likely working but must be tested)

Overview of usermods available in _all bins:

<img width="448" alt="Screenshot 2023-01-08 at 15 13 00" src="https://user-images.githubusercontent.com/91013628/211351663-28e23710-b8e5-441b-8ec3-ff774b0dd106.png">


## Drop downs for pin variables
December 23, 2022

<img width="397" alt="image" src="https://user-images.githubusercontent.com/1737159/209367375-48841ac7-abc5-4f3f-ab43-16d7cdfb3a06.png">

* show pins which are in use (not selectable)
* excludes pins which may not be used (e.g. for 4ld/mclk variable)
* use global pins option
* undefined option

Currently implemented for AudioReactive and 4LineDisplay (tested) and all usermods which uses pin variables (testing in progress)

## mm.kno.wled.ge
December 21, 2022

[MoonModules pages](https://github.com/MoonModules/WLED-Docs) (wich is a fork of upstream pages) is now linked to [mm.kno.wled.ge](https://mm.kno.wled.ge) and is integrated in MoonModules WLED.

## Usermod specific help
December 19, 2022

<img width="282" alt="image" src="https://user-images.githubusercontent.com/91013628/208895794-27d9920e-2316-4c98-b21a-3319954985ce.png">

This goes to <https://mm.kno.wled.ge/soundreactive/Sound-Settings/>

Also added in Weather usermod and four line display usermod (pages wip)

## Ledmap2D
December 5, 2022
In 0.14 ledmaps are only supported for 1D.
This fix makes it work for 2D in WLED MM.

## Custom Effects improvements
November 29, 2022

Custom Effect improvements:
- Simplified [presets.json](https://github.com/MoonModules/WLED-Effects/tree/master/CustomEffects/wled) (can be downloaded directly into WLED MM in Custom Effect editor screen)
- some bug fixes to let Custom Effects run better on 2D

And combining Custom Effects with [1D expansions](#october-21-2022) gives great results and makes Custom Effects very well performing on large 2D matrices!!!

This is color_fade_pulse (by @atuline) with Circles expansion:

<video width="160" autoplay><source src="https://user-images.githubusercontent.com/1737159/204777643-a93413a8-b430-4499-a9b9-64acd55a351c.mp4" type="video/mp4"></video>

## Improved lay-out usermod settings
November 20, 2022

Grouping and pre-post texts in usermod settings (to make it more readable)

<img width="160" alt="image" src="https://user-images.githubusercontent.com/1737159/202906302-6b4411c8-7aee-4c12-a88c-0f1828232199.png">

## Audioreactive palettes
November 19, 2022

by NetMindz

<img width="296" alt="image" src="https://user-images.githubusercontent.com/1737159/202859807-b33ad565-ddf1-450e-9f0b-27d54b5dd0d8.png">

<video width="296" autoplay><source src="https://user-images.githubusercontent.com/1737159/202907087-6b25d88f-f43f-4d6d-9c39-21a7e9f4a5db.mov" type="video/mp4"></video>

## Extended mic settings in platformIO
November 18, 2022

<img width="692" alt="image" src="https://user-images.githubusercontent.com/1737159/202859001-665f245c-df4e-4c83-83d5-99d79cdc5801.png">

allowing to create mic specific environments:

<img width="261" alt="image" src="https://user-images.githubusercontent.com/1737159/202859113-bb4139a2-ba0a-48ab-bf7a-2d9aa033d3aa.png">

## Bin Aware Builds
October 28, 2022

Upload hardware specific configs based on generated filenames (=> WLED install is aware of underlying hardware).

Ultimate goal of bin awareness is that WLED itself says: hey! I found a new update for you, do you want to install?

<img width="334" alt="image" src="https://user-images.githubusercontent.com/1737159/199474001-0fc84cab-e34f-4236-8d37-1b7cee34e2ce.png">

plus

<img width="657" alt="image" src="https://user-images.githubusercontent.com/1737159/199474203-b9802184-532e-40b6-949e-8aa8f2b0d529.png">

(esp32mdev -> esp32_4MB_min. esp32mdevmax -> esp32_4MB_max / esp32_16MB_max)

plus

<img width="234" alt="image" src="https://user-images.githubusercontent.com/91013628/200820664-90f75ba9-523c-485e-bea3-5abd9713c33b.png">

(0.14.0. sequence of upstream commit . sequence of mm commit (need to be updated together with build date)

=>

<img width="422" alt="image" src="https://user-images.githubusercontent.com/91013628/200820550-abe14707-1f10-4c25-b20a-aa4a3770bfab.png">

=>

<img width="430" alt="image" src="https://user-images.githubusercontent.com/91013628/200820950-6d7be54f-c5fd-4b6a-97c0-6829c3201a13.png">

(WLED install is aware of the filename of it's bin, WLEDMM_0.14.0.2.1_esp32_16MB.bin in this example)

plus

<img width="400" alt="image" src="https://user-images.githubusercontent.com/91013628/200821356-36e51551-b055-493e-a3e4-8b332cad3eb2.png">

(Serg and Wladi repo's should use the same names)

## OTA latest release
October 25, 2022

Manual OTA Update is showing the latest MoonModules/WLED release and clicking on the version icon jumps to the [release pages on Github](https://github.com/MoonModules/WLED/releases), links to Serg74 and Wladi builds are also shown on the release page, so Manual OTA Update will guide you to the version you need!

<img width="398" alt="image" src="https://user-images.githubusercontent.com/91013628/197806516-90f49798-66b7-4989-ae11-590446c19a4a.png">

## Add Circles and Block as 1D expansion 
October 21, 2022

Add Circles and Block as 1D expansion and show virtualStrip effects with ⋮⋮

<img width="642" alt="Screenshot 2022-10-21 at 12 08 29" src="https://user-images.githubusercontent.com/91013628/197171416-266b1727-27cc-497c-b1f6-6953538d9dfc.png">

Tetris effect with block expansion:

<video width="437" autoplay><source src="https://user-images.githubusercontent.com/91013628/197814095-829ebffa-0e56-40af-a2fb-6d58c772a559.mov" type="video/mp4"></video>

## compatibility for SR/0.13 presets
October 20, 2022

Thanks to '_renumbered effect ID's back to WLED SR 0.13 numbering_': Add compatibility for SR/0.13 presets. This allows HB effects to be run on 0.14, however this shows that there are some shortcomings in 0.14: e.g. lissajoux not working as at should and overlapping segments not working (e.g. [Akemi from Hell](https://streamable.com/lze6gl)): November update: Lissajoux, Akemi from Hell (and others) fixed, overlapping segments working now. Check this in Led Preferences:

<img width="452" alt="image" src="https://user-images.githubusercontent.com/1737159/202910638-2c40e2dc-1277-4bf0-ad5b-9a6e97121649.png">

(To see them fully working: load them into WLEDSR 0.13!)

<video width="437" autoplay><source src="https://user-images.githubusercontent.com/91013628/196901131-a10f580c-2637-4c82-8054-abb5b8de4458.mov" type="video/mp4"></video>

To upload HR effects put effects / presets.json in <your wled ip>/edit

To start creating your own multiple segment effects put base / presets.json in <your wled ip>/edit

Presets.json files are [here](https://github.com/MoonModules/WLED-Effects/tree/master/Presets/HB_PresetPack210808_32x32_16seg)

## renumbered effect ID's back to WLED SR 0.13 numbering
October 16, 2022

  **Important update: renumbered effect ID's back to WLED SR 0.13 numbering** so WLED (SR) 0.13 is compatible with MoonModules 0.14 for presets and sync between devices 

<img width="437" alt="image" src="https://user-images.githubusercontent.com/91013628/196028158-c7ab7e2f-8a1c-4c5d-a253-19b11bfe1b6e.png">

## Extra hardware info on Info tab
October 13, 2022

<img width="462" alt="image" src="https://user-images.githubusercontent.com/91013628/196035364-3c38bfc5-f366-4d41-8a3b-56dc8858019d.png">


## Refactored JSON Mapping
October 1, 2022
  
smaller memory footprint so larger mappings can be used, e.g. Snake32:

<video width="405" autoplay><source src="https://user-images.githubusercontent.com/91013628/193404268-fb1cccf2-56af-4045-b654-be84d5ef3c8c.mov" type="video/mp4"></video>

Files are here: [JSONMappings](https://github.com/MoonModules/WLED-Effects/tree/master/JSONMappings)

## Games usermod additions 
September 27, 2022

Added to games usermod:

### 3D to 2D mapping
Adding Frame3D class which takes a 3D coordinate and maps this to 2D matrix (using addEffect(), setPixelColor(floats) and drawLine() added in 0.14 version)

<img width="405" alt="image" src="https://user-images.githubusercontent.com/1737159/192524364-4e870d79-4caa-41ad-ac39-288d71543916.png">    =    <img width="248" alt="image" src="https://user-images.githubusercontent.com/1737159/192523682-3d8cd32d-c589-4fe2-b27e-aecb1d5fbbb0.png">

### 3D + Gyro
Refactoring USERMOD_MPU6050_IMU (so that it works!) using latest ElectronicCats/mpu6050 library
Embedding this usermod in games usermod and use yaw pitch and roll in Frame3D class

<img width="248" alt="image" src="https://user-images.githubusercontent.com/1737159/192523682-3d8cd32d-c589-4fe2-b27e-aecb1d5fbbb0.png">    +    <img width="248" alt="image" src="https://user-images.githubusercontent.com/1737159/192525144-8d8590bf-449f-4336-975e-fced3ea34830.png">    =     <video width="248"autoplay><source src="https://user-images.githubusercontent.com/1737159/192526130-64ba2903-4481-42af-a297-4f18b78ed460.mov" type="video/mp4"></video>

## Adding pong
September 16, 2022

### Adding pong
In games usermod

<video width="248" autoplay><source src="https://user-images.githubusercontent.com/1737159/192528357-3cda343c-de1c-4820-adb6-fb71fdfdd1f2.mov" type="video/mp4"></video>

## updates from audio-reactive
September 8, 2022

### updates from audio-reactive
#### merged to upstream
* volume & frequency "dynamics limiter" - slower decay of sound volume in effects. Also has an effect on GEQ, as it turns on smoothing for frequency bands. 
<img width="400" alt="image" src="https://user-images.githubusercontent.com/91616163/189164956-9f5cf51c-d725-4691-94d3-8ab60d8e384c.png">

* GEQ frequency scaling: None (as in SR WLED), Linear, Square Root (new default), Logarithmic. 
<img width="450" alt="image" src="https://user-images.githubusercontent.com/91616163/189165448-61d4c080-2501-42fc-b975-da87bc2adfe9.png">

#### work in progress
* New option "MIC profile" - default (same table as in SR WLED), line-in (strictly "pink noise"), IMNP441 (optimized), ICS-43434 (optimized). 
This option causes the use of different "pink noise tables" when adjusting the frequency spectrum to human "hearing sensitivity". Pink noise calibration is very common when using hardware Equalizers. A good testcase is this [Pink Noise Video](https://www.youtube.com/watch?v=noapz4XPR6g).
<img width="400" alt="image" src="https://user-images.githubusercontent.com/91616163/189166244-482f4530-7d18-42af-ac4f-27bd0bfe5f95.png">

* (minor) Showing the "GEQ input gain" in percent, next to the slider value. 
![image](https://user-images.githubusercontent.com/91616163/189167784-ea972e67-cac0-4b7c-85de-fc024291ddb0.png)

* user-settable "Trebble Amplification" for GEQ effects. Will be placed into the Info Page, directly under "GEQ input gain".


## FrameWork-V4
September 6

**Lessons Learnt**: When upgrading WLED devices to software using the IDF 4.4.x framework, it seems that a flash erase is needed. Without this, we observed crashes whenever files were written.

Suspected cause: Lorol LittleFS (from standards framework) is not compatible with the built-in littleFS from IDF v4.4 / arduino-esp32 v2.0.4. Could be that the partition table is the problem, so a chip erase is needed to clean the table.

A new merge to mdev has been done: new environment `esp32mdev_V4` so that normal compiles are not getting the new framework automatically.


### updates from audioreactive-prototype
* Will merge into upstream

### Json Mapping
From excel/vba <img width="181" alt="image" src="https://user-images.githubusercontent.com/1737159/188688306-b5a5e7d8-3172-43b8-9f53-778ff9a2df3b.png"> via /edit and <img width="98" alt="image" src="https://user-images.githubusercontent.com/1737159/188688993-34c73f35-b642-4120-b31d-c87ea58ea10e.png">
 to matrix <img width="160" alt="image" src="https://user-images.githubusercontent.com/1737159/188688601-73a9e7f8-34d9-463f-9ec3-1cacaea13d6b.png">

Files are here: [JSONMappings](https://github.com/MoonModules/WLED-Effects/tree/master/JSONMappings)

## September 2
### updates from audioreactive-prototype
Merged into upstream
### Expand1D effects
* Virtual strips in 1D effects

Strip bar has been merged to upstream, strip Arc and strip Corner (as opposed to pixel Arc and Corner, see upstream) is "waiting" in upstream branch. To be added to MoonModules.

<video width="429" autoplay><source src="https://user-images.githubusercontent.com/1737159/192609697-15cc43f8-157e-4a0e-8ea7-32e755bf79ef.mov" type="video/mp4"></video>

### Usermod level up

each usermod <img width="166" alt="image" src="https://user-images.githubusercontent.com/1737159/188707291-c9d55626-6b01-4d28-9d61-0f9adb7eb8d3.png"> got its own settings page <img width="186" alt="image" src="https://user-images.githubusercontent.com/1737159/188712805-bb6bdff5-e762-4031-94ae-46d6e961436a.png">


## September 1

## August 31
### Custom Effects

<img width="296" alt="image" src="https://user-images.githubusercontent.com/1737159/188725863-3c133079-f6a5-4885-82d8-d603f3c95f3e.png"> + 
<img width="210" alt="image" src="https://user-images.githubusercontent.com/1737159/188725973-0d3ad535-bb9f-459c-848d-8b11f80bd3cc.png"> = 
<img width="216" alt="image" src="https://user-images.githubusercontent.com/1737159/188726087-98f600b3-5f95-432a-854d-f1ff51426ec0.png">

* drawArc using x2+y2=r2 instead of sin/cos

### Weather usermod

<img width="181" alt="image" src="https://user-images.githubusercontent.com/1737159/189068765-e80c8a0e-3e83-44a6-ae1f-4242ee6514da.png"> + 
<img width="234" alt="image" src="https://user-images.githubusercontent.com/1737159/189068898-eb424d9e-b929-4cd9-9e01-2fbc93847e2d.png"> = <img width="216" alt="image" src="https://user-images.githubusercontent.com/1737159/188919809-1dc14eda-90f9-43fc-a7fa-58957dd810c5.png">

## August 29
### updates from audioreactive-prototype

<img width="245" alt="image" src="https://user-images.githubusercontent.com/1737159/188707602-bbf02069-a09d-4c37-884e-785f500958c4.png"><br>
<img width="334" alt="image" src="https://user-images.githubusercontent.com/1737159/188814448-7e74dacc-3bd3-4348-b280-a2cce294b3ff.png">

## Merged into upstream
* Sound simulations
* Expand 1D into 2D
* Virtual strips in 1D effects
* liveview / peek 2D
* AR: reduce variables 
* AR: Sound info in info panel
* Replace leds[] by sPC/gPC
* Slower fade-out in GEQ and a few other audioreactive effects.
* Audio reactive stuff:
* * upgrade to latest ArduinoFFT, using 'float' instead of 'double'. Up to 8 times faster!
* * configurable sound dynamics limiter, to make audioreactive effects flow with the  music, and prevent "sudden flashes at onsets". A kind of 'flicker fixer'.
* * improvements for UDP sound sync
* * new frequency scaling options 'square root' and 'logarithmic' - GEQ shows more action in higher frequencies.
