# CMOS Operational Transconductance Amplifier (OTA) — With and Without Miller Compensation

This project presents a detailed comparative study of two CMOS OTA designs:
- A **traditional Miller-compensated OTA**.
- A **novel non-Miller compensated OTA** utilizing an RC network implemented using MOSFETs.

Developed using **TSMC 180 nm CMOS technology** and simulated in **LTspice**, this study aims to evaluate performance trade-offs in terms of gain, power, phase margin, and bandwidth.

---

##  Project Objectives

- Design and simulate two-stage CMOS OTAs.
- Evaluate the impact of Miller vs. non-Miller compensation techniques.
- Measure and compare:
  - DC gain
  - Slew rate (SR)
  - Phase margin (PM)
  - Gain-bandwidth product (GBW)
  - Power consumption

---
##  Circuit diagram
![Image](https://github.com/user-attachments/assets/a7ed26f4-8cc2-44f4-b0e3-65ebd5f7e895)\
Miller Compensated Circuit
![Image](https://github.com/user-attachments/assets/32cf4dcb-3f61-47b3-b2da-846e24e75e2f)\
Without Miller Compensated Circuit

##  Background

Operational Transconductance Amplifiers (OTAs) are widely used in analog filters, ADCs, and other analog interfaces. Two-stage OTAs are typically compensated using the **Miller technique**, but this introduces a **Right Half Plane (RHP) zero**, which degrades phase margin and limits performance under capacitive loads.

To address these limitations, a **non-Miller design** using a **MOSFET-based RC compensation network** was proposed to:
- Eliminate the RHP zero.
- Improve slew rate.
- Reduce power consumption.
- Offer better phase margin scalability.

---

##  Design Overview

###  Miller Compensated OTA

- **Stage 1**: Differential NMOS input (M1–M2) with PMOS active loads (M3–M4).
- **Stage 2**: Common-source amplifier (M7) with PMOS load (M6).
- **Compensation**: 2 pF Miller capacitor connected between gate and drain of M7.
- **Supply voltage**: 1.8V
- **Bias current**: 250 µA

###  Non-Miller Compensated OTA (Class A-AB)

- Dual input: NMOS + PMOS differential pairs.
- Output RC network:
  - **RZ** = MOSFET transmission gate (MZ2, MZ3)
  - **CZ** = Gate-source capacitance of MZ1
- Dominant pole at output.
- Slew enhancement through voltage boosting at internal nodes (A, B, C).

---

##  Simulation Setup

### Tools Used
- [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html)
- TSMC 180nm CMOS PDK
- Python/MATLAB (for data analysis and graphing, optional)

### Files (Example):

---

##  Simulation Results

###  Miller Compensated OTA

| Metric           | Value       |
|------------------|-------------|
| DC Gain          | 77.2 dB     |
| Phase Margin     | > 60°       |
| Unity Gain BW    | 8.6 MHz     |
| Slew Rate        | Moderate    |
| Power Consumption| 450 µW      |

###  Non-Miller Compensated OTA

| Load Cap (pF) | DC Gain (dB) | PM (deg) | GBW (MHz) | Slew Rate (V/µs) |
|---------------|--------------|----------|-----------|-------------------|
| 1             | 67.8         | 132.76   | 9.32      | 549.8             |
| 10            | 67.8         | 142.82   | 4.318     | 142.6             |
| 70            | 67.8         | 120.04   | 1.042     | 28.2              |

---

##  Key Equations

### Gain
Av = gm × ro
gm = 2 × Id / Vov
ro = 1 / λId



### Slew Rate
SR = I_bias / C_load


### Bandwidth and Compensation
- For Miller OTA:
f_D = 1 / (2π R_out C_Miller)
Zero at: f_RHPZ ≈ gm / C_Miller

- For Non-Miller OTA:
Compensation zero = 1 / (RZ × CZ)



---

##  Circuit Schematics

### Miller Compensated
Input (NMOS diff pair) -> Common Source Stage -> Miller Capacitor -> Output


### Non-Miller Compensated



---

##  Conclusion

- **Miller OTA**: High gain and good stability but consumes more power and suffers from limited slew rate.
- **Non-Miller OTA**: Better phase margin, faster transient response, and lower power — ideal for high-speed low-power applications.

---

##  Acknowledgment

We express heartfelt thanks to **Dr. Remya Jayachandran** for her technical guidance and mentorship throughout the project.

---

##  References

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill, 2001.
2. P. E. Allen and D. R. Holberg, *CMOS Analog Circuit Design*, Oxford Univ. Press, 2012.
3. LTspice Simulator - Analog Devices
4. TSMC 180nm CMOS Process Design Kit (PDK)
5. Yüce, A. & Tan, N., *Journal of Engineering*, 2020.
6. Sagbas, M. et al., *IET Circuits, Devices & Systems*, 2016.
7. Gangineni, M., et al., *Electronics Letters*, 2023.
