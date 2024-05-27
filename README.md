<h1>Ansible Automation</h1>

<h2>Description</h2>
The Ansible project is a network-wide ad blocker that i did set up on a computer, like a Raspberry Pi, to filter and block unwanted advertisements and malicious websites for all devices connected to my virtual environment.
It acts as a sinkhole which intercepts DNS requests from devices and blocks requests to known ad-serving domains preventing ads from being loaded.
<br />

<h2>Skills Obtained</h2>

- <b>DNS & IP Addressing Understanding:</b> Knowledge the role of DNS servers, DNS resolution process and IP role in networking.
- <b>System Administration:</b>  Installing and configuring software on a server, likely on a Linux-based system.
- <b>Command-Line Proficiency:</b> Enhanced ability to use the command line for system management tasks.
- <b>Ad Blocking:</b> The methods used to block advertisements and unwanted domains at the network level.
- <b>Malware and Phishing Prevention:</b> Preventing access to malicious sites and improve overall network security.
- <b>Diagnosing Network Issues:</b> Identifying and resolving issues related to DNS and general network connectivity.
- <b>Data Analysis:</b> Analyze logs to identify patterns, blocked domains, and potential security threats. Reading and interpreting system and network logs to troubleshoot problems.
- <b>System Optimization:</b> Optimizing system performance by identifying and resolving bottlenecks or misconfigurations.
- <b>End-User Training:</b> Ability to explain how the Pi-Hole works and its benefits to non-technical users.
- <b>Planning and Execution:</b> Skills in planning and executing a technical project from start to finish.

<h2>Utilities Used</h2>

- <b>Ubuntu Terminal</b> 
- <b>Pi-Hole</b>

<h2>Environments Used </h2>

- <b>Windows 11 VM</b> (the device to monitor)
- <b>Ubuntu 22.14 VM</b> 

<h2>Project walk-through:</h2>

<p align="center">
Step 1: Updating repositories and libraries <br/>
<img src="https://i.imgur.com/RIA2Tmj.png" height="80%" width="80% alt="Pi-Hole steps"/>
<br />
<br />
Step 2: Changing the IP address to Static  <br/>
<img src="https://i.imgur.com/K0Ikpv0.png" height="80%" width="80%" alt="Pi-Hole steps"/>
<br />
<br />
Step 3: sudo nano /etc/netplan/00-installer-config.yaml <br/>
<img src="https://i.imgur.com/JCSj5aZ.png" height="80%" width="80%" alt="Pi-Hole steps"/>
<br />
<br />
Step 4: sudo netplan apply (This will give us many warnings as we’re making our IP static)  <br/>
<img src="https://i.imgur.com/dqJlWrI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
As per below image, the IP has been changed and it is now static  <br/>
<img src="https://i.imgur.com/AOi74kF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 5: Manually download the installer and run  <br/>
<img src="https://i.imgur.com/EqxBoEv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/1XupHvO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/eyUnELp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/V3W9neV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/74s0yY2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 7: After successful installation, the admin password will be provided: (to use for web interface)  <br/>
<img src="https://i.imgur.com/WkbCH4S.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
