# Censys

> **Category:** Internet Intelligence / Attack Surface Discovery
>
> **Platform:** Web, API
>
> **License:** Freemium

---

# Overview

Censys is an internet intelligence platform that continuously scans and indexes internet-facing hosts, services, certificates, and network infrastructure. It enables security professionals to discover publicly exposed assets, identify vulnerable systems, analyze digital certificates, and gain visibility into an organization's external attack surface.

Unlike traditional vulnerability scanners, Censys collects global internet scan data, allowing users to search for exposed devices, open ports, services, operating systems, SSL/TLS certificates, and other internet-connected assets without directly scanning the target themselves.

---

# Purpose

Censys assists ethical hackers and security professionals by:

- Discovering internet-facing assets.
- Identifying exposed services and ports.
- Enumerating SSL/TLS certificates.
- Mapping an organization's external attack surface.
- Detecting publicly accessible devices.
- Supporting reconnaissance and OSINT activities.

---

# Features

- Global internet host search
- Certificate transparency search
- Domain and IP intelligence
- Attack surface management
- Internet-wide service enumeration
- Advanced search filters
- Asset monitoring
- REST API support
- Historical host data
- Web-based interface

---

# Installation

Censys is primarily accessed through its web platform.

Visit:

```
https://search.censys.io
```

(Optional) Install the Python CLI:

```bash
pip install censys
```

Configure API credentials:

```bash
censys config
```

---

# Basic Workflow

```text
Define Search Target
        │
        ▼
Search Domain / IP / Certificate
        │
        ▼
Review Internet-Exposed Assets
        │
        ▼
Analyze Open Ports & Services
        │
        ▼
Identify Potential Risks
        │
        ▼
Document Findings
```

---

# Practical Example

During reconnaissance, Censys was used to identify internet-exposed assets belonging to the target organization. By searching for domains, IP addresses, and SSL/TLS certificates, the platform revealed publicly accessible hosts, running services, open ports, and certificate information.

This intelligence helped build an external attack surface profile before conducting further security assessment activities.

---

# Advantages

- Massive internet-wide asset database
- No direct scanning of the target required
- Excellent certificate search capabilities
- Powerful filtering and search queries
- Web-based interface
- Historical asset information
- API integration
- Useful for OSINT and reconnaissance

---

# Limitations

- Limited features in the free tier
- Data freshness depends on scan schedules
- Does not exploit vulnerabilities
- Some assets may not be indexed immediately
- Advanced features require a paid subscription

---

# Alternatives

- Shodan
- ZoomEye
- BinaryEdge
- FOFA
- ONYPHE

---

# Used In

- [Module 18 - IoT and OT Hacking](../Modules/Module-18-IoT-and-OT-Hacking/README.md)

---

# References

- https://search.censys.io/
- https://docs.censys.io/
- https://github.com/censys

---