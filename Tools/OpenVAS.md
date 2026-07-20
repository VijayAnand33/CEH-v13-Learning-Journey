# OpenVAS

> **Category:** Vulnerability Assessment Scanner
>
> **Platform:** Linux (Greenbone Community Edition), Web Interface
>
> **License:** Open Source (GPL)

---

# Overview

OpenVAS (Open Vulnerability Assessment System) is an open-source vulnerability assessment and management framework maintained by Greenbone Networks. It performs comprehensive security scans to identify known vulnerabilities, missing security patches, misconfigurations, insecure services, and other weaknesses across network hosts.

OpenVAS uses an extensive vulnerability database known as Network Vulnerability Tests (NVTs), enabling security professionals to detect thousands of known Common Vulnerabilities and Exposures (CVEs). It is widely used during vulnerability assessment and penetration testing engagements to evaluate the security posture of systems before exploitation.

---

# Purpose

OpenVAS assists ethical hackers and security professionals by:

- Discovering live hosts and exposed services.
- Detecting known software vulnerabilities.
- Identifying missing security patches.
- Finding insecure configurations.
- Prioritizing security risks based on severity.
- Generating detailed vulnerability assessment reports.

---

# Features

- Comprehensive vulnerability scanning
- CVE-based vulnerability detection
- Automated Network Vulnerability Tests (NVTs)
- Risk severity classification (CVSS)
- Scheduled vulnerability scans
- Detailed HTML, PDF, and XML reports
- Credentialed and non-credentialed scanning
- Web-based management interface
- Asset management
- Scan history tracking

---

# Installation

Greenbone Community Edition (Kali Linux):

```bash
sudo apt update
sudo apt install gvm -y
sudo gvm-setup
sudo gvm-start
```

Access the web interface:

```
https://127.0.0.1:9392
```

---

# Basic Workflow

```text
Create Target
      │
      ▼
Create Scan Task
      │
      ▼
Select Scan Configuration
      │
      ▼
Run Vulnerability Scan
      │
      ▼
Analyze Results
      │
      ▼
Generate Report
```

---

# Practical Example

During the vulnerability assessment lab, OpenVAS was used to perform an automated security scan against the target machine.

The scan identified multiple vulnerabilities, including outdated software versions, exposed network services, and missing security patches. Each finding included its severity level, affected host, CVE reference (when applicable), and recommended remediation steps. The generated report provided a comprehensive overview of the target's security posture and helped prioritize vulnerabilities for further analysis and remediation.

---

# Advantages

- Open-source vulnerability scanner
- Large vulnerability database
- Frequent vulnerability feed updates
- Professional reporting capabilities
- Supports credentialed scanning
- Detects thousands of known vulnerabilities
- Web-based graphical interface
- Suitable for enterprise environments

---

# Limitations

- Does not exploit vulnerabilities
- Scan duration can be lengthy
- Requires significant system resources
- Detection accuracy depends on vulnerability feed updates
- May produce false positives that require manual verification

---

# Alternatives

- Nessus
- Qualys VMDR
- Rapid7 InsightVM
- Nexpose
- Nmap NSE
- Nikto

---

# Used In

- [Module 05 - Vulnerability Analysis](../Modules/Module-05-Vulnerability-Analysis/README.md)

---

# References

- https://greenbone.github.io/docs/latest/
- https://github.com/greenbone
- https://nvd.nist.gov/

---