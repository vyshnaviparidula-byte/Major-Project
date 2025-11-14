
# 🐛 Sericulture Automation System

## Project Overview

The **Sericulture Automation System** is an Internet of Things (IoT) based solution designed to modernize and optimize the process of silkworm rearing. 
The success of sericulture heavily relies on maintaining precise environmental conditions (temperature, humidity, ventilation).
This system uses a network of sensors and actuators to automatically monitor and regulate the rearing environment, reducing manual labor, preventing crop loss, and maximizing silk production yield and quality.

## ✨ Key Features

  * **Environmental Control:** Automatic maintenance of optimal temperature and humidity levels inside the rearing house using integrated actuators (fans, heaters, humidifiers).
  * **Real-time Monitoring:** Continuous logging and display of environmental data on a centralized dashboard (e.g., via a web app or mobile application).
  * **Automated Ventilation:** Smart control over air circulation to reduce CO2 build-up and ensure fresh air supply.
  * **Disease Prevention Alerts:** Early detection of abnormal conditions (e.g., sudden temperature spikes or excessive humidity) that could indicate a high risk of silkworm disease.
  * **Data Logging & Analysis:** Historical data storage on a cloud platform for long-term analysis, pattern recognition, and yield optimization.
  * **Remote Access:** Ability to monitor and manually override system settings remotely via the Internet.

## 💻 Technology Stack & Components

### Hardware Components

| Component | Purpose |
| :--- | :--- |
| **Microcontroller (e.g., ESP32/NodeMCU)** | The main control unit; reads sensor data, runs the control logic, and connects to the internet. |
| **DHT22/DHT11 Sensor** | Measures **Temperature** and **Humidity** in the rearing environment. |
| **MQ-135/CO2 Sensor** | Monitors **Air Quality** and potential CO2 build-up from silkworm respiration. |
| **Relay Module** | Acts as an electronic switch to control high-power AC/DC devices (fans, heaters, humidifiers). |
| **Actuators (Fan, Heater, Humidifier)** | Devices controlled by the relay module to regulate the environment. |
| **Power Supply** | Provides stable power to all electronic components. |

### Software and Platforms

| Component | Purpose |
| :--- | :--- |
| **Arduino IDE / PlatformIO** | Used for writing, compiling, and uploading the firmware to the microcontroller. |
| **C/C++ (for firmware)** | The programming language used for the microcontroller's logic. |
| **IoT Platform (e.g., ThingSpeak, Firebase, AWS IoT)** | Cloud service used for data storage, real-time visualization, and remote control. |
| **Web/Mobile Interface (Optional)** | Built using HTML/CSS/JavaScript or a framework like Flutter for a user-friendly dashboard. |

## ⚙️ Installation and Setup

### Prerequisites

1.  Installed **Arduino IDE** (or PlatformIO).
2.  Microcontroller (e.g., ESP32/NodeMCU) board support package installed in the IDE.
3.  Required libraries installed (e.g., for DHT sensor, Wi-Fi, MQTT/API communication).

### Hardware Wiring

Connect the components as follows:

  * `DHT22` Data Pin $\rightarrow$ Microcontroller Pin `D2`
  * `Relay Module` Signal Pins $\rightarrow$ Microcontroller Pins `D3`, `D4`, `D5` (for Fan, Heater, Humidifier)
  * Connect power to all components (ensure relays are connected to the appropriate external power supply for actuators).

### Software Configuration

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/your-username/sericulture-automation.git
    cd sericulture-automation
    ```
2.  **Configure Wi-Fi and IoT Platform:**
      * Open `src/config.h` (or similar file).
      * Update your Wi-Fi credentials:
        ```cpp
        const char* ssid = "YOUR_WIFI_SSID";
        const char* password = "YOUR_WIFI_PASSWORD";
        ```
      * Update your IoT platform API keys and endpoints.
3.  **Upload Firmware:**
      * Open the main sketch file (`main.ino` or similar) in your IDE.
      * Select the correct board and port.
      * Upload the code to the microcontroller.

## 🛠️ Usage

Once the system is powered on and connected to Wi-Fi, it will automatically begin monitoring and regulating the environment:

1.  **Dashboard Monitoring:** Access the centralized IoT dashboard (e.g., ThingSpeak channel) to view the live temperature, humidity, and CO2 readings.
2.  **Autonomous Control:** The system will automatically turn on the heater/humidifier if the temperature/humidity drops below the set lower threshold, and activate the fan if it exceeds the upper threshold.
3.  **Threshold Adjustment:** Environmental set-points (e.g., Temp: 25°C-28°C, Humidity: 60%-80%) can be adjusted by updating the corresponding values in the firmware or, if implemented, via the remote control interface.

## 🔮 Future Enhancements

  * **Machine Vision Integration:** Use a camera module (e.g., ESP32-CAM) and image processing to monitor silkworm growth stages and feeding activity.
  * **Automated Feeding System:** Integrate a mechanism for scheduled, automated dispensing of mulberry leaves/feed.
  * **Predictive Maintenance:** Implement machine learning models to predict actuator failures or required maintenance based on historical usage data.


 
