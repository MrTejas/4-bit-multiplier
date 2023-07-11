
# 4-bit Multiplier

The project mainly deals with design and performance analysis of a simple 4x4 multiplier circuit. The circuit is simulated in ngspice and power and time-delay analysis is done for pre-layout netlist as well as post-layout netlist. 
		
Layout is done in magic and the verification of the logic of the code is done in verilog. The pre-layout and post-layout results are compared and conclusions are drawn about the ideal and real life circuits found ICs present today.
## NgSpice Netlist

For writing the netlist, extensive use of subckt is done to abstract individual building blocks of the circuit for the readability and robustness of the final multiplier. Firstly, subcircuits for basic gates like NAND, NOT, AND, OR are made and their functionality is verified. 

Next, using these basic gates, the building blocks of the 4x4 multiplier such as half-adder, full-adder, 4-bit adder are made and the final multiplier is just a simple combination of these blocks. The gate level circuit used for 4x4 multipllier is as shown in the figure :-

![enter image description here](https://imgur.com/MlxrGew.png)



## Magic Layout

The layout for the same circuit is done in magic. Extensive use of getcell is done todo as much abstrction as possible. For example, one cell is made for each of the basec gates used to build adder circuits, which then are used to make the multiplier circuit. The only 2 basic gates made without using another cell are NAND and NOT. The gates for OR, AND, XOR etc are then made from these and circuits for adders are then made from these gates.

![enter image description here](https://imgur.com/IpVWqBz.png)


### Output Images and Final Layout
- The left image shows output for the layout build of the multiplier and the right image shows the output for the netlist written without considering the various capacitances involved in non-ideal conditions.

![](https://imgur.com/vhOBnj2.png)
- The final layout of the multiplier is build from individual smaller blocks such as :-
	- AND, XOR, OR, NAND, NOT  gates
	- Half-Adder
	- Full-Adder
	- 4-bit Adder
	
![enter image description here](https://imgur.com/PFc5IDr.png)

> **Note :**  For detailed values and calculations of power and time-delay analysis, refer to the `VLSIReport.pdf`
