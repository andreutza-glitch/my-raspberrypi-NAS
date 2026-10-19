# Hardware Selection

## Overview

The hardware platform represents the foundation of the NAS system. The main requirements considered during the selection process were low power consumption, reliability, compact size, silent operation and sufficient performance for personal storage and self-hosted services.

After evaluating different hardware solutions, the selected platform for this project is based on a Raspberry Pi 4 Model B with 8 GB of RAM, combined with SSD storage.

---

# Hardware Requirements

The NAS platform should satisfy the following requirements:

## Low Power Consumption

Since the NAS is designed to operate continuously, power efficiency is an important factor.

The selected hardware should:
- consume minimal energy during continuous operation;
- generate limited heat;
- reduce operating costs.

## Always-On Operation

A NAS is expected to be available whenever a user needs access to stored data.

Therefore, the system should support:
- stable long-term operation;
- automatic startup after power loss;
- minimal maintenance.

## Compact and Silent Design

The system is intended for home use, therefore:
- small physical footprint;
- low noise level;
- easy placement near networking equipment

are important considerations.

## Expandability

The platform should allow future improvements such as:
- additional storage;
- new services;
- improved backup solutions.

---

The final hardware configuration of the self-hosted NAS platform is:

| Component | Specification | Purpose |
|---|---|---|
| Single Board Computer | Raspberry Pi 4 Model B | Main processing and server platform |
| RAM | 4 GB LPDDR4 | Running operating system, Docker containers and self-hosted services |
| Primary Storage | 512 GB SSD | Application data, databases, container storage and user files |
| System Storage | microSD card | Operating system installation and system recovery |
| Storage Interface | USB-to-SATA adapter | Connecting the SSD to the Raspberry Pi |

The selected configuration is designed as a low-power personal server capable of hosting self-managed services while providing practical experience with Linux administration, storage management, containerization and network services.

<img width="1280" height="1280" alt="image" src="https://github.com/user-attachments/assets/91efb0cb-afcc-431a-bacd-cf83d773eeec" />

<img width="2000" height="2000" alt="image" src="https://github.com/user-attachments/assets/1d2ad699-7349-46ef-9174-fc08471ca712" />

<img width="3025" height="3025" alt="image" src="https://github.com/user-attachments/assets/4f8d3146-23d7-4ede-857b-34069efa830f" />

<img width="1536" height="1536" alt="image" src="https://github.com/user-attachments/assets/973292e5-6812-4964-8dc7-6c57d902974d" />



---

# Component Analysis

## Raspberry Pi 4 Model B

The Raspberry Pi 4 Model B was selected as the main computing platform for the NAS due to its balance between performance, power consumption and flexibility.

Its main responsibilities are:

- running the server operating system;
- managing storage devices;
- hosting Docker-based applications;
- providing network-accessible services;
- managing remote access through secure networking solutions.

The main reasons for selecting this platform are:

- low power consumption compared to traditional servers;
- compact size;
- silent operation;
- extensive Linux and open-source ecosystem support;
- compatibility with ARM64-based operating systems and container workloads.

Although the Raspberry Pi 4 provides lower computational performance compared to traditional x86 servers, its resources are sufficient for the intended workloads, including personal file storage, photo management, backups and lightweight self-hosted applications.

---

## Memory - 4 GB RAM

The selected Raspberry Pi configuration includes 4 GB of RAM, providing sufficient capacity for running multiple services simultaneously.

The available memory supports workloads such as:

- OpenMediaVault system management;
- Docker container execution;
- Immich photo management platform;
- database services;
- future monitoring and self-hosted applications.

The additional memory capacity improves system stability when multiple services are running concurrently.

---

## SSD Storage - 512 GB

The NAS uses a 512 GB SSD as the primary data storage device instead of relying exclusively on a microSD card.

The SSD is connected to the Raspberry Pi through a USB-to-SATA adapter.

The SSD provides:

- higher read/write performance;
- improved reliability compared to microSD storage for frequent write operations;
- lower latency;
- better support for application data and database workloads.

The SSD is used for:

- Docker storage;
- container configuration files;
- persistent application data;
- Immich photo library;
- database storage.

Separating application data and user files from the microSD card improves system reliability and reduces storage wear on the operating system medium.

---

## MicroSD Card

The microSD card is used as the system storage medium.

Its main purposes are:

- hosting the operating system;
- enabling system recovery or reinstallation;
- providing a simple and replaceable boot medium.

User data and application workloads are stored on the SSD in order to improve reliability and simplify backup procedures.

---

## USB-to-SATA Adapter

The USB-to-SATA adapter provides the connection between the Raspberry Pi and the SSD storage device.

Its role is to:

- enable external SSD connectivity;
- provide higher-speed storage compared to microSD;
- allow the Raspberry Pi to use SSD storage for persistent data.

Using an external SSD connected through USB allows the system to maintain a compact and low-power design while improving storage performance.

---

# Alternative Platforms Considered

## Traditional Desktop PC

Advantages:

- higher processing capability;
- support for larger storage configurations;
- compatibility with virtualization platforms.

Disadvantages:

- increased power consumption;
- larger physical footprint;
- higher noise levels;
- unnecessary performance for the intended workload.

---

## Mini PC

Advantages:

- higher performance compared to Raspberry Pi;
- low power consumption;
- native x86 compatibility;
- better support for demanding applications.

Disadvantages:

- higher acquisition cost;
- less emphasis on embedded and low-power experimentation.

---

# Final Decision

The Raspberry Pi 4 Model B platform was selected because the objective of this project is not to maximize computational performance, but to build an efficient and reliable personal NAS while developing practical knowledge in:

- Linux server administration;
- storage management;
- Docker containerization;
- self-hosted applications;
- secure remote access.

The final configuration provides sufficient resources for current services while maintaining low energy consumption, compact size and flexibility for future expansion.
