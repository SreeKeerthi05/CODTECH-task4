# CODTECH-task4

"NAME" : LINGAM SREE KEERTHI


"COMPANY" : CODTECH IT SOLUTIONS


"PROJECT BASED ON" : IOT  


"ID" : CT04DF1246


"PROJECT MENTOR" : NEELA SANTOSH


OVERVIEW OF THE PROJECT:
IoT-based Air Quality Monitoring System is a smart device designed to continuously monitor environmental air parameters and provide real-time data through internet connectivity. These systems are especially useful in urban areas, industrial zones, and smart cities to track pollution levels and take preventive actions.


Working Principle

1. Sensors collect air quality and environmental data.


2. Microcontroller reads and processes the data.


3. Data is transmitted via Wi-Fi to an online platform.


4. Users can view the data on a mobile app or dashboard.


5. Alerts or actions (e.g., turning on a purifier) can be automated.


COMPONENTS:


✅ Arduino Uno

✅ MQ-135 Gas Sensor (air quality sensor)

✅ I2C LCD Display (16x2) (or use Serial Monitor)

✅ Breadboard

✅ Connecting Wires


#CODE


#include <Wire.h>
#include <LiquidCrystal_I2C.h>

const int gasSensor = A0;
int air_quality;

LiquidCrystal_I2C lcd(0x27, 16, 2); // I2C address might be 0x3F in some LCDs

void setup() {
  lcd.begin(16, 2);
  lcd.backlight();
  Serial.begin(9600);
  lcd.setCursor(0,0);
  lcd.print("Air Quality:");
}

void loop() {
  air_quality = analogRead(gasSensor);
  lcd.setCursor(0, 1);
  lcd.print("Value: ");
  lcd.print(air_quality);
  Serial.print("Air Quality: ");
  Serial.println(air_quality);
  delay(1000);
}
