# Methodology

## 1. Footprinting & reconnaissance

The report describes six Kali Linux tools used against the authorized `networkwalks.com` domain:

1. WHOIS — domain registration and nameservers
2. WhatWeb — web technology fingerprinting
3. nslookup — domain-to-IP resolution
4. curl `-I` — HTTP response headers
5. wafw00f — WAF identification
6. DNSRecon — DNS record enumeration

The documented findings include WordPress/WP Download Manager identification, an observed IP address, the `/wp-json/` endpoint, ModSecurity (SpiderLabs), and DNS/mail/service records.

## 2. Local network discovery

The report describes using Windows `ipconfig` to identify the local IP/subnet, followed by Zenmap Ping Scan against the author's local LAN. Five live hosts are listed in the report, alongside observed MAC addresses, and a Zenmap topology PDF was generated as part of the practical.

## 3. Risk interpretation

The report categorizes observations as low or medium risk and states that they are not confirmed vulnerabilities. Confirmation would require additional authorized security testing.
