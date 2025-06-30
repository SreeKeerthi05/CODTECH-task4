# CODTECH-task4

"NAME" : LINGAM SREE KEERTHI


"COMPANY" : CODTECH IT SOLUTIONS


"PROJECT BASED ON" : IOT  


"ID" : CT04DF1246


"PROJECT MENTOR" : NEELA SANTOSH


OVERVIEW OF THE PROJECT:
Motion Detection Security System is a smart surveillance solution designed to monitor an area, detect any movement, capture evidence (like images or video), and alert the user in real-time. This type of system is commonly used for home, office, or restricted area security.


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
