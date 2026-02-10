# ASMC: Autonomous System Main Controller

## Project Overview
The **ASMC (Autonomous System Main Controller)** is a central electronic control unit designed for a Formula Student racing vehicle. Its primary objective is to integrate the critical subsystems required for autonomous operation in compliance with the **Formula Student Rules 2026**. 

This board serves as a robust interface between the high-level autonomous compute unit and the vehicle's hardware, ensuring safety, reliable power distribution, and real-time status signaling.

## Key Functionalities

### 1. Power Management & Distribution
* **Peripheral Supply**: Provides regulated and protected power to sensors, actuators, and processing units necessary for the Autonomous System (AS).
* **LVS Compliance**: Operates within the Low Voltage System (LVS) limits (max 60V DC) and ensures proper grounding to the chassis.
* **Overcurrent Protection**: Integrated protection for all connected devices to prevent hardware failure during dynamic disciplines.

### 2. Autonomous System Signaling (ASSI & AMI)
* **ASSI Control**: Drives three Autonomous System Status Indicators (ASSI) positioned on the sides and rear of the vehicle.
* **Visual Logic**: Implements mandatory lighting patterns (e.g., 2–5 Hz flashing for "Driving" and "Emergency" states).
* **Acoustic Warning**: Manages the intermittent sound signal (80–90 dBA) required during the "AS Emergency" state.
* **Mission Selection**: Interfaces with the Autonomous Mission Indicator (AMI) to allow manual mission selection and status feedback without external tools.

### 3. Safety & Braking Interface (ASB/EBS)
* **EBS Data Processing**: Receives and processes critical data from the Emergency Brake System (EBS).
* **SCS Monitoring**: Continuously monitors System Critical Signals (SCS). Any failure (e.g., open circuit or data corruption) triggers a safe state transition within <500ms.
* **SDC & RES Integration**: Interfaces with the Shutdown Circuit (SDC) and the Remote Emergency System (RES) to allow for immediate vehicle shutdown.

## Technical Compliance
Designed according to the **T14 (Autonomous System)** and **T15 (Autonomous System Brake)** sections of the FS 2026 rulebook.

* **AS Status Flowchart**: The board logic follows the mandatory state machine (Off, Ready, Driving, Emergency, Finished).
* **Failsafe Design**: Ensures that loss of power or signal defaults the vehicle to an "AS Emergency" state, engaging the mechanical brakes.
* **Data Logging**: Provides necessary signal outputs to the official Formula Student Data Logger for competition transparency.
