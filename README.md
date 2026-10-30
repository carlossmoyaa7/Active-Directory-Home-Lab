\# Active Directory Home Lab



\## Project Overview



This project demonstrates the deployment and administration of a simulated corporate IT environment using Windows Server 2025, Windows 11, Active Directory Domain Services (AD DS), Group Policy, and NTFS file permissions.



The lab simulates an organization named \*\*TechNova\*\*, with four departments: IT, Human Resources, Finance, and Sales.



The objective was to configure a functioning Windows domain, manage employee accounts, implement workstation security policies, and secure departmental file shares using role-based access control.



\## Technologies Used



\- Windows Server 2025

\- Windows 11

\- Oracle VirtualBox

\- Active Directory Domain Services (AD DS)

\- DNS

\- Group Policy Management

\- NTFS Permissions

\- Windows File Sharing

\- Command Prompt



\## Lab Environment



| Component | Configuration |

|---|---|

| Domain Controller | Windows Server 2025 |

| Client Workstation | Windows 11 |

| Domain Name | corp.technova.test |

| Domain Controller IP | 192.168.56.10 |

| Windows 11 IP | 192.168.56.20 |

| Virtualization Platform | Oracle VirtualBox |

| Network | VirtualBox Host-Only Network |



\## 1. Windows Server Configuration



Deployed Windows Server 2025 in VirtualBox and configured networking to support communication between the domain controller and Windows 11 workstation.



Installed Active Directory Domain Services and promoted the server to a domain controller for the `corp.technova.test` domain.



Configured DNS to support domain authentication and name resolution.



\*\*Skills demonstrated:\*\* Windows Server administration, networking, DNS, and domain controller deployment.



\## 2. Active Directory Administration



Created an organizational unit named `TechNova` containing five child OUs:



\- IT

\- HR

\- Finance

\- Sales

\- Workstations



Created employee accounts and departmental security groups.



| Department | Employee | Security Group |

|---|---|---|

| IT | John Smith | IT-Staff |

| HR | Sarah Johnson | HR-Staff |

| Finance | Michael Brown | Finance-Staff |

| Sales | David Wilson | Sales-Staff |



Practiced account administration, including password resets, enabling and disabling accounts, and managing security group membership.



\*\*Skills demonstrated:\*\* Active Directory administration, user provisioning, organizational units, and security group management.



\## 3. Group Policy Management



Created and linked a Group Policy Object named `Workstation-Security-Policy` to the Workstations OU.



Configured the \*\*Interactive logon: Machine inactivity limit\*\* policy to 600 seconds (10 minutes).



Verified that the Windows 11 workstation received the policy using:



`gpresult /r /scope computer`



The results confirmed that `Workstation-Security-Policy` and `Default Domain Policy` were applied.



\*\*Skills demonstrated:\*\* Group Policy configuration, workstation security, and policy troubleshooting.



\## 4. Windows 11 Domain Integration



Joined a Windows 11 virtual machine named `TN-WIN11-01` to the `corp.technova.test` domain.



Verified domain membership through Windows System Properties and tested domain authentication using employee accounts.



\*\*Skills demonstrated:\*\* Domain joining, Windows client administration, and domain authentication.



\## 5. Departmental File Sharing and Permissions



Created a shared directory on the Windows Server:



`C:\\TechNova-Shares`



Organized departmental folders for IT, HR, Finance, and Sales.



Configured NTFS permissions to grant departmental security groups Modify access while maintaining administrative access.



| Folder | Authorized Group | Permission |

|---|---|---|

| IT | IT-Staff | Modify |

| HR | HR-Staff | Modify |

| Finance | Finance-Staff | Modify |

| Sales | Sales-Staff | Modify |



Restricted the parent shared folder so Domain Users have Read \& execute access rather than Full Control.



\*\*Skills demonstrated:\*\* File sharing, NTFS permissions, least privilege, and role-based access control (RBAC).



\## 6. Security Testing and Validation



Tested departmental file access using domain user accounts.



Verified that John Smith (`CORP\\jsmith`) could create files in the IT shared folder but could not create files in HR, Finance, or Sales.



| Test | Expected Result | Actual Result |

|---|---|---|

| IT user → IT folder | Allowed | Passed |

| IT user → HR folder | Denied | Passed |

| IT user → Finance folder | Denied | Passed |

| IT user → Sales folder | Denied | Passed |



Also tested the Sales account (`CORP\\dwilson`) and confirmed that it could write to its own department folder while unauthorized writes to other departments were denied.



\*\*Skills demonstrated:\*\* Access control testing, permissions troubleshooting, and security validation.



\## Project Documentation



Screenshots are organized into six folders:



1\. `01-Server-Setup`

2\. `02-Active-Directory`

3\. `03-Group-Policy`

4\. `04-Domain-Integration`

5\. `05-File-Sharing-and-Permissions`

6\. `06-Security-Testing`



These screenshots provide evidence of the configuration and testing performed throughout the lab.



\## Key Skills Developed



\- Windows Server installation and administration

\- Active Directory user and group management

\- Organizational Unit administration

\- Group Policy configuration and verification

\- Windows 11 domain integration

\- DNS and virtual networking

\- NTFS permissions and file sharing

\- Role-based access control

\- Security testing and troubleshooting

\- Technical documentation



\## Conclusion



This lab provided hands-on experience building and administering a Windows domain environment.



By configuring Active Directory, Group Policy, domain-joined workstations, and departmental file permissions, I practiced tasks commonly performed by IT Help Desk technicians and junior system administrators.

