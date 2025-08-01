# HOME-AUTOMATION-SYSTEM

**COMPANY:** CODTECH IT SOLUTIONS

**NAME:** I ROHITH KUMAR

**INTERN ID:** CT04DG1391

**DOMAIN:** INTERNET OF THINGS

**DURATION:** 4 WEEKS

**MENTOR:** NEELA SANTOSH

# DESCRIPTION
Description: The goal of this project is to create a Home Automation System prototype where the user can operate various home appliances like lights, fans, and doors using Internet of Things (IoT) concepts in Tinkercad. This automation is obtained with the help of sensors, actuators, and an Arduino Uno microcontroller programmed through Arduino IDE.

**Components Used:**
HC-SR04 Ultrasonic Sensor – For proximity sensing to identify whether a person or object is present.
PIR Motion Sensor – Senses human movement and causes actions like lights coming on or doors opening.
Temperature Sensor (TMP36) – Senses ambient temperature and shows the reading on the Serial Monitor. This can be used for automatic fan control depending on temperature.
Servo Motor and DC Motor – Mimics door motion and fan operation respectively.

**Working Principle:** 
Upon detection of motion by the PIR sensor, the servo motor is automatically engaged, which replicates the opening mechanism of a door. This gives contactless entry, adding an element of security and hygiene. •The ultrasonic sensor is placed to measure the distance of objects from it. A light or alarm (LED indicator) can be initiated if a detected object is within a specified range, providing real-time intruder or object proximity alerts. •The temperature from around the TMP36 is read by the temperature sensor. The information is processed by the Arduino and is displayed real-time on the Serial Monitor. When temperature exceeds a specific value (programmable), the DC motor mimics the action of a fan switching on. •LEDs are utilized to mimic lights and are programmed to turn on/off in response to motion detection and proximity sensing. The Arduino Uno acts as the master controller. It is linked to the breadboard using jumper wires, and the components exchange data with the microcontroller via digital and analog pins. The DC motor is controlled using an L293D motor driver in order to provide proper current supply and direction control.

**code:**
**#include<servo.h>**

**const int pingpin=7**

**int servopin=8**

**servo servo1;**

**void setup(){**

**serial begin(9600);**

**servol attach (servopin);**

**pinMode (2,INPUT);**

**pinMode (4,OUTPUT);**

**pinMode (11,OUTPUT);**

**pinMode (12,OUTPUT);**

**pinMode (13,OUTPUT);**

**pinMode (Ao,INPUT);**

**digitalWrite (2,LOW);**

**digitalWrite (11,HIGH);**

**}**

**voidloop(){**


**Overview of Code:**
Main Loop The loop() function repetitively runs three independent systems:

Ultrasonic Sensor (Distance Measurement): Uses pingPin to send a 5-microsecond pulse and measure the echo duration. Converts the echo duration to distance in inches and centimeters using helper functions: microsecondsToInches: Divides microseconds by 74 and halves it (based on sound speed in air). microsecondsToCentimeters: Divides microseconds by 29 and halves it. Sets the servo (servo1): If the distance is under 40 cm, turns the servo to 90 degrees and pauses for 2 seconds. Otherwise, sets the servo to 0 degrees.

PIR Sensor (Motion Detection): Reads the PIR sensor on pin 2. If motion detected (HIGH), turns on LED on pin 4 for 1 second. If no motion (LOW), switches off the LED.

Temperature Sensor (Fan Control): Reads analog value from pin A0 (temperature sensor). Scales the value to temperature using a factor (value  0.48). Outputs temperature to the Serial Monitor. Manages a fan (through pins 12 and 13): If temperature is above 20°C, makes pin 12 HIGH (fan on) and pin 13 LOW. Otherwise, makes both pins 12 and 13 LOW (fan off).

# OUTPUT:
**When a person enters the door gets opened**
<img width="1440" height="762" alt="Image" src="https://github.com/user-attachments/assets/cbf7f6ef-b9e8-4b30-8b08-8da50900395f" />

**After 2 seconds the door closes automatically**
<img width="1443" height="743" alt="Image" src="https://github.com/user-attachments/assets/86353b4e-51a0-4fb6-ae4e-7f480eb44181" />

**When a person is in the range of PIR sensor the lights turn on**
<img width="1241" height="763" alt="Image" src="https://github.com/user-attachments/assets/e67845a4-635c-45ad-bea6-79fb85aae90e" />

**When a person leaves the range of the of PIR sensor lights turn off**
<img width="1224" height="757" alt="Image" src="https://github.com/user-attachments/assets/f4937ef7-cc85-4be7-9a89-29b871aca0ca" />

**When a person leaves the room (temperature decreases) then the fan turns off (when the temperate is less than 20*C)**
<img width="1868" height="700" alt="Image" src="https://github.com/user-attachments/assets/ff68cc5b-a32f-4604-a1d7-9c358b6a4d13" />

**When a person enters the room (temperature increases) then the fan turns on (when the temperate is more than 20*C)**
https://github.com/user-attachments/assets/5a3924bd-fae9-48d4-8142-232df9cfa81c
      **(press the link for video refference.)**
