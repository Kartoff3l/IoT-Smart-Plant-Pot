# 🌱 Smart Plant Pot – IoT Project

> An energy-efficient, battery-powered automatic watering system for plants using the ESP32 microcontroller.

---

## 👥 Team Members

- **Lê Đức Anh Toàn**
- **Trịnh Phạm Phú Quang**
- **Nguyễn Hoàng Nguyên Khải**

---

## 📌 Overview

The **Smart Plant Pot** detects soil moisture and automatically waters your plant when it's dry. Designed to be:

- 🔋 Low-power & battery-efficient (6–10 months)
- 🪴 Self-sustaining with minimal user input
- 💡 Ideal for indoor plant lovers
- ⚙️ Built with budget-friendly, easily available components

---

## 🔧 Hardware Components

| Component              | Description                                      |
|------------------------|--------------------------------------------------|
| `ESP32 Dev Board`      | Main microcontroller                            |
| `Soil Moisture Sensor` | Measures moisture level in soil                 |
| `Relay Module`         | Switches the pump on/off                        |
| `Mini Water Pump`      | Delivers water to the plant                     |
| `Plastic Tubing`       | Guides water from container to plant            |
| `4 × AA Batteries`     | Powers the entire system (~6V)                  |

---

## 🔌 Circuit Diagram

- Moisture sensor → ADC pin **GPIO 34**
- Pump (via Relay) → GPIO **25**
- System wakes, reads sensor, and turns pump ON for 3s if dry
- Then enters **deep sleep** to save power

---

## 💻 Source Code

Written in **Arduino C++** for ESP32.

### 🔹 Core Logic:

```cpp
constexpr int SENSOR_PIN = 34;
constexpr int PUMP_PIN = 25;
constexpr int DRY_LIMIT = 2200;

void loop() {
  int moisture = analogRead(SENSOR_PIN);
  if (moisture > DRY_LIMIT) {
    pump(true);
    delay(3000);
    pump(false);
  }
  delay(60000); // Wait 1 minute
}
```
