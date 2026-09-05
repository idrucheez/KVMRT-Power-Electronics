markdown_content = """<div align="center">
  <h1>⚡ KVMRT Kajang Line: Train Power Electronics Simulation</h1>
  <p><strong>A full-system MATLAB/Simscape electrical simulation of a 750V DC rapid transit power architecture.</strong></p>
</div>

## 🚄 Project Overview
*   **System Modeled:** Klang Valley Mass Rapid Transit (KVMRT) Kajang Line (Siemens Inspiro).
*   **Academic Context:** EEB/EFB 3033 Power Electronics Engineering Design Project (Universiti Teknologi PETRONAS).
*   **Objective:** Simulate the complete energy conversion pipeline from grid AC to traction motor AC, including onboard auxiliary DC loads.

## 📐 System Architecture
*   **Stage 1: Wayside Rectifier** - Converts 3-phase grid AC (584V line-to-line) to a 750V DC third-rail supply using a 6-pulse diode configuration.
*   **Stage 2: Auxiliary DC-DC Converter** - Steps down 750V DC (variable 500-900V range) to a regulated 110V DC for train auxiliary systems.
*   **Stage 3: Traction Inverter** - Synthesizes 3-phase AC from the 750V DC bus using SPWM (Sinusoidal Pulse Width Modulation) for traction motors.
*   **Train Configuration:** 4-car modular layout (M-T-T-M) with distributed 30 kW auxiliary loads per car (120 kW total).

## 🎯 My Technical Contribution: Auxiliary DC-DC Converter
*   **Topology:** Non-isolated synchronous buck converter.
*   **Control Engineering:** Transitioned from open-loop to closed-loop discrete PI control for robust line and load regulation.
*   **Calculated Sizing:**
    *   Inductor (L): 0.4 mH
    *   Output Capacitor (Cout): 1.5 mF
    *   Input Capacitor (Cin): 2 mF
    *   Switching Frequency (fs): 5 kHz
*   **Integration:** Designed a reusable Simscape Electrical subsystem with measurement outputs (Vout, Iout, Duty Cycle, Pout), deployed across a 4-car network simulation.

## 📊 Key Results & Challenges Solved
*   **Regulated Output:** Achieved ~108-109V DC output at ~270A (29 kW per car) under variable third-rail conditions.
*   **Interface Resolution:** Successfully bridged mathematical Simulink signal logic (Rectifier) with Simscape Electrical physical conservation networks.
*   **Solver Optimization:** Resolved multiple Solver Configuration errors by isolating physical networks.

## 📂 Repository Structure
*   `📁 Simulink_Models/` - `.slx` files for isolated stages and the final integrated M-T-T-M system.
*   `📁 Calculations/` - Duty cycle, component sizing, and ripple mathematics.
*   `📁 Docs_and_Results/` - Project report, output waveforms (voltage, current, power), and Siemens Inspiro spec sheets.

## 👥 Engineering Team
*   **Idriss Rama Salim** - Auxiliary DC-DC Converter & Integration
*   **Eunice Yeo Lok Qian** - AC-DC Rectifier
*   **Mohamad Ameer Harith Bin Amran** - DC-AC Traction Inverter
"""

with open("README_V2.md", "w") as f:
    f.write(markdown_content)
    
print("Updated File generated successfully.")
