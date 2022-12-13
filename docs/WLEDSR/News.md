What's possibly on the horizon (no dates given):

* Add 2D orientation settings, but no multi-SEGMENT 2D orientation support.
* Yes, we'd love dynamic controls for each animation, but we think that may interfere with future releases from Aircoookie.
* We are working on adding multiple panels.
* Automatic gain control. It's a challenge because each animation uses sound variables differently. And yes, it will be there 👍 in the upcoming release.
* Improvements to our audio processing algorithms. More awesomeness for your LEDs.
* More and improved sound reactive effects.

### May 15, 2021

We've since added several 2D routines to WLED and in the process have determined that our ESP32 binary now consumes about 98.5% of flash memory, or in oil industry terms. . . We have reached peak Flash. As a result, we're going to look carefully into ALL of the animations and see which ones consume the most flash and with the least coolness. In the meantime, we've updated SR WLED to support a very recent Master of 0.12.0, which has seen some changes/fixes since it was originally released. Special thanks to THATDONFC for keeping SR WLED in sync with Aircoookie's updates. It's not a small job.

### January 13, 2021

* Well that was a year, only for 2021 to say 'hold my beer'.
* We've been working on fixing bugs, including UDP sync issues among others.
* Normalizing frequency and volume response for different microphones.
* Testing/updating various routines to work with the above changes.
* Modified routines to better support the 'FastLED' way of doing things, specifically for leds[i+1] = leds[i] and vice versa.
* Dealing with platform related noise and spikes. Had to add an exponential filter combined with the squelch control.
* Added a few more animations, and took out one or two.


### November 5, 2020

* The ESP8266 branch continues to be reliable for that platform, but NOT reliable for the regular build. Would love to know why. Update: It was probably RAM usage.
* Have fixed issues around SEGMENTS for various sound reactive animations. Ths issue was SEGMENT specific 'persistent' variables. Use the uint16_t SEGENV.aux0 or SEGENV.aux1 variables if you need those.
* That was updated for both the dev and ESP8266 branches.
* We now have a dedicated Sound Settings page.


### August 22, 2020

* Our dev build now has INMP441 (digital microphone) support for the ESP32.
* Our dev build also now has a Gain settings control for volume reactive or '*' routines.
* Neither update has been rolled up into our main branch.
* We've had a lot of issues with AP mode and ESP8266's, so Andrew created an ESP8266 branch, downloaded the latest version of WLED and added just the volume reactive functionality to that branch.
* We'll be removing ESP8266 support from our dev and main branches over time. That will simplify coding significantly.
* apleschu is still busy with his cross continental move.
