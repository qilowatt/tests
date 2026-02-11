# 🔧 Embedded Developer Evaluation Task

> **Smart Sensor Module for Tasmota** — Build a complete IoT sensor solution that reads environmental data and exposes it via MQTT and a web interface.

---

## 📋 Overview

Design and implement a Tasmota-compatible smart sensor module spanning three layers: a C/C++ hardware driver, a Berry automation script, and a Python provisioning/testing tool.

**Time Limit:** 4–6 hours *(candidates can simulate hardware if they don't have physical devices)*

---

## 🧩 Requirements

### Part 1: C/C++ Driver (Core)

Write a Tasmota driver (`xsns_xx_customsensor.ino`) that:

- Interfaces with a **BME280 sensor** (I2C) on ESP8266/ESP32
- Reads temperature, humidity, and pressure every **10 seconds**
- Publishes data via Tasmota's MQTT telemetry
- Handles sensor errors gracefully (retry logic, error reporting)
- Follows Tasmota coding conventions

### Part 2: Berry Script (Automation)

Write a Berry script that:

- Monitors the sensor readings from Part 1
- Triggers alerts when thresholds are exceeded (e.g., `temp > 30°C`)
- Implements a **moving average filter** (last 5 readings)
- Logs events to flash with rotation (max 100 entries)

### Part 3: Python Tool (Testing/Provisioning)

Write a Python CLI tool that:

- Discovers Tasmota devices on the local network (mDNS or UDP scan)
- Configures WiFi/MQTT settings via Tasmota's HTTP API
- Subscribes to MQTT and validates sensor data format
- Generates a test report (JSON output)

---

## 📦 Deliverables

1. **Source code** with comments
2. **README** with build/flash instructions
3. **Wiring diagram** (ASCII art or image)

---

## 📊 Evaluation Criteria

| Area | Weight |
|:-----|:------:|
| Code quality & embedded best practices | **30%** |
| Memory efficiency (heap usage awareness) | **20%** |
| Error handling & edge cases | **20%** |
| Tasmota integration correctness | **20%** |
| Documentation clarity | **10%** |

---

## ⭐ Bonus Challenges (Optional)

- [ ] Add **deep sleep support** with configurable wake interval
- [ ] Implement **OTA update verification** in the Python tool
- [ ] Create a simple **web UI component** using Tasmota's Berry web server

---

## 🎯 What This Tests

This task evaluates real-world skills across the embedded IoT stack:

| Skill | Covered In |
|:------|:-----------|
| Low-level hardware interfacing (I2C, sensors) | Part 1 |
| Tasmota ecosystem & conventions | Parts 1 & 2 |
| Scripting for automation & data processing | Part 2 |
| Tooling for deployment & testing | Part 3 |
| End-to-end system thinking | All parts |

---

## 📬 Submission

Send your completed work to **[info@qilowatt.eu](mailto:info@qilowatt.eu)**

Include all deliverables as a `.zip` archive or a link to a Git repository.
