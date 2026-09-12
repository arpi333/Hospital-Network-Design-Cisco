# 🏥 Smart Multi-Speciality Hospital Network Using Cisco Packet Tracer

## 📌 Project Overview

This project presents the design and implementation of a Smart
Multi-Speciality Hospital Network using Cisco Packet Tracer.

The proposed network connects a Main Hospital Headquarters with
five specialized hospital branches:

- Main Hospital HQ
- Diagnostic Center
- Emergency Clinic
- Telemedicine
- Maternity Hospital
- Children Care Hospital

The network is designed to provide reliable communication,
efficient resource sharing, secure access, scalability, and
Internet connectivity between different hospital sites and
departments.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Design a multi-site hospital network.
- Develop an efficient IP addressing scheme using VLSM.
- Implement VLANs for departmental network segmentation.
- Configure inter-VLAN routing using Router-on-a-Stick.
- Implement DHCP for automatic IP address assignment.
- Configure EIGRP for dynamic routing between hospital sites.
- Implement NAT/PAT for Internet connectivity.
- Configure ACLs for controlled network access.
- Configure required network services.
- Test and troubleshoot the complete network.
- Develop a reliable, secure, scalable, and manageable network.

---

## 🏗️ Network Architecture

The network consists of six hospital sites connected through an
ISP router.

Each hospital site contains:

- Edge Router
- Core Router
- Access Switch
- End Devices
- Departmental VLANs
- Network Services where required

The Edge Routers provide connectivity toward the ISP, while the
Core Routers connect the departmental networks.

Router-on-a-Stick is used for inter-VLAN communication, and EIGRP
provides dynamic routing between hospital sites.

NAT/PAT is configured on the Edge Routers to provide Internet
connectivity for internal networks.

---

## 🏥 Hospital Sites

| Site | Main Network Segments |
|------|------------------------|
| Main Hospital HQ | DMZ, Doctors & ICU, Billing & Admin, Guest Wi-Fi |
| Diagnostic Center | Laboratory, Admin, Staff |
| Emergency Clinic | Emergency, Admin, IP Phone |
| Telemedicine | Consultation, Admin, Wi-Fi |
| Maternity Hospital | Maternity, Admin, Wi-Fi |
| Children Care Hospital | Children Care, Admin, Wi-Fi |

---

## 🛠️ Technologies & Networking Concepts

The following networking technologies and concepts were used:

- Cisco Packet Tracer
- IPv4
- VLSM
- VLAN
- Router-on-a-Stick
- Inter-VLAN Routing
- EIGRP
- DHCP
- NAT/PAT
- Access Control Lists (ACL)
- DNS
- HTTP
- FTP
- SMTP/POP3 Email
- Ping
- Traceroute
- Packet Tracer Simulation Mode

---

## 🌐 IP Addressing & VLSM

VLSM-based IPv4 addressing was used to allocate IP addresses
according to the requirements of different departments and
network segments.

The project uses:

- `200.1.1.0/24` for ISP-to-Edge Router connections.
- `10.255.0.0/24` for Edge-to-Core Router connections.
- `10.0.0.0/8` private addressing for internal hospital networks.

Point-to-point router connections use `/30` subnets.

VLSM helps use the available IP address space efficiently and
supports future network expansion.

---

## 🔐 VLAN Configuration

VLANs are used to separate different departments and network
segments within the hospital sites.

### Main Hospital HQ VLANs

| VLAN ID | VLAN Name | Network |
|---------|-----------|---------|
| 10 | DMZ | 10.0.1.160/28 |
| 20 | DOCTORS_ICU | 10.0.1.64/26 |
| 30 | BILLING_ADMIN | 10.0.1.0/26 |
| 50 | GUEST_WIFI | 10.0.0.0/24 |

Other hospital sites also use separate VLANs for their respective
departments and services.

---

## 🔄 Inter-VLAN Routing

Router-on-a-Stick is used to enable communication between
different VLANs.

The Core Router uses sub-interfaces for different VLANs, allowing
devices from separate departmental networks to communicate when
permitted.

---

## 🚦 EIGRP Dynamic Routing

EIGRP is configured to provide dynamic route exchange between the
six hospital sites.

**EIGRP Autonomous System:**

```text
AS 100
