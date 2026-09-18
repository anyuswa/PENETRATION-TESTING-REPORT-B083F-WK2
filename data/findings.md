# Findings

## Footprinting observations

| # | Finding | Evidence / observation | Risk level |
|---|---|---|---|
| 1 | Web technology information exposed | WordPress and WP Download Manager identified by WhatWeb | Medium |
| 2 | Server IP address identifiable | nslookup returned `192.232.216.135` | Low |
| 3 | HTTP technical information exposed | HTTP headers and `/wp-json/` observed with curl | Low |
| 4 | WAF technology identifiable | ModSecurity (SpiderLabs) identified by wafw00f | Low |
| 5 | DNS infrastructure information exposed | DNS, mail and service-related records identified | Medium |
| 6 | Multiple live hosts visible on local network | Report lists five live hosts | Medium |

## Important limitation

The source report states that these are observations from information gathering and host discovery, **not confirmed vulnerabilities**. No exploitation or vulnerability validation was performed as part of these modules.

## Local network hosts recorded in source report

- `192.168.8.1`
- `192.168.8.58`
- `192.168.8.105`
- `192.168.8.119`
- `192.168.8.121`

MAC addresses recorded in the source report:

- `E2:98:5A:26:B3:2E`
- `3A:AF:D4:0B:FE:F4`
- `DA:91:44:73:AF:01`
- `6A:4F:87:0A:90:70`
- `D0-AB-D5-AA-F3-CA` (local MAC)
