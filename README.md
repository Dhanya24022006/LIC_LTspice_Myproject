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
5.Now we have to name the mosfet same as pre-built component model.\
5.Now the circuit is completely ready.\
6.In this experiment power rating will be given, we need to find the saturation current for this particular power rating.\
7.After finding the saturation current, we have to vary the width of the mosfet to get the calculated current value.\
