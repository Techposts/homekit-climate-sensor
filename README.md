# Battery-Powered HomeKit Climate Sensor (Temp & Humidity) using AHT10 and ESP32-C3 Supermini

## Overview
This project is a DIY battery-powered temperature and humidity sensor that integrates with Apple's HomeKit. It uses the AHT10 sensor and an ESP32-C3 Supermini, leveraging ESP-NOW (SpanPoint) for low-power data transmission and HomeSpan as the receiver for HomeKit integration.

## Features
- **Battery-powered** for wireless operation.
- **ESP-NOW communication** for efficient data transfer.
- **AHT10 sensor** for accurate temperature and humidity readings.
- **HomeKit integration** using HomeSpan.
- **Displays battery level percentage in HomeKit**.
- **Can also be integrated into Home Assistant**.
- **Low power consumption** with deep sleep mode.

## Components Used
1. **ESP32-C3 Supermini** (Transmitter & Receiver)
2. **AHT10 Temperature & Humidity Sensor**
3. **Battery (Li-ion or LiFePO4) with voltage measurement**
4. **3D Printed or Custom Enclosure (Optional)**

## Wiring Diagram
```
ESP32-C3 (Transmitter)    AHT10 Sensor
----------------------    ------------
3.3V                     VCC
GND                      GND
GPIO8 (SDA)              SDA
GPIO9 (SCL)              SCL

ESP32-C3 (Transmitter)    Battery
----------------------    -------
GND                      Battery GND
ADC (GPIO3)              Battery Positive (via voltage divider)
```

## Installation & Setup
### 1. Flashing the Transmitter (SpanPoint - ESP-NOW Sender)
Upload the provided `transmitter.ino` file to the ESP32-C3 Supermini. Make sure to select **'Huge App'** partition scheme in Arduino IDE.

### 2. Flashing the Receiver (HomeSpan)
The receiver ESP32-C3 runs HomeSpan to bridge the sensor data, including battery percentage, to Apple HomeKit.

### 3. Adding to HomeKit
- Open the Home app on your iPhone.
- Scan the HomeSpan QR code.
- Assign the sensor to a room and start monitoring.

### 4. Home Assistant Integration
This project can also be integrated into **Home Assistant** via ESPHome or MQTT for extended automation and monitoring.

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
