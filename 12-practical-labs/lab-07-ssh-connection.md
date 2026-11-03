# Lab 07: SSH Connection in Linux

## Objective

Learn how to connect to a remote Linux server securely using SSH.

## Requirements

- Local computer with an SSH client.
- Linux server or AWS EC2 instance.
- Private key file (`.pem`) for EC2.
- Server IP address.

## Step 1: Check SSH Client

Run:

```bash
ssh -V
```

This displays the installed SSH client version.

## Step 2: Check EC2 Information

Open the AWS EC2 Console and identify:

- Instance public IPv4 address.
- Instance state.
- Security group.
- Private key file used when launching the instance.

## Step 3: Configure Security Group

For an EC2 instance, allow inbound SSH traffic:

| Type | Protocol | Port | Source            |
| ---- | -------- | ---- | ----------------- |
| SSH  | TCP      | 22   | Your public IP/32 |

Avoid opening SSH to everyone (`0.0.0.0/0`) unless there is a specific, temporary testing requirement.

## Step 4: Set Private Key Permissions

On Linux or macOS:

```bash
chmod 400 my-key.pem
```

On Windows, use the appropriate Windows file permissions for your private key.

## Step 5: Connect to Ubuntu EC2

```bash
ssh -i my-key.pem ubuntu@PUBLIC-IP
```

## Step 6: Connect to Amazon Linux EC2

```bash
ssh -i my-key.pem ec2-user@PUBLIC-IP
```

Replace `PUBLIC-IP` with your actual EC2 public IP address.

## Step 7: Verify Remote Connection

After connecting, run:

```bash
whoami
hostname
uname -a
pwd
```

These commands display information about the remote server.

## Step 8: Transfer a File Using SCP

Copy a local file to Ubuntu EC2:

```bash
scp -i my-key.pem file.txt ubuntu@PUBLIC-IP:/home/ubuntu/
```

For Amazon Linux:

```bash
scp -i my-key.pem file.txt ec2-user@PUBLIC-IP:/home/ec2-user/
```

## Step 9: Exit SSH

```bash
exit
```

## Step 10: Troubleshoot Common Errors

### Permission Denied

Check:

- Correct username.
- Correct private key.
- Key file permissions.
- EC2 key pair.

### Connection Timed Out

Check:

- EC2 instance is running.
- Public IP address is correct.
- Security group allows SSH from your IP.
- Network routing and internet connectivity are configured.

### Connection Refused

Check whether the SSH server is running.

Ubuntu:

```bash
sudo systemctl status ssh
```

Amazon Linux:

```bash
sudo systemctl status sshd
```

## Expected Result

You successfully connected to a remote Linux server using SSH and transferred a file using SCP.

## What I Learned

- Understanding SSH.
- Connecting to EC2 using a private key.
- Configuring SSH security group rules.
- Using SCP for file transfer.
- Troubleshooting SSH connection problems.
