# W2-PM-FINAL — Footprinting & Network Scanning

A GitHub-ready documentation repository for Week 2 of a cybersecurity internship practical covering **reconnaissance/footprinting** and **local network discovery**.

> **Authorization & safety:** The activities documented here were described as being performed only against systems with written permission or systems owned by the author. Do not run reconnaissance or scanning against systems you do not own or lack explicit authorization to test.

## Scope

- **Phase 1:** Reconnaissance & Footprinting
- **Phase 2:** Scanning & Network Discovery
- **Phase 3–5:** In progress in the source report
- **Footprinting target:** `networkwalks.com` (authorized according to the report)
- **Network scanning target:** author's local LAN

## Tools documented

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration and nameserver information |
| WhatWeb | Web technology fingerprinting |
| nslookup | DNS resolution |
| curl | HTTP response headers |
| wafw00f | WAF detection |
| dnsrecon | DNS record enumeration |
| Zenmap / Nmap GUI | Local network host discovery |
| Windows CMD | Local IP/MAC identification |

## Repository layout

```text
.
├── README.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── report.md
│   └── methodology.md
├── evidence/
│   ├── image1.png ... image8.png
│   └── README.md
├── data/
│   └── findings.md
└── src/
    └── commands.md
```

## Key observations from the report

The report records publicly observable technology, DNS, HTTP-header, WAF, and local-network discovery results. It explicitly treats these as **observations rather than confirmed vulnerabilities**; no exploitation or vulnerability validation was performed in these two modules.

## Reproducing the work

Use only an authorized target or your own lab. See [`src/commands.md`](src/commands.md) for the command list transcribed from the report. Replace example/local-network values with your own authorized environment before running anything.

## Evidence

Screenshots extracted from the submitted report are stored under [`evidence/`](evidence/). The report's evidence section is retained in the source material; image-to-step mapping may require visual inspection because the original document does not expose captions for every image.

## Source report

The original submitted report is represented in Markdown under [`docs/report.md`](docs/report.md).
