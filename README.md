# IoT-Smart-Plant-Pot
An energy-efficient, low-cost automatic watering system for plants powered by the ESP32 microcontroller. This project is designed for hobbyists and plant lovers who want a hassle-free way to take care of their plants, especially indoors.

👨‍💻 Team Members
Lê Đức Anh Toàn

Trịnh Phạm Phú Quang

Nguyễn Hoàng Nguyên Khải

📌 Project Overview
The Smart Plant Pot monitors soil moisture in real-time and waters the plant automatically when it gets too dry. The system is powered by 4 AA batteries and designed to operate for several months without human intervention.

Key Features:
🌿 Auto-waters plant based on soil moisture level

🔋 Long battery life (6–10 months)

⚡ Energy-efficient using ESP32's deep sleep mode

🔧 Low maintenance and budget-friendly

🪴 Uses Cây Rau Má in demonstration

🔧 Hardware Components
Component	Description
ESP32 Dev Board	Microcontroller that handles logic and control
Soil Moisture Sensor	Measures soil wetness
Relay Module	Controls the pump via GPIO
Mini Water Pump	Waters the plant when soil is dry
Plastic Tubing	Delivers water to the soil
4×AA Batteries (6V)	Powers the system

🔌 Circuit Design
Soil moisture sensor connected to ADC pin (34) of ESP32

Pump is powered via relay on GPIO pin (25)

ESP32 checks moisture levels every hour and triggers pump for 3 seconds if dry

System then enters deep sleep mode to conserve energy

💻 Source Code
The system is written in C++ using Arduino for ESP32. Main functionality:

Reads analog values from the sensor

Compares with dry threshold

Activates pump through relay if dry

Sleeps for 1 minute (or 1 hour in alternate versions)

📁 View full code in Plant-Pot-ESP.cpp

🔋 Power & Battery Life
Powered by 4 AA batteries (~2500 mAh total)

Estimated current draw: ~0.3 mA/hour

Estimated battery life: 6 to 10 months

Uses deep sleep and turns off sensor when idle

📈 Test Results
Moisture sensor responds accurately to soil condition

Pump waters reliably when triggered

Battery remains steady after days of testing

Wake cycle via deep sleep works as expected

🧠 Possible Improvements
📡 Wi-Fi integration for mobile alerts or remote monitoring

☀️ Solar-powered version for outdoor plants

🌤️ Add sensors for temperature, humidity, or light

📎 References
https://github.com/microsoft/IoT-For-Beginners/tree/main

https://pyimagesearch.com/2021/04/12/opencv-haar-cascades/

https://gisgeography.com/ndvi-normalized-difference-vegetation-index/

https://forum.arduino.cc/t/connect-a-6v-battery-to-the-vin-port/1047992

