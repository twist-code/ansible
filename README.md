<h1>Ansible Automation</h1>

<h2>Description</h2>
ANSIBLE is a software tool that provides simple but powerful automation for cross-platform computer support. It is primarily intended for IT professionals, who use it for application deployment, updates on workstations and servers, configuration management, and nearly anything a systems administrator does on a weekly or daily basis. Ansible doesn't depend on agent software and has no additional security infrastructure, so it's easy to deploy. <br />

<h2>How Ansible works</h2>
In Ansible, there are two categories of computers: the control node and managed nodes. The control node is a computer that runs Ansible. There must be at least one control node, although a backup control node may also exist. A managed node is any device being managed by the control node. <br />
Ansible works by connecting to nodes (clients, servers, or whatever you're configuring) on a network, and then sending a small program called an Ansible module to that node. Ansible executes these modules over SSH and removes them when finished. The only requirement for this interaction is that your Ansible control node has login access to the managed nodes. SSH keys are the most common way to provide access, but other forms of authentication are also supported.
<br />

<img src="https://i.imgur.com/RFjT3Rq.png" height="80%" width="80%" alt="Ansible"/>

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

- <b>Ubuntu Virtual machines</b>
- <b>Kali Linux</b> 
- <b>Ansible</b>
- <b>SSH Keys</b> (security based)

<h2>Environments Used </h2>

- <b>Virtual Box home lab</b>

<h2>Project walk-through:</h2>

<p align="center">
<b>Example1:</b> We were able to log into Ubuntu server via SSH. <br />To execute a simple command “sudo reboot”. Which was able to reboot the VM.
<img src="https://i.imgur.com/Ills94V.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/AG7Lzh5.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<b>Example2:</b> We were able to run an ansible playbook on the localhost. By executing shutdown.yml
<img src="https://i.imgur.com/AJ6fg6F.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/UNoVaeT.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<br />
Step 1: To set up SSH, we need to create a key first  <br/>
<img src="https://i.imgur.com/ayFrhav.png" height="80%" width="80% alt="Ansible steps"/>
<br />
By adopting the Ed25519 algorithm for SSH key generation, we can enjoy enhanced security, faster key generation, and reduced overhead. <br /> Its strong cryptographic properties make it an excellent choice for any scenario where secure remote access is paramount.
<img src="https://i.imgur.com/Fwa9Ple.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/9SuTdgK.png" height="80%" width="80% alt="Ansible steps"/>
 <br />
After that, we copy the key file to the client server.
<img src="https://i.imgur.com/OxTGXoS.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/uOPKtDL.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/W4WUOuy.png" height="80%" width="80% alt="Ansible steps"/>
 <br />
  <br />
The reason to leave passphrase empty for ansible key is to make it simpler by letting ansible through without having to write the passphrase all the time. We will only need to enter the passphrase ONCE.
<img src="https://i.imgur.com/U0BBRdA.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/lFpx4Gv.png" height="80%" width="80% alt="Ansible steps"/>
 <br />
 <br />
Step 2: GIT REPOSITORY ON THE SERVER
<img src="https://i.imgur.com/NTymvfU.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/9uUVq0g.png" height="80%" width="80% alt="Ansible steps"/>
 <br /><br />
Step 3: CREATE AN INVENTORY
<img src="https://i.imgur.com/s4p2XG1.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/PHg8DSQ.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/DkrQATJ.png" height="80%" width="80% alt="Ansible steps"/>
  <br />
Step 4: PINGING THE INVENTORY
<img src="https://i.imgur.com/pUlRaFd.png" height="80%" width="80% alt="Ansible steps"/>  <br /> 
   <br />
Ansible was able to connect to each of the servers and establish a connection. (inventory)  <br />
PING is actually connecting the SSH, making a real connection.
<br />
This below error will be received when SSH is not installed in the client server:
<img src="https://i.imgur.com/fxOLXIR.png" height="80%" width="80% alt="Ansible steps"/>
<br />
Step 5: SETTING DEFAULTS FOR ANSIBLE SCRIPTS <br />
The reason it works is because we declared the path to the key file, and also the file name of the inventory as well.
<img src="https://i.imgur.com/WQ1yHiH.png" height="80%" width="80% alt="Ansible steps"/>  <br /> 
<img src="https://i.imgur.com/2PhIPMI.png" height="80%" width="80% alt="Ansible steps"/>
<br />
 <br />
Step 6: GATHERING FACTS <br />
This module is automatically called by playbooks to gather useful variables about remote hosts that can be used in playbooks. Ansible provides many facts about the system, automatically.
<img src="https://i.imgur.com/E4RPTef.png" height="80%" width="80% alt="Ansible steps"/>  <br /> 
In case you want to limit this command to one HOST. <br /> 
Command: <b>ansible all -m gather_facts –limit  [server_ip]</b> <br /> 
It gives all the information about this targeted host.  
<br />
 <br />
RUNNING ANSIBLE COMMANDS THAT MAKES CHANGES ON HOSTS <br/>
<img src="https://i.imgur.com/MY1y6df.png" height="80%" width="80% alt="Ansible steps"/> 
<img src="https://i.imgur.com/EFHvO02.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<br />
Step 7: INSTALLING A TEXT EDITOR TO OUR INVENTORY (Example)  <br/>
<img src="https://i.imgur.com/X0PbptU.png" height="80%" width="80% alt="Ansible steps"/> <br /> 
The changes made can also be seen on the remote host, in the var/log/apt/history.log file. <br /> 
<img src="https://i.imgur.com/rfukXeA.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<br />
<b>What happens when you implement a change that’s already been made:</b>  <br/>
<img src="https://i.imgur.com/6i35DSa.png" height="80%" width="80% alt="Ansible steps"/><br/>
 <b> /var/log/apt/history.log </b> <br/>
 <img src="https://i.imgur.com/200qmuG.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<br />
Step 8: WRITING A PLAYBOOK  <br/>
<img src="https://i.imgur.com/DaYQBGI.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/NQsW95L.png" height="80%" width="80% alt="Ansible steps"/><br/>
 <b> /var/log/apt/history.log shows this: </b> <br/>
 <img src="https://i.imgur.com/ylS1b8f.png" height="80%" width="80% alt="Ansible steps"/>
<br />
<br />
Step 8: WRITING A PLAYBOOK TO INSTALL ZABBIX AGENT  <br/>
<img src="https://i.imgur.com/lGk7bXy.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/9WlhyXU.png" height="80%" width="80% alt="Ansible steps"/>
<img src="https://i.imgur.com/leYhiQS.png" height="80%" width="80% alt="Ansible steps"/>

<br />

 <h1 align="center">THANK YOU</h1>
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
