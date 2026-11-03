# DNS Commands in Linux

## What is DNS?

DNS stands for Domain Name System.

It converts domain names into IP addresses so computers can find servers on a network.

For example:

```text
google.com → IP Address
```

Without DNS, we would need to remember IP addresses instead of website names.

## 1. nslookup

The `nslookup` command checks DNS information for a domain.

```bash
nslookup google.com
```

It displays the DNS server used and the IP address returned.

## 2. dig

The `dig` command provides detailed DNS information.

### Check a Domain

```bash
dig google.com
```

### Display Only the IP Address

```bash
dig google.com +short
```

### Check a Specific DNS Record

```bash
dig google.com MX
```

Other common DNS record types:

- `A` – IPv4 address
- `AAAA` – IPv6 address
- `CNAME` – Alias of another domain
- `MX` – Mail server
- `NS` – Name server
- `TXT` – Text information

## 3. Install DNS Tools

Ubuntu:

```bash
sudo apt update
sudo apt install dnsutils -y
```

Amazon Linux 2023:

```bash
sudo dnf install bind-utils -y
```

These packages provide commands such as `dig` and `nslookup`.

## 4. Check DNS Configuration

View the configured DNS servers:

```bash
cat /etc/resolv.conf
```

On systems using systemd-resolved, you can also run:

```bash
resolvectl status
```

## 5. Check Domain Resolution

Use:

```bash
getent hosts google.com
```

This checks how the system resolves a hostname.

## Practice

```bash
nslookup google.com
dig google.com
dig google.com +short
dig google.com MX
cat /etc/resolv.conf
```

## Important Points

- DNS converts domain names into IP addresses.
- `nslookup` is used for DNS queries.
- `dig` provides detailed DNS information.
- `/etc/resolv.conf` commonly contains DNS resolver configuration.
