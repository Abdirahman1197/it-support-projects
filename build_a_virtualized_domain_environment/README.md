# 🖥️ Virtualized Domain Environment – Windows Server AD Lab

## 🎯 Objective

This project is based on a real-world deployment I carried out for a community-focused organization in Oslo, Norway. The objective was to simulate a corporate IT infrastructure using Windows Server technologies within a fully virtualized lab environment.

The project includes:
- A Windows Server domain controller (`DC-01`) with **Active Directory Domain Services (AD DS)**, **DNS**, and **DHCP**
- A Windows 11 client (`CLIENT-01`) joined to the custom domain (`yourname.lab`)
- Organizational Units (OUs) and users for departments like `Sales`, `IT`, and `Marketing`
- A fully isolated network for secure lab testing and training

---

## 🛠 Tools Used

| Tool | Purpose |
|------|---------|
| **VMware Workstation** | Created and managed virtual machines for the lab |
| **Windows Server 2019 / 2022** | Domain controller with AD DS, DNS, DHCP roles |
| **Windows 11** | Domain-joined client to test AD services |
| **Server Manager** | Installed server roles and managed configurations |
| **Active Directory Users and Computers (ADUC)** | Created users and Organizational Units |
| **DHCP Management Console** | Set up DHCP scope for client IP leasing |
| **VMware Host-Only Network (VMnet2)** | Isolated internal network for domain communication |
| **Static IP Configuration** | Ensured consistent domain controller address |
| **PowerShell / CMD** | Used for domain joining, diagnostics (`ipconfig`, `ping`, `nslookup`) |

---

## 🔧 Setup Overview

### 1. Domain Controller Setup (`DC-01`)
- Created Windows Server VM with 4 GB RAM, 2 CPUs, and static IP `192.168.50.10`
- Installed roles: Active Directory Domain Services, DNS, DHCP
- Promoted to domain controller for a new forest: `yourname.lab`

### 2. DHCP Configuration
- Created a DHCP scope: `192.168.50.100` – `192.168.50.200`
- Configured options: router `192.168.50.1`, DNS `192.168.50.10`

### 3. Client Setup (`CLIENT-01`)
- Windows 11 VM joined to same VMware Host-Only network
- Joined domain: `yourname.lab`
- Verified DHCP lease and login with domain users

### 4. Active Directory Structure
- Created OUs: `Sales`, `IT`, `Marketing`
- Created sample users: e.g., `jdoe`, `amadhi`, `bmohamed`
- Tested login and access from CLIENT-01 using these accounts

---

## 🧠 Skills Gained

- Deploying and managing Active Directory Domain Services (AD DS)
- Configuring DNS and DHCP in a virtual lab
- Creating and managing Organizational Units and domain users
- Joining clients to a domain and troubleshooting connectivity
- Building realistic IT infrastructure scenarios using virtualization

---

## 📸 Screenshots (Optional)

> You can include screenshots of:
> - Server Manager roles
> - DHCP scope settings
> - ADUC showing OUs and users
> - Command prompt verifying domain join and IP address

---

## 📝 Notes

- This environment was built entirely inside VMware Workstation with isolated networking  
- Based on a real-world deployment for a community-focused organization in Oslo  
- All data used in this demo is fictional and for educational purposes only
