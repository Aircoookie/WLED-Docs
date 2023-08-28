---
title: 2D and 1D Mixed Setup
hide:
  # - navigation
  # - toc
---

## Overview

WLED  supports mixing 2D and 1D setup on the same unit , the expected result is that you could use 2D fixture  and still chain a strip to the start or end of a matrix .

Setup your leds count in  Config, LED Preferences as ususal , for example 16x16 matrix and a strip of 30 pixles chaind at the end of your matrix  , total count should be 256 + 30 =286 

Go to  Config , 2D setup page and create a 16x16 matrix ,and then go to the segments ( the 16x16 segments should be created automaticaly 
DDP RGB (Network) as the LED type and enter the Length (number of LEDs on that remote ESP), then enter the ESPs IP address.

Multiple remote ESP's can be setup this way.

Note: The controlling ESP must be running at least 0.13 firmware while the remotes can be older. As usual, best perfomance is obtained by using an ESP32 for the controlling device. You can use an ESP8266, but only with a small number of LEDs (<300).

<img width="448" alt="image" src="https://user-images.githubusercontent.com/91013628/214262598-e7ce0907-ccad-4370-9d02-918efd20577c.png">

Also, support was recently added for ArtNet virtual LEDs.
