# Week 2 — Footprinting & Network Scanning

Cybersecurity coursework project (Networkwalks Academy — Cyber IT Diploma) covering passive/active reconnaissance and network scanning techniques, performed against an authorized target (`networkwalks.com`) and my own local network.

## ⚠️ Disclaimer

All activity in this repo was performed only against systems I own or have explicit permission to test. This content is for educational purposes only. Do not use any of these techniques against systems you do not own or have written authorization to test — unauthorized access is illegal in most jurisdictions, regardless of intent or outcome.

## Report

The full write-up (with screenshots for each step) is in this repo as a Word document — see `My_Week2_Report.docx`.

## Modules

| Module | Description |
|---|---|
| W2-PM1 | Footprinting with multiple Kali tools (`whois`, `nslookup`, `dnsrecon`, `whatweb`, `wafw00f`, `curl`) |
| W2-PM3 | Maltego footprinting — domain entity, transforms, Footprint L1 Machine |
| W2-PM5 | Zenmap network scanning — local subnet discovery |

## Target Scope

- **External target:** `networkwalks.com` (course-provided target, permission secured)
- **Internal target:** own local LAN (`10.0.0.0/24`)

## Key Findings Summary

**PM1 — Footprinting (`networkwalks.com`)**
- WordPress 7.0.4 on Apache, hosted via HostGator, domain registered through GoDaddy
- Protected by ModSecurity (SpiderLabs) WAF
- WHOIS registrant shielded via privacy proxy (Domains By Proxy)
- MX/SPF records point to standard HostGator/cPanel email setup

**PM3 — Maltego Footprinting (`networkwalks.com`)**
- Mail server confirmed: `mail.networkwalks.com`
- Footprint L1 Machine surfaced a cluster of cPanel/WHM-related subdomains: `www`, `webdisk`, `autodiscover`, `webmail`, `cpanel`
- Confirms the HostGator/cPanel hosting setup independently identified in PM1

**PM5 — Network Scanning (own LAN, `10.0.0.0/24`)**
- 2 live hosts found: `10.0.0.1` (gateway) and `10.0.0.2` (own machine)
- `10.0.0.1` exposes ports 135 (msrpc) and 445 (microsoft-ds)
- `10.0.0.2` shows no open ports (fresh Kali install, no services enabled)

## Tools Used

`whois` · `nslookup` · `dnsrecon` · `whatweb` · `wafw00f` · `curl` · Maltego · Zenmap (Nmap)

## Author

Salwa — [github.com/salwaibrahim00](https://github.com/salwaibrahim00/week2-task)
