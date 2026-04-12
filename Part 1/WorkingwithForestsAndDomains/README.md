# Active Directory Forest and Domain Deployment (someCompany)

This section demonstrates how to build a multi-domain Active Directory environment by creating:

- A forest root domain
- A child domain
- A domain-joined member server

This simulates how organizations like someCompany structure identity across multiple business units.

----------------------------
### Overview

In this project, the following tasks are completed:

- Deployed a new Active Directory forest
- Configured DNS and Active Directory Domain Services
- Created a child domain within the forest
- Joined a member server to the domain
- Verified connectivity and DNS resolution

This reflects real-world enterprise environments where domain hierarchies are used for scalability and management.

Architecture Summary
<img width="1447" height="166" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/cf08027b-b5a1-4e7f-9f96-9319b9bc4d3a" />

----------------------------
### Forest Root Domain Setup
#### Key Actions
- Installed:
    * Active Directory Domain Services (AD DS)
    * DNS Server
- Promoted the server to a Domain Controller
- Created a new forest:
    * ```somecompany.local```
<img width="855" height="600" alt="Screenshot 2026-04-11 at 8 43 59 PM" src="https://github.com/user-attachments/assets/6bc0adce-0549-41af-8712-0e984687b1a6" />


This establishes the root domain for the environment

----------------------------

### Child Domain Configuration
#### Key Actions
- Added a new domain to the existing forest
- Configured it as a child domain:
  * ```child.somecompany.local```
- Authenticated using domain administrator credentials
- Enabled DNS delegation

This creates a hierarchical domain structure within the forest

----------------------------


### DNS and Connectivity Validation
- Verified DNS resolution between domains:
    * ```ping somecompany.local```

<img width="850" height="589" alt="Screenshot 2026-04-11 at 8 48 18 PM" src="https://github.com/user-attachments/assets/8210cdbd-a2a2-4f2d-b33f-6d9b3dd1ef83" />

This confirms communication between the child and root domain controllers

----------------------------

### Domain User Preparation
- Accessed Active Directory Users and Computers
- Reset administrator credentials for domain access

This ensures authentication works for domain operations

----------------------------

### Member Server Domain Join
#### Steps Performed
- Changed system membership from ```WORKGROUP``` to:
    * ```child.somecompany.local```
- Authenticated using domain credentials
- Restarted the system

This successfully joins the server to the domain

----------------------------

### Connectivity Testing

After joining the domain:
```
ping dc02
ping dc01.somecompany.local
```
Verified:

- Connectivity to the child domain controller
- Connectivity to the root domain controller
----------------------------

### Skills Demonstrated
- Active Directory forest deployment
- Multi-domain architecture design
- DNS configuration and validation
- Domain controller promotion
- Domain join operations
- Network connectivity troubleshooting
----------------------------

### Real-World Use Cases
- Enterprise environments with multiple domains
- Parent and subsidiary domain structures
- Scalable identity management
- Centralized authentication across environments
----------------------------

### Key Takeaways
- Forests provide the top-level structure for Active Directory environments
- Child domains allow separation of control and scalability
- DNS is essential for domain communication and resolution
- Domain joins enable centralized authentication and policy enforcement
