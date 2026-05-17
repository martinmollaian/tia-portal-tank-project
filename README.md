# tia-portal-tank-project
# Industrial Tank Automation System

## Overview

This project is an industrial automation system developed in Siemens TIA Portal using Structured Control Language (SCL) and WinCC HMI.

The system simulates an automated tank process with modular PLC architecture, including control logic, recipe management, and process simulation.

---

## System Features

- State machine-based 
- AUTO / MANUAL operating modes
- Recipe management system
- Pump and valve supervision with feedback monitoring
- Alarm and fault handling system
- Tank level simulation
- HMI integration (WinCC)
- Separation between control logic and process simulation

---

## Main Components

### FB_Tank
Core control logic of the system:
- State machine implementation
- Mode management (AUTO / MANUAL)
- Actuator control (pump, valve)
- Timeout and fault detection

### FB_TankSimulation
Simulates the physical process:
- Tank level dynamics
- Sensor behavior
- Fault simulation (stuck actuator, sensor failure)

### FB_Supervision
- Recipe Loading

## HMI Interface

The HMI is divided into two main screens:

- PROCESS OVERVIEW: real-time process visualization
- ![Process Overview](screenshots/st_processing.png)
- CONTROL PANEL: operator commands (start/stop, mode selection, recipe selection)
- 

---

## Technologies

- Siemens TIA Portal
- WinCC
- SCL (Structured Control Language)
- PLC State Machine Design
