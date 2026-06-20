# Active Directory Home Lab

## Project Overview

This project demonstrates the deployment and administration of a Windows Server 2022 Active Directory environment in a virtualized lab environment.

The objective of this lab is to gain hands-on experience with Active Directory administration, user and group management, DNS configuration, domain joining, network enumeration, and Active Directory security analysis using BloodHound.

---

## Lab Architecture

### Network Diagram

```text
                +----------------+
                |  Kali Linux    |
                | 192.168.100.X  |
                +--------+-------+
                         |
                         |
        -----------------------------------
                         |
                         |
                +--------+-------+
                |     DC01       |
                | Windows Server |
                | 192.168.100.10 |
                | corp.local     |
                +--------+-------+
                         |
                         |
                +--------+-------+
                |   WIN11-01     |
                | Windows 11     |
                | 192.168.100.20 |
                +----------------+
```

---

## Lab Environment

### Domain Information

| Component | Value |
|------------|---------|
| Domain Name | corp.local |
| Domain Controller | DC01 |
| DNS Server | DC01 |
| Client Machine | WIN11-01 |
| Attacker Machine | Kali Linux |

---

## Virtual Machines

### DC01

- Windows Server 2022
- Active Directory Domain Services (AD DS)
- DNS Server
- Domain Controller

### WIN11-01

- Windows 11
- Domain Joined Workstation

### Kali Linux

- BloodHound
- Neo4j
- Nmap
- Enum4Linux
- SMB Enumeration Tools
- LDAP Enumeration Tools

---

## Active Directory Structure

### Organizational Units (OUs)

- HR
- Finance
- IT
- Sales
- Marketing
- Service Accounts
- Admins
- Groups
- Servers
- Workstations

### Security Groups

- HR_Users
- Finance_Users
- IT_Users
- Sales_Users
- Marketing_Users
- Workstation Admins
- Server Admins

### User Accounts

Examples:

- sarah.hr
- ali.finance
- ahmed.it
- hamza.sales
- zara.marketing

### Service Accounts

- svc_sql
- svc_backup
- svc_monitor

---

## Technologies Used

### Infrastructure

- Oracle VirtualBox
- Windows Server 2022
- Windows 11
- Kali Linux

### Active Directory

- Active Directory Domain Services
- DNS
- LDAP
- Kerberos
- SMB

### Security Tools

- BloodHound
- BloodHound CE Python
- Neo4j
- Nmap
- Enum4Linux
- SMBClient

---

## Active Directory Deployment

### Domain Controller Installation

- Installed Windows Server 2022
- Configured static IP address
- Installed AD DS role
- Promoted server to Domain Controller
- Created corp.local domain

### DNS Configuration

- Configured Forward Lookup Zone
- Verified DNS resolution
- Verified LDAP service records

### Client Deployment

- Installed Windows 11
- Joined workstation to corp.local
- Logged in using domain users

---

## Enumeration Activities

### DNS Enumeration

```bash
nslookup corp.local 192.168.100.10
```

### LDAP Service Discovery

```bash
nslookup -type=SRV _ldap._tcp.dc._msdcs.corp.local 192.168.100.10
```

### Network Scanning

```bash
nmap -sV -p 53,88,135,139,389,445,464,636,3268,3269 192.168.100.10
```

### SMB Enumeration

```bash
smbclient -L //192.168.100.10 -N
```

### Domain Enumeration

```bash
enum4linux 192.168.100.10
```

---

## BloodHound Analysis

BloodHound was used to collect and analyze Active Directory relationships.

### Data Collection

```bash
bloodhound-python \
-d corp.local \
-u USERNAME \
-p PASSWORD \
-ns 192.168.100.10 \
-c All
```

### Analysis Goals

- User Enumeration
- Group Enumeration
- Computer Enumeration
- Privilege Analysis
- Attack Path Discovery
- Domain Administration Mapping

---

## Screenshots

### VirtualBox Environment

![VirtualBox](images/virtualbox-lab.png)

### Active Directory Overview

![AD Overview](images/ad-overview.png)

### Organizational Units

![OUs](images/ous-structure.png)

### Users

![Users](images/users.png)

### Groups

![Groups](images/groups.png)

### DNS Configuration

![DNS](images/dns.png)

### Domain Join

![Domain Join](images/domain-join.png)

### BloodHound Dashboard

![BloodHound Dashboard](images/bloodhound-dashboard.png)

### BloodHound Analysis

![BloodHound Graph](images/bloodhound-graph.png)

### Nmap Scan

![Nmap](images/nmap-scan.png)

---

## Skills Demonstrated

### Active Directory

- Active Directory Administration
- Organizational Unit Management
- User and Group Administration
- Domain Management
- DNS Administration

### Security Operations

- Network Enumeration
- SMB Enumeration
- LDAP Enumeration
- Attack Surface Mapping
- BloodHound Analysis

### Windows Administration

- Windows Server Deployment
- Domain Controller Configuration
- Domain Joining
- Account Management

---

## Learning Outcomes

Through this project I gained practical experience in:

- Building an Active Directory environment from scratch
- Configuring Domain Controllers
- Managing users, groups, and permissions
- Performing Active Directory enumeration
- Understanding Kerberos and LDAP services
- Visualizing AD relationships using BloodHound
- Analyzing potential privilege escalation paths

---

## Future Improvements

Planned enhancements include:

- Additional Domain Controllers
- Group Policy Objects (GPOs)
- File Server Deployment
- Service Account Hardening
- Kerberoasting Lab
- AS-REP Roasting Lab
- Privilege Escalation Scenarios
- Full Red Team Simulation

---

## Author

Umar Farooq

Cybersecurity Student | Active Directory Security | Penetration Testing | Blue Team & Red Team Learning
