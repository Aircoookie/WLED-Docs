This page has moved to https://moonmodules.github.io/WLED-Docs/2D/introduction/

Do not edit below!!

## Introduction

In order to accommodate 2D effects we have modified how Segment settings are used and added 2D Matrix and panel variables on the [Led Preferences](https://github.com/atuline/WLED/wiki/LED-Preferences) settings.
Note: Currently only working in dev. You are invited to test this and give feedback on [Beta testing discord channel](https://discord.com/channels/700041398778331156/700701772838207640)

## 2D architecture

WLED SR distinguishes between the following levels
* 2D Segment (dev)
* 2D Matrix (dev)
* 2D Panel (dev)

An effect is plotted on a segment. A segment is a rectangle on a matrix (logical level). A matrix is implemented by one or more identical led panels,  with a specific layout (e.g. first led bottom left, serpentine, physical level).

Note: 2D effects can also be projected on a 1D LED Strip instead of a 2D Panel. e.g. for a led strip of 144 leds you can define width=height=12 and each zone of 12 leds is a row of a matrix. Rows are then side by side instead of above each other. Some 2D effects, e.g. graphic equalizer look still pretty cool on strips (as is the other way around with 1D effects on a 2D matrix like NoiseMove or Sparkle).

## 2D Segments
As WLED supports multiple segments, all effects and therefore also 2D effects are first projected on a segment. In [1D, a segment is a zone on a LED strip](https://github.com/Aircoookie/WLED/wiki/Segments) and is specified by Start Led and a Stop Led (note that Stop Led is one led after the last led in the segment).

In 2D, a segment is a rectangle on a 2D matrix and 2D effects plot on this rectangle using x,y coordinates of the SEGMENT.
A rectangle can be defined in the Segment UI where the start led specifies the top-left and the stop led specifies the bottom-right of the rectangle.
Multiple segments can be specified this way. Segments can overlap. In fact overlapping creates very nice effects.

See [Segment start stop charts](https://github.com/atuline/WLED/wiki/2D-Support#2d-segment-start-stop-charts) to easy find matrix start and stop values

### Rotation and ReverseX/Y
A segment can be rotated 90º degrees and reversed on the X or Y-axis and can be specified in the Segment-UI. The SegmentRotation branch of dev supports this and is currently in beta-test. This will move to dev and release over time.

The following table shows the effect setting these values:

Value | Rotation | Reverse X | Reverse Y| Effect
|---|---|---|---|---|
0|-|-|-|0º rotation and no reverse
1|-|-|+|Reverse horizontal
2|-|+|-|Reverse vertical
3|-|+|+|180º rotation
4|+|-|-|90º rotation
5|+|-|+|90º and reverse horizontal
6|+|+|-|90º and vertical
7|+|+|+|270º rotation

## 2D Matrices and panels

See [Led Preferences](https://github.com/atuline/WLED/wiki/LED-Preferences)

## Technical

* CRGB leds[MAX_LEDS+1]; in FX.cpp defines all leds on the matrix. Multiple segments share this array and effects should only write to leds[] within the boundaries of a segment. This is done by calling leds[XY(x,y)] or leds[realPixelIndex(i)].
* Functions with leds as parameter should follow above rule and have been refactored for this. E.g. fadeToBlackBy(leds, 32) or fill_solid(leds, 0) otherwise it writes outside the segment boundaries. 

## 2D Segment start stop charts
### 16x16 matrix
![6 - 8x32 panels](https://github.com/atuline/WLED/blob/assets/media/2Dsegmentstartstop1616.png?raw=true)

### 32x32 matrix
![6 - 8x32 panels](https://github.com/atuline/WLED/blob/assets/media/2Dsegmentstartstop3232.png?raw=true)
(Created by Harry Baas)

## Examples

### 16x16 matrix
To get the (x,y) coordinates from the start and stop led:
* Segment top left = (start%matrixWidth, start/matrixWidth)
* Segment bottom right = (stop%matrixWidth, stop/matrixWidth)

Example of 1 segment (default) covering a whole 16x16 matrix:
* start = 0, stop = 255
* top left = (0,0)
* bottom right = (15,15)
* width = height = 16

Example of a segment covering a middle part rectangle of the 16x16 matrix:
* start = 20, stop = 235
* top left = (4,1)
* bottom right = (10,14)
* width = 7
* height = 14

Example of a segment covering the left part of the 16x16 matrix:
* start = 0, stop = 241
* top left = (0,0)
* bottom right = (0,15)
* width = 1
* height = 16

### 16 x 12 matrix

matrixWidth = 16, matrixHeight = 12.

Total led count 192 leds

left and right binmap effect. In the middle noisemove.

* Segment 0 (middle): start=1, stop=191, effect=noisemove
* Segment 1 (left): start=0, stop=176, effect=binmap
* Segment 2 (right): start=15, stop=192, effect=binmap

## Api commands for 2D effects
### 16 segments for 32x32 matrices
Add the following Api command into a preset. This will show the Saw effect rotated and reversed in 16 8*8 segments. 

After that you, if you select all 16 segments and select another effect, this effect will also be populated to all 16 segments, resulting in surprising new effects


`{"on":true,"bri":89,"transition":7,"mainseg":0,"seg":[{"id":0,"start":0,"stop":232,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":false,"mi":false,"rot2D":false},{"id":1,"start":8,"stop":240,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":false,"mi":false,"rot2D":false},{"id":2,"start":16,"stop":248,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":false,"mi":false,"rot2D":false},{"id":3,"start":24,"stop":256,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":false,"mi":false,"rot2D":false},{"id":4,"start":256,"stop":488,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":true,"mi":false,"rot2D":false},{"id":5,"start":264,"stop":496,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":true,"mi":false,"rot2D":false},{"id":6,"start":272,"stop":504,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":true,"mi":false,"rot2D":false},{"id":7,"start":280,"stop":512,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":true,"mi":false,"rot2D":false},{"id":8,"start":512,"stop":744,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":false,"mi":false,"rot2D":false},{"id":9,"start":520,"stop":752,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":false,"mi":false,"rot2D":false},{"id":10,"start":528,"stop":760,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":false,"mi":false,"rot2D":false},{"id":11,"start":536,"stop":768,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":false,"mi":false,"rot2D":false},{"id":12,"start":768,"stop":1000,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":true,"mi":false,"rot2D":false},{"id":13,"start":776,"stop":1008,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":true,"mi":false,"rot2D":false},{"id":14,"start":784,"stop":1016,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":false,"rev2D":true,"mi":false,"rot2D":false},{"id":15,"start":792,"stop":1024,"grp":1,"spc":0,"on":true,"bri":255,"col":[[255,0,0],[59,42,27],[0,0,255]],"fx":16,"sx":47,"ix":142,"f1x":89,"f2x":74,"f3x":111,"pal":12,"sel":true,"rev":true,"rev2D":true,"mi":false,"rot2D":false},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0},{"stop":0}]}`
