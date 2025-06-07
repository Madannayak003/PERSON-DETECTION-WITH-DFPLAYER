# PERSON-DETECTION-WITH-DFPLAYER

# Ultrasonic-Based Audio Welcome & Exit System Using DFPlayer Mini

This Arduino project uses **ultrasonic sensors** to detect people entering or exiting an area. When detected, it plays a **welcome** or **thank you** audio message using the **DFPlayer Mini MP3 module**.

---

## 📦 Features

- 🎵 Plays **"Welcome"** audio when a person is detected at the **entry point**.
- 🎵 Plays **"Thank you"** audio when a person is detected at the **exit point**.
- 📏 Uses **ultrasonic distance measurement** to detect presence within **5 meters**.
- 🔊 Uses **DFPlayer Mini** for standalone audio playback (no need for internet or computer).

---

## 🛠️ Required Components

| Component               | Quantity |
|------------------------|----------|
| Arduino Uno/Nano       | 1        |
| HC-SR04 Ultrasonic Sensor | 2      |
| DFPlayer Mini MP3 Module | 1       |
| MicroSD Card (formatted FAT32) | 1 |
| Speaker (3W recommended) | 1       |
| Jumper Wires           | As needed|
| Breadboard (optional)  | 1        |

---

## 🔌 Pin Configuration

| Module              | Arduino Pin |
|---------------------|-------------|
| Entry Trigger       | D2          |
| Entry Echo          | D3          |
| Exit Trigger        | D4          |
| Exit Echo           | D5          |
| DFPlayer RX (to TX) | D10         |
| DFPlayer TX (to RX) | D11         |
| DFPlayer VCC        | 5V          |
| DFPlayer GND        | GND         |

> ⚠️ **Important:**  
> Store the following MP3 files on the SD card:
> - `0001.mp3` → Welcome message  
> - `0002.mp3` → Thank you message  

---

## 💾 How to Use

1. Format a **microSD card** as FAT32.
2. Add two MP3 files:
   - `0001.mp3` – Welcome message
   - `0002.mp3` – Thank you message
3. Insert the SD card into the DFPlayer Mini module.
4. Wire all components as per the pin configuration above.
5. Upload the Arduino code provided in this repository.
6. Power the system and test it by walking in front of the entry and exit sensors.

---

## 🧠 Code Overview

```cpp
// Entry sensor detects presence and plays welcome message
if (distanceEntry > 0 && distanceEntry <= 500) {
  myDFPlayer.play(1); // 0001.mp3
}

// Exit sensor detects presence and plays thank-you message
if (distanceExit > 0 && distanceExit <= 500) {
  myDFPlayer.play(2); // 0002.mp3
}
```
Libraries Used
//DFRobotDFPlayerMini

Install via Arduino Library Manager:
Sketch > Include Library > Manage Libraries > Search "DFRobotDFPlayerMini"

Author
Developed by: MADAN.R
GitHub: https://github.com/Madannayak003

License
This project is licensed under the MIT License - free to use and modify.

## 🌐 Website
[![Netlify Status](https://img.shields.io/badge/Live%20Site-Netlify-brightgreen?style=for-the-badge&logo=netlify)](https://stellular-genie-403aa8.netlify.app)
