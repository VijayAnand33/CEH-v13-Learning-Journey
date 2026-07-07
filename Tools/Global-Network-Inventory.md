# Global Network Inventory

## Overview

Global Network Inventory (GNI) is an agentless network auditing and inventory management tool that scans computers across a network to collect detailed information about hardware, software, operating systems, installed applications, users, services, and other system components. During penetration testing and security assessments, it is used to enumerate comprehensive information about target systems from a centralized interface.

---

## Purpose

Global Network Inventory is used to:

- Perform comprehensive host enumeration.
- Collect hardware and software inventory.
- Enumerate operating system information.
- Identify installed applications and services.
- Gather user, group, and NetBIOS information.
- Audit systems across a network.

---

## Key Features

- Agentless network inventory.
- Single host and IP range scanning.
- Hardware and software inventory.
- Operating system and BIOS enumeration.
- User, service, and NetBIOS enumeration.
- Generates centralized audit reports.

---

## Installation

Install Global Network Inventory on a Windows system.

Launch the application from the Start Menu:

```text
Global Network Inventory
```

---

## Typical Workflow

```mermaid
flowchart LR
    A[Specify Target Host] --> B[Authenticate]
    B --> C[Perform Audit Scan]
    C --> D[Collect System Information]
    D --> E[Generate Inventory Report]

    style A fill:#1f2937,color:#fff,stroke:#2563eb
    style B fill:#374151,color:#fff,stroke:#2563eb
    style C fill:#4b5563,color:#fff,stroke:#2563eb
    style D fill:#7c3aed,color:#fff,stroke:#8b5cf6
    style E fill:#059669,color:#fff,stroke:#10b981
```

---

## CEH Practical Example

In **Module 04 – Enumeration**, Global Network Inventory was used to perform a comprehensive audit of a Windows Server 2022 system. The tool enumerated operating system information, hardware details, installed software, user accounts, services, NetBIOS information, shared resources, and other system components through a centralized inventory scan.

---

## Advantages

- Agentless deployment.
- Comprehensive hardware and software inventory.
- Supports auditing of multiple hosts.
- Easy-to-use graphical interface.
- Generates detailed inventory reports.

---

## Limitations

- Full enumeration may require valid credentials.
- Windows-based application.
- Scan duration depends on network size and target systems.

---

## Best Practices

- Scan only systems you are authorized to assess.
- Use least-privilege credentials whenever possible.
- Validate important findings using additional tools.
- Secure generated inventory reports as they may contain sensitive information.

---

## Used In

- Module 04 – Enumeration

---

## References

- https://www.softinventive.com/global-network-inventory/