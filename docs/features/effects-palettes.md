---
title: Effects and Palettes
hide:
  # - navigation
  # - toc
---

### Effects



| EffectID | Name | Description | Intensity slider effect
| ---: | --- | --- | ---
| 0 | Solid | Solid primary color on all LEDs <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_0.gif) | -
| 1 | Blink | Blinks between primary and secondary color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_1.gif) | Duty cycle of blinking
| 2 | Breathe | Fades between primary and secondary color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_2.gif) | -
| 3 | Wipe | Switches between primary and secondary, switching LEDs one by one, start to end <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_3.gif) | Smoothness
| 4 | Wipe Random | Same as Wipe, but uses random colors <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_4.gif) | Smoothness
| 5 | Random Colors | Applies a new random color to all LEDs <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_5.gif) | Duration of fading between colors
| 6 | Sweep | Switches between primary and secondary, switching LEDs one by one, start to end to start <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_6.gif) | Smoothness
| 7 | Dynamic | Sets each LED to a random color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_7.gif) | 0-127: Set single LED 128-255: Set all LEDs
| 8 | Colorloop | Cycle all LEDs through the rainbow colors <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_8.gif) | 0-127: Pastel colors 128-255: Saturated colors
| 9 | Rainbow | Displays rainbow colors along the whole strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_9.gif) | Number of rainbows
| 10 | Scan | A single primary colored light wanders between start and end <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_10.gif) | Scan dot size
| 11 | Dual Scan | Same as Scan but uses two lights starting at both ends <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_11.gif) | scan dot size
| 12 | Fade | Fades smoothly between primary and secondary color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_12.gif) | -
| 13 | Theater | Pattern of one lit and two unlit LEDs running <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_13.gif) | Gap in lights
| 14 | Theater Rainbow | Same as Theater but uses colors of the rainbow <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_14.gif) | -
| 15 | Running | Sine Waves scrolling <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_15.gif) | Wavelength
| 16 | Saw | Sawtooth Waves scrolling <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_16.gif) | Wavelength
| 17 | Twinkle | Random LEDs light up in the primary color with secondary as background, turns all off <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_17.gif) | Amount of LEDs turning on
| 18 | Dissolve | Fills LEDs with primary in random order, then off again <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_18.gif) | Dissolve rate
| 19 | Dissolve Rnd | Fills LEDs with random colors in random order, then off again <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_19.gif) | Dissolve rate
| 20 | Sparkle | Single random LEDs light up in the primary color for a short time, secondary is background <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_20.gif) | -
| 21 | Sparkle Dark | All LEDs are lit in the primary color, single random LEDs turn off for a short time <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_21.gif) | -
| 22 | Sparkle+ | All LEDs are lit in the primary color, multiple random LEDs turn off for a short time <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_22.gif) | -
| 23 | Strobe | All LEDs are lit in the secondary color, all LEDs flash in a single short burst in primary color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_23.gif) | -
| 24 | Strobe Rainbow | Same as strobe, cycles through the rainbow <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_24.gif) | -
| 25 | Strobe Mega | All LEDs are lit in the secondary color, all LEDs flash in several short bursts in primary color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_25.gif) | -
| 26 | Blink Rainbow | Same as blink, cycles through the rainbow <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_26.gif) | Blink Duty cycle
| 27 | Android | Section of varying length running <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_27.gif) | Maximum section length
| 28 | Chase | 2 LEDs in primary color running on secondary <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_28.gif) | Size of chaser
| 29 | Chase Random | Like Chase but leaves trail of random color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_29.gif) | Size of chaser
| 30 | Chase Rainbow | Like 28 but leaves trail of rainbow <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_30.gif) | Size of chaser
| 31 | Chase Flash | 2 LEDs flash in secondary color while the rest is lit in primary. The flashing LEDs wander from start to end  <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_31.gif) | -
| 32 | Chase Flash Rnd | Like Chase Flash, but the 2 LEDs flash in random colors and leaves a random color behind <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_32.gif) | -
| 33 | Rainbow Runner | Like Chase, but the 2 LEDs light up in rainbow colors and leave a primary color trail <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_33.gif) | Size of chaser
| 34 | Colorful | Shifting Red-Amber-Green-Blue pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_34.gif) | 0-127: Pastel colors 128-255: Saturated colors
| 35 | Traffic Light | Emulates a traffic light <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_35.gif) | -
| 36 | Sweep Random | Like Sweep, but uses random colors <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_36.gif) | Smoothness
| 37 | Running 2 | Pattern of n LEDs primary and n LEDs secondary moves along the strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_37.gif) | Amount of LEDs lit/unlit
| 38 | Aurora | Simulation of the Aurora Borealis | Number of waves 
| 39 | Stream | Flush bands random hues along the string <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_39.gif) | Width of each band (lower is wider)
| 40 | Scanner | Dot moves between ends, leaving behing a fading trail <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_40.gif) | Fade rate
| 41 | Lighthouse | Dot moves from start to end, leaving behing a fading trail <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_41.gif) | Fade rate
| 42 | Fireworks | Random color blobs light up, then fade again <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_42.gif) | Amount of fireworks
| 43 | Rain | Like Fireworks, but the blobs move <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_43.gif) | Amout of Rain
| 44 | Merry Christmas | Running 2, but always uses red and green <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_44.gif) | Amount of LEDs lit/unlit
| 45 | Fire Flicker | LEDs randomly flickering <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_45.gif) | Flickering intensity
| 46 | Gradient | Moves a saturation gradient of the primary color along the strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_46.gif) | Gradient width
| 47 | Loading | Moves a sawtooth pattern along the strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_47.gif) | Width
| 48 | Police | A red and a blue dot running | Size of dots
| 49 | Police All | Two areas, one red and one blue, sweeping | -
| 50 | Two Dots | Like Police, but with custom colors | Size of dots
| 51 | Two Areas | Like Police All, but with custom colors | -
| 52 | Circus | Pattern of secondary, red and white <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_52.gif) | Width of pattern
| 53 | Halloween | Running 2, but always uses orange and purple <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_53.gif) | Amount of LEDs lit/unlit
| 54 | Tri Chase | Like Chase, but with 3 colors <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_54.gif) | Width of pattern
| 55 | Tri Wipe | Like Wipe but turns LEDs off as "third color" <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_55.gif) | -
| 56 | Tri Fade | Fades the whole strip from primary color to secondary color to off <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_56.gif) | -
| 57 | Lightning | Short random white strobe similar to a lightning bolt <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_57.gif) | Amount of strobes
| 58 | ICU | Two "eyes" running on opposite sides of the strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_58.gif) | -
| 59 | Multi Comet | Like Scanner, but creates multiple trails <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_59.gif) | Fade rate
| 60 | Scanner Dual | Like Scanner, but with two dots running on opposite sides <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_60.gif) | Fade rate
| 61 | Stream 2 | Flush random hues along the string <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_61.gif) | -
| 62 | Oscillate | Areas of primary and secondary colors move between opposite ends, combining colors where they touch <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_62.gif) | -
| 63 | Pride 2015 | Rainbow cycling with brightness variation <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_63.gif) | -
| 64 | Juggle | Eight colored dots running, leaving trails <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_64.gif) | Fade rate
| 65 | Palette | Running color palette <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_65.gif) | -
| 66 | Fire 2012 | Simulates flickering fire in red and yellow <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_66.gif) | Sparkling of fire
| 67 | Colorwaves | Like Pride 2015, but uses palettes <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_67.gif) | -
| 68 | BPM | Pulses moving back and forth on palette <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_68.gif) | BPM setting
| 69 | Fill Noise | Noise pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_69.gif) | -
| 70 | Noise 1 | Fast Noise shift pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_70.gif) | -
| 71 | Noise 2 | Fast Noise shift pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_71.gif) | -
| 72 | Noise 3 | Noise shift pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_72.gif) | -
| 73 | Noise 4 | Noise sparkle pattern <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_73.gif) | -
| 74 | Colortwinkles | LEDs light up randomly in random colors and fade off again <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_74.gif) | Twinkle rate
| 75 | Lake | Calm palette waving <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_75.gif) | -
| 76 | Meteor | The primary color creates a trail of randomly decaying color <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_76.gif) | Fade rate
| 77 | Meteor Smooth | Smoothly animated meteor <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_77.gif) | Fade rate
| 78 | Railway | Shows primary and secondary color on alternating LEDs. All LEDs fade to their opposite color and back again <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_78.gif) | Duty cycle of fade transition
| 79 | Ripple | Effect resembling random water ripples <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_79.gif) | Rate of new ripples
| 80 | Twinklefox | FastLED gentle twinkling with slow fade in/out <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_80.gif) | Density
| 81 | Twinklecat | Twinkling with fast in / slow out <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_81.gif) | Density
| 82 | Halloween Eyes | One Pair of blinking eyes at random intervals along strip <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/FX_82.gif) | Fading rade of eyes
| 83 | Solid Pattern | Speed sets number of LEDs on, intensity sets off | Amount of LEDs turned off
| 84 | Solid Pattern Tri | Solid Pattern with three colors | Amount of LEDs of each color
| 85 | Spots | Solid lights with even distance | Size of each spot
| 86 | Spots Fade | Spots, getting bigger and smaller | Fading of each spot
| 87 | Glitter | Rainbow with white sparkles | Amount of glitter
| 88 | Candle | Flicker resembling a candle flame | Intensity of flickering
| 89 | Fireworks Starburst | Exploding multicolor fireworks | Fragment count
| 90 | Fireworks 1D | one dimension fireworks with flare | Firing side
| 91 | Bouncing Balls | Bouncing ball effect | Number of balls
| 92 | Sinelon | Fastled sinusoidal moving eye | Fade rate
| 93 | Sinelon Dual | Sinelon from both directions | Fade rate
| 94 | Sinelon Rainbow | Sinelon in rainbow colours | Fade rate
| 95 | Popcorn | popping kernels | Number of kernels
| 96 | Drip | Water dripping effect | Intensity of dripping
| 97 | Plasma | Plasma lamp | Max brightness
| 98 | Percent | Lights up a percentage of segment | Percentage
| 99 | Ripple Rainbow | Like ripple, but with a dimly lit changing background | Rate of new ripples
| 100 | Heartbeat | led strip pulsing rhythm similar to a heart beat | -
| 101 | Pacifica | Gentle, blue-green ocean waves (one color palette currently) | Intensity of waves
| 102 | Candle Multi | Like candle effect, but each LED has it's own flicker pattern | Intensity of flicker
| 103 | Solid Glitter | Like Glitter, but with solid color background | Amount of glitter
| 104 | Sunrise | Simulates a gradual sunrise or sunset. Speed sets:<br/> 0 - static sun, 1 - 60: sunrise time in minutes,<br/> 60 - 120: sunset time in minutes - 60, above: "breathing" rise and set | Sun intensity
| 105 | Phased | Sine waves (in sourcecode) | Wave brightness against background
| 106 | TwinkleUp | Twinkle effect with fade-in | Amount of Twinkles
| 107 | Noise Pal | Peaceful noise that's slow and with gradually changing palettes | Wave intensity
| 108 | Sine | Controllable sine waves | Sinewave frequency
| 109 | Phased Noise | Noisy sine waves | Wave brightness against background
| 110 | Flow | Blend of palette and spot effects | waveform frequency
| 111 | Chunchun | Birds flying in a circle formation | Number of birds
| 112 | Dancing Shadows | Moving spotlights | Number of spotlights
| 113 | Washing machine | Alternating direction _(in source)_ | Size of lit sections
| 114 | Candy Cane | Running 2 in Red & White | Amount of LEDs lit/unlit
| 115 | Blends | Blends random colors across palette | Blend speed
| 116 | TV Simulator | TV light spill simulation | - 
| 117 | Dynamic Smooth | Link Dynamic but with smooth palette blends | 0-127: Set single LED 128-255: Set all LEDs


