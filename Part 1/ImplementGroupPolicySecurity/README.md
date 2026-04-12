# Group Policy Security Configuration (someCompany)

This section demonstrates how to secure Windows systems and Active Directory using Group Policy Objects (GPOs) in a domain environment.

The lab focuses on applying security controls, auditing, and policy filtering within the someCompany Active Directory domain.

## Overview

In this lab, the following tasks were completed:

- Created and configured security-focused GPOs
- Applied system and user-level security policies
- Enabled auditing for Active Directory events
- Configured password and account lockout policies
- Applied and verified GPOs on client systems
- Implemented GPO security filtering using groups

These tasks simulate how organizations enforce centralized security policies across domain environments.

------------------------------

### Windows Security GPO Configuration
#### Key Policies Applied
- Machine inactivity limit set to 600 seconds (auto-lock)
- Disabled anonymous SID/Name translation
- Blocked access to all removable storage devices

These settings improve endpoint security by reducing unauthorized access and limiting data exfiltration risks.

------------------------------

### GPO Deployment and Validation
- Linked GPO to the domain (somecompany.local)
- Forced policy update on client systems:
```gpupdate /force```
-Verified applied policies:
```gpresult /r```

Confirmed that security policies were successfully applied to domain clients.

------------------------------

### Active Directory Security Hardening
#### Audit Policy Configuration
- Enabled auditing for:
    * System events (Success and Failure)
    * Directory service changes
#### Security Enhancements
- Disabled storage of LAN Manager (LM) password hashes
- Enabled directory service change tracking

<img width="237" height="235" alt="Screenshot 2026-04-11 at 9 12 06 PM" src="https://github.com/user-attachments/assets/8243cfd0-172f-42b8-bf76-1f00c7b73761" />
<img width="981" height="589" alt="Screenshot 2026-04-11 at 9 12 30 PM" src="https://github.com/user-attachments/assets/90794158-90f1-441e-bd36-58ad647bccfc" />

These configurations improve visibility and protect against weak authentication mechanisms.

------------------------------

### Domain Password and Lockout Policies
#### Password Policy
- Password history: 24 remembered
- Maximum age: 42 days
- Minimum length: 10 characters
- Complexity requirements: Enabled

### Account Lockout Policy
- Lockout threshold: 5 failed attempts
- Lockout duration: 0 minutes (manual unlock)
- Reset counter after: 15 minutes

These policies enforce strong authentication standards across the domain.

------------------------------

### GPO Security Filtering
#### Configuration Steps
- Removed default Authenticated Users access
- Applied GPO only to:
    * ```AllUsers group```
    * ```Domain Computers group```
#### Purpose
- Limits policy scope to specific users and systems
- Prevents unnecessary or unintended policy application

<img width="538" height="93" alt="Screenshot 2026-04-11 at 9 13 01 PM" src="https://github.com/user-attachments/assets/10f36815-6361-49f0-a5a8-cf149d3a4e44" />


This demonstrates targeted policy enforcement using Active Directory groups.

------------------------------

### Skills Demonstrated
- Group Policy Object (GPO) management
- Windows security configuration
- Active Directory hardening
- Audit policy configuration
- Password and lockout policy enforcement
- GPO filtering and access control

### Real-World Use Cases
- Enforcing endpoint security standards
- Preventing unauthorized access and data leakage
- Monitoring and auditing domain activity
- Applying role-based security policies
- Meeting compliance and security requirements

### Key Takeaways
- GPOs provide centralized control over security settings
- Security policies can be applied at both user and system levels
- Auditing improves visibility into domain activity
- Filtering allows precise control over policy application
- Strong password and lockout policies are critical for security
