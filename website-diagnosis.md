# Curl request without hosts file change
```
curl -k -I --resolve test.example.com:443:10.10.10.1 https://test.example.com/
HTTP/1.1 200 OK
```


# Curl timings

## Create a new file, curl-format.txt, and paste in:

```
    time_namelookup:  %{time_namelookup}\n
       time_connect:  %{time_connect}\n
    time_appconnect:  %{time_appconnect}\n
   time_pretransfer:  %{time_pretransfer}\n
      time_redirect:  %{time_redirect}\n
 time_starttransfer:  %{time_starttransfer}\n
                    ----------\n
         time_total:  %{time_total}\n
```

## Make a request:
```
# Linux
curl -w "@curl-format.txt" -o /dev/null -s "http://www.example.com/"

# Windows
curl -w "@curl-format.txt" -o NUL -s "http://www.example.com/"
```
