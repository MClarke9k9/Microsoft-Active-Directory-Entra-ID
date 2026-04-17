# Active Directory Backup and Recovery (someCompany)

This section demonstrates how to restore deleted Active Directory user accounts and preserve group memberships using the Active Directory Recycle Bin.

The lab focuses on improving resilience and recovery capabilities within the someCompany domain environment.

## Overview

In this lab, the following tasks were completed:

- Installed and configured Active Directory Domain Services (AD DS)
- Created users, groups, and organizational units
- Enabled the Active Directory Recycle Bin
- Simulated accidental deletion of user accounts
- Restored deleted users and verified group memberships

These steps reflect real-world scenarios where administrators must quickly recover from accidental deletions.

## Active Directory Environment Setup

### Key Actions
- Deployed Active Directory using PowerShell automation
- Created domain:
```somecompany.local```

- Configured domain services and management tools

This establishes the foundation for identity management within the environment

## User and Group Configuration

#### Created Users
- user1
- user2

#### Created Group

```SalesGroup```

#### Group Membership
user1 → Member of ```SalesGroup```<br/>
user2 → Member of ```SalesGroup```

#### Created Organizational Unit

```SalesOU```

These objects simulate a department-based structure within Active Directory

## Active Directory Recycle Bin Configuration

### Key Actions
- Enabled Active Directory Recycle Bin
- Verified creation of the Deleted Objects container

This feature allows recovery of deleted objects with attributes and memberships intact

## Simulated Deletion Scenario

#### Deleted:
- user1
- user2

#### Verified both users appeared in the Deleted Objects container

This simulates accidental user account deletion

## User Restoration

#### Restore to Original Location
- Restored user1 to the domain root
- Verified:
    * User account restored
    * Membership in ```SalesGroup``` retained

#### Restore to Alternate Location
- Restored user2 to:
```SalesOU```
- Verified:
    * User account restored to new OU
    * Membership in SalesGroup retained

This demonstrates flexible recovery options within Active Directory

## Skills Demonstrated
- Active Directory administration
- Backup and recovery operations
- AD Recycle Bin configuration
- User and group management
- Organizational Unit (OU) management
- PowerShell-based deployment

## Real-World Use Cases
- Recovering accidentally deleted user accounts
- Maintaining group memberships during restoration
- Implementing disaster recovery strategies
- Improving Active Directory resilience

## Key Takeaways
- The Active Directory Recycle Bin enables fast and reliable recovery
- Deleted objects can be restored with attributes and group memberships intact
- Recovery can be performed to original or alternate locations
- Proper configuration reduces downtime and administrative overhead
