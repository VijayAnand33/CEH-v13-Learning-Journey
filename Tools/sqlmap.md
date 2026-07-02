# sqlmap

## Overview

sqlmap is an open-source penetration testing tool that automates the process of detecting and exploiting SQL Injection vulnerabilities in web applications. It supports numerous database management systems and provides features such as database fingerprinting, database enumeration, data extraction, operating system command execution, and privilege escalation where supported.

---

## Purpose

The primary purpose of sqlmap is to assist penetration testers in identifying SQL Injection vulnerabilities and assessing their impact by automating the exploitation process. It reduces manual effort while providing accurate database fingerprinting, enumeration, and exploitation capabilities during authorized security assessments.

---

## Key Features

- Automatic SQL Injection Detection
- Database Fingerprinting
- Database Enumeration
- Table Enumeration
- Data Extraction
- Authentication Cookie Support
- Operating System Command Execution
- Database User Enumeration
- File System Access (where supported)

---

## Installation

### Linux

```bash
sudo apt install sqlmap
```

### Verify Installation

```bash
sqlmap --version
```

---

## Basic Syntax

```bash
sqlmap -u <Target_URL>
```

Example:

```bash
sqlmap -u "http://example.com/profile.php?id=1"
```

---

## Commonly Used Options

> **Copilot Task**
>
> Create a professional GitHub Markdown table explaining the following sqlmap options:
>
> - `-u`
> - `--cookie`
> - `--dbs`
> - `-D`
> - `--tables`
> - `-T`
> - `--dump`
> - `--os-shell`
> - `--batch`
>
> Include a short description and purpose for each option.

---

## Typical Workflow

> **Copilot Task**
>
> Generate a GitHub-compatible Mermaid flowchart for the following workflow:
>
> Target URL
>
> ↓
>
> Detect SQL Injection
>
> ↓
>
> Fingerprint Database
>
> ↓
>
> Enumerate Databases
>
> ↓
>
> Enumerate Tables
>
> ↓
>
> Extract Sensitive Data
>
> ↓
>
> Obtain OS Shell (if applicable)
>
> Return only Mermaid markdown.

---

## CEH Practical Example

During **Module 15 – SQL Injection**, sqlmap was used to assess an authenticated Microsoft SQL Server-backed web application. By supplying the vulnerable URL together with an authenticated session cookie, sqlmap automatically detected the SQL Injection vulnerability, fingerprinted the backend database, enumerated available databases, extracted information from the `user_login` table, and successfully obtained operating system shell access.

---

## Advantages

- Automates SQL Injection detection and exploitation.
- Supports multiple database management systems.
- Performs accurate database fingerprinting.
- Reduces manual testing effort.
- Supports authenticated web applications.
- Widely used by penetration testers and security professionals.

---

## Limitations

- Requires proper authorization before use.
- Some advanced features depend on database permissions.
- May generate false positives that require manual verification.
- Automated exploitation should always be validated by the tester.

---

## Best Practices

- Test only authorized systems.
- Verify identified vulnerabilities manually.
- Supply authentication cookies when testing authenticated applications.
- Understand each command before execution.
- Combine sqlmap with manual testing techniques for comprehensive assessments.

---

## Used In

- Module 15 – SQL Injection

---

## Related Tools

- OWASP ZAP
- ShellGPT
- Burp Suite
- cURL

---

## References

- Official Website: https://sqlmap.org/
- Official Documentation: https://github.com/sqlmapproject/sqlmap/wiki