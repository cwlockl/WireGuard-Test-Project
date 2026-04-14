# WireGuard Home Lab Project
This project demonstrates a secure remote access solution for my Proxmox home lab using WireGuard.

![Network Diagram](your-filename-here.png)

## Overview
- **Gateway:** Netgear Nighthawk R6700AX
- **Server:** Proxmox LXC (Debian)
- **Client:** Samsung S24+

- ### **Security & Logic**
This deployment utilizes **Curve25519 Asymmetric Encryption**. Each endpoint (Server and Smartphone) generates a private/public key pair. Access is only granted when both sides have the other's Public Key registered, creating a zero-trust environment.

### **Network Capabilities**
- **Internal Mapping:** The WireGuard peer resides on the `10.0.0.0/24` subnet, allowing for remote network discovery and mapping using tools like Nmap.
- **Remote Administration:** Secure access to the Proxmox GUI (`10.0.0.3:8006`) and the Nighthawk Router (`10.0.0.1`) without exposing these management ports to the public internet.
- **Encapsulated Traffic:** All data is encapsulated in UDP packets, making the VPN connection look like standard traffic to outside observers.
