# Lab 02: User Management in Linux

## Objective

Create, manage, and delete Linux users and groups.

## Requirements

- Ubuntu or Amazon Linux EC2 instance.
- Terminal access.
- A user account with sudo privileges.

## Step 1: Check Current User

```bash
whoami
```

Display logged-in users:

```bash
who
```

## Step 2: Create a New User

Create a user named `developer`:

```bash
sudo adduser developer
```

Follow the prompts to set a password and user information.

## Step 3: Verify the User

```bash
id developer
```

Display the user entry:

```bash
getent passwd developer
```

## Step 4: Create a Group

Create a group named `developers`:

```bash
sudo groupadd developers
```

Verify the group:

```bash
getent group developers
```

## Step 5: Add User to a Group

```bash
sudo usermod -aG developers developer
```

Check group membership:

```bash
groups developer
```

## Step 6: Give Sudo Privileges

On Ubuntu:

```bash
sudo usermod -aG sudo developer
```

On Amazon Linux:

```bash
sudo usermod -aG wheel developer
```

The user may need to log out and log in again for the new group membership to apply to their session.

## Step 7: Switch User

```bash
su - developer
```

Check the current user:

```bash
whoami
```

Return to the previous account:

```bash
exit
```

## Step 8: Delete the User

Return to an administrative account and run:

```bash
sudo userdel developer
```

To delete the user's home directory as well:

```bash
sudo userdel -r developer
```

**Warning:** The `-r` option removes the user's home directory and mail spool. Back up important data first.

## Verification

Run:

```bash
id developer
groups developer
getent passwd developer
```

If the user has been deleted, these commands will no longer return the user's account information.

## Expected Result

You successfully created a Linux user, assigned group membership, configured sudo access, and removed the test account.

## What I Learned

- Creating Linux users.
- Creating groups.
- Managing group membership.
- Assigning sudo privileges.
- Switching and deleting users.
