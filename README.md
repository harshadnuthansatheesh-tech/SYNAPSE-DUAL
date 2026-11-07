# SYNAPSE-DUAL
# Project SYNAPSE-DUAL: Assistive Haptic Navigation & Kinetic Gauntlet Architecture

> **Hack Club Fallen Project Submission**  
> *An integrated dual-system wearable platform featuring 360-degree ultrasonic distance sensing, IMU orientation feedback, and low-latency haptic directional alerts.*

---

## 📌 Project Overview
Project **SYNAPSE-DUAL** combines assistive technology with kinetic mechanical prototyping:
1. **Haptic Navigation Core (System 1):** Uses an ESP32 microcontroller, a 9-axis BNO085 IMU, and a 4-channel HC-SR04P ultrasonic array mounted on a neckband to drive 4 coin ERM vibration motors stitched into a forearm sleeve for intuitive 360° spatial awareness.
2. **Mechanical Iron Man Gauntlet (System 2):** A dedicated ESP32 and MPU6050 telemetry arm gauntlet tracking wrist pitch, roll, and spatial gesture vectors.

---

## 🛠️ Hardware & Pinout Architecture

| Component | Function / Role | ESP32 GPIO Pin Mapping |
| :--- | :--- | :--- |
| **BNO085 IMU** | $I^2C$ Spatial Heading & Yaw | `SDA: GPIO 21`, `SCL: GPIO 22` |
| **Ultrasonic Array** | 4-Direction Scan (N, S, E, W) | `Trig: GPIO 4, 5, 16, 17`, `Echo: GPIO 18, 19, 23, 25` |
| **Haptic Motors** | AO3400A Low-Side MOSFET Drivers | `PWM Gates: GPIO 12, 13, 14, 15` |
| **Power Stage** | 1S LiPo (3.7V) $\rightarrow$ MT3608 Boost | `5V Rail` & `3.3V System Rail` |

---

## 📊 Bill of Materials (BoM Summary)
The complete itemized Bill of Materials with supplier details and component breakdown is available in [`bom.csv`](./bom.csv).

- **Total Estimated Cost:** ~$64.70 USD
- **Key Semiconductors:** ESP32 DevKit V1, BNO085 IMU, MPU6050, AO3400A N-MOSFETs, 1N5819 Schottky Diodes, MT3608 Boost, TP4056 Charger.

---

## 📂 Firmware Installation & Setup

1. Open Arduino IDE and install required libraries:
   - `Adafruit BNO08x`
   - `Adafruit MPU6050`
   - `Wire`
2. Open `firmware/haptic_core/haptic_core.ino` and upload to **ESP32 #1**.
3. Open `firmware/gauntlet_telemetry/gauntlet_telemetry.ino` and upload to **ESP32 #2**.

---

## 📜 License
Distributed under the **MIT License**. See `LICENSE` for details.
