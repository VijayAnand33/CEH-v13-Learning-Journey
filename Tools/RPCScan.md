# RPCScan

## Overview

RPCScan is a command-line enumeration tool used to communicate with Remote Procedure Call (RPC) services running on target systems. It helps identify RPC programs, port mappings, Network File System (NFS) services, and mount points, making it useful during network reconnaissance and NFS enumeration.

---

## Purpose

RPCScan is used to:

- Enumerate Remote Procedure Call (RPC) services.
- Identify NFS-related services.
- Discover RPC port mappings.
- Verify NFS service availability.
- Assist in network service enumeration.

---

## Key Features

- Enumerates RPC services and port mappings.
- Detects NFS services.
- Simple command-line interface.
- Lightweight and easy to use.
- Useful during Linux and Windows NFS reconnaissance.

---

## Installation

Clone the repository:

```bash
git clone <repository_url>
```

Navigate to the directory:

```bash
cd RPCScan
```

---

## Basic Syntax

```bash
python3 rpc-scan.py <target_ip> --rpc
```

Example:

```bash
python3 rpc-scan.py 10.10.1.19 --rpc
```

---

## Commonly Used Options

| Option | Description |
|---------|-------------|
| `--rpc` | Enumerate RPC services on the target host |

---

## Typical Workflow

```mermaid
flowchart LR
    A[Target Host] --> B[Query RPC Services]
    B --> C[Enumerate Port Mapper]
    C --> D[Identify NFS Services]
    D --> E[Analyze Results]

    style A fill:#1f2937,color:#fff,stroke:#2563eb
    style B fill:#374151,color:#fff,stroke:#2563eb
    style C fill:#4b5563,color:#fff,stroke:#2563eb
    style D fill:#7c3aed,color:#fff,stroke:#8b5cf6
    style E fill:#059669,color:#fff,stroke:#10b981
```

---

## CEH Practical Example

In **Module 04 – Enumeration**, RPCScan was used to enumerate Remote Procedure Call (RPC) services on the target Windows Server 2019 system. The scan verified that the NFS service was running on TCP port 2049 and displayed the available RPC information.

---

## Advantages

- Fast RPC enumeration.
- Lightweight command-line utility.
- Useful for NFS reconnaissance.
- Easy to integrate into penetration testing workflows.

---

## Limitations

- Limited to RPC-related enumeration.
- Depends on RPC services being accessible.
- May be restricted by firewall rules.

---

## Best Practices

- Use only on authorized systems.
- Correlate RPC results with NFS enumeration.
- Document discovered services for further analysis.
- Verify findings using multiple enumeration techniques.

---

## Used In

- Module 04 – Enumeration

---

## References

- https://github.com/