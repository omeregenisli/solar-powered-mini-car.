# ☀️ Mini Solar-Powered Electric Car Prototype

A small-scale vehicle powered entirely by solar energy — integrating a 6V photovoltaic panel, a TP4056 charge management module, and an internal rechargeable buffer battery pack to supply instantaneous motor inrush current.

Final project for **EED1014 – Engineering Design**, Dokuz Eylül University, Department of Electrical & Electronics Engineering.

---

### 🎥 Video Demonstration
▶️ **[Click Here to Watch the Test Drive & Drift Demo on YouTube (0:12)](https://www.youtube.com/watch?v=L9RL3uXSAv0)**

---

<p align="center">
  <img src="circuit-closeup.jpg" width="85%" alt="TP4056 Charging Module and Circuitry" />
  <br>
  <em>Figure 1: Custom wiring hub featuring the TP4056 charging module with active power regulation (blue LED illuminated) mounted at the rear.</em>
</p>

---

## 📌 Project Overview

The primary objective was to engineer an autonomous remote-controlled car chassis running **solely on solar energy**, eliminating all reliance on disposable batteries or direct grid charging.

### Core Engineering Challenges & Solutions:
- **Low Solar Current vs. High Inrush Demand:** A compact 6V 100mA panel produces only ~0.6W. When DC motors start or turn, current demand surges to 500mA–1A. Connecting the panel directly would cause the supply voltage to collapse to 0V.
- **The Buffer Solution:** The solar panel trickles charge into a 4× 1.2V (4.8V) rechargeable NiMH battery pack via a TP4056 controller. The pack acts as an energy buffer, absorbing fluctuating solar output and delivering instantaneous torque.
- **Safety Regulation:** Built-in safeguards prevent over-discharge, overcharging, and short-circuits during dynamic operation.

---

## 📸 Prototype & Energy Storage Subsystem

<table>
  <tr>
    <td width="50%" align="center">
      <img src="hero.jpg" alt="Solar Car Profile View" width="100%" />
      <br>
      <strong>Vehicle Profile</strong><br>
      <sub>Streamlined RC chassis with roof-mounted 6V photovoltaic cell</sub>
    </td>
    <td width="50%" align="center">
      <img src="battery-compartment.jpg" alt="Battery Buffer Pack" width="100%" />
      <br>
      <strong>Energy Storage Buffer</strong><br>
      <sub>4× 1.2V 2100mAh Philips Rechargeable NiMH cells in series (4.8V pack)</sub>
    </td>
  </tr>
</table>

<p align="center">
  <img src="top-view.jpg" width="55%" alt="Top view showing solar panel placement" />
  <br>
  <em>Top-down view: 6V 100mA polycrystalline panel optimized for direct sunlight exposure.</em>
</p>

---

## ⚡ Technical Specifications & Calculations

- **Solar Collector:** 6 V, 100 mA DC Polycrystalline ($P_{max} = 0.6\text{ W}$)
- **Battery Storage Pack:** 4× 1.2 V, 2100 mAh NiMH in series $\rightarrow$ 4.8 V nominal, 10.08 Wh capacity
- **Motor Speed & Linear Velocity:**
  $$\text{Motor Speed } (N) \approx 240\text{ rpm at } 4.8\text{ V}, \quad \text{Wheel Radius } (R) = 0.03\text{ m}$$
  $$V = \left(\frac{N}{60}\right) \times (\pi \times 2R) \approx 0.38\text{ m/s}$$
- **Charging Time (Experimental):**
  - **Direct Sunlight:** ~3 hours for full cycle
  - **Partially Overcast:** ~6 hours
- **Range per Full Charge:** ~10 meters continuous run under dynamic load

---

## 🛒 Bill of Materials (BOM)

| # | Component | Qty | Unit Price (₺) | Total Cost (₺) |
|---|---|:---:|:---:|:---:|
| 1 | Toy Car Base (with dual DC motors) | 1 | 300 | 300 |
| 2 | 6V 100mA Polycrystalline Solar Panel | 1 | 100 | 100 |
| 3 | TP4056 Power Management / Charging Module | 1 | 50 | 50 |
| 4 | Philips 1.2V 2100mAh Rechargeable NiMH Batteries | 4 | 150 | 600 |
| 5 | Miscellaneous (wiring, hardware switch, adhesives) | 1 | 50 | 50 |
| | **Total Project Budget** | | | **₺1100** |

---

## 🔌 System Architecture & Circuit Design

The power flow transitions from the solar panel through the protection module into the storage buffer, and finally to the DC motors via a manual control switch:
