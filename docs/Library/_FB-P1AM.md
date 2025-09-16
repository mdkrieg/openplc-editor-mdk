# P1AM

| Version: 1.0.0 | Author: Autonomy Logic |


## P1AM_INIT

Type: function-block

Extensible: 

Initialize P1AM Modules and return the number of initialized modules on SUCCESS. If SUCCESS is zero, an error has occurred, or there aren't any modules on the bus

Variables:

| Name | Class | Type | Notes |
    
| INIT | input | BOOL |  |
    
| SUCCESS | output | SINT |  |
    

```
SUCCESS := 0;
```

## P1_16CDR

Type: function-block

Extensible: 

Get all inputs and update all outputs from P1-16CDR module. Also works with P1-15CDD1 and P1-15CDD2

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
| O1 | input | BOOL |  |
    
| O2 | input | BOOL |  |
    
| O3 | input | BOOL |  |
    
| O4 | input | BOOL |  |
    
| O5 | input | BOOL |  |
    
| O6 | input | BOOL |  |
    
| O7 | input | BOOL |  |
    
| O8 | input | BOOL |  |
    
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

## P1_08N

Type: function-block

Extensible: 

Get all inputs from P1-08Nxx modules. Compatible with P1-08NA, P1-08ND3, P1-08NE3 and P1-08SIM

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
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

## P1_16N

Type: function-block

Extensible: 

Get all inputs from P1-16Nxx modules. Compatible with P1-16ND3 and P1-16NE3

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
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

## P1_08T

Type: function-block

Extensible: 

Set all outputs on P1-08Txx modules. Compatible with P1-08TA, P1-08TD1, P1-08TD2 and P1-08TRS

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
| O1 | input | BOOL |  |
    
| O2 | input | BOOL |  |
    
| O3 | input | BOOL |  |
    
| O4 | input | BOOL |  |
    
| O5 | input | BOOL |  |
    
| O6 | input | BOOL |  |
    
| O7 | input | BOOL |  |
    
| O8 | input | BOOL |  |
    
| DUMMY | local | SINT |  |
    

```
DUMMY := SLOT;
```

## P1_16TR

Type: function-block

Extensible: 

Set all outputs on P1-16TR modules. Also compatible with P1-15TD1 and P1-15TD2

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
| O1 | input | BOOL |  |
    
| O2 | input | BOOL |  |
    
| O3 | input | BOOL |  |
    
| O4 | input | BOOL |  |
    
| O5 | input | BOOL |  |
    
| O6 | input | BOOL |  |
    
| O7 | input | BOOL |  |
    
| O8 | input | BOOL |  |
    
| O9 | input | BOOL |  |
    
| O10 | input | BOOL |  |
    
| O11 | input | BOOL |  |
    
| O12 | input | BOOL |  |
    
| O13 | input | BOOL |  |
    
| O14 | input | BOOL |  |
    
| O15 | input | BOOL |  |
    
| O16 | input | BOOL |  |
    
| DUMMY | local | SINT |  |
    

```
DUMMY := SLOT;
```

## P1_04AD

Type: function-block

Extensible: 

Get all analog inputs from P1-04ADxx modules. Compatible with P1-04AD, P1-04ADL-1 and P1-04ADL-2

Variables:

| Name | Class | Type | Notes |
    
| SLOT | input | SINT |  |
    
| I1 | output | UINT |  |
    
| I2 | output | UINT |  |
    
| I3 | output | UINT |  |
    
| I4 | output | UINT |  |
    
| DUMMY | local | SINT |  |
    

```
DUMMY := SLOT;
```
