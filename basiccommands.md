## dig
`Domain Information Groper` used for retrieivng info abt dns name servers

```bash
dig google.com any
```


## ping
sends and recieves data over a network, Tests connectivity between the host and another host

```bash
ping
ping -c 10 www.google.com
```


## traceroute
used to find network path from machine to server, Traces the route packets take from one host to another. Displays each hop along the path
```bash
traceroute -m 10 www.google.com
```


## tracepath 
similar to traceroute but doesnt require superuser priveleges and no fancy options
```bash
tracepath -n www.google.com
```

## nslookup
name server lookup,command used for getting info from dns server to obtain domain name or ip address mapping or any other record
```bash
nslookup
```

## netstat
prints network connections,routing tables, etc. used for finding problems in n/w and determining the amt of traffic, displays network stats and connections
```bash
netstat
```

## host
coverts names to ip adresses and vice versa
```bash
host
host google.com
```


## ifconfig
used to configure the systems kernel-resident n/w, used during boot time to setup interfaces, debugging, system tuning, displays status of systems interfaces.used to view the current configuration of network interfaces, including IP addresses and MAC addresses.
```bash
ifconfig
```


## ip 
similar to ifconfig but more powerful, info about state of network interfaces and their associated IP addresses.
```bash
ip addr show
```
