# Obstacle-Avoiding-Robot-MultiSensor
Autonomous 4WD multi-sensor obstacle-avoidance robot using Arduino, ultrasonic sensing, and servo-based environmental scanning.

📌 Overview

This project is an autonomous obstacle-avoiding robot built using Arduino UNO, ultrasonic sensor, servo motor, and 4 DC motors.
The robot constantly scans its surroundings, detects obstacles, and automatically chooses the safest direction to move.

This repository includes:

Well-commented Arduino code

Flowchart of the navigation logic

Sensor filtering & calibration notes

Motor control explanation

PID notes for upcoming multi-sensor hybrid version

Hardware list & wiring details

Demo video (Google Drive link)

⭐ Features

4WD smooth movement (speed ramping)

Ultrasonic obstacle detection

Servo-based left–right environmental scanning

Automatic turning decision (choose longest free path)

Reliable distance filtering (noise reduction)

Modular code (easy to upgrade)

Expandable to line-following + PID later

🔧 Hardware Components
Component	Qty
Arduino UNO	1
Motor Driver Shield (AFMotor)	1
TT Gear Motor	4
Wheels	4
Ultrasonic Sensor (HC-SR04)	1
Servo Motor (SG90/MG90S)	1
18650 Li-ion Battery	2
18650 Battery Holder	1
Acrylic Sheet / Robot Base	1
Jumper Wires	–
DC Switch	1
🧠 How It Works

Robot moves forward by default.

Ultrasonic sensor reads distance continuously.

If obstacle < 15 cm → robot stops.

Robot moves backward slightly.

Servo looks right → measures distance.

Servo looks left → measures distance.

Robot turns to the side with more free space.

Continues normal forward movement.

🛠 Wiring Connections
Ultrasonic Sensor (HC-SR04)

TRIG → A0

ECHO → A1

VCC → 5V

GND → GND

Servo Motor

Signal → D10

VCC → 5V

GND → Common GND

Motors (via AFMotor Shield)

Motor1 → M1

Motor2 → M2

Motor3 → M3

Motor4 → M4

Power Supply

2×18650 → Motor shield power input

Arduino powered via USB or Vin

Common ground is compulsory

🧩 Code Explanation (Short Summary)
🔍 readPing()

Takes multiple samples

Removes 0-cm noise

Returns reliable average distance

➡️ moveForward()

Smooth motor ramp-up

Prevents sudden battery load

Ensures stable movement

🔄 lookRight() & lookLeft()

Turns servo

Measures free space

Helps robot choose best turning direction

🧭 Main loop

Checks distance

Chooses safe path

Handles movement decisions

📜 License

This project is released under the MIT License.
