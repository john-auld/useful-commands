# Send data to the netowrk using /dev/tcp or /dev/udp

/dev/tcp and /dev/udp can be used to send data to a monitoring service, such as sensu or statsd without needing to use a tool such as netcat (nc) or socat. 

```
echo '{"name": "check-mysql-status", "status": 1, "output": "error!"}' > /dev/tcp/localhost/3030
```

```
echo '{"name": "check-mysql-status", "status": 1, "output": "error!"}' > /dev/udp/127.0.0.1/3030
```
