# tia-portal-tank-project
# Industrial Tank Automation System

## Overview

This project is an industrial automation system developed in Siemens TIA Portal using Structured Control Language (SCL) and WinCC HMI.

The system simulates an automated tank process with modular PLC architecture, including control logic, recipe management, and process simulation.

The system architecture is described in detail in the plc-architecture section

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
 <p align="center">
  <img src="screenshots/st_filling_processing.png" width="400"/>
  <img src="screenshots/st_draining_fault.png" width="400"/>
</p>


### FB_TankSimulation
Simulates the physical process:
- Tank level dynamics
- Sensor behavior
- Fault simulation (stuck actuator, sensor failure)

<p align="center">
  <img src="screenshots/tank_sim1.png" width="400"/>
  <img src="screenshots/tank_sim2.png" width="350"/>
</p>

### FB_Supervision
- Recipe Loading

<p align="center">
  <img src="screenshots/fb_supervision.png" width="400"/>
  <img src="screenshots/db_recipes.png" width="400"/>
</p>

## HMI Interface

The HMI is divided into two main screens:

- PROCESS OVERVIEW: real-time process visualization



 <p align="center">
  <img src="screenshots/overview.png" width="480"/>
  <img src="screenshots/st_processing.png" width="480"/>
</p>


- CONTROL PANEL: operator commands (start/stop, mode selection, recipe selection)



<p align="center">
  <img src="screenshots/cmd_panel.png" width="480"/>
  <img src="screenshots/cmd_automode.png" width="480"/>
</p>

ALARMS / FAULTS 



<p align="center">
  <img src="screenshots/fault_fb_lost.png" width="480"/>
  <img src="screenshots/fault_tm_pump.png" width="480"/>
</p>
---

## Technologies

- Siemens TIA Portal
- WinCC
- SCL (Structured Control Language)
- PLC State Machine Design
