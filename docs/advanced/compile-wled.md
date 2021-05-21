---
title: Compile WLED
hide:
  # - navigation
  # - toc
---

A lot of people ask how they can compile their own WLED .bin file, whether it be for a custom pins or analog LEDs, so this picture guide will show how to do it.

First, download the latest source code from [https://github.com/Aircoookie/WLED](https://github.com/Aircoookie/WLED) under the `Code` dropdown menu.

![](https://i.ibb.co/2hnGhyb/Screen-Shot-2020-11-03-at-5-25-18-PM.png)

Then download, install and open VSCode (https://code.visualstudio.com/download) and install the PlatformIO IDE extension from the VSCode Settings > Extensions menu.

![](https://i.ibb.co/SNv8TtH/Screen-Shot-2020-11-03-at-6-27-58-PM.png)

After PlatformIO IDE is installed, restart VSCode and open your unzipped WLED source code folder.

![](https://i.ibb.co/pXs1G0j/Screen-Shot-2020-11-03-at-5-27-03-PM.png)
![](https://i.ibb.co/10ykGxk/Screen-Shot-2020-11-03-at-5-27-17-PM.png)

Now you need to find which GPIO pins go to which color and make these adjustments in your code.

* PWM1 - Red
* PWM2 - Blue
* PWM3 - Green
* PWM4 - White1
* PWM5 - White2

The best place to find your pins is the Tasmota device repo. https://templates.blakadder.com 

![](https://i.ibb.co/51k3ck2/Screen-Shot-2020-11-03-at-7-43-25-PM.png)

Above you can see which GPIO pin goes to each PWM channel.

Insert this information into the `NpbWrapper.h` file back in VSCode.

![](https://i.ibb.co/tpHgGRx/Screen-Shot-2020-11-03-at-5-30-36-PM.png)

Now you can adjust your build flags in the `platformio.ini` if you want to enable our disable certain things. 

![](https://i.ibb.co/wQKNcwk/Screen-Shot-2020-11-03-at-5-32-20-PM.png)

Now click the PlatformIO logo in the left side bar and find `env:esp8285_4CH_MagicHome` and then click `General` > `Build`

![](https://i.ibb.co/rbB9vLy/Screen-Shot-2020-11-03-at-5-32-57-PM.png)
![](https://i.ibb.co/30sRrDM/Screen-Shot-2020-11-03-at-5-33-25-PM.png)

It will probably fail the first time. Just click build again.

![](https://i.ibb.co/WGPcNnn/Screen-Shot-2020-11-03-at-5-35-28-PM.png)

It might fail again. Third times a charm.

![](https://i.ibb.co/727JZKx/Screen-Shot-2020-11-03-at-5-35-48-PM.png)

There we go!

![](https://i.ibb.co/QdW361W/Screen-Shot-2020-11-03-at-5-36-18-PM.png)

The .bin file is located in a hidden folder called `.pio` in your WLED folder. Since it's in a hidden folder you have to move it out to use it.

All that's left to do is flash this .bin file onto your esp chip and then connect it to wifi. 

Here's a good video tutorial on how to flash a MagicHome controller like the one pictured above. https://www.youtube.com/watch?v=qgBAU39v07k 

You just need to use the `firmware.bin` instead. 

![](https://i.ibb.co/bdj0WNb/Screen-Shot-2020-11-03-at-5-38-43-PM.png)

I prefer to use ESPHome-Flasher just because that's what I've had the best luck with. https://github.com/esphome/esphome-flasher/releases