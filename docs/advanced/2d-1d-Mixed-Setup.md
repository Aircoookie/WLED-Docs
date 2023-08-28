---
title: 2D and 1D Mixed Setup
hide:
  # - navigation
  # - toc
---

## Overview

WLED supports mixing 2D and 1D setup on the same unit, the expected result is that you could use 2D fixture and still chain a strip after or setup a strip and then a matrix after on the same pin. 

Setup your leds count in Config, LED Preferences as usual, for example 8x8 matrix and a strip of 30 pixels chained at the end of your matrix, total count should be 64 + 30 =94. 
 
Go to Config, 2D setup page and create an 8x8 matrix, and then go to the segments, the 8x8 segments should be created automatically. For the 1D strip, add a new segment with the start pixel beyond the matrix, and it will automatically change to a 1D segment, as in this example 

<img width="448" alt="image" src="https://github.com/dosipod/WLED-Docs/blob/master/docs/assets/images/content/2D-1D-MIX.png ">

Note: If the matrix is chained after the strip, then use reversing at the bus level, i.e. check Reversed (rotated 180°) in LED & Hardware setup 
