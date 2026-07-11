# Caido

> **Category:** Web Application Security Testing Proxy
>
> **Platform:** Windows, Linux, macOS
>
> **License:** Freemium
>
> **Official Website:** https://caido.io/

---

## Overview

Caido is a modern web security testing platform designed for penetration testers and security researchers to inspect, intercept, and manipulate HTTP and HTTPS traffic. It provides an intuitive interface for analyzing requests and responses, modifying traffic in real time, and identifying vulnerabilities in web applications.

Caido combines proxy interception, request editing, project management, and automation features to simplify web application security assessments.

---

## Key Features

- HTTP/HTTPS proxy interception
- Request and response modification
- Real-time traffic inspection
- Project-based workflow
- Request history and sitemap
- Manual request forwarding
- Traffic replay capabilities
- Modern web interface

---

## Common Usage

Typical workflow:

1. Create a new project.
2. Configure the local proxy.
3. Route browser traffic through Caido.
4. Intercept HTTP requests.
5. Modify and forward requests for analysis.

---

## CEH Practical Example

During **Module 11 – Session Hijacking**, Caido was configured as an interception proxy between the victim and the target web application. Intercepted HTTP requests were modified before being forwarded, demonstrating how attackers can manipulate web traffic to hijack user sessions and redirect victims to attacker-controlled content.

---

## Defensive Perspective

Organizations should enforce HTTPS, implement secure session management, validate server certificates, deploy HTTP Strict Transport Security (HSTS), and monitor for unauthorized proxy usage to reduce the risk of session hijacking through intercepted web traffic.

---

## Used In

- Module 11 – Session Hijacking

---

## References

- Official Website: https://caido.io/
- Official Documentation: https://docs.caido.io/