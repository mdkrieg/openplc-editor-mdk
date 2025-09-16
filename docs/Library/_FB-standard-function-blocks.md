# Standard Function Blocks

| Version: 1.0.0 | Author: Autonomy Logic |


## SR

Type: function-block

Extensible: 

The SR bistable is a latch where the Set dominates.

Variables:

| Name | Class | Type | Notes |
    
| S1 | input | BOOL |  |
    
| R | input | BOOL |  |
    
| Q1 | output | BOOL |  |
    

```
Q1 := S1 OR ((NOT R) AND Q1);
```

## RS

Type: function-block

Extensible: 

The RS bistable is a latch where the Reset dominates.

Variables:

| Name | Class | Type | Notes |
    
| S | input | BOOL |  |
    
| R1 | input | BOOL |  |
    
| Q1 | output | BOOL |  |
    

```
Q1 := (NOT R1) AND (S OR Q1);
```

## SEMA

Type: function-block

Extensible: 

The semaphore provides a mechanism to allow software elements mutually exclusive access to certain resources.

Variables:

| Name | Class | Type | Notes |
    
| CLAIM | input | BOOL |  |
    
| RELEASE | input | BOOL |  |
    
| BUSY | output | BOOL |  |
    
| Q_INTERNAL | local | BOOL |  |
    

```
Q_INTERNAL := CLAIM OR ( Q_INTERNAL AND (NOT RELEASE));BUSY := Q_INTERNAL; 
```

## R_TRIG

Type: function-block

Extensible: 

The output produces a single pulse when a rising edge is detected.

Variables:

| Name | Class | Type | Notes |
    
| CLK | input | BOOL |  |
    
| Q | output | BOOL |  |
    
| M | local | BOOL |  |
    

```
Q := CLK AND NOT M; M := CLK;
```

## F_TRIG

Type: function-block

Extensible: 

The output produces a single pulse when a falling edge is detected.

Variables:

| Name | Class | Type | Notes |
    
| CLK | input | BOOL |  |
    
| Q | output | BOOL |  |
    
| M | local | BOOL |  |
    

```
Q := NOT CLK AND NOT M; M := NOT CLK;
```

## CTU

Type: function-block

Extensible: 

The up-counter can be used to signal when a count has reached a maximum value.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| R | input | BOOL |  |
    
| PV | input | INT |  |
    
| Q | output | BOOL |  |
    
| CV | output | INT |  |
    
| CU_T | local | R_TRIG |  |
    

```
CU_T(CU);
        IF R THEN CV := 0;
        ELSIF CU_T.Q AND (CV < PV) THEN CV := CV+1;
        END_IF;
        Q := (CV >= PV);
```

## CTU_DINT

Type: function-block

Extensible: 

The up-counter can be used to signal when a count has reached a maximum value.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| R | input | BOOL |  |
    
| PV | input | DINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | DINT |  |
    
| CU_T | local | R_TRIG |  |
    

```
CU_T(CU);
        IF R THEN CV := 0;
        ELSIF CU_T.Q AND (CV < PV) THEN CV := CV+1;
        END_IF;
        Q := (CV >= PV);
```

## CTU_LINT

Type: function-block

Extensible: 

The up-counter can be used to signal when a count has reached a maximum value.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| R | input | BOOL |  |
    
| PV | input | LINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | LINT |  |
    
| CU_T | local | R_TRIG |  |
    

```
CU_T(CU);
        IF R THEN CV := 0;
        ELSIF CU_T.Q AND (CV < PV) THEN CV := CV+1;
        END_IF;
        Q := (CV >= PV);
```

## CTU_UDINT

Type: function-block

Extensible: 

The up-counter can be used to signal when a count has reached a maximum value.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| R | input | BOOL |  |
    
| PV | input | UDINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | UDINT |  |
    
| CU_T | local | R_TRIG |  |
    

```
CU_T(CU);
        IF R THEN CV := 0;
        ELSIF CU_T.Q AND (CV < PV) THEN CV := CV+1;
        END_IF;
        Q := (CV >= PV);
```

## CTU_ULINT

Type: function-block

Extensible: 

