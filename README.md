Gesture-Based Communication System for Speech-Impaired Individuals

## 📋 Project Overview

This project is designed to aid **speech-impaired (mute) individuals** in communicating effectively using a glove-based gesture recognition system. Each finger of the glove is equipped with a **flex sensor**, which detects bending motions. Specific combinations of finger movements are mapped to predefined messages. These messages are then converted to audio output via a speaker, enabling non-verbal communication.
Gesture recognition integrated into Internet of Things (IoT) systems is an emerging area of research with significant potential for various applications. This system primarily focuses on recognizing hand gestures to facilitate communication, especially for individuals with speech impairments. The proposed hand gesture recognition system employs sensors, such as flex sensors and accelerometers, to accurately capture hand movements. These sensors are connected to an IoT device, which processes the data and translates gestures into meaningful commands or text. The system is designed to be cost-effective, making it accessible for users who require assistive technologies.
One notable application of this technology is in aiding communication for speech-impaired individuals. By converting recognized gestures into text or speech, the system enables users to interact more effectively with their environment and with others. The integration of machine learning algorithms enhances the accuracy and efficiency of gesture recognition, allowing for real-time processing and feedback.Overall, the hand gesture recognition system using IoT aims to improve accessibility and communication for differently-abled individuals, showcasing the potential of combining hardware and software solutions to address real-world challenges in human-computer interaction

---

## 🎯 Key Features

- ✅ Gesture recognition using flex sensors.
- 🔊 Real-time conversion of hand gestures into spoken messages.
- 🧤 Wearable design for ease of use and comfort.
- 🛠️ Easily customizable with additional messages and gestures.
- 💡 Low-cost and scalable assistive technology.

---

## 🧰 Components Used

- Arduino UNO / Nano (or compatible microcontroller)
- Flex Sensors (1 for each finger)
- Audio Output Module (e.g., speaker or voice playback module)
- Glove (to mount the sensors)
- Jumper wires, resistors, and basic circuit components
- Power supply or battery pack

---

## ⚙️ How It Works

1. **Flex Sensors** detect the degree of bending on each finger.
2. The **Arduino** reads analog input values from the sensors.
3. Based on predefined thresholds and gesture combinations, a specific message is selected.
4. The message is sent to a **voice module or speaker** for audio output.

---

## 🚀 Getting Started

### 1. Hardware Setup
- Attach one flex sensor to each finger of the glove.
- Connect the sensors to the analog pins of the Arduino.
- Connect the audio output module to a digital pin.
- Power the Arduino with a USB cable or battery.

### 2. Code Upload
- // Define pin numbers
const int flexSensor1Pin = A0;  // Flex sensor 1 connected to analog pin A0
const int flexSensor2Pin = A1;  // Flex sensor 2 connected to analog pin A1
const int buzzerPin = 9;         // Buzzer connected to digital pin 9
const int ledPin = 13;           // LED connected to digital pin 13

// Threshold values for gesture recognition
const int threshold = 300;       // Adjust based on your calibration

void setup() {
Serial.begin(9600);            // Start serial communication
pinMode(buzzerPin, OUTPUT);    // Set buzzer pin as output
pinMode(ledPin, OUTPUT);        // Set LED pin as output
}

void loop() {
  // Read flex sensor values
  int flexValue1 = analogRead(flexSensor1Pin);
  int flexValue2 = analogRead(flexSensor2Pin);
// Print sensor values for debugging
Serial.print("Flex Sensor 1: ");
Serial.print(flexValue1);
Serial.print(" | Flex Sensor 2: ");
Serial.println(flexValue2);

  // Gesture recognition logic
  if (flexValue1 < threshold && flexValue2 < threshold) {
    // Gesture recognized: "Closed Fist"
Serial.println("Gesture: Closed Fist");
digitalWrite(buzzerPin, HIGH); // Activate buzzer
digitalWrite(ledPin, HIGH);     // Turn on LED
delay(1000);                    // Keep it on for 1 second
  } else if (flexValue1 > threshold && flexValue2 < threshold) {
    // Gesture recognized: "Open Hand"
Serial.println("Gesture: Open Hand");
digitalWrite(buzzerPin, HIGH); // Activate buzzer
digitalWrite(ledPin, LOW);      // Turn off LED
delay(1000);                    // Keep it on for 1 second
  } else {
    // No recognized gesture
digitalWrite(buzzerPin, LOW);  // Deactivate buzzer
digitalWrite(ledPin, LOW);      // Turn off LED
  }

  // Short delay before the next reading
delay(100);
}



### 3. Test
- Wear the glove and perform the predefined gestures.
- You should hear the corresponding message through the speaker.

---

## 🧠 Applications

- Communication aid for mute/dumb individuals.
- Can be used in hospitals, schools, or personal settings.
- Extendable to mobile app integration or IoT platforms.

---

## 📁 Repository Structure

Gesture-Speech-System/
│
├── ArduinoCode/
│ └── gesture_to_speech.ino
│
├── images/
│ └── demo_glove.jpg
│
├── README.md
└── LICENSE

yaml
Copy
Edit

---

## 📷 Demo

*![image](https://github.com/user-attachments/assets/a0c5da77-4a1f-46ed-9ff8-73b4fa7f01a3)

---

