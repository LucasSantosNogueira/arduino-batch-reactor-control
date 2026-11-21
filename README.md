# Arduino-Based Batch Reactor Simulator (ISA-88)

An Arduino-based dynamic simulator of a **Batch Chemical Reactor**, designed around the concepts of recipe management and sequential process control defined by the international **ISA-88 standard**.

The project implements a Finite State Machine (FSM) to manage the reactor's operational sequence, including material loading, thermal reaction control, product discharge, and emergency shutdown.

## ⚙️ Operational Features

The system manages the reactor through a **Finite State Machine (FSM)** consisting of five operational states, displayed through a 7-segment display and an RGB signal tower.

### 1. Standby (State 0)
- Display indicates `0`.
- System is initialized and waiting for an operator command.
- Green LED indicates Automatic Mode; Blue LED indicates Manual Mode.

### 2. Loading (State 1)
- Display indicates `1`.
- Simulates the volumetric filling of reactants from 0% to 100%.
- Loading progress is monitored through the Serial Monitor.

### 3. Reaction (State 2)
- Display indicates `2`.
- Main thermal control stage.
- The operator must adjust a potentiometer to maintain the simulated reactor temperature within the optimal range of **70°C to 90°C for 5 seconds**.

### 4. Discharging (State 3)
- Display indicates `3`.
- Simulates the opening of the discharge valve to release the final product.
- RGB LED pulses to indicate the discharge operation.

### 5. Emergency Alarm (State 9)
- Display indicates `9`.
- Red LED remains continuously illuminated.
- An interlock mechanism is triggered if the temperature exceeds **92°C**.
- The system remains locked until the reactor cools below **60°C** and the operator presses the START button to reset the system.

## 🛠️ Hardware Components

| Component | Specification | Quantity |
|---|---|---:|
| Microcontroller | Arduino Uno R3 | 1 |
| 7-Segment Display | 5161AS (Common Cathode) | 1 |
| RGB LED | Common Cathode | 1 |
| Potentiometer | 10 kΩ Linear | 1 |
| Push Buttons | START and Mode Selection | 2 |
| Resistors | 220 Ω | 5 |

## 🧠 Engineering Concepts

This project explores practical applications of industrial automation and process engineering:

- **ISA-88:** Batch process management and sequential operation.
- **Finite State Machine (FSM):** Structured control logic and state transitions.
- **Thermal Process Control:** Temperature monitoring and operating range enforcement.
- **Interlocks and Safety Logic:** Emergency shutdown and reset conditions.
- **Human-Machine Interface (HMI):** Operator feedback through visual indicators and displays.

## 🎯 Project Objective

To develop a low-cost educational prototype that demonstrates how industrial batch reactor operations can be represented through sequential control logic, operator interfaces, and basic safety interlocks using an Arduino microcontroller.
