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
| VDD | ___1V___ |
| RD | ___Sweep(Best 5K)___ |
| NMOS W/L | ___120nm/45nm___ |
| NMOS Bias Voltage | ___0.6V____ |
| Input Amplitude | ___50mV____ |
| Input Frequency | ___1kHz____ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **______**
- Drain Current (ID): **______**
- Small Signal Gain (Av): **___3.25V____**
- Output Swing: **__520mV___  to __840mV___**

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
| VDD | __1V____ |
| PMOS W/L | __925nm/45nm____ |
| NMOS W/L | ___120nm/45nm____ |
| NMOS Bias Voltage | ___600mV____ |
| Input Amplitude | ___50mV____ |
| Input Frequency | ___1kHz____ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **___403mV___**
- Drain Current (ID): **___2.323uA___**
- Small Signal Gain (Av): **___0.65V____**
- Output Swing: **___470mV___ to ___530mV___**

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

 
- Provides highest gain among all three configurations

###  Design Parameters
| Parameter | Value |
|--------|------|
| VDD | ___1V___ |
| PMOS Bias Voltage | ___400mV___ |
| PMOS W/L | ___1um/45nm___ |
| NMOS W/L | ___120nm/45nm____ |
| NMOS Bias Voltage | ___600mV___ |
| Input Amplitude | ___25mV____ |
| Input Frequency | ___1kHz____ |

###  Observations (From Simulation)
- DC Operating Point (Vout): **______**
- Drain Current (ID): **______**
- Small Signal Gain (Av): **___0.4V___**
- Output Swing: **___964mV___ to ___984mV___**

###  Inference
- High gain and wide output swing
- Excellent bias stability
- Preferred topology for **LDOs, Op-Amps, and BGRs**

### All the related pictures are present under the folder Day_1/CS_with_Active_Load_PMOS

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






  
