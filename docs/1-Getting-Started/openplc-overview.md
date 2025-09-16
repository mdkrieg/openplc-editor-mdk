1.1 OpenPLC Overview
====================

 

OpenPLC is an open-source [Programmable Logic Controller](https://en.wikipedia.org/wiki/Programmable_logic_controller) that is based on an easy to use software. It is the first fully functional standardized open source PLC, both in software and in hardware. The OpenPLC project was created in accordance with the IEC 61131-3 standard, which defines the basic software architecture and programming languages for PLCs.

OpenPLC is mainly used on industrial and home automation, internet of things and SCADA research. You can check OpenPLC in action on the short video below:

[<https://autonomylogic.com//wp-content/uploads/2022/05/OpenPLC-Intro.mp4>](https://autonomylogic.com//wp-content/uploads/2022/05/OpenPLC-Intro.mp4?_=1)

The OpenPLC Project consists of two parts: Runtime and Editor. The Runtime is a portable software designed to run from the smallest of all microcontrollers (Arduino-compatible) to powerful servers in the cloud. It is responsible for executing the PLC programs you create using the Editor. Currently, OpenPLC Runtime is officially supported on the following platforms:

* Arduino Uno / Nano / Leonardo / Micro
* Arduino Mega / Due
* Arduino Nano Every / IoT / BLE
* Arduino RB2040 Connect
* Arduino Mkr / Zero / WiFi
* Arduino Pro (Machine Control and EDGE)
* Controllino Maxi / Automation / Mega / Mini
* Productivity Open P1AM
* ESP8266 (nodemcu)
* ESP32
* Raspberry Pi 2 / 3 / 4
* PiXtend
* UniPi Industrial Platform
* Neuron PLC
* FreeWave Zumlink
* FreeWave ZumIQ
* Windows (generic target as a soft-PLC)
* Linux (generic target as a soft-PLC)

The OpenPLC Editor is the software that runs on your computer and, as mentioned, is used to create your PLC programs. It is very simple to use and supports all five languages defined in the IEC 61131-3 standard: Ladder Logic (LD), Function Block Diagram (FBD), Instruction List (IL), Structured Text (ST), and Sequential Function Chart (SFC).