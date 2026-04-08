
# Global Enterprise Network Architecture — ACME Corporation
A Multi-Regional Cisco-Based Network Architecture with Subnetting, VLAN Segmentation, and Adaptive Routing.


---

## Overview

This repository documents a high-performance, secure, and scalable global network architecture designed for **ACME Corporation**. It spans three international offices (UK, US, India) and integrates hybrid network topologies, VLAN segmentation, dynamic routing, and cloud-based services to ensure enterprise-level reliability and security.

**Key Highlights:**
- Multi-Regional Deployment (UK, US, India)
- Hybrid Star–Mesh Topology
- VLAN-Based Department Segmentation
- Dynamic Routing with RIP
- Switch-Port Security and Access Control
- AWS Hybrid Cloud Integration

---

## 1. Organizational Scope & Requirements

| Office          | Staff | Departments (Staff Count)         |
|-----------------|-------|----------------------------------|
| UK (Regional HQ)| 300   | IT: 105, Finance: 105, HR: 90   |
| US Branch       | 200   | IT: 60, Finance: 70, HR: 70     |
| India Branch    | 100   | IT: 50, Finance: 25, HR: 25     |

**Objective:** Build a robust, scalable network to support inter-department communication, secure data handling, and global resource sharing.

---

## 2. Network Architecture & Topology

- **Intra-Branch (Star Topology):** Central switch connects all devices in each office  
- **Inter-Branch (Point-to-Point):** Dedicated P2P links connect routers via simulated cloud infrastructure  
- **VLAN Segmentation:** Isolates traffic to reduce broadcast domains and improve security  

| VLAN ID | Department | Purpose                          |
|---------|-----------|----------------------------------|
| 10      | IT        | Admin traffic, high-priority operations |
| 20      | HR        | Secure employee data traffic     |
| 30      | Finance   | Encrypted financial data streams |

**Visual Placeholder:**  
[Insert Global Network Topology Diagram here]

---

## 3. Technical Implementation

### IP Addressing & Subnetting
- Private IP Range: 172.16.0.0/16 (Class B)  
- Optimized with VLSM for efficient host allocation  

| Branch | Subnet          | Department | Hosts |
|--------|----------------|------------|-------|
| UK     | 172.16.10.0/24  | IT         | 254   |
| UK     | 172.16.11.0/25  | HR         | 126   |
| US     | 172.16.20.0/25  | IT         | 126   |
| US     | 172.16.21.0/26  | Finance    | 62    |
| India  | 172.16.30.0/26  | IT         | 62    |
| India  | 172.16.30.64/27 | HR         | 30    |

### Routing & Connectivity
- **Routing Protocol:** RIP v2 for dynamic path discovery  
- **IP Assignment:** DHCP for automated host configuration  
- **Domain Resolution:** DNS integrated for efficient name mapping  
- **Wireless:** IEEE 802.11 standards for Wi-Fi access  

**Visual Placeholder:**  
[Insert Ping Test / Connectivity Verification Screenshot]

---

## 4. Security Architecture

- Switch-Port Security: Sticky MAC addresses, Restrict mode  
- Traffic Isolation: VLAN separation between user and management traffic  
- Encryption: TLS/SSL for data in transit  
- Access Control: Role-Based Access Control (RBAC) and optional Two-Factor Authentication  
- Firewall: Dedicated firewalls at each branch perimeter  

**Visual Placeholder:**  
[Insert Security Configuration Diagram / Screenshot]

---

## 5. Hardware & Infrastructure Components

| Device    | Model                     | Purpose                               |
|-----------|---------------------------|---------------------------------------|
| Routers   | Synology RT2600ac         | Core routing and inter-branch connectivity |
| Routers   | Cisco ISR 331             | Regional backbone routing             |
| Switches  | Cisco Catalyst 9000 Series| L2/L3 switching, VLANs, trunking      |
| Endpoints | Dell OptiPlex 3020        | Staff desktops                         |
| Mobile    | Samsung Galaxy S22 Ultra  | Mobile endpoint testing                |
| Storage   | Central Database Server   | Centralized UK branch database        |

**Visual Placeholder:**  
[Insert Rack/Hardware Setup Image]

---

## 6. Cloud Strategy & Integration

Hybrid cloud approach ensures global resource availability:

| AWS Service | Purpose                                           |
|-------------|--------------------------------------------------|
| VPC         | Dedicated, isolated network environment          |
| S3          | Centralized object storage for cross-branch access |
| RDS         | Managed relational databases for HR and Finance  |
| CloudFront  | Secure, low-latency content delivery globally    |

**Visual Placeholder:**  
[Insert AWS Architecture Diagram]

---

## 7. Testing & Validation

- Successful inter-VLAN communication across all offices  
- Dynamic routing tables converged as expected  
- P2P inter-office connectivity verified  
- Security policies enforced via simulated attacks  

**Visual Placeholder:**  
[Insert Testing & Validation Screenshots]

---

## 8. Future Enhancements

- Transition from RIP → OSPF/BGP for large-scale routing efficiency  
- Network automation using Python (Netmiko / Paramiko)  
- AI-driven traffic monitoring and anomaly detection  
- Zero Trust Security Implementation  

---

## 10. Conclusion

This project delivers a secure, high-performance, and globally scalable network architecture that aligns with enterprise-level standards. It demonstrates:

- Effective VLAN segmentation and dynamic routing  
- Robust security measures at endpoints and network boundaries  
- Cloud-enabled cross-region resource sharing  
- Future-proof architecture ready for automation and AI integration
