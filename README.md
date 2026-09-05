# KVMRT Power Electronics Conversion System Simulation

## Project Overview
This repository contains the MATLAB/Simulink simulation of the power conversion system for the Klang Valley Mass Rapid Transit (KVMRT) Kajang Line (Siemens Inspiro rolling stock). Developed as part of the EEB/EFB 3033 Power Electronics Engineering Design Project at Universiti Teknologi PETRONAS.

## System Architecture
The simulated system represents a complete multi-stage Rectifier-DC/DC Converter-Inverter layout:
*   **Stage 1: Rectifier (Wayside Substation)** - Converts 3-phase AC grid supply to a 750V DC third-rail supply.
*   **Stage 2: Auxiliary DC-DC Converter (Onboard)** - Steps down the 500-900V DC input to a stable 110V DC for onboard auxiliary loads (30 kW per car).
*   **Stage 3: Traction Inverter** - Converts 750V DC to 3-phase AC using SPWM for traction motors.
*   **Integration**: 4-car system representation (M-T-T-M) integrating all subsystems.

## Key Contribution: Auxiliary DC-DC Converter
Designed and implemented the onboard auxiliary power conversion subsystem:
*   **Topology**: Non-isolated synchronous buck converter.
*   **Specifications**: 500-900V DC input, 110V DC output, 30 kW rated power (120 kW total for 4 cars).
*   **Component Sizing**: Calculated and validated L = 0.4 mH, Cout = 1.5 mF, Cin = 2 mF at fs = 5 kHz.
*   **Control Strategy**: Engineered a discrete PI controller closed-loop system to replace open-loop fixed duty cycles, ensuring robust line and load regulation.
*   **Modularity**: Created a reusable Simscape Electrical subsystem duplicated across the 4-car network for accurate load representation.

## Repository Structure
*   `/Simulink_Models` - Contains the individual and integrated `.slx` simulation files.
*   `/Calculations` - Mathematical derivations for component sizing, duty cycles, and ripple analysis.
*   `/Docs_and_Results` - Final project report, exported waveform graphs, and Siemens Inspiro reference data.

## Team Members
*   **Idriss Rama Salim** - Auxiliary DC-DC Converter & System Integration
*   **Eunice Yeo Lok Qian** - AC-DC Rectifier
*   **Mohamad Ameer Harith Bin Amran** - DC-AC Inverter & SPWM Generator

## Tools Used
*   MATLAB / Simulink
*   Simscape Electrical
