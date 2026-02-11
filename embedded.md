 Embedded Developer Evaluation Task

  Overview

  Build a smart sensor module for Tasmota that reads environmental data and exposes it via MQTT and a web interface.

  Requirements

  Part 1: C/C++ Driver (Core)

  Write a Tasmota driver (xsns_xx_customsensor.ino) that:
  - Interfaces with a BME280 sensor (I2C) on ESP8266/ESP32
  - Reads temperature, humidity, and pressure every 10 seconds
  - Publishes data via Tasmota's MQTT telemetry
  - Handles sensor errors gracefully (retry logic, error reporting)
  - Follows Tasmota coding conventions

  Part 2: Berry Script (Automation)

  Write a Berry script that:
  - Monitors the sensor readings from Part 1
  - Triggers alerts when thresholds are exceeded (e.g., temp > 30°C)
  - Implements a moving average filter (last 5 readings)
  - Logs events to flash with rotation (max 100 entries)

  Part 3: Python Tool (Testing/Provisioning)

  Write a Python CLI tool that:
  - Discovers Tasmota devices on the local network (mDNS or UDP scan)
  - Configures WiFi/MQTT settings via Tasmota's HTTP API
  - Subscribes to MQTT and validates sensor data format
  - Generates a test report (JSON output)

  Deliverables

  1. Source code with comments
  2. Brief README with build/flash instructions
  3. Wiring diagram (can be simple ASCII or image)

  Evaluation Criteria
  ┌──────────────────────────────────────────┬────────┐
  │                   Area                   │ Weight │
  ├──────────────────────────────────────────┼────────┤
  │ Code quality & embedded best practices   │ 30%    │
  ├──────────────────────────────────────────┼────────┤
  │ Memory efficiency (heap usage awareness) │ 20%    │
  ├──────────────────────────────────────────┼────────┤
  │ Error handling & edge cases              │ 20%    │
  ├──────────────────────────────────────────┼────────┤
  │ Tasmota integration correctness          │ 20%    │
  ├──────────────────────────────────────────┼────────┤
  │ Documentation clarity                    │ 10%    │
  └──────────────────────────────────────────┴────────┘
  Time Limit

  4-6 hours (candidates can simulate hardware if they don't have physical devices)

  ---
  Bonus Challenges (Optional)

  - Add deep sleep support with configurable wake interval
  - Implement OTA update verification in Python tool
  - Create a simple web UI component using Tasmota's Berry web server

  ---
  This task tests real-world skills: low-level hardware interfacing, Tasmota ecosystem knowledge, scripting for automation, and tooling for deployment. Want me
  to adjust the scope or focus on specific areas?
