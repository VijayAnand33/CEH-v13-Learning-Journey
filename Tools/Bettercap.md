# Bettercap

> **Category:** Network Attack and Monitoring Framework
>
> **Platform:** Linux, macOS
>
> **License:** Open Source
>
> **Official Website:** https://www.bettercap.org/

---

## Overview

Bettercap is a powerful network attack and monitoring framework used for network reconnaissance, packet sniffing, Man-in-the-Middle (MITM) attacks, ARP spoofing, and session interception. It enables penetration testers to analyze network traffic, discover active hosts, and evaluate network security within authorized environments.

---

## Key Features

- Network reconnaissance
- Packet sniffing
- ARP spoofing
- Man-in-the-Middle (MITM) attacks
- DNS spoofing
- Network probing
- Credential sniffing
- Modular command framework

---

## Common Usage

Launch Bettercap:

```bash
sudo bettercap -iface eth0
```

Common workflow:

1. Select the network interface.
2. Enable network probing.
3. Discover active hosts.
4. Start packet sniffing.
5. Analyze captured traffic.

---

## CEH Practical Example

During **Module 11 – Session Hijacking**, Bettercap was used to perform network reconnaissance and packet sniffing by enabling the **net.probe**, **net.recon**, and **net.sniff** modules. The generated ARP traffic was captured with Wireshark, demonstrating how abnormal network behavior can indicate an attempted session hijacking attack.

---

## Defensive Perspective

Organizations should implement encrypted communications, Dynamic ARP Inspection (DAI), network segmentation, intrusion detection systems, and continuous traffic monitoring to detect ARP spoofing and other network-based session hijacking techniques.

---

## Used In

- Module 11 – Session Hijacking

---

## References

- Official Website: https://www.bettercap.org/
- Official Documentation: https://www.bettercap.org/modules/