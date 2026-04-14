# DHCP Lab - Azure Implementation (Jake's Tech Labs)

**Date:** April 2026  
**Student:** Changli (IchiXRuki1415)

## Lab Objective
Configure a Windows Server 2025 DHCP server in Microsoft Azure with multiple scopes, exclusions, scope options, and a reservation.

## 1. Azure Environment Setup

Created resource group `rg-dhcp-lab`, virtual network `vnet-dhcp-lab`, and Windows Server VM (`dc1`).

![Resource Group](Images/01-resource-group.png)

![Virtual Network](Images/02-virtual-network.png)

![VM Creation - Basics](Images/03-vm-creation-basics.png)

![VM Networking Tab](Images/04-vm-networking.png)

Downloaded RDP file and connected to the VM.

![RDP Connection](Images/05-rdp-file.png)

Verified internal IP address inside the VM.

![ipconfig](Images/06-ipconfig-inside-vm.png)

## 2. DHCP Server Role Installation

Installed DHCP Server role via Server Manager.

![Server Manager Dashboard](Images/07-server-manager-dashboard.png)

![DHCP Role Added](Images/08-dhcp-role-installed.png)

## 3. DHCP Scopes

Created and activated three scopes:
- **Users LAN** – 192.168.1.0/24
- **Corporate Voice** – 192.168.2.0/24
- **Guest Wi-Fi** – 192.168.3.0/24

![All Scopes Active](Images/09-all-scopes-active.png)

## 4. Scope Options

Configured essential options on each scope:
- **003 Router**: 192.168.x.254  
- **006 DNS Servers**: 10.0.0.4 (dc1)  
- **015 DNS Domain Name**: lab.local

![Scope Options](Images/10-scope-options.png)

## 5. Address Exclusions

Added exclusion ranges to protect infrastructure devices.

![Address Pool with Exclusions](Images/11-address-pool-exclusion.png)

## 6. DHCP Reservations

Created reservation for **Printer-01** (192.168.1.25).

![Printer-01 Reservation](Images/15-reservation.png)

## 7. Final Validation

![Scope Deactivate Menu](Images/12-scope-deactivate-menu.png)

![PowerShell Validation](Images/13-powershell-validation.png)

![DHCP Service Running](Images/14-dhcp-service-running.png)

## Azure Notes & Key Takeaways
- Focused on server-side DHCP configuration (Azure platform DHCP handles client leasing).
- Learned proper use of scope options, exclusions vs reservations.
- Gained hands-on experience with Windows Server DHCP MMC and PowerShell.

## Cleanup
Deallocated VM and deleted resource group to avoid charges.
