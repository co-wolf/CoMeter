# CoMeter

**CoMe**_ter_ is an Arduino based measurement system that has been developed in the scope of a **Co**mputer-based **Me**asurement lab at Coburg University of Applied Science. The project was inspired by NI myDAQ, but is in no way affiliated with National Instruments. The unique features of the system are that it is cheap and its software as well as hardware is open, can be studied, modified and extended. It is intended to be used in teaching, student projects and research, but it can also be built by any interested person.

The project and the measurement system consists of the following components:
- Electronic circuit with Arduino (Fritzing PCB)
- Mechanical case (tbd)
- Arduino sketch
- Desktop GUI (Python)

## Electronic circuit

The measurement hardware is based on the Arduino Nano microcontroller and only costs abaout 35 €. It is connected to a PC via USB cable, which is used for data transfer as well as power supply. At the moment the following features are implemented in the circuit:
- Voltage input (-10...+10 V, 15 bit)
- Current input (-1...+1 A, 15 bit)
- Voltage output (-10...+10 V, 12 bit)

## Arduino sketch

The Arduino code implements the low level measurenet features on the microcontroller board. Communication is done via serieal interface over USB. A powerful command interpreter has been developed, which allows to dynamically set parameters and query measurement values from the Arduino. The command syntax has been chosen such that it partially resembles the standardized SCPI commands used by modern lab equipment such as multimeters, function generators, and oscilloscopes. The idea behind this design choise is that the system can be used as drop-in replacement for one or more of these instruments in a given measurement setup without the need to modify the measurement software.

## Desktop GUI

The GUI is written in PyQt and implements the following measurement instruments in software:
- Digital multimeter (DMM)
- Function generator (FGEN)
- Digital storage oscilloscope (DSO)

For the desktop side of the communication the Python VISA library is used. VISA is an abstraction layer for measurement devices that is implemented by most modern instruments. In combination with the SCPI commands this means that the measurement GUI can also be used with commercial DMMs, FGENs or DSOs. In the future it is planed to extend the software to be able to use a combination of different devices to accomplish complex, hirachycal measurement tasks.

The project has been funded by the Innovationsfond Lehre of Coburg University of Applied Sciences.
