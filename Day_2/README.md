#  Analog IC Design Workshop – Day 2  
## Differential Amplifier with PMOS Load and OTA Symbol Creation

This document presents the work completed on **Day 2** of the *Analog IC Design and Layout Considerations* workshop using **Cadence Virtuoso**.  
The focus of this session was the design, analysis, and abstraction of a **MOS differential amplifier with PMOS active loads**, which forms the core of an **Operational Transconductance Amplifier (OTA)**.

---

##  Objective

- To design a **differential amplifier** using MOS transistors
- To understand the role of **PMOS active loads**
- To perform:
  - DC analysis
  - AC analysis
  - Transient analysis
- To create a **symbol (OTA)** from the schematic
- To verify the symbol functionality against schematic-level results

---

##  Differential Amplifier Circuit Description

The circuit consists of:
- An **NMOS differential pair** driven by differential inputs
- A **tail current source** providing constant bias current
- **PMOS current mirror loads** acting as active loads
- A **single-ended output** taken from one branch

The differential pair steers the tail current depending on the input voltage difference, while the PMOS active load converts the current variation into a voltage output.

---

##  Working Principle

- When both inputs are equal, the tail current splits equally between the two NMOS transistors.
- A differential input voltage causes current to shift from one branch to the other.
- The PMOS load mirrors and amplifies this difference, producing a voltage output.
- The use of PMOS active loads significantly increases the output resistance, resulting in high gain.

---

##  DC Analysis

DC analysis was performed to:
- Verify correct biasing of the circuit
- Ensure all MOS transistors operate in the **saturation region**

The results confirmed:
- Stable operating point
- Proper tail current distribution
- Saturation operation of both NMOS and PMOS transistors, which is essential for high-gain amplification

---

##  AC Analysis

AC analysis was carried out to evaluate:
- Small-signal gain
- Frequency response

The differential amplifier exhibited:
- High voltage gain due to the use of PMOS active loads
- Flat mid-band response, making it suitable for OTA applications
- Behavior consistent with a first-stage amplifier in analog IC design

---

##  Transient Analysis

Transient analysis was performed by applying time-varying differential inputs.

Observations:
- Output voltage followed the differential input accurately
- Clear amplification of input difference
- Stable and predictable dynamic behavior

This confirms correct time-domain operation of the differential amplifier.

---

##  OTA Symbol Creation

After verifying the schematic-level operation:
- A **symbol view** was created from the differential amplifier schematic
- The symbol represents an **Operational Transconductance Amplifier (OTA)**
- The symbol includes:
  - Differential inputs
  - Power supply pins
  - Output pin

This abstraction enables hierarchical and modular IC design.

---

##  Symbol-Level Verification

The OTA symbol was tested using the same biasing and input conditions as the original schematic.

Results:
- DC response matched schematic-level behavior
- AC gain and frequency response were consistent
- Transient output closely matched the original circuit

This confirmed that the symbol accurately represents the underlying differential amplifier.

---

### Spectrum Analysis (DFT)

Spectrum analysis using DFT was performed in Cadence Virtuoso to study the frequency-domain behavior of the differential amplifier / OTA. The DFT converts the time-domain output signal into its frequency components, allowing identification of the fundamental tone, harmonic distortion, and noise floor. Harmonics arise due to circuit non-linearities and appear at integer multiples of the input frequency. Key performance metrics evaluated include Signal-to-Noise Ratio (SNR), Signal-to-Noise-and-Distortion Ratio (SNDR), Total Harmonic Distortion (THD), and Spurious-Free Dynamic Range (SFDR). For a well-designed analog block, the noise and distortion components should be significantly lower than the fundamental, with typical design targets of SNR and SFDR greater than 80 dB and low THD. The spectrum analysis confirms that the OTA exhibits acceptable noise and distortion performance for precision analog and mixed-signal applications.


##  Conclusion (Day 2)

- A MOS differential amplifier with PMOS active load was successfully designed and analyzed
- DC, AC, and transient analyses validated correct operation
- OTA symbol creation enabled modular and reusable design
- This OTA forms a fundamental building block for:
  - Low Dropout Regulators (LDOs)
  - Operational Amplifiers
  - Bandgap Reference circuits
- Spectrum analysis using DFT was also performed

---

