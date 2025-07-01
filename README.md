# ⚙️ Automated Clutch Transmission System

[![MATLAB](https://img.shields.io/badge/MATLAB-R2022a-blue)](https://mathworks.com)
[![Simulink](https://img.shields.io/badge/Simulink-R2022a-green)](https://mathworks.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)


---

## 🚗 Project Overview
Manually shifting the clutch in stop‑and‑go traffic can cause knee strain and discomfort. This project **converts a standard manual-transmission car into a semi‑automatic** by mechanically linking the accelerator and clutch pedals through an electromechanical actuator and rack‑and‑pinion, all without altering factory drivetrain components.

---

## 🖼️ Pictures

<p align="center">
  <img src="https://github.com/user-attachments/assets/64fa0360-8cff-4b63-8c70-0447e37fcc4e" width="550" alt="CAD in Car Interior"/>
  <img src="https://github.com/user-attachments/assets/d8ea27f3-7bec-4211-b535-3c2e887659a4" width="415" alt="Simulink Model"/>
  <img src="https://github.com/user-attachments/assets/f8e2fc7f-46d4-470f-a959-d39a4cbbf3dc" width="500" alt="3D Driving Scene"/>
  <img src="https://github.com/user-attachments/assets/bb29c444-457f-49a0-99e2-29fa2dd4b686" width="370" alt="3D Driving Scene"/>
</p>

![Simulation](https://github.com/user-attachments/assets/cdefdd9b-f45f-4b5a-82bb-668d12114c27)

---



## 🎯 Objectives
1. **Clutch–Accelerator Interlock**  
   Automate clutch engagement/disengagement based on accelerator position.  
2. **Non‑invasive Installation**  
   No modification to engine, gearbox, or factory wiring.  
3. **Maintain Ergonomics & Safety**  
   Preserve OEM pedal travel, seating position, and insurance compliance.  
4. **Cost‑Effective & Compact**  
   Use off‑the‑shelf linear actuator and minimal frame for under‑$200 BOM.

---

## 🚀 Key Features
- **12 V DC Electromechanical Linear Actuator** (LD3 series)  
- **Rack & Pinion + Potentiometer** feedback loop  
- **SolidWorks‑designed frame** mounts under driver seat  
- **MATLAB/Simulink + Simscape** transfer‑function modeling  
- **SimMechanics + 3D Scene** for full‑vehicle virtual demo  

---

## 🛠️ What We Did 

### 1. Concept & Measurement  
- Chose Hyundai i20 (2019 MT) as reference.  
- Measured pedal travel (15 cm) and mounting clearances.  
- Mapped required clutch force (~80 N) from lever geometry and driver feedback.

### 2. Theoretical Modeling  
- **DC Motor → Linear Actuator** transfer function derived via Kirchhoff’s laws and Lagrange mechanics.  
- **Rack & Pinion** gear ratios computed to map accelerator rotation to actuator stroke.  
- Combined electromechanical and mechanical equations to form overall system transfer function.

### 3. CAD & Structural Design  
- Designed a stainless‑steel frame clampable to under‑seat rails—no drilling.  
- Modeled rack, pinion, and actuator mounts in SolidWorks.  
- Ran static stress analysis under 500 N loads; max von Mises stress ≪ yield.

### 4. Simulation  
- **Simulink Subsystem**: Modeled 12 V DC supply, DPDT switch, motor+gear train, leadscrew, sensor feedback.  
- **SimMechanics Model**: Imported STEP parts, defined joints (revolute for pedals, prismatic for piston), set material properties.  
- **3D Driving Scene**: Linked pedal motion to virtual vehicle on road network, generating real‑time turn and throttle behavior.

### 5. Results  
- **Actuator velocity**: 45 mm/s (matches LD3 spec)  
- **Stroke**: 170 mm total (15 cm clutch travel)  
- **Force**: 80 N at clutch pedal  
- **Smooth virtual demo** showing gear‑down on cornering via pedal actuation.

---

> For full details, see the [project report](./report/Automated_Clutch_Transmission_System.pdf).  
> To run the Simulink model, open `/code/simulink/automatic_clutch.slx` in MATLAB R2020a or later.  
