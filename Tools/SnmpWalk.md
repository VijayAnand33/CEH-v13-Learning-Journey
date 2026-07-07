# SnmpWalk

## Overview

SnmpWalk is a command-line utility included with the Net-SNMP package that retrieves management information from SNMP-enabled devices by traversing the Management Information Base (MIB). It is commonly used during penetration testing and network administration to enumerate system information, network configuration, interfaces, routing tables, and other management data exposed through the Simple Network Management Protocol (SNMP).

---

## Purpose

SnmpWalk is used to:

- Enumerate SNMP-enabled devices.
- Retrieve Object Identifiers (OIDs).
- Enumerate system and network information.
- Identify exposed management information.
- Assess SNMP security configurations.

---

## Key Features

- Supports SNMP v1, v2c, and v3.
- Traverses the complete MIB tree automatically.
- Retrieves management information using OIDs.
- Lightweight command-line utility.
- Compatible with Linux and Unix-based systems.

---

## Installation

### Debian / Ubuntu / Parrot OS

```bash
sudo apt update
sudo apt install snmp
```

Verify installation:

```bash
snmpwalk --version
```

---

## Basic Syntax

```bash
snmpwalk -v <version> -c <community_string> <target_ip>
```

Example:

```bash
snmpwalk -v2c -c public 10.10.1.22
```

---

## Commonly Used Options

| Option | Description |
|---------|-------------|
| `-v1` | Use SNMP Version 1 |
| `-v2c` | Use SNMP Version 2c |
| `-v3` | Use SNMP Version 3 |
| `-c` | Specify the community string |

---

## Typical Workflow

```mermaid
flowchart LR
    A[Target SNMP Device] --> B[Authenticate using Community String]
    B --> C[Traverse MIB]
    C --> D[Retrieve OIDs]
    D --> E[Analyze Information]

    style A fill:#1f2937,color:#fff,stroke:#2563eb
    style B fill:#374151,color:#fff,stroke:#2563eb
    style C fill:#7c3aed,color:#fff,stroke:#8b5cf6
    style D fill:#059669,color:#fff,stroke:#10b981
    style E fill:#2563eb,color:#fff,stroke:#60a5fa
```

---

## CEH Practical Example

In **Module 04 – Enumeration**, SnmpWalk was used to enumerate a Windows Server 2022 system using SNMPv1 and SNMPv2c with the default `public` community string. The enumeration revealed accessible Object Identifiers (OIDs), system information, and network management data.

---

## Advantages

- Simple and lightweight.
- Enumerates complete MIB trees.
- Supports multiple SNMP versions.
- Widely used for network management and security assessments.

---

## Limitations

- Requires valid community strings or credentials.
- SNMPv1 and SNMPv2c transmit community strings in plaintext.
- Large MIB trees may produce extensive output.

---

## Best Practices

- Disable default community strings.
- Prefer SNMPv3 whenever possible.
- Restrict SNMP access using firewall rules.
- Monitor SNMP traffic for unauthorized enumeration attempts.

---

## Used In

- Module 04 – Enumeration

---

## References

- https://www.net-snmp.org/
- https://www.net-snmp.org/docs/man/snmpwalk.html