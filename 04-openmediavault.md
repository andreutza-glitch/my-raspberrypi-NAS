# OpenMediaVault Installation and Configuration

## Overview

OpenMediaVault (OMV) is an open-source network attached storage (NAS) management platform based on Debian Linux.

It provides a web-based administration interface that simplifies the management of storage resources and network services.

In this project, OpenMediaVault is used as the base management layer for the Raspberry Pi NAS.

Its main responsibilities are:

- managing storage devices and filesystems;
- creating and managing shared folders;
- controlling user permissions;
- providing a web-based administration interface;
- managing additional plugins and services;
- providing the foundation for running Docker-based applications.

Instead of manually configuring every service directly from the Linux command line, OpenMediaVault provides a centralized interface while maintaining the flexibility of the underlying Debian system.

The final architecture is:

```text
Raspberry Pi 4
        |
        ↓
Raspberry Pi OS Lite 64-bit
        |
        ↓
OpenMediaVault
        |
        ↓
Docker Engine
        |
        ├── Immich
        ├── PostgreSQL
        ├── Redis
        └── Future services

```


# Installation Reference

The installation and initial configuration of OpenMediaVault followed the steps described in the following tutorial:

https://pimylifeup.com/raspberry-pi-openmediavault/

The tutorial was used as a reference for:

- installing OpenMediaVault on Raspberry Pi;
- accessing the web administration interface;
- configuring storage devices;
- creating shared folders;
- enabling additional functionality through plugins.

The following sections describe the configuration choices and adjustments made specifically for this NAS project.

---

# Initial Configuration

After installing OpenMediaVault, the web administration interface was accessed using the Raspberry Pi IP address:

http://raspberry-pi-ip-address

