# Experiment 3:
# Current Mirror Circuit
## Part A
## Aim:
 Design and Analyze Current mirror circuit as active load in amplifier circuit.
**Given** :
Vdd=1.8V.<br>
P<=1mW. <br>
Av>-10V/V.<br>

### Perform
- DC Ananlysis
- Transient Analysis
- AC Analysis
- Extract required parameters

## Components Required:
- MOSFET(NMOS,PMOS)
- Resistors
- Current source
- Voltage supply
- Connecting wires

## Theory
### Function:
The primary purpose of a current mirror is to replicate a current flowing through one active device (the "input" transistor) to another active device (the "output" transistor), maintaining a constant current regardless of load conditions.
In this specific configuration, the two PMOS transistors are used to create a current mirror, with the NMOS transistor acting as a current source or sink. 
### Operation:
- The input current is set by an external source, which flows through the input PMOS transistor. 
- The voltage drop across the input PMOS transistor is mirrored by the output PMOS transistor. 
- This mirrored voltage drop, in turn, controls the current flow through the output PMOS transistor, creating a mirrored current.

## Circuit Diagram







