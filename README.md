# Ultrasonic-maze-solver
An autonomous robot that navigates a maze using ultrasonic sensors. By emitting sound waves and measuring the echo, it detects walls and obstacles. An onboard microcontroller processes this data, executing a wall-following algorithm to intelligently find the path from start to finish without collision.    Sources Video  Deep Research  Canvas  Image
Arduino Maze Solver Robot Controller 🤖🧭
This document outlines how to use this PCB as the main controller board for an autonomous, 2-wheel drive maze-solving robot. The board integrates a motor driver, power regulation, and headers for sensors, making it an ideal all-in-one solution for your project.

Note: You can ignore the CNC-specific labels on the silk screen (like GRBL, Spindle, X/Y/Z Limit). For this project, these pins will be used as general-purpose inputs for our maze-solving sensors.

## Key Features ✨
Microcontroller Core: A dedicated socket for an Arduino Nano, which will act as the robot's brain.

Integrated Motor Control: Features an onboard TB6612FNG dual motor driver, perfect for controlling two DC motors in a differential drive setup (left and right wheels).

Sensor Integration: Provides multiple headers (JP3, JP5, JP6) to easily connect sensors like ultrasonic (HC-SR04) or infrared (IR) proximity sensors to detect walls.

Onboard Power Regulation: Includes an L7805 voltage regulator that takes power from your battery and provides a stable 5V for the Arduino and sensors.

Compact Design: The board is small enough to fit on most common small robot chassis.

## Hardware & Connections 🔌
The following table explains how to connect your robot's components to the board.

Connector	Purpose	Connection Details
Central Header	Arduino Nano Socket	The brain of your robot. Flash your maze-solving code to the Arduino before mounting it.
JP1	Battery Input	Connect your main battery pack here (e.g., 7.4V LiPo or a 9V battery).
JP2 / JP4	Motor Outputs	Connect your Left Motor and Right Motor to these two headers.
JP5	Primary Sensor Bank	Ideal for connecting three sensors (e.g., Left, Front, and Right ultrasonic sensors). The X/Y/Z Limit pins can be used as the digital I/O pins for your sensors.
JP6	Auxiliary I/O	Can be used for additional sensors, start/stop buttons, or status LEDs.

Export to Sheets
## Setup & Usage Guide 🚀
Build the Chassis: Assemble your 2-wheel drive robot chassis with motors and a caster wheel.

Mount Hardware:

Secure the PCB to your chassis.

Mount your sensors (e.g., one facing forward, one left, and one right).

Wire Everything:

Connect the left and right motors to JP2 and JP4.

Connect your sensors to the I/O pins on JP5. Each sensor will need VCC (5V), GND, and signal pins connected to the Arduino I/O broken out on the headers.

Connect your battery pack to JP1.

Upload Code: Write or download a maze-solving algorithm for your Arduino Nano. A great starting point is the Wall Follower algorithm, where the robot uses its side sensor to always stay a fixed distance from one wall.

Run! Place the robot in a maze and power it on to watch it solve.