### Palettes

| PaletteID | Name | Description
| ---: | --- | ---
| 0 | Default | The palette is automatically selected depending on the effect. For most effects, this is the primary color<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_0.gif)
| 1 | Random Cycle | The palette changes to a random one every few seconds. Subject to change<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_1.gif)
| 2 | Primary color | A palette consisting only of the primary color<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_2.gif)
| 3 | Based on primary | Consists of the primary color, as well as a slightly desaturated version and black<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_3.gif)
| 4 | Set colors | A palette which is a mixture of all segment colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_4.gif)
| 5 | Based on set | Contains primary, secondary colors and a desaturated version<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_5.gif)
| 6 | Party | Rainbow without green hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_6.gif)
| 7 | Cloud | Gray-blueish colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_7.gif)
| 8 | Lava | Dark red, yellow and bright white<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_8.gif)
| 9 | Ocean | Blue, teal and white colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_9.gif)
| 10 | Forest | Yellow and green hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_10.gif)
| 11 | Rainbow | Every hue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_11.gif)
| 12 | Rainbow bands | Rainbow colors with black spots in-between<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_12.gif)
| 13 | Sunset | Dark blue with purple, red and yellow hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_13.gif)
| 14 | Rivendell | Desaturated greens<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_14.gif)
| 15 | Breeze | Teal colors with varying brightness<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_15.gif)
| 16 | Red & Blue | Red running on blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_16.gif)
| 17 | Yellowout | Yellow, fading out<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_17.gif)
| 18 | Analoguous | Red running on blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_18.gif)
| 19 | Splash | Vibrant pink and magenta<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_19.gif)
| 20 | Pastel | Different hues with very little saturation<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_20.gif)
| 21 | Sunset 2 | Yellow and white running on dim blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_21.gif)
| 22 | Beech | Different shades of light blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_22.gif)
| 23 | Vintage | Warm white running on very dim red<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_23.gif)
| 24 | Departure | Greens and white fading out<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_24.gif)
| 25 | Landscape | Blue, white and green gradient<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_25.gif)
| 26 | Beach | Teal and yellow gradient fading out<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_26.gif)
| 27 | Sherbet | Bright white, pink and mint colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_27.gif)
| 28 | Hult | White, magenta and teal<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_28.gif)
| 29 | Hult 64 | Teal and yellow hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_29.gif)
| 30 | Drywet | Blue and yellow gradient<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_30.gif)
| 31 | Jul | Pastel green and red <br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_31.gif)
| 32 | Grintage | Yellow fading out<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_32.gif)
| 33 | Rewhi | Bright orange on desaturated purple<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_33.gif)
| 34 | Tertiary | Red, green and blue gradien<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_34.gif)
| 35 | Fire | White, yellow and fading red gradient<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_35.gif)
| 36 | Icefire | Same as Fire, but with blue colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_36.gif)
| 37 | Cyane | Desaturated pastel colors<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_37.gif)
| 38 | Light Pink | Desaturated purple hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_38.gif)
| 39 | Autumn | Three white fields surrounded by yellow and dim red<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_39.gif)
| 40 | Magenta | White with magenta and blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_40.gif)
| 41 | Magred | Magenta and red hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_41.gif)
| 42 | Yelmag | Magenta and red hues with a yellow<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_42.gif)
| 43 | Yelblu | Blue with a little yellow<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_43.gif)
| 44 | Orange & Teal | An Orange - Gray - Teal gradient<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_44.gif)
| 45 | Tiamat | A bright meteor with blue, teal and magenta hues<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_45.gif)
| 46 | April Night | Dark blue background with colorful snowflakes<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_46.gif)
| 47 | Orangery | Orange and yellow tones<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_47.gif)
| 48 | C9 | Christmas lights palette. Red - amber - green - blue<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_48.gif)
| 49 | Sakura | Pink and rose tones<br />![](https://raw.githubusercontent.com/photocromax/WLED-live-visualizations/master/GIF/PAL_49.gif)
| 50 | Aurora | Greens on dark blue
| 51 | Atlantica | Greens & Blues of the ocean
| 52 | C9 2 | C9 plus yellow
| 53 | C9 New | C9, but brighter and with a less purple blue
| 54 | Temperature | Temperature mapping
| 55 | Aurora 2 | Aurora with some pinks & blue
| 56 | Retro Clown | Yellow to purple gradient
| 57 | Candy | Vivid yellows, magenta, salmon and blues
| 58 | Toxy Reaf | Vivid aqua to purple gradient
| 59 | Fairy Reaf | Bright aqua to purple gradient
| 60 | Semi Blue | Dark blues with a bright blue burst
| 61 | Pink Candy | White, pinks and purple
| 62 | Red Reaf | Blue, aqua and red gradient
| 63 | Aqua Flash | Aqua gradient with a flash of yellow and white
| 64 | Yelblu Hot | Yellow, red, blue spectrum  
| 65 | Lite Light | Faint white and purple
| 66 | Red Flash | Red gradient with burst of white in the center 
| 67 | Blink Red | Dark blue to dark red gradient with burst of purple
| 68 | Red Shift | Vibrant yellow to blue gradient with magenta, purple and red 
| 69 | Red Tide | Waves of yellow, orange and red
| 70 | Candy2 | Faded gradient of yellow, salmon and blue
