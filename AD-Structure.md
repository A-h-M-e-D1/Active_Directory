##  Why Active Directory?

Organizations use Active Directory to **centralize** the management of Windows network environments and to control:
- Users
- Computers
- File shares
- Servers and workstations
- Group Policies

Active Directory provides both **authentication** and **authorization** services within a Windows domain environment

---

## Active Directory Domain Services (AD DS)

- Allows organizations to **store and manage** directory data centrally
- Makes directory information available to **both standard users and administrators** across the network
- Stores critical information such as **usernames and passwords**
- Manages **access rights** and **permissions** needed by authorized users to access resources securely
  
---
#  Active Directory Structure


- **Active Directory** (AD) is built using a **hierarchical tree structure**.
- At the very top, we have a **Forest**.
- A Forest contains one or more **Domains**, and Domains may have **Subdomains**.
- Each Domain contains **Objects**, such as:
  - **Users**
  - **Computers**
  - **Groups**
- Domains often have built-in **Organizational Units (OUs)**, like:
  - **Domain Controllers**
  - **Users**
  - **Computers**


  
---
# What Causes Attacks in Active Directory
Active Directory (AD) misconfigurations are one of the leading causes that allow attackers to:
- Obtain a **foothold** (initial internal access)
- Move **laterally** (across systems)
- Escalate **vertically** (gain higher privileges)
- Access protected resources like:
  - Databases
  - File shares
  - Source code repositories
  - Critical servers

AD behaves like a **large open database** where even standard users can retrieve sensitive information.

---

##  Key is 

- **Any standard domain user** can enumerate a large part of the AD structure
- Enumeration doesn't require special privileges
- Active Directory flaws combined with basic user enumeration can lead to **major security breaches**

---

##  What a Standard Domain User Can Enumerate

| Category | Examples |
|----------|----------|
| **Computers** | List of domain-joined machines |
| **Users** | List of user accounts in the domain |
| **Groups** | Membership information (e.g., Domain Admins, IT Department) |
| **Organizational Units (OUs)** | Hierarchical structure of AD organization |
| **Policies** | Default Domain Policy, Password Policies, Group Policy Objects (GPOs) |
| **Domain Trusts** | Relationships between domains and forests |
| **Access Control Lists (ACLs)** | Permissions set on objects (can be abused for privilege escalation) |
| **Functional Domain Levels** | Version and feature levels of the domain (Windows Server versions, Kerberos options) |

---


