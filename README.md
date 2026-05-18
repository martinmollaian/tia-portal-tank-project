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

### [FB_Tank](function_blocks/fb_tank)
Core control logic of the system:
- State machine implementation
- Mode management (AUTO / MANUAL)
- Actuator control (pump, valve)
- Timeout and fault detection
 


### [FB_Tank_Simulation](function_blocks/fb_tank_simulation)
Simulates the physical process:
- Tank level dynamics
- Sensor behavior
- Fault simulation (stuck actuator, sensor failure)


### [FB_Supervision](fb_supervision)
- Recipe Loading


## HMI Interface

The HMI is divided into three screens:

- PROCESS OVERVIEW: real-time process visualization



 <p align="center">
  <img src="screenshots/hmi/overview_panel_idle.png" width="480"/>
  <img src="screenshots/hmi/overview_panel_processing.png" width="480"/>
</p>

ALARMS / FAULTS 



<p align="center">
  <img src="screenshots/hmi/ov_panel_fault_fb_lost.png" width="480"/>
  <img src="screenshots/hmi/ov_panel_fault_tm_pump.png" width="480"/>
</p>
- CONTROL PANEL: operator commands (start/stop, mode selection, recipe selection)



<p align="center">
  <img src="screenshots/hmi/command_panel_start.png" width="480"/>
  <img src="screenshots/hmi/command_panel_automode.png" width="480"/>
</p>

- RECIPE SELECTION POPUP (FROM CONTROL PANEL)
  <p align="center">
  <img src="screenshots/hmi/popup_panel_recipe_selection.png" width="400"/>
  <img src="screenshots/hmi/popup_panel_recipe_selected.png" width="400"/>
</p>


---

## Technologies

- Siemens TIA Portal
- WinCC
- SCL (Structured Control Language)
- PLC State Machine Design
