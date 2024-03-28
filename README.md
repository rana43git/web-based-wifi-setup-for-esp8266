# Web-Based Wi‑Fi Setup for ESP8266

Enable dynamic Wi‑Fi configuration on your ESP8266 via a simple web interface.

## 🔍 Overview

This project enables users to configure Wi-Fi credentials through a captive‑portal style web interface hosted by the ESP8266 module. On startup, the ESP attempts to connect using stored credentials; if it fails (or none exists), it starts an Access Point (AP) at `192.168.4.1` and serves a web page to enter SSID/password. Once saved, the device reconnects and persists credentials to EEPROM or flash.

## ⚙️ Features

- Automatic fallback to AP mode if no valid Wi-Fi credentials are found  
- Built-in web portal (captive‑style HTML page) for configuration  
- Persistence of settings across power cycles (via EEPROM or SPIFFS)  
- Lightweight Arduino sketch for ESP8266 (NodeMCU / WeMos D1 etc.)

## 📂 Repository Structure

```
/ (root)
├── your-sketch.ino
├── /data/ (if using SPIFFS for HTML files)
├── README.md
└── LICENSE (optional)
```

## 📥 Prerequisites

- **Arduino IDE** or **PlatformIO** with ESP8266 support  
- ESP8266 core for Arduino installed  
- Required libraries:  
  - `ESP8266WiFi.h`  
  - `ESP8266WebServer.h`  
  - `EEPROM.h`  
  - (Optional) `WiFiManager` if you plan to use it

## 🚀 Installation & Upload

1. Clone the repository:
   ```bash
   git clone https://github.com/rana43git/web-based-wifi-setup-for-esp8266.git
   cd web-based-wifi-setup-for-esp8266
   ```
2. Open the `.ino` file in Arduino IDE or PlatformIO.
3. Install required libraries if needed.
4. Select your ESP8266 board (e.g. NodeMCU 1.0).
5. Upload the sketch to the board.

## 🌐 How It Works

1. On boot, ESP tries to connect to previously saved Wi-Fi.
2. If it fails, it starts AP mode with SSID like `ESP8266_Setup`.
3. Connect to that AP and open `http://192.168.4.1` in browser.
4. Enter your Wi-Fi credentials and submit.
5. ESP saves and reboots, connecting to your network.

## 🎛️ Example Usage

To configure:
- Connect to ESP8266 AP (e.g. `ESP8266_Setup`)
- Go to: `http://192.168.4.1`
- Enter SSID and password
- Device will restart and connect to your router

After successful connection, you can access ESP with its local IP address.

## 🌟 Customization

| Feature                | How to Modify                                  |
|------------------------|------------------------------------------------|
| AP SSID/Password       | Change in sketch before starting AP mode       |
| HTML UI                | Edit embedded strings or serve via SPIFFS      |
| EEPROM/SPIFFS Settings | Customize for your device's storage method     |

## 📜 License

This project is open-source. You may add a license of your choice (e.g., MIT, GPL) here.

## 👨‍💻 Author

**Md. Shohel Rana**  
GitHub: [rana43git](https://github.com/rana43git)