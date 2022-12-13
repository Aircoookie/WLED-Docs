**Use this basic code to read and calculate the average from the INMP401/MAX4466/MAX9814 microphone on an ESP32 or ESP8266**

* Use the Arduino Serial plotter to view the output and compare your results to those found [here](https://github.com/atuline/WLED/blob/assets/docs/Microphones.pdf).
* Make sure you have set the baud rate on your Serial plotter to 115200 (as defined in the sketch).
* Note that the ESP32 employs a 12 bit ADC, while the ESP8266 has a 10 bit ADC. Also note the anomalous spikes on the ESP8266.
* The `micLev` variable is the DC Offset value that you can use for zeroing your samples.

```C
/* ESPSample
 *
 * By: Andrew Tuline
 *
 * Updated: Feb, 2019
 *
 * Basic code to read and calculate average from the Sparkfun INMP401/MAX4466/MAX9814 microphone
 * on an ESP32 or ESP8266.
 * 
 * Use the Arduino Serial plotter to view the output. Compare results to those found at:
 * 
 * https://github.com/atuline/WLED/blob/assets/docs/Microphones.pdf
 *
 * Note that the ESP32 employs a 12 bit A/D, while the ESP8266 has a 10 bit A/D. Also note
 * the anomalous spikes on the ESP8266.
 * 
 * The micLev variable is the DC Offset value that you can use for zeroeing your samples.
 * 
 */

#ifdef ESP8266
#define MIC_PIN A0                              // ESP8266 pin A0
#else
#define MIC_PIN 36                              // ESP32 pin also known as 'VP'.
#endif

void setup() {
  delay(1000);
  Serial.begin(115200);                         // Initialize serial port for debugging.
} // setup()

void loop() {
  analog_sample();
} // loop()

void analog_sample() {
  static float micLev;                          // Needs to be a float, or smoothing calculation below will be very inaccurate.
  int micIn = analogRead(MIC_PIN);
  micLev = ((micLev*31)+micIn)/32;              // Smooth out the data to get average value (used for zeroeing).
  Serial.print(micIn); Serial.print(" ");
  Serial.print(micLev); Serial.println(" ");
} // analog_sample()
```
Original code can be found [here](https://pastebin.com/BHtzh5yY).