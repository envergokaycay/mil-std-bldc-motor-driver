# MIL-STD-461G Compliant BLDC Motor Driver

![Project Status](https://img.shields.io/badge/Status-Work_in_Progress-orange)
![Hardware](https://img.shields.io/badge/Hardware-Altium_Designer-blue)

## Project Overview
This repository contains the hardware design for a high-reliability, **28V 3-phase Brushless DC (BLDC)** motor controller. The project is specifically engineered for defense and aerospace applications, focusing on **MIL-STD-461G** EMI/EMC compliance and robust power management.

## Key Technical Specifications
* **Power Stage**: 3-Phase Inverter topology designed for a 28V nominal bus (18V-32V operating range).
* **Control Architecture**: Implementation of Field Oriented Control (FOC) utilizing Space Vector PWM (SVPWM).
* **Communication**: On-board isolated **CAN** bus and **RS422** differential encoder receiver.

## Core Component Breakdown
| Function | Component | Description |
| :--- | :--- | :--- |
| **Main MCU** | STM32G474 | Cortex-M4 with CORDIC math accelerator for optimized FOC. |
| **Gate Driver** | DRV8353 | 3-phase smart gate driver with integrated protection features. |
| **Current Sense** | INA240 | In-line phase current sensing amplifiers (x3) with PWM rejection. |
| **Power Rails** | LM5005 & TPS54302 | Step-down converters for internal 12V and 3.3V power rails. |

## Schematic Previews
*The hardware design is modularized into four main functional blocks as shown below.*

### 1. Power Protection
![Power Protection](images/power_protection.png)
*Featuring **Ideal Diode** for reverse polarity protection, **TVS diodes** for transient suppression, and a **Pi-type EMI filter** designed to meet MIL-STD-461G standards.*

### 2. Power Stage
![Power Stage](images/power_stage.png)
*High-efficiency **3-phase inverter** stage with low-RDS(on) MOSFETs and optimized trace routing for high current paths.*

### 3. Power Distribution
![Power Distribution](images/power_distribution.png)
*Staged buck conversion utilizing **LM5005** (28V to 12V) and **TPS54302** (12V to 3.3V) for stable internal power delivery.*

### 4. MCU & Control
![MCU Control](images/mcu_control.png)
*STM32G474 controller core with isolated **CAN** and **RS422** interfaces, and precise analog feedback paths for current sensing.*

## 🚀 Development Roadmap
- [x] **System Architecture & Component Selection**
- [x] **Modular Schematic Design** (Protection, Stage, Distribution, Control)
- [ ] **PCB Layout** (Active Phase - Focusing on EMI and Thermal management)
- [ ] **Hardware Manufacturing & Bring-up**
- [ ] **Firmware Development (FOC Algorithm Implementation)**

## Author
**Enver Gökay ÇAY**
Electrical and Electronics Engineer | Karadeniz Technical University
