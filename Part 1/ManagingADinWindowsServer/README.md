# Manage Active Directory in Windows Server

## Group Policy Object (GPO) Configuration

This section demonstrates how to create and configure a Group Policy Object (GPO) and link it to an Organizational Unit in the someCompany Active Directory environment.

### Overview
-------------------------------------------
In this task, we:

- Created a new GPO named ```User Settings```
- Configured a user policy to restrict offline file access
- Linked the GPO to an Organizational Unit (```someCompanyOU```)

### This simulates real-world scenarios where administrators enforce user restrictions and security policies across departments.
-------------------------------------------
### Steps Performed
1. Open Group Policy Management
- Logged into the Domain Controller
- Navigated to:
  * ```Start Menu``` → ```Windows Administrative Tools``` → ```Group Policy Management```
--------------------------------------------
2. Create a New GPO
- Expanded:
  * ```Forest: somecompany.local```
  * ```Domains``` → ```somecompany.local```
- Right-clicked Group Policy Objects → New
- Created GPO:
  * Name: ```User Settings```
 
--------------------------------------------
3. Edit the GPO
- Right-clicked ```User Settings``` → ```Edit```
- Navigated to:
``` User Configuration
  └── Policies
      └── Administrative Templates
          └── Network
              └── Offline Files
```

<img width="397" height="454" alt="Screenshot 2026-04-10 212513" src="https://github.com/user-attachments/assets/938a8a79-bc22-4227-bd37-6a49604fe565" />

4. Configure Policy Setting
- Opened:
   * ```Remove "Make Available Offline" command```
- Set to:
   * ```Enabled```
<img width="684" height="217" alt="Screenshot 2026-04-10 212426" src="https://github.com/user-attachments/assets/a85c9e2c-3465-401b-a4e6-d4f21dd4e282" />

### This prevents users from making files available offline
--------------------------------------------
5. Link GPO to OU
- Right-clicked OU:
    * ```someCompanyOU```
- Selected:
    * ```Link an Existing GPO```
- Chose:
    * ```User Settings```

### Successfully linked the GPO to the OU
--------------------------------------------
6. Verification
- Selected ```someCompanyOU```
-Confirmed:
    * ```User Settings``` GPO is linked and active

--------------------------------------------
### Skills Demonstrated
- Group Policy Management (GPO)
- Policy Configuration (Administrative Templates)
- OU-Level Policy Enforcement
- Windows Server Administration
- --------------------------------------------
### Real-World Use Cases
- Restricting user behavior across departments
- Enforcing company-wide security policies
- Controlling file access and network usage
- Standardizing user environments
--------------------------------------------
### Key Takeaways
- GPOs allow centralized control over user and computer settings
- Linking GPOs to OUs enables targeted policy enforcement
- Administrative Templates provide predefined security controls
  
Proper GPO use improves security, compliance, and consistency
