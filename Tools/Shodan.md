# Shodan

## Overview

Shodan is a specialized search engine that indexes Internet-connected devices and services instead of websites. It enables security professionals to discover publicly accessible systems, identify exposed services, and gather information about IoT devices, industrial control systems, and network infrastructure.

---

## Key Features

- Searches Internet-connected devices.
- Identifies open ports and services.
- Displays device banners and metadata.
- Filters results by port, location, organization, and product.
- Discovers exposed IoT and OT devices.
- Supports reconnaissance during penetration testing.

---

## Common Usage

```
port:1883
```

Search for MQTT-enabled IoT devices.

---

## Practical Example

During **Module 18 – IoT and OT Hacking**, Shodan was used to search for Internet-connected MQTT devices by querying the default MQTT port (1883). The discovered devices provided information such as open ports, services, hostnames, and network details during the footprinting phase.

---

## Defensive Perspective

Organizations should regularly monitor their Internet-facing assets using search engines such as Shodan to identify unintentionally exposed services, close unnecessary ports, and reduce the attack surface of IoT and OT environments.

---

## Used In

- Module 18 – IoT and OT Hacking

---

## Official Resources

- https://www.shodan.io

---