# Task 3 - Temperature Sensor with LCD and Serial Monitor

This project reads temperature using an analog temperature sensor (TMP36 or LM35) and displays it on a 16x2 LCD and the Serial Monitor.

## 🔧 Components Used
- Arduino Uno
- Breadboard
- TMP36 / LM35 Temperature Sensor
- 16x2 LCD (I2C)
- Jumper Wires
- USB Cable

## 🧠 Working Principle
1. The analog output of the temperature sensor is connected to A0.
2. The sensor output is converted to voltage.
3. Voltage is converted to temperature in °C.
4. Displayed on LCD and Serial Monitor.

## 🔌 Circuit Connections
### Sensor (TMP36 / LM35):
- VCC → 5V
- GND → GND
- OUT → A0

### I2C LCD:
- VCC → 5V  
- GND → GND  
- SDA → A4  
- SCL → A5
## circuit
https://github.com/Sivanesan-ece/embedded-systems-internship/blob/main/Screenshot%202025-08-02%20142905.png
## 🧾 Arduino Code
```cpp
const int sensorPin = A0;

void setup() {
  Serial.begin(9600);         // Start serial communication
  lcd.init();                 // Initialize LCD
  lcd.backlight();            // Turn on backlight
}

void loop() {
  int reading = analogRead(sensorPin);
  float voltage = reading * 5.0 / 1024.0;
  float temperatureC = voltage * 100.0;

  // Serial Monitor
  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.println(" °C");

  // LCD Output
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Temp: ");
  lcd.print(temperatureC);
  lcd.print(" C");

  delay(1000);
}
