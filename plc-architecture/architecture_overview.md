# PLC System Architecture Overview

## 1. High-Level Architecture

The system is structured into four main layers:

### 1.1 HMI Layer
- WinCC interface
- Provides operator control and process visualization
- Sends commands and recipe selection to PLC via DB_HMI

### 1.2 Supervision Layer
- FB_Supervision
- Manages recipe loading and activation
- Handles interaction between HMI and control logic

### 1.3 Control Layer 
- FB_Tank
- Implements the main state machine:
  - IDLE
  - MANUAL
  - FILLING
  - PROCESSING
  - DRAINING
  - FAULT
- Manages:
  - timing constraints
  - safety conditions
  - actuator commands

### 1.4 Process Simulation Layer
- FB_TankSimulation
- Simulates physical behavior of the system:
  - tank level dynamics
  - actuator delays 
  - sensor feedback
  - fault injection (stuck valve, frozen sensor, leaks)

---

## 2. Data Separation

The system uses dedicated data blocks:

- DB_HMI:
  - operator commands
  - status visualization
  - alarm handling

- DB_Recipes:
  - process parameters
  - active recipe selection

- DB_Simulation:
  - simulated sensor values
  - actuator state feedback

---

## 3. Control Logic

The control logic is based on a deterministic state machine approach.

Key principles:

- Each state has a defined entry and exit condition
- Transitions are event-driven (start, stop, faults, completion)
- Safety conditions (STOP / E-STOP) 
- Manual mode bypasses sequence logic but preserves safety constraints

---

## 4. Process & Control Flow Overview

The system is event-driven and allows continuous operator interaction.

### Operator actions (HMI)
- Recipe selection
- START / STOP commands
- AUTO / MANUAL mode selection

### Execution conditions (AUTO mode)
The automatic cycle starts only if:
- AUTO mode is active
- START is triggered
- A valid recipe is loaded
- No FAULT is present

### Control behavior
- FB_Supervision handles recipe loading into DB_Recipes
- FB_Tank executes the state machine sequence:
  IDLE → FILLING → PROCESSING → DRAINING → IDLE
- FB_TankSimulation provides real-time feedback signals

### Interrupt logic
- STOP → safe return to IDLE
- FAULT → transition to FAULT state
- Manual mode overrides automatic sequence

---

## 5. Fault Handling Strategy

Fault management is integrated into the control layer:

- Timeout monitoring for actuators
- Sensor validation (range and plausibility checks)
- Simulation of realistic failures:
  - stuck pump/valve
  - frozen level sensor
  - leakage conditions

When a fault is detected:
- system transitions to FAULT state
- outputs are safely disabled
- manual reset is required for recovery




