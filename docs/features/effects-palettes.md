---
title: Effects and Palettes
hide:
  # - navigation
  # - toc
---

### Effects

To aid in showing where colors vs palettes are used, all effects are rendered with the Party palette ![party](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_06.gif)
and the colors ![primary](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_1.gif) primary 
![secondary](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_2.gif) secondary 
![tertiary](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_3.gif) tertiary colors


| EffectID | Name | Description | Intensity slider effect 
| ---: | --- | --- | ---
| 0 | Solid | Solid primary color on all LEDs <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_000.gif) | -
| 1 | Blink | Blinks between primary and secondary color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_001.gif) | Duty cycle of blinking
| 2 | Breathe | Fades between primary and secondary color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_002.gif) | -
| 3 | Wipe | Switches between primary and secondary, switching LEDs one by one, start to end <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_003.gif) | Smoothness
| 4 | Wipe Random | Same as Wipe, but uses random colors <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_004.gif) | Smoothness
| 5 | Random Colors | Applies a new random color to all LEDs <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_005.gif) | Duration of fading between colors
| 6 | Sweep | Switches between primary and secondary, switching LEDs one by one, start to end to start <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_006.gif) | Smoothness
| 7 | Dynamic | Sets each LED to a random color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_007.gif) | 0-127: Set single LED 128-255: Set all LEDs
| 8 | Colorloop | Cycle all LEDs through the rainbow colors <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_008.gif) | 0-127: Pastel colors 128-255: Saturated colors
| 9 | Rainbow | Displays rainbow colors along the whole strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_009.gif) | Number of rainbows
| 10 | Scan | A single primary colored light wanders between start and end <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_010.gif) | Scan dot size
| 11 | Scan Dual | Same as Scan but uses two lights starting at both ends <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_011.gif) | scan dot size
| 12 | Fade | Fades smoothly between primary and secondary color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_012.gif) | -
| 13 | Theater | Pattern of one lit and two unlit LEDs running <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_013.gif) | Gap in lights
| 14 | Theater Rainbow | Same as Theater but uses colors of the rainbow <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_014.gif) | -
| 15 | Running | Sine Waves scrolling <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_015.gif) | Wavelength
| 16 | Saw | Sawtooth Waves scrolling <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_016.gif) | Wavelength
| 17 | Twinkle | Random LEDs light up in the primary color with secondary as background, turns all off <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_017.gif) | Amount of LEDs turning on
| 18 | Dissolve | Fills LEDs with primary in random order, then off again <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_018.gif) | Dissolve rate
| 19 | Dissolve Rnd | Fills LEDs with random colors in random order, then off again <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_019.gif) | Dissolve rate
| 20 | Sparkle | Single random LEDs light up in the primary color for a short time, secondary is background <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_020.gif) | -
| 21 | Sparkle Dark | All LEDs are lit in the primary color, single random LEDs turn off for a short time <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_021.gif) | -
| 22 | Sparkle+ | All LEDs are lit in the primary color, multiple random LEDs turn off for a short time <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_022.gif) | -
| 23 | Strobe | All LEDs are lit in the secondary color, all LEDs flash in a single short burst in primary color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_023.gif) | -
| 24 | Strobe Rainbow | Same as strobe, cycles through the rainbow <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_024.gif) | -
| 25 | Strobe Mega | All LEDs are lit in the secondary color, all LEDs flash in several short bursts in primary color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_025.gif) | -
| 26 | Blink Rainbow | Same as blink, cycles through the rainbow <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_026.gif) | Blink Duty cycle
| 27 | Android | Section of varying length running <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_027.gif) | Maximum section length
| 28 | Chase | 2 LEDs in primary color running on secondary <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_028.gif) | Size of chaser
| 29 | Chase Random | Like Chase but leaves trail of random color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_029.gif) | Size of chaser
| 30 | Chase Rainbow | Like 28 but leaves trail of rainbow <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_030.gif) | Size of chaser
| 31 | Chase Flash | 2 LEDs flash in secondary color while the rest is lit in primary. The flashing LEDs wander from start to end  <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_031.gif) | -
| 32 | Chase Flash Rnd | Like Chase Flash, but the 2 LEDs flash in random colors and leaves a random color behind <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_032.gif) | -
| 33 | Rainbow Runner | Like Chase, but the 2 LEDs light up in rainbow colors and leave a primary color trail <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_033.gif) | Size of chaser
| 34 | Colorful | Shifting Red-Amber-Green-Blue pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_034.gif) | 0-127: Pastel colors 128-255: Saturated colors
| 35 | Traffic Light | Emulates a traffic light <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_035.gif) | -
| 36 | Sweep Random | Like Sweep, but uses random colors <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_036.gif) | Smoothness
| 37 | Running 2 | Pattern of n LEDs primary and n LEDs secondary moves along the strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_037.gif) | Amount of LEDs lit/unlit
| 38 | Aurora | Simulation of the Aurora Borealis <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_038.gif) | Number of waves 
| 39 | Stream | Flush bands random hues along the string <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_039.gif) | Width of each band (lower is wider)
| 40 | Scanner | Dot moves between ends, leaving behing a fading trail <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_040.gif) | Fade rate
| 41 | Lighthouse | Dot moves from start to end, leaving behing a fading trail <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_041.gif) | Fade rate
| 42 | Fireworks | Random color blobs light up, then fade again <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_042.gif) | Amount of fireworks
| 43 | Rain | Like Fireworks, but the blobs move <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_043.gif) | Amout of Rain
| 44 | Tetrix | Falling blocks stack <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_044.gif) | -
| 45 | Fire Flicker | LEDs randomly flickering <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_045.gif) | Flickering intensity
| 46 | Gradient | Moves a saturation gradient of the primary color along the strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_046.gif) | Gradient width
| 47 | Loading | Moves a sawtooth pattern along the strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_047.gif) | Width
| 48 | Police | A red and a blue dot running <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_048.gif) | Size of dots
| 49 | Police All | Two areas, one red and one blue, sweeping<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_049.gif) | -
| 50 | Two Dots | Like Police, but with custom colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_050.gif) | Size of dots
| 51 | Two Areas | Like Police All, but with custom colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_051.gif) | -
| 52 | Running Dual | Sine waves in both directions <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_052.gif) |  Number of waves
| 53 | Halloween | Running 2, but always uses orange and purple <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_053.gif) | Amount of LEDs lit/unlit
| 54 | Tri Chase | Like Chase, but with 3 colors <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_054.gif) | Width of pattern
| 55 | Tri Wipe | Like Wipe but turns LEDs off as "third color" <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_055.gif) | -
| 56 | Tri Fade | Fades the whole strip from primary color to secondary color to off <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_056.gif) | -
| 57 | Lightning | Short random white strobe similar to a lightning bolt <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_057.gif) | Amount of strobes
| 58 | ICU | Two "eyes" running on opposite sides of the strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_058.gif) | -
| 59 | Multi Comet | Like Scanner, but creates multiple trails <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_059.gif) | Fade rate
| 60 | Scanner Dual | Like Scanner, but with two dots running on opposite sides <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_060.gif) | Fade rate
| 61 | Stream 2 | Flush random hues along the string <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_061.gif) | -
| 62 | Oscillate | Areas of primary and secondary colors move between opposite ends, combining colors where they touch <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_062.gif) | -
| 63 | Pride 2015 | Rainbow cycling with brightness variation <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_063.gif) | -
| 64 | Juggle | Eight colored dots running, leaving trails <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_064.gif) | Fade rate
| 65 | Palette | Running color palette <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_065.gif) | -
| 66 | Fire 2012 | Simulates flickering fire in red and yellow <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_066.gif) | Sparkling of fire
| 67 | Colorwaves | Like Pride 2015, but uses palettes <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_067.gif) | -
| 68 | BPM | Pulses moving back and forth on palette <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_068.gif) | BPM setting
| 69 | Fill Noise | Noise pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_069.gif) | -
| 70 | Noise 1 | Fast Noise shift pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_070.gif) | -
| 71 | Noise 2 | Fast Noise shift pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_071.gif) | -
| 72 | Noise 3 | Noise shift pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_072.gif) | -
| 73 | Noise 4 | Noise sparkle pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_073.gif) | -
| 74 | Colortwinkles | LEDs light up randomly in random colors and fade off again <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_074.gif) | Twinkle rate
| 75 | Lake | Calm palette waving <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_075.gif) | -
| 76 | Meteor | The primary color creates a trail of randomly decaying color <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_076.gif) | Fade rate
| 77 | Meteor Smooth | Smoothly animated meteor <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_077.gif) | Fade rate
| 78 | Railway | Shows primary and secondary color on alternating LEDs. All LEDs fade to their opposite color and back again <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_078.gif) | Duty cycle of fade transition
| 79 | Ripple | Effect resembling random water ripples <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_079.gif) | Rate of new ripples
| 80 | Twinklefox | FastLED gentle twinkling with slow fade in/out <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_080.gif) | Density
| 81 | Twinklecat | Twinkling with fast in / slow out <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_081.gif) | Density
| 82 | Halloween Eyes | One Pair of blinking eyes at random intervals along strip <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_082.gif) | Fading rade of eyes
| 83 | Solid Pattern | Speed sets number of LEDs on, intensity sets off <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_083.gif) | Amount of LEDs turned off
| 84 | Solid Pattern Tri | Solid Pattern with three colors <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_084.gif)| Amount of LEDs of each color
| 85 | Spots | Solid lights with even distance <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_085.gif)| Size of each spot
| 86 | Spots Fade | Spots, getting bigger and smaller <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_086.gif)| Fading of each spot
| 87 | Glitter | Rainbow with white sparkles <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_087.gif)| Amount of glitter
| 88 | Candle | Flicker resembling a candle flame <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_088.gif)| Intensity of flickering
| 89 | Fireworks Starburst | Exploding multicolor fireworks <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_089.gif)| Fragment count
| 90 | Fireworks 1D | one dimension fireworks with flare <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_090.gif)| Firing side
| 91 | Bouncing Balls | Bouncing ball effect <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_091.gif)| Number of balls
| 92 | Sinelon | Fastled sinusoidal moving eye <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_092.gif)| Fade rate
| 93 | Sinelon Dual | Sinelon from both directions <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_093.gif)| Fade rate
| 94 | Sinelon Rainbow | Sinelon in rainbow colours <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_094.gif)| Fade rate
| 95 | Popcorn | popping kernels <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_095.gif) | Number of kernels
| 96 | Drip | Water dripping effect <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_096.gif) | Intensity of dripping
| 97 | Plasma | Plasma lamp <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_097.gif) | Max brightness
| 98 | Percent | Lights up a percentage of segment <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_098.gif) | Percentage
| 99 | Ripple Rainbow | Like ripple, but with a dimly lit changing background <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_099.gif) | Rate of new ripples
| 100 | Heartbeat | led strip pulsing rhythm similar to a heart beat <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_100.gif) | -
| 101 | Pacifica | Gentle, blue-green ocean waves (one color palette currently) <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_101.gif) | Intensity of waves
| 102 | Candle Multi | Like candle effect, but each LED has it's own flicker pattern <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_102.gif) | Intensity of flicker
| 103 | Solid Glitter | Like Glitter, but with solid color background <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_103.gif) | Amount of glitter
| 104 | Sunrise | Simulates a gradual sunrise or sunset. Speed sets:<br/> 0 - static sun, 1 - 60: sunrise time in minutes,<br/> 60 - 120: sunset time in minutes - 60, above: "breathing" rise and set <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_104.gif) | Sun intensity
| 105 | Phased | Sine waves (in sourcecode) <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_105.gif) | Wave brightness against background
| 106 | TwinkleUp | Twinkle effect with fade-in <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_106.gif) | Amount of Twinkles
| 107 | Noise Pal | Peaceful noise that's slow and with gradually changing palettes <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_107.gif) | Wave intensity
| 108 | Sine | Controllable sine waves <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_108.gif) | Sinewave frequency
| 109 | Phased Noise | Noisy sine waves <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_109.gif) | Wave brightness against background
| 110 | Flow | Blend of palette and spot effects <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_110.gif) | waveform frequency
| 111 | Chunchun | Birds flying in a circle formation <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_111.gif) | Number of birds
| 112 | Dancing Shadows | Moving spotlights <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_112.gif) | Number of spotlights
| 113 | Washing machine | Alternating direction _(in source)_ <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_113.gif) | Size of lit sections
| 114 | Candy Cane | Running 2 in Red & White <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_114.gif) | Amount of LEDs lit/unlit
| 115 | Blends | Blends random colors across palette <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_115.gif) | Blend speed
| 116 | TV Simulator | TV light spill simulation <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_116.gif) | - 
| 117 | Dynamic Smooth | Link Dynamic but with smooth palette blends <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_117.gif) | 0-127: Set single LED 128-255: Set all LEDs


