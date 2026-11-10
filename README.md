# Active Directory Home Lab

### Project Status: Phase 1, Building the Domain

## Project Objective
Build a Windows Active Directory environment from scratch to practice
identity and access management, help desk support tasks, and security
monitoring.

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

## Milestone Logs

### Day 1: Planning and Provisioning Prep
- **Task:** Check host resources, download ISOs, and document the network plan.
- **Status:** Complete ✅
- **Verification:**