The up-counter can be used to signal when a count has reached a maximum value.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| R | input | BOOL |  |
    
| PV | input | ULINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | ULINT |  |
    
| CU_T | local | R_TRIG |  |
    

```
CU_T(CU);
        IF R THEN CV := 0;
        ELSIF CU_T.Q AND (CV < PV) THEN CV := CV+1;
        END_IF;
        Q := (CV >= PV);
```

## CTD

Type: function-block

Extensible: 

The down-counter can be used to signal when a count has reached zero, on counting down from a preset value.

Variables:

| Name | Class | Type | Notes |
    
| CD | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | INT |  |
    
| Q | output | BOOL |  |
    
| CV | output | INT |  |
    
| CD_T | local | R_TRIG |  |
    

```
CD_T(CD);
        IF LD THEN CV := PV;
        ELSIF CD_T.Q AND (CV > 0) THEN CV := CV-1;
        END_IF;
        Q := (CV <= 0);
```

## CTD_DINT

Type: function-block

Extensible: 

The down-counter can be used to signal when a count has reached zero, on counting down from a preset value.

Variables:

| Name | Class | Type | Notes |
    
| CD | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | DINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | DINT |  |
    
| CD_T | local | R_TRIG |  |
    

```
CD_T(CD);
        IF LD THEN CV := PV;
        ELSIF CD_T.Q AND (CV > 0) THEN CV := CV-1;
        END_IF;
        Q := (CV <= 0);
```

## CTD_LINT

Type: function-block

Extensible: 

The down-counter can be used to signal when a count has reached zero, on counting down from a preset value.

Variables:

| Name | Class | Type | Notes |
    
| CD | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | LINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | LINT |  |
    
| CD_T | local | R_TRIG |  |
    

```
CD_T(CD);
        IF LD THEN CV := PV;
        ELSIF CD_T.Q AND (CV > 0) THEN CV := CV-1;
        END_IF;
        Q := (CV <= 0);
```

## CTD_UDINT

Type: function-block

Extensible: 

The down-counter can be used to signal when a count has reached zero, on counting down from a preset value.

Variables:

| Name | Class | Type | Notes |
    
| CD | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | UDINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | UDINT |  |
    
| CD_T | local | R_TRIG |  |
    

```
CD_T(CD);
        IF LD THEN CV := PV;
        ELSIF CD_T.Q AND (CV > 0) THEN CV := CV-1;
        END_IF;
        Q := (CV <= 0);
```

## CTD_ULINT

Type: function-block

Extensible: 

The down-counter can be used to signal when a count has reached zero, on counting down from a preset value.

Variables:

| Name | Class | Type | Notes |
    
| CD | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | ULINT |  |
    
| Q | output | BOOL |  |
    
| CV | output | ULINT |  |
    
| CD_T | local | R_TRIG |  |
    

```
CD_T(CD);
        IF LD THEN CV := PV;
        ELSIF CD_T.Q AND (CV > 0) THEN CV := CV-1;
        END_IF;
        Q := (CV <= 0);
```

## CTUD

Type: function-block

Extensible: 

The up-down counter has two inputs CU and CD. It can be used to both count up on one input and down on the other.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| CD | input | BOOL |  |
    
| R | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | INT |  |
    
| QU | output | BOOL |  |
    
| QD | output | BOOL |  |
    
| CV | output | INT |  |
    
| CD_T | output | R_TRIG |  |
    
| CU_T | output | R_TRIG |  |
    

```
CD_T(CD);
        CU_T(CU);
        IF R THEN CV := 0;
        ELSIF LD THEN CV := PV;
        ELSE
          IF NOT (CU_T.Q AND CD_T.Q) THEN
            IF CU_T.Q AND (CV < PV)
            THEN CV := CV+1;
            ELSIF CD_T.Q AND (CV > 0)
            THEN CV := CV-1;
            END_IF;
          END_IF;
        END_IF;
        QU := (CV >= PV);
        QD := (CV <= 0);
```

## CTUD_DINT

Type: function-block

Extensible: 

The up-down counter has two inputs CU and CD. It can be used to both count up on one input and down on the other.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| CD | input | BOOL |  |
    
