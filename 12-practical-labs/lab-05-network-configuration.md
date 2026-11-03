# Lab 05: Network Configuration in Linux

## Objective

Learn how to check IP addresses, network interfaces, routes, DNS, and connectivity in Linux.

## Requirements

- Ubuntu or Amazon Linux.
- Internet connection.
- Terminal access.

## Step 1: Check IP Address

```bash
ip addr
```

Or:

```bash
hostname -I
```

Identify the IP address assigned to your Linux machine.

## Step 2: Check Network Interfaces

```bash
ip link show
```

This displays available network interfaces.

## Step 3: Check Routing Table

```bash
ip route
```

Look for the default route used to reach external networks.

## Step 4: Test Network Connectivity

Check connectivity to an IP address:

```bash
ping -c 4 8.8.8.8
```

Check connectivity using a domain name:

```bash
ping -c 4 google.com
```

If the IP test works but the domain test fails, DNS resolution may be the problem.

## Step 5: Check DNS Information

```bash
nslookup google.com
```

Or:

```bash
dig google.com
```

If these commands are missing, install the required DNS utilities.

Ubuntu:

```bash
sudo apt install dnsutils -y
```

Amazon Linux 2023:

```bash
sudo dnf install bind-utils -y
```

## Step 6: Check Listening Ports

```bash
sudo ss -tulnp
```

This displays listening TCP and UDP sockets and associated process information.

## Step 7: Check Network Path

Install traceroute if needed.

Ubuntu:

```bash
sudo apt install traceroute -y
```

Amazon Linux 2023:

```bash
sudo dnf install traceroute -y
```

Run:

```bash
traceroute google.com
```

## Step 8: Check SSH Port

```bash
sudo ss -tulnp | grep :22
```

This checks whether a process is listening on port 22.

## Verification

Run:

```bash
ip addr
ip route
ping -c 4 google.com
nslookup google.com
sudo ss -tulnp
```

Confirm that you can identify your network configuration and test connectivity.

## Expected Result

You successfully inspected network interfaces, IP addresses, routes, DNS, and listening ports.

## What I Learned

- Checking IP addresses.
- Understanding network interfaces.
- Viewing routing information.
- Testing connectivity.
- Troubleshooting DNS.
- Checking listening ports.
