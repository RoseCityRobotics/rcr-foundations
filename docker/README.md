# Docker on Ubuntu 24 (ARM64 / Pi 5)

Docker provides an easy way to build, run and share containerised
applications.  This guide shows how to install Docker Engine on Ubuntu
24.04 running on a Raspberry Pi 5.  The steps are adapted from the
official Docker documentation for Ubuntu【608065015325007†L935-L1003】.

## Install using the apt repository

1. **Uninstall old versions** (optional):

   ```bash
   sudo apt remove docker docker-engine docker.io containerd runc
   ```

2. **Install prerequisites:**

   ```bash
   sudo apt update
   sudo apt install -y ca-certificates curl gnupg
   ```

3. **Add Docker’s official GPG key:**

   ```bash
   sudo install -m 0755 -d /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
     | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   sudo chmod a+r /etc/apt/keyrings/docker.gpg
   ```

4. **Add the Docker apt repository:**

   ```bash
   echo \
     "deb [arch=$(dpkg --print-architecture) \
     signed-by=/etc/apt/keyrings/docker.gpg] \
     https://download.docker.com/linux/ubuntu \
     $(. /etc/os-release && echo "$VERSION_CODENAME") stable" \
     | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

5. **Install Docker Engine and related components:**

   ```bash
   sudo apt update
   sudo apt install -y docker-ce docker-ce-cli containerd.io \
     docker-buildx-plugin docker-compose-plugin
   ```

   These packages install the Docker daemon, CLI, container runtime
   and the `docker compose` command【608065015325007†L935-L1003】.

6. **Verify the installation:**

   ```bash
   sudo docker run hello-world
   ```

   Docker downloads a test image, runs it and prints a confirmation
   message【608065015325007†L935-L1003】.  If you see "Hello from Docker!", the
   installation succeeded.

## Manage Docker as a non‑root user

By default, only `root` can run Docker commands.  To avoid typing
`sudo` every time, add your user to the `docker` group:

```bash
sudo usermod -aG docker $USER
newgrp docker
```

Log out and back in (or run `newgrp docker`) for the group change to
take effect.

## Next steps

* Learn basic Docker commands: `docker images`, `docker ps`,
  `docker run -it ubuntu bash`.
* Use `docker compose` to define multi‑container applications.
* Explore container registries such as Docker Hub and GitHub Container
  Registry.

Containers provide isolation and portability for your robotics and
software projects.  Combined with your Pi 5, you can run modern
development stacks such as ROS 2, MQTT brokers, web servers and more.