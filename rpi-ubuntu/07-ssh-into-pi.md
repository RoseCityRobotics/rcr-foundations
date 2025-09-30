# SSH into your Raspberry Pi

Once your Pi is running Ubuntu and connected to your network, you can
access it remotely via **SSH**.  This guide assumes you know the IP
address of each Pi (e.g., `192.168.1.10`, `192.168.1.11`, etc.).

## Basic SSH command

Open a terminal on your laptop and run:

```bash
ssh <username>@192.168.1.N
```

Replace `<username>` with the user you created during installation
(e.g., `pi` or `ubuntu`) and `N` with the last octet of the Pi’s
address.  The first time you connect, the client will ask you to
verify the host key.  Type `yes` to continue.  Enter your password
when prompted【102108394223886†L1273-L1294】.

## Save hosts in SSH config

If you have multiple robots on your network, create an
`~/.ssh/config` file to define shortcuts:

```
Host robot1
  HostName 192.168.1.10
  User pi

Host robot2
  HostName 192.168.1.11
  User pi

Host robot3
  HostName 192.168.1.12
  User pi
```

Now you can connect by simply typing `ssh robot1`.  This file also
allows you to set per‑host options such as port number or key
location.

## SSH keys vs. passwords

For convenience and security, generate an SSH key on your laptop and
copy it to each Pi:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
ssh-copy-id robot1
ssh-copy-id robot2
```

After copying, you can log in without entering a password.  Always
protect your private key with a passphrase.

## Troubleshooting

If you cannot connect:

* Ensure the Pi is powered and connected to the network.
* Verify the IP address via your router or `arp -a`.
* Check that the `openssh-server` service is running on the Pi:

  ```bash
  sudo systemctl status ssh
  ```

SSH is a powerful tool for remote administration.  Combine it with
VS Code’s Remote SSH extension to develop on the Pi from your laptop.