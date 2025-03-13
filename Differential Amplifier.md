# MOSFET Differential Amplifier Experiment Report
## Aim:
Design and analyze the MOS differential amplifier circuit for the following specifications:
- Suppy Voltage(V<sub>DD</sub>) = 1.8V
- Input Common Mode Voltage(V<sub>icm</sub>) = 0.95V
- Power Consumption(P) <= 2.2mW
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
### Key Concepts:
- Differential Amplification:The amplifier's strength lies in amplifying the difference between two input signals (V1-V2) rather than each signal individually. 
- Common-Mode Rejection:The amplifier is designed to minimize or eliminate gain for signals that are present on both input terminals (common-mode signals), which helps to filter out noise. 
- MOSFETs as Active Devices:Two matched MOSFETs are used, each with a "pull-up" load, and the gate voltage determines the electrical resistance between the source and drain. 
- Two input terminals and one output terminal:The differential amplifier has two input terminals (inverting and non-inverting) and one output terminal.

## Circuit Diagram:
![Image](https://github.com/user-attachments/assets/afa41c11-f56b-4891-bfea-b9aed7182d56)
- Input bias Voltages(V<sub>2</sub> and V<sub>3</sub>= 0.95V): A DC current that flows into or out of the amplifier's input pins to establish a defined operating point, ensuring proper amplification and preventing saturation. 
- Power Supply(V<sub>1</sub>=1.8V): Provides the necessary DC voltage levels (positive and negative) to bias the MOSFETs, enabling them to operate in the desired amplification region and ensuring proper signal amplification and stability.
- Output Nodes(V<sub>out1</sub> and V<sub>out2</sub>): The differential output is taken from these two terminals.
- NMOS Transistors(M<sub>1</sub>)and M<sub>2</sub>):These are the amplifying elements which forms the differential pair.
- Load Resistors(R<sub>1</sub> and R<sub>2</sub>):Play a crucial role in determining the voltage gain, DC bias, and overall circuit performance by controlling the drain current and voltage swing.
- Current source resistor(R<sub>3</sub>): Establishing a stable bias current and enabling differential amplification by providing a high impedance at the source terminals.

## Design:
### Calculations:
1. I<sub>ss</sub>(Source Current)=P/V<sub>DD</sub> <br/>
I<sub>ss</sub>=2.2mW/1.8V = 1.22mA

2. R<sub>D</sub>(Load resistor)=V<sub>out</sub>-v<sub>DD</sub>/I<sub>D</sub> <br/>
R<sub>D</sub>=0.7kV/0.61mA = 1.147k ohms

3. R<sub>ss</sub>(Current source resistor)=V<sub>p</sub>/I<sub>ss</sub> <br/>
R<sub>ss</sub>=0.4V/1.22mA = 0.327k ohms

## DC Analysis:

### Steps to Perform DC Analysis in LTspice XVII:
1. Build the circuit as per the diagram shown above and set the values of the voltage sources,resistors as per the calculated values.
2. Next go to **SPICE Directive** and type **.lib filename.lib or .lib filepath.lib** to import the Library file.
3. Click **OK**, and place the generated command on the schematic.
4. After importing the library file name the two mosfet as CMOSN.
5. Set the channel length value of M<sub>1</sub> as 180nm and  we have to vary the value of the width to get a desired value of I<sub>D</sub> and V<sub>out</sub>
6. Repeat the same steps with M<sub>2</sub> mosfet.
7. Now go to **Edit simulation command** and select **DC op pnt**.
8. Click **OK**, and place the generated command on the schematic.
9. Next click on run button, you will get a pop up window which gives us information about operating point.It includes the values of V<sub>out</sub> and I<sub>D</sub>.
![Image](https://github.com/user-attachments/assets/8b0b8b80-f0f9-42bf-bb10-ce12d8c2d4a7)

- We got the Operating point as V<sub>out</sub>= 1.10033V and I<sub>D</sub>=0.610004mA

## Transient Analysis:

### Steps to Perform Transient Analysis in LTspice XVII
1. After setting the operating point, we will give sine wave as the input for both the gate terminals of the mosfet.
2. Next set the **Amplitude** as 50mV and **Frequency** as 1kHz for both V<sub>2</sub> and V<sub>3</sub>.
3. You should specify the AC amplitude for each voltage source separately. You have two voltage sources, you can set their AC amplitudes as follows:
 - First Voltage Source(V<sub>2</sub>): **AC amplitude** = 1
 - Second Voltage Source(V<sub>3</sub>): **AC amplitude** = -1
4. Next set **phi[deg]** for V<sub>3</sub> as 180.
5. Now go to **Edit Simulation cmd** and select **Transient**.
6. Give **stop time** as per your convenience, here it is 5m.
7. Click **OK**, and place the generated command on the schematic.
8. Verify the response and note the phase shift and signal gain.
![Image](https://github.com/user-attachments/assets/0d839d46-ac1b-4194-9227-ef2579bb4283)

- According to the calculations the gain(A<sub>v</sub>) is 7.36 <br/>
   A<sub>v</sub>=-g<sub>m</sub>R<sub>D</sub> <br/>
   A<sub>v</sub>=7.36 

- According to the graph obtained from transient analysis the gain(A<sub>v</sub>) is 8<br/>
   A<sub>v</sub>=V<sub>out</sub>/V<sub>in</sub><br/>
   A<sub>v</sub>=0.856/0.107 = 8

## AC Analysis:

### Steps to Perform AC Analysis in LTspice XVII:

1. Go to Simulate > Edit Simulation Cmd.
2. In the AC Analysis tab, choose Decade as the sweep type.
3. Specify the number of points per decade and set the frequency range from 0.1Hz to 1THz.
4. Click OK and place the generated command on the schematic.
5. Ensure that the input voltage source has an AC amplitude of 1V.
6. Click the Run button to start the analysis.
7. Examine the gain and phase plots.
8. Determine key characteristics such as bandwidth and gain margin.


