# EXPERIMENT 1
## DC,TRANSIENT AND AC ANALYSIS OF COMMON SOURCE AMPLIFIER USING LTSPICE
### COMPONENTS:
n-mosfet(180nm technology node),resistor-1k,voltage source(1.8V,0.9V)),wires.
### CIRCUIT DAIGRAM:
![Image](https://github.com/user-attachments/assets/293dee60-46d8-4a96-947e-c5be22458ccd)
### PROCEDURE:
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
### CALCULATIONS:
Power rating is: 100*u*W\
The gate voltage is: 1.8V\
The the input DC voltage is: 0.9V

