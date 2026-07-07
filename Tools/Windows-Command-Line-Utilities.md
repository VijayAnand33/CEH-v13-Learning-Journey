# Windows Command-Line Utilities

## Overview

Windows Command-Line Utilities are built-in administrative tools that allow users and security professionals to manage, troubleshoot, and gather information about Windows systems through the Command Prompt. During penetration testing and security assessments, these utilities are frequently used to enumerate system information, network resources, user accounts, shared folders, and NetBIOS details without requiring third-party software.

---

## Purpose

Windows Command-Line Utilities are used to:

- Enumerate NetBIOS information.
- Identify shared network resources.
- Display active network connections.
- Enumerate users, groups, and shares.
- Gather system and network information.
- Assist in Windows reconnaissance and enumeration.

---

## Key Features

- Built into all Windows operating systems.
- Requires no additional installation.
- Provides system and network administration capabilities.
- Supports enumeration of network resources.
- Useful for troubleshooting and penetration testing.
- Lightweight and command-line based.

---

## Installation

No installation is required.

Windows Command-Line Utilities are included by default with Microsoft Windows.

Launch Command Prompt:

```cmd
cmd
```

---

## Commonly Used Commands

| Command | Description |
|---------|-------------|
| `nbtstat -a <IP>` | Display the NetBIOS name table of a remote computer |
| `nbtstat -c` | Display the NetBIOS name cache |
| `net use` | Display or manage shared network connections |
| `net view` | List shared resources on a computer |
| `net user` | Display or manage user accounts |
| `net localgroup` | Display local groups |
| `net share` | Display shared folders |

---

## Typical Workflow

```mermaid
flowchart LR
    A[Launch Command Prompt] --> B[Execute Enumeration Command]
    B --> C[Collect System Information]
    C --> D[Analyze Results]

    style A fill:#1f2937,color:#fff,stroke:#2563eb
    style B fill:#374151,color:#fff,stroke:#2563eb
    style C fill:#7c3aed,color:#fff,stroke:#8b5cf6
    style D fill:#059669,color:#fff,stroke:#10b981
```

---

## CEH Practical Example

In **Module 04 – Enumeration**, the `nbtstat` utility was used to enumerate the NetBIOS name table and cached NetBIOS entries of a remote Windows system, while `net use` was used to enumerate existing network connections and shared resources.

---

## Advantages

- Available on every Windows system.
- No additional software required.
- Fast and lightweight.
- Useful for reconnaissance and system administration.
- Supports multiple enumeration tasks.

---

## Limitations

- Primarily designed for Windows environments.
- Some commands require administrative privileges.
- Information available depends on system configuration and permissions.

---

## Best Practices

- Use only on systems you are authorized to assess.
- Verify enumeration results using multiple techniques.
- Avoid making unnecessary configuration changes.
- Document all collected information during assessments.

---

## Used In

- Module 04 – Enumeration

---

## References

- https://learn.microsoft.com/windows-server/administration/windows-commands/