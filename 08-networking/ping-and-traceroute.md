# Ping and Traceroute in Linux

## Introduction

When a Linux server cannot connect to another machine or website, networking commands help us troubleshoot the problem.

Two useful commands are:

- `ping` – Checks whether a destination is reachable.
- `traceroute` – Shows the network path taken by packets to reach a destination.

## 1. Ping Command

The `ping` command sends ICMP packets to another device and waits for a response.

### Check Internet Connectivity

```bash
ping google.com
```

### Ping an IP Address

```bash
ping 8.8.8.8
```

### Send a Limited Number of Packets

```bash
ping -c 4 google.com
```

This sends four packets and then stops.

### Stop Ping Manually

Press:

```text
Ctrl + C
```

### Understand the Output

Example:

```text
64 bytes from 142.250.183.14: icmp_seq=1 ttl=117 time=20 ms
```

- `64 bytes` – Size of the response.
- `icmp_seq` – Packet sequence number.
- `ttl` – Time to live.
- `time` – Response time in milliseconds.

## 2. Traceroute Command

The `traceroute` command displays the network hops between your machine and a destination.

### Install Traceroute

Ubuntu:

```bash
sudo apt install traceroute -y
```

Amazon Linux 2023:

```bash
sudo dnf install traceroute -y
```

### Trace a Website

```bash
traceroute google.com
```

### Trace an IP Address

```bash
traceroute 8.8.8.8
```

Each hop represents a router or network device along the route.

Some routers may not respond, so you might see `* * *` in the output.

## 3. Traceroute Alternative

Linux also provides `tracepath` on many distributions.

```bash
tracepath google.com
```

## Difference Between Ping and Traceroute

| Ping                            | Traceroute                                      |
| ------------------------------- | ----------------------------------------------- |
| Checks destination reachability | Shows the network path                          |
| Measures response time          | Displays intermediate hops                      |
| Uses ICMP                       | Uses probe packets, depending on implementation |

## Practice

```bash
ping -c 4 google.com
ping -c 4 8.8.8.8
traceroute google.com
```

Try these commands when troubleshooting network connectivity.
