### Debugging 

Capture the first three packets, of any port number or protocol and between any source and destination (a filter of none), that passes through the network interface named port1. The capture uses a low level of verbosity (indicated by 1)
```
diag sniffer packet port1 none 1 3
```

How to use host addresses and ports in filter, in this example number of packets is not specified so the command will run until interupted.
```
diag sniffer packet port1 'host 192.168.0.2 or host 192.168.0.1 and tcp port 80' 1
```
This example sniffs https trafic with hight verbosity indicated by 3.

```
diag sniffer port1 'tcp port 443' 3
```
