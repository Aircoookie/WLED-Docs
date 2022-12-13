**Use this code to read and calculate the average from the INMP441/ICS-43434 microphone on an ESP32 or ESP8266**

* Use the Arduino Serial plotter to view the output and compare your results to those found [here](https://github.com/atuline/WLED/blob/assets/docs/Microphones.pdf).
* Make sure you have set the baud rate on your Serial plotter to 115200 (as defined in the sketch).

```C
/* 
 * ESP32 I2S Noise Level Example.
 * 
 * By: maspetsberger
 * 
 * Updated by: Andrew Tuline
 * 
 * This example calculates a mean noise level.
 * 
 * Tie the L/R pin to ground. Other pins are listed below.
 * VDD goes to 3.3V
 * GND goes to Gnd 
 * 
 */
 
#include <driver/i2s.h>
 
#define I2S_WS  15         // aka LRCL
#define I2S_SD  32         // aka DOUT
#define I2S_SCK 14         // aka BCLK
 
const i2s_port_t I2S_PORT = I2S_NUM_0;
const int BLOCK_SIZE = 64;
const int SAMPLE_RATE = 10240;
 
float mean = 0;
bool INMP_flag = 0;
 
void setup() {
 
  Serial.begin(115200);
 
  Serial.println("Configuring I2S...");
  esp_err_t i2s_err;
 
  // The I2S config as per the example
  const i2s_config_t i2s_config = {
      .mode = i2s_mode_t(I2S_MODE_MASTER | I2S_MODE_RX), // Receive, not transfer
      .sample_rate = SAMPLE_RATE,                         // 16KHz
      .bits_per_sample = I2S_BITS_PER_SAMPLE_32BIT, // could only get it to work with 32bits
      .channel_format = I2S_CHANNEL_FMT_ONLY_LEFT, // LEFT when pin is tied to ground.
      .communication_format = i2s_comm_format_t(I2S_COMM_FORMAT_I2S | I2S_COMM_FORMAT_I2S_MSB),
      .intr_alloc_flags = ESP_INTR_FLAG_LEVEL1,     // Interrupt level 1
      .dma_buf_count = 8,                           // number of buffers
      .dma_buf_len = BLOCK_SIZE                     // samples per buffer
  };
 
  // The pin config as per the setup
  const i2s_pin_config_t pin_config = {
      .bck_io_num = I2S_SCK,       // BCLK aka SCK
      .ws_io_num = I2S_WS,        // LRCL aka WS
      .data_out_num = -1,         // not used (only for speakers)
      .data_in_num = I2S_SD       // DOUT aka SD
  };
 
  // Configuring the I2S driver and pins.
  // This function must be called before any I2S driver read/write operations.
  i2s_err = i2s_driver_install(I2S_PORT, &i2s_config, 0, NULL);
  if (i2s_err != ESP_OK) {
    Serial.printf("Failed installing driver: %d\n", i2s_err);
    while (true);
  }
  i2s_err = i2s_set_pin(I2S_PORT, &pin_config);
  if (i2s_err != ESP_OK) {
    Serial.printf("Failed setting pin: %d\n", i2s_err);
    while (true);
  }
  Serial.println("I2S driver installed.");
 
  delay(1000);                        // Enough time to see these messages. This need to be BEFORE the INMP test.
  
  getINMP();
  if (mean != 0.0) {
    Serial.println("INMP is present.");
    INMP_flag = 1;
  }
 
} // setup()
 
 
 
void loop() {
 
  if (INMP_flag) {
    getINMP();
    Serial.print(abs(mean)); Serial.print(" ");
    Serial.println(1600);
    
  } else {
    // Analog Read here!!
  }
  
} // loop()
 
 
 
void getINMP() {
  // Read multiple samples at once and calculate the sound pressure
  int32_t samples[BLOCK_SIZE];
  int num_bytes_read = i2s_read_bytes(I2S_PORT, 
                                      (char *)samples, 
                                      BLOCK_SIZE,     // the doc says bytes, but its elements.
                                      portMAX_DELAY); // no timeout
  
  int samples_read = num_bytes_read / 8;
  if (samples_read > 0) {
 
    for (int i = 0; i < samples_read; ++i) {
      mean += samples[i];
    }
    mean = mean/BLOCK_SIZE/16384;
  }  
}
```
