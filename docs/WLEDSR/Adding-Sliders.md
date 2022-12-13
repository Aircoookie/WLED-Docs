## Introduction
This page provides WLED programmers information on adding another slider to WLED. This information is not yet complete, as it doesn't yet deal with icons, EEPROM or IR. I will also be researching how to programmatically show/hide these sliders.

## Updating html_ui.h

Please see [https://github.com/atuline/WLED/wiki/Modifying-Sound-Reactive-WLED](https://github.com/atuline/WLED/wiki/Modifying-Sound-Reactive-WLED) on how to generate html_ui.h since the UI was changed in v0.10.0-alpha-lw.

***

**The information below describes the way html_ui.h was generated before the UI change and is deprecated.**

This file is compressed and is taken from data\index.htm. Please see Aircoookie's page on 'adding your own effect:

https://github.com/Aircoookie/WLED/wiki/Add-own-functionality

To serve your changes by the internal webserver, you will need to follow these or similar steps to gzip compress the index.html file:

1. Gzip compress the file. I use this online converter, use setting Compress this file, output – gz
1. Rename file to xxx.gz.png (change file type to image)
1. Convert it to a C-style byte/char array. I use this converter, intended for image sprites. Therefore, the previous step of changing the file format was neccessary. Select Raw as Color format.
1. Open the downloaded .c file in a text editor, e. g. Notepad++. Select the contents of the array and replace the array contents in html_ui.h with them.
1. Update PAGE_index_L to the binary size stated in the bottom of the downloaded .c file
Recompile and flash WLED!

Here's a link to my Google document containing the changes required:

https://docs.google.com/document/d/1m6dm3O_aXgJLGDJfM6E-4CHzzvU8bsaHqrs7VmisYko/edit