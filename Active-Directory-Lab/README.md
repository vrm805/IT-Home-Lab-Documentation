# Active Directory & Windows Server 2022 Home Lab

## Overview
This lab simulates a small business IT environment using two Windows Server 2022 virtual machines in VirtualBox. The goal was to build hands-on experience with Active Directory Domain Services, networking fundamentals, and enterprise administration tasks.

## Environment
- **Platform:** VirtualBox
- **Operating System:** Windows Server 2022 (x2 VMs)
- **Domain:** victorslab.local
- **DC01:** Domain Controller
- **SERVER01:** Member Server

## What I Built

### Domain Controller Setup
- Installed Active Directory Domain Services and promoted DC01 to a Domain Controller
- Created the victorslab.local domain
- Configured static IP addressing and DNS

### User & Group Management
- Created user accounts (jsmith, mgarcia, bjones)
- Created security groups (IT_Staff, HR_Staff) and assigned appropriate members
- Configured Account Lockout Policy and practiced password reset procedures

### Organizational Units (OUs)
- Restructured the default Active Directory layout into IT Department, HR Department, and Workstations OUs
- Moved users, groups, and computers into appropriate OUs to reflect a real enterprise structure

### Group Policy Objects (GPOs)
- Created and linked a domain-wide login warning message policy
- Created a Block USB Storage policy and applied Security Filtering to scope it to the HR Department OU only, rather than the entire domain

### Networking Services
- Configured DHCP Server role with a defined scope, successfully tested automatic IP assignment
- Configured DNS Forwarders to route external DNS requests to Google's public DNS (8.8.8.8, 8.8.4.4)

### File Sharing & Permissions
- Created a shared network folder (CompanyShare) with NTFS permissions scoped to the IT_Staff group
- Mapped the shared folder as a network drive on the member server

### Remote Desktop Services
- Enabled and tested Remote Desktop Protocol (RDP) between DC01 and SERVER01
- Verified DNS resolution by connecting using the computer name instead of IP address

## Troubleshooting Highlights

**MAC Address Conflict:** After joining SERVER01 to the domain, both VMs were unable to communicate over the network. Diagnosed the issue by comparing `ipconfig /all` output on both machines and discovered both had identical MAC addresses inherited from being cloned off the same base image. Resolved by regenerating unique MAC addresses in VirtualBox network settings.

**SID Conflict:** After resolving the network issue, domain join attempts failed with an error indicating a duplicate Security Identifier (SID) — another symptom of improper VM cloning. Resolved by running Sysprep on the affected machine to generate a new, unique SID before rejoining the domain successfully.

## Skills Demonstrated
- Active Directory Domain Services administration
- Group Policy creation, linking, and Security Filtering
- DHCP and DNS configuration
- NTFS permissions and file sharing
- Remote Desktop Services configuration
- Systematic troubleshooting of real-world networking and cloning issues
