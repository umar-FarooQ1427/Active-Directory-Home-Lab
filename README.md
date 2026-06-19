# Active Directory Home Lab

## Overview

This project demonstrates the deployment and administration of a Windows Server 2022 Active Directory environment in a virtualized lab.

The lab was built to practice Active Directory administration, user and group management, DNS configuration, domain joining, network enumeration, and BloodHound analysis.

---

## Lab Environment

### Domain

- Domain Name: corp.local
- Domain Controller: DC01

### Machines

| Machine | Operating System | Purpose |
|----------|----------|----------|
| DC01 | Windows Server 2022 | Domain Controller |
| WIN11-01 | Windows 11 | Domain-Joined Workstation |
| Kali Linux | Kali Linux | Security Testing & Enumeration |

---

## Active Directory Structure

### Organizational Units

- Employees
- Admins
- Groups
- HR
- Finance
- IT
- Sales
- Marketing
- Service Accounts

### Groups

- HR_Users
- Finance_Users
- IT_Users
- Sales_Users
- Marketing_Users
- Workstation Admins
- Server Admins

---

## Tools Used

- Active Directory Users and Computers
- DNS Manager
- BloodHound
- BloodHound-Python
- Neo4j
- Nmap
- enum4linux
- Kali Linux

---

## Skills Demonstrated

- Active Directory Administration
- User and Group Management
- DNS Configuration
- Domain Joining
- LDAP Enumeration
- SMB Enumeration
- BloodHound Analysis
- Windows Server Administration

---

## BloodHound Analysis

BloodHound was used to collect and visualize Active Directory relationships, including:

- Users
- Groups
- Computers
- Organizational Units
- Group Policy Objects

---

## Screenshots

### Lab Architecture

![Lab Architecture](images/network-diagram.png)

### Active Directory Overview

![AD Overview](images/ad-overview.png)

### BloodHound Analysis

![BloodHound](images/bloodhound-graph.png)

---

## Learning Outcomes

Through this project I learned:

- Active Directory deployment and management
- User and group administration
- DNS configuration in enterprise environments
- Active Directory enumeration techniques
- BloodHound graph analysis
- Security assessment of AD environments

---
