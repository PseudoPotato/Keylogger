Videos link: https://drive.google.com/drive/folders/1qCVHomjLmavzRba9uP7g3w_7qDYEmS5_?usp=sharing

This project explores the implementation of a Keylogger using two distinct approaches: leveraging Metasploit on Kali Linux and scripting in Python. The Metasploit method capitalizes on an established penetration testing framework to covertly capture keystrokes within a controlled environment, demonstrating the potential risks in cybersecurity scenarios. In contrast, the Python-based implementation focuses on customizability and simplicity, providing a hands-on understanding of keylogging techniques through code. Both methods highlight the ethical considerations and security implications of keylogging, with an emphasis on responsible usage in educational and testing contexts only. This project aims to increase awareness of cybersecurity vulnerabilities and emphasize the importance of robust security measures.

Keylogger using Metasploit (Kali Linux):

Kali Linux: ipconfig
The first step is to run the ipconfig command in Kali Linux. This command displays the IP configuration of the network interfaces on Kali, which is necessary to confirm the system's IP address. By knowing the IP, we ensure that Kali is set up correctly to connect to other devices on the same network.
![image](https://github.com/user-attachments/assets/24da589a-4f44-4ef5-bd10-5d91237abf1a)

Kali Linux: Network Scan with nmap
We use nmap -sV 10.2.0.4 to scan the Windows XP machine. This command reveals open ports and services running on the target, which helps identify potential vulnerabilities that Kali can exploit to gain access.

Windows XP: ipconfig
Next, we run ipconfig on the Windows XP machine to verify its IP address. Comparing this with Kali’s IP allows us to confirm that both systems are on the same network and can communicate with each other, which is essential for the following steps.
 
![image](https://github.com/user-attachments/assets/acf0c5bb-13d1-4661-90ff-fb5cbbbae09c)


Kali Linux: Start msfconsole for Metasploit
Starting msfconsole opens the Metasploit framework, a powerful tool for penetration testing. Metasploit allows us to exploit vulnerabilities on the Windows XP system, which we’ll use to initiate access.
 ![image](https://github.com/user-attachments/assets/59a30919-6bde-44e5-9149-ecd58402ae53)
 ![image](https://github.com/user-attachments/assets/04beff90-98d2-484d-a1c3-658ca2c23621)


 
Metasploit: Select an Exploit
Using use 0 selects a specific exploit module for the vulnerability found in Windows XP. This module will be used to target the system directly, creating a pathway for access.
Metasploit: Set Target IP with RHOSTS
The command set RHOSTS 10.2.0.4 sets the IP of the Windows XP system as the target, allowing Metasploit to focus on the correct machine during exploitation.
Metasploit: Run the Exploit
With run, we execute the exploit to attempt access on the target machine. If successful, this provides a session on the Windows XP system, granting initial control over it
![image](https://github.com/user-attachments/assets/1974583b-8341-4dca-8b3f-7af7c972b74a)

 
Metasploit: List Processes with ps
Running ps lists the processes currently active on Windows XP. This helps identify a stable process, such as explorer.exe, which we can migrate to for more reliable access.
Metasploit: Migrate to explorer.exe Process
The command migrate 252 switches control to the explorer.exe process, which is stable and runs with user privileges. This migration helps maintain a persistent session without interruption.
Metasploit: Check User ID with getuid
We use getuid to check the user ID currently in use. This verifies our current level of access on the Windows XP system and confirms if we are operating as the correct user.
Metasploit: Attempt to Gain System Privileges
The command getsystem is used to elevate our privileges to system-level access, giving us more control over Windows XP. System privileges provide the highest level of authority on the target.
Metasploit: Confirm User ID Again
Running getuid again allows us to verify if the privilege escalation was successful by checking if our user ID has changed to a system-level account.
 
Metasploit: Display Available Commands with help
Typing help displays a list of available commands in Metasploit, helping us to locate commands related to keylogging and other functions we may want to perform on the target.
![image](https://github.com/user-attachments/assets/03311bcf-3a68-4f33-b0be-ce1a7a036616)
![image](https://github.com/user-attachments/assets/9b900ab7-0f08-47b4-b82e-d64f9da130b6)

Metasploit: Start Keylogger with keyscan_start
With keyscan_start, we activate a keylogger on Windows XP. This command begins recording keystrokes, allowing us to capture any input made on the target’s keyboard.
 ![image](https://github.com/user-attachments/assets/ed8cbdc9-afe9-4bfd-8fac-15f294552d2d)

Windows XP: Perform Keystrokes
At this point, we switch to Windows XP and type some text. These keystrokes are recorded by the keylogger running through Metasploit on the Kali Linux system.
 ![image](https://github.com/user-attachments/assets/2e7ca3f3-b06f-4d12-90e9-2b609ecaa148)

Kali Linux: Retrieve Keystrokes with keyscan_dump
The command keyscan_dump displays the captured keystrokes from Windows XP. This allows us to view all recorded input, showing what was typed on the target system.
Metasploit: Stop Keylogger with keyscan_stop
Finally, keyscan_stop halts the keylogging process. This command stops the recording of keystrokes and concludes our keylogging session on the Windows XP machine.

