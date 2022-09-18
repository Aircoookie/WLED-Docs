---
title: Long Data lines
hide:
  # - navigation
  # - toc
---

# Long Data Line configurations

Addressable LEDs are controlled over a data line(s) based on 5V TTL (Transistor-Transistor-Logic) signals.  Over long distances (> 5m) keeping those signals "clean" and well defined for the LED they're meant to drive can be difficult.  While there are many methods used to get good results over 10m and longer runs (in-line resistors, voltage boosters, sacrificial pixels, etc.) they are often problematic and unreliable.
There is a method specifically designed to send high speed (~1Mhz) TTL data over long (10's to 100's of meter) distances: using a differential pair.

Commonly known as RS485, differential pair transmission for LED's takes the single data line from your MCU (ESP32, ESP8266, etc) and translates that into a differential signal that is sent across **two** wires instead of one.  A transmitter unit (Tx) at the MCU takes in the single data signal and outputs 2 lines usually called A+ and B-.  At the LED strip a matching receiver unit (Rx) takes the A+, B- signals as inputs and outputs clean and accurate 5V LED data that can directly feed the strip.  The only thing that needs to connect the TxRx pair is a pair of wires and a common ground.  The wires don't carry much current at all (~50mA) and can often be a light wire pair from a length of Cat5e or 22/4 alarm wire.

![Diff_Pair_Diag_Reduc](https://user-images.githubusercontent.com/13357571/187837079-bdbaabf4-71b9-4735-af9d-fa4675158298.jpg)

The distance between the Tx and Rx devices can easily be 30m.  With Cat5e UTP wire you can reliably reach 150m or more.

Note, there is no need for a level shifter with the Tx module.  Typical transmitters are spec'd for a minimum 2.4V High level input which is well within the output range of a 3.3V MCU.
The only other thing to note about the TxRx pair is that they usually require 5V to operate and often have a 120 ohm termination resistor across the A+,B- connections. Those resistors are important to maintain the integrity of the transmitted data.

A TxRx pair can also be used in the middle of a run of LED's when the distance to the next strip is long.  Just put a Tx unit at the end of the first strip and the Rx unit at the start of the next strip.

The individual Tx and Rx units are fairly inexpensive and can found on Amazon or via Aliexpress usually for less than $2 USD each (try "RS485 TTL interface").


