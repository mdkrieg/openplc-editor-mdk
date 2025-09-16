# Sequent Microsystems Modules

| Version: 1.0.0 | Author: Autonomy Logic |


## SM_8RELAY

Type: function-block

Extensible: 

Update all outputs from 8-relays card

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| 01 | input | BOOL |  |
    
| 02 | input | BOOL |  |
    
| 03 | input | BOOL |  |
    
| 04 | input | BOOL |  |
    
| 05 | input | BOOL |  |
    
| 06 | input | BOOL |  |
    
| 07 | input | BOOL |  |
    
| 08 | input | BOOL |  |
    
| DUMMY | output | SINT |  |
    

```
DUMMY := STACK;
```

## SM_16RELAY

Type: function-block

Extensible: 

Update all outputs from 16-relays card

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| 01 | input | BOOL |  |
    
| 02 | input | BOOL |  |
    
| 03 | input | BOOL |  |
    
| 04 | input | BOOL |  |
    
| 05 | input | BOOL |  |
    
| 06 | input | BOOL |  |
    
| 07 | input | BOOL |  |
    
| 08 | input | BOOL |  |
    
| 09 | input | BOOL |  |
    
| 010 | input | BOOL |  |
    
| 011 | input | BOOL |  |
    
| 012 | input | BOOL |  |
    
| 013 | input | BOOL |  |
    
| 014 | input | BOOL |  |
    
| 015 | input | BOOL |  |
    
| 016 | input | BOOL |  |
    
| DUMMY | output | SINT |  |
    

```
DUMMY := STACK;
```

## SM_8DIN

Type: function-block

Extensible: 

Get all inputs from Sequent microsystems 8 HV Inputs modules

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| I1 | output | BOOL |  |
    
| I2 | output | BOOL |  |
    
| I3 | output | BOOL |  |
    
| I4 | output | BOOL |  |
    
| I5 | output | BOOL |  |
    
| I6 | output | BOOL |  |
    
| I7 | output | BOOL |  |
    
| I8 | output | BOOL |  |
    

```
I1 := 0;
```

## SM_16DIN

Type: function-block

Extensible: 

Get all inputs from Sequent microsystems 16 digital inputs modules.

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| I1 | output | BOOL |  |
    
| I2 | output | BOOL |  |
    
| I3 | output | BOOL |  |
    
| I4 | output | BOOL |  |
    
| I5 | output | BOOL |  |
    
| I6 | output | BOOL |  |
    
| I7 | output | BOOL |  |
    
| I8 | output | BOOL |  |
    
| I9 | output | BOOL |  |
    
| I10 | output | BOOL |  |
    
| I11 | output | BOOL |  |
    
| I12 | output | BOOL |  |
    
| I13 | output | BOOL |  |
    
| I14 | output | BOOL |  |
    
| I15 | output | BOOL |  |
    
| I16 | output | BOOL |  |
    

```
I1 := 0;
```

## SM_4REL4IN

Type: function-block

Extensible: 

Get all inputs from and set all outputs to SM_4REL4IN modules

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| RELAY1 | input | BOOL |  |
    
| RELAY2 | input | BOOL |  |
    
| RELAY3 | input | BOOL |  |
    
| RELAY4 | input | BOOL |  |
    
| OPTO1 | output | BOOL |  |
    
| OPTO2 | output | BOOL |  |
    
| OPTO3 | output | BOOL |  |
    
| OPTO4 | output | BOOL |  |
    
| AC_OPTO1 | output | BOOL |  |
    
| AC_OPTO2 | output | BOOL |  |
    
| AC_OPTO3 | output | BOOL |  |
    
| AC_OPTO4 | output | BOOL |  |
    
| PWM1 | output | REAL |  |
    
| PWM2 | output | REAL |  |
    
| PWM3 | output | REAL |  |
    
| PWM4 | output | REAL |  |
    
| FREQ1 | output | UINT |  |
    
| FREQ2 | output | UINT |  |
    
| FREQ3 | output | UINT |  |
    
| FREQ4 | output | UINT |  |
    
| BUTTON | output | BOOL |  |
    

```
OPTO1 := 0;
```

## SM_INDUSTRIAL

Type: function-block

Extensible: 

Get all input and set all outputs of a Sequent Microsystems Industrial Automation card.

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| LED1 | input | BOOL |  |
    
| LED2 | input | BOOL |  |
    
| LED3 | input | BOOL |  |
    
| LED4 | input | BOOL |  |
    
| Q0_10V1 | input | REAL |  |
    
| Q0_10V2 | input | REAL |  |
    
| Q0_10V3 | input | REAL |  |
    
| Q0_10V4 | input | REAL |  |
    
| Q4_20MA1 | input | REAL |  |
    
| Q4_20MA2 | input | REAL |  |
    
| Q4_20MA3 | input | REAL |  |
    
| Q4_20MA4 | input | REAL |  |
    
| QOD1 | input | REAL |  |
    
| QOD2 | input | REAL |  |
    
| QOD3 | input | REAL |  |
    
| QOD4 | input | REAL |  |
    
| OPTO1 | output | BOOL |  |
    
| OPTO2 | output | BOOL |  |
    
| OPTO3 | output | BOOL |  |
    
| OPTO4 | output | BOOL |  |
    
| I0_10V1 | output | REAL |  |
    
| I0_10V2 | output | REAL |  |
    
| I0_10V3 | output | REAL |  |
    
| I0_10V4 | output | REAL |  |
    
| I4_20MA1 | output | REAL |  |
    
| I4_20MA2 | output | REAL |  |
    
| I4_20MA3 | output | REAL |  |
    
