# Analog IC Design Workshop – Day 4  
## CMOS Fabrication, Layout Fundamentals & Biasing Improvement

This document summarizes the learning from **Day 4** of the *Analog IC Design and Layout Considerations* workshop.  
The session was conducted by **Charan M.S. (Texas Instruments)** and focused on **CMOS fabrication basics, layout concepts, verification checks**, and **practical biasing improvements** in analog circuits.

---

##  Objective

- To understand the **CMOS fabrication process**
- To learn **layout fundamentals** used in analog IC design
- To study **process-related issues** such as parasitics and isolation
- To understand **DRC and LVS checks**
- To improve biasing of the differential amplifier designed earlier

---

## CMOS Fabrication Overview

CMOS fabrication involves building transistors layer by layer on a silicon wafer using multiple processing steps such as oxidation, deposition, lithography, and etching.

Key regions in CMOS:
- **N-well**: Used to form PMOS transistors
- **P-well**: Used to form NMOS transistors

Proper well formation is essential for device isolation and correct operation.

---

## Isolation Techniques

### LOCOS (Local Oxidation of Silicon)
- Used for transistor isolation in older technologies
- Creates thick oxide regions between devices
- Suffers from the **bird’s beak problem**, where oxide grows sideways and reduces active area

### STI (Shallow Trench Isolation)
- Modern isolation technique
- Trenches are etched and filled with oxide
- Provides better isolation and higher density
- Eliminates bird’s beak issue

---

##  Bird’s Beak Problem

- Occurs in LOCOS isolation
- Oxide grows laterally under the mask
- Reduces effective transistor width
- A major reason for moving to STI in modern processes

---

##  Role of Polysilicon

- **Polysilicon (Poly)** is used as the gate material
- Allows self-aligned gate formation
- Enables precise control of channel length
- Acts as a mask during source/drain implantation

---

##  Contacts, Vias, and Interconnects

- **Contacts** connect diffusion or poly to metal layers
- **Vias** connect one metal layer to another
- **ILD (Inter-Layer Dielectric)** isolates metal layers electrically
- Proper via placement is critical to reduce resistance and parasitics

---

##  Lithography Basics

### Photoresist
- Light-sensitive material applied on wafer
- Used to transfer mask patterns onto the wafer

### Masks
- **Positive Mask**: Exposed regions are removed
- **Negative Mask**: Unexposed regions are removed

### Etching
- Removes unwanted material after lithography
- Can be wet or dry etching

---

##  Annealing

- Heat treatment process after implantation
- Activates dopants
- Repairs crystal damage
- Improves electrical characteristics of devices

---

##  Parasitics in Layout

- Parasitic resistance and capacitance arise from:
  - Interconnects
  - Contacts
  - Device geometry
- Parasitics affect:
  - Gain
  - Speed
  - Stability
- Good layout practices help minimize parasitic effects

---

##  Verification Checks

### DRC (Design Rule Check)
- Ensures layout follows fabrication rules
- Checks spacing, width, enclosure, etc.

### LVS (Layout Versus Schematic)
- Ensures layout matches schematic connectivity
- Confirms correct implementation of the circuit

Both checks are mandatory before fabrication.

---

##  Biasing Improvement in Differential Amplifier

In earlier designs (Day 2), the tail current source was biased using a fixed voltage (`Vb`).

In Day 4:
- A **golden current source** was introduced
- A **current mirror** was used to generate a stable bias voltage
- This approach improves:
  - Bias stability
  - Process and temperature tolerance
  - Matching accuracy

This method reflects **industry-standard biasing practice** in analog IC design.

---

##  Conclusion (Day 4)

- CMOS fabrication and layout fundamentals were introduced
- Key isolation, lithography, and interconnect concepts were explained
- Importance of DRC and LVS verification was highlighted
- Differential amplifier biasing was improved using current mirrors
- This session bridged the gap between **schematic design and physical layout**

---



