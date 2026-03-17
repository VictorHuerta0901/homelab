# pfSense Firewall Lab (Proxmox)

## 📌 Overview
Built a virtual firewall environment using Proxmox, pfSense, and Ubuntu to simulate real-world network segmentation and routing.

---

## Overview
Built a segmented virtual network in Proxmox using pfSense as the firewall and Ubuntu as a client VM on an isolated LAN.

## Architecture
- vmbr0 = WAN / home network
- vmbr1 = LAN / isolated lab network
- pfSense WAN = DHCP on 10.0.0.x
- pfSense LAN = 192.168.1.1/24
- Ubuntu client = DHCP on 192.168.1.x

## Problem Encountered
Initial connectivity failed because:
- pfSense WAN and LAN were placed on the same subnet
- DHCP was not properly enabled on the LAN
- Client VM had no IP address and could not reach the firewall

## Troubleshooting Steps
1. Verified Proxmox bridge assignments
2. Created isolated LAN bridge (vmbr1)
3. Reassigned pfSense LAN to vmbr1
4. Reconfigured pfSense LAN to 192.168.1.1/24
5. Enabled DHCP range 192.168.1.100–192.168.1.200
6. Restarted pfSense and client VM
7. Verified DHCP lease and connectivity from Ubuntu

## Final Working State
- Ubuntu received IP address 192.168.1.101
- Successful ping to 192.168.1.1
- Successful ping to 8.8.8.8
- Successful DNS resolution to google.com

## Skills Demonstrated
- Proxmox virtual networking
- Firewall configuration
- DHCP troubleshooting
- Network segmentation
- Layer 3 connectivity validation

## Screenshots
- Ubuntu `ip a` 
- Successful ping to pfSense
- Successful ping to public internet
- pfSense LAN configuration
---

## ⚙️ Configuration

### Proxmox
- vmbr0 → WAN (external network)
- vmbr1 → LAN (isolated network)

### pfSense
- WAN: DHCP (10.0.0.x)
- LAN: Static (192.168.1.1/24)
- DHCP Range: 192.168.1.100–192.168.1.200

### Ubuntu
- Connected to vmbr1
- Receives IP via DHCP

---

## 🧪 Testing

### Check IP
```bash
ip a
ping 192.168.1.1

ping 8.8.8.8
ping google.com
