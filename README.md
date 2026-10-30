# Active Directory Home Lab

**Windows Server 2025 | Active Directory | Group Policy | Windows 11**

## Project Overview

This project demonstrates the setup and administration of a Windows Server 2025 Active Directory environment using Oracle VirtualBox.

The lab simulates a company called **TechNova**, consisting of four departments: IT, HR, Finance, and Sales.

The goal was to gain hands-on experience with Windows Server administration, user management, Group Policy, domain integration, and file permissions.

## Technologies Used

- Windows Server 2025
- Windows 11
- Oracle VirtualBox
- Active Directory Domain Services (AD DS)
- Group Policy Management
- DNS
- NTFS Permissions
- Windows File Sharing

## Lab Environment

| Component | Configuration |
|---|---|
| Domain | corp.technova.test |
| Domain Controller | Windows Server 2025 |
| Client | Windows 11 |
| Server IP | 192.168.56.10 |
| Client IP | 192.168.56.20 |
| Virtualization | Oracle VirtualBox |

## Project Implementation

### 1. Windows Server Setup
- Installed Windows Server 2025.
- Configured static IP addressing.
- Installed Active Directory Domain Services.
- Promoted the server to a domain controller.
- Configured DNS.

**Documentation:** [Server Setup](01-Server-Setup/)

### 2. Active Directory Configuration
- Created organizational units for IT, HR, Finance, Sales, and Workstations.
- Created employee accounts.
- Created departmental security groups.
- Managed group memberships.
- Practiced password resets and account management.

**Documentation:** [Active Directory](02-Active-Directory/)

### 3. Group Policy Management
- Created and configured Group Policy Objects.
- Applied workstation security settings.
- Configured a 10-minute inactivity limit.
- Verified applied policies using `gpresult`.

**Documentation:** [Group Policy](03-Group-Policy/)

### 4. Windows 11 Domain Integration
- Joined Windows 11 to the Active Directory domain.
- Verified domain membership.
- Tested domain user authentication.

**Documentation:** [Domain Integration](04-Domain-Integration/)

### 5. File Sharing and Permissions
- Created departmental shared folders.
- Configured NTFS permissions.
- Assigned access using Active Directory security groups.
- Restricted unauthorized departmental access.

**Documentation:** [File Sharing and Permissions](05-File-Sharing-and-Permissions/)

### 6. Security Testing
- Verified authorized access to departmental folders.
- Tested unauthorized access using domain accounts.
- Confirmed that unauthorized file creation was denied.

**Documentation:** [Security Testing](06-Security-Testing/)

## Security Testing Results

| User | Folder | Expected | Result |
|---|---|---|---|
| John Smith (IT) | IT | Allowed | PASS |
| John Smith (IT) | HR | Denied | PASS |
| John Smith (IT) | Finance | Denied | PASS |
| John Smith (IT) | Sales | Denied | PASS |
| David Wilson (Sales) | Sales | Allowed | PASS |
| David Wilson (Sales) | IT | Denied | PASS |
| David Wilson (Sales) | HR | Denied | PASS |
| David Wilson (Sales) | Finance | Denied | PASS |

## Skills Demonstrated

- Windows Server Administration
- Active Directory Management
- User and Group Administration
- Group Policy Configuration
- Windows Domain Integration
- NTFS Permissions
- Role-Based Access Control
- Network Troubleshooting
- Security Testing
- Technical Documentation

## Conclusion

This project provided practical experience configuring and managing a Windows enterprise environment.

Through this lab, I developed hands-on skills in Active Directory administration, Group Policy management, Windows Server configuration, and access control—skills relevant to IT Help Desk and junior system administration roles.
