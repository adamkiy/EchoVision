# EchoVision 🔊📷
**An assistive vision system for the visually impaired, combining ESP32-CAM, OpenAI, Google Text-to-Speech, and Flask.**

---

## 🧠 What It Does
EchoVision captures an image using the ESP32-CAM, sends it to a local Flask server that uses OpenAI’s GPT-4o vision model to describe the scene, and then converts the description to spoken audio using Google Text-to-Speech. The result: a spoken summary of what's in front of the user.

---

## 🌐 System Architecture

![System Architecture] <img width="1024" height="1024" alt="ChatGPT Image Jul 19, 2025 at 04_26_10 AM" src="https://github.com/user-attachments/assets/b01a01d4-35f9-4e7e-8d16-938bbb66f0f5" />



---

## 🔧 Tech Stack

- **ESP32-CAM** (client hardware)
- **Arduino** (C++ code)
- **Flask** (Python server)
- **OpenAI GPT-4o** (image understanding)
- **Google Cloud TTS API** (text-to-speech)
- **MicroSD Storage** (for saved photos + audio)

---

## 🚀 How It Works

1. **User presses a physical button** on the ESP32.
2. **ESP32-CAM captures an image** and saves it to SD card.
3. **Image is sent via HTTP POST** to the Flask server.
4. **Flask sends image to GPT-4o**, asking for a short description.
5. **Description is sent to Google TTS**, which returns an MP3.
6. **ESP32 receives MP3** and stores it to SD card.
7. **System plays the MP3**, describing the scene aloud.

---

## 🛠️ How to Run

### 📦 Server (Python Flask)
1. Clone the repo
2. Create `.env` from template:
   ```bash
   cp server/.env.example server/.env
