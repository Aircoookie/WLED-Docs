## Changing Web UI 

In order to conserve space, Web UI interface are represented as a series of wled00/html_ui.h, wled00/html_settings.h and wled00/html_other.h files which contain C/C++ strings with specific parts of the Web UI.

These files are automatically created from source files available in wled00/data folder. To generate files, install [NodeJS 11.0+ globally](https://nodejs.org/en/download/). After that, recreate html_*.h files by running in the repo directory:

```bash
> npm install
> npm run build
```

If you want to test changes to the UI, it is easiest to work with the local wled00/data/index.htm file. You just need to enter the IP address of a WLED 0.10.0 or newer instance into the popup. If you accidentally input an incorrect IP or want to test with a different instance, clear the local storage (in Chrome: Developer Tools -> Application -> Local Storage)

If you continuously modify files in the wled00/data directory, you want to monitor these changes to make local html_*.h files being updated automatically. To do this, run this in repo directory: 

```bash
> npm run dev
```

This will start monitoring wled00/data folder for changes.

**WARNING!!!** Be careful with changing the javascript in HTML files! For example `function GetV() {}` must be the *last* javascript function in the `<script>` element as it will be replaced by automatically generated code to fetch relevant settings from EEPROM. See tools/cdata.js for the replacement rules which run for every *.htm file in wled00/data.