# System Architecture Overview

The **IoT Telemetry Scale** system is a modular IoT setup designed for measuring, streaming, and tracking weights of small objects or animals — like birds at feeding stations — but it’s customizable for many use cases.

---

## 🔗 Components Overview

| Component | Description |
|----------|-------------|
| Microcontroller (ESP8266/ESP32) | Publishes live weight via MQTT every second |
| MQTT Broker | Receives all weight data + control signals |
| Raspberry Pi Streamer | Provides MJPEG live stream + still image capture |
| WebSocket Server | Stores per-individual weight data in JSON |
| NiceGUI Client | Web UI to review, assign, and chart weights |
| Home Assistant / ioBroker | Optional dashboards and automations |

---

## 🧭 Data Flow

[Load Cell + HX711] ↓ [ESP8266/ESP32 MCU] ↓ (MQTT every 1s) [MQTT Broker] ←←←←←←←←←←←←←←←←←←←← ↓ ↑ [Raspberry Pi Streamer] [Home Assistant] ↓ (15s Snapshots) [ioBroker (optional)] [Filesystem] / [WebSocket DB] → [NiceGUI Client (per-individual weights)]

---

## 📶 MQTT Topics

All topics are prefixed with a device ID (e.g., `scale01/weight`).

| Topic | Payload | Description |
|-------|---------|-------------|
| `scale01/weight` | Float | Raw weight in grams |
| `scale01/heartbeat` | `online` / `timestamp` | Device status |
| `scale01/cmd/tare` | N/A | Remote tare command |
| `scale01/cmd/calibrate` | Number | Trigger calibration with known weight |

(See `docs/mqtt.md` for full topic structure.)

---

## 📂 File/Folder Organization

- 📸 Snapshots saved in `/captures/YYYY-MM-DD/` structure
- 📁 JSON database of individuals: `/data/individuals.json`

---

## 🛠️ Configuration Points

- Wi-Fi credentials + MQTT config via private `private_config.ini` (firmware)
- Daily folder generation + JPEG size in python file which creates the streaming service
- WebSocket server stores user-modifiable names and weight history
- MQTT broker settings managed separately (e.g. Mosquitto)

---

## 🧱 Stack Summary

| Component | Stack |
|----------|--------|
| Firmware | Arduino (ESP8266) |
| Streamer | Python 3 + Picamera2 |
| WebSocket Server | Node.js |
| UI | Python (NiceGUI) |
| Automation | Home Assistant or ioBroker |
| Files | JSON + JPEGs |

---

## 🌍 Deployments

- Firmware can run on ESP8266 or ESP32
- Streamer runs on any Pi with camera module
- JSON server + UI on same or separate Pi
- MQTT broker can be local or cloud-based

---
