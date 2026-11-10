# Active Directory Home Lab

### Project Status: Phase 1, Building the Domain

**Project started:** November 2026

## Project Objective
Build a Windows Active Directory environment from scratch to practice
identity and access management, help desk support tasks, and security
monitoring.

## Skills Demonstrated
- Virtualization and VM configuration (Oracle VirtualBox)
- Network planning and isolation
- VBoxManage command line
- Windows Server 2025 installation
- Boot and firmware troubleshooting

## Tooling Stack
- **Virtualization:** Oracle VirtualBox
- **Domain Controller:** Windows Server 2025 (Evaluation)
- **Client:** Windows 11 Enterprise (Evaluation)

## Lab Network Plan
| Item | Value |
|---|---|
| Domain name | lab.local |
| Network | VirtualBox NAT Network, 10.0.0.0/24 |
| DC01 | 10.0.0.10 (static) |
| CLIENT01 | DHCP from DC01 |
| DHCP scope | 10.0.0.100 to 10.0.0.200 |

## Lab Modules

### Module 1: Lab Network and Host Planning
- **Objective:** Confirm the host can run the lab, download the installer, and build an isolated lab network.
- **Status:** Complete ✅
- **What I Did:**
  - Checked host resources in Task Manager. The host has 40 GB of RAM, enough to run DC01, a client, and Wazuh at the same time.
  - Downloaded the Windows Server 2025 Evaluation ISO.
  - Created a NAT Network named AD-LAB on 10.0.0.0/24 using the VBoxManage command line tool.
  - Turned off DHCP on AD-LAB so DC01 can hand out addresses later. Two DHCP servers on one network cause address conflicts.
- **Skills:** Virtualization, network planning, VBoxManage CLI
- **Verification:**

*Host resources in Task Manager*

<img width="813" height="395" alt="Screenshot 2026-11-10 at 11 48 54 AM" src="https://github.com/user-attachments/assets/79cd79e8-34b4-41bf-8aab-aeec32b787bc" />


*AD-LAB NAT Network created with VBoxManage (DHCP disabled)*

<img width="1107" height="616" alt="DESCRIBE THIS SCREENSHOT" src="https://github.com/user-attachments/assets/3cee573d-37ba-4344-989f-97cc211b6566" />

### Module 2: Build the Domain Controller VM
- **Objective:** Create the DC01 virtual machine and install Windows Server 2025.
- **Status:** Complete ✅
- **What I Did:**
  - Created DC01 with 4 GB of RAM, 2 CPUs, and a 60 GB disk.
  - Connected DC01 to the AD-LAB NAT Network.
  - Installed Windows Server 2025 Standard Evaluation (Desktop Experience).
  - Took a snapshot named Fresh Install as a restore point.
- **Troubleshooting:**
  - The first ISO was a Windows 11 IoT client image, not Server. Downloaded the correct Server 2025 Evaluation ISO.
  - NAT Network was hidden in VirtualBox's Basic settings mode. Created AD-LAB with VBoxManage and switched Settings to Expert mode.
  - The VM froze during UEFI startup. Switched the firmware to BIOS, and the installer loaded.
- **Skills:** VM configuration, Windows Server installation, boot troubleshooting
- **Verification:**

*DC01 configuration summary*

<img width="812" height="395" alt="DC01 configuration summary" src="https://github.com/user-attachments/assets/0eee47b1-d760-4659-a895-d2092572e4b4" />

*Server 2025 ISO attached in DC01 storage settings*

<img width="793" height="531" alt="Server 2025 ISO attached to DC01" src="https://github.com/user-attachments/assets/69e6b027-eb09-4a80-9def-862e31fa798d" />

*DESCRIBE THIS SCREENSHOT*

<img width="1117" height="745" alt="DESCRIBE THIS SCREENSHOT" src="https://github.com/user-attachments/assets/a71f87b6-072e-48fe-9a82-509597601a40" />
