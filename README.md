# Home Infrastructure Lab

## Overview
This repository documents my personal homelab built to develop hands-on skills related to data center, virtualization, Linux administration, storage, and networking.

## Core Technologies
- Proxmox VE
- Ubuntu Server
- Hardware RAID 10
- Netdata Monitoring
- Virtual Machines
- Linux Networking

## Current Infrastructure

### Hypervisor
- Proxmox VE

### Storage
- Dell PERC H710P Mini hardware RAID controller
- RAID 10 using 4 SAS drives
- RAID validated in controller BIOS
- Proxmox reads the array as a single logical disk

### Virtual Machines
- **100 - infra-netdata**: Monitoring VM running Netdata
- **101 - template-ubuntu-base**: Ubuntu template used for cloning new VMs
- **102 - app-docker**: Docker server
- **103 - net-pfsense**: pfSense firewall VM
- **104 - test-firewall**: Ubuntu firewall testing VM
- **105 - app-jellyfin**: Jellyfin media server with dedicated storage
![IMG_A8D568CC-CC71-4296-8966-8C0A7D8EA6D4](https://github.com/user-attachments/assets/ee1b76a1-5392-4334-84c8-c921dc828355)

## Featured Work

### Jellyfin Media Server
Deployed Jellyfin in its own Ubuntu VM with a dedicated 600GB virtual disk mounted at `/media/jellyfin`.

Documented here: [Jellyfin Deployment](docs/services/jellyfin.md)

## Skills Demonstrated
- Hardware RAID configuration and validation
- Proxmox virtualization and VM management
- Ubuntu template creation and VM cloning
- Linux disk partitioning and ext4 filesystem setup
- Persistent storage configuration with `/etc/fstab`
- Monitoring setup with Netdata
- Troubleshooting:
  - disk detection issues
  - mount persistence warnings
  - repository and DNS issues
  - installer script redirect problems

## Lab Goals
- Build production-style infrastructure
- Improve troubleshooting ability
- Learn storage, networking, and monitoring workflows
- Create projects that reflect real-world IT and data center tasks
- Deploy Linux servers
- Troubleshoot networking
- Implement monitoring systems
- Build production-style infrastructure
