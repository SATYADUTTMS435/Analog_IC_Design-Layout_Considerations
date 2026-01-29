#  Analog IC Design Workshop – Day 1  
## Common Source (CS) Amplifier Biasing Techniques (Cadence Virtuoso)

This repository documents **Day 1** of the *Analog IC Design and Layout Considerations* workshop.  
The objective of Day 1 was to design, simulate, and compare a **Common Source (CS) amplifier** using different load and biasing techniques in **Cadence Virtuoso**.

---

##  Objective

- To understand the working of a **Common Source amplifier**
- To study the effect of different **biasing and load techniques**
- To analyze:
  - DC operating point
  - Small-signal gain
  - Output swing
  - Bias stability
- To identify suitable CS topologies for **Analog IC applications** such as **LDOs and Bandgap References**

---

## Circuits Implemented

1. CS Amplifier with **Resistor Load (RD)**
2. CS Amplifier with **PMOS Diode-Connected Load**
3. CS Amplifier with **PMOS Biased (Active Load)**

---

##  CS Amplifier with Resistor Load (RD)

###  Circuit Description
- NMOS configured in common source mode
- Drain connected to a resistor **RD**
- Source connected to ground
- Gate driven by input signal

###  Theory
- Drain current depends on **VGS** and **RD**
- Small signal gain: Av = -gm * Rd
  
- Output swing is limited due to voltage drop across **RD**

###  Design Parameters
| Parameter | Value |
|--------|------|
| VDD | 1V |
| RD | Sweep(Best 5K) |
| NMOS W/L | 120nm/45nm |
| NMOS Bias Voltage | 0.6V |
| Input Amplitude | 50mV |
| Input Frequency | 1kHz |

###  Observations (From Simulation)
- DC Operating Point (Vout): **To be added**
- Drain Current (ID): **To be added**
- Small Signal Gain (Av): **3.25V**
- Output Swing: **520mV  to  840mV**

###  Inference
- Bias point is sensitive to resistor value and process variations
- Limited gain and output swing
- Not preferred for modern IC design

### All the related pictures are present under the folder Day_1/CS_with_Rd

---

##  CS Amplifier with PMOS Diode-Connected Load

###  Circuit Description
- RD replaced with **PMOS diode-connected load**
- PMOS gate and drain shorted
- Provides self-biasing

###  Theory
- PMOS acts as a non-linear resistive load
- Small signal gain: Av = -gmn / gmp

- Improved bias stability compared to RD load

###  Design Parameters
| Parameter | Value |
|--------|------|
| VDD | 1V |
| PMOS W/L | 925nm/45nm |
| NMOS W/L | 120nm/45nm |
| NMOS Bias Voltage | 600mV |
| Input Amplitude | 50mV |
| Input Frequency | 1kHz |

###  Observations (From Simulation)
- DC Operating Point (Vout): **403mV**
- Drain Current (ID): **2.323uA**
- Small Signal Gain (Av): **0.65V**
- Output Swing: **470mV to 530mV**

###  Inference
- Better bias stability than resistor load
- Moderate gain
- Used in simple current mirrors and bias circuits

### All the related pictures are present under the folder Day_1/CS_with_Diode_Connected_PMOS

---

##  CS Amplifier with PMOS Biased Load (Active Load)

###  Circuit Description
- PMOS biased using a fixed gate voltage
- PMOS behaves as a current source
- High output resistance at drain

###  Theory
- Small signal gain: Av = -gm * (ron || rop)

 
- Provides **highest gain** among all three configurations

###  Design Parameters
| Parameter | Value |
|--------|------|
| VDD | 1V |
| PMOS Bias Voltage | 400mV |
| PMOS W/L | 1um/45nm |
| NMOS W/L | 120nm/45nm |
| NMOS Bias Voltage | 600mV |
| Input Amplitude | 25mV |
| Input Frequency | 1kHz |

###  Observations (From Simulation)
- DC Operating Point (Vout): **To be added**
- Drain Current (ID): **To be added**
- Small Signal Gain (Av): **0.4V**
- Output Swing: **964mV to 984mV**

###  Inference
- High gain and wide output swing
- Excellent bias stability
- Preferred topology for **LDOs, Op-Amps, and BGRs**

### All the related pictures are present under the folder Day_1/CS_with_Active_Load_PMOS

---

##  Comparison Table

| Parameter | RD Load | PMOS Diode Load | PMOS Biased Load |
|--------|--------|----------------|----------------|
| Gain | 3.25V | 0.65 | To be added |
| Bias Stability | Low | Medium | High |
| Power Efficiency | Low | Medium | High |
| IC Suitability | No | Partial | Yes |

---

##  Conclusion (Day 1)

- CS amplifier with RD load is useful for basic understanding
- Diode-connected PMOS provides better biasing and IC compatibility
- PMOS biased CS amplifier is the most suitable for **analog IC design**
- This topology forms the basis for **LDO and Bandgap Reference circuits**

---






  
