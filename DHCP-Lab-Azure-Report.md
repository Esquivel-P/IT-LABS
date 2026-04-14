# DHCP Lab - Azure Implementation (Jake's Tech Labs)

**Date:** April 2026  
**Student:** Patrick E  
**Platform:** Microsoft Azure (Windows Server 2025 Datacenter)

## Lab Objective
The goal of this lab was to deploy and configure a fully functional DHCP server on Windows Server 2025 in Azure, replicating the steps from Jake's Tech Labs DHCP guide. Key focus areas included:
- Creating multiple scopes for different network segments (Users, Corporate Voice, Guest Wi-Fi)
- Configuring scope options (Router, DNS, Domain Name)
- Implementing exclusions and reservations
- Validating the server-side configuration

## 1. Azure Infrastructure Setup

A dedicated environment was provisioned to host the DHCP server:

- **Resource Group**: `rg-dhcp-lab`
- **Virtual Network**: `vnet-dhcp-lab` (10.0.0.0/16)
- **Virtual Machine**: `dc1` (Standard D2s v3, Windows Server 2025 Datacenter)

![Resource Group](images/01-resource-group.png)

![Virtual Network](images/02-virtual-network.png)

![VM Creation - Basics](images/03-vm-creation-basics.png)

![VM Networking Tab](images/04-vm-networking.png)

RDP access was enabled and the connection file was downloaded.

![RDP Connection](images/05-rdp-file.png)

Inside the VM, the assigned private IP was verified using `ipconfig`.

![ipconfig](images/06-ipconfig-inside-vm.png)

## 2. DHCP Server Role Installation

The DHCP Server role was installed through Server Manager.

![Server Manager Dashboard](images/07-server-manager-dashboard.png)

![DHCP Role Added](images/08-dhcp-role-installed.png)

## 3. DHCP Scope Configuration

Three IPv4 scopes were created and activated:

- **Users LAN**: 192.168.1.0/24 (8-hour lease)
- **Corporate Voice**: 192.168.2.0/24 (1-day lease)
- **Guest Wi-Fi**: 192.168.3.0/24 (2-hour lease)

All scopes were confirmed **Active**.

![All Scopes Active](images/09-all-scopes-active.png)

## 4. Scope Options Configuration

The following standard options were configured on each scope:

- **003 Router** — Set to the appropriate `.254` gateway address per scope (e.g., 192.168.1.254)
- **006 DNS Servers** — Pointed to the domain controller at `10.0.0.4`
- **015 DNS Domain Name** — `lab.local`

These options ensure clients receive correct gateway, DNS, and domain information during the DORA process.

![Scope Options](images/10-scope-options.png)

## 5. Address Exclusions

Exclusion ranges were added to prevent the DHCP server from assigning IPs to known static devices or infrastructure:

- Example: Guest Wi-Fi exclusion `192.168.3.50 – 192.168.3.60`

![Address Pool with Exclusions](images/11-address-pool-exclusion.png)

## 6. DHCP Reservations

A reservation was created for a printer to guarantee a consistent IP address while keeping management centralized:

- **Name**: Printer-01
- **IP Address**: 192.168.1.25
- **MAC Address**: Placeholder value

![Printer-01 Reservation](images/15-reservation.png)

## 7. Validation & Verification

Configuration was validated through multiple methods:
- GUI confirmation that scopes were Active
- Right-click context menu showing Deactivate option (proof of active state)
- PowerShell command `Get-DhcpServerv4Scope`
- Services.msc confirming the DHCP Server service was Running and set to Automatic

![Scope Deactivate Menu](images/12-scope-deactivate-menu.png)

![PowerShell Validation](images/13-powershell-validation.png)

![DHCP Service Running](images/14-dhcp-service-running.png)

## Azure-Specific Considerations
In Azure, the virtual machine receives its own IP from Azure's platform DHCP. Therefore, this lab emphasized **server-side configuration only**. In a real on-premises or hybrid environment, client devices would lease addresses directly from this DHCP server.

## Key Takeaways & Skills Demonstrated
- Full understanding of the DHCP DORA process and scope-based design
- Proper configuration of scope options (003, 006, 015) and their importance for client connectivity
- Difference between **exclusions** (protect static/infrastructure IPs) and **reservations** (centrally managed static assignments)
- Hands-on experience with Windows Server DHCP MMC snap-in and supporting PowerShell cmdlets
- Experience deploying infrastructure in Azure while managing costs (deallocation + resource group deletion)

## Cleanup
- VM was stopped and deallocated
- Resource group `rg-dhcp-lab` was deleted to prevent ongoing charges

---
