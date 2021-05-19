Starting in WLED 0.9.0, Segments are supported.

This feature allows you to set different zones on the LED strip, each running a different effect or color.

A segment is selected if the checkmark next to the segment number is checked. Changes you make to color or effects will apply to all selected segments. The color/effect that is shown in the web UI is that of the first selected segment.

There is one _main segment_, Segment 0 by default. This segment has a few important differences to the rest of the segments.
- Color transitions only work on the main segment
- The main segment's color is the one that will be reported to HTTP and MQTT APIs

Tip: If you divide your strip into two segments, reverse the second one and select both, you can achieve very nice symmetrical effects!

Segment 0 has a Start LED of 0 and a Stop LED equal to the LED Count you defined in Configuration, LED Preferences. _The Stop LED is **not** included in the Segment._ Currently you can create a maximum of 10 segments.  Presets 1-15 use only Segment 0 by default.  Preset 16 is the only Preset that saves settings for Segments 1-10.

To display segment information select the down arrow in the Segment box.  To add a Segment select “+ Add Segment”.  Enter the Start and Stop LED as appropriate.  Grouping and Spacing control the organization of the LEDs within the selected effect.  To reverse the direction of an effect select Reverse Direction.  To delete a Segment select the trash can.  To save your Segment settings select the checkmark to the right of the Start and Stop LED numbers.

## Grouping and Spacing
When an effect changes the color of one LED, it is really changing the color of one LED group. Since the default group size is one, the effect normally only changes a single LED. When Grouping is set to two, the effect will light two LEDs using the same color. The two LEDs are treated as a single _virtual_ LED. 

To illustrate this, we can create a segment with 12 LEDS (physically referred to as LED 0 to LED 11) and select an effect that repeats three colors. When Grouping is set to one we see a repeating pattern of one red LED, one blue LED, and one green LED. When Grouping is set to two the segment of 12 physical LEDs becomes a segment of 6 virtual LEDs (virtualLED 0 to virtualLED 5). The same effect will now set the color of each virtual LED (which consists of two physical LEDs). The pattern becomes two red LEDs followed by two blue LEDs then two green LEDs.

|Setting|LED Output|
| :---: | --- |
|Grouping 1<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G1S0A.png)|
|Grouping 2<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G2S0Virtual.png)|

As the pattern cycles, the group of LEDs will move together.

|Setting|LED Output|
| :---: | --- |
|Grouping 1<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G1S0Cycle.gif)|
|Grouping 2<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G2S0Cycle.gif)|

Spacing controls the space or gap between LEDs. The default spacing is zero, so normally there is no space between LEDs. When Spacing is set to one, every other LED will be lit. The number of _virtual_ LEDs in the strip will be half the number of physical LEDs.

Again, we can create a segment with 12 LEDS (physically referred to as LED 0 to LED 11) and select an effect that repeats three colors. When Spacing is set to zero we see a repeating pattern of one red LED, one blue LED, and one green LED. When Spacing is set to one the segment of 12 physical LEDs becomes a segment of 6 virtual LEDs (virtualLED 0 to virtualLED 5). The same effect will now set the color of each virtual LED (which consists of the even numbered physical LEDs). The pattern becomes one red LED followed by a blank LED, one blue LED followed by a blank LED, then one green LED followed by a blank LED.

|Setting|LED Output|
| :---: | --- |
|Grouping 1<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G1S0A.png)|
|Grouping 1<br /> Spacing 1|![](https://github.com/twlare/WLEDDocs/blob/master/G1S1Virtual.png)|

As the pattern cycles, only the virtual LEDs will be lit - the blank LEDs in between the virtual LEDs will always be off.

|Setting|LED Output|
| :---: | --- |
|Grouping 1<br /> Spacing 0|![](https://github.com/twlare/WLEDDocs/blob/master/G1S0Cycle.gif)|
|Grouping 1<br /> Spacing 1|![](https://github.com/twlare/WLEDDocs/blob/master/G1S1Cycle.gif)|

Grouping and Spacing can be combined to create many different custom LED layouts. In the example below, the strip of 12 physical LEDs has been configured to function as four virtual LEDs with a small gap between them.

|Setting|LED Output|
| :---: | --- |
|Grouping 2<br /> Spacing 1|![](https://github.com/twlare/WLEDDocs/blob/master/G2S1A.png)|
|Grouping 2<br /> Spacing 1|![](https://github.com/twlare/WLEDDocs/blob/master/G2S1Cycle.gif)|

