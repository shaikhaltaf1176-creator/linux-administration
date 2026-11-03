# SSH in Linux

## What is SSH?

SSH stands for Secure Shell.

It is a network protocol that allows us to securely connect to and manage another computer over a network.

For example, we use SSH to connect to an AWS EC2 Linux instance from our local computer.

## 1. Basic SSH Syntax

```bash
ssh username@server-ip
```

Example:

```bash
ssh ubuntu@192.168.1.10
```

Here:

- `ssh` – Starts the SSH connection.
- `ubuntu` – Remote server username.
- `192.168.1.10` – Remote server IP address.

## 2. Connect to AWS EC2 Using SSH

For an Ubuntu EC2 instance:

```bash
ssh -i my-key.pem ubuntu@PUBLIC-IP
```

For an Amazon Linux EC2 instance:

```bash
ssh -i my-key.pem ec2-user@PUBLIC-IP
```

Replace `my-key.pem` and `PUBLIC-IP` with your actual key file and EC2 public IP address.

## 3. Set Private Key Permissions

On Linux or macOS, SSH requires private keys to have restricted permissions.

```bash
chmod 400 my-key.pem
```

Then connect:

```bash
ssh -i my-key.pem ubuntu@PUBLIC-IP
```

## 4. Connect Using a Custom Port

The default SSH port is `22`.

If the server uses another port, specify it with `-p`:

```bash
ssh -p 2222 username@server-ip
```

## 5. Generate an SSH Key Pair

Create a new SSH key pair:

```bash
ssh-keygen -t ed25519
```

This creates:

- Private key: `id_ed25519`
- Public key: `id_ed25519.pub`

Never share your private key.

## 6. Copy a Public Key to Another Server

```bash
ssh-copy-id username@server-ip
```

After configuring key-based authentication, you can connect without entering the account password each time.

## 7. Exit an SSH Session

```bash
exit
```

Or press:

```text
Ctrl + D
```

## 8. Common SSH Errors

### Permission Denied

Possible reasons:

- Incorrect username.
- Wrong private key.
- Incorrect key permissions.
- Public key not configured on the server.

### Connection Timed Out

Possible reasons:

- Server is not reachable.
- Incorrect IP address.
- Port 22 is blocked.
- AWS security group does not allow SSH traffic.

### Connection Refused

Possible reasons:

- SSH service is not running.
- SSH server is not listening on the requested port.

## 9. Check SSH Service

On Ubuntu:

```bash
sudo systemctl status ssh
```

On Amazon Linux:

```bash
sudo systemctl status sshd
```

## Important Points

- SSH provides secure remote access.
- The default SSH port is 22.
- AWS EC2 Linux instances commonly use SSH for administration.
- Private keys must be kept secure.
- AWS security groups must allow SSH traffic from the intended source IP.

## Practice

1. Generate an SSH key pair.
2. Connect to a Linux server using SSH.
3. Check the SSH service status.
4. Exit the remote session.
5. Connect to an EC2 instance using a `.pem` key.
