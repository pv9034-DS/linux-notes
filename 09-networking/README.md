# Networking Commands

## Introduction

Networking is a critical Linux skill for system administrators, cloud engineers, and DevOps professionals. Linux provides several tools to diagnose connectivity issues, inspect network configurations, and troubleshoot communication between systems.

---

## Check Network Interfaces

### ip

Display network interfaces.

```bash
ip addr
```

Short version:

```bash
ip a
```

Example Output:

```text
2: wlp2s0
inet 192.168.1.100/24
```

---

### Show Routing Table

```bash
ip route
```

or

```bash
ip r
```

Example:

```text
default via 192.168.1.1
```

---

## Test Connectivity

### ping

Check connectivity between systems.

```bash
ping google.com
```

Send 4 packets only:

```bash
ping -c 4 google.com
```

Example Output:

```text
64 bytes from ...
```

---

## Display Open Ports

### ss

Show active network connections.

```bash
ss
```

Show listening ports:

```bash
ss -tuln
```

Options:

- t → TCP
- u → UDP
- l → Listening
- n → Numeric

---

### netstat

Older networking utility.

```bash
netstat -tulnp
```

May require installation:

```bash
sudo dnf install net-tools
```

or

```bash
sudo apt install net-tools
```

---

## Trace Network Path

### traceroute

Display the path packets take.

```bash
traceroute google.com
```

Install if needed:

```bash
sudo dnf install traceroute
```

---

### tracepath

Similar to traceroute.

```bash
tracepath google.com
```

---

### mtr

Combines ping and traceroute.

```bash
mtr google.com
```

Install:

```bash
sudo dnf install mtr
```

---

## DNS Commands

### nslookup

Query DNS records.

```bash
nslookup google.com
```

Query a specific DNS server:

```bash
nslookup google.com 8.8.8.8
```

---

### dig

More advanced DNS utility.

```bash
dig google.com
```

Query A record:

```bash
dig google.com A
```

Query MX record:

```bash
dig google.com MX
```

Short answer:

```bash
dig google.com +short
```

---

## Test Ports

### telnet

Test connectivity to a port.

```bash
telnet google.com 80
```

Install:

```bash
sudo dnf install telnet
```

---

### nc (Netcat)

Check port availability.

```bash
nc -zv google.com 80
```

Check multiple ports:

```bash
nc -zv google.com 80 443
```

---

## Wireless Networking

### iw

Display wireless device information.

```bash
iw dev
```

Show wireless interfaces:

```bash
iwconfig
```

---

### nmcli

NetworkManager command-line tool.

Show connections:

```bash
nmcli connection show
```

Show devices:

```bash
nmcli device status
```

Connect to Wi-Fi:

```bash
nmcli device wifi connect "SSID" password "password"
```

---

## Host Information

### hostname

Display system hostname.

```bash
hostname
```

Display IP address:

```bash
hostname -I
```

---

## Whois

Display domain registration information.

```bash
whois google.com
```

Install:

```bash
sudo dnf install whois
```

---

## ARP

Display ARP table.

```bash
arp -a
```

Alternative:

```bash
ip neigh
```

---

## Useful Examples

Check IP address:

```bash
ip a
```

Check internet connectivity:

```bash
ping google.com
```

Check open ports:

```bash
ss -tuln
```

Check DNS resolution:

```bash
dig google.com
```

Check default gateway:

```bash
ip route
```

---

## Summary

Commands covered:

- ip
- ping
- ss
- netstat
- traceroute
- tracepath
- mtr
- nslookup
- dig
- telnet
- nc
- iw
- nmcli
- hostname
- whois
- arp

These commands are fundamental for Linux networking, cloud computing, AWS, troubleshooting, and DevOps operations.
