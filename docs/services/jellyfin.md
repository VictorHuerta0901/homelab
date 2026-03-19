# Jellyfin Media Server Deployment

## Overview
Deployed Jellyfin in a dedicated Ubuntu VM on Proxmox with attached persistent storage.

## VM Details
- VM ID: 105
- Role: Jellyfin media server
- OS: Ubuntu

## Storage Setup
A second virtual disk was added to the Jellyfin VM through Proxmox.

Inside the VM:
- verified the new disk with `lsblk`
- created a partition on `/dev/sdb`
- formatted `/dev/sdb1` with ext4
- mounted the disk at `/media/jellyfin`

## Persistence
To make sure the disk stayed mounted after reboot, `/etc/fstab` was updated with:

`/dev/sdb1 /media/jellyfin ext4 defaults 0 0`

Then the mount was tested using:
- `sudo systemctl daemon-reload`
- `sudo mount -a`
- `df -h`

## Result
Jellyfin now uses dedicated storage separate from the operating system disk.

## Problems Solved
- New disk did not appear at first because it had not been added in Proxmox
- Initial mount persistence test showed a reload warning
- A typo in the mount command had to be corrected
- Verified final mount successfully with `df -h`

## Skills Demonstrated
- Proxmox VM storage management
- Linux disk partitioning
- ext4 filesystem creation
- mount point management
- persistent storage configuration with fstab
- troubleshooting command and configuration errors
