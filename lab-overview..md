# Linux SSH Lab: Alpine Linux + OpenSSH + PuTTY

## Goal
Set up a Linux server in a virtual machine and connect to it remotely over SSH from Windows.

## Tools
- VMware Workstation
- Alpine Linux 3.24
- OpenSSH (sshd)
- PuTTY (Windows SSH client)

## Steps
1. Booted the Alpine Linux VM (`02-alpine-linux-boot.png`)
2. Brought up the network interface with `ip link set eth0 up` and `setup-interfaces` (`03`)
3. Configured DHCP and obtained an IP address (`04`, `05`)
4. Created a non-root user with `setup-user` and gave it admin rights through `doas`
5. Updated the system with `apk update` and `apk upgrade`
6. Installed and started the OpenSSH server with `setup-sshd`, then verified it with `rc-status` (`06`)
7. Configured PuTTY with the VM's IP address, port 22, and SSH (`07`)
8. Connected to the VM successfully over SSH (`08`)

## Problems I troubleshot
- **`doas: Authentication failed`:** reset the user's password with `passwd` and retried.
- **Network interface was down:** brought it up manually, then requested an IP through DHCP.
- **Typos in commands:** read the error messages and corrected them.

## What I learned
- Basic Linux administration and package management
- Network setup and DHCP
- Creating users with limited privileges
- Setting up and testing remote access with SSH
