---
title: 2D and 1D Mixed Setup
hide:
  # - navigation
  # - toc
---

## Overview

WLED supports mixing 2D and 1D setup on the same unit, the expected result is that you could use 2D fixture and still chain a strip after or setup a strip and then a matrix after on the same pin. 

1. Setup your total LED count in Config -> LED Preferences as usual. For example a 8x8 matrix and a strip of 30 pixels chained to the end of your matrix. The total count should be 64 + 30 = 94. This also works with virtual LEDs via DDP or ArtNet. 
2. Go to Config -> 2D setup and create the 8x8 matrix
3. Go back to edit the segments. The 8x8 segments should be created automatically. Add a new Segment. Initially the form will be for creating a new Matrix.
4. In the "Start X" field enter a number larger or equal to the total LEDS in the matrix. In this example you should enter 64 (8 x 8). The form will automatically change to display that of a 1D segment. 

<img width="448" alt="example" src="/assets/images/content/2D-1D-MIX.png">

Note: If the matrix is chained after the strip, then use reversing at the bus level, i.e. check Reversed (rotated 180°) in LED & Hardware setup. This may also require you reverse segment.
