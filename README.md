# 🏠 Beckhoff Smarthome / IoT Gateway

This project is a home automation system built on **Beckhoff TwinCAT 3**. It allows seamless mobile control via the **IoT Communicator App** and the integration of third-party **MQTT** sensors and actuators.

## 🚀 The Engineering Behind It

While many smarthome solutions rely on consumer-grade hubs, this system uses a **Beckhoff PLC** as the "Single Source of Truth." 
**Technical Highlights:**

* **TwinCAT IoT Communicator (TF6735):** Integration of the mobile app interface directly into the PLC logic. It handles bidirectional communication for toggling states and receiving real-time push notifications.
* **Hybrid MQTT Gateway:** I implemented a custom handler using **TF6701** to bridge the gap between deterministic PLC logic and asynchronous MQTT devices (like Shelly or ESP32 nodes).
* **Industrial Logic Patterns:** True to my development style, this project utilizes **PLC-standard blocks** (TON, R_TRIG, F_TRIG) to ensure debounced sensor inputs and stable state transitions for lighting and blinds.

## 🛠️ Features

* **Mobile Control:** Dedicated dashboard via the IoT Communicator App with custom widgets for lights, heating, and shading.
* **Universal MQTT Integration:** Automatically subscribes to and publishes to MQTT topics, allowing the PLC to control non-Beckhoff hardware.
* **Smart Shading & Lighting:** Automated logic for blinds based on sun position and occupancy-driven lighting scenes.
* **Push Alerts:** Instant smartphone notifications for system status changes or alarms.
* **Local-First Architecture:** All core logic runs locally on the CX-controller; the system remains fully functional even without an internet connection.

## 🔧 Technical Stack

* **Controller:** Beckhoff CX-series (or TwinCAT 3 Runtime)
* **Communication:** ADS, MQTT (TF6701), IoT Communicator (TF6730)
* **Language:** Structured Text (IEC 61131-3)
* **Interface:** TwinCAT IoT Communicator App (iOS/Android)
