# pi-pico-humidity-sensor
Pi Pico implementation of 5 DHT11 humidity/temperature sensors with I2C-AMOLED display (128x64p)

# Usage

## Dependecies
 - CMake
 - make
 - pico-sdk

## Hardware
Connect your SSD1306 oled display to i2c1 port (you can change it during initialization)
```
  SDA -> GPIO2
  SCL -> GPIO3
  GND -> GND
  VCC -> 3V3(OUT)
```

## To Build
Run the following commands in terminal
```
  $ git clone https://github.com/Ryledra/pi-pico-humidity-sensor.git
  $ cd pi-pico-humidity-sensor
  $ mkdir build
  $ cd build
  $ cmake ../src
  $ make
```

# Libs included

## Raspberry Pico SSD1306 + GFX Library
URL: https://github.com/mbober1/RPi-Pico-SSD1306-library

Based on Adafruit GFX Library
https://github.com/adafruit/Adafruit-GFX-Library