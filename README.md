# Small-Business-Azure-Infrastructure-Deployment-Lab
Hands-on Azure project deploying a secure small business cloud infrastructure using Microsoft Entra ID, RBAC, Administrative Units, and identity management. The repository includes a detailed breakdown of the architecture, implementation process, design decisions, and the purpose of each Azure resource used.


# Azure Project 1: Small Business Infrastructure Deployment

## Project Overview

This project simulates deploying a secure Microsoft Azure environment for **Atlas Technologies**, a fictional small business with approximately **75 employees** transitioning from an on-premises environment to Azure.

The goal of this project was to build a secure and scalable cloud environment while implementing Microsoft Entra ID identity management, Role-Based Access Control (RBAC), and core Azure infrastructure following Microsoft best practices.

---

## Project Objectives

### Identity & Access Management

* Create 30–40 Microsoft Entra ID users
* Organize users into departments
* Create security groups
* Configure Role-Based Access Control (RBAC)
* Enable Multi-Factor Authentication (MFA)
* Configure Self-Service Password Reset (SSPR)
* Create Administrative Units (where applicable)

### Departments

* Human Resources (HR)
* Finance
* Information Technology (IT)
* Sales

---

## Azure Infrastructure

The following Azure resources were deployed:

| Resource                     | Purpose                                      |
| ---------------------------- | -------------------------------------------- |
| Resource Group               | Organize Azure resources                     |
| Virtual Network (VNet)       | Private network for Azure resources          |
| Multiple Subnets             | Separate workloads and improve security      |
| Windows Server VM            | Administrative server                        |
| Linux VM                     | Linux workload management                    |
| Storage Account              | Store files and Azure data                   |
| Azure Key Vault              | Secure secrets and credentials               |
| Recovery Services Vault      | Backup and disaster recovery                 |
| Network Security Group (NSG) | Control inbound and outbound network traffic |

---

## Identity & Security Configuration

### Microsoft Entra ID

* Created 20–30 user accounts
* Assigned users to departments
* Organized users into security groups

### Role-Based Access Control (RBAC)

Configured Azure RBAC using the principle of least privilege.

Example role assignments included:

| Group   | Role          |
| ------- | ------------- |
| IT      | Contributor   |
| HR      | Standard User |
| Finance | Standard User |
| Sales   | Standard User |

Administrative roles were assigned only where necessary.

---

## Security Features

* Multi-Factor Authentication (MFA)
* Self-Service Password Reset (SSPR)
* Azure RBAC
* Network Security Groups (NSGs)
* Azure Key Vault for credential protection

---

## Virtual Machines

### Windows Server VM

* Deployed in Azure
* Connected to the virtual network
* Configured for administrative management

### Linux VM

* Deployed in Azure
* Connected to the virtual network
* Verified network connectivity

---

## Networking

Configured the following networking components:

* Virtual Network (VNet)
* Multiple Subnets
* Network Security Groups
* Private IP addressing
* Virtual machine communication

---

## Project Screenshots

The following screenshots document the deployment process and final environment:

* Azure Resource Group
* Microsoft Entra ID Users
* Security Groups
* RBAC Assignments
* MFA Configuration
* SSPR Configuration
* Administrative Units
* Virtual Network
* Virtual Machines
* Storage Account
* Azure Key Vault
* Recovery Services Vault
* Network Security Groups

---

## Technologies Used

* Microsoft Azure
* Microsoft Entra ID
* Azure RBAC
* Azure Virtual Machines
* Azure Virtual Network
* Azure Storage
* Azure Key Vault
* Azure Backup
* Network Security Groups

---

## Skills Demonstrated

* Azure Administration
* Identity and Access Management (IAM)
* Microsoft Entra ID
* Azure RBAC
* Virtual Networking
* Azure Security
* Virtual Machine Deployment
* Cloud Infrastructure
* Least Privilege Access Control

---

## Future Improvements

Potential enhancements for this environment include:

* Azure Bastion
* Azure Monitor
* Log Analytics Workspace
* Azure Policy
* Microsoft Defender for Cloud
* Azure Automation
* Infrastructure as Code (Bicep or Terraform)

---

## Challenges & Troubleshooting

### Bulk User Import Failed

While importing users into Microsoft Entra ID using a CSV file, the bulk import repeatedly failed.

**Issue**

* The `userPrincipalName` values in the CSV were not valid for my Microsoft Entra tenant.
* I also discovered that each `userPrincipalName` must be unique and use the correct verified tenant domain.

**Troubleshooting**

* Reviewed the import error messages returned by Microsoft Entra ID.
* Verified my tenant's default `onmicrosoft.com` domain.
* Updated the CSV with unique `userPrincipalName` values that matched the tenant's verified domain.
* Re-ran the bulk import successfully.

**Lesson Learned**
This reinforced the importance of carefully validating user identity information before performing bulk operations in Microsoft Entra ID. Even a small formatting issue can prevent an entire batch import from succeeding.
