# 🚗 Vehicle Plate Recognition System

A license plate recognition system using **NodeMCU**, **Python**, and a **webcam** that automatically captures images when a **trigger button** is pressed and displays results on an **OLED screen**.

---

## 🎬 Demo
https://github.com/Parwez44/vehicle-plate-recognition-system/blob/main/demofinal.mp4?raw=true

---

## 🛠️ Components Needed
- NodeMCU ESP8266  
- SSD1306 OLED Display (128x64)  
- Push Button  
- Computer Webcam  
- Breadboard  
- Jumper Wires  


---

## 🔌 Connections

### OLED Display:
NodeMCU → OLED Display
3.3V → VCC
GND → GND
D1 (GPIO5) → SCL
D2 (GPIO4) → SDA

shell
Copy code

### Trigger Button:
NodeMCU → Push Button
3.3V → One leg of button
GPIO0 (D3) → Other leg of button
GND → 10K resistor to GPIO0 leg (pull-down)

yaml
Copy code

---

## 📋 Setup

### 1. Install Python Dependencies
```bash
pip install opencv-python pytesseract pyserial numpy
2. Install Tesseract OCR
Download from: Tesseract OCR for Windows

3. Upload Arduino Code
Upload plate_recognition_nodemcu.ino to NodeMCU

Use Arduino IDE with:

Adafruit SSD1306 Library

Adafruit GFX Library

🚀 Usage
Update the Python script with your COM port:

python
Copy code
SERIAL_PORT = 'COM6'  # Change to your port
Run the Python program:

bash
Copy code
python plate_recognition.py
Press the physical button to capture images

The system automatically processes the image and displays the recognized text on the OLED screen

Type 'q' in the terminal to quit

📁 Files
plate_recognition_nodemcu.ino → Arduino code with button trigger

plate_recognition.py → Python code for image processing and OCR

⚙️ Features
🟢 Button Trigger – Physical button for manual image capture

⚙️ Auto Processing – Captures and processes images automatically

🖥️ Real-Time Display – Shows recognized text on OLED screen

🔤 OCR Processing – Uses Tesseract with multiple configurations

🔌 Serial Communication – Seamless data transfer between Python and NodeMCU

🔧 How It Works
Press the button → NodeMCU sends a "CAPTURE" signal via serial

Python script detects the signal and captures an image from the webcam

Image is processed using OpenCV and Tesseract OCR

Extracted plate text is sent back to NodeMCU

NodeMCU displays the recognized text on the SSD1306 OLED screen

🐛 Troubleshooting
Check the COM port in your Python code

Verify button wiring and pull-down resistor

Ensure Tesseract is installed and accessible from PATH

Test webcam permissions if image capture fails

Monitor serial communication for debug messages

📜 License
This project is licensed under the MIT License — feel free to use and modify it.

💡 Developed by Parwez44 with collaboration  — a simple yet powerful IoT vision project combining NodeMCU, OpenCV, and Python.
