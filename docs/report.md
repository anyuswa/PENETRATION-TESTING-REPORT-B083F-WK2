# 🔐 Penetration Testing Report — Week 2

### Footprinting, Reconnaissance & Network Scanning

**Cybersecurity Internship | Networkwalks**

![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-blue)
![Phase](https://img.shields.io/badge/Phase-Reconnaissance%20%26%20Scanning-orange)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux%20%7C%20Windows-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 👤 Project Information

| Field                                      | Details                                                               |
| ------------------------------------------ | --------------------------------------------------------------------- |
| **Pentester / Cybersecurity Professional** | Asanda Lloyd Nyuswa                                                   |
| **Program / Batch**                        | Cybersecurity Int. B083F                                              |
| **Date**                                   | 17 September 2026                                                     |
| **Modules Completed**                      | W2-PM1 — Multiple Kali Tools<br>W2-PM5 — Zenmap Scanning              |
| **Client / Target**                        | Networkwalks — secured written permission<br>My own local LAN network |
| **Permission Secured**                     | ✅ Yes                                                                 |
| **Phase 1**                                | Reconnaissance & Footprinting                                         |
| **Phase 2**                                | Scanning & Network Discovery                                          |
| **Phases 3–5**                             | In Progress                                                           |

---

## ⚠️ Authorization & Liability Notice

> **Important:** All activities documented in this repository were performed only against systems and devices where authorization had been secured or against systems/devices owned by the tester.
>
> These materials are provided for educational and research purposes. Unauthorized access, scanning, or testing of systems may be illegal. Always obtain appropriate authorization and operate within the agreed scope before conducting cybersecurity testing.

---

## 📋 Project Overview

This Week 2 practical project covers two main cybersecurity activities:

1. **Footprinting & Reconnaissance** against the `networkwalks.com` domain using multiple Kali Linux tools.
2. **Network Scanning & Discovery** of the tester's own local network using Zenmap.

The exercises demonstrate how a security professional can progress from collecting publicly available information to identifying active hosts within an authorized network environment.

Each activity documents the command/tool used, the observed result, supporting evidence, and the security relevance of the finding.

---

# 🛰️ Phase 1 — Footprinting & Reconnaissance

The reconnaissance phase used six Kali Linux tools to collect different categories of information about the target domain.

### Tools

| Tool         | Purpose                                                                                |
| ------------ | -------------------------------------------------------------------------------------- |
| **WHOIS**    | Find domain registration details, including registration information and name servers. |
| **WhatWeb**  | Fingerprint web technologies such as the server, CMS, plugins and IP information.      |
| **nslookup** | Resolve the domain name to its IP address using DNS.                                   |
| **curl -I**  | Inspect HTTP response headers returned by the website.                                 |
| **wafw00f**  | Identify whether a Web Application Firewall protects the website.                      |
| **DNSRecon** | Enumerate DNS records such as NS, MX, SPF, TXT and SRV records.                        |

---

## 🔎 Reconnaissance Findings

### WHOIS

WHOIS was used to obtain publicly available domain registration information and identify domain infrastructure such as name servers.

### WhatWeb

WhatWeb was used to fingerprint the website's technologies.

The report identified:

* WordPress **7.1**
* WP Download Manager **3.3.58**
* Additional website technology information

### nslookup

The domain was resolved using `nslookup`.

**Observed IP:**

```text
192.232.216.135
```

### curl

The `curl -I` command was used to inspect HTTP response headers.

The response also exposed:

```text
/wp-json/
```

### wafw00f

Wafw00f identified:

```text
ModSecurity (SpiderLabs)
```

### DNSRecon

DNSRecon was used to enumerate DNS infrastructure, including:

* Name servers
* Mail servers
* SPF/TXT records
* Service records
* DNS software information

These observations are documented in the original practical report.

---

# 🌐 Phase 2 — Network Scanning & Discovery

The second practical involved scanning the tester's **own local network** using Zenmap.

The objectives were to:

* Identify the local IP address
* Identify the LAN subnet
* Discover active hosts
* Identify IP and MAC addresses
* Generate a network topology

Windows `ipconfig` was first used to identify the local network configuration. The subnet was then entered into Zenmap using a Ping Scan to identify active hosts.

---

## 🖥️ Discovered Hosts

The practical results documented the following hosts:

|  # | Host            |
| -: | --------------- |
|  1 | `192.168.8.1`   |
|  2 | `192.168.8.58`  |
|  3 | `192.168.8.105` |
|  4 | `192.168.8.119` |
|  5 | `192.168.8.121` |

### MAC Addresses

|  # | MAC Address                     |
| -: | ------------------------------- |
|  1 | `E2:98:5A:26:B3:2E`             |
|  2 | `3A:AF:D4:0B:FE:F4`             |
|  3 | `DA:91:44:73:AF:01`             |
|  4 | `6A:4F:87:0A:90:70`             |
|  5 | `D0-AB-D5-AA-F3-CA` — Local MAC |

> **Note:** The original report states that the actual subnet, number of hosts and addresses should be replaced with the tester's own network results when submitting the report.

---

# 📊 Risk Analysis

The following risks were identified from the information-gathering and network-discovery exercises.

|     # | Risk / Finding                                   | Evidence / Observation                                      | Potential Impact                                                                                    | Risk Level    |
| ----: | ------------------------------------------------ | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------------- |
| **1** | **Web technology information exposed**           | WhatWeb identified WordPress and WP Download Manager        | Exposed technology/version information may help identify software requiring further security review | 🟡 **Medium** |
| **2** | **Server IP address identifiable**               | nslookup resolved the domain to `192.232.216.135`           | Provides information about the network location of the web service                                  | 🟢 **Low**    |
| **3** | **HTTP technical information exposed**           | curl returned HTTP response headers and exposed `/wp-json/` | May assist technology fingerprinting and further enumeration                                        | 🟢 **Low**    |
| **4** | **WAF technology identifiable**                  | wafw00f identified ModSecurity (SpiderLabs)                 | Reveals information about the web application's security architecture                               | 🟢 **Low**    |
| **5** | **DNS infrastructure information exposed**       | DNSRecon identified DNS, mail and service-related records   | DNS information can help build a broader infrastructure profile                                     | 🟡 **Medium** |
| **6** | **Multiple live hosts visible on local network** | Zenmap identified live hosts in the example network         | Unknown or unauthorized devices may potentially be present on a network                             | 🟡 **Medium** |

### Risk Level Legend

| Indicator | Level    |
| --------- | -------- |
| 🔴        | Critical |
| 🟡        | Medium   |
| 🟢        | Low      |

> **Important:** These findings represent observations from the footprinting and scanning exercises. They are **not confirmed vulnerabilities**. No exploitation or vulnerability validation was performed as part of these two modules.

---

# 🛡️ Recommendations

Based on the observations documented during the practical, the following security improvements were recommended:

1. **Review publicly exposed technology information**
2. **Keep CMS, plugins and other software updated**
3. **Review HTTP response headers**
4. **Review DNS records regularly**
5. **Properly configure and monitor the WAF**
6. **Perform regular internal network discovery**
7. **Investigate unknown devices**
8. **Maintain updated network documentation**
9. **Perform security testing only with appropriate authorization**

These recommendations are based on the observations recorded in the report.

---

# 🧰 Technology Stack

```text
Operating Systems
├── Kali Linux
└── Windows

Reconnaissance
├── WHOIS
├── WhatWeb
├── nslookup
├── curl
├── wafw00f
└── DNSRecon

Network Discovery
├── Zenmap
├── Nmap
└── Windows CMD
```

---

# 📁 Repository Structure

```text
networkwalks-pentest/
│
├── README.md
│
├── docs/
│   ├── report.md
│   └── methodology.md
│
├── evidence/
│   ├── README.md
│   ├── image1.png
│   ├── image2.png
│   ├── image3.png
│   ├── image4.png
│   ├── image5.png
│   ├── image6.png
│   ├── image7.png
│   └── image8.png
│
├── data/
│   └── findings.md
│
├── src/
│   └── commands.md
│
├── LICENSE
└── .gitignore
```

---

# 📸 Evidence

Screenshots and supporting evidence collected during the practical are stored in:

```text
/evidence
```

The evidence covers the reconnaissance and network-scanning activities documented in the report.

---

# 🎯 Learning Outcomes

Through these practical exercises, I developed experience with:

* Domain reconnaissance
* DNS enumeration
* Web technology fingerprinting
* HTTP header inspection
* WAF identification
* Network discovery
* IP address identification
* MAC address identification
* Network topology discovery
* Security finding documentation
* Risk analysis
* Security recommendations
* Authorized cybersecurity testing

The exercises demonstrated the importance of information gathering before attempting further security assessment.

---

# 👨‍💻 Author

**Asanda Lloyd Nyuswa**

Cybersecurity Professional
Program/Batch: **Cybersecurity Int. B083F**

**Cybersecurity Program — Networkwalks**

**Week 02**

---

## 📌 Disclaimer

This repository is intended for **authorized cybersecurity education, research and documentation**.

Only perform reconnaissance, scanning or other security testing against systems for which you have explicit authorization or ownership.

**Never use these techniques against unauthorized targets.**

---

⭐ *Cybersecurity is not about breaking systems — it is about understanding them, identifying risk, and improving their security.*
