## Introduction
This page outlines the methods we used and the files that must be modified to add a Sound Settings page to the WLED UI.

## NEW settings_sound.htm
I first added a new file in the data folder named `settings_sound.htm`. I did a copy/paste from `settings_leds.htm` to have a base for the new settings page. Let's break down this file.
* At the top, we have our standard HTML beginning lines with the TITLE of the page between the `<title>` tags.
* Inside of the `<script>` tags we have a few functions that are necessary for the page to function.
* `function H()` is our help button function. When called, the UI will direct you to the relevant wiki page inside the `window.open()` function.
* `function B()` is our back button function. When called, the UI will direct you to the previous main settings page via `window.open("/settings","_self")`.
* `function GetV()` injects the values from the relevant settings stored in EEPROM to the settings page.
* Inside the `<style>` tag we `@import` the relevant `style.css` file. This closes our `<head>` tag.
* When the body of the page is loaded, function `GetV()` is called. This can vary depending on the functions that need to be called when the page loads.
* Inside the `<body>` tag we have our form. This form holds the layout for the settings page. 
  * Our squelch and gain settings have the names "SQ" and "GN" respectively. These names refer to the name given to the setting in `xml.cpp` and are used to retrieve and save these settings from/to EEPROM.

## Modify settings.htm
This file holds the settings page button layout. We want to add an entry so we can access our new settings page. This was pretty straight forward. I added the following line, in the position I wanted it to appear on the page, using the previous entries as an example.
```html
<form action="/settings/sound"><button type="submit">Sound Settings</button></form>
```
I also made some changes to the style of the buttons so they all show on the same page. This was not necessary but I feel it gave a more polished look.

## Modify xml.cpp
This is our map, so to speak. Each setting is given a unique 2 character string that will be used to reference it in the UI. In our case, "SQ" and "GN". This file is also the map for the XML response when querying the API. Our settings aren't used in the API at this time so I won't go into that right now.

There are two important functions in xml.cpp that relates to our task which are `void sappend()` and `void sappends()`
* `sappend()` takes a numeric setting and appends it to the string buffer. Valid cases for this function are:
  * 'c', a check box
  * 'v', a numeric value
  * 'i', the selected index
* `sappends()` takes a string setting and appends it to the string buffer. Valid cases for this function are:
  * 's', a string setting
  * 'm', a message to be displayed

Around line 192 in xml.cpp we have the function `getSettingsJS()` which retrieves the settings values from EEPROM based on the current sub-page which is defined in wled_server.cpp.

We want to add a sub-page so we need to change the following line from `if (subPage <1 || subPage >7)` to `if (subPage <1 || subPage >8)`. At the end of this function, after the last sub-page (previously 7) we have the following code block around line 522:
```cpp
if (subPage == 8)
{
  sappend('v',"SQ",soundSquelch);
  sappend('v',"GN",sampleGain);
  }
```
Here we can see our SQ and GN settings are loaded from EEPROM and filled in to their respective form field using the v case from the `sappend()` function.

## Modify set.cpp
This file handles storing the settings entered into EEPROM. Similar to xml.cpp, we want to add a settings page so we need to tell WLED there is an additional page in the `handleSettingsSet()` function. I changed the following line from `if (subPage <1 || subPage >7) return;` to `if (subPage <1 || subPage >8) return;`. 

Lastly, I added the following code block after the last defined sub-page around line 361:
```cpp
//SOUND SETTINGS
if (subPage == 8)
{
  int t;
  t = request->arg("SQ").toInt();
  if (t > 0) soundSquelch = t;
  t = request->arg("GN").toInt();
  if (t > 0) sampleGain = t;
}
```

## Modify wled_server.cpp
This file serves the webpage for the WLED frontend. We want to _add_ a settings page so we will add the following block of code around line 82, using the previous block as an example. Notice the sub-page defined in xml.cpp is referenced as well as the NEW setting page URL defined in settings.htm.
```cpp
// add sound settings page
server.on("/settings/sound", HTTP_POST, [](AsyncWebServerRequest *request){
  handleSettingsSet(request, 8);
  serveMessage(request, 200,F("Sound settings saved."),"Redirecting...",1);
});
```
In the `serveSettings()` function around line 383 we need to add `else if (url.indexOf("sound")> 0) subPage = 8;  // add sound settings page`, so the webserver knows to load those settings. 

And finally we need to add a case around line 406 for our new sub-page like this `case 8:   request->send_P(200, "text/html", PAGE_settings_sound, settingsProcessor); break;`.

## Modify cdata.js
Finally, we need to add our new settings page to `cdata.js` in the tools folder. This file holds the framework for modifying the compressed `*.h` files that serve the WLED frontend. This is the file nodejs looks to when running `npm run build` to compress the `*.htm` files in the data folder into `*.h` files which are compiled with the firmware.

I used the previous entries as an example and added the following code block around line 243:
```js
{
  file: "settings_sound.htm",
  name: "PAGE_settings_sound",
  prepend: "=====(",
  append: ")=====",
  method: "plaintext",
  filter: "html-minify",
  mangle: (str) =>
    str
      .replace(/\<link rel="stylesheet".*\>/gms, "")
      .replace(/\<style\>.*\<\/style\>/gms, "%CSS%%SCSS%")
      .replace(
        /function GetV().*\<\/script\>/gms,
        "function GetV() {var d=document;\n"
      ),
},
```

Those are the steps I took to modify the WLED settings pages and add a page for the sound reactive related settings in the UI. Once those were completed, I ran `npm install` and `npm run build` to compress the new UI and include it in the firmware. After compiling the new firmware, I needed to reset the EEPROM via `http://WLED/settings/sec?` -> Factory reset.