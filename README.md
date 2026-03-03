# Windows-Detection-Lab
Simulation and Detecting Brute force attack
Lab Phase 1: Environment Preparation
I disabled the Windows Firewall This is important so the firewall doesn't block my work and I can see the traffic clearly
I opened Kali Linux and used the command nmap -sV -p 445,3389 [Target_IP]. I did this to check which ports are open like SMB (445) and RDP (3389)
I used Hydra tool to try many passwords. I want to see how these failed attempts look in the system logs
Before I start, I enabled the Audit Policy in Windows. Then I checked the results in two ways
Way 1: Windows Event Viewer
I went to Security Logs and searched for Event ID 4625. This ID means someone tried to login but failed
Inside the details, I found Logon Type 3, which means the attack came from the network (my Kali machine)
Way 2: Using Sysmon
I installed Sysmon using PowerShell. It gives more details in the "Applications and Services" logs
I looked for:
Event ID 1: To see which process or program was opened
Event ID 3: To see the network connection details
Event IDs 12, 13, 14: To check if there is any change in the Windows Registry.
My Goal: This is my first lab session alone. I'm trying to learn how the attack traffic looks like and how to find it
![Brute Force Evidence](final%20result.png)
