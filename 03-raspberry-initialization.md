# Raspberry Pi Initialization

## Overview

This document describes the initial setup and preparation of the Raspberry Pi platform before installing and configuring OpenMediaVault.

The objective of this stage was to prepare a stable Linux-based environment with remote administration capabilities and network connectivity.


# Operating System Installation

The Raspberry Pi was initialized using **Raspberry Pi OS Lite (64-bit)**.

The 64-bit version was selected because:

- Raspberry Pi 4 uses an ARM64 architecture;
- modern Docker containers provide ARM64 images;
- it ensures better compatibility with current applications;
- it provides a stable Debian-based environment required for OpenMediaVault.

Please note that you need to avoid using a desktop variant of your chosen operating system. OpenMediaVault will only work on terminal-based systems. In the case of the Pi, this is Raspberry Pi OS Lite.

The operating system image was written to the microSD card using Raspberry Pi Imager.

During the imaging process, the following options were configured:

- hostname assignment;
- SSH enabled;
- initial user creation;
- network configuration.

After completing the imaging process, the microSD card was inserted into the Raspberry Pi and the system was booted.

For more informations follow this tutorial: https://www.raspberrypi.com/documentation/computers/getting-started.html#installing-the-operating-system

# First Boot Configuration

After the first boot, the Raspberry Pi was accessed remotely through SSH. To identify the IP address of the Raspberry Pi I checked the recognized devices from the administration page of the home router.

Connection:

```bash
ssh username@raspberry_ip_address
```

# Static IP Configuration

To ensure reliable access to the Raspberry Pi NAS, a static IP address was configured for the Ethernet interface.

A fixed IP address is important for a server environment because services such as OpenMediaVault, Docker containers and remote administration require a predictable network address.

The static IP address was assigned outside the router DHCP pool to avoid possible IP conflicts with other devices on the network.

The current network configuration was checked using:

```bash
ip addr
```

The routing table was verified using:

```bash
ip route
```
## Configuring Static IP Using NetworkManager

The Raspberry Pi network configuration was managed using NetworkManager.

Available network connections were identified using:

```bash
nmcli connection show
```

The Ethernet connection was selected and configured with a manual IPv4 address:

```bash
sudo nmcli connection modify <connection_name> \
ipv4.method manual \
ipv4.addresses <static_ip_address>/<subnet_mask> \
ipv4.gateway <gateway_address> \
ipv4.dns <dns_server>
```

The configuration parameters are:

- `ipv4.method manual` - enables static IP configuration;
- `ipv4.addresses` - assigns the static IP address;
- `ipv4.gateway` - defines the default gateway used for external network communication;
- `ipv4.dns` - specifies the DNS server.

Example configuration:

```bash
sudo nmcli connection modify eth0 \
ipv4.method manual \
ipv4.addresses 192.168.1.137/24 \
ipv4.gateway 192.168.1.1 \
ipv4.dns 8.8.8.8
```

## Applying Network Configuration Changes

After modifying the network configuration, the connection was restarted to apply the new settings.

The network connection was restarted using:

```bash
sudo nmcli connection down <connection_name> && nmcli connection up <connection_name>
```

The `&&` operator ensures that the second command (`connection up`) is executed only after the connection has been successfully brought down.

This approach prevents the network interface from remaining disabled after applying the new configuration.

After restarting the connection, the new settings were verified using:

```bash
ip addr
```

The routing configuration was checked using:

```bash
ip route
```

A correct configuration should display a default route through the configured gateway:

```text
default via <gateway_address>
```

Connectivity was tested using:

```bash
ping google.com
```

A successful response confirmed that the Raspberry Pi had a functional static IP configuration and external network access.

## Note

When changing network parameters remotely through SSH, restarting the active connection may temporarily interrupt the SSH session. The new configuration should be verified before disconnecting from the local console or remote session.
