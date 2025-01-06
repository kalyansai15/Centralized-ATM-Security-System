# Centralized ATM Security System

An IoT-based security system designed to enhance ATM security by integrating sensors, a microcontroller, Wi-Fi, and Google Assistant. The system detects unauthorized access, provides real-time alerts, and enables remote monitoring through live camera feeds.

---

## Features
- **Unauthorized Access Detection**: Hall-effect sensor for real-time detection of unauthorized activities.
- **Real-Time Alerts**: Notifications and alerts sent via Flask server integration.
- **Live Monitoring**: Remote camera feed accessible through the server.
- **Voice-Controlled Automation**: Integrated with Google Assistant for advanced control.

---

## System Architecture
[Add a brief description of the architecture here, e.g., "The system leverages an Arduino Uno microcontroller, Flask server, and Google Assistant for end-to-end security and monitoring."]

![System Architecture](./images/system_architecture.png)

---

## Components Used
1. **Microcontroller**: Arduino Uno
2. **Sensor**: Hall-effect sensor
3. **Networking**: Wi-Fi module (e.g., ESP8266)
4. **Camera**: USB or IP camera
5. **Software**: Flask, Python, Google Assistant integration
6. **Other Components**: Breadboard, resistors, connecting wires, etc.

---

## Installation and Setup

### Hardware Setup
1. Connect the Hall-effect sensor to the Arduino Uno.
2. Interface the Wi-Fi module for internet connectivity.
3. Connect the camera to the system (via USB or IP configuration).

### Software Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/kalyansai15/Centralized_ATM_Security_System.git
