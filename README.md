# IT Labs Portfolio

Documentation for my home lab projects focused on **CompTIA A+ Core 2**, **Network+**, **Security+**, and practical IT administration skills.

Built using **Oracle VirtualBox**, **Windows Server 2025**, **Windows 11**, and **Microsoft Azure**.

## Lab Projects

### Active Directory Domain Lab
**Completed**  
Multi-VM Windows Server 2025 Domain Controller + Windows 11 client.  
Configured AD DS, DNS, OUs, users/groups, security groups, file shares, and basic Group Policy.

**Skills Practiced:**
- Domain Controller promotion
- User and group management
- File sharing and permissions
- Domain join troubleshooting
- PowerShell for AD verification

**View Full Report:** [Active Directory Domain Lab](./Active-Directory/README.md)

---

### DHCP Lab (Azure)
**Completed**  
Deployed and configured a Windows Server 2025 DHCP server entirely in Microsoft Azure.

Created three scopes (Users LAN, Corporate Voice, Guest Wi-Fi), configured scope options (003 Router, 006 DNS Servers, 015 DNS Domain Name), added exclusions, and created reservations.

**Skills Practiced:**
- DHCP scope creation and management
- DHCP options configuration
- Exclusions vs Reservations
- Server-side validation using MMC and PowerShell
- Understanding Azure networking constraints

**View Full Report:** [DHCP Lab - Azure Implementation](./DHCP-Lab-Azure-Report.md)

---

### VirtualBox Base Setup
Optimized VirtualBox configuration for reliable lab environments (Guest Additions, networking, snapshots, performance tweaks).

**View Details:** [VirtualBox Base Setup](./VirtualBox-Setup/README.md)

---

### Linux Basics (Coming Soon)
Ubuntu server installation, networking, user management, SSH hardening, and package management.

### Troubleshooting Scenarios (Coming Soon)
Real-world troubleshooting exercises for Windows, networking, and Active Directory issues.

---

## Lab Topology (Current)

- **Active Directory Lab**: Windows Server 2025 DC + Windows 11 Client (VirtualBox – Host-Only + NAT)
- **DHCP Lab**: Single Windows Server 2025 VM in Microsoft Azure

---

## Technologies Used
- **Hypervisor**: Oracle VirtualBox
- **Cloud**: Microsoft Azure
- **Server OS**: Windows Server 2025 Standard Evaluation
- **Client OS**: Windows 11 Pro
- **Tools**: Active Directory, DHCP, PowerShell, Group Policy, File Sharing

---

**Goal:** Build strong practical skills for IT support, systems administration, and entry-level roles.

Last updated: April 2026
