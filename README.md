# NPE-PSQ 2D Simulator

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Status](https://img.shields.io/badge/status-stable-green.svg)

**Open-source 2D plasma simulator oriented to control, safety, and real-time applications.**

---

## 🎯 Purpose

NPE-PSQ is **not** a full MHD or physics-accurate tokamak simulator.
Its goal is to provide a **control-oriented, lightweight, and realistic-enough** environment for:

- **Model Predictive Control (MPC)**
- **Robust and adaptive control**
- **Fault detection and mitigation**
- **Safety systems (SCRAM, interlocks)**
- **Education and benchmarking**

Designed to be accessible to:
- Students
- Small universities
- Research groups without access to large simulators (DINA, CORSICA)

---

## 🧠 Core Philosophy

> *“Correct dynamics for control are more important than perfect physics.”*

The simulator focuses on:
- Correct vertical instability behavior ($Z$ dynamics)
- Actuator limitations (saturation, slew-rate)
- Delays and disturbances
- Failure scenarios
- Real-time execution constraints

---

## 📊 Technical Specs

### State Vector (Reduced-Order)
`x = [Ip, β, li, Z]`
- **Ip**: Plasma current
- **β**: Normalized pressure
- **li**: Internal inductance
- **Z**: Vertical position (unstable mode)

### Actuators
`u = [PF_radial, PF_vertical, Heating]`
Includes saturation, delay, and optional fault injection.

### Disturbances & Faults
- ELM-like impulses
- Parameter Drift
- Actuator failure (short/open)
- Vertical displacement events (VDE)

---

## 🎚️ Fidelity Levels

| Level | Description | Use Case |
| :--- | :--- | :--- |
| **🟢 Level 1** | Linear/LPV dynamics, basic disturbances. | Undergraduate teaching, fast prototyping. |
| **🟡 Level 2** | Non-linear terms, delays, slew-rate, structured noise. | **Standard Research**, controller benchmarking. |
| **🔴 Level 3** | Data-calibrated, thermal effects, extended safety. | Advanced research (Reduced-order). |

---

## 🧪 Official Benchmarks

1.  **Vertical Stabilization:** Zero-disturbance settling time test.
2.  **ELM Rejection:** Impulse recovery at $t=20ms$.
3.  **Actuator Failure:** Time-to-SCRAM measurement under coil short.
4.  **Adaptive Control:** Performance under parameter drift.

---

## 📦 Installation

```bash
git clone [https://github.com/YourUsername/NPE-PSQ-2D.git](https://github.com/YourUsername/NPE-PSQ-2D.git)
cd NPE-PSQ-2D
pip install -r requirements.txt
