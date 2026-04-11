# Active Directory User & Domain Management 

This project demonstrates how to manage users, groups, and domain operations within a Windows Active Directory environment, using both GUI tools and PowerShell.

The simulates a real-world enterprise setup for someCompany, focusing on identity management, access control, and domain administration.

## Overview

- Created Organizational Units (OUs)
- Managed users and security groups
- Automated user creation with PowerShell
- Delegated permissions to non-admin users
- Performed domain join and unjoin operations

### This reflects real-world IT tasks such as onboarding users, managing permissions, and maintaining domain infrastructure.

### Environment Setup
- Domain: somecompany.local
- Domain Controller: Windows Server<br/>
- Tools Used:
   * Active Directory Users and Computers (ADUC)
   * PowerShell (ActiveDirectory Module)
   * Server Manager<br/>

### User & Group Management (GUI)
- Created Organizational Unit
- OU Name: ``` someCompany```
- Created Groups
   ``` NetAdmins ```
   ``` AllUsers ```
- Created & Managed Users:
    * user1 → Created in ```someCompany``` OU
    * user2 → Moved from default Users container into ```someCompany``` OU
- Group Memberships
    * Added ```user1``` to ```AllUsers``` group
  
### PowerShell User Management
List All Users
```
Get-ADUser -Filter * | Select samAccountName,givenName,surname
```
### Generates a report of all domain users

Create New User (user3)
```
New-ADUser -Name 'user3' `
-Path 'OU=someCompany,DC=someCompany,DC=local' `
-GivenName 'user3' `
-Surname 'user3' `
-SamAccountName 'user3' `
-AccountPassword (Read-Host -AsSecureString "Input User Password") `
-PasswordNeverExpires $true `
-Enabled $True
```
### Creates a new enabled user account in the OU

Modify User Settings
```
Set-ADUser user3 -ChangePasswordAtLogon $false
```
### Disables forced password change at first login

Add User to Group
```
Add-ADGroupMember NetAdmins -Members user3
```
### Grants administrative group access

----------------

## Domain Operations

#### Unjoin Computer from Domain
- Changed system from ```somecompany.local``` → ```WORKGROUP```
- Restarted system
#### Remove Computer Object
- Deleted computer object from Active Directory
#### Delegate Permissions
- Delegated control to ```NetAdmins``` group
- Permissions granted:
   * Read
   * Write
   * Create All Child Objects
   * Delete All Child Objects

#### Enables non-admin users to manage domain-joined systems

- Join Computer to Domain
- Domain: ```somecompany.local```
- User: ```user3```
- Authentication successful
- System restarted and rejoined domain


### Skills Demonstrated
- Active Directory Administration
- User & Group Management
- PowerShell Automation
- Delegation of Control
- Domain Join / Unjoin Operations
- Identity & Access Management (IAM)

### Real-World Use Cases
- Employee onboarding/offboarding
- Role-based access control (RBAC)
- Delegating IT tasks securely
- Managing domain-joined devices
- Automating administrative workflows

### Key Takeaways
- GUI tools are useful for basic administration
- PowerShell enables scalable automation
- Delegation reduces reliance on Domain Admins
- These skills are foundational for enterprise IT environments
