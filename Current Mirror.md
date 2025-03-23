# Experiment 3:
# Current Mirror Circuit
## Part A
## Aim:
 Design and Analyze Current mirror circuit as active load in amplifier circuit.
**Given** :
- Power Supply (V<sub>DD</sub>) = 1.8V.
- Power Consumption (P) <= 1mW. 
- Gain (A<sub>v</sub>) > -10V/V.

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

![Image](https://github.com/user-attachments/assets/f5bd39e0-d8e9-46bd-954a-145ff21f8ad8)

- Input bias Voltages(V<sub>2</sub> and V<sub>3</sub>= 0.95V): A DC current that flows into or out of the amplifier's input pins to establish a defined operating point, ensuring proper amplification and preventing saturation. 
- Power Supply(V<sub>1</sub>=1.8V): Provides the necessary DC voltage levels (positive and negative) to bias the MOSFETs, enabling them to operate in the desired amplification region and ensuring proper signal amplification and stability.
- Output Nodes(V<sub>out1</sub>): The output is taken from this terminal.
- PMOS(M2,M3) and NMOS(M1): NMOS typically acting as a current sink (drawing current towards ground) and PMOS acting as a current source (supplying current from the positive supply). 
- Current source (I<sub>ref</sub>): The current source's role is to provide a stable and well-defined reference current

Calculations:<br>
I<sub>t</sub>=P/V<sub>DD</sub>.<br>
I<sub>t</sub>=I<sub>ref</sub>+I<sub>x</sub>.<br>

## DC Analysis(1:1)
As we know I<sub>t</sub>=I<sub>ref</sub>+I<sub>x</sub><br>
Therefore, for 1:1 ratio I<sub>ref</sub>=Ix<sub>x</sub>br>
So,I<sub>ref</sub>=I<sub>t</sub>/2<br>
I<sub>t</sub>=P/V<sub>DD</sub><br>
I<sub>t</sub>=1mW/1.8V<br>
I<sub>t</sub>=0.555mA.<br>
Therefore,I<sub>ref</sub>=0.2778mA.<br>

To obtain the current value according to the given ratio, the provided values of W/L for M1 is 3um/180nm , M2 is 3um/180nm, and M3 is 3um/180nm.<br>
Vin is selected in such a way that it should be in saturation region so the given Vin is 0.838V.<br>

OUTPUT:

![Image](https://github.com/user-attachments/assets/a41e51b1-a35c-475c-854d-16af4a2f0c67)

### Analyzing the current mirroring circuit by changing the w and L but maintaing the same ratio.

**(a)L=180nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=180nm the w=3um.

|Mosfet     |  I<sub>d</sub>                 | 
|-----------|---------------------|
|  M1       |   0.000277527       |             
|  M2       |   0.000277527       |         
|  M3       |   0.0002778         |             

**(b)L=500nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=500nm the w=8.334um.

|Mosfet     |  I<sub>d</sub>                  |  
|-----------|-----------------------|
|  M1       |   0.000281241         |             
|  M2       |   0.000281241         |             
|  M3       |   0.0002778           |             

**(c)L=1um.**

We know the (w/L) ratio is 16.667.

Therefore for L=1um the w=16.667um.


|Mosfet     |  I<sub>d</sub>                   | 
|-----------|-----------------------|
|  M1       |   0.000280654         |             
|  M2       |   0.000280654         |             
|  M3       |   0.0002778           |             

## Transient Analysis








