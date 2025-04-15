<h1> 🕵️‍♀️ Network Vulnerability & Packet Analysis - Nmap & Wireshark </h1>

 

<h2>Description</h2>
Conducted network vulnerability scanning and deep packet inspection using Nmap and Wireshark on a controlled lab environment. The project focused on identifying active hosts, open ports, and service-level vulnerabilities, as well as capturing and analyzing network anomalies from a packet capture file. Demonstrated foundational skills in reconnaissance, traffic analysis, and identifying insecure protocols.
<br />


<h2>Utilities Used</h2>

- <b>Nmap – Network discovery and vulnerability scanning </b> 
- <b>Wireshark – Packet capture and deep protocol analysis </b>

<h2>Environments Used </h2>

- <b>Kali Linux VM – Host for running Nmap & Wireshark</b>
- <b>Windows 10 VM – Target machine for scanning</b>

<h2>Project Documentation & Walkthrough:</h2>




<p align="center">
Launch your Virtual Machine of choice, Ill be going with Kali. I'll also use Zenmap, since it comes with a GUI which makes it easier for this demonstration.
To do this lab, you will need a target to scan, make sure you have the target's permission.<br/>
<img src="https://i.imgur.com/TNEKTBG.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To do a proper scan, you need to insert commands and flags into the 'command' section of Zenmap, this functions as your command prompt.
  The command I used was nmap -sV -T4 - O -F, which means:
  -sV → Service Version Detection =
  Detects versions of the services running on open ports.
  -T4 → Aggressive Timing Template = 
  Speeds up the scan by reducing wait times between probes; good balance of speed and accuracy for local or fast networks.
  -O → OS Detection = 
  Attempts to determine the operating system of the target based on TCP/IP stack behavior.
  -F → Fast Scan = 
  Scans only the top 100 most common ports (instead of all 65,535), making the scan quicker.
<br/>
<img src="https://i.imgur.com/k6o9vAl.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
These scans can tell us a lot of information, such as which ports are open, what type of operating system the target is using,
  and the topology of our target's network. In this case, it's a star topology. <br/>
<img src="https://i.imgur.com/WGt6uA0.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From our scans, we have found a few vulnerabilities. First vulnerability seen after doing the scan is the operating system used, which is Windows 7. Windows 7 reached end of life a very long time ago, meaning it does not receive any patches or security updates, making it weak and vulnerable. On the CVE database, CVE-2024-23594 is listed as a medium severity vulnerability. This vulnerability allows “a privileged attacker with local access to execute arbitrary code”. 
This would allow an attacker full access into the system, meaning they can
bypass any security mechanisms in place and escalate privileges and even implant backdoors to allow
access to the system even after a reboot in completed. The target is also running widows server 2008, which also reached End of Life a while back, making it susceptible to attacks. Using the CVE
database we can see that CVE-2019-0543 is a strong vulnerability. CVE-2019-0543 can be used to
elevation privileges, which would allow an attacker to grant themselves more permissions that can bypass
security implication, allowing themselves access to sensitive information in the system
<br/>
<img src="https://i.imgur.com/cwNEDp0.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now onto Wireshark, where we can analyze network traffic to catch anomalies. I will be running a pcap file that I had saved   <br/>
<img src="https://i.imgur.com/7Vxcuiu.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the scan, we can see a lot of FTP traffic, which is insecure. We can see the data in clear text. Instead, opt into using FTPS or SFTP instead of FTP. <br/>
<img src="https://i.imgur.com/FV1QZIa.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right below the FTP traffic, we can also see HTTP traffic, which is again, insecure. 
  HTTP runs on port 80, instead, you should be using port 443 which is HTTPS because it encrypts the data using SSL/TLS.  <br/>
<img src="https://i.imgur.com/Fg4sOZ5.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
  
<h2> ✅ Conclusion</h2>
This lab demonstrated the practical use of Nmap for network reconnaissance and vulnerability enumeration, paired with Wireshark for in-depth packet analysis. By scanning a target system and inspecting captured traffic, I was able to identify open ports, running services, potential vulnerabilities, and network anomalies. The project reinforced core skills in network mapping, protocol analysis, and the importance of securing services exposed to the network. This hands-on experience served as a foundational exercise in both offensive and defensive cybersecurity techniques.
<br />



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
