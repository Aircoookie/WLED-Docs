---
title: Virtual LEDs via DDP
hide:
  # - navigation
  # - toc
---

# Overview

Docs in process...

Virtual LEDs allow you to "attach" LEDs from multiple ESPs to a main, controlling ESP. These LEDs can be added to an ESP just like physical pins in Config, LED Preferences. Choose one ESP to be the main then add the others to it by adding a pin, selecting DDP RGB (Network), entering the Length (number of LEDs on that remote ESP), then enter the ESPs IP address.

Note: The controlling ESP must be running at least 0.13 firmware while the remotes can be older. As usual, best perfomance is obtained by using an ESP32 for the controlling device. You can use an ESP8266, but only with a small number of LEDs (<300).
