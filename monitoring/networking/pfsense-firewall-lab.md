# pfSense Firewall Lab (Proxmox)

## 📌 Overview
Built a virtual firewall environment using Proxmox, pfSense, and Ubuntu to simulate real-world network segmentation and routing.

---

## 🧱 Architecture
Internet (10.0.0.x)
│
Router
│
pfSense (WAN - vmbr0)
│
Firewall
│
pfSense (LAN - vmbr1 → 192.168.1.1)
│
Ubuntu VM (DHCP: 192.168.1.x)

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
