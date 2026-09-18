# Commands & Procedures

The original report identifies the following command-line activities. Exact command syntax for several tools was not included in the parsed report, so this file intentionally does **not** invent commands that were not documented.

## Footprinting

- `whois` — obtain publicly available registration information.
- `whatweb` — fingerprint web technologies.
- `nslookup` — resolve the authorized domain to an IP address.
- `curl -I` — inspect HTTP response headers.
- `wafw00f` — identify whether a WAF is present.
- `dnsrecon` — enumerate DNS records.

## Local network discovery

- Windows `ipconfig` — identify local IP configuration and subnet.
- Zenmap — enter the authorized local subnet and use **Ping Scan** to discover live hosts.
- Zenmap **Topology** — inspect the topology and save the generated topology evidence.

> Only run these procedures against assets you own or have explicit authorization to test.
