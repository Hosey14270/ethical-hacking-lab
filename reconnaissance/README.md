# Reconnaissance Phase

## Target Information

- Target IP: 192.168.112.130
- Attacker IP: 192.168.112.129
- Network: 192.168.112.0/24
- Target System: Metasploitable 2

---

## Host Discovery

Command used:

nmap -sn 192.168.112.130

Result:
- Host is up
- Responding to ICMP
- Network distance: 1 hop

---

## Service Enumeration

Command used:

nmap -sS -sV -O 192.168.112.130

Open ports identified:
- 21 (FTP - vsftpd 2.3.4)
- 22 (SSH)
- 23 (Telnet)
- 25 (SMTP)
- 53 (DNS)
- 80 (HTTP - Apache 2.2.8)
- 139 / 445 (Samba)
- 1524 (Bindshell)
- 3306 (MySQL)
- 5432 (PostgreSQL)
- 5900 (VNC)
- 6667 (IRC)
- 8180 (Tomcat)

---

## Initial Observations

- Multiple outdated services
- Large attack surface
- High likelihood of remote code execution vulnerabilities
- Legacy Linux kernel (2.6.x)
- nmap --script=http-enum -p 80 192.168.112.130
