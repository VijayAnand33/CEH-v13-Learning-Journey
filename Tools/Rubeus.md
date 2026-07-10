# Rubeus

## Overview

Rubeus is an open-source post-exploitation tool designed for interacting with the Kerberos authentication protocol in Active Directory environments. It enables security professionals to enumerate Kerberos tickets, perform Kerberoasting and AS-REP Roasting attacks, request Ticket Granting Tickets (TGTs), and analyze Kerberos authentication mechanisms during authorized security assessments.

---

## Purpose

Rubeus is used to:

- Interact with the Kerberos protocol.
- Perform Kerberoasting attacks.
- Request and manage Kerberos tickets.
- Enumerate Service Principal Names (SPNs).
- Assess Active Directory authentication security.

---

## Key Features

- Kerberoasting.
- Ticket management.
- TGT and TGS requests.
- Kerberos enumeration.
- PowerShell and executable versions.
- Active Directory focused.

---

## Installation

Download the compiled executable from the GhostPack project.

Execute:

```cmd
Rubeus.exe
```

---

## Basic Syntax

```cmd
Rubeus.exe kerberoast
```

---

## Commonly Used Commands

| Command | Description |
|---------|-------------|
| `kerberoast` | Extract Kerberos service ticket hashes |
| `asreproast` | Perform AS-REP Roasting |
| `triage` | Display Kerberos tickets |
| `klist` | List Kerberos tickets |
| `purge` | Purge cached tickets |

---

## Typical Workflow

```mermaid
flowchart TD

A[Execute Rubeus]
-->B[Request Kerberos Tickets]
-->C[Extract Service Ticket Hashes]
-->D[Save Hashes]
-->E[Offline Password Cracking]

classDef start fill:#1f2937,color:#fff,stroke:#2563eb
classDef process fill:#374151,color:#fff,stroke:#2563eb
classDef success fill:#059669,color:#fff,stroke:#10b981

class A start
class B,C,D process
class E success
```

---

## CEH Practical Example

In **Module 06 – System Hacking**, Rubeus was executed after obtaining elevated privileges within the Active Directory environment. The **kerberoast** function extracted Kerberos service ticket hashes for privileged accounts, which were later transferred to the attacker machine and cracked offline using Hashcat.

---

## Advantages

- Comprehensive Kerberos functionality.
- Excellent Active Directory integration.
- Lightweight executable.
- Widely used in penetration testing.
- Open-source.

---

## Limitations

- Requires domain access.
- Easily detected by modern monitoring solutions.
- Dependent on Kerberos configuration.
- Intended only for authorized assessments.

---

## Best Practices

- Execute only in authorized environments.
- Secure extracted ticket hashes.
- Monitor Kerberos ticket requests.
- Remove artifacts after testing.
- Document all findings.

---

## Used In

- Module 06 – System Hacking

---

## References

- https://github.com/GhostPack/Rubeus