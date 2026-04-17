# Microsoft Entra ID Bulk Operations (someCompany)

This section demonstrates how to manage users and groups in Microsoft Entra ID using bulk operations within the Azure portal.

The lab focuses on automating identity management tasks for someCompany by leveraging CSV-based bulk actions.

## Overview

In this lab, the following tasks were completed:

- Bulk created multiple users using a CSV template
- Bulk deleted a user account
- Created a security group
- Bulk added users to a group

These operations simulate real-world scenarios where administrators manage large numbers of users efficiently in cloud environments.

## Bulk User Creation

- Downloaded the bulk user creation CSV template
- Added new users:
    *  ```
        user1,user1@somecompany.local,myPassword1234,No
        user2,user2@somecompany.local,myPassword1234,No
        user3,user3@somecompany.local,myPassword1234,No
       [insert primary domain]
       
- Uploaded the CSV file to the Azure portal
- Executed the bulk create operation

### Result
- Users were successfully created in Microsoft Entra ID
- Verified users appeared in the directory

Bulk creation enables rapid onboarding of multiple users with minimal manual effort

## Bulk User Deletion

- Downloaded the bulk delete CSV template
- Specified user for removal:
```user2@somecompany.local```
- Uploaded and executed the bulk delete operation

### Result
-User account was successfully removed from the directory

Bulk deletion simplifies offboarding and cleanup processes

## Group Creation

- Created a new security group:
```PrimaryColorTeam```

Purpose
- Used to organize users and manage access control


## Bulk Group Membership Assignment

- Downloaded group membership CSV template
- Added user to group:
```user1@somecompany.local```
- Uploaded and executed the bulk import operation

### Result
- User was successfully added to the group

Bulk group management enables efficient assignment of permissions at scale

## Skills Demonstrated
- Microsoft Entra ID administration
- Bulk user lifecycle management
- CSV-based automation in Azure
- Group-based access control (RBAC)
- Cloud identity management

## Real-World Use Cases
- Onboarding large numbers of employees
- Offboarding and account cleanup
- Managing access through security groups
- Automating identity operations in cloud environments

## Key Takeaways
Bulk operations significantly reduce manual administrative effort
CSV templates provide a scalable way to manage identities
Group-based management simplifies access control
Microsoft Entra ID enables efficient cloud identity administration
