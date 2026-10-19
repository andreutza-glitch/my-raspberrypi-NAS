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
