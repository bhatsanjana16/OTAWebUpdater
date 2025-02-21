# OTAWebUpdater
# ESP32 Web-Based Firmware Updater & LED Controller

Overview
This project sets up an ESP32 as a web server with a login authentication page, allowing users to upload firmware updates via a web interface. Additionally, it controls an LED based on the state of a connected switch.

Features
- Web-Based Firmware Update: Users can upload new firmware files via the `/update` endpoint.
- User Authentication: Basic login page that redirects authorized users to the firmware update page.
- WiFi Connectivity: The ESP32 connects to a predefined WiFi network.
- LED Control: The onboard LED (GPIO 2) is controlled by a switch connected to GPIO 33.
- mDNS Support: The ESP32 can be accessed via `http://esp32.local`.

Hardware Requirements
- ESP32 development board
- LED connected to GPIO 2 (built-in for many ESP32 boards)
- Switch connected to GPIO 33
- WiFi network for connectivity

Software Requirements
- Arduino IDE or PlatformIO
- ESP32 board package installed
- Libraries:
  - `WiFi.h`
  - `WiFiClient.h`
  - `WebServer.h`
  - `ESPmDNS.h`
  - `Update.h`

Installation & Setup
1. Clone this repository or copy the provided code into your Arduino IDE.
2. Modify the WiFi credentials in the `setup()` function:
   ```cpp
   const char* ssid = "your_wifi_ssid";
   const char* password = "your_wifi_password";
   ```
3. Upload the code to your ESP32 board.
4. Connect to the ESP32 Web Interface:
   - Find the ESP32's IP address in the serial monitor.
   - Open a web browser and enter `http://<ESP32_IP>` or `http://esp32.local`.
5. Login with Credentials:
   - Username: `Samsung`
   - Password: `12131415`
   - Upon successful login, you will be redirected to the firmware update page.
6. Upload Firmware:
   - Choose a `.bin` firmware file and click `Update`.
   - The ESP32 will restart after a successful update.

File Structure
```
|-- esp32_firmware_update
    |-- esp32_firmware_update.ino  # Main code file
    |-- README.md                   # Project documentation
```

Troubleshooting
- ESP32 not connecting to WiFi?
  - Ensure the correct SSID and password are set.
  - Check if the WiFi network is operational.
- Web interface not opening?
  - Check the serial monitor for the ESP32's IP address.
  - Ensure your computer is on the same network as the ESP32.
- Firmware upload fails?
  - Ensure the firmware file is compatible with ESP32.
  - Check the console logs for errors.



