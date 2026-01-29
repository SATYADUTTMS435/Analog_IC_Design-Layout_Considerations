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
| VDD | ______ |
| RD | ______ |
| NMOS W/L | ______ |
| NMOS Bias Voltage | ______ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **______ V**
- Drain Current (ID): **______ A**
- Small Signal Gain (Av): **______**
- Output Swing: **______ V to ______ V**

###  Inference
- Bias point is sensitive to resistor value and process variations
- Limited gain and output swing
- Not preferred for modern IC design

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
| VDD | ______ |
| PMOS W/L | ______ |
| NMOS W/L | ______ |
| NMOS Bias Voltage | ______ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **______ V**
- Drain Current (ID): **______ A**
- Small Signal Gain (Av): **______**
- Output Swing: **______ V to ______ V**

###  Inference
- Better bias stability than resistor load
- Moderate gain
- Used in simple current mirrors and bias circuits

---

##  CS Amplifier with PMOS Biased Load (Active Load)

###  Circuit Description
- PMOS biased using a fixed gate voltage
- PMOS behaves as a current source
- High output resistance at drain

###  Theory
- Small signal gain: Av = -gm * (ron || rop)

 
- Provides highest gain among all three configurations

###  Design Parameters
| Parameter | Value |
|--------|------|
| VDD | ______ |
| PMOS Bias Voltage | ______ |
| PMOS W/L | ______ |
| NMOS W/L | ______ |
| NMOS Bias Voltage | ______ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **______ V**
- Drain Current (ID): **______ A**
- Small Signal Gain (Av): **______**
- Output Swing: **______ V to ______ V**

###  Inference
- High gain and wide output swing
- Excellent bias stability
- Preferred topology for **LDOs, Op-Amps, and BGRs**

---

##  Comparison Table

| Parameter | RD Load | PMOS Diode Load | PMOS Biased Load |
|--------|--------|----------------|----------------|
| Gain | ______ | ______ | ______ |
| Output Swing | ______ | ______ | ______ |
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






  
