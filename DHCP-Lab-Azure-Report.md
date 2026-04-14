# DHCP Lab - Azure Implementation (Jake's Tech Labs)

**Date:** April 2026  
**Student:** Changli (IchiXRuki1415)

## Lab Objective
Configure a Windows Server 2025 DHCP server in Microsoft Azure with multiple scopes, exclusions, scope options, and a reservation.

## 1. Azure Environment Setup
![Resource Group](images/01-resource-group.png)
![Virtual Network](images/02-virtual-network.png)
![VM Creation - Basics](images/03-vm-creation-basics.png)
![VM Networking Tab](images/04-vm-networking.png)
![RDP Connection](images/05-rdp-file.png)
![ipconfig](images/06-ipconfig-inside-vm.png)

## 2. DHCP Server Role Installation
![Server Manager Dashboard](images/07-server-manager-dashboard.png)
![DHCP Role Added](images/08-dhcp-role-installed.png)

## 3. DHCP Scopes
![All Scopes Active](images/09-all-scopes-active.png)

## 4. Scope Options
![Scope Options](images/10-scope-options.png)

## 5. Address Exclusions
![Address Pool with Exclusions](images/11-address-pool-exclusion.png)

## 6. DHCP Reservations
![Printer-01 Reservation](images/15-reservation.png)

## 7. Final Validation
![Scope Deactivate Menu](images/12-scope-deactivate-menu.png)
![PowerShell Validation](images/13-powershell-validation.png)
![DHCP Service Running](images/14-dhcp-service-running.png)

## Key Takeaways
- Server-side DHCP configuration completed successfully in Azure.
- Proper scope options (003 Router, 006 DNS, 015 Domain) and reservations applied.
