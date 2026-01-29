#  Analog IC Design Workshop – Day 1  
## Common Source (CS) Amplifier Biasing Techniques (Cadence Virtuoso)

This repository documents **Day 1** of the *Analog IC Design and Layout Considerations* workshop.  
The objective of Day 1 was to design, simulate, and compare a **Common Source (CS) amplifier** using different load and biasing techniques in **Cadence Virtuoso**.

---

## 🎯 Objective

- To understand the working of a **Common Source amplifier**
- To study the effect of different **biasing and load techniques**
- To analyze:
  - DC operating point
  - Small-signal gain
  - Output swing
  - Bias stability
- To identify suitable CS topologies for **Analog IC applications** such as **LDOs and Bandgap References**

---

## 🧱 Circuits Implemented

1. CS Amplifier with **Resistor Load (RD)**
2. CS Amplifier with **PMOS Diode-Connected Load**
3. CS Amplifier with **PMOS Biased (Active Load)**

---

## 1️⃣ CS Amplifier with Resistor Load (RD)

### 🔹 Circuit Description
- NMOS configured in common source mode
- Drain connected to a resistor **RD**
- Source connected to ground
- Gate driven by input signal

### 🔹 Theory
- Drain current depends on **VGS** and **RD**
- Small signal gain: Av = -gm * Rd
- 
  
