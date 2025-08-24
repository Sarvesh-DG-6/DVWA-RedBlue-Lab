# DVWA-RedBluePurple-Lab (Low Security) 
This project demonstrates OWASP Top 10 web application vulnerabilities using DVWA as a **attack → detect → document → report workflow** on a lightweight multi-VM lab built in VirtualBox.  
We simulated **Red Team attacks** from Kali Linux, **Blue Team monitoring** on Ubuntu, and documented artifacts as a **Purple Team**.

**Security Level:** Low  

**VMs Used:**
- Kali Linux (Attacker)
- Ubuntu 22.04 LTS (Victim, DVWA host)
- Windows 10 (Optional target via RDP connection)

**Network:** Host-Only subnet 192.168.56.x (for communication between VMs)
             NAT (dynamic, for Internet-access)              

---

## Tools Used
- Kali Linux: Nmap, Nikto, Hydra, Burp Suite, SQLmap
- Ubuntu Linux: Apache2, MySQL, PHP, DVWA, tcpdump
- Optional: Windows 10 services (RDP/SMB), EventViewer

---

## Workflow
1. **Red Team (Attacker)**  
   - SQL Injection (manual + sqlmap)  
   - XSS (Reflected & Stored)  
   - Command Injection  
   - File Upload → Web Shell (RCE)  
   - Brute Force login attacks (Hydra)  
   - CSRF demonstration  
2. **Blue Team (Victim)**  
   - Monitor Apache/MySQL logs:      
     tail -f /var/log/apache2/access.log /var/log/apache2/error.log
     tail -f /var/log/mysql/error.log     
   - Capture network traffic via tcpdump/Wireshark  
3. **Purple Team (Integration)**  
   - Document payloads, logs, screenshots  
   - Summarize impact and mitigation strategies

---

## Execution 
1. Launch three VMs: Kali, Ubuntu, Win10.  
2. Configure Host-Only networking.  
3. Install DVWA on Ubuntu as well as Kali, configure Apache2 & MySQL.  
4. Install attack tools on Kali.  
5. Run attacks sequentially on DVWA Low Security: SQLi → XSS → Command Injection → File Upload → Brute Force → CSRF.  
6. Monitor logs and capture traffic for documentation:
    \n on Ubuntu: Monitored Ubuntu logs, observed attack evidence, captured traffic using tcpdump/Wireshark, analyzed Apache and system logs.
    \n on Windows10: Monitored EventVewer -> Security logs for failed login attempts (Event ID 4625). 
7. Document every attack with screenshots, payloads, logs, PCAPs, and mitigation steps.
 
---

## Key Learning Outcomes:
- Web application penetration testing basics (SQLi, XSS, CSRF, RCE).  
- Log monitoring and traffic capture for security analysis.  
- Red/Blue/Purple Team workflow understanding.
- Can be upgraded further to medium and high security levels.   

---
