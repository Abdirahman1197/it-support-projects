# DC01 Installation & Configuration Guide

This repository contains a complete, illustrated walkthrough for installing and configuring **DC01** (a Windows Server Domain Controller) for an enterprise lab.  
It includes **VM setup, AD DS promotion, DHCP configuration**, and a **firewall hardening** script.

---

## 📑 Table of Contents
- [Introduction](#introduction)
- [Step-by-Step Setup](#step-by-step-setup)
- [Firewall Hardening](#firewall-hardening)
- [Verification & Next Steps](#verification--next-steps)

---

## Introduction
What you’ll find here:
- 📷 **Full step-by-step screenshots** in `/screenshots/`
- 📘 A **PDF guide** (if included) for offline reading
- 🛡️ `dc01-firewall-hardening.ps1.txt` with Windows Firewall rules

---

## Step-by-Step Setup
_(Screenshots folder empty in this bundle.)_ 

---

## Firewall Hardening

A PowerShell snippet applied on the DC to ensure DNS/RPC rules are open on all profiles:

```powershell
# Enable DNS and RPC firewall rules
Enable-NetFirewallRule -DisplayName "DNS (UDP, Incoming)","DNS (TCP, Incoming)"
Set-NetFirewallRule -DisplayName "DNS (UDP, Incoming)","DNS (TCP, Incoming)" -Profile Any

# Enable RPC
Enable-NetFirewallRule -DisplayName "RPC (TCP, Incoming)","RPC Endpoint Mapper (TCP, Incoming)"
Set-NetFirewallRule -DisplayName "RPC (TCP, Incoming)","RPC Endpoint Mapper (TCP, Incoming)" -Profile Any
```

See the full script in: **`dc01-firewall-hardening.ps1.txt`**.

---

## Verification & Next Steps
- ✅ AD DS and DNS running without errors (`dcdiag`, `Get-Service DNS`)
- ✅ DHCP scope hands out addresses correctly (`Get-DhcpServerv4Scope`)
- ✅ Join a Windows client to the domain and log on with a domain user
- 🔜 Prepare to integrate **FS01** (File Server) and **WSUS**

---

**Prepared by:** Abdirahman A. Mohamed
