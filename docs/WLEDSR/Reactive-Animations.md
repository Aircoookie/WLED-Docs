
**Note 1:** Effects beginning with '*' are volume only and run on both ESP32 and ESP8266 (unless they are 2D).    
**Note 2:** Effects beginning with '**' use FFT (Fast Fourier Transforms) for frequency detection and only run on the ESP32.    
**Note 3:** We have also not added 2D animations to the ESP8266 platform.    
**Note 4:** The 2D routines require a minimum of 4 pixels in both directions. If you see blinking red, your 2D settings don't match the requirements. (not required in latest dev)  
**Note 5:** As we continue to develop SR WLED, some animations may appear or disappear. It's still a work very much in progress. Some may only appear in the dev branch for now.    
**Note 6:** In dev branch, sliders have been renamed from FFT Low to Custom 1, FFT High to Custom 2 and FFT Custom to Custom 3.    

See also [Non reactive animations](https://github.com/atuline/WLED/wiki/Non-Reactive-Animations)   

See [List of effects and palettes](https://github.com/Aircoookie/WLED/wiki/List-of-effects-and-palettes) for AC Animations.

See [ScottrBaileys GIF visualizer](https://github.com/scottrbailey/WLED-Utils/blob/main/effects_sr.md) for animations of the effects

| Effect | Description | Sliders
| :------------------ | --- | ---
| * 2D Swirl | Several blurred circles. Looks good with pink plasma palette. Supports AGC.  | **Speed:** Speed  <br/>**Intensity:** Sensitivity<br/>**FFT Low:** Blur
| * 2D Waverly | Noise waves with some sound | **Speed:** Amplification<br/>**Intensity:** Sensitivity
| * Gravcenter | Volume reactive vu-meter from center with gravity and perlin noise. | **Speed:** Rate of fall <br /> **Intensity:** Sensitivity
| * Gravcentric     |  Volume reactive vu-meter from center with gravity. Volume provides index to (time rotating) palette colour. | **Speed:** Rate of fall <br /> **Intensity:** Sensitivity
| * Gravimeter | Volume reactive vu-meter with gravity and perlin noise. | **Speed:** Rate of fall <br /> **Intensity:** Sensitivity
| * Juggles | Juggling balls.| **Speed:** Yes <br /> **Intensity:** # of balls
| * Matripix | Similar to Matrix. | **Speed:** yes <br /> **Intensity:** Brightness
| * Midnoise | Perlin noise emanating from center.| **Speed:** Fade rate <br /> **Intensity:** Maximum length
| * Noisefire | A perlin noise based volume reactive fire routine. | n/a
| * Noisemeter | Volume reactive vu-meter. | **Speed:** Fade rate <br /> **Intensity:** Width
| * Pixels | Random pixels. | **Speed:** Fade rate <br /> **Intensity:** # of pixels
| * Pixelwave | Pixels emanating from center. | **Speed:** yes <br /> **Intensity:** Sensitivity
| * Plasmoid | Sine wave based plasma. | **Intensity:** # of pixels
| * Puddlepeak | Blast coloured puddles randomly up and down the strand with the 'beat'. |**Speed:** Adjust fade rate.<br /> **Intensity:** Size of puddles<br /> **FFT High:** 256 freq bin select on ESP32.<br /> **FFT Custom:** Volume comparator on ESP32
| * Puddles | Blast coloured puddles based on volume.| **Speed:** Fade rate <br /> **Intensity:** Size of puddle
| * Ripple Peak | Peak detection triggers ripples. | **Intensity:** Max number of ripples.<br /> **FFT High:** 256 freq bin select on ESP32<br /> **FFT Custom:** Volume comparator on ESP32
| * Waterfall | A volume AND FFT version of a Waterfall that has 'beat' support.| **Speed:** Speed <br /> **Intensity:** Adjust colour
| ** 2D CenterBars | A 16x16 spectral analysis routine emanating from the center | **Speed:** Bar Speed <br /> **Intensity:** Ripple time<br /> **FFT Custom1:** Center horizontally<br /> **FFT Custom2:** Center vertically<br /> **FFT Custom3:** Color vertically
| ** 2D Funky Plank | A 2D wall of reactivity running from bottom to top | **Speed:** Scroll Speed <br /> **FFT Custom1:** Number of bands
| ** 2D GEQ | A 16x16 graphic equalizer. | **Speed:** Bar Speed <br /> **Intensity:** Ripple time<br />**FFT Custom1:** Number of bands
| ** Binmap | Map bins 3-255 throughout the length of the LEDs. This does not work with UDP sync.<br />Values are not normalized.| **Intensity:** Max volume 
| ** Blurz  | Flash an fftResult bin per frame and then blur/fade. | **Speed:** Fade Rate<br /> **Intensity:** Blurring
| ** DJLight | An effect emanating from the center to the edges. | **Speed:** Speed
| ** Freqmap | Map the loudest frequency throughout the length of the LED's.|**Speed:** Fade rate<br />**Intensity:** Starting colour 
| ** Freqmatrix | See below | See below
| ** Freqpixels | Random pixels coloured by frequency. |**Speed:** Fade rate<br />**Intensity:** Starting colour and number of pixels
| ** Freqwave | See below | See below
| ** Gravfreq | VU Meter from center. Log of frequency is index to center colour. | **Speed:** Rate of fall<br />**Intensity:** Sensitivity
| ** Noisemove | Using perlin noise as movement for different frequency bins. |**Speed:** Speed of perlin movement <br /> **Intensity:** Fade rate
| ** Rocktaves | Colours the same for each note between octaves, with sine wave going back and forth. |**Speed:** n/a<br />**Intensity:** n/a
| ** Waterfall | FFT version of a Waterfall.| **Speed:** Speed <br /> **Intensity:** Adjust colour<br />**FFT High:** 256 freq bin select on ESP32<br /> **FFT Custom:** Volume comparator on ESP32
| ** DJ Light|tbd|
| ** 2D Akemi|tbd|

## Slider Usage
Please see the brief slider descripion for each effect in the rightmost column above.

### Speed/Intensity
These typically reflect the value of their namesake. Intensity would typically be number of LED's lit, or brightness of the LED's

### FFT Sliders
These may get renamed in the future and could be used for FFT routines OR for additional effect adjustments.

## Peak Detection
This is NOT beat detection, but rather samples that are louder than a the current average plus a slider adjustable value.

## Automatic Gain Control
We are just beginning to add Automatic Gain Control to the routines, starting with 2D Swirl. This setting is only available on the LED Preferences page on the ESP32.

## FFT Routines


## Additional effect notes

### Freqmatrix 
The temporal tail for this animation starts at the beginning of the Segment rather than in the center of the segment.

**Sliders used:**

Slider usage is described in the rightmost column for each effect. In general, the sliders are configured for:

1. **Speed:** This determines the time delay before each pixel is moved down the line.
1. **Intensity:** This determines how _MUCH_ the sound input affects the selected effect.
1. **FFT Low:** Can be an additional adjustment. Can also select low end of frequency bins if used by that effect.
1. **FFT High:** Can be an additional adjustment. Can also select high end of frequency bins if used by that effect.
1. **FFT Custom:** Can be an addiitional adjustment.

### Freqwave
This effect maps the major frequencies from the incoming signal to colors in the HSV color space. From the low notes being mapped to red (0) to the high notes being mapped to blue (255) and everything in between. The band you are looking at can be restricted by the FFT Low and FFT High sliders. We are digitizing at 10240Hz, meaning the highest frequency bin that you can find is 5120Hz, which for most music is just fine.
 
**Sliders used:**

1. **Speed:** This determines the time delay before each pixel is moved down the line.
1. **Intensity:** This determines how _MUCH_ the sound input affects the selected effect.
1. **FFT Low:** The low cut off for the FFT bins. Values range from 0-100. Good values are from 0 to 10
1. **FFT High:** High cut off for the FFT bins. Values range from 0-100. This is important because every type of music is different and what is considered a high note in one type of music is not the case in others. 
1. **FFT Custom:** This slider works similarly to a **"pre-amp"** for the input signal. The possible values for this slider are 1-10. A good starting point for this is around 2-3.


