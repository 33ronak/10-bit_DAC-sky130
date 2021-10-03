# 10 Bit Potentiometric DAC

The following repository is the documentation to simulation of a 10 Bit Pottentiometric Digital to Analog Converter(DAC), using [eSim](https://esim.fossee.in/downloads), [ngspice 35](https://sourceforge.net/projects/ngspice/files/), and [Skywater 130nm PDK](https://github.com/google/skywater-pdk). All the refrances and contributors are mentioned in aknowledgement.

## Content 

- [Theory](#theory)
- [Prerequisite](#prerequisite)
- [Circuit Diagrams](#circuit-diagrams)
  * [Switch](#switch)
  * [2 bit DAC](#2-bit-dac)
  * [3 bit DAC](#3-bit-dac)
  * [4 bit DAC](#4-bit-dac)
  * [5 bit DAC](#5-bit-dac)
  * [6 bit DAC](#6-bit-dac)
  * [7 bit DAC](#7-bit-dac)
  * [8 bit DAC](#8-bit-dac)
  * [9 bit DAC](#9-bit-dac)
  * [10 bit DAC](#10-bit-dac)
- [Observation](#observation)
- [Acknowledgements](#acknowledgements)


## Theory 

Almost all the signals that exist in the nature and the physical phenomena associated with them are all analog signal. The digital systems can not interpret these analog signal as they are made of binary and can only process the digital signals fed to these systems. Thus there is a need of a digital system that can convert an analog signal into a digital signal for the processing bt intended digital system. The analog input signals are converted to digital signals using an Analog-to-Digital Converters (ADC). As the converted analog signal to the digital signal is processed by a digital system like Logic Gates, Microcontrollers or Microprocessors etc., after the processing of the digital signal by the digital system, it would be required to send back the signal into an analog form to interact with the natures physical phenom and to do that there is a need of a Digital-to-Analog-Converter(DAC).

![Block Diagram DAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Block-Diagram.png?raw=true)

A n-bit DAC takes a n-bit digital data and converts it into a proportional analog signal with a varrying voltage with respect to the reference voltage. The potentiometric DAC is build using the concepts of Voltage Divider. In an n-bit DAC, the analog voltage range i.e. the Vref is equally divided into 2^n voltage values, and then this is transfered by a series on 2^n resistors having same resistance R. The combination of switches are added to create a data flow path at the end interface and then there is a transducer which interprets the varrying voltage values with respect to the reference voltage (Vref) and produce another physical phenomena at the end of the system as output for interacting with the nature.

![generalDAC](https://user-images.githubusercontent.com/71374784/135751325-c32b5248-ee0b-4a39-a75e-9138ad8bcec6.png)

I have tried to simulate an 10-bit DAC, the block diagram of which is given below:

![1bit_block_Diagram](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Block-Diagram.png?raw=true)




## Prerequisite

### Tools
The tools required for the design and simulation of the circuits are:-
- [eSim](https://esim.fossee.in/downloads)
- [ngspice 35](https://sourceforge.net/projects/ngspice/files/)
- [Skywater 130nm PDK](https://github.com/google/skywater-pdk)

## Circuit Diagrams
The Circuit Diagram for a switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-DAC, 7-bit, 8-bit, 9-bit and 10-bit were all designed in eSim. The simulation was done using ngspice 35 and sky 130 transistors models, after creating the schematics, the spice netlist was extracted for all the circuits and the subcircuits models that were created and used in higher DACs design. The Circuit Digram for all the circuits are given below subsequently, along with the post simulation observation and the transient analyisis graphs.

### Switch
The switch circuit was designed using the mosfets and then sky130 models were integrated while simulation. The schematic is shown below:

![switch](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/switch.png?raw=true)


The result of transient analysis and the ngspice output of the switch is shown below:

![switch op](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/switch/ngspice_switch.png?raw=true)
![switch opt](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/switch/switch_tran.png?raw=true)


### 2 bit DAC
The subcircuits of switch was used for designing of 2-bit DAC; the schematic of 2 bit DAC is as shown below: 

![2bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/2-bit.png?raw=true)

The result of transient analysis and the ngspice output of the 2-bit DAC is shown below:

![2bit dac op](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/2bit_DAC/ngspice_2bit-DAC.png)
![2bit dac opt](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/2bit_DAC/2bit_DAC-tran.png)

### 3 bit DAC
For the 3 bit DAC, the subcircuits of 2bit DAC and switch were used. The schematic of 3 bit DAC circuit is as shown below:

![3bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/3-bit.png?raw=true)

The result of transient analysis and ngspice of 3 bit DAC is shown below:

![3bit dac op](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/3bit_DAC/ngspice_3bit-DAC.png)
![3bit dac opt](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/3bit_DAC/3bit_DAC-tran.png)

The subcircuit of 3bit DAC was futher created for 4-bit DAC which included the 2bit DAC and switch subcircuits.

### 4 bit DAC
For the 4 bit DAC, the subcircuits 3bit DAC and switch were used. The schematic is as shown below:

![4bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/4bit_DAC/ngspice_4bit-DAC.png)

The result of the transient analysis and the ngspice output of the circuit is shown below:

![4bit dac op](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/4bit_DAC/ngspice_4bit-DAC.png)
![4bit dac op](https://github.com/33ronak/10-bit_DAC-sky130/tree/main/IMAGES/4bit_DAC)

The subcircuit of 4 bit DAC was further created to be used in 5 bit DAC, which included 3bit DAC and switch.

### 5 bit DAC
For the 5 bit DAC, the subcircuits 4bit DAC and switch were used. The eSim schematic is as shown below:

![5bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/5-bit.png?raw=true)

The result of the transient analysis of the circuit is shown below:

![5bit dac op](https://github.com/vsdip/avsddac_3v3_sky130_v2/blob/main/DAC_Prelayout/Screenshots/5bitDAC_op.png)

Here, there are 5 digital input bits and hence 32 steps in the analog output.

The subcircuit of 5 bit DAC was created which included 4bit DAC and switch.

### 6 bit DAC
For the 6 bit DAC, the subcircuits 5bit_DAC.sub and switch.sub were used. The eSim schematic is as shown below:

![6bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/6-bit.png?raw=true)

The result of the transient analysis of the circuit is shown below:

![6bit dac op](https://github.com/vsdip/avsddac_3v3_sky130_v2/blob/main/DAC_Prelayout/Screenshots/6bitDAC_op.png)

Here, there are 6 digital input bits and hence 64 steps in the analog output.

The subcircuit of 6 bit DAC was created which included 5bit DAC and switch.

### 7 bit DAC
For the 7 bit DAC, the subcircuits 6bit_DAC.sub and switch.sub were used. The eSim schematic is as shown below:

![7bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/7-bit.png?raw=true)

The result of the transient analysis of the circuit is shown below:

![7bit dac op](https://github.com/vsdip/avsddac_3v3_sky130_v2/blob/main/DAC_Prelayout/Screenshots/7bitDAC_op.png)

Here, there are 7 digital input bits and hence 128 steps in the analog output.

The subcircuit of 7 bit DAC was created which included 6bit DAC and switch.

### 8 bit DAC
For the 8 bit DAC, the subcircuits 7bit_DAC.sub and switch.sub were used. The eSim schematic is as shown below:

![8bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/8-bit.png?raw=true)

Here, there are 8 digital input bits and hence 256 steps in the analog output.

![8bit dac op](https://github.com/vsdip/avsddac_3v3_sky130_v2/blob/main/DAC_Prelayout/Screenshots/8bitDAC_op.png)

The subcircuit of 8 bit DAC was created which included 7bit DAC and switch.

### 9 bit DAC
For the 9 bit DAC, the subcircuits 8bit_DAC.sub and switch.sub were used. The eSim schematic is as shown below:

![9bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/9-bit.png?raw=true)

The transient response of this schematic could not be obtained. The ngspice session got killed.

However, the subcircuit of 9 bit DAC was created which included 8bit DAC and switch.

### 10 bit DAC
For the 10 bit DAC, the subcircuits 9bit_DAC.sub and switch.sub were used. The eSim schematic is as shown below:

![10bitDAC](https://github.com/33ronak/10-bit_DAC-sky130/blob/main/IMAGES/Circut%20Diagram(eSim)/10-bit.png?raw=true)

The transient response of this schematic is as shown below:

![10bitDAC](https://github.com/vsdip/avsddac_3v3_sky130_v2/blob/main/DAC_Prelayout/Screenshots/10bit_DAC_output.png)
## Observation
## Acknowledgements

 * Kunal Ghosh, Co-Founder of VLSI System Design (VSD) Corp. Pvt. Ltd. - kunalghosh@gmail.com

