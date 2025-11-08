# IoT-Enabled Patient Vital Signs Monitoring with Emergency Alerts

## Project Overview

This system continuously monitors critical patient health parameters including:

* Heart Rate & SpO2 (using **MAX30102**)
* Body Temperature (using **MLX90614** contactless sensor)
* Fall/Movement Detection (using **MPU6050** accelerometer/gyroscope)

All readings are processed by the **Silicon Labs BRD2605A Rev A02** microcontroller board. Data can be transmitted wirelessly via Bluetooth Low Energy (BLE) to a smartphone or monitoring dashboard. Emergency alerts are triggered automatically if abnormal health conditions are detected.

---

## Hardware Components

| Component                                |  Description                                                                    |
| ---------------------------------------- |  ------------------------------------------------------------------------------ |
| **BRD2605A Rev A02 (SiLabs MCU Board)**  |  Main microcontroller that processes sensor data and handles BLE communication. |
| **MAX30102 Heart Rate & SpO₂ Sensor**    |  Measures pulse rate and oxygen saturation using optical method.                |
| **MLX90614 Infrared Temperature Sensor** |  Measures body/skin temperature without physical contact.                       |
| **MPU6050 6-axis Motion Sensor**         |  Detects patient falls or abnormal movements using accelerometer & gyroscope.   |


---

## System Block Diagram

**Flow:**
Sensors → Microcontroller (BRD2605A) → BLE Communication → Mobile/Cloud App → Emergency Alerts

---

## Features

* ✅ Real-time vital sign monitoring
* 📡 Wireless BLE data transmission
* 🚨 Automatic emergency alerts for abnormal readings
* 🔥 Fall detection for elderly or critical care patients
* 🏥 Suitable for home-care and hospital monitoring environments

---

## Pin Connections

### MAX30102 (I2C)

* SDA → MCU SDA
* SCL → MCU SCL
* VIN → 3.3V
* GND → GND

### MLX90614 (I2C)

* SDA → MCU SDA
* SCL → MCU SCL
* VCC → 3.3V
* GND → GND

### MPU6050 (I2C)

* SDA → MCU SDA (shared bus)
* SCL → MCU SCL (shared bus)
* VCC → 3.3V
* GND → GND

> All sensors share the same **I2C bus**, which makes wiring simpler.

---

## Software Tools

| Tool                                  | Purpose                          |
| ------------------------------------- | -------------------------------- |
| **Simplicity Studio (Silicon Labs)**  | Main firmware development IDE    |
| **Gecko SDK**                         | Hardware abstraction & BLE Stack |
| **Mobile App / Dashboard (Optional)** | Display patient health data      |

---

## Working Principle

1. Sensors continuously collect patient health parameters.
2. Microcontroller reads sensor data via I2C protocol.
3. Data is processed & evaluated for safety thresholds.
4. BLE transmits data to mobile dashboard.
5. If dangerous conditions are detected → alert is triggered.

---

## Example Use Cases

* Elderly care monitoring
* Post-surgery patient observation
* Remote home health monitoring
* Emergency response support

---

## Future Enhancements

* Cloud data logging (Firebase / AWS IoT)
* Multi-patient monitoring dashboard
* AI-based health risk prediction
* GPS tracking when emergency occurs

