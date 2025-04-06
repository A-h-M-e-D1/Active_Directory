# Active Directory Fundamentals

Understanding each feature of Active Directory is critical before designing an infrastructure. Missing a fundamental concept could lead to an incomplete or inefficient design.

---

## 📚 Basic Concepts and Terminology

### 🔹 Objects
- **Containers**: Can contain other objects.
- **Non-containers (Leaf Nodes)**: Cannot contain other objects.

### 🔹 Hierarchy
- Active Directory is structured in a hierarchical format, similar to filesystems.

### 🔹 Domain
- A logical group of network objects (users, computers, devices).

### 🔹 Organizational Unit (OU)
- The most common container used in Active Directory for organization and delegation.

---

## 🗂️ How Objects Are Stored

### 🔸 Hierarchical Presentation
- **Similar to a filesystem**: Objects are presented in a parent-child tree structure (e.g., Sales → Pre-Sales).

### 🔸 Flat Database Storage
- **Stored using database rows and columns**, not actual trees.
- Backed by:
  - **Directory Information Tree (DIT)** file
  - **Extensible Storage Engine (ESE)** database
    - ESE is a JET technology.

---

## 🧬 How Objects Are Identified

### 🔸 Globally Unique Identifier (GUID)
- A **128-bit identifier** assigned at object creation.
- Microsoft's implementation of the **UUID** concept.
- **Persistent**:
  - Survives object renaming or moving within DIT.
  - Remains unchanged when moved across domains in the same forest.
- **Not preserved** during cross-forest moves (e.g., using **ADMT**).
- Designed to be **statistically unique** until at least the year 3400.

### 🔸 Distinguished Name (DN)
- **Hierarchical path** to uniquely reference an object.
- Defined in **LDAP standard**.
- Syntax example: `dc=mycorp,dc=com`
- Components:
  - **dc**: Domain Component
  - **ou**: Organizational Unit
  - **cn**: Common Name

#### ▫️ Relative Distinguished Name (RDN)
- Unique within its parent container.
- Example: `cn=Administrator`
- Used to identify the object within its local container.

---

## 🏷️ Prefixes (Attribute Types)

| Prefix | Meaning                     |
|--------|-----------------------------|
| cn     | Common Name                 |
| l      | Locality Name               |
| st     | State or Province Name      |
| o      | Organization Name           |
| ou     | Organizational Unit Name    |
| c      | Country Name                |
| street | Street Address              |
| dc     | Domain Component            |
| uid    | User ID                     |

> Active Directory primarily uses: `cn`, `ou`, `dc`

---

## 🧾 Examples of Distinguished Names

### 🔹 Domain Roots
- `dc=mycorp,dc=com`
- `dc=mydomain,dc=mycorp,dc=com`

### 🔹 User in Users Container
- `cn=Administrator,cn=Users,dc=mycorp,dc=com`

### 🔹 User in OU
- `cn=Keith Cooper,ou=Northlight IT Ltd,dc=mycorp,dc=com`

### 🔹 OUs
- `ou=Pre-Sales,ou=Sales,dc=mycorp,dc=com`
- `ou=Post-Sales,ou=Sales,dc=mycorp,dc=com`

### 🔹 Objects in Pre-Sales
- **User**: `cn=Richard Lang,ou=Pre-Sales,ou=Sales,dc=mycorp,dc=com`
- **Group**: `cn=My Group,ou=Pre-Sales,ou=Sales,dc=mycorp,dc=com`
- **Computer**: `cn=PC1,ou=Pre-Sales,ou=Sales,dc=mycorp,dc=com`

---

> **Note:** User, group, and computer objects can be containers but are usually not represented as such in diagrams.
