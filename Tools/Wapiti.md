# Wapiti

## Overview

Wapiti is an open-source web application vulnerability scanner that performs black-box scans by injecting payloads into web application parameters and analyzing responses for potential vulnerabilities. It supports multiple modules for detecting issues such as XSS, SQL injection, file disclosure, and more.

---

## Purpose

Wapiti automates the detection of web application vulnerabilities by crawling target sites, testing input points with crafted payloads, and reporting suspicious responses for manual verification.

---

## Key Features

- Web crawling and parameter discovery
- Detection modules for XSS, SQL injection, file disclosure, command injection, and more
- Report generation in multiple formats (HTML, XML)
- Customizable attack modules and payloads
- Supports authentication and session handling

---

## Installation

### Linux

```bash
sudo apt install wapiti
```

### Verify Installation

```bash
wapiti --version
```

---

## Basic Usage

```bash
wapiti http://example.com -o report.html
```

To enable specific modules:

```bash
wapiti -u http://example.com -m xss,sqli -o findings.html
```

---

## Common Options

| Option | Description |
|--------|-------------|
| `-u` / positional URL | Target URL to scan. |
| `-m` | Comma-separated modules to run (e.g., `xss,sqli`). |
| `-o` | Output file (HTML, XML). |
| `-f` | Output format (html, xml). |
| `--scope` | Limit scanning to a specific host or path. |
| `--auth` | Provide authentication credentials or use session cookies. |
| `--crawl` | Control crawler depth and behavior. |
| `--timeout` | Set request timeout. |

---

## Typical Workflow

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#E3F2FD', 'primaryTextColor': '#0D47A1', 'primaryBorderColor': '#1565C0', 'lineColor': '#546E7A', 'secondaryColor': '#E8F5E9', 'tertiaryColor': '#F3E5F5'}}}%%
flowchart TD
	A[Select Target Site] --> B[Run Wapiti Crawler]
	B --> C[Discover Parameters & Inputs]
	C --> D[Run Detection Modules (XSS, SQLi, etc.)]
	D --> E[Collect Suspicious Responses]
	E --> F[Generate Report]
	F --> G[Manually Validate Findings]

	classDef start fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px,color:#1B5E20;
	classDef process fill:#E3F2FD,stroke:#1565C0,stroke-width:1.5px,color:#0D47A1;
	classDef end fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px,color:#4A148C;

	class A start;
	class B,C,D,E,F process;
	class G end;
```

---

## CEH Practical Example

In Module 14 – Web Application Hacking, Wapiti was used to scan the target application for common input-based vulnerabilities and to generate a report for manual follow-up.

---

## Advantages

- Lightweight and easy to use.
- Multiple detection modules for common vulnerabilities.
- Generates readable reports suitable for triage.

---

## Limitations

- May produce false positives that require manual validation.
- Not as feature-rich as some commercial scanners.
- Scanning can be noisy and should be authorized.

---

## Best Practices

- Obtain authorization before scanning.
- Limit the crawler scope to avoid unintended content exposure.
- Combine automated results with manual testing.
- Review and validate all reported findings.

---

## Used In

- Module 14 – Web Application Hacking

---

## References

- Official: https://wapiti-scanner.github.io/
- Official Documentation: https://wapiti-scanner.github.io/documentation.html