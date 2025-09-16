# Arduino Function Blocks

| Version: 1.0.0 | Author: Autonomy Logic |


## DS18B20

Type: function-block

Extensible: 

Reads temperature from one DS18B20 one-wire sensor connected to the pin specified in PIN

Variables:

| Name | Class | Type | Notes |
    
| PIN | input | SINT | Arduino pin where sensor is connected to |
    
| OUT | output | REAL | Temperature output in Celsius |
    

```
OUT := 0.0;
```

## DS18B20_2_OUT

Type: function-block

Extensible: 

Reads temperature from two DS18B20 one-wire sensors. Both sensors must be on the same bus connected to the pin specified in PIN

Variables:

| Name | Class | Type | Notes |
    
| PIN | input | SINT | Arduino pin where sensor is connected to |
    
| OUT_0 | output | REAL | Temperature output in Celsius |
    
| OUT_1 | output | REAL | Temperature output in Celsius |
    

```
OUT := 0.0;
```

## DS18B20_3_OUT

Type: function-block

Extensible: 

Reads temperature from three DS18B20 one-wire sensors. All sensors must be on the same bus connected to the pin specified in PIN

Variables:

| Name | Class | Type | Notes |
    
| PIN | input | SINT | Arduino pin where sensor is connected to |
    
| OUT_0 | output | REAL | Temperature output in Celsius |
    
| OUT_1 | output | REAL | Temperature output in Celsius |
    
| OUT_2 | output | REAL | Temperature output in Celsius |
    

```
OUT := 0.0;
```

## DS18B20_4_OUT

Type: function-block

Extensible: 

Reads temperature from four DS18B20 one-wire sensors. All sensors must be on the same bus connected to the pin specified in PIN

Variables:

| Name | Class | Type | Notes |
    
| PIN | input | SINT | Arduino pin where sensor is connected to |
    
| OUT_0 | output | REAL | Temperature output in Celsius |
    
| OUT_1 | output | REAL | Temperature output in Celsius |
    
| OUT_2 | output | REAL | Temperature output in Celsius |
    
| OUT_3 | output | REAL | Temperature output in Celsius |
    

```
OUT := 0.0;
```

## DS18B20_5_OUT

Type: function-block

Extensible: 

Reads temperature from five DS18B20 one-wire sensors. All sensors must be on the same bus connected to the pin specified in PIN

Variables:

| Name | Class | Type | Notes |
    
| PIN | input | SINT | Arduino pin where sensor is connected to |
    
| OUT_0 | output | REAL | Temperature output in Celsius |
    
| OUT_1 | output | REAL | Temperature output in Celsius |
    
| OUT_2 | output | REAL | Temperature output in Celsius |
    
| OUT_3 | output | REAL | Temperature output in Celsius |
    
| OUT_4 | output | REAL | Temperature output in Celsius |
    

```
OUT := 0.0;
```

## CLOUD_ADD_BOOL

Type: function-block

Extensible: 

Add a BOOL variable to sync with the Arduino Cloud. VAR_NAME must have the same name as the variable set up in the Arduino IoT Cloud

Variables:

| Name | Class | Type | Notes |
    
| VAR_NAME | input | STRING |  |
    
| BOOL_VAR | input | BOOL |  |
    

```
SSID := SSID;
```

## CLOUD_ADD_DINT

Type: function-block

Extensible: 

Add an DINT variable (Arduino int) to sync with the Arduino Cloud. VAR_NAME must have the same name as the variable set up in the Arduino IoT Cloud

Variables:

| Name | Class | Type | Notes |
    
| VAR_NAME | input | STRING |  |
    
| DINT_VAR | input | DINT |  |
    

```
SSID := SSID;
```

## CLOUD_ADD_REAL

Type: function-block

Extensible: 

Add a REAL variable (Arduino float) to sync with the Arduino Cloud. VAR_NAME must have the same name as the variable set up in the Arduino IoT Cloud

Variables:

| Name | Class | Type | Notes |
    
| VAR_NAME | input | STRING |  |
    
| REAL_VAR | input | REAL |  |
    

```
SSID := SSID;
```

## CLOUD_BEGIN

Type: function-block

Extensible: 

Setup and initialize Arduino Cloud communication. Must be called before adding any variables (properties).

Variables:

| Name | Class | Type | Notes |
    
| THING_ID | input | STRING |  |
    
| SSID | input | STRING |  |
    
| PASS | input | STRING |  |
    

```
SSID := SSID;
```

## PWM_CONTROLLER

Type: function-block

Extensible: 

Configures the CPU internal PWM peripheral to generate a PWM signal through hardware. If the CPU does not have a PWM peripheral, compiling this block will result in a compilation error. CHANNEL is the PWM channel number. For most Arduino boards that number is the pin number for the PWM capable pin. FREQ is the desired PWM frequency in Hz. DUTY is the PWM duty cycle (between 0 and 100).

Variables:

| Name | Class | Type | Notes |
    
| CHANNEL | input | SINT | CHANNEL |
    
| FREQ | input | REAL | FREQ |
    
| DUTY | input | REAL | DUTY |
    
| internal_ch | local | SINT | internal_ch |
    
| internal_freq | local | REAL | internal_freq |
    
| internal_duty | local | REAL | internal_duty |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```

          IF CHANNEL < 1 THEN
            SUCCESS := FALSE;
            RETURN;
          END_IF;


          IF (CHANNEL <> internal_ch) OR (FREQ <> internal_freq) OR (DUTY <> internal_duty) THEN
            SUCCESS := TRUE;
          END_IF;
        
```

## ARDUINOCAN_CONF

Type: function-block

Extensible: 

Configure Arduino CAN communication

Variables:

| Name | Class | Type | Notes |
    
| EN_PIN | input | WORD | Arduino CAN Enable pin |
    
| BR | input | LINT | Arduino CAN Baudrate |
    
| DONE | output | BOOL | Arduino CAN configuration Done flag |
    

```
DONE := FALSE;
```

## ARDUINOCAN_WRITE

Type: function-block

Extensible: 

Write data to Arduino CAN bus

Variables:

| Name | Class | Type | Notes |
    
| ID | input | DWORD | Arduino CAN message ID |
    
| D0 | input | USINT | Arduino CAN first payload byte |
    
| D1 | input | USINT | Arduino CAN second payload byte |
    
| D2 | input | USINT | Arduino CAN third payload byte |
    
| D3 | input | USINT | Arduino CAN fourth payload byte |
    
| D4 | input | USINT | Arduino CAN fifth payload byte |
    
| D5 | input | USINT | Arduino CAN sixth payload byte |
    
| D6 | input | USINT | Arduino CAN seventh payload byte |
    
| D7 | input | USINT | Arduino CAN eighth payload byte |
    
| DONE | output | BOOL | Arduino CAN write done flag |
    

```
DONE := FALSE;
```

## ARDUINOCAN_WRITE_WORD

Type: function-block

Extensible: 

Write word data to Arduino CAN bus

Variables:

| Name | Class | Type | Notes |
    
| ID | input | DWORD | Arduino CAN message ID |
    
| DATA | input | LWORD | Arduino CAN payload |
    
| DONE | output | BOOL | Arduino CAN write done flag |
    

```
DONE := FALSE;
```

## ARDUINOCAN_READ

Type: function-block

Extensible: 

CAN READ

Variables:

| Name | Class | Type | Notes |
    
| DATA | output | LWORD | Arduino CAN readed data from arduino can message |
    

```
DATA := 0;
```
