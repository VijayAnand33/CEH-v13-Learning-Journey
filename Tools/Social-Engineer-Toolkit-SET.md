# Social-Engineer Toolkit (SET)

> **Category:** Social Engineering Framework
>
> **Platform:** Linux
>
> **License:** Open Source
>
> **Official Website:** https://github.com/trustedsec/social-engineer-toolkit

---

## Overview

The Social-Engineer Toolkit (SET) is an open-source penetration testing framework specifically designed for social engineering attacks. Developed by TrustedSec, SET automates the creation of phishing campaigns, credential harvesting websites, malicious payload delivery, and various other human-focused attack simulations used during authorized security assessments.

SET is widely used by ethical hackers and penetration testers to evaluate an organization's resilience against phishing and other social engineering attacks.

---

## Key Features

- Website cloning for phishing simulations
- Credential harvesting attacks
- Spear phishing campaign generation
- Malicious payload delivery
- USB attack creation
- Multi-attack vectors
- Integration with Metasploit Framework
- Automated social engineering workflows

---

## Common Usage

Launch the toolkit:

```bash
sudo setoolkit
```

Common attack workflow:

1. Social-Engineering Attacks
2. Website Attack Vectors
3. Credential Harvester Attack Method
4. Site Cloner
5. Specify local IP address
6. Clone target website
7. Capture submitted credentials

---

## CEH Practical Example

During **Module 09 – Social Engineering**, the Social-Engineer Toolkit (SET) was used to clone a legitimate website and launch a Credential Harvester attack. A phishing email containing a disguised hyperlink redirected the victim to the cloned login page, where submitted credentials were captured to demonstrate how phishing attacks compromise user accounts during authorized security assessments.

---

## Defensive Perspective

Organizations should deploy multi-factor authentication, conduct regular phishing awareness training, implement secure email gateways, and educate users to verify website URLs before entering credentials. Security awareness programs remain one of the strongest defenses against social engineering attacks.

---

## Used In

- Module 09 – Social Engineering

---

## References

- Official Website: https://trustedsec.com/
- Official GitHub Repository: https://github.com/trustedsec/social-engineer-toolkit

---