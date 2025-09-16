* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [2. OpenPLC Runtime](https://autonomylogic.com/docs-category/openplc-runtime/ "2. OpenPLC Runtime")
* 2.5 Modbus Addressing


2.5 Modbus Addressing
=====================

 

OpenPLC can be configured as a Modbus slave (server). A Modbus slave is normally controlled by a master that performs measurement and control. The remote master initiates read and write requests to the OpenPLC slave sending Modbus frames over the network (Modbus/TCP). The OpenPLC micro runtime for Arduino-compatible boards also supports Modbus frames over serial and USB. The OpenPLC Runtime for Linux and Windows hosts has a Modbus server running by default on TCP port 502. This configuration can be changed on the “Settings” tab.

OpenPLC supports the following Modbus function codes:

* Read discrete output coil (0x01)
* Write discrete output coil (0x05)
* Write multiple discrete output coils (0x0F)
* Read discrete input contacts (0x02)
* Read analog input registers (0x04)
* Read analog output holding registers (0x03)
* Write analog output holding register (0x06)
* Write multiple analog output registers (0x10)

The Modbus addresses bind to PLC addresses based on the hierarchical address value, i.e. lower PLC addresses are mapped to lower Modbus addresses. Addresses are mapped sequentially whenever possible. The following table shows the Modbus address space for the OpenPLC Linux/Windows runtime:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| Modbus Data Type | Usage | PLC Address | Modbus Data Address | Data Size | Range | Access |
| Discrete Output Coils | Digital Outputs | %QX0.0 – %QX99.7 | 0 – 799 | 1 bit | 0 or 1 | RW |
| Discrete Output Coils | Slave Outputs | %QX100.0 – %QX199.7 | 800 – 1599 | 1 bit | 0 or 1 | RW |
| Discrete Input Contacts | Digital Inputs | %IX0.0 – %IX99.7 | 0 – 799 | 1 bit | 0 or 1 | R |
| Discrete Input Contacts | Slave Inputs | %IX100.0 – %IX199.7 | 800 – 1599 | 1 bit | 0 or 1 | R |
| Analog Input Registers | Analog Input (including slave) | %IW0 – %IW1023 | 0 – 1023 | 16 bits | 0 – 65535 | R |
| Holding Registers | Analog Outputs (including slave) | %QW0 – %QW1023 | 0 – 1023 | 16 bits | 0 – 65535 | RW |
| Holding Registers | Memory (16-bits) | %MW0 – %MW1023 | 1024 – 2048 | 16 bits | 0 – 65535 | RW |
| Holding Registers | Memory (32-bits) | %MD0 – %MD1023 | 2048 – 4095 | 32 bits | 0 – 4294967295 | RW |
| Holding Registers | Memory (64-bits) | %ML0 – %ML1023 | 4096 – 8191 | 64 bits | 0 – a really big number! | RW |

Due to memory limitations, microcontroller-based platforms like ESP32, STM32, RP2040 and some Arduino boards have a much more limited Modbus address space, according to the table below:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| Modbus Data Type | Usage | PLC Address | Modbus Data Address | Data Size | Range | Access |
| Discrete Output Coils | Digital Outputs | %QX0.0 – %QX6.7 | 0 – 55 | 1 bit | 0 or 1 | RW |
| Discrete Input Contacts | Digital Inputs | %IX0.0 – %IX6.7 | 0 – 55 | 1 bit | 0 or 1 | R |
| Analog Input Registers | Analog Input | %IW0 – %IW31 | 0 – 31 | 16 bits | 0 – 65535 | R |
| Holding Registers | Analog Outputs | %QW0 – %QW31 | 0 – 31 | 16 bits | 0 – 65535 | RW |
| Holding Registers | Memory (16-bits) | %MW0 – %MW19 | 32 – 51 | 16 bits | 0 – 65535 | RW |
| Holding Registers | Memory (32-bits) | %MD0 – %MD19 | 52 – 91 | 32 bits | 0 – 4294967295 | RW |
| Holding Registers | Memory (64-bits) | %ML0 – %ML19 | 92 – 171 | 64 bits | 0 – a really big number! | RW |

Platforms based on ATmega 328P, ATmega 168, ATmega32U4, and ATmega16U4 like the Arduino Uno and similar have an even more limited address space due to their very low RAM footprint:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| Modbus Data Type | Usage | PLC Address | Modbus Data Address | Data Size | Range | Access |
| Discrete Output Coils | Digital Outputs | %QX0.0 – %QX3.7 | 0 – 31 | 1 bit | 0 or 1 | RW |
| Discrete Input Contacts | Digital Inputs | %IX0.0 – %IX0.7 | 0 – 7 | 1 bit | 0 or 1 | R |
| Analog Input Registers | Analog Input | %IW0 – %IW5 | 0 – 5 | 16 bits | 0 – 65535 | R |
| Holding Registers | Analog Outputs | %QW0 – %QW31 | 0 – 31 | 16 bits | 0 – 65535 | RW |

Discrete output coil and discrete input contact binding are based on the the two-part PLC address, without unused Modbus data addresses. The least-significant part of the PLC address has a range 0 to 7, therefore, a little math is needed to translate between PLC addresses and Modbus data addresses. Given the Modbus data address, the PLC address is determined as:

> msp := int(modbus\_data\_address / 8)
>
> lsp := modbus\_data\_address mod 8
>
> final address = msp.lsp

For example, if the Modbus address for a discrete output coil is *22*, then the most significant part is *2* (22 / 8) and the least significant part is *6* (22 mod 8). Therefore, the PLC address is *%QX2.6*.

##### What are your Feelings

Updated on 2024-12-16

Leave a Reply [Cancel reply](/docs/2-5-modbus-addressing/#respond)
------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2F2-5-modbus-addressing%2F) to post a comment.