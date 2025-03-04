# Battery-Powered HomeKit Climate Sensor (Temp & Humidity) using AHT10 and ESP32-C3 Supermini

## Overview
This project is a DIY battery-powered temperature and humidity sensor that integrates with Apple's HomeKit. It uses the AHT10 sensor and an ESP32-C3 Supermini, leveraging ESP-NOW (SpanPoint) for low-power data transmission and HomeSpan as the receiver for HomeKit integration.

## Features
- **Battery-powered** for wireless operation.
- **ESP-NOW communication** for efficient data transfer.
- **AHT10 sensor** for accurate temperature and humidity readings.
- **HomeKit integration** using HomeSpan.
- **Low power consumption** with deep sleep mode.

## Components Used
1. **ESP32-C3 Supermini** (Transmitter & Receiver)
2. **AHT10 Temperature & Humidity Sensor**
3. **Battery (Li-ion or LiFePO4)**
4. **3D Printed or Custom Enclosure (Optional)**

## Wiring Diagram
```
ESP32-C3 (Transmitter)    AHT10 Sensor
----------------------    ------------
3.3V                     VCC
GND                      GND
GPI03 (SDA)              SDA
GPIO1 (SCL)              SCL
```

## Installation & Setup
### 1. Flashing the Transmitter (SpanPoint - ESP-NOW Sender)
Upload the provided code to the ESP32-C3 Supermini that reads the AHT10 sensor data and transmits it via ESP-NOW.

### 2. Flashing the Receiver (HomeSpan)
The receiver ESP32-C3 runs HomeSpan to bridge the sensor data to Apple HomeKit.

### 3. Adding to HomeKit
- Open the Home app on your iPhone.
- Scan the HomeSpan QR code.
- Assign the sensor to a room and start monitoring.

## Power Optimization
- Use deep sleep mode to conserve battery life.
- Optimize transmission intervals to reduce power consumption.

## Repository Structure
```
/homekit-climate-sensor
│── /code
│    ├── transmitter.ino  # ESP-NOW sender code
│    ├── receiver.ino     # HomeSpan receiver code
│── /docs
│    ├── README.md        # Documentation
│    ├── wiring.png       # Circuit diagram
│── LICENSE
│── .gitignore
```

## Future Enhancements
- Support for additional sensors like BMP280.
- OTA updates for both transmitter and receiver.
- Improved enclosure for aesthetics and durability.

## Contributions
Feel free to fork, modify, and submit pull requests!

## License
[MIT License](LICENSE)
