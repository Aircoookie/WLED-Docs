We learned a long time ago that adding new code can make for a LOT of testing. If you offer to help out with this fork, please keep in mind that we support:

* Several different analog microphones and some in different configurations (ie MAX9814), each of which need to be tested.
* Line-in, with different possible line-in levels.
* The digital INMP441 and ICS-43434 microphones.
* Sampling for both volume and FFT calculations.
* Volume, peak and FFT based animations.
* Up to 5 sliders for each animation.
* 1D and 2D routines.
* UDP sound synchronization.
* Settings for gain, squelch, sliders, UDP sync and 2D layout.
* EEPROM code to save/load those settings.
* A dedicated sound reactive settings web page.
* ESP32 and ESP8266 based devices.
* Support for both the Arduino IDE as well as Platform IO.
* Supporting both AP mode as well as STA mode for WiFi.
* A dev branch for the latest code for ESP32.
* An ESP8266 branch for volume only routines.
* A master branch, which gets occasionally gets merged with AC's master by one of our team members. New development happens on our 'dev' branch.
* SEGMENTS. Every routine must be compatible and tested for SEGMENTS.
* Try and keeping our fork current with the original WLED.
* Our Flash usage is now FULL. Prior to adding anything new, we either need to free up the same or larger space elsewhere, typically other animations.

If you'd like to contribute, you would need to be able to perform a significant amount of testing and future maintenance (see above) so your new code doesn't unintentionally break other functionality.

## What functionality to add:

* Is the addition specific to sound reactive WLED or should it be a part of regular WLED?
* Will the proposed addition break potential future WLED functionality?
* Can other members of the team support this added functionality in the future?
* Is the code clear and concise?

## In addition:

* Good communication with team members is very important. Join our [discord](https://discord.gg/4CQRmfR).
* Pull Requests and any changes should first go into our `dev` branch! Do not create a PR for `master` unless there is a very good reason.
* Keep any git update to a limited topic for ease of testing/rollback.
* Keep the Wiki documentation in 'good order'.
* Technical support for a long enough period of time to ensure your code is fully tested, the UI is fine, and supportable by others.
* Commitment. You're really keen on WLED and have a long term commitment to support the community.


## Knowledge That Helps:

* Github versioning, commits, branching, merging.
* FastLED (for animations), combined with NeoPixelBus.
* Junior/intermediate level C programming. Please use the opportunity for a code review by making pull requests.
* HTML, CSS, Javascript, XML, JSON, npm for any UI changes.
* WLED coding standards.

We still have the occasional issue with our dev/master branches where we lose connectivity with the web server. This was most prevalent with the ESP8266 branch in AP mode, and precipitated a re-write for that platform. As a result of this ongoing issue, we are sensitive to new functionality being added without adequate testing.

In conclusion, the most important factors are commitment, teamwork, communication, documentation, testing, testing and more testing. Oh yea, and a bit of new code as well, just so long as it's thoroughly tested across the range of supported environments.

## Can I help?

Yes! This is a community project, and contributions are welcome! We're always up for a good PR(see above).

Just remember that any code you add will need to be maintained when we attempt to incorporate future versions of WLED. It's easy to add new code; maintaining it across multiple versions of WLED is a whole other matter. Be sparing with your additions.
