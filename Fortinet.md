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


### Using Rest API user

```
import requests

# FortiAnalyzer API endpoint and your credentials
api_key = 'topsecret'
api_url = f'https://10.110.32.51/jsonrpc?access_token={api_key}'

verify_certificate = False


info_payload = {
    "method": "get",
    "params": [{
        "url": "/eventmgmt/adom/Customer_Two/alerts",
        "apiver": 3,
        "limit": 1
    }],
    "jsonrpc": "2.0",
    "id": 2
}

response = requests.post(api_url, json=info_payload, verify=verify_certificate)

if response.status_code == 200:
    return (data["result"]["data"])
else:
    print(f"Failed to fetch alerts from FortiAnalyzer. Error code: {response.status_code}")
```
