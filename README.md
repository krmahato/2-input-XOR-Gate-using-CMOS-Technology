# 2-input XOR Gate using CMOS Technology
In this repository, the design and impementation of 2-input XOR Gate is presented using Synopsis Custom Compiler on 28nm CMOS Technology.

## Table of content
 - [Introduction](#introduction)
 - [Reference Circuit](#reference-circuit)
 - [Reference Circuit Waveform](#reference-circuit-waveform)
 - [Tools Used](#tools-used)
 - [Schematics in Synopsys](#schematics-in-synopsys)
 - [Simulation in Synopsys](#simulation-in-synopsys)
 - [Netlist of the Circuit:](#netlist-of-the-circuit)
 - [Author:](#author)
 - [Acknowledgements](#acknowledgements)
 - [References](#references)
## Introduction
XOR gate is a digital logic gate that gives a true (1/HIGH) output when the number of true inputs is odd. An XOR gate implements an exclusive-or from mathematical logic, a true output results if only one of the inputs to the gate is true. If both inputs are same, i.e, both HIGH or both LOW, then it results false(0/LOW).
Here, the realization of XOR gate is done by putting together different combinations of p-type MOSFETs and n-type MOSFETs to get the desired Boolean expression of XOR gate.
The Boolean expression of two-input XOR gate is Y = AB’ + A’B.

![xor](https://user-images.githubusercontent.com/100530105/155894009-6f952568-a463-4907-a5e2-664316b0c598.png)

  Fig.1 XOR Gate Symbol

![image](https://user-images.githubusercontent.com/100530105/155894211-f0911051-07b7-4f37-ace0-ae08ec496470.png)
 
 Fig.2 Truth table of XOR Gate
 
 ## Reference Circuit
 The Boolean expression of two-input XOR gate is
	Y =  AB’ + A’B  =  A'B' + AB

For pull down part, there are two AND terms and one OR term. 
Each of the AND term is realized by two series-connected n-MOSFETs. And, the OR term is realized by parallel connection of two series-connected n-MOSFETs realizing AND terms. Then for the pull up part, four p-MOSFETs are connected in a reverse manner. Two additional inverters are also required to obtain the inverse of both variables, i.e. A and B. With these inverters the final circuit will contain in total of 12 transistors.

![20220219_183454087_001](https://user-images.githubusercontent.com/100530105/155898602-0464d156-19d4-4b76-975d-e4d9efca6e74.jpg)

Fig.3 Reference Circuit Diagram

## Reference Circuit Waveform
![refWave](https://user-images.githubusercontent.com/100530105/155894824-3101aaa8-c310-43ee-90b2-3e8fb6b729ae.jpg)

## Tools Used
#### 1. Synopsys Custom Compiler:
The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.

#### 2. Synopsys Primewave:
PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

#### 3. Synopsys 28nm PDK:
The Synopsys 28nm Process Design Kit(PDK) was used in creating and simulating the above circuit design.

## Schematics in Synopsys
### Schematic for XOR Gate:
![klib_xorgate_schematic](https://user-images.githubusercontent.com/100530105/155895263-19f2555d-3d57-4679-9b9b-3efd3767514a.png)

### Symbol for XOR Gate:
![klib_xorgate_symbol](https://user-images.githubusercontent.com/100530105/155895386-456b8064-ed0e-409f-a066-05f2762b4517.png)

## Simulation in Synopsys
### XOR Gate test circuit:
![klib_xortesting_schematic](https://user-images.githubusercontent.com/100530105/155895333-70383291-e763-4624-bc56-825c4ff4e351.png)

### Input Parameters for test circuit:
#### For Input A:-
![v1](https://user-images.githubusercontent.com/100530105/155896341-3baad3a3-c184-48e4-8c0b-516335db18d5.png)

#### For Input B:-
![v2](https://user-images.githubusercontent.com/100530105/155896392-f2aa58d5-4cbc-4c57-973b-0b888aa54e9e.png)

### Transient Analysis:
After successfully creating the schematic, Primewave is used to start the simulation. In the Primewave, the 'model file' is set to 'saed32nm.lib'. Then Transient Analysis is selected in 'Analysis Window'. Below is the setting for Transient analysis.

![transient ana](https://user-images.githubusercontent.com/100530105/155896126-2c245204-5291-422e-a878-79f10c08b5ef.png)

Fig.4 Setting for Transient Analysis

Then add the outputs which needs to be plotted by selecting the nets on the schematic.

Then goto 'Simulations'->'Netlist and Run' to generate a netlist and run the simulation.

### Output Waveform
![waveform](https://user-images.githubusercontent.com/100530105/155896261-4ff76759-23e1-4c6e-abb4-0fe27c25533c.png)

## Netlist of the circuit
Refer to the netlist of the circuits here:[netlist.txt](https://github.com/krmahato/2-input-XOR-Gate-using-CMOS-Technology/files/8149282/netlist.txt)

## Author
Krishna Mahato, B.Tech, 3rd year, National Institute of Science and Technology, Berhampur, Odisha

## Acknowledgements
- [Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
- [Synopsys India](https://www.synopsys.com/)
- [VLSI System Design (VSD) Corp. Pvt. Ltd India](https://www.vlsisystemdesign.com/)
- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
- Chinmay panda, IIT Hyderabad
- Sameer Durgoji, NIT Karnataka

## References
- Sung-Mo Kang and Yusuf Leblebici, “CMOS Digital Integrated Circuits Analysis and Design”, third edition, McGraw Hill, 2005.
- John P. Uyemura, “Chip Design for Submicron VLSI: CMOS Layout and Simulation”, Thomson, 2006.
- [Wikipedia](https://en.wikipedia.org/wiki/XOR_gate)