| I4_20MA4 | output | REAL |  |
    
| OWB_T1 | output | REAL |  |
    
| OWB_T2 | output | REAL |  |
    
| OWB_T3 | output | REAL |  |
    
| OWB_T4 | output | REAL |  |
    

```
OPTO1 := 0;
```

## SM_RTD

Type: function-block

Extensible: 

Get all temperature inputs from SM_RTD modules as REAL values in deg Celsius

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| TEMP1 | output | REAL |  |
    
| TEMP2 | output | REAL |  |
    
| TEMP3 | output | REAL |  |
    
| TEMP4 | output | REAL |  |
    
| TEMP5 | output | REAL |  |
    
| TEMP6 | output | REAL |  |
    
| TEMP7 | output | REAL |  |
    
| TEMP8 | output | REAL |  |
    

```
TEMP1 := 0.0;
```

## SM_BAS

Type: function-block

Extensible: 

Get all input and set all outputs of a Sequent Microsystems Building Automation card.

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| TRIAC1 | input | BOOL |  |
    
| TRIAC2 | input | BOOL |  |
    
| TRIAC3 | input | BOOL |  |
    
| TRIAC4 | input | BOOL |  |
    
| LED1 | input | BOOL |  |
    
| LED2 | input | BOOL |  |
    
| LED3 | input | BOOL |  |
    
| LED4 | input | BOOL |  |
    
| IN1_T | input | UINT |  |
    
| IN2_T | input | UINT |  |
    
| IN3_T | input | UINT |  |
    
| IN4_T | input | UINT |  |
    
| IN5_T | input | UINT |  |
    
| IN6_T | input | UINT |  |
    
| IN7_T | input | UINT |  |
    
| IN8_T | input | UINT |  |
    
| Q0_10V1 | input | REAL |  |
    
| Q0_10V2 | input | REAL |  |
    
| Q0_10V3 | input | REAL |  |
    
| Q0_10V4 | input | REAL |  |
    
| UNIV1 | output | REAL |  |
    
| UNIV2 | output | REAL |  |
    
| UNIV3 | output | REAL |  |
    
| UNIV4 | output | REAL |  |
    
| UNIV5 | output | REAL |  |
    
| UNIV6 | output | REAL |  |
    
| UNIV7 | output | REAL |  |
    
| UNIV8 | output | REAL |  |
    
| DRY_C1 | output | BOOL |  |
    
| DRY_C2 | output | BOOL |  |
    
| DRY_C3 | output | BOOL |  |
    
| DRY_C4 | output | BOOL |  |
    
| DRY_C5 | output | BOOL |  |
    
| DRY_C6 | output | BOOL |  |
    
| DRY_C7 | output | BOOL |  |
    
| DRY_C8 | output | BOOL |  |
    
| OWB_T1 | output | REAL |  |
    
| OWB_T2 | output | REAL |  |
    
| OWB_T3 | output | REAL |  |
    
| OWB_T4 | output | REAL |  |
    

```
DRY_C1 := 0;
```

## SM_HOME

Type: function-block

Extensible: 

Get all inputs and set all outputs of a Sequent Microsystems Home Automation card.

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| RELAY1 | input | BOOL |  |
    
| RELAY2 | input | BOOL |  |
    
| RELAY3 | input | BOOL |  |
    
| RELAY4 | input | BOOL |  |
    
| RELAY5 | input | BOOL |  |
    
| RELAY6 | input | BOOL |  |
    
| RELAY7 | input | BOOL |  |
    
| RELAY8 | input | BOOL |  |
    
| Q0_10V1 | input | REAL |  |
    
| Q0_10V2 | input | REAL |  |
    
| Q0_10V3 | input | REAL |  |
    
| Q0_10V4 | input | REAL |  |
    
| QOD1 | input | REAL |  |
    
| QOD2 | input | REAL |  |
    
| QOD3 | input | REAL |  |
    
| QOD4 | input | REAL |  |
    
| OPTO1 | output | BOOL |  |
    
| OPTO2 | output | BOOL |  |
    
| OPTO3 | output | BOOL |  |
    
| OPTO4 | output | BOOL |  |
    
| OPTO5 | output | BOOL |  |
    
| OPTO6 | output | BOOL |  |
    
| OPTO7 | output | BOOL |  |
    
| OPTO8 | output | BOOL |  |
    
| ADC1 | output | REAL |  |
    
| ADC2 | output | REAL |  |
    
| ADC3 | output | REAL |  |
    
| ADC4 | output | REAL |  |
    
| ADC5 | output | REAL |  |
    
| ADC6 | output | REAL |  |
    
| ADC7 | output | REAL |  |
    
| ADC8 | output | REAL |  |
    
| OWB_T1 | output | REAL |  |
    
| OWB_T2 | output | REAL |  |
    
| OWB_T3 | output | REAL |  |
    
| OWB_T4 | output | REAL |  |
    

```
OPTO1 := 0;
```

## SM_8MOSFET

Type: function-block

Extensible: 

Update all outputs from 8-mosfets card

Variables:

| Name | Class | Type | Notes |
    
| STACK | input | SINT |  |
    
| MOS1 | input | BOOL |  |
    
| MOS2 | input | BOOL |  |
    
| MOS3 | input | BOOL |  |
    
| MOS4 | input | BOOL |  |
    
| MOS5 | input | BOOL |  |
    
| MOS6 | input | BOOL |  |
    
| MOS7 | input | BOOL |  |
    
| MOS8 | input | BOOL |  |
    
| DUMMY | local | SINT |  |
    

```
DUMMY := STACK;
```
