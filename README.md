# Task 1: Temperature Sensor Monitoring using Arduino

This task simulates temperature monitoring using a DHT11 sensor and Arduino Uno. The temperature values are read and displayed on the serial monitor.

## Components Used
- Arduino Uno
- DHT11 Sensor
- Breadboard and jumper wires

## Screenshot
(https://github.com/Sivanesan-ece/embedded-systems-internship/blob/main/Screenshot%202025-08-02%20135853.png)

## Output
Displays temperature and humidity on the serial monitor.

## Code
// Task 1: Temperature Sensor Monitoring using LM35
const int sensorPin = A0;
float voltage, temperature;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int reading = analogRead(sensorPin); // Convert analog reading to voltage
  voltage = reading * (5.0 / 1023.0);
  temperature = (voltage - 0.5) * 100.0; // Convert voltage to Celsius

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");

  delay(1000);  // Wait 1 second
}

