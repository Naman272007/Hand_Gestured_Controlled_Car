# Gesture Controlled Robotic Car

An IoT-based wireless robotic car that translates human hand movements into real-time directional and speed commands using ESP32, MPU6050 and the ESP-NOW communication protocol.

## Overview

The project eliminates the need for conventional remote controllers by introducing an intuitive hand gesture control system. The MPU6050 detects hand tilt, while the transmitter ESP32 processes sensor readings and wirelessly communicates with the receiver ESP32 to control the robotic car.

## Key Features

- Wireless communication using ESP-NOW
- Real-time hand tilt detection
- Proportional speed control based on tilt angle
- Forward, backward, left and right movement
- Differential steering and on-the-spot rotation
- Automatic sensor calibration
- Noise filtering and gesture sensitivity adjustment
- Automatic failsafe on communication loss
- No internet or Wi-Fi router required

## Hardware Components

| Component | Quantity |
|---|---:|
| ESP32-WROOM-32 DevKit V1 | 2 |
| MPU6050 | 1 |
| L298N Motor Driver | 1 |
| DC Geared Motors | 4 |
| LM2596 Buck Converter | As required |
| Suitable Power Supplies | 2 |
| Robotic Car Chassis | 1 |
| Jumper Wires | As required |

## System Architecture

Hand Gesture → MPU6050 → Transmitter ESP32 → ESP-NOW → Receiver ESP32 → L298N → DC Motors

### Transmitter Pin Configuration

| ESP32 | MPU6050 |
|---|---|
| 3V3 | VCC |
| GND | GND |
| GPIO 21 | SDA |
| GPIO 22 | SCL |

### Receiver Pin Configuration

| ESP32 | L298N |
|---|---|
| GPIO 25 | ENA |
| GPIO 26 | IN1 |
| GPIO 27 | IN2 |
| GPIO 32 | IN3 |
| GPIO 33 | IN4 |
| GPIO 14 | ENB |
| GND | GND |

## Technologies Used

- Arduino C++
- ESP32
- ESP-NOW
- I²C Communication
- Pulse Width Modulation (PWM)
- Embedded Systems
- Mokxi Circuit Simulation
- Arduino IDE

## Getting Started

1. Install Arduino IDE and the ESP32 board package.
2. Assemble the transmitter and receiver circuits.
3. Upload the respective programs to both ESP32 boards.
4. Power the transmitter and calibrate the MPU6050.
5. Verify wireless communication through Serial Monitor.
6. Test the robotic car using hand gestures with the wheels raised initially.

## Safety Mechanisms

The transmitter uses a neutral-position check, acceleration validation and sensor error detection to reduce unintended movement. The receiver disables motor drive if no valid control packet is received for 300 milliseconds.

## Future Improvements

- Accelerometer and gyroscope sensor fusion
- Obstacle detection and avoidance
- Encrypted wireless communication
- Rechargeable wearable controller
- Autonomous navigation
- Mobile application integration

## Applications

- Human-machine interaction
- Wireless robotics
- Assistive technology
- Smart vehicle control
- Industrial automation research

## Project Status

Hardware prototype under development and testing.

---

Built with an interest in IoT, robotics and embedded systems.
