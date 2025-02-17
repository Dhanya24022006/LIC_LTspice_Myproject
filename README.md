# EXPERIMENT 1
## DC,TRANSIENT AND AC ANALYSIS OF COMMON SOURCE AMPLIFIER USING LTSPICE
### COMPONENTS:
n-mosfet(180nm technology node),resistor-1k,voltage source(1.8V,0.9V)),wires.
### CIRCUIT DAIGRAM:
![Image](https://github.com/user-attachments/assets/293dee60-46d8-4a96-947e-c5be22458ccd)\
### THEORY:
The NMOS transistor common-source amplifier is one of the most commonly used configurations in analog electronics. It offers a high voltage gain, making it suitable for signal amplification applications. The amplifier's behavior is analyzed in three key domains:\
1.DC Analysis: Determines the biasing and operating point.\
2.Transient Analysis: Evaluates the time-domain response.\
3.AC Analysis: Examines the small-signal behavior and frequency response.

### DC Analysis:
The primary objective of DC analysis is to establish a stable operating point for the MOSFET, ensuring it remains in the saturation region for effective amplification. A MOSFET operates in saturation when the drain-source voltage (V<sub>DS</sub>) exceeds the overdrive voltage (V<sub>OV</sub>), where V<sub>OV</sub>=V<sub>GS</sub>−V<sub>TH</sub>. \
The drain current is given by:
I<sub>D</sub>=1/2Kn(V<sub>OV</sub>)<sup>2</sup>\
The values of V<sub>DS</sub> and I<sub>D</sub> determine the MOSFET’s operating point.

### Transient Analysis:
Transient analysis evaluates how the amplifier reacts to time-dependent signals, such as pulse inputs or abrupt voltage changes. The response is influenced by the charging and discharging of capacitors, including coupling and bypass capacitors. The amplifier's reaction to sudden input variations is constrained by its time constants, which depend on the circuit’s resistance and capacitance. This analysis is particularly important in high-speed applications, where factors like rise time, fall time, and propagation delay determine the amplifier's effectiveness in handling fast signals.

### AC Analysis:
In AC analysis, the MOSFET is considered a linear small-signal amplifier, where the drain current varies proportionally with small changes in gate voltage:\
i<sub>D</sub>=g<sub>m</sub>v<sub>gs</sub>
where g<sub>m</sub> represents the transconductance.\
Consequently, the voltage gain of the amplifier is expressed as:
A<sub>v</sub>=−g<sub>m</sub>(RD∣∣RL)
 
The negative sign signifies a 180-degree phase shift between the input and output signals. The input impedance is mainly determined by the gate biasing resistors, whereas the output impedance is largely affected by the drain resistor RDRD​. At low frequencies, gain is influenced by coupling and bypass capacitors, while at high frequencies, parasitic capacitances play a significant role.
### NMOS Transistor in Saturation Region

For an NMOS transistor to operate in the saturation region, the following condition must be satisfied:
V<sub>DS</sub>≥V<sub>GS</sub>−V<sub>th</sub>

where:
V<sub>GS</sub> is the gate-to-source voltage (given as 0.9V),
V<sub>DS</sub> is the drain-to-source voltage,
V<sub>th</sub> is the NMOS threshold voltage.

The drain current in the saturation region is expressed as:
I<sub>D</sub>=1/2μ<sub>n</sub>CoxW/L(V<sub>GS</sub>−V<sub>th</sub>)<sup>2</sup>

Where:

I<sub>D</sub>​ is the drain current (55µA),
μ<sub>n</sub> is the electron mobility,
Cox is the oxide capacitance per unit area,
W is the width of the NMOS transistor,
L is the length of the NMOS transistor,
V<sub>GS</sub>​ is the gate-to-source voltage,
V<sub>th</sub> is the threshold voltage.

### Width Calculation for Desired Current:

To determine the required width WW, we rearrange the drain current equation as follows:
W={2I<sub>D</sub>L}/μ<sub>n</sub>Cox(V<sub>GS</sub>−V<sub>th</sub>)<sup>2</sup>

By substituting the given parameters, including process-dependent values of μnμn​ and CoxCox​, we can calculate the necessary width WW to achieve the desired drain current of 55µA.
### Parameters to Substitute:
( ID = 55 , un ),
( L ) is the length of the NMOS transistor,
( un) and ( Cox} ) are process-dependent constants (typically given in the datasheet or technology library),
( VGS = 0.9 , V ),
( Vth ) is the threshold voltage (typically provided in the datasheet).
### Procedure:
1.Build a common source amplifier circuit using LTspice software.\
2.Now set the values for voltage sources and resistors.\
3.For Mosfet, we need to import a pre-built component model by loading a library file.\
4.Next to import a library file, we open SPICE directive and enter a command: .lib filename.lib.\
5.Now, we have to name the MOSFET the same as pre-built component model.\
6.Now the circuit is completely ready.\
7.In this experiment power rating will be given, we need to find the saturation current for this particular power rating.\
8.After finding the saturation current, we have to vary the width of the mosfet to get the calculated current value.\
9.In LTspice to get the saturation current we have to DC analysis.This is done by simulating the circuit.\
10.Now, we need to edit the simulation command to: DC op pnt.\
11.After simulating the circuit in the above mentioned command, we will get the operating point which will be having the values of saturation current, Vout, etc.\
12.Now the next process is, we need to do transient analysis.
13.In transient analysis we will give a sine wave as input.
14.Now again edit the simulation command to:Transient, here we need set the stop time as per the given data.\
15.After simulating in this command we get the graph of input and output waveforms.\
16.Next is AC analysis, for this we need to edit the simulation command to:AC analysis.\
17.Here we need to set the value for start frequency,stop frequency and number of points. Also set the type of sweep.\
18.Simulate the circuit using this command, we will get the frequency response of a circuit.\
### Calculations:
Power rating is: 100*u*W\
The gate voltage is: 1.8V\
The the input DC voltage is: 0.9V\
We know that P=VI,so I=55.55A\
From loop equation : VDD = IDRD + Vout\
where VDD= 1.8, ID=55.5uA, RD=1KHz\
Therefore Vout= 1.745V\
Hence Q point= (1.745V, 55.5uA)\
### Tabulation:
|Width   |I<sub>D</sub>      |Vout    |
|--------|--------|--------|
|1*u*m     |152.7*u*A |1.64V   |
|--------|--------|--------|
### Result:
1.DC Analysis:\
![Image](https://github.com/user-attachments/assets/006a6311-edbe-4cc5-b654-d88e790d2bda)\
we got I<sub>D</sub>= 55.5uA\
width = 0.203um\
Vout= 1.7444V\
we get DC operating point as (1.7444V, 55.5uA)\

2.Transient Analysis:\

