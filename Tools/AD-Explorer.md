# AD Explorer

## Overview

AD Explorer is an advanced Active Directory database viewer and editor developed by Microsoft Sysinternals. It enables administrators and security professionals to browse, search, and analyze Active Directory objects through a graphical interface. During security assessments, AD Explorer is commonly used to enumerate LDAP information, inspect user accounts, examine directory structures, and view object attributes without relying on native Active Directory management tools.

---

## Purpose

AD Explorer is used to:

- Enumerate Active Directory objects.
- Browse LDAP directory structures.
- View user, group, and computer objects.
- Inspect object attributes and permissions.
- Search Active Directory efficiently.
- Analyze domain configurations.

---

## Key Features

- Graphical Active Directory browser.
- Advanced LDAP search functionality.
- View and edit object attributes.
- Browse domain hierarchy.
- Display object permissions and schema.
- Snapshot comparison capability.

---

## Installation

Download AD Explorer from Microsoft Sysinternals.

Run:

```text
ADExplorer.exe
```

No installation is required.

---

## Typical Workflow

```mermaid
flowchart LR
    A[Connect to Domain Controller] --> B[Browse LDAP Tree]
    B --> C[Enumerate Directory Objects]
    C --> D[Inspect User Attributes]
    D --> E[Analyze Domain Information]

    style A fill:#1f2937,color:#fff,stroke:#2563eb
    style B fill:#374151,color:#fff,stroke:#2563eb
    style C fill:#4b5563,color:#fff,stroke:#2563eb
    style D fill:#7c3aed,color:#fff,stroke:#8b5cf6
    style E fill:#059669,color:#fff,stroke:#10b981
```

---

## CEH Practical Example

In **Module 04 – Enumeration**, AD Explorer was used to connect to a target Active Directory domain and enumerate LDAP information. The directory hierarchy was explored to identify user objects and inspect their associated LDAP attributes.

---

## Advantages

- Easy graphical interface.
- Powerful LDAP browsing capabilities.
- Supports advanced directory searches.
- Useful for Active Directory analysis.
- Portable executable requiring no installation.

---

## Limitations

- Limited to Active Directory environments.
- Requires appropriate permissions for full access.
- Modification capabilities should be used cautiously.

---

## Best Practices

- Use read-only enumeration whenever possible.
- Obtain authorization before accessing Active Directory.
- Avoid modifying directory objects during reconnaissance.
- Document discovered domain information carefully.

---

## Used In

- Module 04 – Enumeration

---

## References

- https://learn.microsoft.com/sysinternals/downloads/adexplorer