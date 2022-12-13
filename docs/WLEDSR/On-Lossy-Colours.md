## Issue
The following code moves the pixels down the line, but as it gets to the end, the intensity decreases significantly:

`setPixelColor(i, getPixelColor(i-1));`

## Explanation

`getPixelColor()` is lossy, whereas `setPixelColor()` perfectly sets the intended color. Unfortunately, the raw pixel memory buffer is also lossy, since it has to save the values scaled by master brightness. And unfortunately, if you do `s = x\*b /255`, later doing `x = s\*255/b` won't yield exactly the same result (thanks integer division). To solve this problem, we would need a secondary pixel data buffer.

See: [https://github.com/Aircoookie/WLED/issues/820](https://github.com/Aircoookie/WLED/issues/820)

## Workarounds
As a workaround, you could allocate memory for each function on the fly as a double buffer and use that, or you could hard code an array. Either way, you need to double up on the memory requirements and that is extremely limited with the ESP8266  and not recommended for that platform.

### Allocate memory
```C
if (!SEGENV.allocateData(SEGLEN)) return mode_static();  // Allocation failed
byte* myVal = SEGENV.data;                               // Could also be an int or long or whatever.
```
In this case, we are using that byte defined array for some function, but NOT to store full color values.
You could then refer to `myVal[0]` up through `myVal[SEGLEN-1]` within the routine for that function.
You could also define a `long`, then allocate the memory for it, and then store your colors in the array until you need to transfer them to the NeoPixel buffer at the end of your routine. See the transfer code below.

One problem with dynamic memory allocation at the firmware level is that it can become segmented and fail.

### Hard-coded array

First off, I would encapsulate ALL of this with `#ifndef` statements because you can't guarantee memory available on an ESP8266. In FX.cpp, you would define globally:

```C
#ifndef ESP8266
uint32_t ledData[1500];  // Or whatever value.
#endif
```
Similarly, you would encapsulate all functions and definitions that support that array. In the (encapsulated) animation, you would do the following:

```C
uint16_t WS2812FX::mode_myMode(void) {

#ifndef ESP8266

  uint32_t* leds = ledData;

// PERFORM ANIMATION MAGIC HERE!!

  for (int i = SEGLEN; i > 0; i--) {   // You can shift LED's the FastLED way.
    leds[i] = leds[i-1];
  }

  for (int i= 0; i < SEGLEN; i++) {    // Now send to the NeoPixelBus array
    c.h = (leds[i] >> 16) & 0xFF;
    c.s = (leds[i] >> 8) &0xFF;
    c.v = leds[i] & 0xFF;
    color = c;                         // Implicit conversion to RGB supplied by FastLED
    setPixelColor(i, color.red, color.green, color.blue);
  }
#else
// DO SOMETHING ELSE IF YOU WANT. Maybe a fade_out(32);
#endif

  return FRAMETIME;
} // mode_myMode()
```