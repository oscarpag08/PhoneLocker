# PhoneLocker - A smart locker for schools and offices (RFID + Phone Detection)

A security locker control system. A controller verifies the real-time presence of 4 phones in their respective slots and manages the lock mechanism via a relay when an authorized RFID wristband is scanned. It includes a responsive, glassmorphism-style WebUI with fluid animations.

## Features
* **Presence Control:** Continuous monitoring of 4 slots via digital sensors.
* **RFID Unlock:** Timed opening management (5 seconds) using an MFRC522 reader.
* **Web Interface:** Futuristic UI (separated HTML/CSS/JS) featuring 3D animations and a real-time counter.
* **Remote Unlock:** Password-protected emergency button integrated directly into the dashboard.

## Hardware Components
* Arduino Uno (designed for easy migration to ESP32)
* RC522 RFID Reader
* 4x Presence Sensors (Digital Inputs)
* Relay Module (Locker Lock)
* Status LEDs (Red/Green)

## Project Structure
* `/src` - Source code for the microcontroller (.ino)
* `/webui` - Graphical interface files (`index.html`, `style.css`, `script.js`)

## Pin Mapping (Arduino)
* **Phone Sensors:** Pins 2, 3, 4, 5
* **Status LEDs:** Green (Pin 7) | Red (Pin 6)
* **Relay:** Pin 8
* **RC522 RFID:** RST (Pin 9) | SDA/SS (Pin 10) + Standard SPI Bus

## Development Notes
The web interface includes a JavaScript simulator for local testing on a PC. The project is structured to be transferred to an ESP32, where a WebSocket server can be configured to send hardware state changes to the UI using JSON strings.
