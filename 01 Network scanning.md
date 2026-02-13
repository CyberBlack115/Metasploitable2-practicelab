# Metasploitable 2 - Network Scanning Report

**Date:** 2026-02-13
**Target IP:** 192.168.56.101
**Tool Used:** Nmap (Network Mapper)

## 1. Objective
To perform network discovery and identify open ports and services running on the Metasploitable 2 target machine.

## 2. Methodology
I performed a service version detection scan using Nmap to identify open ports and the specific software versions running on them.

**Command Run:**
```bash
nmap -sV 192.168.56.101
```
## 3. Findings
The scan identified the following open ports and services:

**Scan Output:**
```
Nmap scan report for 192.168.56.101
Host is up (0.0019s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.3.4
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp   open  telnet      Linux telnetd
25/tcp   open  smtp        Postfix smtpd
53/tcp   open  domain      ISC BIND 9.4.2
80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp  open  rpcbind     2 (RPC #100000)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
512/tcp  open  exec        netkit-rsh rexecd
513/tcp  open  login
514/tcp  open  shell       Netkit rshd
1099/tcp open  java-rmi    GNU Classpath grmiregistry
1524/tcp open  bindshell   Metasploitable root shell
2049/tcp open  nfs         2-4 (RPC #100003)
2121/tcp open  ftp         ProFTPD 1.3.1
3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
5900/tcp open  vnc         VNC (protocol 3.3)
6000/tcp open  X11         (access denied)
6667/tcp open  irc         UnrealIRCd
8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)
8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1
MAC Address: 08:00:27:04:FE:15 (PCS Systemtechnik/Oracle VirtualBox virtual NIC)
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```

## 4. Analysis
Based on the scan results, I identified several potentially critical vulnerabilities:
​Port 21 (FTP): Running vsftpd 2.3.4. This version is known to have a backdoor vulnerability.
​Port 23 (Telnet): Running Linux telnetd. Telnet transmits data in cleartext, which is insecure.
​Port 1524 (Bindshell): A root shell is listening on this port, allowing unauthorized access.
​Port 3306 (MySQL): Database service is open to the network.


## 5. Conclusion
The target machine has multiple high risk services exposed. The next step will be to verify these vulnerabilities using exploit tools.
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.18 seconds
