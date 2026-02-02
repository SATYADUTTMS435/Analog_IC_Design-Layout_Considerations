#  Analog IC Design Workshop – Day 3  
## CTAT & PTAT Generation using Bandgap Reference (BGR)

This document describes the work completed on **Day 3** of the *Analog IC Design and Layout Considerations* workshop.  
The focus of this session was the design and understanding of **CTAT and PTAT voltage generation** using a **Bandgap Reference (BGR)** circuit implemented with **PNP transistors, resistors, and an operational amplifier**.

---
##  Objective

- To understand **CTAT** and **PTAT** characteristics
- To design a **Bandgap Reference circuit**
- To mathematically derive the **temperature-independent reference voltage**
- To analyze BGR operation at **27°C**

---

##  Temperature Dependence in BJTs

### CTAT Quantity – Base Emitter Voltage

The base–emitter voltage of a BJT is given by:

\[
V_{BE} = V_T \ln\left(\frac{I_C}{I_S}\right)
\]

As temperature increases:
- \( I_S \) increases exponentially
- \( V_{BE} \) decreases

\[
\Rightarrow V_{BE} \text{ is CTAT}
\]

---

### PTAT Quantity – Difference in Base Emitter Voltages

For two PNP transistors operating at different current densities:

\[
\Delta V_{BE} = V_{BE1} - V_{BE2}
\]

This simplifies to:

\[
\Delta V_{BE} = V_T \ln(n)
\]

Where:
- \( n \) = emitter area ratio or current density ratio
- \( V_T = \frac{kT}{q} \)

Since \( V_T \propto T \):

\[
\Rightarrow \Delta V_{BE} \text{ is PTAT}
\]

---

##  Bandgap Reference Circuit Operation

The BGR circuit consists of:
- Two PNP transistors operating at different emitter areas
- An operational amplifier enforcing equal node voltages
- Resistors used to scale PTAT and CTAT components
- A reference output voltage \( V_{REF} \)

The op-amp ensures accurate current and voltage matching across branches.

---

##  PTAT Current Generation

The PTAT voltage is converted into a current using a resistor:

\[
I_{PTAT} = \frac{\Delta V_{BE}}{R}
\]

Design condition:

\[
I_{PTAT} = \_\_\_\_\_ \,\mu A
\]

---

##  Reference Voltage Generation

The reference voltage is formed by summing a CTAT voltage and a scaled PTAT voltage:

\[
V_{REF} = c_1 V_{BE} + c_2 \Delta V_{BE}
\]

Where:
- \( c_1 \) and \( c_2 \) are constants defined by resistor ratios

---

##  Final Expression for VREF

Using resistor scaling, the reference voltage can be written as:

\[
V_{REF} = V_{BE2} + V_T \ln(n)\left(1 + \frac{R_2}{R_3}\right)
\]

---

##  Design Conditions (At 27°C)

\[
T = 27^\circ C
\]

\[
V_T = \_\_\_\_\_ \, V
\]

\[
n = \_\_\_\_\_
\]

\[
R_2 = \_\_\_\_\_ \, \Omega
\quad
R_3 = \_\_\_\_\_ \, \Omega
\]

\[
I = \_\_\_\_\_ \,\mu A
\]

---

##  Calculations

\[
\Delta V_{BE} = V_T \ln(n) = \_\_\_\_\_ \, V
\]

\[
V_{PTAT} = V_T \ln(n)\left(1 + \frac{R_2}{R_3}\right) = \_\_\_\_\_ \, V
\]

\[
V_{REF} = V_{BE2} + V_{PTAT} = \_\_\_\_\_ \, V
\]

---

##  Observations

- \( V_{BE} \) decreases with temperature (CTAT)
- \( \Delta V_{BE} \) increases linearly with temperature (PTAT)
- Proper scaling of CTAT and PTAT terms produces a nearly temperature-independent \( V_{REF} \)

---

##  Conclusion (Day 3)

- CTAT and PTAT voltages were successfully derived
- Bandgap Reference principle was verified mathematically
- Resistor scaling enables temperature compensation
- The BGR provides a stable reference for:
  - LDOs
  - Biasing circuits
  - Precision analog IC systems

---


