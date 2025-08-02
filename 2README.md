# Arduino Task 2 - LED Control via Serial Monitor

## 🔧 Project Description
This project demonstrates controlling two LEDs using Serial input commands in Arduino UNO.

- Send `'1'` → Turn ON LED1 (Pin 13)
- Send `'0'` → Turn OFF LED1 (Pin 13)
- Send `'2'` → Turn ON LED2 (Pin 12)
- Send `'3'` → Turn OFF LED2 (Pin 12)

## 🖥️ Circuit Connections
| Component | Arduino Pin |
|----------|-------------|
| Red LED | 13 |
| Green LED | 12 |
| GND | GND |
| Resistors | 220Ω in series with each LED |

## 🔌 Components Used
- Arduino UNO
- 2 LEDs (Red & Green)
- 2 Resistors (220Ω)
- Breadboard and jumper wires

## 📸 Circuit Diagram
https://github.com/Sivanesan-ece/embedded-systems-internship/blob/main/Screenshot%202025-08-02%20142227.png

## 💻 Code
```cpp
char inputChar;

void setup() {
  Serial.begin(9600);
  pinMode(13, OUTPUT); // LED 1
  pinMode(12, OUTPUT); // LED 2
}

void loop() {
  if (Serial.available()) {
    inputChar = Serial.read();

    if (inputChar == '1') {
      digitalWrite(13, HIGH); // ON LED 1
    } else if (inputChar == '0') {
      digitalWrite(13, LOW);  // OFF LED 1
    } else if (inputChar == '2') {
      digitalWrite(12, HIGH); // ON LED 2
    } else if (inputChar == '3') {
      digitalWrite(12, LOW);  // OFF LED 2
    }
  }
}
