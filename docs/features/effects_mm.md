---
title: Effects
hide:
  # - navigation
  # - toc
---

!!! info "Version Info"
    Effects above 117 are only available 0.14+ or Sound Reactive forks.<br />
    [Retired Effects](#retired-effects) - Can't find an old favorite? Look here.

#### Effect Overlay
Some effects can be overlaid on the background of another effect. To use overlay, set up
segments with overlapping pixels. The overlay effect must be playing on the segment with the higher id. 
If the Overlay option is checked, the background will not be painted and the effect
from the lower segment will be displayed.


To aid in showing where colors vs palettes are used, all effects are rendered with the 
_Party_ palette ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/PAL_06.gif)<br />
and the colors: <br />
![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_1.gif) Primary (_Fx_)<br />
![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_2.gif) (or black) Secondary  (_Bg_)<br />
![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/color_3.gif) Tertiary (_Cs_).<br />


| ID | Effect | Description | Flags | Colors | Parms
| ---: | --- | --- | --- | --- | --- 
| 186 | Akemi |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_186.gif) |  ▦ ♫ | Head palette, Arms & Legs, Eyes & Mouth | Color speed, Dance
| 27 | Android |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_027.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Width
| 38 | Aurora |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_038.gif) |  ⋮ | 🎨 1, 2, 3 | Speed, Intensity
| 183 | Black Hole |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_183.gif) |  ▦ |  | Fade rate, Outer Y freq., Outer X freq., Inner X freq., Inner Y freq.
| 115 | Blends |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_115.gif) |  ⋮ | 🎨  | Shift speed, Blend speed
| 1 | Blink |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_001.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Duty cycle
| 26 | Blink Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_026.gif) |  ⋮ | 🎨 Fx, Bg | Frequency, Blink duration
| 121 | Blobs |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_121.gif) |  ▦ | 🎨 Fx | Speed, # blobs, Blur
| 163 | Blurz ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM163.gif) |  ⋮ ♫ | 🎨 Fx, Color mix | Fade rate, Blur
| 91 | Bouncing Balls |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_091.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Gravity, # of balls, Overlay
| 68 | Bpm |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_068.gif) |  ⋮ | 🎨 Fx | Speed
| 2 | Breathe |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_002.gif) |  ⋮ | 🎨 Fx, Bg | Speed
| 88 | Candle |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_088.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 102 | Candle Multi |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_102.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 28 | Chase |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_028.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, Width
| 37 | Chase 2 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_037.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Width
| 54 | Chase 3 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_054.gif) |  ⋮ | 🎨 1, 2, 3 | Speed, Size
| 31 | Chase Flash |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_031.gif) |  ⋮ | 🎨 Bg, Fx | Speed
| 32 | Chase Flash Rnd |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_032.gif) |  ⋮ | 🎨 Fx, Bg | Speed
| 30 | Chase Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_030.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Width
| 29 | Chase Random |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_029.gif) |  ⋮ | 🎨 Fx, Cs | Speed, Width
| 111 | Chunchun |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_111.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Gap size
| 167 | Colored Bursts |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_167.gif) |  ▦ | 🎨  | Speed, # of lines, Blur, Gradient, Dots
| 34 | Colorful |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_034.gif) |  ⋮ | 🎨 1, 2, 3 | Speed, Saturation
| 8 | Colorloop |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_008.gif) |  ⋮ | 🎨  | Speed, Saturation
| 74 | Colortwinkles |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_074.gif) |  ⋮ | 🎨  | Fade speed, Spawn speed
| 67 | Colorwaves |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_067.gif) |  ⋮ | 🎨 Fx | Speed, Hue
| 119 | Crazy Bees |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_119.gif) |  ▦ |  | Speed, Blur
| 159 | DJ Light |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_159.gif) |  ⋮ ♫ |  | Speed, Candy Factory
| 152 | DNA |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_152.gif) |  ▦ | 🎨  | Scroll speed, Blur
| 182 | DNA Spiral |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_182.gif) |  ▦ | 🎨  | Scroll speed, Y frequency
| 112 | Dancing Shadows |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_112.gif) |  ⋮ | 🎨 Fx | Speed, # of shadows
| 18 | Dissolve |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_018.gif) |  ⋮ | 🎨 Fx, Bg | Repeat speed, Dissolve speed, Random
| 19 | Dissolve Rnd |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_019.gif) |  ⋮ | 🎨 Bg | Repeat speed, Dissolve speed
| 124 | Distortion Waves |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_124.gif) |  ▦ |  | Speed, Scale
| 164 | Drift |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_164.gif) |  ▦ | 🎨  | Rotation speed, Blur amount
| 123 | Drift Rose |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_123.gif) |  ▦ |  | Fade, Blur
| 96 | Drip |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_096.gif) |  ⋮ | 🎨 Fx, Bg | Gravity, # of drips, Overlay
| 7 | Dynamic |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_007.gif) |  ⋮ | 🎨  | Speed, Intensity, Smooth
| 117 | Dynamic Smooth |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_117.gif) |  ⋮ | 🎨  | Speed, Intensity
| 12 | Fade |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_012.gif) |  ⋮ | 🎨 Fx, Bg | Speed
| 49 | Fairy |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_049.gif) |  ⋮ | 🎨 Fx, Bg | Speed, # of flashers
| 51 | Fairytwinkle |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_051.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 69 | Fill Noise |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_069.gif) |  ⋮ | 🎨 Fx | Speed
| 66 | Fire 2012 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_066.gif) |  ⋮ | 🎨  | Cooling, Spark rate, Boost
| 45 | Fire Flicker |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_045.gif) |  ⋮ | 🎨 Fx | Speed, Intensity
| 149 | Firenoise |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_149.gif) |  ▦ | 🎨  | X scale, Y scale
| 42 | Fireworks |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_042.gif) |  ⋮ ▦ | 🎨 Fx, Bg | Frequency
| 90 | Fireworks 1D |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_090.gif) |  ⋮ ▦ | 🎨 Fx, Bg | Gravity, Firing side
| 89 | Fireworks Starburst |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_089.gif) |  ⋮ | 🎨 Bg | Chance, Fragments, Overlay
| 110 | Flow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_110.gif) |  ⋮ | 🎨  | Speed, Zones
| 179 | Flow Stripe |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_179.gif) |  ⋮ |  | Hue speed, Effect speed
| 155 | Freqmap |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_155.gif) |  ⋮ ♫ | 🎨 Fx, Bg | Fade rate, Starting color, Smooth mover ☾
| 138 | Freqmatrix |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_138.gif) |  ⋮ ♫ |  | Speed, Sound effect, Low bin, High bin, Sensivity
| 141 | Freqpixels |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_141.gif) |  ⋮ ♫ |  | Fade rate, Starting color and # of pixels
| 137 | Freqwave |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_137.gif) |  ⋮ ♫ |  | Speed, Sound effect, Low bin, High bin, Pre-amp, Musical Scale ☾
| 177 | Frizzles |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_177.gif) |  ▦ | 🎨  | X frequency, Y frequency, Blur
| 160 | Funky Plank |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_160.gif) |  ▦ ♫ |  | Scroll speed, # of bands
| 139 | GEQ ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM139.gif) |  ▦ ♫ | 🎨 Fx, Peaks | Fade speed, Ripple decay, # of bands, Color bars, Smooth bars ☾
| 172 | Game Of Life |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_172.gif) |  ▦ | 🎨 Fx, Bg | Speed, All colors ☾
| 120 | Ghost Rider |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_120.gif) |  ▦ | 🎨  | Fade rate, Blur
| 87 | Glitter |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_087.gif) |  ⋮ | 🎨 1, 2, Glitter color | Speed, Intensity, Overlay
| 46 | Gradient |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_046.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Spread
| 156 | Gravcenter |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_156.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Rate of fall, Sensitivity
| 157 | Gravcentric |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_157.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Rate of fall, Sensitivity
| 158 | Gravfreq ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM158.gif) |  ⋮ ♫ | 🎨 Fx, Bg | Rate of fall, Sensivity
| 132 | Gravimeter ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM132.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Rate of fall, Sensitivity, Invert Palette, Sound Pressure, AGC debug
| 82 | Halloween Eyes |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_082.gif) |  ⋮ ▦ | 🎨 Fx, Bg | Duration, Eye fade time, Overlay
| 100 | Heartbeat |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_100.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 180 | Hiphotic |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_180.gif) |  ▦ | 🎨 Fx | X scale, Y scale, Speed
| 58 | ICU |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_058.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity, Overlay
| 64 | Juggle |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_064.gif) |  ⋮ | 🎨  | Speed, Trail
| 130 | Juggles |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_130.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Speed, # of balls
| 168 | Julia |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_168.gif) |  ▦ | 🎨 Fx | Max iterations per pixel, X center, Y center, Area size
| 75 | Lake |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_075.gif) |  ⋮ | 🎨 Fx | Speed
| 41 | Lighthouse |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_041.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Fade rate
| 57 | Lightning |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_057.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity, Overlay
| 176 | Lissajous ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM176.gif) |  ▦ | 🎨 Fx | X frequency, Fade rate, Speed, ☾ Smooth Style
| 47 | Loading |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_047.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Fade
| 131 | Matripix ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM131.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Speed, Brightness, Frequency Colors, Sound Pressure
| 153 | Matrix |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_153.gif) |  ▦ | Spawn, Trail | Speed, Spawning rate, Trail, Custom color
| 154 | Metaballs |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_154.gif) |  ▦ | 🎨  | Speed
| 76 | Meteor |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_076.gif) |  ⋮ | 🎨 Fx | Speed, Trail length
| 77 | Meteor Smooth |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_077.gif) |  ⋮ | 🎨 Fx | Speed, Trail length
| 135 | Midnoise |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_135.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, Max. length
| 59 | Multi Comet |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_059.gif) |  ⋮ |  | 
| 70 | Noise 1 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_070.gif) |  ⋮ | 🎨 Fx | Speed
| 71 | Noise 2 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_071.gif) |  ⋮ | 🎨 Fx | Speed
| 72 | Noise 3 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_072.gif) |  ⋮ | 🎨 Fx | Speed
| 73 | Noise 4 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_073.gif) |  ⋮ | 🎨 Fx | Speed
| 107 | Noise Pal |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_107.gif) |  ⋮ | 🎨  | Speed, Scale
| 146 | Noise2D |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_146.gif) |  ▦ | 🎨  | Speed, Scale
| 143 | Noisefire |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_143.gif) |  ⋮ ♪ |  | Speed, Intensity
| 136 | Noisemeter |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_136.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, Width
| 145 | Noisemove |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_145.gif) |  ⋮ ♫ | 🎨 Fx, Bg | Speed of perlin movement, Fade rate
| 126 | Octopus |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_126.gif) |  ▦ | 🎨  | Speed, Offset X, Offset Y, Legs
| 62 | Oscillate |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_062.gif) |  ⋮ |  | 
| 101 | Pacifica |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_101.gif) |  ⋮ | 🎨  | Speed, Angle
| 65 | Palette |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_065.gif) |  ⋮ | 🎨  | Cycle speed
| 98 | Percent |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_098.gif) |  ⋮ | 🎨 Fx, Bg | % of fill, One color
| 147 | Perlin Move |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_147.gif) |  ⋮ | 🎨 Fx, Bg | Speed, # of pixels, Fade rate
| 105 | Phased |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_105.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 109 | Phased Noise |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_109.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 128 | Pixels |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_128.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, # of pixels
| 129 | Pixelwave |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_129.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Speed, Sensitivity
| 97 | Plasma |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_097.gif) |  ⋮ | 🎨 Fx | Phase, Intensity
| 178 | Plasma Ball |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_178.gif) |  ▦ | 🎨  | Speed, Fade, Blur
| 133 | Plasmoid |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_133.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Phase, # of pixels
| 174 | Polar Lights |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_174.gif) |  ▦ |  | Speed, Scale
| 95 | Popcorn |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_095.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, Intensity, Overlay
| 63 | Pride 2015 |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_063.gif) |  ⋮ |  | Speed
| 144 | Puddlepeak |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_144.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, Puddle size, Select bin, Volume (min)
| 134 | Puddles |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_134.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, Puddle size
| 162 | Pulser |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_162.gif) |  ▦ | 🎨  | Speed, Blur
| 78 | Railway |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_078.gif) |  ⋮ | 🎨 1, 2 | Speed, Smoothness
| 43 | Rain |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_043.gif) |  ⋮ ▦ | 🎨 Fx, Bg | Speed, Spawning rate
| 9 | Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_009.gif) |  ⋮ | 🎨  | Speed, Size
| 33 | Rainbow Runner |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_033.gif) |  ⋮ | 🎨 Bg | Speed, Size
| 5 | Random Colors |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_005.gif) |  ⋮ | 🎨  | Speed, Fade time
| 79 | Ripple |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_079.gif) |  ⋮ ▦ | 🎨 Bg | Speed, Wave #, Overlay
| 148 | Ripple Peak |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_148.gif) |  ⋮ ♪ | 🎨 Fx, Bg | Fade rate, Max # of ripples, Select bin, Volume (min)
| 99 | Ripple Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_099.gif) |  ⋮ ▦ | 🎨  | Speed, Wave #
| 185 | Rocktaves |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_185.gif) |  ⋮ ♫ | 🎨 Fx, Bg | 
| 15 | Running |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_015.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Wave width
| 52 | Running Dual |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_052.gif) |  ⋮ | 🎨 L, Bg, R | Speed, Wave width
| 16 | Saw |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_016.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Width
| 10 | Scan |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_010.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, # of dots, Overlay
| 11 | Scan Dual |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_011.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, # of dots, Overlay
| 40 | Scanner |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_040.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Fade rate
| 60 | Scanner Dual |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_060.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, Fade rate
| 122 | Scrolling Text |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_122.gif) |  ▦ | 🎨 Fx, Bg, Gradient | Speed, Y Offset, Trail, Font size, Gradient, Overlay
| 181 | Sindots |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_181.gif) |  ▦ | 🎨  | Speed, Dot distance, Fade rate, Blur
| 108 | Sine |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_108.gif) |  ⋮ |  | 
| 92 | Sinelon |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_092.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, Trail
| 93 | Sinelon Dual |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_093.gif) |  ⋮ | 🎨 Fx, Bg, Cs | Speed, Trail
| 94 | Sinelon Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_094.gif) |  ⋮ | 🎨 Cs | Speed, Trail
| 125 | Soap |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_125.gif) |  ▦ | 🎨  | Speed, Smoothness
| 0 | Solid |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_000.gif) |  ⋮ |  | 
| 103 | Solid Glitter |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_103.gif) |  ⋮ | Bg, Glitter color | Intensity
| 83 | Solid Pattern |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_083.gif) |  ⋮ | 🎨 Fg, Bg | Fg size, Bg size
| 84 | Solid Pattern Tri |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_084.gif) |  ⋮ | 1, 2, 3 | Size
| 118 | Spaceships |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_118.gif) |  ▦ | 🎨  | Speed, Blur
| 20 | Sparkle |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_020.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Overlay
| 21 | Sparkle Dark |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_021.gif) |  ⋮ | 🎨 Bg, Fx | Speed, Intensity, Overlay
| 22 | Sparkle+ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_022.gif) |  ⋮ | 🎨 Bg, Fx | Speed, Intensity, Overlay
| 85 | Spots |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_085.gif) |  ⋮ | 🎨 Fx, Bg | Spread, Width, Overlay
| 86 | Spots Fade |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_086.gif) |  ⋮ | 🎨 Fx, Bg | Spread, Width, Overlay
| 150 | Squared Swirl |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_150.gif) |  ▦ | 🎨  | Blur
| 61 | Stream 2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM061.gif) |  ⋮ |  | Speed
| 39 | Stream ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM039.gif) |  ⋮ | 🎨  | Speed, Zone size
| 23 | Strobe |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_023.gif) |  ⋮ | 🎨 Fx, Bg | Speed
| 25 | Strobe Mega |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_025.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 24 | Strobe Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_024.gif) |  ⋮ | 🎨 Bg | Speed
| 166 | Sun Radiation |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_166.gif) |  ▦ |  | Variance, Brightness
| 104 | Sunrise |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_104.gif) |  ⋮ | 🎨  | Time [min], Width
| 6 | Sweep |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_006.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 36 | Sweep Random |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_036.gif) |  ⋮ | 🎨  | Speed
| 175 | Swirl |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_175.gif) |  ▦ ♪ | 🎨 Bg Swirl | Speed, Sensitivity, Blur
| 116 | TV Simulator |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_116.gif) |  ⋮ |  | Speed, Intensity
| 173 | Tartan |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_173.gif) |  ▦ | 🎨  | X scale, Y scale, Sharpness
| 44 | Tetrix |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_044.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Width, One color
| 13 | Theater |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_013.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Gap size
| 14 | Theater Rainbow |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_014.gif) |  ⋮ | 🎨 Bg | Speed, Gap size
| 35 | Traffic Light |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_035.gif) |  ⋮ | 🎨 Bg | Speed, US style
| 56 | Tri Fade |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_056.gif) |  ⋮ | 🎨 1, 2, 3 | Speed
| 55 | Tri Wipe |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_055.gif) |  ⋮ | 🎨 1, 2, 3 | Speed
| 17 | Twinkle |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_017.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 81 | Twinklecat |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_081.gif) |  ⋮ | 🎨  | Speed, Twinkle rate
| 80 | Twinklefox |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_080.gif) |  ⋮ | 🎨  | Speed, Twinkle rate
| 106 | Twinkleup |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_106.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 50 | Two Dots |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_050.gif) |  ⋮ | 🎨 1, 2, Bg | Speed, Dot size, Overlay
| 113 | Washing Machine |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_113.gif) |  ⋮ | 🎨  | Speed, Intensity
| 140 | Waterfall |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_140.gif) |  ⋮ ♫ | 🎨 Fx, Bg | Speed, Adjust color, Select bin, Volume (min)
| 165 | Waverly ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM165.gif) |  ▦ ♪ | 🎨  | Amplification, Sensitivity, No Clouds, Sound Pressure, AGC debug
| 184 | Wavesins |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_184.gif) |  ⋮ | 🎨 Fx | Speed, Brightness variation, Starting color, Range of colors, Color variation
| 127 | Waving Cell |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_127.gif) |  ▦ | 🎨  | Speed, Amplitude 1, Amplitude 2, Amplitude 3
| 3 | Wipe |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_003.gif) |  ⋮ | 🎨 Fx, Bg | Speed, Intensity
| 4 | Wipe Random |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_004.gif) |  ⋮ | 🎨  | Speed
| 207 | Y💡Big_Caleido ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM207.gif) |  ▦ |  | Speed
| 224 | Y💡Caleido1 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM224.gif) |  ▦ |  | Speed
| 223 | Y💡Caleido2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM223.gif) |  ▦ |  | Speed
| 222 | Y💡Caleido3 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM222.gif) |  ▦ |  | Speed
| 226 | Y💡Center_Field ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM226.gif) |  ▦ |  | Speed
| 228 | Y💡Chasing_Spirals ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM228.gif) |  ▦ |  | Speed
| 197 | Y💡Complex_Kaleido ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM197.gif) |  ▦ |  | Speed
| 196 | Y💡Complex_Kaleido_2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM196.gif) |  ▦ |  | Speed
| 195 | Y💡Complex_Kaleido_3 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM195.gif) |  ▦ |  | Speed
| 194 | Y💡Complex_Kaleido_4 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM194.gif) |  ▦ |  | Speed
| 193 | Y💡Complex_Kaleido_5 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM193.gif) |  ▦ |  | Speed
| 192 | Y💡Complex_Kaleido_6 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM192.gif) |  ▦ |  | Speed
| 225 | Y💡Distance_Experiment ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM225.gif) |  ▦ |  | Speed
| 216 | Y💡Hot_Blob ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM216.gif) |  ▦ |  | Speed
| 221 | Y💡Lava1 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM221.gif) |  ▦ |  | Speed
| 189 | Y💡Module_Experiment1 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM189.gif) |  ▦ |  | Speed
| 48 | Y💡Module_Experiment10 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM048.gif) |  ▦ |  | Speed
| 188 | Y💡Module_Experiment2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM188.gif) |  ▦ |  | Speed
| 171 | Y💡Module_Experiment3 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM171.gif) |  ▦ |  | Speed
| 169 | Y💡Module_Experiment4 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM169.gif) |  ▦ |  | Speed
| 161 | Y💡Module_Experiment5 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM161.gif) |  ▦ |  | Speed
| 151 | Y💡Module_Experiment6 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM151.gif) |  ▦ |  | Speed
| 142 | Y💡Module_Experiment7 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM142.gif) |  ▦ |  | Speed
| 114 | Y💡Module_Experiment8 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM114.gif) |  ▦ |  | Speed
| 53 | Y💡Module_Experiment9 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM053.gif) |  ▦ |  | Speed
| 190 | Y💡Parametric_Water ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM190.gif) |  ▦ |  | Speed
| 213 | Y💡Polar_Waves ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM213.gif) |  ▦ |  | Speed
| 212 | Y💡RGB_Blobs ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM212.gif) |  ▦ |  | Speed
| 211 | Y💡RGB_Blobs2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM211.gif) |  ▦ |  | Speed
| 210 | Y💡RGB_Blobs3 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM210.gif) |  ▦ |  | Speed
| 209 | Y💡RGB_Blobs4 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM209.gif) |  ▦ |  | Speed
| 208 | Y💡RGB_Blobs5 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM208.gif) |  ▦ |  | Speed
| 229 | Y💡Rotating_Blob ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM229.gif) |  ▦ |  | Speed
| 206 | Y💡SM1 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM206.gif) |  ▦ |  | Speed
| 198 | Y💡SM10 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM198.gif) |  ▦ |  | Speed
| 205 | Y💡SM2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM205.gif) |  ▦ |  | Speed
| 204 | Y💡SM3 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM204.gif) |  ▦ |  | Speed
| 203 | Y💡SM4 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM203.gif) |  ▦ |  | Speed
| 202 | Y💡SM5 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM202.gif) |  ▦ |  | Speed
| 201 | Y💡SM6 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM201.gif) |  ▦ |  | Speed
| 200 | Y💡SM8 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM200.gif) |  ▦ |  | Speed
| 199 | Y💡SM9 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM199.gif) |  ▦ |  | Speed
| 220 | Y💡Scaledemo1 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM220.gif) |  ▦ |  | Speed
| 214 | Y💡Slow_Fade ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM214.gif) |  ▦ |  | Speed
| 218 | Y💡Spiralus ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM218.gif) |  ▦ |  | Speed
| 217 | Y💡Spiralus2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM217.gif) |  ▦ |  | Speed
| 191 | Y💡Water ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM191.gif) |  ▦ |  | Speed
| 227 | Y💡Waves ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM227.gif) |  ▦ |  | Speed
| 219 | Y💡Yves ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM219.gif) |  ▦ |  | Speed
| 215 | Y💡Zoom ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM215.gif) |  ▦ |  | Speed
| 170 | Y💡Zoom2 ☾ |  <br /> ![](https://raw.githubusercontent.com/scottrbailey/WLED-Utils/master/gifs/FX_MM170.gif) |  ▦ |  | Speed
| 187 | ⚙️ ARTI-FX ☾ |  <br />  |  ⋮ | 🎨 Fx | Speed, Intensity, Custom 1,  Custom 2,  Custom 3


### Retired Effects

Some effects get retired when they can be recreated with newer, more general effects.

| Removed Effect  | Replacement                           | Retired After |
|-----------------|---------------------------------------|---------------|
| Candy Cane      | Chase 2                               | 0.14.0        |
| Dissolve Rnd    | Dissolve                              | 0.14.0        |
| Dynamic Smooth  | Dynamic                               | 0.14.0        |
| Halloween       | Chase 2                               | 0.14.0        |
 | Merry Christmas | Chase 2 - red/green                   | 0.12.0        |    
 | Police          | Two Dot                               | 0.14.0        |
 | Police All      | Two Dots - red/blue w/ full intensity | 0.13.0        |
 | Two Areas       | Two Dots - full intensity             | 0.13.0        |

