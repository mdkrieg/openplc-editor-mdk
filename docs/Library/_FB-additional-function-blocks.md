# Additional Function Blocks

| Version: 1.0.0 | Author: Autonomy Logic |


## RTC

Type: function-block

Extensible: 

The real time clock has many uses including time stamping, setting dates and times of day in batch reports, in alarm messages and so on.

Variables:

| Name | Class | Type | Notes |
    
| IN | input | BOOL | 0 - current time, 1 - load time from PDT |
    
| PDT | input | DT | Preset datetime |
    
| Q | output | BOOL | Copy of IN |
    
| CDT | output | DT | Datetime, current or relative to PDT |
    
| PREV_IN | local | BOOL |  |
    
| OFFSET | local | TIME |  |
    
| CURRENT_TIME | local | DT |  |
    

```
{__SET_VAR(data__->,CURRENT_TIME,,__CURRENT_TIME)}

 IF IN
 THEN
   IF NOT PREV_IN
   THEN
       OFFSET := PDT - CURRENT_TIME;
   END_IF;

   (* PDT + time since PDT was loaded *)
   CDT := CURRENT_TIME + OFFSET;
 ELSE
   CDT := CURRENT_TIME;
 END_IF;

 Q := IN;
 PREV_IN := IN;
```

## INTEGRAL

Type: function-block

Extensible: 

The integral function block integrates the value of input XIN over time.

Variables:

| Name | Class | Type | Notes |
    
| RUN | input | BOOL | 1 = integrate, 0 = hold |
    
| R1 | input | BOOL | Overriding reset |
    
| XIN | input | REAL | Input variable |
    
| X0 | input | REAL | Initial value |
    
| CYCLE | input | TIME | Sampling period |
    
| Q | output | BOOL | NOT R1 |
    
| XOUT | output | REAL | Integrated output |
    

```
Q := NOT R1 ;
IF R1 THEN XOUT := X0;
ELSIF RUN THEN XOUT := XOUT + XIN * TIME_TO_REAL(CYCLE);
END_IF;
```

## DERIVATIVE

Type: function-block

Extensible: 

The derivative function block produces an output XOUT proportional to the rate of change of the input XIN.

Variables:

| Name | Class | Type | Notes |
    
| RUN | input | BOOL | 0 = reset |
    
| XIN | input | REAL | Input to be differentiated |
    
| CYCLE | input | TIME | Sampling period |
    
| XOUT | output | REAL | Differentiated output |
    
| X1 | local | REAL |  |
    
| X2 | local | REAL |  |
    
| X3 | local | REAL |  |
    

```
IF RUN THEN
  XOUT := (3.0 * (XIN - X3) + X1 - X2)
          / (10.0 * TIME_TO_REAL(CYCLE));
  X3 := X2;
  X2 := X1;
  X1 := XIN;
ELSE 
  XOUT := 0.0;
  X1 := XIN;
  X2 := XIN;
  X3 := XIN;
END_IF;
```

## PID

Type: function-block

Extensible: 

The PID (proportional, Integral, Derivative) function block provides the classical three term controller for closed loop control.

Variables:

| Name | Class | Type | Notes |
    
| AUTO | input | BOOL | 0 - manual, 1 - automatic |
    
| PV | input | REAL | Process variable |
    
| SP | input | REAL | Set point |
    
| X0 | input | REAL | Manual output adjustment - Typically from transfer station |
    
| KP | input | REAL | Proportional gain |
    
| TR | input | REAL | Reset time |
    
| TD | input | REAL | Derivative time constant |
    
| CYCLE | input | TIME | Sampling period |
    
| XOUT | output | REAL |  |
    
| ERROR | local | REAL | PV - SP |
    
| ITERM | local | INTEGRAL | FB for integral term |
    
| DTERM | local | DERIVATIVE | FB for derivative term |
    

```
ERROR := PV - SP ;
(*** Adjust ITERM so that XOUT := X0 when AUTO = 0 ***)
ITERM(RUN := AUTO, R1 := NOT AUTO, XIN := ERROR,
      X0 := TR * (X0 - ERROR), CYCLE := CYCLE);
DTERM(RUN := AUTO, XIN := ERROR, CYCLE := CYCLE);
XOUT := KP * (ERROR + ITERM.XOUT/TR + DTERM.XOUT*TD);
```

## RAMP

Type: function-block

Extensible: 

The RAMP function block is modelled on example given in the standard.

Variables:

| Name | Class | Type | Notes |
    
| RUN | input | BOOL | 0 - track X0, 1 - ramp to/track X1 |
    
| X0 | input | REAL |  |
    
| X1 | input | REAL |  |
    
| TR | input | TIME | Ramp duration |
    
| CYCLE | input | TIME | Sampling period |
    
| BUSY | output | BOOL | BUSY = 1 during ramping period |
    
| XOUT | output | REAL |  |
    
| XI | local | REAL | Initial value |
    
| T | local | TIME | Elapsed time of ramp |
    

```
BUSY := RUN ;
IF RUN THEN
  IF T >= TR THEN
    BUSY := 0;
    XOUT := X1;
  ELSE XOUT := XI + (X1-XI) * TIME_TO_REAL(T)
                            / TIME_TO_REAL(TR);
    T := T + CYCLE;
  END_IF;
ELSE
  XOUT := X0;
  XI := X0;
  T := T#0s;
END_IF;
```

## HYSTERESIS

Type: function-block

Extensible: 

The hysteresis function block provides a hysteresis boolean output driven by the difference of two floating point (REAL) inputs XIN1 and XIN2.

Variables:

| Name | Class | Type | Notes |
    
| XIN1 | input | REAL |  |
    
| XIN2 | input | REAL |  |
    
| EPS | input | REAL |  |
    
| Q | output | BOOL |  |
    

```
IF Q THEN
  IF XIN1 < (XIN2 - EPS) THEN
    Q := 0;
  END_IF;
ELSIF XIN1 > (XIN2 + EPS) THEN
  Q := 1;
END_IF;
```
