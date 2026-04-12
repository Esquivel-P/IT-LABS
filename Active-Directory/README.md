# Active Directory Home Lab - Windows Server 2025

**Project Overview**  
Built a functional multi-VM Active Directory domain environment in Oracle VirtualBox for CompTIA A+ / Network+ practice.

**Skills Practiced**  
- VirtualBox VM & networking setup  
- Windows Server 2025 Desktop Experience installation  
- Active Directory Domain Services installation and promotion  
- DNS, OU, user/group, and Group Policy configuration  
- Windows 11 client domain join  
- Troubleshooting domain join and GPO issues  

**Lab Topology**  
![AD Lab Topology](../diagrams/ad-topology.png)

### Environment Specs
| Component         | Details                                      |
|-------------------|----------------------------------------------|
| Hypervisor        | Oracle VirtualBox                            |
| Domain Controller | Windows Server 2025 Standard (Desktop Experience) |
| Client            | Windows 11 Pro                               |
| Networking        | Host-only Adapter (192.168.10.0/24)          |
| Domain Name       | `LAB.local`                                 |

### Key Steps Completed
- Installed Server 2025 with Desktop Experience
- Promoted server to Domain Controller
- Created OUs and test users/groups
- Configured basic GPOs
- Joined Windows 11 client to the domain

**Lessons Learned**  
- Importance of static IPs and correct DNS settings before domain join  
- Value of snapshots before major changes  
- GUI (Desktop Experience) makes initial learning much faster than Server Core

**Screenshots**  
- Server Manager with AD DS role  
- Active Directory Users and Computers  
- Group Policy Management Console  
- Domain join on Windows 11 client

---

*Last updated: April 2026*
