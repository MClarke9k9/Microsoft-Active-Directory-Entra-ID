# Restricting Server Access with Group Policy (someCompany)

This section demonstrates how to restrict remote access to Windows servers using Group Policy Objects (GPOs) and Active Directory group-based controls.

The lab focuses on enforcing access restrictions so that only authorized users can log in to critical systems within the someCompany environment.

## Overview

In this lab, the following tasks were completed:

- Configured Active Directory Domain Services (AD DS)
- Created users and security groups
- Implemented a Group Policy to restrict remote access
- Tested access control using different user roles

This simulates real-world scenarios where organizations enforce role-based access restrictions to protect sensitive infrastructure.

## Active Directory Environment Setup

### Key Actions
- Deployed Active Directory using PowerShell automation
- Configured domain:
```somecompany.local```

- Verified domain controller configuration and networking

This establishes the foundation for centralized authentication and policy enforcement

## User and Group Configuration

### Created Users
- adminUser (Domain Administrator)
- user1 (Standard user)

### Created Group
- ```SalesGroup```

### Group Membership
- user1 → Member of ```SalesGroup```

This structure enables role-based access control within the domain

## Group Policy Configuration

### GPO Creation
- Created a new Group Policy Object:
```SalesAccessRestriction```
- Linked GPO to the domain

## Policy Configuration

Navigated to:

```
  Computer Configuration
    → Policies
    → Windows Settings
    → Security Settings
    → Local Policies
    → User Rights Assignment
```

Configured:

```Deny log on through Remote Desktop Services```

Added:

```SalesGroup```

This prevents all users in the Sales group from accessing servers via Remote Desktop

## Access Validation

### Test 1: Restricted User
- Attempted remote login using:
    * user1 (member of ```SalesGroup```)

Result:

- Access denied

### Test 2: Authorized User
- Attempted remote login using:
    * adminUser (not in SalesGroup)

Result:

- Access granted

These tests confirm that the Group Policy is functioning correctly

## Skills Demonstrated
- Group Policy Object (GPO) configuration
- Role-based access control (RBAC)
- Active Directory user and group management
- Windows Server security hardening
- Remote access control and validation

## Real-World Use Cases
- Restricting access to sensitive servers
- Enforcing least privilege access
- Securing administrative environments
- Preventing unauthorized remote logins

## Key Takeaways
- Group Policy enables centralized control of user access
- Security groups allow scalable permission management
- Deny policies override allow permissions for stronger enforcement
- Testing access scenarios is critical to validating security configurations
