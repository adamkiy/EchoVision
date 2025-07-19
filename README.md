# EchoVision 🔊📷
**An assistive vision system for the visually impaired, combining ESP32-CAM, OpenAI, Google Text-to-Speech, and Flask.**

---

## 🧠 What It Does
EchoVision captures an image using the ESP32-CAM, sends it to a local Flask server that uses OpenAI’s GPT-4o vision model to describe the scene, and then converts the description to spoken audio using Google Text-to-Speech. The result: a spoken summary of what's in front of the user.

---

## 🌐 System Architecture

![System Architecture](./A_flowchart-style_diagram_illustrates_the_EchoVisi.png)


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
