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

# Selected Hardware Configuration

The final hardware configuration is:

| Component | Specification | Purpose |
|---|---|---|
| Single Board Computer | Raspberry Pi 4 Model B | Main processing unit |
| RAM | 8 GB LPDDR4 | Running operating system and services |
| System/Data Storage | 256 GB SSD | Storage for operating system, applications and user data |
| Secondary Storage | 128 GB microSD card | Recovery/testing medium |
| Enclosure | X825-C8 Metal Case | Protection, cooling and SSD integration |

---

# Component Analysis

## Raspberry Pi 4 Model B

The Raspberry Pi 4 Model B was selected as the main computing platform for the NAS.

Its role is to:
- run the operating system;
- manage storage devices;
- provide network services;
- host self-managed applications.

The main reasons for selecting this platform are:

- low energy consumption;
- compact size;
- silent operation;
- large community support;
- compatibility with Linux-based operating systems.

Although it has lower performance compared to traditional x86 servers, its capabilities are sufficient for a personal NAS focused on file storage, backups and lightweight services.

---

## Memory - 8 GB RAM

The selected Raspberry Pi configuration includes 8 GB of RAM.

Additional memory provides more flexibility for running multiple services simultaneously.

The available RAM can support workloads such as:

- file sharing services;
- Docker containers;
- monitoring applications;
- web-based management interfaces.

---

## SSD Storage - 256 GB

The project uses SSD storage instead of relying exclusively on a microSD card.

The SSD provides:

- higher read/write performance;
- better reliability for frequent access;
- lower latency;
- improved experience when running applications.

The SSD will be used for:
- operating system installation;
- application data;
- frequently accessed files.

---

## MicroSD Card - 128 GB

The microSD card is included as an additional storage medium.

Possible uses:

- system recovery;
- testing different operating systems;
- backup installation media.

The final decision regarding boot configuration will be made during the operating system installation phase.

---

## X825-C8 Metal Case

The X825-C8 enclosure provides:

- physical protection for the Raspberry Pi;
- SSD mounting support;
- improved thermal management;
- a compact final assembly.

The enclosure helps transform the individual components into a dedicated server appliance suitable for continuous operation.

---

# Alternative Platforms Considered

## Traditional Desktop PC

Advantages:
- higher processing power;
- more storage expansion options;
- support for virtualization.

Disadvantages:
- higher power consumption;
- larger physical size;
- increased noise.

## Mini PC

Advantages:
- better performance than Raspberry Pi;
- low power consumption;
- x86 compatibility.

Disadvantages:
- higher cost;
- less compact compared to a Raspberry Pi solution.

## Final Decision

The Raspberry Pi 4 platform was selected because the primary goal of this project is not maximum performance, but creating a low-power personal NAS while gaining practical experience with Linux server administration and self-hosted services.
