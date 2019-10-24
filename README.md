# ESP32 Smarthome

Current prototype

![Image of the project](https://i.imgur.com/s7tQL1k.jpg)

Web-interface made with [Grafana](https://grafana.com/) to see the data visualised.
![Grafana-dashboard](https://i.imgur.com/rTwOSI8.png)

## Basics
This project aims to create a smarthome-system that can measure, control & show various useful information, such as temperature and important local events. The exact featureset is yet to determined. :)

## Hardware
Currently I use the following hardware-stuff to make this project tick. There's more stuff to be added later.

+ Bunch of dupont-wires & a prototyping board
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
+ Time-display based on NTP
+ Sending the data over the Internet to [Influxdb](https://www.influxdata.com/)-database. I have a separate [Grafana](https://grafana.com/)-instance that can show graphs of the data on a browser

## Planned features
+ Replace Dallas DS18B20 temperature sensor with a Bosch BME680 that is more accurate and does humidity, pressure & gas too
+ Implement proper multithreaded code where different tasks (Sensor-polling, time, API-access etc) run separately and share data as necessary
+ More?
