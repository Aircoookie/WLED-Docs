During the development of our sound reactive version of WLED, we've had several challenges with WiFi along with the ADC capability of the ESP devices.


### ESP8266

After the code refactoring of WLED from .ino to .cpp files around April 2020, our ESP8266 code lost connection between the user interface and the ESP8266's web server. This eventually culimated in a re-write of a stripped down version of SR WLED dedicated just for the ESP8266. It included the UDP sound sync as a receiver (only), but supported none of the FFT or 2D functionality. This stripped down version seems to be stable, however that platform is now deprecated from further development.


### ESP32

Although the ESP32 did lose connection with the web server, it was nowhere near as bad as the ESP8266. 


### Both platforms

![power_noise_and_mic_output](https://user-images.githubusercontent.com/91616163/205751772-8e954e26-200e-42ba-aff0-2583d45749ab.jpg)


On both platforms, we encountered significant spikes when using the analog ADC when the WiFi is active. There are numerous articles on this issue, along with various [methods to reduce the noise](https://moonmodules.github.io/WLED-Docs/WLEDSR/First-Time-Setup#noise-and-spikes). We've found that an I2S microphone, such as the INMP441 or ICS-43434 will provide a better response than any of the analog microphones or input methods that we support.

Here's some [test results](https://github.com/atuline/WLED/blob/assets/docs/Noise%20and%20Spikes.pdf) with the analog input, including strong spikes observed very frequently.

![ADC_analog_spikes](https://user-images.githubusercontent.com/91616163/205752648-03136605-eb61-4eb9-8427-f6740f53485d.jpg)


Here's some references:

* https://www.atomic14.com/2020/09/12/esp32-audio-input.html
* https://www.youtube.com/watch?v=pPh3_ciEmzs
* https://www.youtube.com/watch?v=3g7l5bm7fZ8
* https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/peripherals/adc.html
* https://www.esp32.com/viewtopic.php?t=9613
* https://github.com/espressif/arduino-esp32/issues/92
* https://randomnerdtutorials.com/esp32-adc-analog-read-arduino-ide/

Note: According to atomic14 in the above videos, the I2S microphones do not exhibit the issues found with the analog microphones.
