---
title: Presets
hide:
  # - navigation
  # - toc
---

Presets can be used to save your favorite light configurations to apply later!
You can compare them to the "scenes" feature present in some other smart devices.

### New version (0.11+)

#### Overview

WLED 0.11.0 contains a major overhaul of presets, storing them in a `/presets.json` file in an internal filesystem.  
This enables many new features, you can now have up to 250 presets and each of them can save all segments which are set up!  
Speaking of segments, the maximum number has been increased to 12 on ESP8266 and 16 on ESP32!  
Presets can now also contain both HTTP and JSON API commands, replacing the previous Macro functionality.  
Each preset can be named, so you'll be able to access it more easily!  

#### How to use

The new preset system is quite a bit more advanced than the previous one, thus it is likely not as self-explanatory to use.  
Here you can find what each setting does and how to make best use of it!

*"Create Preset" button*  
Use this to save the current state as a permanent preset, or to add a new API macro.

*Preset name*  
Enter a nice name for your preset here. I would recommend putting something short, but to the point here, like `Epic fireworks` or `Slow fade`.  
All special characters and emoji are permitted (however, there must not be more than 6 consecutive whitespaces)  
If you leave this empty, you'll get a name based on the preset ID number, like `Preset 16`.

*Quick load label*  
You can optionally add a short label up to 2 characters or 1 emoji long.  
It will show up in a small circle on top of the preset list for extra quick access without scrolling!  
I recommend using this for the presets you truly love.  

*Use current state/Overwrite with state*  
This is enabled by default when adding a new preset and disabled when editing an existing preset.  
When enabled, it will write the current segment config, including all colors and effect, to the preset.  
When disabled, it will instead give you a textfield to enter a custom API command or show you the command currently saved.  

*Include brightness*  
If disabled, the brightness value is not included in the preset. This can be useful e.g. when you want to control the brightness manually and want the preset to only set the effect.

*Save segment bounds*  
This is an important one. Make sure it is enabled for your boot preset, so that your segment config is properly restored on boot!  
When disabled, the segment start and stop LEDs are not included in the preset. This can be useful if you plan to make changes to your segment setup and don't want your presets to always reset it to the point it was when the preset was saved.

*API command*  
This accepts any HTTP or JSON API command! (only visible if the current state checkbox is unchecked)  
It replaces the previous macro functionality.  
If you know your JSON, you can even create playlists of other presets!

*Save to ID*  
This is the ID the preset will be saved to.  
When creating a new preset, you likely won't have to change it as the lowest unused ID will be chosen automatically.  
If you change the ID on an existing preset and save, you can copy it to the new ID - change the name though.  

*Save and Delete buttons*  
Now these are self-explanatory, but I said I'd cover each point :)

*ID*  
This is the number you'll want to use to apply this preset from a timed macro or automation!  

#### A note on performance

This new preset system is quite fast where it matters, reading the presets.  
Applying a preset will typically take less than a tenth of a second.  

However, due to a design choice of the LittleFS filesystem used by WLED, random writes to the preset file are very resource intensive.  
This means that while updating your presets, you might notice your light freezing and becoming unresponsive for up to a few seconds.  
Adding new presets is usually very fast, those performance issues will occur once you delete/edit/overwrite older presets and your preset file becomes very large, or when adding presets after deleting older ones.

I'm looking into ways to mitigate this situation as soon as possible! Meanwhile, to keep things snappy, I would recommend not having more than 50-ish single segment or a dozen of multi-segment presets.

#### What about my cool presets from earlier versions?

Don't worry, they (as well as your settings) will be automatically imported to the new system!  
And if you ever need to downgrade to v0.10 for some reason, they will still be there (although any changes made in v0.11 won't be applied)

#### Obtaining preset list

Obtaining the preset list is possible with the /presets.json file
Seeing the name of the current preset with the API only is not possible, you can only obtain its ID. Then you'd need some code to match it with the entries from presets.json (this is also what the UI does).  See section "Backing up/restoring presets".

#### Saving named presets

Save a named preset with `{"psave":<preset number here>;"n":"Preset name","ib":true,"sb":true}`

#### Backing up/restoring presets

To backup all presets, go to `[WLED-IP]/edit` (OTA lock must be off), right click the `presets.json` file and download!  
To restore, use the `Choose file` and `Upload` buttons.  

#### Applying presets at a certain time of day

!!! tip
    If you want to create a preset that turns on the light to the last effect displayed, uncheck `Use current state` and enter `T=1` into the API Command field.
    
WLED supports schedules - that is, applying presets at a certain time automatically.  
Here is a simple guide to get it set up quickly!  

- Creates the preset(s) you want to load at specific time(s)  
- Note the preset ID - the small gray number to the left of the preset name (or, in the bottom of the preset menu)  
- Go to the `Time & Macros` section in the WLED settings.  
- Make sure the time displayed is correct and accurate. It is highly recommended to enable NTP for a reliable schedule. Do not forget to set the correct timezone.
If applicable, daylight saving time is handled automatically.  
- Scroll down to `Time-controlled presets`. There are 8 different timer slots available.  
- Enter the hour, minute, and weekdays you want the preset to activate. In the `Preset` column, enter the preset ID you noted earlier.  
- Save the settings page! You have successfully set up a schedule :)  

!!! info "Note"
    This only applies the preset at the _start_ of the specified minute. If you set up two presets, one to turn on the light at 7 and another to turn it off at 8,
    if WLED is booted at 7:30, the light will not turn on. This should not be an issue in most applications.
    
#### Applying presets at sunrise and sunset
    
Applying a preset at sunrise and/or sunset is also supported, the last two timed preset slots are used for this.  
To calculate the times, WLED needs your location. This is possible with the "Get Location" button in Time & Macro settings if accessed via a browser. If you are using the WLED app, you will need to open [locate.wled.me](https://locate.wled.me/) in your browser and copy the coordinates over to the settings page manually.  
With the Minutes input field, you may specify an offset of up to 59 minutes before or 59 minutes after the actual sunrise/set time.

!!! warning "Location"
    Sunrise and sunset calculation do not work if you live in the polar circles (latitude >66.6N or >66.6S).

### Earlier versions (up to 0.10)

There are 16 preset slots in total.
In 0.9.0, the last preset (16) is capable of saving the entire segment configuration. All other presets only save a single segment (main segment, the first one by default) and restore that preset to all selected segments.

In the Favorites tab, the number buttons from 1-16 are the different save slots. Find a config you like, then toggle _Saving mode_ on and click on a number to save the preset to that slot. If _Saving mode_ is toggled off, you can restore presets with a single click.

### Preset cycle (up to 0.12.1)

With this feature, you can create an animation by automatically swapping between presets within a specified range.
Keep in mind that any changes you make to effects/colors will be overridden once the system applies the next preset.

If you want to start the preset cycle on boot, go to LED settings and tick "Save current preset cycle configuration as boot default

To modify the duration of the preset cycle, ensure the preset cycle box is unchecked before entering a new time value. Once updated, the preset cycle can be enabled again"

Playlists supersede Preset cycle in 0.13.
