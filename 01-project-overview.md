# Project Overview

## Introduction

This project documents the design, implementation and configuration of a personal Network Attached Storage (NAS) system built using a Raspberry Pi 4 Model B.

The goal of this project is to create a low-power, always-on home server capable of providing centralized storage for personal data such as photos, videos and documents, while also serving as a practical learning platform for Linux system administration, networking and self-hosted services.

The repository documents the complete development process, including hardware selection, operating system installation, storage configuration, network setup, deployed services, troubleshooting and lessons learned.

---

## Project Motivation

Modern devices generate large amounts of personal data, especially photos and videos. Relying exclusively on third-party cloud storage can introduce limitations related to storage costs, privacy and control over personal data.

This project aims to build a self-managed storage solution that provides:

- full ownership of stored data;
- local access through the home network;
- remote administration capabilities;
- the ability to deploy additional self-hosted services.

Additionally, the project is intended as a hands-on learning environment for understanding how real server systems are designed, configured and maintained.

---

## Objectives

### Functional Objectives

The NAS system should provide:

- centralized storage for personal files;
- network access to stored data;
- photo and video management;
- backup capabilities;
- remote administration;
- support for additional services.

### Learning Objectives

Through this project, the following concepts will be explored:

- Linux server administration;
- filesystem and storage management;
- networking fundamentals;
- service management;
- remote administration using SSH;
- containerization using Docker;
- deployment of self-hosted applications;
- backup and security practices.

---

## Project Requirements

### Hardware Requirements

The system should:

- have low power consumption;
- support continuous operation;
- be compact and silent;
- provide reliable storage.

### Software Requirements

The system should support:

- Linux-based operating system;
- network file sharing;
- containerized applications;
- monitoring and maintenance tools.

---

## Expected Architecture

The planned architecture consists of:

<img width="382" height="281" alt="strcturanou" src="https://github.com/user-attachments/assets/a1237dfa-5171-47d4-bad9-27fa357a84a0" />

The Raspberry Pi will act as the central server responsible for managing storage and providing services to connected devices.

---

## Future Improvements

Potential future improvements include:

- additional storage capacity;
- automated backups;
- monitoring system health;
- remote access through VPN;
- improved security mechanisms;
- integration with additional self-hosted services.
