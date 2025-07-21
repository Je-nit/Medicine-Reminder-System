# 💊 Medicine Reminder System Using LPC2148

## 📘 Project Description  
This project is designed to remind users to take medicine at specific times using an ARM7 LPC2148 microcontroller. It relies on various embedded peripherals including:

- LCD display for showing time, menus, and alerts  
- RTC (Real-Time Clock) to track time and date  
- Keypad for user input and navigation  
- Buzzer to alert the user when it's medicine time  
- GPIO switches (SW1, SW2) for mode control and acknowledgement  

The system continuously monitors the RTC. When the current time matches the preset medicine time (±2 seconds), the buzzer sounds until SW2 is pressed.

---

## 🔧 Hardware Requirements  
- LPC2148 Development Board  
- 16x2 LCD  
- 4x4 Matrix Keypad  
- RTC (DS1307 or on-chip RTC of LPC2148)  
- Buzzer (connected to P1.24)  
- Push Buttons  
  - SW1: Mode selection  
  - SW2: Acknowledge alert  
- Power Supply  
- Connecting Wires  

---

## 📌 Pin Connections  
- LCD: Connected via control and data pins (refer to `lcd.h`)  
- Keypad: Connected to GPIO P0.16–P0.23 (see `keypad_defines.h`)  
- RTC: On-chip RTC (refer to `rtc.h`)  
- SW1: Connected to P0.5  
- SW2: Connected to P0.6  
- Buzzer: Connected to P1.24  

---

## 🎛️ Keypad Pin Mapping  
- Row0 → P0.16  
- Row1 → P0.17  
- Row2 → P0.18  
- Row3 → P0.19  
- Col0 → P0.20  
- Col1 → P0.21  
- Col2 → P0.22  
- Col3 → P0.23  

---

## 💻 Software Requirements  
- Keil uVision IDE for coding and compiling  
- Flash Magic for programming the LPC2148 microcontroller  
- Header files used:  
  - `lcd.h`  
  - `rtc.h`  
  - `keypad.h`  
  - `delay.h`  
  - `defines.h`  
  - `keypad_defines.h`  

---

## 🚀 How to Use the Project  

### Initial Setup  
- Flash the compiled program to LPC2148 using Flash Magic  
- Power on the board  
- LCD displays current RTC time and medicine time  

### Mode Selection via SW1  
- Press SW1 to access menu:  
  - Option 1: Edit RTC  
  - Option 2: Set Medicine Time  

### RTC Edit (Option 1)  
- Use keypad to enter time and date values  
- If invalid entries are made, re-entry is requested  

### Update Medicine Time (Option 2)  
- Press SW1 again to set medicine reminder time  
- Enter Hour, Minute, Second using keypad  
- Press Exit to return to main screen  

### Medicine Alert  
- When RTC matches medicine time ±2 seconds:  
  - LCD displays an alert  
  - Buzzer sounds until SW2 is pressed  

---

## 📝 Notes  
- Valid Time Ranges:  
  - Hour: 0–23  
  - Minute/Second: 0–59  
  - Date: 1–31  
  - Month: 1–12  
  - Day of Week: 0–6 (0 = Sunday)  
- Buzzer toggles periodically during alert  
- Debouncing of SW1 and SW2 is assumed  

---

Let me know if you'd like help designing schematics, writing test cases, or preparing slides for project presentation. I’m here to collaborate! 🌟
