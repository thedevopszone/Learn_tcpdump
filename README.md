# Learn TCPDump


```
apt install tcpdump
```
 

# Interfaces anzeigen
```
tcpdump -D
```
 

 

# Auf allen netzwerk Interfaces lauschen (Unübersichtlich) Was wir senden
```
tcpdump -i any
```
 

# Auf einem Netzwerk Interface (was wir senden)
```
tcpdump -i ens192
```
 

# Übersichtlicher
```
tcpdump -i ens192 -q
```
 

# Mehr anzeigen
```
tcpdump -i ens192 -v

tcpdump -i ens192 -vv

tcpdump -i ens192 -vvv
```
 

# In eine Datei schreiben
```
tcpdump -i ens192 -w out.dump
```
 

 

# Nur tcp Packete
```
tcpdump -i ens192 tcp
```
 

# Nur udp Packete
```
tcpdump -i ens192 udp
```
 

# Nur Port 443

# Nur tcp Packete
```
tcpdump -i ens192 tcp port 443

tcpdump -i ens192 tcp port 443 -q
```
 

# Only 10 lines
```
tcpdump -c 10
```

# All packets from the host HOST-NAME
```
tcpdump -i ens192 host HOST-NAME
```
 

# Only packets sent from the host HOST-NAME
```
tcpdump -i ens192 src host HOST-NAME
```
 

# Only packets sent to host HOST-NAME
```
tcpdump -i ens192 dst host HOST-NAME
```
 

# Only packets sent to ip IP-ADDR
```
tcpdump -i ens192 dst host IP-ADDR
```

# Only packets sent to a host where the ip has changed
```
tcpdump -i ens192 ether host MAC-ADDR
```
 

# Netmask filter
```
tcpdump -i ens192 net 172.16.0.0 mask 255.255.255.252
```
 

# Also show IPs
```
tcpdump -i ens192 net 172.16.0.0 mask 255.255.255.252 -n
```
 

 

# Filter by port numbers
```
tcpdump -i ens192  port 22 -n
```
 
```
tcpdump -i ens192 src host 10.0.2.12 and port 22 -n

tcpdump -i ens192 src host 10.0.2.12 and not port 22 -n

 

tcpdump -i ens192 src host 10.0.2.12 or port 22 -n
```
 

# Save packet data
```
tcpdump -w /tmp/demo.pcap -c 25
```
 

# Read saved file
```
tcpdump -r /tmp/demo.pcap

tcpdump -r /tmp/demo.pcap | less
```
 

# You can manipulate the output
```
tcpdump -r /tmp/demo.pcap -e # Show MAC addresses instead of IP addresses
```
 

# Show the hole package data (example nly one package)
```
tcpdump -r /tmp/demo.pcap -c 1 -XX
```
 

# Output without timestap
```
tcpdump -r /tmp/demo.pcap -c 3 -t
```
 

# Show the delta time
```
tcpdump -r /tmp/demo.pcap -c 10 -ttt
```
 
```
tcpdump -r /tmp/demo.pcap -c 10 -ttt # Also with date
```
 

Beste Grüße

Thomas Mundt (extern)


