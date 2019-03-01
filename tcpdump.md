# Save payload to text - useful for work with logstash

tcpdump -i any dst port 5152 -w syslog.tcp

tshark -n -T fields -e data -r syslog.tcp | ./decode-hex.py  > raw.txt

cat decode-hex.py
```python
#!/usr/bin/env python
import sys
 
for line in sys.stdin:
    print( line.strip().decode('hex') )
```
