# MOS Differential Amplifier Experiment Report
## Aim:
Design and analyze the MOS differential amplifier circuit for the following specifications:
- Suppy Voltage(V<sub>DD</sub>) = 1.8V
- Input Common Mode Voltage(V<sub>icm</sub>) = 0.95V
- Power Rating(P) <= 2.2mW
- Output Common Mode Voltage(V<sub>ocm</sub>) = 1.1V
- Differential Amplifier node voltage(V<sub>p</sub>) = 0.4V
### Perform
- DC Ananlysis
- Transient Analysis
- AC Analysis
- Extract required parameters

## Components Required:
- MOSFET(NMOS)
- Resistors
- Current source
- Voltage supply
- Connecting wires

## Theory:
A MOSFET differential amplifier amplifies the difference between two input voltages while rejecting common-mode signals, leveraging two MOSFETs to produce an output proportional to the difference between the inputs. 
Key Concepts:
- Differential Amplification:The amplifier's strength lies in amplifying the difference between two input signals (V1-V2) rather than each signal individually. 
- Common-Mode Rejection:The amplifier is designed to minimize or eliminate gain for signals that are present on both input terminals (common-mode signals), which helps to filter out noise. 
- MOSFETs as Active Devices:Two matched MOSFETs are used, each with a "pull-up" load, and the gate voltage determines the electrical resistance between the source and drain. 
- Two input terminals and one output terminal:The differential amplifier has two input terminals (inverting and non-inverting) and one output terminal.

