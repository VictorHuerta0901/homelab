# Architecture Overview

## Host
- Proxmox VE running on Dell server hardware
- Hardware RAID 10 configured via PERC controller

## Virtual Machines
- Monitoring (Netdata)
- Application servers (Jellyfin, Docker)
- Networking (pfSense)
- Testing environment

## Storage Flow
Physical disks → RAID controller → Proxmox → VM disk → mounted filesystem → application

## Key Concept
Separation of layers:
- hardware
- hypervisor
- guest OS
- application
