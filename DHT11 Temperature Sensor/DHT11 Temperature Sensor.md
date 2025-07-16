---
title: DHT11 Temperature Sensor
created: "[[2024-07-15]]"
updated: "[[2025-07-16]]"
up:
  - "[[37 Sensor Kit Ver 1]]"
in:
  - "[[Temperature Sensor]]"

---
[DHT11 basic temperature-humidity sensor + extras : ID 386 : Adafruit Industries, Unique & fun DIY electronics and kits](https://www.adafruit.com/product/386)
![[CleanShot 2024-07-15 at 13.15.20@2x.png | 300]]
Temp and Humidity

* A module with a temperature/humidity sensor type DHT11, Temperature range:
* -20 - 60°C (+/-1°C), Rel. humidity: 5-95% (+/5%), Supply voltage: 3 to 5.5V. With a built-in 10 K ohm pull up resistor. Library:DHT .h
## Issues
* The code from the [[37 Sensor Kit Ver 1]] doesn't work, I had to use the Arduino code (in the links). 
* The DHT11 is only good for **1 C resolution**. A better sensor in the same series is the DHT22 which provides 0.1 C resolution
## Links
* Arduino Code: [Using DHT11 | Arduino Project Hub](https://projecthub.arduino.cc/arcaegecengiz/using-dht11-12f621)
