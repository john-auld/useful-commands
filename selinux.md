Get ports assigned to type
```
sepolicy network -t http_port_t  
semanage port -l | grep ^http_port_t
```

Get types associated with port
```
sepolicy network -p 8081
semanage port -l | grep ^http_port_t
```

Add port to type
```
semanage port -a -t http_port_t  -p tcp 8081
```
