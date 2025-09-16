# CharacterString

| Version: 1.0.0 | Author: Autonomy Logic |


## LEN

Type: function

Extensible: False

(IN:STRING) => OUT:INT

Variables:

| Name | Class | Type | Notes |
    
| IN | input | STRING |  |
    
| OUT | output | INT |  |
    

```
Length of string
```

## LEFT

Type: function

Extensible: False

(IN:STRING, L:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN | input | STRING |  |
    
| L | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
String left of
```

## RIGHT

Type: function

Extensible: False

(IN:STRING, L:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN | input | STRING |  |
    
| L | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
String right of
```

## MID

Type: function

Extensible: False

(IN:STRING, L:ANY_INT, S:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN | input | STRING |  |
    
| L | input | ANY_INT |  |
    
| S | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
String from middle of
```

## CONCAT

Type: function

Extensible: True

(IN1:STRING, IN2:STRING) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | STRING |  |
    
| IN2 | input | STRING |  |
    
| OUT | output | STRING |  |
    

```
Concatenation
```

## CONCAT_DATE_TOD

Type: function

Extensible: False

(IN1:DATE, IN2:TOD) => OUT:DT

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | DATE |  |
    
| IN2 | input | TOD |  |
    
| OUT | output | DT |  |
    

```
Time concatenation
```

## INSERT

Type: function

Extensible: False

(IN1:STRING, IN2:STRING, P:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | STRING |  |
    
| IN2 | input | STRING |  |
    
| P | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
Insertion (into)
```

## DELETE

Type: function

Extensible: False

(IN:STRING, L:ANY_INT, P:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN | input | STRING |  |
    
| L | input | ANY_INT |  |
    
| P | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
Deletion (within)
```

## REPLACE

Type: function

Extensible: False

(IN1:STRING, IN2:STRING, L:ANY_INT, P:ANY_INT) => OUT:STRING

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | STRING |  |
    
| IN2 | input | STRING |  |
    
| L | input | ANY_INT |  |
    
| P | input | ANY_INT |  |
    
| OUT | output | STRING |  |
    

```
Replacement (within)
```

## FIND

Type: function

Extensible: False

(IN1:STRING, IN2:STRING) => OUT:INT

Variables:

| Name | Class | Type | Notes |
    
| IN1 | input | STRING |  |
    
| IN2 | input | STRING |  |
    
| OUT | output | INT |  |
    

```
Find position
```
