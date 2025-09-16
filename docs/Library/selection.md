# Selection

| Version: 1.0.0 | Author: Autonomy Logic |


## SEL

Type: function

Extensible: False

(G:BOOL, IN0:ANY, IN1:ANY) => OUT:ANY

Variables:

| Name | Class | Type | Notes |
    
| G | input | BOOL |  |
    
| IN0 | input | ANY |  |
    
| IN1 | input | ANY |  |
    
| OUT | output | ANY |  |
    

```
Binary selection (1 of 2)
```

## MAX

Type: function

Extensible: True

(IN1:ANY, IN2:ANY) => OUT:ANY

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | ANY |  |
    
| IN2 | input | ANY |  |
    
| OUT | output | ANY |  |
    

```
Maximum
```

## MIN

Type: function

Extensible: True

(IN1:ANY, IN2:ANY) => OUT:ANY

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | ANY |  |
    
| IN2 | input | ANY |  |
    
| OUT | output | ANY |  |
    

```
Minimum
```

## LIMIT

Type: function

Extensible: False

(MN:ANY, IN:ANY, MX:ANY) => OUT:ANY

Variables:

| Name | Class | Type | Notes |
    
| MN | input | ANY |  |
    
| IN | input | ANY |  |
    
| MX | input | ANY |  |
    
| OUT | output | ANY |  |
    

```
Limitation
```

## MUX

Type: function

Extensible: True

(K:INT, IN0:ANY, IN1:ANY) => OUT:ANY

Variables:

| Name | Class | Type | Notes |
    
| K | input | INT |  |
    
| IN0 | input | ANY |  |
    
| IN1 | input | ANY |  |
    
| OUT | output | ANY |  |
    

```
Multiplexer (select 1 of N)
```
