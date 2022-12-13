# Introduction
This version of WLED contains sound reactive routines, which are prefaced with a `* FX_NAME` for volume reactive routines and `** FX_NAME` for FFT routines. Each is controllable by the intensity and/or speed sliders. Some routines also include 3 dedicated FFT control sliders.

**Caveat: As our sound reactive fork of WLED evolves, some of this content may become out of date. We'll update as we become aware of any issues.

Contents:
* [HTTP API Links](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#http-api-links), [Updating FX.h](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#updating-fxh-line-numbers-will-vary), [Updating FX.cpp](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#updating-fxcpp)
* [WLED Support Functions](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#wled-support-functions)
* [Important WLED variables](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#important-wled-variables), [Important Structures](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#important-structures)
* [Delays in WLED](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#delays), [Displaying LEDs](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#displaying-the-leds), [FastLED](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#fastled), [2D Functionality](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#2d-functionality)
* [Variable Length Arrays](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#on-variable-length-arrays), [Using CRGB Color Space](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#using-crgb-color-space), [Using CHSV Colour Space](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#proposed---using-chsv-colour-space)
* [Non-Dynamically Created Variable Arrays](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#how-to-use-a-non-dynamically-created-variable-array)
* [Sound Reactive EEPROM Layout](https://moonmodules.github.io/WLED-Docs/WLEDSR/WLED-Programming-Notes#sound-reactive-eeprom-layout)

Caveat: Some information on this page is in our 'dev' branch only and not yet ready for prime time.

## HTTP API Links
I hope to work on an Android application in the future, so I'm keeping notes on the HTTP API.
* https://tynick.com/blog/01-28-2020/controlling-wled-with-raspberry-pi-using-the-wled-api/
* https://github.com/Aircoookie/WLED/wiki/HTTP-request-API

## Updating FX.h (line numbers will vary)

* Line 105 – Update the mode count.
* Line 250 - Added extern variables around line 250 of FX.h. These are defined in audio_reactive.h.
* Line 214 – Update the defines.
* Line 456 – Update the _mode.
* Line 697 – Update the mode definition and don’t forget , and ;
* Line 816 – Update the JSON entry. Can add an extra entry. No Spaces, 10 per line!!

## Updating FX.cpp

Append the new function(s) and use current functions as templates. Cannot add any functions without accompanying index entry. 

## WLED Support Functions
* `fade_out(uint8_t rate);`                 - This is CRITICAL!!!
* `blur(uint8_t blur_amount);`              - Can be useful.
* `color_wheel(uint8_t index);`             - This has history with NeoPixel library. I use palettes instead.

## Important WLED variables

* `SEGLEN`	              // uint16_t - Segment length.
* `_segment_index`            // uint8_t - Current segment being displayed.

* `SEGMENT.length`              // uint16_t - Segment length (but not for ESP8266 :^/ )
* `SEGMENT.intensity`          // uint8_t - You can use this from the slider.
* `SEGMENT.speed`              // uint8_t - You can use this from the slider.
* `SEGMENT.palette`            // uint8_t - Current palette. Otherwise SEGCOLOR(0) and SEGCOLOR(1).
* `SEGMENT.mode`             // uint8_t - Current mode.
* `now`			   // uint32_t – Millis counter.
* `SEGENV.call`		   // uint32_t – Counter each time a routine is called. Can be used for 'setup'.
* `SEGENV.next_time`           // uint32_t – Millis counter.
* `SEGENV.step`              // uint32_t - Counter each time a routine is called.
* `SEGENV.aux0`             // uint16_t   - Available for use as a SEGMENT specific persistent variable.
* `SEGENV.aux1`	           // uint16_t   - Available for use as a SEGMENT specific persistent variable.

## Important Structures

* FX.h:267 - Segment<value> aka SEGMENT
* FX.h:318 - Segment runtime.value> aka SEGENV
* FX.h:66  - Other stuff

## Delays
You DO NOT use delay statements here, except to keep the watchdog happy. Here is the awesome FastLED method of timing/scheduling (which DOES NOT work with segments):

```C
EVERY_N_MILLISECONDS_I(pixTimer, SEGMENT.speed) {
  pixTimer.setPeriod(256 - SEGMENT.speed);
  // Put your display code here.
}
```

Here's the standard blink without delay version:

```C
long lastTime = 0;
int delayMs = 2000;            // We want to do something every 2 seconds.

void userLoop()
{
  if (millis()-lastTime > delayMs)
  {
    lastTime = millis();
    //do something you want to do every 2 seconds
  }
}
```

## Displaying the LED's.
We were used to FastLED.show(). Well, no longer, and this has some disadvantages.

```C
CRGB myCol = ColorFromPalette(currentPalette, index, brightness, LINEARBLEND);
setPixelColor(myLED, myCol.red, myCol.green, myCol.blue);
```

The next line supports SEGCOLOR(0) and SEGCOLOR(1) if no palette (i.e. default) is selected:

```C
setPixelColor(i, color_blend(SEGCOLOR(1), color_from_palette(index, false, PALETTE_SOLID_WRAP, 0), pixBri));
```

where, `i` is the location, `index` is the color and `pixBri` is the brightness.

Now, onto the disadvantage. . The problem is that you can perform a `getPixelColor` and move it to another LED with `setPixelColor`. After moving to about 10 pixels, the LED is now black. This is because of the built-in scaling and addressing the memory that's used for DMA transfer. Unfortunately, we don't get a nice lossless `leds[location]` as we do with FastLED.



## FastLED

WLED uses the NeoPixelBus library to drive the LED's directly, however, a significant amount of FastLED functionality has been enabled in WLED. Things included:

* FastLED Math and trigonometry
* Noise
* Palettes
* Palette transitioning (use your own palette variables though)
* EVERY_N_MILLIS

What is NOT included:
* `FastLED.show()`
* FastLED pixel setup
* FastLED power management
* Working directly with the `leds[x]` array
* `fill_rainbow` and related routines that directly affect the array
* `fade`/`nscale`, you need to use the WLED equivalent

## On Variable Length Arrays

These will be used so that we can address leds[x] in our routines with the known and lossless FastLED method rather than the lossy NeoPixelBus method. We'll also be using these for ancillary functions, i.e. heat[x] as used in fire2012.

Since you cannot define variable arrays in C, we need other methods to do so for our functions.

The WLED method has been to malloc() some memory as follows:

```C
  if (!SEGENV.allocateData(SEGLEN)) return mode_static();
  byte *heat = SEGENV.data;
  heat[value] = 25;
```

For the 2D and FastLED data array functionality, the developers of this fork are not comfortable with the `malloc()` method of memory allocation and have decided to create large fixed arrays instead and to create pointers for use with variable-length arrays.

Already declared in FX.cpp:
```C
  uint32_t ledData[MAX_LEDS];    // Currently 1500 as defined in const.h. Used for conversion from NeoPixelBus to FastLED. RGB or RGBW.
  uint32_t dataStore[4096];     // For ancillary functions. Can use any data type.
```

### Using CRGB Color Space

```C
  CRGB *leds = (CRGB *)ledData;     // Define the pointer and override the default data type.
  leds[0] = CRGB::Red;
  leds[1] = ColorFromPalette(currentPalette, index, bright, LINEARBLEND);
```

### Display the CRGB Array

First, define a function and add to FX.h
```
void WS2812FX::setPixels(CRGB* leds) {
   for (int i=0; i<SEGLEN; i++) {
      setPixelColor(i, leds[i].red, leds[i].green, leds[i].blue);
   }  
}
```
You can now use FastLED address methods, AND it works with segments.

Then, you can call this function at the end of your routine as follows:
```
  setPixels(leds);
  return FRAMETIME;
} // End of your routine.
```

### Proposed - Using CHSV Colour Space

```C
   CHSV *leds = (CHSV *)ledData;
   leds[i]  = CHSV(25, 255,255);
```

### Proposed - Display the CHSV Colour Space
The `leds[]` array is already defined in the CHSV color space.

```C
    CRGB color;
    for (int i=0; i<SEGLEN; i++) {
      color = leds[i];
      setPixelColor(i, color.red, color.green, color.blue);
    }
```

### Current Use of the CHSV Colour Space
As used in one of the FFT animations (** Freqmatrix) in FX.cpp around line 4079.

```C
    uint32_t *leds = ledData;
    CHSV c;
    c = CHSV(20, 255, 255);
    leds[i] = (c.h << 16) + (c.s << 8)  + (c.v );
```

### Current Display of CHSV array

```C
    for (int i=0; i<SEGLEN; i++) {
      c.h = (leds[i] >> 16) & 0xFF;
      c.s = (leds[i] >> 8) &0xFF;
      c.v = leds[i] & 0xFF;
      color = c;
      setPixelColor(i, color.red, color.green, color.blue);
    }
```
### How to use a non-dynamically created variable array

We'll use that large dataStore array that was defined globally in FX.cpp. Although it was defined as a `unint32_t`, you can still use smaller dynamic arrays and override the data type using pointers with a function:

`uint8_t *myArray = (uint8_t *)dataStore;    // Just make sure you don't go over.`

You can now use it as a 1D or quasi 2D array, i.e.
```C
  myArray[5] = 4;                        // 1D array
  myArray[5*matrixWidth + 4] = 10;       // 2D array
```
# 2D Changes
We have implemented an advanced XY() function to support not only panels of varying sizes and orientations, but also for multiple (identical) panels.

Animations have been written so that the top left led in the panel(s) is, well, at the top left.

We do not (yet) have animation specific orientation settings. If you would like to do so, for any given 2D animation, you'll need to swap the parameters for the XY() function as well as changing the for loop parameter from height to width (or vice versa).

# Sound Reactive EEPROM Layout
We've expanded `EEPSIZE` in const.h to 4095 for ESP32 and 3300 for ESP8266 due to our additional requirements. We started saving values at 3072 defined as `EEP_AUDIO`. Although we'd like to apply SEGMENT specific settings, we may have some challenges with the FFT sliders. We're not sure at this point.

| Byte         | Data       |
| ----         | ----       |
| EEP_AUDIO    | Sound Squelch Setting
| EEP_AUDIO+1  | Audio Sync Port
| EEP_AUDIO+2  | Audio Sync Port
| EEP_AUDIO+3  | Audio Sync Enabled
| EEP_AUDIO+4  | FFT1 Slider Value
| EEP_AUDIO+5  | FFT2 Slider Value
| EEP_AUDIO+6  | FFT3 Slider Value
| EEP_AUDIO+7  | Begin 2D Matrix Values
| EEP_AUDIO+11 | End 2D Matrix Values
| EEP_AUDIO+12 | Input Gain Setting

### Presets in EEPROM
How do we store FFT slider values in EEPROM for WLED presets? WLED Presets are 20-byte blocks (slots) stored in EEPROM. There is space reserved in EEPROM for 25 slots from 400-899. Currently, 18 of the 20 bytes are being used by WLED. This presents a problem for us since, at the time of writing,  we have 3 bytes that we need to store for our FFT sliders. We didn't want to attempt to rewrite the entire WLED preset protocol as that would surely introduce unnecessary headaches.

To solve this problem, we reserved 25 5-byte blocks (slots) in EEPROM from 3175-3299. With the space in EEPROM allocated, we can now save/retrieve FFT slider data to/from WLED presets. 

| Byte | Data |
| :--: | ---  |
| 0    | FFT1 Slider Value |
| 1    | FFT2 Slider Value |
| 2    | FFT3 Slider Value |
| 3    | ZERO (Reserved)   |
| 4    | ZERO (Reserved)   |

### On Frame Rates

WLED limits the frame rate, and it's apparently because the LED's start flashing if the frame rate is too high. The standard for maintaining a consistent frame rate when writing any animations is to make sure you add to the end of your animation:

return FRAMETIME;

If you wish to increase the frame rate, have a look at fx.h with:

\#define MIN_SHOW_DELAY 15

Also, in fx_fcn.h, there's:

if (nowUp - _lastShow<MIN_SHOW_DELAY) return;

* Frametime is a constant, which is 1000/42. In order to increase the FPS, instead of return frametime, we can write a smaller value than that and for max speed simply go for return(0), which is the smallest.

### On Segments

Some animations may break when the users start implementing SEGMENTS. Issues encountered were:

* Triggers. A triggered event, which was reset by the animation. This does not work with SEGMENTS. One workaround is knowing that the MIN_SHOW_DELAY is 15, and then determine if now-original_event > MIN_SHOW_DELAY in order to reset the animation.
* To get the current segment being displayed, try Serial.println(_segment_index);
* To use persistent variable across SEGMENTS, don't use 'static', but rather use the existing uint16_t defined SEGENV.aux0 and SEGENV.aux1 variables. Too bad they're not uint32_t.
* For further reading on persistent variables, see this page https://moonmodules.github.io/WLED-Docs/WLEDSR/Persistent-Variables-and-WLED

Here's a replacement for EVERY_N_MILLIS()

```C
  uint8_t secondHand = millis()/(256-SEGMENT.speed) % 10;
  if (SEGENV.aux0 != secondHand) {
    SEGENV.aux0 = secondHand;
    <rest of code goes here>
  }
```

### getPixel and setPixel

In the FastLED world, we could cascade led information with things like:

```C
   leds[i+1] = leds[i];
```

That's not an option with WLED (unless you use the *ledData method described above), because it doesn't have the leds[] array. Instead, you have:

```C
  setPixelColor(i+1,getPixelColor(i)); 
```

The problem, however is that while the FastLED method preserves the original pixel information, the 'WLED' method is lossy, and eventually the cascaded led's will fade out entirely. The workaround, as previously shown, is to create an array used by the segment that preserves the LED information. AirCoookie's method is to allocate memory on the fly for this. For instance:

```C
  if (!SEGENV.allocateData(SEGLEN)) return mode_static(); // allocation failed
  SEGENV.data[SEGLEN-1] = 0;                              // a byte value
```


If you want, you can give it another name with:

```C
  if (!SEGENV.allocateData(SEGLEN)) return mode_static(); // allocation failed
  byte* heat = SEGENV.data;
  heat[SEGLEN-1] = 0;                                     // a byte value
```

You now have SEGENV.data[SEGLEN] allocated for your use. Adding a structure for use with your segment is a whole other level of complexity and can be found by examining mode_multi_comet and mode_oscillate among others. Just search for SEGENV.allocateData in FX.cpp.


