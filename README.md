# ** Global Enterprise Network Architecture — ACME Corporation**

![Cisco](https://img.shields.io/badge/Cisco-Networking-blue?style=for-the-badge&logo=cisco)
![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazon-aws)
![VLAN](https://img.shields.io/badge/VLAN-Segmentation-red?style=for-the-badge)
![RIP](https://img.shields.io/badge/RIP-Routing-yellow?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-Automation-blue?style=for-the-badge&logo=python)
![FAANG Ready](https://img.shields.io/badge/FAANG-Portfolio-green?style=for-the-badge&logo=linkedin)

---
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/ca9dc432-4e33-4a93-b671-51ddf3145a30" />

## **Overview**

This repository documents a **high-performance, secure, and globally scalable network architecture** for **ACME Corporation**. The design spans **UK, US, and India offices**, integrating:

- Hybrid Star–Mesh Topology  
- VLAN-Based Department Segmentation  
- Dynamic Routing (RIP v2)  
- Switch-Port Security & Role-Based Access Control  
- Hybrid Cloud Integration (AWS VPC, S3, RDS, CloudFront)  

**Objective:** Enable **secure, efficient, and future-proof global communication** and inter-departmental resource sharing.

**Multi-Regional Staff Distribution**

| Office          | Staff | Departments (Staff Count)         |
|-----------------|-------|----------------------------------|
| UK (Regional HQ)| 300   | IT: 105, Finance: 105, HR: 90   |
| US Branch       | 200   | IT: 60, Finance: 70, HR: 70     |
| India Branch    | 100   | IT: 50, Finance: 25, HR: 25     |

---

## **Architecture & Topology**

- **Intra-Branch:** Star topology connecting devices within each office  
- **Inter-Branch:** Point-to-Point (P2P) links connecting regional routers  
- **VLAN Segmentation:** Departmental traffic isolation for security and performance

**VLAN Configuration**

| VLAN ID | Department | Purpose |
|---------|-----------|---------|
| 10      | IT        | Admin & high-priority traffic |
| 20      | HR        | Secure employee data traffic |
| 30      | Finance   | Encrypted financial data streams |

**Network Topology**

![Global Network Topology](https://github.com/user-attachments/assets/aecc1cd6-9a56-4ffa-bfd4-1fb825f02940)

---

## **Technical Implementation**

### **IP Addressing & Subnetting**

- **Private IP Range:** `172.16.0.0/16` (Class B)  
- **Subnetting:** Optimized with VLSM for efficient host allocation

| Branch | Subnet          | Department | Hosts |
|--------|----------------|------------|-------|
| UK     | 172.16.10.0/24  | IT         | 254   |
| UK     | 172.16.11.0/25  | HR         | 126   |
| US     | 172.16.20.0/25  | IT         | 126   |
| US     | 172.16.21.0/26  | Finance    | 62    |
| India  | 172.16.30.0/26  | IT         | 62    |
| India  | 172.16.30.64/27 | HR         | 30    |

### **Routing & Connectivity**

- **Routing Protocol:** RIP v2 for adaptive, hop-count-based routing  
- **IP Assignment:** DHCP for automated configuration  
- **Domain Resolution:** DNS integration  
- **Wireless:** IEEE 802.11 Wi-Fi standards

![Routing & Connectivity](https://github.com/user-attachments/assets/7f9638ff-ea06-4b7d-945d-9dfe46bb7356)

### **Security Measures**

- Static MAC addresses & **Restrict violation mode** on critical devices  
- VLAN-based traffic isolation  
- TLS/SSL encryption for all inter-office communication  
- Role-Based Access Control (RBAC) + optional Two-Factor Authentication  
- Firewalls at branch perimeters

---

## **Hardware & Infrastructure**

**Enterprise-Grade Devices & Estimated Costs**

| Device    | Model                     | Purpose | Cost (USD) |
|-----------|---------------------------|---------|------------|
| Router    | Synology RT2600ac         | Core routing & VPN | $272 |
| Router    | Cisco ISR 331             | Regional backbone routing | TBD |
| Switch    | Cisco Catalyst 9000 Series| VLANs & L2/L3 switching | $2,400 |
| Endpoints | Dell OptiPlex 3020        | Staff desktops | $800 |
| Mobile    | Samsung Galaxy S22 Ultra  | Mobile endpoints | $1,000 |
| Storage   | Central Database Server   | UK branch database | TBD |
| Security  | TBD                        | Network security appliance | TBD |
| Wireless  | TBD                        | Access points | TBD |

**Hardware Overview**

![Hardware Overview](https://github.com/user-attachments/assets/065231bf-1a86-4806-8aa2-5760f4c8c804)

---

## **Cloud Strategy**

Hybrid cloud ensures **high availability, security, and global access**:

| AWS Service | Purpose |
|-------------|---------|
| VPC         | Isolated, dedicated network environment |
| S3          | Centralized cross-branch object storage |
| RDS         | Managed HR/Finance databases |
| CloudFront  | Low-latency, secure content delivery |

**Cloud Architecture Placeholder**

![AWS Architecture Diagram](#)

---

## **Testing & Validation**

- Inter-VLAN communication verified across all branches  
- Dynamic routing convergence confirmed  
- P2P inter-office connectivity tested  
- Security enforcement validated through simulated attacks

![Testing & Validation](https://github.com/user-attachments/assets/827e8b32-872e-4fb9-821c-bbe8eea64d4c)

---

## **Future Enhancements**

- Upgrade RIP → OSPF/BGP for advanced scalability  
- Python-based automation with Netmiko / Paramiko  
- AI-driven traffic monitoring and anomaly detection  
- Zero Trust Security Architecture

---

## **Conclusion**

This project delivers a **secure, scalable, and globally connected network** for ACME Corporation:  

- VLAN segmentation & adaptive routing for optimized traffic  
- Endpoint and perimeter security best practices  
- Cloud-enabled cross-region collaboration  
- Future-proof architecture ready for AI and automation
