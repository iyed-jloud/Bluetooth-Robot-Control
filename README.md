# Bluetooth Controlled Mobile Robot

## Project Overview
This project involves the design and implementation of a **mobile robotic system** controlled remotely via Bluetooth. The core objective was to develop an embedded system capable of receiving wireless commands and translating them into physical motion using H-Bridge logic.

This project demonstrates my proficiency in **Embedded C++**, **Hardware-Software Integration**, and **UART Communication protocols**.

## Technical Stack
* **Language:** C++ (Embedded)
* **Microcontroller:** Arduino (Uno/Nano)
* **Communication:** Bluetooth Module (HC-05/HC-06) via UART
* **Actuators:** DC Gear Motors
* **Driver:** L298N Dual H-Bridge Motor Driver

## Hardware Architecture & Wiring
The system relies on a precise wiring schematic to ensure safe current flow between the logic level (Arduino) and the power level (Motors).

| Component | Pin Function | Arduino Pin | Description |
| :--- | :--- | :--- | :--- |
| **Bluetooth** | RX / TX | D3 / D2 | SoftwareSerial Communication |
| **Left Motor** | IN1 / IN2 | D5 / D6 | PWM/Direction Control |
| **Right Motor** | IN3 / IN4 | D9 / D10 | PWM/Direction Control |

## Firmware Logic (C++)
The firmware (`ROBOTOT.ino`) is optimized for real-time responsiveness. It utilizes a polling loop to listen for incoming data packets via the Bluetooth Serial interface.

### Communication Protocol
The robot executes commands based on single-byte characters received from the controller app:

| Command | Action | Logic Implementation |
| :--- | :--- | :--- |
| **'F'** | Forward | `IN1=H, IN2=L` | `IN3=H, IN4=L` |
| **'B'** | Backward | `IN1=L, IN2=H` | `IN3=L, IN4=H` |
| **'L'** | Turn Left | `IN1=L, IN2=H` | `IN3=H, IN4=L` (Differential Drive) |
| **'R'** | Turn Right | `IN1=H, IN2=L` | `IN3=L, IN4=H` (Differential Drive) |
| **'S'** | Stop | All Pins LOW |

## Key Learnings & Skills Demonstrated
1.  **Low-Level Programming:** Direct manipulation of Digital I/O pins to control hardware states.
2.  **Circuit Design:** Understanding voltage regulation and motor driver isolation.
3.  **Serial Communication:** Implementing `SoftwareSerial` to emulate UART ports on digital pins.
4.  **Modular Code Structure:** Creating dedicated functions (`avancer`, `reculer`) for clean and maintainable code.

---
*Project developed by IYED JLOUD.*
