# 🌊 AquaMonitor 

A **real-time water quality monitoring system** built with Arduino to measure **turbidity** (water clarity) and **water level**. This project includes a live **LCD display** and **audio alerts** for low water level warnings.

---

## 🌟 Features

- 📏 **Real-Time Turbidity Measurement** in NTU  
- 🌊 **Water Level Monitoring** with threshold-based alert  
- 🖥️ **Live Display** on 16x2 I2C LCD  
- 🔊 **Buzzer Alert** for low water level  
- 🔋 **Low Power Operation** (updates every 60 seconds)

---


## 🔩 Hardware Components and Connections

| Component                  | Purpose                         | Arduino Pin(s)         |
|---------------------------|----------------------------------|------------------------|
| **Arduino Uno / Nano**    | Microcontroller                  | —                      |
| **Turbidity Sensor**      | Measures water clarity (NTU)     | A1                     |
| **Water Level Sensor**    | Detects water level              | A0                     |
| **16x2 I2C LCD (0x27)**   | Displays turbidity & level data  | SDA: A4, SCL: A5       |
| **Buzzer**                | Audio alert for low water level  | D8                     |
| **Breadboard / PCB**      | Circuit assembly                 | —                      |
| **Jumper Wires**          | Wiring connections               | —                      |

---

## 🔌 Circuit Diagram
<div align="center">
  <img src="https://github.com/user-attachments/assets/e57323e0-5d8a-4334-b713-9112899a3a7a" alt="Circuit Diagram" width="700px">
</div>

---

## 📚 Required Libraries

Install the following libraries using the **Arduino Library Manager**:

- [`Wire.h`](https://www.arduino.cc/en/Reference/Wire) (built-in)
- [`LiquidCrystal_I2C.h`](https://github.com/johnrickman/LiquidCrystal_I2C)

---

## 🚀 Installation & Setup

### 🔌 Hardware Setup

- Connect all components based on the pin configuration table above.


### 💻 Software Setup

```bash
git clone https://github.com/Janvi-M/AquaMonitor.git
cd AquaMonitor
```

+  Open `turbidity_water_monitor.ino` in Arduino IDE  
+  Select your board and COM port  
+  Click **Upload** to flash the code  

--- 
## ⚙️ Configuration Options

Update the following values in the .ino file as needed:

```
if (water_level < 200) {     // Water level threshold
  tone(buzzer_pin, 1000);    // Buzzer frequency in Hz
  delay(2000);               // Alert duration in milliseconds
}
delay(60000);                // Reading interval in milliseconds

```

| Parameter             | Default   | Description                        |
| --------------------- | --------- | ---------------------------------- |
| Turbidity ADC Range   | 0–208     | Mapped to 300–0 NTU                |
| Water Level Threshold | 200       | Level below which buzzer triggers  |
| Buzzer Frequency      | 1000 Hz   | Tone frequency                     |
| Alert Duration        | 2 seconds | Duration of buzzer sound           |
| Reading Interval      | 60 secs   | Time delay between sensor readings |

---

## 🎥 Demo
<div align="center">
  <img src="https://github.com/user-attachments/assets/9d1b52bf-d928-4eb7-a2b1-96221f3da803" alt="Demo Video" width="700px">
</div>




