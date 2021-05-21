---
title: Wiring Pro Tips
hide:
  # - navigation
  # - toc
---

# Overview

RGB LEDs can draw a lot of current (amps). While most people usually worry about the dangers from high voltage, low voltage + high amperage can be dangerous too, as it can easily become [a fire hazard in certain circumstances](https://youtu.be/nWC0PkHB8O4). Depending on your setup size (the number of LEDs you want to drive), use these tips to help guide your wiring.

There are plenty of guides out there to help with [power supply selection](https://quinled.info/2018/10/03/power-supply-selection/), which is out of scope of this page. Size your power supply to your installation both up and down, so you both provide them with enough current and don't introduce unnecessary risk. It's better to power 30 LEDs from a 10W (2A @5V) power supply than a 100W power supply, as you don't need to worry about the potential for as much energy flowing through small wires.

As you increase the number of LEDs, you increase the amps your power supply will need to be able to provide. The more amps you're working with, the more you need to be cautious about your wiring and [fusing](https://quinled.info/2019/02/18/use-fuses-for-increased-safety/).

For example, if you want to power your LEDs off a sealed lead acid battery (e.g. a car battery), you need to be very careful about current. These kinds of batteries can supply hundreds of amps, so you need to ensure that you use fuses along the way to protect against shorts. If you're using USB pocket chargers on the other hand, they tend to be current limited (most provide only 1-2A max) so you can worry less about fusing there.

Make sure to also check out this [great list of resources to help you learn](/basics/tutorials)!

# Small Setups (< 30 RGB LEDs)

WLED has a great built-in automatic current-limiting feature, set to 850mA by default. If you have a very small setup (< 30 LEDs), you can use this feature to help simplify your wiring and keep things safe.

In most circumstances, it's best to power your LED strip directly from the power supply and wire power to your WLED control board in parallel.

{insert diagram here}

With the current limiting feature turned on and for very small setups (on the smaller side of 1-30 LEDs), you can power the LED strip directly through the USB port of D1 mini or similar board. That is, power comes in to the control board through the USB port and out to a 5V pin. Each board will be a little different, so it would be wise to verify that you can do this for your specific board. You want to ensure that there are no voltage regulators, diodes, or other components between the 5V pin and the USB port input that are going to be damaged by the high-current draw of the LEDs. You also want to ensure that any PCB traces are big enough that they don't heat up with increased current. Never try to draw more than 1A through a board's USB port like this; the boards really aren't designed for large amounts of current to flow through them.

When using this technique, make sure to add strain relief to your wires so that they don't flex and break. The easiest way to do this is to use hot glue. While you want to use plenty of hot glue, just be careful to not cover any components that are going to get hot with hot glue.

# Medium Setups (30-300 RGB LEDs)

For a medium-sized setup of 30-300 LEDs, you should find a power supply that can provide enough current (see the link above) and make sure to power the strip directly. For setups with more than 150 LEDs, you should consider power injection.

## Power injection

Power injection is where you connect multiple wires from your power supply to the strip in multiple places, usually once at the beginning and once at the end. This is needed because the LED strips can only pass a small amount of current through them and you need to ensure that all your power-hungry LEDs get fed enough power. If your LEDs are dim or discolored at one end of the strip, you should add power injection.

When doing power injection, make sure your [wires are rated](https://www.powerstream.com/Wire_Size.htm) for the amperage you wish to send over them. You should also check the [voltage drop](https://www.calculator.net/voltage-drop-calculator.html) if you're doing a particularly long run. As a rough guide, you should never use anything thinner than 22AWG wire for power injection.

For medium-sized setups, you should add fuses if your power supply is over 100W. Considering an inline fuse on each power injection line.

## Inline Fuses

![Inline fuse](https://images-na.ssl-images-amazon.com/images/I/61Pe89yvIRL._AC_SL1000_.jpg)

You should place the fuse as close to the power supply as possible, on the positive lead, so that as much of the current flows through it as possible. That will cause the fuse to blow if the power injection line shorts or if the strip shorts, instead of causing your power injection wire or strip to heat up. Buy a fuse that's rated just over what you expect your LED strip to draw. For example, if you calculate that your LEDs will draw at most 4.5A, buy a 5A fuse.

First match your power injection wire size with the inline fuse's wire. If the inline fuse comes with 16AWG wire (it's usually printed on the wire itself in small type), you should use 16AWG or thicker wire for your power injection wire. If you use thinner wire, you weaken the utility of the inline fuse and risk your power injection wire heating up in the case of a failure.

To wire in an inline fuse, trim back the positive wire (not ground) of your power injection line enough to allow the inline fuse to be spliced in. Place a cut of heat-shrink tubing over the wire so that the cable can be insulated once your solder joint is complete. Strip and bend both wires of your splice so that they create hooks to mechanically reinforce the joint, then solder. Cover with the heat-shrink tubing and you're done! Now you have a beautiful, professional-looking fused power injection line.

# Larger Setups (300+ RGB LEDs)

The more power you're working with, the more you need to be careful about your wiring. If you're using a 150W or higher power supply or multiple power supplies, check out these tips:

## Wire ferrules

If you're using stranded wire and lever-lock or screw terminals, all your wire → terminal connections should be terminated with [a wire ferrule](https://blog.delcity.net/what-is-a-wire-ferrule/) of the appropriate wire gauge.

This is because stranded wires can splay and lose tension over time, creating a weaker connection that could lead to sparking. Loose strands can also cause shorts or break off. The same is true for tinned stranded wires: the solder can deform (especially if it's heated), loosening the screw terminal, and cause a weaker electrical connection or complete failure. That said, untinned stranded wire in a screw terminal actually creates a better connection than tinned stranded wire, so for high current applications where they could possibly heat up, don't tin them if you don't have ferrules.

Shrouded wire ferrules also act as strain relief, minimizing mechanical damage if the wire moves at all. This is especially important for any installations that are mobile, could experience vibrations, or are installed/removed seasonally.

## Multiple power supplies

When doing power injection with multiple power supplies never mix two power supplies on the same LED strip. You can connect grounds together, just never the positive rails. This means you need to segment your LEDs based on power supplies, including your power injection. For the same reasons listed below, never connect multiple power supplies to the same strip for power injection purposes, always fork one power supply and route it to the start/mid/end of the same strip.

Because multiple power supplies could have subtle variations in their positive voltages (e.g. 12.1V and 12.3V), this could lead to power flowing in ways that aren't expected or which could be damaging to your equipment. In general, wired power supplies don't like to be directly connected to other power supplies unless they are explicitly designed for that purpose. This is not true for cell batteries, which are usually fine with being connected in parallel provided all the battery voltage + chemistry are the same.

## Even more tips

  * Always check [wire gauge + amp ratings](https://www.powerstream.com/Wire_Size.htm) and make sure to overcompensate by 2-3×
  * more, lower-current wires are better than fewer, higher-current wires
  * Ensure that all strips are fused just above their max current. Fuses should be located as close to the power supply as possible.
  * Make sure all distribution wires are neat, tidy, and mounted to a structure. If it needs to be loose to bridge an air gap, minimize the amount of dangling wire as much as possible. This ensures that if you were to have a wire become disconnected, it'll be easy to see where it is.
  * Did you add fuses? Add fuses. Seriously.