* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [2. OpenPLC Runtime](https://autonomylogic.com/docs-category/openplc-runtime/ "2. OpenPLC Runtime")
* 2.4 Physical Addressing


2.4 Physical Addressing
=======================

 

OpenPLC Runtime is compatible with several different hardware platforms with different I/O module configurations. Internally, all I/O variables are associated with a PLC Address, as explained on **[*2.3 Input, Output and Memory Addressing*](/docs/2-3-input-output-and-memory-addressing/)**. The hardware layer is the component responsible for translating internal PLC Address variables into physical hardware locations. Each platform OpenPLC supports must have a different hardware layer. Below you can find the pinout description for each platform, extracted from the platform’s hardware layer file:

Microcontroller-based boards
============================

Arduino Opta
------------

|  |  |  |
| --- | --- | --- |
| Digital In | A0, A1, A2, A3, A4, A5, A6, A7 | %IX0.0 – %IX0.7 |
| Digital Out | D0, D1, D2, D3 | %QX0.0 – %QX0.3 |
| Analog In | A0, A1, A2, A3, A4, A5, A6, A7 | %IW0 – %IW7 |
| Analog Out | – | – |

Controllino Maxi
----------------

|  |  |  |
| --- | --- | --- |
| Digital In | A4, A5, A6, A7, A8, A9, IN0, IN1 | %IX0.0 – %IX0.7 |
| Digital Out | D4, D5, D6, D7, D8, D9, D10, D11  R0, R1, R2, R3, R4, R5, R6, R7  R8, R9 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.7  %QX2.0 – %QX2.1 |
| Analog In | A0, A1, A2, A3 | %IW0 – %IW3 |
| Analog Out | D0, D1, D2, D3 | %QW0 – %QW3 |

Controllino Maxi Automation
---------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | AI2, AI3, AI4, AI5, AI6, AI7, AI8, AI9  AI10, AI11, DI0, DI1, DI2, DI3, IN0, IN1 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.7 |
| Digital Out | DO0, DO1, DO2, DO3, DO4, DO5, DO6, DO7  R0, R1, R2, R3, R4, R5, R6, R7  R8, R9 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.7  %QX2.0 – %QX2.1 |
| Analog In | A0, A1, A13, A13 | %IW0 – %IW3 |
| Analog Out | AO0, AO1 | %QW0 – %QW1 |

Controllino Mega
----------------

|  |  |  |
| --- | --- | --- |
| Digital In | A5, A6, A7, A8, A9, A10, A11, A12  A13, A14, A15, I16, I17, I18, IN0, IN1 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.7 |
| Digital Out | D12, D13, D14, D15, D16, D17, D18, D19  R0, R1, R2, R3, R4, R5, R6, R7  R8, R9, R10, R11, R12, R13, R14, R15 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.7  %QX2.0 – %QX2.7 |
| Analog In | A0, A1, A2, A3, A4 | %IW0 – %IW4 |
| Analog Out | D0, D1, D2, D3, D4, D5, D6, D7  D8, D9, D10, D11 | %QW0 – %QW7  %QW8 – %QW11 |

esp32
-----

|  |  |  |
| --- | --- | --- |
| Digital In | 17, 18, 19, 21, 22, 23, 27, 32  33 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.0 |
| Digital Out | 01, 02, 03, 04, 05, 12, 13, 14  15, 16 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.1 |
| Analog In | 34, 35, 36, 39 | %IW0 – %IW3 |
| Analog Out | 25, 26 | %QW0 – %QW1 |

esp8266 (node-mcu board)
------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | 4, 5, 6, 7 | %IX0.0 – %IX0.3 |
| Digital Out | 0, 1, 2, 3 | %QX0.0 – %QX0.3 |
| Analog In | A0 | %IW0 – %IW0 |
| Analog Out | 8 | %QW0 – %QW0 |

Machine Control
---------------

|  |  |  |
| --- | --- | --- |
| Digital In | 0, 1, 2, 3, 4, 5, 6, 7 | %IX0.0 – %IX0.7 |
| Digital Out | 0, 1, 2, 3, 4, 5, 6, 7 | %QX0.0 – %QX0.7 |
| Analog In | 0, 1, 2 | %IW0 – %IW2 |
| Analog Out | 0, 1, 2, 3 | %QW0 – %QW3 |

Mega / Due
----------

|  |  |  |
| --- | --- | --- |
| Digital In | A8, A9, A10, A11, A12, A13, A14, A15  22, 24, 26, 28, 30, 32, 34, 36  38, 40, 42, 44, 46, 48, 50, 52 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.7  %IX2.0 – %IX2.7 |
| Digital Out | 14, 15, 16, 17, 18, 19, 20, 21  23, 25, 27, 29, 31, 33, 35, 37  39, 41, 43, 45, 47, 49, 51, 53 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.7  %QX2.0 – %QX2.7 |
| Analog In | A0, A1, A2, A3, A4, A5, A6, A7 | %IW0 – %IW7 |
| Analog Out | 2, 3, 4, 5, 6, 7, 8, 9  10, 11, 12, 13 | %QW0 – %QW7  %QW8 – %QW11 |

MKR Series
----------

|  |  |  |
| --- | --- | --- |
| Digital In | 0, 1, 2, 3, 4, 5 | %IX0.0 – %IX0.5 |
| Digital Out | 7, 8, 9, 10, 11, 12 | %QX0.0 – %QX0.5 |
| Analog In | A1, A2, A3, A4, A5, A6 | %IW0 – %IW5 |
| Analog Out | 6, 15 | %QW0 – %QW1 |

Nano Every
----------

|  |  |  |
| --- | --- | --- |
| Digital In | 2, 3, 4, 5, 6 | %IX0.0 – %IX0.4 |
| Digital Out | 7, 8, 10, 11, 12, 13 | %QX0.0 – %QX0.5 |
| Analog In | A1, A2, A3, A4, A5, A6, A7 | %IW0 – %IW6 |
| Analog Out | 9, 14 | %QW0 – %QW1 |

Productivity Open P1AM-100
--------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | 31, 0, 1, 2, 3, 4 | %IX0.0 – %IX0.5 |
| Digital Out | 32, 6, 7, 11, 12, 13, 14 | %QX0.0 – %QX0.6 |
| Analog In | A1, A2, A5, A6 | %IW0 – %IW3 |
| Analog Out | A0 | %QW0 – %QW0 |

> Notes:
>
> – P1AM modules are addressed using specific P1AM blocks on OpenPLC Editor
>
> – P1AM Toggle Switch (digital pin 31) mapped to %IX0.0
>
> – P1AM LED (digital pin 32) mapped to %QX0.0

RP2040
------

|  |  |  |
| --- | --- | --- |
| Digital In | 2, 3, 4, 5, 6, 7 | %IX0.0 – %IX0.5 |
| Digital Out | 8, 9, 10, 11, 12, 13 | %QX0.0 – %QX0.5 |
| Analog In | A1, A2, A3 | %IW0 – %IW2 |
| Analog Out | 14 | %QW0 – %QW0 |

STM32F103CB (Blue pill)
-----------------------

|  |  |  |
| --- | --- | --- |
| Digital In | PA8, PA11, PA12, PB3, PB4, PB5, PB8, PB9  PB10 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.0 |
| Digital Out | PB11, PB12, PB13, PB14, PB15, PC13, PC14, PC15 | %QX0.0 – %QX0.7 |
| Analog In | PA0, PA1, PA4, PA5, PA6, PA7 | %IW0 – %IW5 |
| Analog Out | PB0, PB1 | %QW0 – %QW1 |

STM32F411CE (Black pill)
------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | PA8, PA11, PA12, PB3, PB4, PB5, PB8, PB9 | %IX0.0 – %IX0.7 |
| Digital Out | PB10, PB12, PB13, PB14, PB15, PC13, PC14, PC15 | %QX0.0 – %QX0.7 |
| Analog In | PA0, PA1, PA4, PA5, PA6, PA7 | %IW0 – %IW5 |
| Analog Out | PB0, PB1 | %QW0 – %QW1 |

Uno, Leonardo, Nano, Micro, Zero
--------------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | 2, 3, 4, 5, 6 | %IX0.0 – %IX0.4 |
| Digital Out | 7, 8, 12, 13 | %QX0.0 – %QX0.3 |
| Analog In | A0, A1, A2, A3, A4, A5 | %IW0 – %IW5 |
| Analog Out | 9, 10, 11 | %QW0 – %QW2 |

Linux-based boards
==================

Neuron PLC
----------

> There isn’t a fixed mapping since Neuron PLCs can be combined with different expansion modules. Mapping is shown on dashboard logs once the Runtime starts and all modules are detected

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201886%20842'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/06/pinout.png)

PiXtend / PiXtend 2L / PiXtend 2S
---------------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | DI0, DI1, DI2, DI3, DI4, DI5, DI6, DI7 | %IX0.0 – %IX0.7 |
| Digital Out | DO0, DO1, DO2, DO3, DO4, DO5, REL0, REL1  REL2, REL3 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.1 |
| Analog In | AI0, AI1, AI2, AI3 | %IW0 – %IW3 |
| Analog Out | AO0, AO1, PWM0, PWM1 | %QW0 – %QW3 |

Raspberry Pi
------------

|  |  |  |
| --- | --- | --- |
| Digital In | 03, 05, 07, 11, 13, 15, 19, 21  23, 29, 31, 33, 35, 37 | %IX0.0 – %IX0.7  %IX1.0 – %IX1.5 |
| Digital Out | 08, 10, 16, 18, 22, 24, 26, 32  36, 38, 40 | %QX0.0 – %QX0.7  %QX1.0 – %QX1.2 |
| Analog In | – | – |
| Analog Out | 12 | %QW0 (PWM) |

UniPi Industrial Platform
-------------------------

|  |  |  |
| --- | --- | --- |
| Digital In | I01, I02, I03, I04, I05, I06, I07  I08, I09, I10, I11, I12, I13, I14 | %IX0.1 – %IX0.7  %IX1.0 – %IX1.6 |
| Digital Out | REL8, REL7, REL6, REL5, REL4, REL3, REL2, REL1 | %QX0.0 – %QX0.7 |
| Analog In | AI1, AI2 | %IW0 – %IW1 |
| Analog Out | AO | %QW0 – %QW0 |

##### What are your Feelings

Updated on 2024-04-12

Leave a Reply [Cancel reply](/docs/2-4-physical-addressing/#respond)
--------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2F2-4-physical-addressing%2F) to post a comment.