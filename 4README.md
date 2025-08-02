# Task 4 - Simulated Speech Command LED Control using Arduino

## Description
This project simulates a speech-command-based LED controller using two push buttons in Tinkercad. Each button mimics a voice command:
- **Button 1:** "Turn ON"
- **Button 2:** "Turn OFF"

It is a beginner-friendly task in embedded systems and helps understand how speech-command simulations can be implemented using simple digital inputs.

## Components Used
- Arduino UNO
- LED
- 2 Push Buttons
- Breadboard
- Resistors
- Jumper Wires

## Circuit Design
The push buttons are connected to digital pins 2 and 3, and the LED is connected to pin 8. The serial monitor logs the simulated speech commands.

## Code
// Task 4 - Speech-Based LED Control using Buttons

const int buttonOn = 2;    // Button to simulate "Turn ON" speech
const int buttonOff = 3;   // Button to simulate "Turn OFF" speech
const int ledPin = 8;      // LED pin

void setup() {
  pinMode(buttonOn, INPUT);
  pinMode(buttonOff, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);  // Start serial communication for speech simulation log
}

void loop() {
  // Check if ON button is pressed
  if (digitalRead(buttonOn) == HIGH) {
    digitalWrite(ledPin, HIGH);  // Turn LED ON
    Serial.println("Speech Command: Turn ON");  // Simulated speech output
    delay(500);  // Debounce delay
  }

  // Check if OFF button is pressed
  if (digitalRead(buttonOff) == HIGH) {
    digitalWrite(ledPin, LOW);  // Turn LED OFF
    Serial.println("Speech Command: Turn OFF");  // Simulated speech output
    delay(500);  // Debounce delay
  }
}


## Output
The LED turns ON/OFF based on the button pressed and prints:
- `Speech Command: Turn ON`
- `Speech Command: Turn OFF`

in the Serial Monitor.

## Screenshot
https://github.com/Sivanesan-ece/embedded-systems-internship/blob/main/Screenshot%202025-08-02%20143001.png
