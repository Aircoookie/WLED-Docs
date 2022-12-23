---
title: Custom Access Point SSID and Password
hide:
  # - navigation
  # - toc
---

!!! warning
    _Note: These options change the documented access point name and password. The WLED community does not recommend changing these settings unless you are familiar with the risks._

Three compile time defines are available to modify the access point name. These are `WLED_AP_SSID`, `WLED_AP_PASS`, and `WLED_AP_SSID_UNIQUE`. Defining `WLED_AP_SSID` will set the SSID to the value of the define. Defining `WLED_AP_PASS` will set the password to the value of the define. Defining `WLED_AP_SSID_UNIQUE` will append the last 6 digits of the MAC address to the SSID.

`WLED_AP_SSID` and `WLED_AP_PASS` are string values, and as such need to be defined with `"` surrounding them. For example, `#define WLED_AP_SSID "MyWLED"` or `-D WLED_AP_SSID='"MyWLED"'` in the `build_flags` of `platformio.ini`.

### Modifying the Access Point SSID
Defining `WLED_AP_SSID` will set the SSID to the value of the define. This is useful to set a device specific access point name. For example, if you have multiple WLED devices, you can set the SSID to the device name.

`WLED_AP_SSID` is a string value, and as such needs to be defined with `"` surrounding it. For example, `#define WLED_AP_SSID "MyWLED"` or `-D WLED_AP_SSID='"MyWLED"'` in the `build_flags` of `platformio.ini`.

### Modifying the Access Point Password
Defining `WLED_AP_PASS` will set the password to the value of the define. This is useful to set a device specific access point password. For example, if you have multiple WLED devices, you can set the password to the device name.

!!! tip
If `WLED_AP_PASS` is defined, but `WLED_AP_SSID` is not, the compilation will fail. Ensure you define both `WLED_AP_SSID` and `WLED_AP_PASS` if you wish to change the access point password. Please also change the SSID if you wish to set a custom password.

`WLED_AP_PASS` is a string value, and as such needs to be defined with `"` surrounding it. For example, `#define WLED_AP_PASS "MyWLEDPass"` or `-D WLED_AP_PASS='"MyWLEDPass"'` in the `build_flags` of `platformio.ini`.

### Modifying the Access Point SSID to be Unique
Defining `WLED_AP_SSID_UNIQUE` will append the last 6 digits of the MAC address to the SSID. This is useful to set a device specific access point name with a common prefix. For example, if you have multiple WLED devices, you can set the SSID to `ChristmasTree-` followed by the last 6 digits of the MAC address.

`WLED_AP_SSID_UNIQUE` is a boolean value, and as such only needs to be defined or not. For example, `#define WLED_AP_SSID_UNIQUE` or `-D WLED_AP_SSID_UNIQUE` in the `build_flags` of `platformio.ini`.

### Example

For custom devices in `platformio_override.ini`:

```ini
[env:mywled]
board = esp32dev
platform = ${esp32.platform}
platform_packages = ${esp32.platform_packages}
build_unflags = ${common.build_unflags}
build_flags =
    ${common.build_flags_esp32}
    -D WLED_AP_SSID_UNIQUE
    -D WLED_AP_SSID='"MyWLED"'
    -D WLED_AP_PASS='"MyWLEDPass"'
lib_deps = ${esp32.lib_deps}
monitor_filters = esp32_exception_decoder
board_build.partitions = ${esp32.default_partitions}
```

In `my_config.h`:

```cpp
#define WLED_AP_SSID_UNIQUE
#define WLED_AP_SSID "MyWLED"
#define WLED_AP_PASS "MyWLEDPass"
```
