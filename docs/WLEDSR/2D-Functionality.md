## 2D functionality
* An `XY()` function which returns the index number of the X-Y coordinate on the matrix has been added.
  * The origin (x=0,y=0) is at the top left of the display, with X axis extending to the right, Y axis toward the bottom.
  * The LED order starts from 0 at the top left, and ascends to the right on the top row.
  * 2D addressing is leds[XY(column, row)]
* A serpentine/zig-zag setting has been added to 'LED Settings'.
  * With serpentine mode enabled, the led index on every odd row (top row is row 0) is ascending from right to left, and on even rows is ascending from left to right
  * The opposite of serpentine is "progressive", where all rows are oriented in ascending order from left to right

As documented in [FastLED](https://github.com/FastLED/FastLED/blob/master/examples/XYMatrix/XYMatrix.ino), leds[0] should end up being at the top left of your array:

```
Don't enable serpentine setting if your pixels are
laid out all running the same way, like this:

    0 >  1 >  2 >  3 >  4
                        |
    .----<----<----<----'
    |
    5 >  6 >  7 >  8 >  9
                        |
    .----<----<----<----'
    |
   10 > 11 > 12 > 13 > 14
                        |
    .----<----<----<----'
    |
   15 > 16 > 17 > 18 > 19

Enable serpentine setting if your pixels are
laid out back-and-forth, like this:

    0 >  1 >  2 >  3 >  4
                        |
                        |
    9 <  8 <  7 <  6 <  5
    |
    |
   10 > 11 > 12 > 13 > 14
                       |
                       |
   19 < 18 < 17 < 16 < 15

```

* `matrixWidth` and `matrixHeight` are new 'LED Settings'.
  * `matrixWidth` is the number of pixels per row.
  * `matrixHeight` is the number of pixels per column.
* Some existing animations (as of Jan 2021) were coded for different orientations and need to be redone to match the newly agreed to orientation described above.
  * It's likely that there will at least a minor change in animations required to support a non-rectangular or non-contiguous mapping.

### XY() routine update

The dev branch has a new XY() function (thanks Sutaburosu) in FX.cpp, which supports multiple layouts.

There are 5 orientation flags as follows:


*  SERPENTINE - Select if your layout is serpentine. Otherwise, it's not.
*  ROWMAJOR   - Select if your layout is horizontal. De-select if it's vertical.
*  FLIPMAJOR  - Flip the major axis, ie top to bottom if it's a horizontal layout.
*  FLIPMINOR  - Flip the minor axis, ie left to right if it's a horizonal layout.
*  TRANSPOSE  - Swap the major and the minor axes (otherwise no swap). Don't use on non-square.

By comparison, the author's aliexpress purchased 16x16 array needs to be configured as:

```
Serpentine | Rowmajor | Flipmajor
```

**Note:** When an X,Y value goes out of bounds, this routine writes to an LED beyond SEGLEN, and as a result, we need to use the setPixels() routine to write to the display.

**Note:** Working with this can be confusing, so here's a simulator you can play around with to get familiar with[ XY()  at Wokwi](https://wokwi.com/arduino/projects/298774787561357832).

### Multiple panels (202106/dev)
When you want to create larger matrices, the standard available panels are not big enough. They typically are 16x16 or 8x32 pixels. To support large matrices, they should be connected together. This is now supported in WLED SR (currently in dev version). Multiple panels can be specified in the LED-Preferences screen by checking Multiple Panels and then defining the number of horizontal and vertical panels. First panel should be top left, extending to the right, the extending down, until bottom right.

For example if you create a 32x32 matrix by connecting 4 8x32 panels together you have 4 horizontal panels and 1 vertical panel. Alternatively if you have 4 16x16 panels, you have 2 horizontal and 2 vertical panels. In the latter case, panel ordering is:

0   1

2   3

The XY() function supports this by first determining in which panel an (x,y) coordinate should be displayed and then within a panel it's position is determined as described above (using flipmajor, serpentine etc.).

In the 8x32 example above, 0<x<8 is displayed in the first panel, 8<x<16 in the second panel and so on. For each panel, the first led number is calculated. E.g. if each panel has 256 leds then the second panel first led is led[256]. The values of x and y are then corrected by the width and the height of the panel to find the place within the panel (major and minor values)