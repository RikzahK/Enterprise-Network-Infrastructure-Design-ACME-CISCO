
# Global Enterprise Network Architecture — ACME Corporation
A Multi-Regional Cisco-Based Network Architecture with Subnetting, VLAN Segmentation, and Adaptive Routing.


---
<img width="1067" height="683" alt="image" src="https://github.com/user-attachments/assets/aecc1cd6-9a56-4ffa-bfd4-1fb825f02940" />

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
<img width="1234" height="750" alt="image" src="https://github.com/user-attachments/assets/fc60d69d-9bf8-46f3-9439-3f319738eafd" />


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
<img width="1051" height="458" alt="image" src="https://github.com/user-attachments/assets/7f9638ff-ea06-4b7d-945d-9dfe46bb7356" />
<img width="1040" height="203" alt="image" src="https://github.com/user-attachments/assets/e0174b48-7d26-431f-bcd7-ed89ebf408ea" />
IP ADDRESS:
IP address has been configured for all devices along with Static MAC Address Configuration. For critical
network devices such as servers and printers I have configured static MAC addresses on the ports, restrict
violation mode (will not accept traffic from the port resulted in violation & not shutdown as well) and set a
limit on maximum mac addresses allowed. Implementing port-security measures can help enhance network
PG:6
security and prevent unauthorized access to network resources. This ensures that only the specified devices
can connect to those ports, providing an additional layer of security
<img width="1053" height="383" alt="image" src="https://github.com/user-attachments/assets/3e8bf3a0-a99d-4336-b5fb-1a2aa2d1c929" />

Next, I have provided subnetting for each department (VLANs) and configured intra-VLAN for
communication within departments

<img width="1304" height="565" alt="image" src="https://github.com/user-attachments/assets/4871eb38-2cd7-4b3c-9051-3be8eb00a177" />

---
Why is RIP chosen over other Protocols?
RIP is a routing protocol used to route data over a computer network and chooses paths based on the number
of hops finding the most efficient way to route data over a network. It offers features such as fast convergence,
scalability, and efficient use of network resources. Most importantly, ACME can benefit from RIP's
scalability, accommodating their network growth and evolving needs.
RIP CONFIGURATION

<img width="1359" height="367" alt="image" src="https://github.com/user-attachments/assets/582a8972-15b2-4df6-805a-4d92de724e1f" />

Router configuration for security
<img width="1350" height="181" alt="image" src="https://github.com/user-attachments/assets/fe203766-2d80-4f10-bd14-a1b372dd7c3b" />

BUDGETING:
THE FOLLWING TABEL SIGGESTS BIDGETING FOR ACME The ACME Corporation network infrastructure utilizes professional-grade hardware, including the Synology RT2600ac router for high-performance VPN and security, Cisco Catalyst 9000 Series switches for enterprise VLAN management and advanced network control, and Dell OptiPlex 3020 PCs for reliable staff endpoints. Security appliances and wireless access points will be selected based on specific coverage and protection requirements, while Samsung Galaxy S22 Ultra smartphones provide high-end mobile connectivity, and printers will be chosen to meet corporate printing needs. Estimated costs for the defined devices are $272 for the router, $2,400 for switches, $800 per PC, and $1,000 per smartphone, with TBD items pending specification. 
<img width="692" height="598" alt="image" src="https://github.com/user-attachments/assets/065231bf-1a86-4806-8aa2-5760f4c8c804" />

SECURITY RECOMMENDATIONS:
In order to ensure a secure environment for ACME Corporation's operations, the following security
recommendations can be implemented:
 Implement Private VLANs: Private VLANs restrict communication between ports within the same
VLAN, increasing overall network security and providing enhanced security.
 Separate Management and User Data Traffic: It is crucial to separate management traffic from user data
traffic by assigning the management functions to a separate VLAN (to secure remote access for
administrative purposes), different from the VLAN used by regular users.
 secure remote access for administrative purposes.
 Implement strong user authentication mechanisms, such as two-factor authentication (2FA), to ensure
that only authorized individuals can access network resources. Additionally, establish access control
policies to define user privileges & restrict access to sensitive data based on job roles and responsibilities
 Utilize Encryption Techniques: Implement encryption mechanisms, such as Transport Layer Security
(TLS) or Secure Sockets Layer (SSL), to secure communication across offices and between departments.
Router configuration for security
PG:9
This ensures that data is protected during transit and mitigates the risk of unauthorized access or
eavesdropping.
 Implement Firewall Solutions: Deploy firewalls at network boundaries to control incoming and outgoing
traffic. Use firewall rules and access control policies to restrict access to network resources based on
security policies. This helps prevent unauthorized access and protects against external threats.
All these measures will further enhance the overall security posture of the ACME organization.

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
<img width="1645" height="394" alt="image" src="https://github.com/user-attachments/assets/827e8b32-872e-4fb9-821c-bbe8eea64d4c" />


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
