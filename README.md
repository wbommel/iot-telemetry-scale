# !!! WIP !!!
The sub projects are in process of generalization and will be published one after another in the upcoming weeks. 
* April 25, 2025: done preparing the firmware project (tested with ESP32 and ESP8266, generalized calibration process)
* April 22, 2025: preparing the first project, the telemetry firmware for ESP8266/ESP32 hardware detection

<br><br><br><br><br>

# IoT Telemetry Scale 📡⚖️

A modular open-source system for wireless weight sensing, live telemetry, and remote monitoring — designed for small animals, feeding stations, or general-purpose IoT measurement.

**This is the meta repository** linking all parts of the project ecosystem.

> ⚠️ **Disclaimer**
> 
> This project is the result of personal experimentation and learning. I am a hobbyist and not a certified electronics engineer, nor an expert in load cell calibration or metrology.
> 
> While the system works well in my own setup (and with budgies 🐦!), it may require adaptation, validation, and care before use in other environments—especially in critical or commercial applications.
> 
> Please review all schematics, firmware, and configuration settings carefully before use. I welcome contributions, feedback, and improvements from the community!

---

## How it started

Me and my wife were involved in animal protection specifically working to help budgies for quite aome years. Nursing the little animals, often more or less sick ones, requires to weigh them from time to time because the weight is an important metric regarding possible health problems. As catching the little birds is very stressful and counter acts their well being.
So, combining my every day job as a programmer with my interest and knowledge of electronics, I came up with the idea to build a scale which fits under a feeding bowl of the budgies (pictures coming up).
That's a quick wrapup of the history of the project and might be extended in the future.
<br>
<img src="/assets/img/WeighingScale_Current.jpg" alt="Our current setup" width="200"/>

## 🔧 What It Does

- 📏 Measures weight via load cell & HX711 with ESP8266 or ESP32 as basis
- 📶 Publishes readings via MQTT continuously (roughly one value every second)
- 🎥 Streams live video with snapshots (via a RaspberryPi and a RaspiCam)
- 🧠 Stores and organizes measurements per individual (via a minimal and simple nodejs websocket backend using a json file and a python nicegui frontend (running on a RaspberryPi in my case))
- 📊 Displays historical data as charts on iobroker or Homeassistant dashboards (running on RaspberryPi's) 
- 🏠 Integrates with Home Assistant & ioBroker (see above)
- 💡 Designed to be flexible, low-stress, and extensible

---

## 📦 Subprojects

| Component | Description | Repository |
|----------|-------------|------------|
| 🧠 Firmware | ESP8266-based MQTT weight publisher | [iot-telemetry-scale-firmware](https://github.com/wbommel/iot-telemetry-scale-firmware) (done) |
| 🔌 PCB | KiCad PCB design for ESP8266 + HX711 | [iot-telemetry-scale-pcb](https://github.com/wbommel/iot-telemetry-scale-pcb) (upcoming) |
| 🧱 Housing | FreeCAD model of scale casing | [iot-telemetry-scale-housing](https://github.com/wbommel/iot-telemetry-scale-housing) (upcoming) |
| 📸 Streamer | Python + PiCamera live MJPEG + snapshot handler | [iot-telemetry-scale-streamer](https://github.com/wbommel/iot-telemetry-scale-streamer) (upcoming) |
| 🔌 Server | Node.js-based WebSocket JSON database | [iot-telemetry-scale-server](https://github.com/wbommel/iot-telemetry-scale-server) (upcoming) |
| 💻 UI | NiceGUI frontend for individuals & weights | [iot-telemetry-scale-client](https://github.com/wbommel/iot-telemetry-scale-client) (upcoming) |
| 🏠 HA Config | Home Assistant MQTT dashboard setup | [iot-telemetry-scale-ha](https://github.com/wbommel/iot-telemetry-scale-ha) (upcoming) |
| 📈 ioBroker | ioBroker setup, MQTT & charts | [iot-telemetry-scale-iobroker](https://github.com/wbommel/iot-telemetry-scale-iobroker) (upcoming) |

---

## 📚 Documentation

- [System Architecture](docs/ARCHITECTURE.md)
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
