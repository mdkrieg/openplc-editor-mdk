# Jaguar

| Version: 1.0.0 | Author: Autonomy Logic |


## ADC_CONFIG

Type: function-block

Extensible: 

Configures the analog channel inputs on the Jaguar board. ADC_CH must be between 0 - 3. ADC_TYPE must be between 0 - 3, where 0 = unipolar 10V, 1 = bipolar 10V, 2 = unipolar 5V, and 3 = bipolar 5V. Upon successful configuration of the ADC, SUCCESS is set to TRUE.

Variables:

| Name | Class | Type | Notes |
    
| ADC_CH | input | INT | ADC_CH |
    
| ADC_TYPE | input | INT | ADC_TYPE |
    
| ADC_CH_LOCAL | local | SINT | ADC_CH_LOCAL |
    
| ADC_TYPE_LOCAL | local | SINT | ADC_TYPE_LOCAL |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
IF ADC_CH <> ADC_CH_LOCAL OR ADC_TYPE <> ADC_TYPE_LOCAL THEN
    ADC_CH_LOCAL := ADC_CH;
    ADC_TYPE_LOCAL := ADC_TYPE;
    SUCCESS := TRUE;
  ELSE
    SUCCESS := FALSE;
  END_IF;
```