| R | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | DINT |  |
    
| QU | output | BOOL |  |
    
| QD | output | BOOL |  |
    
| CV | output | DINT |  |
    
| CD_T | output | R_TRIG |  |
    
| CU_T | output | R_TRIG |  |
    

```
CD_T(CD);
        CU_T(CU);
        IF R THEN CV := 0;
        ELSIF LD THEN CV := PV;
        ELSE
          IF NOT (CU_T.Q AND CD_T.Q) THEN
            IF CU_T.Q AND (CV < PV)
            THEN CV := CV+1;
            ELSIF CD_T.Q AND (CV > 0)
            THEN CV := CV-1;
            END_IF;
          END_IF;
        END_IF;
        QU := (CV >= PV);
        QD := (CV <= 0);
```

## CTUD_LINT

Type: function-block

Extensible: 

The up-down counter has two inputs CU and CD. It can be used to both count up on one input and down on the other.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| CD | input | BOOL |  |
    
| R | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | LINT |  |
    
| QU | output | BOOL |  |
    
| QD | output | BOOL |  |
    
| CV | output | LINT |  |
    
| CD_T | output | R_TRIG |  |
    
| CU_T | output | R_TRIG |  |
    

```
CD_T(CD);
        CU_T(CU);
        IF R THEN CV := 0;
        ELSIF LD THEN CV := PV;
        ELSE
          IF NOT (CU_T.Q AND CD_T.Q) THEN
            IF CU_T.Q AND (CV < PV)
            THEN CV := CV+1;
            ELSIF CD_T.Q AND (CV > 0)
            THEN CV := CV-1;
            END_IF;
          END_IF;
        END_IF;
        QU := (CV >= PV);
        QD := (CV <= 0);
```

## CTUD_UDINT

Type: function-block

Extensible: 

The up-down counter has two inputs CU and CD. It can be used to both count up on one input and down on the other.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| CD | input | BOOL |  |
    
| R | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | UDINT |  |
    
| QU | output | BOOL |  |
    
| QD | output | BOOL |  |
    
| CV | output | UDINT |  |
    
| CD_T | output | R_TRIG |  |
    
| CU_T | output | R_TRIG |  |
    

```
CD_T(CD);
        CU_T(CU);
        IF R THEN CV := 0;
        ELSIF LD THEN CV := PV;
        ELSE
          IF NOT (CU_T.Q AND CD_T.Q) THEN
            IF CU_T.Q AND (CV < PV)
            THEN CV := CV+1;
            ELSIF CD_T.Q AND (CV > 0)
            THEN CV := CV-1;
            END_IF;
          END_IF;
        END_IF;
        QU := (CV >= PV);
        QD := (CV <= 0);
```

## CTUD_ULINT

Type: function-block

Extensible: 

The up-down counter has two inputs CU and CD. It can be used to both count up on one input and down on the other.

Variables:

| Name | Class | Type | Notes |
    
| CU | input | BOOL |  |
    
| CD | input | BOOL |  |
    
| R | input | BOOL |  |
    
| LD | input | BOOL |  |
    
| PV | input | ULINT |  |
    
| QU | output | BOOL |  |
    
| QD | output | BOOL |  |
    
| CV | output | ULINT |  |
    
| CD_T | output | R_TRIG |  |
    
| CU_T | output | R_TRIG |  |
    

```
CD_T(CD);
        CU_T(CU);
        IF R THEN CV := 0;
        ELSIF LD THEN CV := PV;
        ELSE
          IF NOT (CU_T.Q AND CD_T.Q) THEN
            IF CU_T.Q AND (CV < PV)
            THEN CV := CV+1;
            ELSIF CD_T.Q AND (CV > 0)
            THEN CV := CV-1;
            END_IF;
          END_IF;
        END_IF;
        QU := (CV >= PV);
        QD := (CV <= 0);
```

## TP

Type: function-block

Extensible: 

The pulse timer can be used to generate output pulses of a given time duration.

Variables:

| Name | Class | Type | Notes |
    
| IN | input | BOOL | first input parameter |
    
