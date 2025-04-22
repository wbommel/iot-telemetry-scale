# !!! WIP !!!
* April 22, 2025: preparing telemetry firmware for ESP8266/ESP32 hardware detection

<br><br><br><br><br>
# IoT Telemetry Scale 📡⚖️

A modular open-source system for wireless weight sensing, live telemetry, and remote monitoring — designed for small animals, feeding stations, or general-purpose IoT measurement.

**This is the meta repository** linking all parts of the project ecosystem.

---

## 🔧 What It Does

- 📏 Measures weight via load cell & HX711
- 📶 Publishes readings via MQTT
- 🎥 Streams live video with snapshots
- 🧠 Stores and organizes measurements per individual
- 📊 Displays charts, dashboards, and historical data
- 🏠 Integrates with Home Assistant & ioBroker
- 💡 Designed to be flexible, low-stress, and extensible

---

## 📦 Subprojects

| Component | Description | Repository |
|----------|-------------|------------|
| 🧠 Firmware | ESP8266-based MQTT weight publisher | [iot-telemetry-scale-firmware](https://github.com/yourusername/iot-telemetry-scale-firmware) |
| 🔌 PCB | KiCad PCB design for ESP8266 + HX711 | [iot-telemetry-scale-pcb](https://github.com/yourusername/iot-telemetry-scale-pcb) |
| 🧱 Housing | FreeCAD model of scale casing | [iot-telemetry-scale-housing](https://github.com/yourusername/iot-telemetry-scale-housing) |
| 📸 Streamer | Python + PiCamera live MJPEG + snapshot handler | [iot-telemetry-scale-streamer](https://github.com/yourusername/iot-telemetry-scale-streamer) |
| 🔌 Server | Node.js-based WebSocket JSON database | [iot-telemetry-scale-server](https://github.com/yourusername/iot-telemetry-scale-server) |
| 💻 UI | NiceGUI frontend for individuals & weights | [iot-telemetry-scale-client](https://github.com/yourusername/iot-telemetry-scale-client) |
| 🏠 HA Config | Home Assistant MQTT dashboard setup | [iot-telemetry-scale-ha](https://github.com/yourusername/iot-telemetry-scale-ha) |
| 📈 ioBroker | ioBroker setup, MQTT & charts | [iot-telemetry-scale-iobroker](https://github.com/yourusername/iot-telemetry-scale-iobroker) |

---

## 📚 Documentation

- [System Architecture](docs/architecture.md)
- [MQTT Topic Format](docs/mqtt.md) *(to create)*
- [Data Format / JSON Spec](docs/data-structure.md) *(to create)*
- [Naming + Contribution Guidelines](CONTRIBUTING.md)

---

## 🙌 Get Involved

We love collaborators! Whether you're into:
- 🛠️ Hardware
- 🧠 Firmware
- 🖥️ Frontend/backend
- 🧪 Testing
- 📚 Documentation

…there's a spot for you. See [CONTRIBUTING.md](CONTRIBUTING.md) to learn how to jump in.

---

## 📜 License

This project is open source under the [MIT License](LICENSE).

---
> Designed with ❤️ to help animals and those who care for them — now open to all creative uses.
