# DC01 Installation & Configuration Guide

A step-by-step illustrated guide for setting up a Domain Controller (DC01) in a virtualized enterprise lab environment.  
This project demonstrates installation, configuration of Active Directory, DHCP, and basic firewall hardening.

---

## 📑 Table of Contents
- [Introduction](#introduction)
- [Step-by-Step Setup](#step-by-step-setup)
- [Firewall Hardening](#firewall-hardening)
- [Verification & Next Steps](#verification--next-steps)

---

## Introduction
This guide documents the installation, setup, and configuration of a Domain Controller (DC01).  
It covers:
- Creating the VM
- Installing the OS
- Configuring Active Directory Domain Services
- Setting up DHCP
- Applying firewall hardening

Screenshots are included for each step.

---

## Step-by-Step Setup

### Step 1 – Choose how to install VM
![Step 1](./screenshots/Step-1-Choose-how-to-install-vm.png)

### Step 2 – Choose Operating System
![Step 2](./screenshots/Step-2-Choose-Operating-Sytem.png)

### Step 10 – Set Admin Password
![Step 10](./screenshots/Step-10-Set-Admin-Password.png)

### Step 14 – Add AD Role
![Step 14](./screenshots/Step-14-Add-AD-Role.png)

### Step 15 – Root Domain Name
![Step 15](./screenshots/Step-15-Root-Domain-Name.png)

### Step 16 – DSRM Password
![Step 16](./screenshots/Step-16-DSRM-Pass.png)

### Step 18 – Promote Server
![Step 18](./screenshots/Step-18-Promote-Server.png)

### Step 21 – Set IPv4 Manually
![Step 21](./screenshots/Step-21-Set-IPV4-Manually.png)

### Step 22 – Add DHCP Server Role
![Step 22](./screenshots/Step-22-DHCP-Server-Role.png)

### Step 23 – Install DHCP Server
![Step 23](./screenshots/Step-23-Install-DHCP-Server.png)

### Step 25 – Enable Shared File (VMware)
![Step 25](./screenshots/Step-25-Enable-Sharedfile-Vmware.png)

### Step 26 – Confirm Shared File in DC01
![Step 26](./screenshots/Step-26-Confirm-file-in-DC01.png)

*(Add all steps you want here – keep screenshots in `/screenshots/` folder.)*

---

## Firewall Hardening

A PowerShell script was applied to secure DC01. Example:

```powershell
# Enable DNS and RPC firewall rules
Enable-NetFirewallRule -DisplayName "DNS (UDP, Incoming)","DNS (TCP, Incoming)"
Set-NetFirewallRule -DisplayName "DNS (UDP, Incoming)","DNS (TCP, Incoming)" -Profile Any

# Enable RPC
Enable-NetFirewallRule -DisplayName "RPC (TCP, Incoming)","RPC Endpoint Mapper (TCP, Incoming)"
Set-NetFirewallRule -DisplayName "RPC (TCP, Incoming)","RPC Endpoint Mapper (TCP, Incoming)" -Profile Any
```

*(See `dc01-firewall-hardening.ps1.txt` for the full script.)*

---

## Verification & Next Steps
After completing the installation and configuration:
- ✅ Verify Active Directory and DNS functionality  
- ✅ Ensure DHCP assigns IP addresses correctly  
- ✅ Join a Windows client to the domain  
- ✅ Prepare for integration with File Server (FS01) and WSUS  

---

## 📌 Prepared by
**Abdirahman A. Mohamed**  
_DC01 Installation & Configuration Guide_
