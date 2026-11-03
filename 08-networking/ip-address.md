# IP Address in Linux

## What is an IP Address?

An IP address (Internet Protocol address) is a unique address assigned to a device on a network.

It helps devices communicate with each other.

For example, when an EC2 instance communicates with another server, IP addresses help identify both machines.

## Types of IP Addresses

### 1. IPv4

IPv4 is the most commonly used IP address format.

Example:

```text
192.168.1.10
10.0.0.5
8.8.8.8
```

An IPv4 address contains four numbers separated by dots.

### 2. IPv6

IPv6 was introduced to provide a much larger number of IP addresses.

Example:

```text
2001:db8:85a3::8a2e:370:7334
```

## Private and Public IP Addresses

### Private IP Address

A private IP address is used inside a local network or private cloud network.

Examples:

```text
10.0.0.10
172.16.0.5
192.168.1.20
```

Private IP addresses are commonly used by EC2 instances inside a VPC.

### Public IP Address

A public IP address is used to communicate over the internet.

For example, a public IP allows users to connect to an internet-facing EC2 instance.

## Check Your IP Address

Use:

```bash
hostname -I
```

To display detailed network information:

```bash
ip addr
```

To check your hostname:

```bash
hostname
```

## Important Points

- Every device on an IP network needs an IP address.
- IPv4 and IPv6 are two IP address versions.
- Private IP addresses are used inside private networks.
- Public IP addresses allow internet communication.
- AWS EC2 instances can have private and public IP addresses.

## Practice

1. Check your Linux machine's IP address.
2. Identify its network interface.
3. Find out whether the IP address is private or public.