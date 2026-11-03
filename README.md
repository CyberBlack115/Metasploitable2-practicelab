# Metasploitable2-practicelab

Hands-on practice against Metasploitable 2, a Linux VM that is built to be vulnerable. I attack it from Kali, write down what I find, and note how each problem should be fixed.

Part of my [CyberSecurity-Journal](https://github.com/CyberBlack115/CyberSecurity-Journal).

> ⚠️ Metasploitable 2 is deliberately insecure. It only ever runs on a VirtualBox **host-only** network on my own computer. Never bridged, never on the internet.

## Lab setup

| | |
|---|---|
| Attacker | Kali Linux (VirtualBox) |
| Target | Metasploitable 2 at 192.168.56.101 |
| Network | VirtualBox host-only (192.168.56.0/24) |

## Write-ups

| # | Topic | Status |
|---|---|---|
| 01 | [Network scanning with Nmap](01-network-scanning.md) | ✅ Done |
| 02 | vsftpd 2.3.4 backdoor (port 21) | 🔜 Planned |
| 03 | Bindshell on port 1524 | 🔜 Planned |
| 04 | Telnet and the r-services (23, 512–514) | 🔜 Planned |
| 05 | Samba (139 / 445) | 🔜 Planned |
| 06 | UnrealIRCd (6667) | 🔜 Planned |
| 07 | Tomcat manager (8180) | 🔜 Planned |

## How each write-up is laid out
Goal → command → output → what it means → how to fix it → questions I should be able to answer.

## 📸 Screenshots
Screenshots live in [`images/`](images). Each write-up has a box that says *Screenshot goes here* with the file name to use.
