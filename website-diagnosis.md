# Curl request without hosts file change
```
curl -k -I --resolve test.example.com:443:10.10.10.1 https://test.example.com/
HTTP/1.1 200 OK
```
