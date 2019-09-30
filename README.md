# ESP32 Smarthome

Current prototype

![Image of the project](https://i.imgur.com/s7tQL1k.jpg)

## Basics
This project aims to create a smarthome-system that can measure, control & show various useful information, such as temperature and important local events. The exact featureset is yet to determined. :)

## Hardware
Currently I use the following hardware-stuff to make this project tick. There's more stuff to be added later.
+ [ESP32 microcontroller](http://esp32.net/)
+ [Dallas DS18B20 temperature sensor](https://datasheets.maximintegrated.com/en/ds/DS18B20.pdf)
+ 1602 LCD for displaying the information

## Software
I write the code in C++ and use ESP32 Arduino-framework as a base for functionality. Some of the other stuff used include...
+ [PlatformIO](https://platformio.org/) for project-management, library-management, flashing and so on.
+ Arduino libraries for accessing the sensors, controlling the LCD, parsing JSON and so on

## Features
+ Polling of Dallas DS18B20 for my apartment's temperature
+ Using WiFi to connect to Internet to access OpenWeatherMap via their API to get the weather of my city
+ Displaying all the useful data on the 1602 LCD
+ Time based on NTP

## Planned features
+ More sensors, also possibly replacing the Dallas with more accurate Bosch that does humidity too
+ Implement proper multithreaded code where different tasks (Sensor-polling, time, API-access etc) run separately and share data as necessary
+ Multipage system that redraws the LCD-screen with different information every XX seconds
+ Sending the data that's being collected from my apartment to my backend where it can then be accessed by a separate website with graphs and stuff
+ More?
