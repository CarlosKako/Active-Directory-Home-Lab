
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
#### Azure Virtual Machine Environment

The lab environment was deployed in Microsoft Azure using two virtual machines on the same virtual network.

![Azure Virtual Machine Environment](azure-vm-environment.png)
#### Domain Controller Configuration

I deployed DC-1 using Windows Server 2022 and configured its private IP address as static.

Using a static private IP is important for a Domain Controller because client devices rely on the Domain Controller for services such as DNS and authentication. If the Domain Controller's IP address changed, clients could lose connectivity to these services.

#### Client Configuration

I deployed Client-1 using Windows 10 Pro within the same Resource Group and Virtual Network as DC-1.

I then configured Client-1's DNS settings to use the private IP address of DC-1 as its DNS server. This allows the client to locate the Domain Controller and prepares the machine to join the Active Directory domain.


After applying the DNS configuration and restarting Client-1, I connected to the client through Remote Desktop and verified network connectivity with DC-1.

#### Network Connectivity Verification

I verified Client-1's network configuration using `ipconfig /all` and tested connectivity to DC-1 using `ping`.

The successful ping test confirmed communication between the client and Domain Controller with 0% packet loss.

![Client-1 Network Connectivity](client1-network-connectivity.png)

I used tools such as:

- `ping`
- `ipconfig`
- PowerShell

Successful communication between the two machines confirmed that the virtual network and DNS configuration were functioning correctly.

### 2. Active Directory Deployment & Domain Join

![Active Directory Domain Services Installation](ad-ds-installation.png)

After configuring the network environment, I installed Active Directory Domain Services (AD DS) on DC-1 and promoted the server to a Domain Controller.

#### Installing Active Directory Domain Services

Using Server Manager on DC-1, I added the **Active Directory Domain Services** server role through the Add Roles and Features wizard.

After the installation completed, I promoted DC-1 to a Domain Controller and created a new Active Directory forest.

**Domain:** `mydomain.com`

This established DC-1 as the Domain Controller responsible for centralized authentication and domain management within the lab environment.

![Domain Controller Promotion](domain-controller-promotion.png)

#### Organizational Unit Configuration

Using Active Directory Users and Computers (ADUC), I created Organizational Units to organize accounts based on their purpose:

- `_EMPLOYEES` — standard domain user accounts
- `_ADMINS` — privileged administrator accounts

Organizational Units provide a structured way to manage users and allow policies and permissions to be applied to specific groups of objects.

![Active Directory Organizational Units](active-directory-ou-structure.png)

#### Domain Administrator Account

I created a dedicated administrative user inside the `_ADMINS` Organizational Unit and added the account to the **Domain Admins** security group.

I then used the domain administrator account for subsequent domain-level administrative tasks instead of relying on the original local administrator account.

![Domain Administrator Account](domain-admin-account.png)

#### Joining Client-1 to the Domain

After Active Directory was configured, I joined Client-1 to `mydomain.com`.

From Client-1, I opened System Properties, changed the computer's membership from a workgroup to the domain, and authenticated using domain administrator credentials.

After restarting Client-1, I successfully logged into the computer using a domain account, confirming that:

- Client-1 could locate DC-1 through DNS
- Domain authentication was functioning
- Client-1 was successfully joined to Active Directory
- The Domain Controller could centrally manage the client computer

![Successful Domain Join](client-domain-join.png)

### 3. User & Organizational Unit Management
After deploying Active Directory, I organized domain users and administrative accounts using Organizational Units (OUs) in Active Directory Users and Computers (ADUC).

#### Organizational Unit Structure

I created separate Organizational Units to organize accounts based on their roles:

* **_EMPLOYEES** — standard domain user accounts
* **_ADMINS** — privileged administrative accounts

Separating standard users from administrative accounts provides a cleaner directory structure and makes it easier to apply different policies, permissions, and administrative controls.

![Active Directory Organizational Units](active-directory-ou-structure.png)

#### User Account Management

I created user accounts within Active Directory and placed them into the appropriate Organizational Units based on their intended roles.

For administrative tasks, I created a dedicated administrator account inside the **_ADMINS** OU and added the account to the **Domain Admins** security group.

This allowed administrative privileges to be assigned through group membership rather than relying on the original local administrator account.

![Domain Administrator Account](domain-admin-account.png)

#### Skills Demonstrated

* Active Directory Users and Computers (ADUC)
* Organizational Unit (OU) management
* User account creation and administration
* Security group membership
* Role-based account organization
* Domain administrator configuration


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