### Palettes

| PaletteID | Name | Description
| ---: | --- | ---
| 0 | Default | The palette is automatically selected depending on the effect. For most effects, this is the primary color<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_00.gif)
| 1 | Random Cycle | The palette changes to a random one every few seconds. Subject to change<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_01.gif)
| 2 | Color 1 | A palette consisting only of the primary color<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_02.gif)
| 3 | Colors 1 & 2 | Consists of the primary and secondary color<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_03.gif)
| 4 | Color Gradient | A palette which is a mixture of all segment colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_04.gif)
| 5 | Colors Only | Contains primary, secondary and tertiary colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_05.gif)
| 6 | Party | Rainbow without green hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_06.gif)
| 7 | Cloud | Gray-blueish colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_07.gif)
| 8 | Lava | Dark red, yellow and bright white<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_08.gif)
| 9 | Ocean | Blue, teal and white colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_09.gif)
| 10 | Forest | Yellow and green hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_10.gif)
| 11 | Rainbow | Every hue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_11.gif)
| 12 | Rainbow bands | Rainbow colors with black spots in-between<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_12.gif)
| 13 | Sunset | Dark blue with purple, red and yellow hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_13.gif)
| 14 | Rivendell | Desaturated greens<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_14.gif)
| 15 | Breeze | Teal colors with varying brightness<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_15.gif)
| 16 | Red & Blue | Red running on blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_16.gif)
| 17 | Yellowout | Yellow, fading out<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_17.gif)
| 18 | Analoguous | Red running on blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_18.gif)
| 19 | Splash | Vibrant pink and magenta<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_19.gif)
| 20 | Pastel | Different hues with very little saturation<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_20.gif)
| 21 | Sunset 2 | Yellow and white running on dim blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_21.gif)
| 22 | Beech | Different shades of light blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_22.gif)
| 23 | Vintage | Warm white running on very dim red<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_23.gif)
| 24 | Departure | Greens and white fading out<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_24.gif)
| 25 | Landscape | Blue, white and green gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_25.gif)
| 26 | Beach | Teal and yellow gradient fading out<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_26.gif)
| 27 | Sherbet | Bright white, pink and mint colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_27.gif)
| 28 | Hult | White, magenta and teal<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_28.gif)
| 29 | Hult 64 | Teal and yellow hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_29.gif)
| 30 | Drywet | Blue and yellow gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_30.gif)
| 31 | Jul | Pastel green and red <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_31.gif)
| 32 | Grintage | Yellow fading out<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_32.gif)
| 33 | Rewhi | Bright orange on desaturated purple<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_33.gif)
| 34 | Tertiary | Red, green and blue gradien<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_34.gif)
| 35 | Fire | White, yellow and fading red gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_35.gif)
| 36 | Icefire | Same as Fire, but with blue colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_36.gif)
| 37 | Cyane | Desaturated pastel colors<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_37.gif)
| 38 | Light Pink | Desaturated purple hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_38.gif)
| 39 | Autumn | Three white fields surrounded by yellow and dim red<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_39.gif)
| 40 | Magenta | White with magenta and blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_40.gif)
| 41 | Magred | Magenta and red hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_41.gif)
| 42 | Yelmag | Magenta and red hues with a yellow<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_42.gif)
| 43 | Yelblu | Blue with a little yellow<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_43.gif)
| 44 | Orange & Teal | An Orange - Gray - Teal gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_44.gif)
| 45 | Tiamat | A bright meteor with blue, teal and magenta hues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_45.gif)
| 46 | April Night | Dark blue background with colorful snowflakes<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_46.gif)
| 47 | Orangery | Orange and yellow tones<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_47.gif)
| 48 | C9 | Christmas lights palette. Red - amber - green - blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_48.gif)
| 49 | Sakura | Pink and rose tones<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_49.gif)
| 50 | Aurora | Greens on dark blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_50.gif) 
| 51 | Atlantica | Greens & Blues of the ocean<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_51.gif) 
| 52 | C9 2 | C9 plus yellow<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_52.gif)
| 53 | C9 New | C9, but brighter and with a less purple blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_53.gif)
| 54 | Temperature | Temperature mapping<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_54.gif)
| 55 | Aurora 2 | Aurora with some pinks & blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_55.gif)
| 56 | Retro Clown | Yellow to purple gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_56.gif)
| 57 | Candy | Vivid yellows, magenta, salmon and blues<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_57.gif)
| 58 | Toxy Reaf | Vivid aqua to purple gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_58.gif)
| 59 | Fairy Reaf | Bright aqua to purple gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_59.gif)
| 60 | Semi Blue | Dark blues with a bright blue burst<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_60.gif)
| 61 | Pink Candy | White, pinks and purple<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_61.gif)
| 62 | Red Reaf | Blue, aqua and red gradient<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_62.gif)
| 63 | Aqua Flash | Aqua gradient with a flash of yellow and white<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_63.gif)
| 64 | Yelblu Hot | Yellow, red, blue spectrum<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_64.gif)  
| 65 | Lite Light | Faint white and purple<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_65.gif)
| 66 | Red Flash | Red gradient with burst of white in the center <br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_66.gif)
| 67 | Blink Red | Dark blue to dark red gradient with burst of purple<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_67.gif)
| 68 | Red Shift | Vibrant yellow to blue gradient with magenta, purple and red<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_68.gif) 
| 69 | Red Tide | Waves of yellow, orange and red<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_69.gif)
| 70 | Candy2 | Faded gradient of yellow, salmon and blue<br />![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_70.gif)
