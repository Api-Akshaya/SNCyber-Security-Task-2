Nmap Network Scanning & Enumeration – Cybersecurity Task 2

This project demonstrates network scanning and enumeration performed using Nmap on a vulnerable Metasploitable2 machine from a Kali Linux attacker system.
The objective is to identify open ports, running services, service versions, and OS fingerprints to understand the attack surface of the target.

Project Overview

This lab is part of cybersecurity training and focuses on:
Identifying target machine IP
Performing different types of Nmap scans
Enumerating services and versions
Understanding network response behavior
Documenting results for reporting

Environment Setup
Component	Description
Attacker Machine	Kali Linux
Target Machine	Metasploitable2
Network Mode	Host-Only Adapter
Scanning Tool	Nmap

Target IP used: 192.168.56.101

1. Basic Scan

Command:
nmap 192.168.56.101
Purpose:
Identify commonly open ports and active services on the target.
Key Findings:
FTP (21)
SSH (22)
Telnet (23)
SMTP (25)
DNS (53)
HTTP (80)
RPC, SMB, SQL Services, VNC, IRC, etc.

This shows that the target exposes multiple insecure services — ideal for penetration testing practice.

 2. Aggressive Scan (OS + Version Detection)

Command:
sudo nmap -A 192.168.56.101
Purpose:
Extract detailed information:
Service versions
OS fingerprinting
Script scanning
SSL/TLS info
Highlights:
vsftpd 2.3.4 (known vulnerable version)
Apache 2.2.8
OpenSSH 4.7p1
BIND DNS 9.4.2
Linux Kernel 2.6.x detected

3. Full Port Scan (All 65,535 Ports)

Command:
sudo nmap -p- 192.168.56.101
Purpose:
Enumerates the entire attack surface by scanning every port.
Results:
Reinforced findings from basic scan
No additional high ports appeared
Confirms service exposure across known vulnerable ports

Conclusion

This exercise successfully demonstrates:

Fundamental Nmap scanning techniques
Enumeration of open ports and network services
Identification of outdated and vulnerable service versions
Understanding of a real-world attack surface

Such enumeration plays a crucial role in penetration testing, vulnerability assessment, and cybersecurity analysis.
