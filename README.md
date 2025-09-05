# LED Control System using NodeMCU

## 📖 Project Overview
This project implements a wireless LED control system using NodeMCU ESP8266. It allows users to control LEDs remotely through a web interface, making it ideal for home automation, IoT applications, and learning ESP8266 programming.

![LED Control System](https://img.shields.io/badge/NodeMCU-ESP8266-orange.svg)
![IoT](https://img.shields.io/badge/IoT-Home_Automation-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 🚀 Features
- **Web-based Control**: Control LEDs through a responsive web interface
- **Multiple Control Modes**: Manual on/off, PWM dimming, and scheduling
- **Wireless Connectivity**: Built on Wi-Fi technology (802.11 b/g/n)
- **Cross-Platform**: Accessible from any device with a web browser
- **Real-time Feedback**: Immediate visual confirmation of LED status

## 📋 Hardware Requirements
| Component | Quantity | Notes |
|-----------|----------|-------|
| NodeMCU ESP8266 | 1 | Main controller |
| LEDs | 1-8 | Any color |
| Resistors (220Ω) | As needed | Current limiting for LEDs |
| Breadboard | 1 | For prototyping |
| Jumper Wires | Several | For connections |
| Micro-USB Cable | 1 | For power and programming |

## 🔧 Wiring Diagram

### Basic Connection (1 LED)
```
NodeMCU D1 → 220Ω Resistor → LED (+) → LED (-) → NodeMCU GND
```

### Multiple LEDs Connection
```
NodeMCU D1 → Resistor → LED1 → GND
NodeMCU D2 → Resistor → LED2 → GND
NodeMCU D3 → Resistor → LED3 → GND
... (up to 8 LEDs)
```

## ⚙️ Software Requirements
- Arduino IDE (with ESP8266 board support)
- Required Libraries:
  - ESP8266WiFi
  - ESP8266WebServer
  - WiFiManager (optional for easy configuration)

## 🛠️ Installation & Setup

### 1. Arduino IDE Configuration
1. Install Arduino IDE from [arduino.cc](https://www.arduino.cc/en/software)
2. Add ESP8266 board support:
   - Go to File → Preferences
   - Add `http://arduino.esp8266.com/stable/package_esp8266com_index.json` to Additional Boards Manager URLs
   - Install ESP8266 platform via Boards Manager

### 2. Uploading the Code
1. Clone this repository or download the source code
2. Open `led_control_nodemcu.ino` in Arduino IDE
3. Select NodeMCU 1.0 (ESP-12E Module) from Tools → Board
4. Set correct COM port
5. Click Upload

### 3. Network Configuration
1. After uploading, the NodeMCU will create a WiFi access point named "LED-Control-AP"
2. Connect to this AP (password: "12345678")
3. Open a browser and go to `192.168.4.1`
4. Configure your WiFi credentials on the web page

## 🌐 Web Interface Usage
Once connected to your network:
1. Find the IP address assigned to your NodeMCU (check serial monitor or router admin page)
2. Open a web browser and navigate to the IP address
3. The control interface will appear with:
   - On/Off toggle switches for each LED
   - Brightness sliders for dimmable LEDs
   - Schedule setup interface
   - System status information

## 📚 Code Structure
```
led_control_nodemcu/
├── led_control_nodemcu.ino  # Main Arduino sketch
├── index.h                  # HTML/CSS/JS for web interface
├── readme.md               # This file
└── schematics/             # Wiring diagrams
    ├── single_led.fzz
    └── multiple_leds.fzz
```

## 🔌 API Endpoints
The system provides these HTTP endpoints for programmatic control:

- `GET /` - Serve control web page
- `GET /status` - Return JSON status of all LEDs
- `POST /control` - Control specific LED (parameters: `led`, `state`, `brightness`)
- `POST /schedule` - Set scheduling for LEDs

## 💡 Example Usage Scenarios
1. **Home Lighting Control**: Control room lights from your phone
2. **Aquarium Lighting**: Schedule LED strips for fish tanks
3. **Plant Growth Lights**: Automate grow lights for indoor plants
4. **Mood Lighting**: Create lighting scenes for different occasions
5. **Education**: Learn about IoT, programming, and electronics

## 🔮 Future Enhancements
- [ ] MQTT support for integration with home automation systems
- [ ] Voice control compatibility (Alexa, Google Assistant)
- [ ] Time-based automation/scheduling
- [ ] Energy consumption monitoring
- [ ] OTA (Over-The-Air) updates
- [ ] Temperature and light sensors integration

## 🐛 Troubleshooting
| Issue | Solution |
|-------|----------|
| Can't connect to WiFi | Check credentials, signal strength |
| Web interface not loading | Check IP address, restart NodeMCU |
| LEDs not responding | Check wiring, verify GPIO pins in code |
| NodeMCU not detected | Install correct drivers, check USB cable |

## 📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check [issues page](https://github.com/yourusername/led-control-nodemcu/issues).

## 🙏 Acknowledgments
- NodeMCU community for excellent documentation
- Arduino and ESP8266 development teams
- Contributors to the ESP8266WiFi and WebServer libraries

## 📞 Support
If you have any questions or run into problems, please:
1. Check the troubleshooting section above
2. Search existing issues on GitHub
3. Create a new issue with details about your problem

---

**Happy Making!** ✨💡
