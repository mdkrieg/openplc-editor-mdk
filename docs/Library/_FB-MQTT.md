# MQTT

| Version: 1.0.0 | Author: Autonomy Logic |


## MQTT_RECEIVE

Type: function-block

Extensible: 

Receive MQTT messages for a particular TOPIC when RECEIVE is active. You must subscribe to a topic first before you can start receiving messages for that particular topic. Once a message is received, RECEIVED output is triggered, and MESSAGE will contain the received message as a STRING.

Variables:

| Name | Class | Type | Notes |
    
| RECEIVE | input | BOOL | RECEIVE |
    
| TOPIC | input | STRING | TOPIC |
    
| RECEIVED | output | BOOL | RECEIVED |
    
| MESSAGE | output | STRING | MESSAGE |
    

```
RECEIVED := 0;
```

## MQTT_SEND

Type: function-block

Extensible: 

Sends a MESSAGE to a particular TOPIC when SEND input is triggered. Keep in mind that SEND is not configured as a rising edge input, which means that MQTT_SEND will continuously send messages every scan cycle while SEND is TRUE. If the message was sent without errors, SUCCESS will be TRUE.

Variables:

| Name | Class | Type | Notes |
    
| SEND | input | BOOL | SEND |
    
| TOPIC | input | STRING | TOPIC |
    
| MESSAGE | input | STRING | MESSAGE |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```

## MQTT_CONNECT

Type: function-block

Extensible: 

Connect to a BROKER at a given PORT when CONNECT is triggered. If a successful connection is made, SUCCESS is set to TRUE

Variables:

| Name | Class | Type | Notes |
    
| CONNECT | input | BOOL | CONNECT |
    
| BROKER | input | STRING | BROKER |
    
| PORT | input | UINT | PORT |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```

## MQTT_CONNECT_AUTH

Type: function-block

Extensible: 

Connect to an authenticated BROKER at a given PORT using the credentials from USER and PASSWORD when CONNECT is triggered. If a successful connection is made, SUCCESS is set to TRUE

Variables:

| Name | Class | Type | Notes |
    
| CONNECT | input | BOOL | CONNECT |
    
| BROKER | input | STRING | BROKER |
    
| PORT | input | UINT | PORT |
    
| USER | input | STRING | USER |
    
| PASSWORD | input | STRING | PASSWORD |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```

## MQTT_SUBSCRIBE

Type: function-block

Extensible: 

Subscribe to a given TOPIC when SUBSCRIBE input is triggered. Upon a successful subscription, SUCCESS is set to TRUE. Keep in mind that once you subscribe to a topic, OpenPLC will start receiving messages sent to that topic and storing them in a message pool. You must use the MQTT_RECEIVE block to retrieve messages from the pool and free up space to receive more messages. The maximum pool size is currently limited to 10 messages. If you let messages accumulate in the pool you will start loosing messages once the pool is full.

Variables:

| Name | Class | Type | Notes |
    
| SUBSCRIBE | input | BOOL | SUBSCRIBE |
    
| TOPIC | input | STRING | TOPIC |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```

## MQTT_UNSUBSCRIBE

Type: function-block

Extensible: 

Unsubscribe to a given TOPIC when UNSUBSCRIBE input is triggered. Upon a successful unsubscription, SUCCESS is set to TRUE. Keep in mind that once you unsubscribe to a topic, OpenPLC will stop storing messages sent to that topic in the message pool. However, messages received previously and not captured with a MQTT_RECEIVE block will remain in the pool using up pool space.

Variables:

| Name | Class | Type | Notes |
    
| UNSUBSCRIBE | input | BOOL | UNSUBSCRIBE |
    
| TOPIC | input | STRING | TOPIC |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```

## MQTT_DISCONNECT

Type: function-block

Extensible: 

Disconnects from the current broker when DISCONNECT is set to TRUE. Upon a successful disconnection, SUCCESS is set to TRUE.

Variables:

| Name | Class | Type | Notes |
    
| DISCONNECT | input | BOOL | DISCONNECT |
    
| SUCCESS | output | BOOL | SUCCESS |
    

```
SUCCESS := 0;
```
