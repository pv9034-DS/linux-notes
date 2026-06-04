# AWS Networking Fundamentals

## Introduction

AWS networking is built around Virtual Private Cloud (VPC), which allows you to create isolated networks in the cloud.

Understanding AWS networking is essential for:

- Cloud Computing
- DevOps
- Solutions Architecture
- System Administration

---

## Virtual Private Cloud (VPC)

A VPC is a logically isolated network in AWS.

Features:

- Private network environment
- Custom IP address ranges
- Public and private subnets
- Routing control
- Security controls

Example:

```text
VPC
├── Public Subnet
└── Private Subnet
```

---

## CIDR Block

CIDR defines the IP range of a VPC.

Example:

```text
10.0.0.0/16
```

Meaning:

- Network: 10.0.0.0
- Total IPs: 65,536

---

## Subnets

A subnet is a smaller network inside a VPC.

Example:

```text
VPC: 10.0.0.0/16

Public Subnet:
10.0.1.0/24

Private Subnet:
10.0.2.0/24
```

---

## Public Subnet

A subnet connected to the Internet through an Internet Gateway.

Common Resources:

- Web Servers
- Load Balancers
- Bastion Hosts

---

## Private Subnet

A subnet without direct internet access.

Common Resources:

- Databases
- Backend Services
- Internal Applications

---

## Internet Gateway (IGW)

Provides internet access for resources in public subnets.

Workflow:

```text
EC2
↓
Route Table
↓
Internet Gateway
↓
Internet
```

---

## Route Tables

A route table determines where network traffic is sent.

Example:

```text
Destination      Target
0.0.0.0/0        IGW
10.0.0.0/16      Local
```

---

## Security Groups

A Security Group acts as a virtual firewall.

Characteristics:

- Stateful
- Allow rules only
- Attached to resources

Example:

Allow SSH:

```text
Port 22
Source: My IP
```

Allow HTTP:

```text
Port 80
Source: Anywhere
```

---

## Network ACL (NACL)

Subnet-level firewall.

Characteristics:

- Stateless
- Allow and deny rules
- Applied to subnets

---

## NAT Gateway

Allows private subnet resources to access the internet without exposing them publicly.

Example:

```text
Private EC2
↓
NAT Gateway
↓
Internet Gateway
↓
Internet
```

Common Uses:

- Software updates
- Package downloads
- API access

---

## Elastic IP

A static public IPv4 address provided by AWS.

Benefits:

- Persistent public address
- Can be reassigned to another instance

---

## EC2 Networking

Check private IP:

```bash
ip a
```

Check public IP:

```bash
curl ifconfig.me
```

---

## DNS Basics

DNS translates domain names into IP addresses.

Example:

```text
google.com
↓
142.250.x.x
```

Useful Commands:

```bash
nslookup google.com
```

```bash
dig google.com
```

---

## Route 53

AWS managed DNS service.

Features:

- Domain registration
- DNS management
- Health checks
- Routing policies

---

## Route 53 Record Types

### A Record

Maps a domain to an IPv4 address.

```text
example.com → 192.168.1.10
```

---

### AAAA Record

Maps a domain to an IPv6 address.

---

### CNAME Record

Maps one domain to another.

Example:

```text
www.example.com → example.com
```

---

### MX Record

Mail server record.

Example:

```text
example.com → mail server
```

---

## VPC Peering

Allows communication between two VPCs.

Example:

```text
VPC-A
↕
VPC-B
```

Requirements:

- Non-overlapping CIDR blocks
- Route table updates
- Security Group configuration

---

## Availability Zones

AWS Regions contain multiple Availability Zones.

Example:

```text
ap-south-1a
ap-south-1b
ap-south-1c
```

Benefits:

- High Availability
- Fault Tolerance

---

## Best Practices

- Use private subnets for databases
- Restrict SSH access
- Use Security Groups carefully
- Avoid open access to all ports
- Use NAT Gateway for outbound internet access
- Design for high availability

---

## Common Architecture

```text
Internet
    │
Internet Gateway
    │
Public Subnet
    │
Load Balancer
    │
Application Server
    │
Private Subnet
    │
Database
```

---

## Summary

Topics covered:

- VPC
- CIDR
- Subnets
- Internet Gateway
- Route Tables
- Security Groups
- NACL
- NAT Gateway
- Elastic IP
- DNS
- Route 53
- VPC Peering
- Availability Zones

These concepts form the foundation of AWS networking and cloud infrastructure design.
