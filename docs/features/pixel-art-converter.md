---
title: Pixel Art Converter
hide:
  # - navigation
  # - toc
---

The Pixel Art Converter tool aims to make it easier to show pixelart on a LED matrix panel, by converting any image to 2D pixelart and send it to the WLED device.

## Installation approaches

There are two ways to install the pixel art converter:

1. Local web browser. Will a web page run on the local machine connecting to the WLED device but will require to fetch an extra file. Supported from WLED release [v0.14.0-b1](https://github.com/Aircoookie/WLED/blob/main/CHANGELOG.md#wled-release-0140-b1) or later
2. Include the pixel art converter in the binary and compile from source. Allows access the pixel art converter on any device that have a connection to the WLED device. Supported from WLED release [v0.14.0-b2](https://github.com/Aircoookie/WLED/blob/main/CHANGELOG.md#build-2301240) (PR [#3042](https://github.com/Aircoookie/WLED/pull/3042))

### Approach 1: Local Browser
The instruction for the pixel art generator is best described in the original repository under "Basic Operations": [https://github.com/werkstrom/WLED-PixelArtConverter/](https://github.com/werkstrom/WLED-PixelArtConverter/).

### Approach 2: Include Pixart Converter in build files
!!! warning "Compilation required"
	Compiling WLED from source is required. Follow the instructions on [compiling WLED](advanced/compiling-wled) in order to do this.

1. Set the flag `#define WLED_ENABLE_PIXART` in `./WLED/wled00/my_config.h`
2. Compile and flash the binary to the ESP board
3. Power on board and connect via WiFi using the [default login](basics/getting-started/)

## Setup 2D matrix
2D LED panels are natively supported by WLED, but needs some configuration for the software to show the 2D grid correctly.

1. Head into the `2D Configuration` settings menu
2. Set the option "Strip or panel" to `2D Matrix`
3. Setup rest of the LED panel layout according to the specifics of your LED panel

!!! tip "Serpentine option"
	Setting the serpentine LED panel option incorrectly can lead to very confusing results that looks almost correct but no quite. Enabling or Disabling the option depends on the build style of the 2D matrix


## Usage
The Pixel Art Generator does not yet have link in the WLED front-end, therefore head over to the web page: `http://[device_ip_address]/pixart.htm`  (default IP-address [link](http://4.3.2.1/pixart.htm)).

On the web page:

1. Set the option "LED setup" to 2D matrix or serpentine accordingly.
2. Select an image that should be showed on the matrix display

	![16x16 pixel happy Akemi](../assets/images/ui/akemi/043_16_cheerful.png)

	This example uses a 16x16 pixel, happy version of the the WLED mascot Akemi by [Aircoookie](https://github.com/Aircoookie/Akemi).

3. A preview is displayed further down the web page.

	!!! tip "Scaling option"
		It can help to use the `Scale image`  option, depending on the image size used.

	![Pixel Art Generator output preview](../assets/images/content/043_16_cheerful_pixart_output.png)

4. Click on "Send to device" to push the generated image to the WLED device.