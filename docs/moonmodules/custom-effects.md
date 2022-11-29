---
title: Custom Effects
hide:
  # - navigation
  # - toc
---


![unknown](https://user-images.githubusercontent.com/91616163/197343053-f7deb257-5fd3-40f2-8ffd-31c06f02f12a.png)

## Custom effects

Custom effects are effects which are not compiled in the WLED repository but specified by a file (program file) which is interpreted in real time.

The big advantage of this is that effects are not limited by what is made by WLED programmers but anybody can create effects without releasing a new version of WLED. Furthermore any change in the effect code is instantly shown on leds allowing fast developing of effects.

A disadvantage is that the file needs to be loaded, examined and then run in real-time which is 'per definition' slower then pre-compiled code, although performance is promising already and will get better over time.

## Quick start
To get your first Custom Effect running, perform the following steps

* In tab effects, select '⚙️ Custom Effect'

![Custom effect](https://github.com/MoonModules/WLED-Effects/blob/master/Images//CustomEffect.PNG?raw=true)

* In tab Segments, give the segment a name, this will be the name of the Custom Effect

![Segment name](https://github.com/MoonModules/WLED-Effects/blob/master/Images/SegmentName.jpg?raw=true)

* Click on Custom Effect Editor

![Segment name](https://github.com/MoonModules/WLED-Effects/blob/master/Images/CustomEffectsEditor.PNG?raw=true)

* Click on Download wled.json to enable Custom Effects for WLED (needed each time a new version of CE is published)
* Click on Load template to get a 'hello world' example
* Press save and the template will be executed

## Running examples

Custom Effects examples are stored in [Github repository](https://github.com/MoonModules/WLED-Effects/tree/master/CustomEffects/wled)

If you develop effects which you want to share, ask for access on Github.

These effects can be loaded easily within WLED: Give a Custom Effects segment name the same name as an effect in this repository (case sensitive, without .wled), click on Custom Effect Editor and click Download 'effect'.wled and press Save.

Alternatively, if you want all the effects in this folder at once, go to the Custom Effect Editor and click Download presets.json (Segment stop is set to 50! This will overwrite any existing presets you have). Refresh the WLED page or reboot to see the new presets.

![Examples presets](https://github.com/MoonModules/WLED-Effects/blob/master/Images//ExamplesPreset.PNG?raw=true)

## Create your own Custom Effects

A Custom Effects program typically looks like this:

![Example](https://github.com/MoonModules/WLED-Effects/blob/master/Images/Custom%20Effects%20program%20example.PNG?raw=true)

A program contains structures like if statements, for loops, assignments, calls (e.g. renderFrame) etc., commands like setPixelcolor and variables like ledCount.

### Components
* program: Once every effect. Can contain global variables and internal functions. There are 2 special internal functions: renderFrame and renderLed

* Global variables: Once every effect, reused between functions. Variables (global and local) are defined by using an assignment e.g. t=0

* renderFrame: Once every frame

* renderLed: Once every led within a frame

### Functions and variables

Functions and variables give access to the WLED functionality. The list of functions and variables will grow as we go.
A function has parameters (even empty parameters) e.g. setPixelColor(x,y), variables haven't e.g. ledCount.

#### WLED general

    "ledCount": {},
    "setPixelColor": {"pixelNr":"int", "color":"int"},
    "leds": {},
    "setPixels": {"leds": "array"},
    "hsv": {"h":"uint8", "s":"uint8", "v":"uint8"},

    "setRange": {"from":"uint16", "to":"uint16", "color":"uint32"},
    "fill": {"color":"uint32"},
    "colorBlend": {"color1":"uint32", "color2":"uint32", "blend":"uint16"},
    "colorWheel": {"pos":"uint8"},
    "colorFromPalette": {"index":"uint8", "brightness":"uint8"},

    "segcolor": {"index":"uint8"},
    "speedSlider": {"return":"uint8"},
    "intensitySlider": {"return":"uint8"},

#### WLED SR
    "beatSin": { "bpm":"uint16", "lowest":"uint8", "highest":"uint8", "timebase":"uint32", "phase_offset":"uint8"},
    "fadeToBlackBy": {"fadeBy":"uint8"},
    "iNoise": {"x":"uint32", "y":"uint32"},
    "fadeOut": {"rate":"uint8"},

    "custom1Slider": {"return":"uint8"},
    "custom2Slider": {"return":"uint8"},
    "custom3Slider": {"return":"uint8"},
    "sampleAvg": {"return": "double"},

#### Custom Effects
    "counter": {"return": "uint32"},

    "shift": {"delta": "int"},
    "circle2D": {"degrees": "int"}, 

#### Math
    "constrain": {"amt":"any", "low":"any", "high":"any"},
    "map": {"x":"int", "in_min":"int", "in_max":"int", "out_min":"int", "out_max":"int"},
    "seed": {"seed": "uint16"},
    "random": {"return": "uint16"},
    "sin": {"degrees": "double", "return": "double"},
    "cos": {"degrees": "double", "return": "double"},
    "abs": {"value": "double", "return": "double"},
    "min": {"value1": "double", "value2": "double", "return": "double"},
    "max": {"value1": "double", "value2": "double", "return": "double"},

#### Time
    "hour": {"return":"uint8"},
    "minute": {"return":"uint8"},
    "second": {"return":"uint8"},
    "millis": {"return": "uint32"},

#### Pixelblase support
    "time": {"inVal":"double", "return": "double"},
    "triangle": {"t":"double", "return": "double"},
    "wave": {"v":"double", "return": "double"},
    "square": {"v":"double", "t":"double", "return": "double"},

#### Serial output
    "printf": {"args": "__VA_ARGS__"}

#### Details
* ledcount: number of leds within(!) a segment 
* setpixelColor: currently the second parameter is color from palette!
* leds: one or 2 dimensional array: One index for led strips and 2 indexes for panels. If the leds variable is used an implicit setPixels(leds) will be done each frame! 
* shift: shift all leds left or right (using delta)
* circle2D: puts a dot on a circle using the angle. Used to show a 2D clock, see clock2D.wled
* random: 16 bit random nr
* sin/cos: value between -1 and 1
* hour/minute/second: current time (set in time preferences)
* printf: currently no real printf: prints numbers, max 3

### Implementation of variables and functions

All variables and values are internally stored as doubles and where needed converted to (unsigned) integers, e.g. to WLED functions or operators like %.

Technical details about external variables and functions can be found in arti_wled.h. Look for arti_external_function, arti_set_external_variable and arti_get_external_variable. Some examples:

![Function implementation](https://github.com/MoonModules/WLED-Effects/blob/master/Images/Function%20implementation.PNG?raw=true)

## Current limitations

* Only 1 segment
* no unary operators like - (use 0-1) and ++, --
* no strings


## trouble shooting

* effect crashes: most likely too deeply nested commands (e.g. pixbri = (sin(startVal + millis()/(255- freq)) + 1) * 128), try to split up in more lines.
