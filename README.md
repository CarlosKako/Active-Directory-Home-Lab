
# Active Directory Home Lab

## 📌 Overview
This project demonstrates the deployment and administration of a Windows Active Directory environment in a virtualized lab.

The lab simulates common tasks performed by IT Support and System Administration professionals, including configuring a domain controller, creating and managing users, joining client computers to a domain, configuring Group Policy, managing account lockouts, setting file permissions, and enabling Remote Desktop access.

The purpose of this project was to gain hands-on experience with enterprise Windows environments and common IT administration tasks.

---

## 🛠️ Technologies Used

- Windows Server
- Windows 10
- Active Directory Domain Services (AD DS)
- Microsoft Azure
- PowerShell
- Group Policy
- DNS
- Remote Desktop Protocol (RDP)

---

## 🧪 Lab Environment

The environment consists of:

- **Domain Controller (DC-1)** — Windows Server
- **Client Computer (Client-1)** — Windows 10
- **Active Directory Domain**
- Microsoft Azure virtual machines
- Private virtual network

DC-1 provides Active Directory Domain Services and DNS services for the environment, while Client-1 is joined to the domain and used to simulate an employee workstation.

---

## 🎯 Project Objectives

During this project, I performed the following tasks:

- Deployed Windows Server and Windows 10 virtual machines
- Installed Active Directory Domain Services
- Promoted Windows Server to a Domain Controller
- Created and configured an Active Directory domain
- Created Organizational Units (OUs)
- Created and managed domain users
- Joined a Windows client computer to the domain
- Configured Remote Desktop access for domain users
- Created and tested Group Policy settings
- Configured an account lockout policy
- Managed user account lockouts
- Created network file shares
- Configured NTFS and share permissions
- Used PowerShell for Active Directory administration
- Practiced troubleshooting common user and access issues

---

## 📚 Lab Documentation

### 1. Domain Controller & Network Setup

I created the foundational Azure infrastructure for the Active Directory environment by deploying two virtual machines on the same private virtual network:

- **DC-1:** Windows Server 2022 virtual machine used as the Domain Controller
- **Client-1:** Windows 10 Pro virtual machine used as the domain client

#### Azure Network Configuration

I created a Resource Group and Virtual Network (VNet) in Microsoft Azure to keep the lab resources organized and allow DC-1 and Client-1 to communicate over the same private network.

#### Domain Controller Configuration

I deployed DC-1 using Windows Server 2022 and configured its private IP address as static.

Using a static private IP is important for a Domain Controller because client devices rely on the Domain Controller for services such as DNS and authentication. If the Domain Controller's IP address changed, clients could lose connectivity to these services.

#### Client Configuration

I deployed Client-1 using Windows 10 Pro within the same Resource Group and Virtual Network as DC-1.

I then configured Client-1's DNS settings to use the private IP address of DC-1 as its DNS server. This allows the client to locate the Domain Controller and prepares the machine to join the Active Directory domain.

#### Connectivity Testing

After applying the DNS configuration and restarting Client-1, I connected to the client through Remote Desktop and verified network connectivity with DC-1.

I used tools such as:

- `ping`
- `ipconfig`
- PowerShell

Successful communication between the two machines confirmed that the virtual network and DNS configuration were functioning correctly.

### 2. Active Directory Deployment & Domain Join
Coming soon.

### 3. User & Organizational Unit Management
Coming soon.

### 4. Remote Desktop Configuration
Coming soon.

### 5. Group Policy & Account Lockout
Coming soon.

### 6. File Shares & Permissions
Coming soon.

---

## 💡 Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- User and Group Management
- Group Policy
- DNS
- PowerShell
- Remote Desktop
- File and Share Permissions
- Identity and Access Management
- IT Troubleshooting

---

## 📖 What I Learned

This project gave me practical experience working with a Windows domain environment and helped me understand how centralized identity, authentication, permissions, and policies are managed in an enterprise network.

I also gained experience troubleshooting user accounts, managing access to resources, and performing administrative tasks commonly encountered in IT Support and System Administration environments.
