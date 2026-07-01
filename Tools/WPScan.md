# WPScan

## Overview

WPScan is a WordPress security scanner designed to find vulnerabilities in WordPress core, plugins, and themes. It leverages a vulnerability database (WPVulnDB) and supports enumeration, fingerprinting, and reporting to assist security assessments of WordPress sites.

---

## Purpose

The primary purpose of WPScan is to automate the discovery of WordPress-specific security issues such as outdated plugins/themes, vulnerable versions, and exposed usernames to help prioritize manual verification and remediation.

---

## Key Features

- WordPress fingerprinting (version detection)
- Plugin and theme enumeration
- Vulnerability lookup via WPVulnDB (API token)
- Username enumeration
- Multiple output formats and report generation
- Support for passive and active detection methods

---

## Installation

### Linux (Debian / Kali)

```bash
sudo apt install wpscan
```

### Ruby gem (alternative)

```bash
sudo gem install wpscan
```

### Verify Installation

```bash
wpscan --version
```

---

## Basic Usage

1. Enumerate plugins and attempt vulnerability checks:

```bash
wpscan --url https://example.com --enumerate p --api-token YOUR_WPVULNDB_TOKEN
```

2. Enumerate users and plugins, save output:

```bash
wpscan --url https://example.com --enumerate u,p --format json --output wpscan-report.json
```

---

## Common Options

| Option | Description |
|--------|-------------|
| `--url` | Target WordPress site URL. |
| `--enumerate` | What to enumerate: `u` (users), `p` (plugins), `t` (themes), `vp` (vulnerable plugins), `tt` (timthumbs), etc. Use commas to combine. |
| `--plugins-detection` | Plugin detection method: `passive` or `mixed`/`aggressive`. |
| `--plugins-version-detection` | Attempt to detect plugin versions for vulnerability correlation. |
| `--api-token` | WPVulnDB API token to enable vulnerability lookups. |
| `--format` | Output format: `cli`, `json`, `xml`. |
| `--output` | Write scan output to a file. |
| `--random-agent` | Use a random User-Agent string for requests. |
| `--threads` | Number of concurrent threads (speeds up scanning). |
| `--no-banner` | Suppress the WPScan banner. |

---

## Typical Workflow

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#E3F2FD', 'primaryTextColor': '#0D47A1', 'primaryBorderColor': '#1565C0', 'lineColor': '#546E7A', 'secondaryColor': '#E8F5E9', 'tertiaryColor': '#F3E5F5'}}}%%
flowchart TD
    A[Target WordPress Site] --> B[Run WPScan]
    B --> C[Enumerate Users, Plugins & Themes]
    C --> D[Identify Potential Vulnerable Components]
    D --> E[Lookup Vulnerabilities (WPVulnDB)]
    E --> F[Manually Validate Findings]
    F --> G[Generate Report & Remediation Plan]

    classDef start fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px,color:#1B5E20;
    classDef process fill:#E3F2FD,stroke:#1565C0,stroke-width:1.5px,color:#0D47A1;
    classDef end fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px,color:#4A148C;

    class A start;
    class B,C,D,E,F process;
    class G end;
```

---

## CEH Practical Example

During Module 14 – Web Application Hacking, WPScan can be used to enumerate plugins and identify a plugin with a known CVE, which is then validated manually before attempting any controlled exploitation.

Example:

```bash
wpscan --url https://target.example --enumerate p --api-token $WPVULNDB_TOKEN --format json --output findings.json
```

---

## Advantages

- WordPress-specific checks and large vulnerability database.
- Simple command-line interface suitable for automation.
- Supports API integration for up-to-date vulnerability data.

---

## Limitations

- May produce false positives; manual verification required.
- Aggressive enumeration can be noisy and detectable.
- Requires WPVulnDB API token for full vulnerability lookup functionality.

---

## Best Practices

- Always obtain authorization before scanning WordPress sites.
- Use `--random-agent` and throttle requests to avoid disrupting services.
- Complement WPScan results with manual validation and additional tools.
- Keep WPScan and its vulnerability data up to date.

---

## Used In

- Module 14 – Web Application Hacking

---

## References

- Official: https://wpscan.com/
 - Documentation: https://github.com/wpscanteam/wpscan