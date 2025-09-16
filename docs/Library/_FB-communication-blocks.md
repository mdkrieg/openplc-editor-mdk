# Communication Blocks

| Version: 1.0.0 | Author: Autonomy Logic |


## TCP_CONNECT

Type: function-block

Extensible: 

Connect to a remote TCP server when CONNECT is TRUE. Upon success, this block returns the connection ID on SOCKET_ID. If SOCKET_ID is less than zero, then the connection was not successfull

Variables:

| Name | Class | Type | Notes |
    
| CONNECT | input | BOOL |  |
    
| IP_ADDRESS | input | STRING |  |
    
| PORT | input | INT |  |
    
| SOCKET_ID | output | INT |  |
    

```
SOCKET_ID := 0;
```

## TCP_SEND

Type: function-block

Extensible: 

Send a message to a remote device using TCP/IP when SEND is TRUE. SOCKET_ID must receive a connection ID from a successfull connection using the TCP_Connect block. BYTES_SENT returns the number of bytes sent to the remote device. If BYTES_SENT is less than zero then an error occurred while trying to send the message

Variables:

| Name | Class | Type | Notes |
    
| SEND | input | BOOL |  |
    
| SOCKET_ID | input | INT |  |
    
| MSG | input | STRING |  |
    
| BYTES_SENT | output | INT |  |
    

```
BYTES_SENT := 0;
```

## TCP_RECEIVE

Type: function-block

Extensible: 

Send a message to a remote device using TCP/IP when SEND is TRUE. SOCKET_ID must receive a connection ID from a successfull connection using the TCP_Connect block. BYTES_RECEIVED returns the number of bytes received from the remote device. MSG is a String containing the message received

Variables:

| Name | Class | Type | Notes |
    
| RECEIVE | input | BOOL |  |
    
| SOCKET_ID | input | INT |  |
    
| BYTES_RECEIVED | output | INT |  |
    
| MSG | output | STRING |  |
    

```
BYTES_RECEIVED := 0;
```

## TCP_CLOSE

Type: function-block

Extensible: 

Close the TCP connection with the remote server. If SUCCESS is less than zero, then the connection was not successfully closed, or the connection does not exist anymore.

Variables:

| Name | Class | Type | Notes |
    
| CLOSE | input | BOOL |  |
    
| SOCKET_ID | input | INT |  |
    
| SUCCESS | output | INT |  |
    

```
SUCCESS := 0;
```
