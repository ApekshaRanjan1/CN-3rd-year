
# Configuring IP Addresses on Ubuntu

## Finding the IP Address of the Network Card

To find the IP address of the network card, run the following command in the terminal:

```bash
sudo ip addr
```

**Sample Output:**
```
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP
inet 192.168.1.103/24 scope global enp0s3
```

In this example, the network card name is **enp0s3**, and its IP address is **192.168.1.103**.

## Adding an Additional IP Address

To add an additional IP address (e.g., **192.168.1.104**) to the interface card, run:

```bash
sudo ip addr add 192.168.1.104/24 dev enp0s3
```

To check if the IP is added, use:

```bash
sudo ip address show enp0s3
```

**Sample Output:**
```
inet 192.168.1.104/24 scope global secondary enp0s3
```

## Verifying the IP Address

To verify the new IP address, ping it:

```bash
sudo ping 192.168.1.104
```

## Checking the Routing Table

To check the routing table, run:

```bash
netstat -rn
```

**Sample Output:**
```
Destination    Gateway        Genmask       Flags Metric Ref    Use Iface
0.0.0.0        192.168.0.1   0.0.0.0       UG    0      0        0 wlan0
```

## Adding/Deleting Routes

To add a route:

```bash
sudo route add -net 192.168.3.0 gw 192.168.1.1 netmask 255.255.255.0 dev eth0
```

To delete a route:

```bash
sudo route del -net 192.168.3.0 gw 192.168.1.1 netmask 255.255.255.0 dev eth0
```

## Default Route Management

To quickly add a default route:

```bash
sudo route add default gw 192.168.1.1
```

To quickly delete the default route:

```bash
sudo route del default gw 192.168.1.1
```