| PT | input | TIME | second input parameter |
    
| Q | output | BOOL | first output parameter |
    
| ET | output | TIME | second output parameter |
    
| STATE | local | SINT | internal state: 0-reset, 1-counting, 2-set |
    
| PREV_IN | local | BOOL |  |
    
| CURRENT_TIME | local | TIME |  |
    
| START_TIME | local | TIME |  |
    

```
{__SET_VAR(data__->,CURRENT_TIME,,__CURRENT_TIME)}

        IF ((STATE = 0) AND NOT(PREV_IN) AND IN)   (* found rising edge on IN *)
        THEN
          (* start timer... *)
          STATE := 1;
          Q := TRUE;
          START_TIME := CURRENT_TIME;

        ELSIF (STATE = 1)
        THEN
          IF ((START_TIME + PT) <= CURRENT_TIME)
          THEN
            STATE := 2;
            Q := FALSE;
            ET := PT;
          ELSE
            ET := CURRENT_TIME - START_TIME;
          END_IF;
        END_IF;

        IF ((STATE = 2) AND NOT(IN))
        THEN
          ET := T#0s;
          STATE := 0;
        END_IF;

        PREV_IN := IN;
```

## TON

Type: function-block

Extensible: 

The on-delay timer can be used to delay setting an output true, for fixed period after an input becomes true.

Variables:

| Name | Class | Type | Notes |
    
| IN | input | BOOL | first input parameter |
    
| PT | input | TIME | second input parameter |
    
| Q | output | BOOL | first output parameter |
    
| ET | output | TIME | second output parameter |
    
| STATE | local | SINT | internal state: 0-reset, 1-counting, 2-set |
    
| PREV_IN | local | BOOL |  |
    
| CURRENT_TIME | local | TIME |  |
    
| START_TIME | local | TIME |  |
    

```
{__SET_VAR(data__->,CURRENT_TIME,,__CURRENT_TIME)}

      IF ((STATE = 0) AND NOT(PREV_IN) AND IN)   (* found rising edge on IN *)
      THEN
        (* start timer... *)
        STATE := 1;
        Q := TRUE;
        START_TIME := CURRENT_TIME;

      ELSE
        (* STATE is 1 or 2 !! *)
        IF (NOT(IN))
        THEN
          ET := T#0s;
          Q := FALSE;
          STATE := 0;

        ELSIF (STATE = 1)
        THEN
          IF ((START_TIME + PT) <= CURRENT_TIME)
          THEN
            STATE := 2;
            Q := TRUE;
            ET := PT;
          ELSE
            ET := CURRENT_TIME - START_TIME;
          END_IF;
        END_IF;

      END_IF;

      PREV_IN := IN;
```

## TOF

Type: function-block

Extensible: 

The off-delay timer can be used to delay setting an output false, for fixed period after input goes false.

Variables:

| Name | Class | Type | Notes |
    
| IN | input | BOOL | first input parameter |
    
| PT | input | TIME | second input parameter |
    
| Q | output | BOOL | first output parameter |
    
| ET | output | TIME | second output parameter |
    
| STATE | local | SINT | internal state: 0-reset, 1-counting, 2-set |
    
| PREV_IN | local | BOOL |  |
    
| CURRENT_TIME | local | TIME |  |
    
| START_TIME | local | TIME |  |
    

```
{__SET_VAR(data__->,CURRENT_TIME,,__CURRENT_TIME)}

      IF ((STATE = 0) AND PREV_IN AND NOT(IN))   (* found falling edge on IN *)
      THEN
        (* start timer... *)
        STATE := 1;
        START_TIME := CURRENT_TIME;

      ELSE
        (* STATE is 1 or 2 !! *)
        IF (IN)
        THEN
          ET := T#0s;
          STATE := 0;

        ELSIF (STATE = 1)
        THEN
          IF ((START_TIME + PT) <= CURRENT_TIME)
          THEN
            STATE := 2;
            ET := PT;
          ELSE
            ET := CURRENT_TIME - START_TIME;
          END_IF;
        END_IF;

      END_IF;

      Q := IN OR (STATE = 1);
      PREV_IN := IN;
```
