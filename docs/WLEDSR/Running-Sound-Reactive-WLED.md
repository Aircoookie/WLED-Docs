### Captive Portal
When you first connect to a WLED device in AP mode, there is some really annoying behavior on the captive portal implementation in Android. The captive portal is the limited browser you are forwarded to in order to login to a web site. What happens is that if you go into 'Effects', you can't scroll up. In order to get around that, click the three dots at the top right of the page, select 'Use Network as is', then open up Chrome and navigate to the site at 4.3.2.1.

### Initial Sound Reactive Settings
On the _"Sound Settings"_ page, configure the Squelch for a value (default is 10) to reduce your background noise for volume reactive effects. Volume reactive effects start with a single '*'. Typically, values between 4 and 20 should suffice. The higher the number, the greater the background noise is suppressed.   
  
Configure the Gain setting (default is 60) to change the "perceived volume" of the input signal. More info on [Squelch and Gain here](https://moonmodules.github.io/WLED-Docs/WLEDSR/Sound-Settings#squelch).

### Initial 2D Settings - ESP32 Only
When changing any values in the LED settings page, you'll need to update the 2D settings. If not using a 2D matrix, you can set them to 1 x <number of LED's> or vice versa.  If using a 2D matrix, configure these values for width x height. A value of less than 4 in either dimension will not work with some of the 2D animations.

The serpentine parameter configures whether the LED's are wired up in a continuous/serpentine layout or top to bottom and repeat.

### Initial UDP Sync Settings
Devices can be configured as 'disabled', 'transmit' or 'receive' [UDP sound](https://moonmodules.github.io/WLED-Docs/WLEDSR/UDP-Sound-Sync). This is completely independent of the 'Sync' button, which synchronizes effects. 

As a result, you can run multiple types of sound reactive animations when [UDP Sound Sync](https://moonmodules.github.io/WLED-Docs/WLEDSR/UDP-Sound-Sync) is enabled. This feature provides a subset of the sound and FFT data to several 'slave' devices. As a result, some FFT enabled routines will not function in this mode. You must RESET the ESP32 after you enable/disable this on the Sync settings page.



## Connect to WLED

1.	Open up settings on your phone or computer.
1.	Navigate to your Wi-Fi settings.
1.	Look for the WLED SSID, default is "WLED-AP".
1.	Enter the password, the default is "wled1234".
1.	Once connected, you should automatically be re-directed to your LED strip.
1.	This gets you to the limited captive portal 'browser'.
1.	If not, open up a browser and navigate to 4.3.2.1.



## Configure a bootup effects sequence

1.	From the main screen, click on "TO THE CONTROLS!"
1.	Select the "Effects" tab.
1.	Select an effect mode, i.e. "Bpm".
1.	Adjust overall brightness, speed, and intensity/fade rate.
1.	Select the "Colors" tab.
1.	Select one of the palettes, such as "Beach".
1.	Select the "Favorites" tab.
1.	Select the "Saving mode" checkbox.
1.	Save to slot "1".
1.	Check the "Preset" cycle.
1.	Select the Config cog at the top right of the application display.
1.	Select "LED Preference".
1.	Check "Set current preset cycle setting as boot default" checkbox.
1.	Click on "Save" at the bottom of the screen.


## Reset the device

1.	Log in to the device. If you cannot log in, then you need to Reflash the device, which may default to AP mode.
1.	Select the Config cog at the top right of the application display.
1.	Select "Security and Updates".
1.	Check "Factory reset".
1.	Click on "Save & reboot".
1.	Reverts to the initial AP Mode and all other settings are gone.
