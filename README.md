# Simulated SOC: Vulnerability Discovery to Intrusion Detection

## Demo Video
Watch the full project demo: [Click here](https://1drv.ms/v/c/ca84ccba0e93da2d/IQDWMXo22FkYSLtxkGzn3VOdASKGmw-Def_yVnvyTtVtjJY?e=QbH1Q8)

## Overview
Built a 3-VM SOC lab (Windows victim, Kali attacker, Ubuntu IDS).
Used Nessus Essentials to discover real CVEs in Apache, PHP, MySQL,
and SSL. Wrote custom Snort IDS rules mapped directly to CVE findings.
Simulated 5 attacks from Kali and validated real-time detection.

## Environment
- Windows VM - victim (Apache 2.4.29, PHP 7.2.0, MySQL, OpenSSL via XAMPP)
- Kali VM - attacker (Nessus, nmap, curl, mysql client, hydra)
- Ubuntu VM - SOC monitor (Snort IDS with custom rules)

## CVEs Discovered by Nessus
- Apache 2.4.29 - CVE-2017-15715
- PHP 7.2.0 - CVE-2019-11043, CVE-2020-7069
- MySQL - CVE-2012-2122 (weak authentication)
- OpenSSL - multiple SSL/TLS weaknesses

## Custom Snort Rules Written
5 rules written based directly on Nessus findings:
Apache banner detection, PHP version disclosure,
MySQL weak credential attempt, SSL traffic, SYN scan detection.
Full rules: [snort-rules/local.rules](snort-rules/local.rules)

## Key Results
- Discovered 48 Apache + 44 PHP + 12 OpenSSL vulnerabilities
- All 5 attack simulations successfully detected by Snort
- Demonstrated full workflow: CVE discovery → rule writing → detection

## Tools Used
Nessus Essentials, Snort IDS, Kali Linux, curl, mysql client,
hydra, nmap, XAMPP, Ubuntu, Windows 10, VirtualBox
