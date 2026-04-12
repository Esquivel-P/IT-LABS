# VirtualBox Base Setup for IT Labs

**Project Overview**  
Configured Oracle VirtualBox as the primary hypervisor for reliable, reproducible home labs (Windows Server, Windows 11 client, future Linux VMs, Active Directory, etc.).

**Skills Practiced**  
- VirtualBox installation and Extension Pack setup  
- Optimal VM settings for Windows Server 2025 and Windows 11  
- Networking configuration (NAT + Host-only)  
- Guest Additions installation and troubleshooting  
- Snapshot strategy and performance tuning  
- Avoiding common issues (black screen, unattended install, Hyper-V conflicts)

### Environment Details
- **Host OS**: Windows 11 (12 cores, 16+ GB RAM recommended)
- **VirtualBox Version**: 7.2.6 r172322 (Qt6.8.0 on windows)
- **Extension Pack**: Installed (same version as VirtualBox)

### Recommended VM Settings (Used for This Lab)

| Setting                  | Recommended Value                          | Reason |
|--------------------------|--------------------------------------------|--------|
| OS Type                  | Windows 11 (64-bit)                        | Better compatibility with Server 2025 setup |
| RAM                      | 6–8 GB (DC), 4–6 GB (Client)               | Smooth performance without starving host |
| CPU Cores                | 4 cores                                    | Good balance |
| Graphics Controller      | VMSVGA (or VBoxSVGA)                       | Prevents black screens during install |
| Video Memory             | 128 MB                                     | Maximum for best display |
| 3D Acceleration          | Disabled until after Guest Additions       | Avoids early install issues |
| EFI                      | Enabled                                    | Required for modern Windows/Server |
| Networking               | Adapter 1: NAT (internet)<br>Adapter 2: Host-only (lab network) | Internet + isolated communication |
| Hard Disk                | 60 GB dynamic VDI                          | Grows as needed |

### Key Steps Performed

1. **Installed VirtualBox + Extension Pack**
2. **Created VMs with correct settings** (avoided unattended installation checkbox)
3. **Installed Windows Server 2025 Standard (Desktop Experience)**
4. **Installed Windows 11 Pro client**
5. **Installed Guest Additions** on both VMs for:
   - Seamless mouse integration
   - Shared clipboard
   - Better resolution / fullscreen
   - Shared folders (optional)
6. **Configured networking**:
   - Host-only Adapter for isolated 192.168.10.0/24 network
   - Static IPs on VMs
7. **Snapshot strategy**:
   - "Clean Install"
   - "After Guest Additions"
   - "Before Domain Promotion"
   - "After GPO Testing"

### Common Issues Encountered & Fixes
- **Black screen after install** → Changed Graphics Controller to VMSVGA + max video memory
- **Edition selection skipped** → Unchecked "Proceed with Unattended Installation"
- **Guest Additions not working** → Ran installer after first boot + reboot
- **Hyper-V conflict** → Disabled Hyper-V in Windows Features on host

### Lessons Learned
- Always disable unattended installation when you want full control over edition selection
- Guest Additions are critical for a good lab experience
- Taking snapshots before major changes saves hours of rework
- Setting OS Type to "Windows 11 (64-bit)" improves compatibility with Server 2025

**Screenshots** (add later):
- VirtualBox VM settings (Display tab)
- Guest Additions installation
- Host-only network configuration
- Snapshot manager

---

*Last updated: April 2026*  
Part of [IT-Labs Portfolio](https://github.com/Esquivel-P/IT-Labs)
