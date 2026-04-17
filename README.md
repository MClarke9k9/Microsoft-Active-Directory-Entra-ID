# Microsoft Active Directory & Entra ID 
A hands-on hybrid identity project demonstrating how to deploy, configure, and manage on-premises Active Directory integrated with Microsoft Entra ID. This simulates a real-world enterprise environment where identity is managed across on-prem infrastructure and cloud services, enabling centralized authentication, SSO, and secure access control.

-------------------------

This section demonstrates configuring and managing Active Directory, including user and domain management, multi-domain deployment, and enforcing security using Group Policy.
- #### [Active Directory User & Domain Management](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%201/ManagingAccountsinAD)
- #### [Manage Active Directory in Windows Server](http://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%201/ManagingADinWindowsServer)
- #### [Active Directory Forest and Domain Deployment](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%201/WorkingwithForestsAndDomains)
- #### [Group Policy Security Configuration](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%201/ImplementGroupPolicySecurity)
-------------------------

In this section it demonstrates managing users at scale, recovering deleted accounts, and enforcing secure access using Microsoft Entra ID, Active Directory, and Group Policy:
- #### [Microsoft Entra ID Bulk Operations](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%202/PerformBulkEntraIDOperations)
- #### [Active Directory Backup and Recovery](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%202/RestoreADUserAccountsAndGroupMemberships)
- #### [Restricting Server Access with Group Policy](https://github.com/MClarke9k9/Microsoft-Active-Directory-Entra-ID/tree/main/Part%202/RestrictWindowsServerAccess)



### Architecture Diagram
<img width="3361" height="1713" alt="mermaid-diagram (1)" src="https://github.com/user-attachments/assets/2a0daac0-eac6-4e15-a7ed-89e7b4d40203" />

This is how real companies manage users across:

- Microsoft 365
- Internal networks
- SaaS applications<br/>


This project demonstrates:

On-Prem Identity → Active Directory Domain Services<br/>
Cloud Identity → Microsoft Entra ID<br/>
Synchronization → Azure AD Connect<br/>

### Technologies Used
- Windows Server (Domain Controller)<br/>
- Active Directory Domain Services<br/>
- Microsoft Entra ID<br/>
- Azure AD Connect<br/>
- Group Policy (GPO)<br/>
- PowerShell<br/>
- DNS / DHCP<br/>
