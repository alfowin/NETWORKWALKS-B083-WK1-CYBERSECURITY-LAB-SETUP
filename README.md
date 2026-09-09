Cybersecurity Lab Environment Setup
Project Overview
Objectives
Purpose of the Lab
Lab Architecture
Lab Configuration
Lab Setup Procedure
Step 1. Install 7 Zip
Step 2. Install VirtualBox
Step 3. Create the NAT Network
Step 4. Import Kali Linux Network
Step 5. Configure the Kali Linux Network
Step 6. Create a clean VM Snapshot
Lab Verification
Examples: Result
Problem Encountered and solution
Problem 1. Internet Connectivity after static IP Configuration
Problem 2. VirtualBox VT-x/ Virtual Error
What i learned 
1. NAT vs NAT Network
2. Virtual Machine Networking
3. Static IP Configuration
4. VM Snapshots
5. Documentation
Security and Ethical use

                                                                                                           

CYBERSECURITY LAB ENVIRONMENT SETUP
Building an isolated virtual lab for penetration testing and ethical hacking

Skill: Cybersecurity Ver Virtualbox v7.2
    Kali Linux v2026.2 Skill Linux
  Network 10.0.0.0/24 Penetration Testing
Skill Virtualization GitHub Kali Linux
   #Networkwalks  #Ethical Haching
         Alfred Owino

OBJECTIVES
The main objectives of this project are to:

Install and configure VirtualBox.
Install/import Kali Linux as a virtual machine.
Create a private NAT Network for the cybersecurity lab.
Configure network connectivity for Kali Linux.
Assign a consistent IP address to the Kali VM.
Verify network connectivity and DNS resolution.
Take a clean VM snapshot for recovery.
Document the complete setup process.
Prepare the environment for future cybersecurity projects.

PURPOSE OF THE LAB
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Exploitation practice
Security-tool experimentation

NB This laboratory must only be used for systems that one own or one has been permitted to test

LAB CONFIGURATION
Component              Configuration

Host OS                Windows 10
Host RAM               8 GB
Processor              Intel Core i7
Hypervisor             VirtualBox 7.2
Security OS            Kali Linux 2026.2
Kali RAM               2048 MB
Virtual Network        NAT Network
Network Address        10.0.0.0/24
Kali IP Address        10.0.0.2/24
Default Gateway        10.0.0.1
DNS Server             8.8.8.8
Future VM Range        10.0.0.3–10.0.0.99

Step 1. Install 7-Zip

​7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive.
​Tool: 7-Zip

​Step 2. Install VirtualBox
​VirtualBox was installed as the hypervisor.

​Step 3. Create the NAT Network
​A dedicated NAT Network was created in VirtualBox.
​Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled
​A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.
​This will allow future attacker and target VMs to communicate within the lab.

​Step 4. Import Kali Linux
​The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.
​The VM network adapter was configured as follows:
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT

The MV allocated:
RAM 2048 MB
A shared folder was also configured for transferring required files between the host operating system and the kali VM

Step 5. Configure the Kali Linux Network
​The Kali Linux network configuration was checked and configured with a consistent IPv4 address.
​Example configuration:
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8


Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

 Lab Verification
 
 TEST                             COMMAND                               EXPECTED RESULT
 Check IP address	                ip a                                 	Correct Kali IP displayed
 
 Test gateway                     ping 10.0.0.1                         Successful replies
 
 Test Internet connectivity     	ping 8.8.8.8	                        Successful replies
 
 Test DNS resolution              nslookup networkwalks.com	            Domain resolves
 
 Verify Nmap	                    nmap --version	                      Nmap version displayed
 
 Verify snapshot	                Restore snapshot and run ip a	        Baseline configuration restored

 
Example Results
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8 

Problems Encountered & Solutions

Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.
The network connection was then restarted/rebooted and connectivity was tested again.

Problem 2. VirtualBox VT-x / Virtualization Error
The VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

The issue was resolved by:

Restarting the computer.
Entering BIOS/UEFI settings.
Enabling Intel VT-x / hardware virtualization.
Saving the configuration.
Restarting the computer.
Starting the Kali VM again.
After enabling virtualization, the VM started successfully.

What I Learned
Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

I. NAT vs NAT Network
A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

II. Virtual Machine Networking
I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

III. Static IP Configuration
I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

IV. VM Snapshots
I learned that a clean snapshot should be created before performing risky or experimental activities.

This provides a known-good recovery point for future cybersecurity exercises.

V. Documentation
I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

 Security & Ethical Use
This laboratory is intended strictly for education purposes only.

Tools & Resources
7-Zip: https://7-zip.org/download.html

VirtualBox https://virtualbox.org/wiki/Downloads

Kali Linux:: https://kali.org/get-kali

Linkedin: www.linkedin.com/in/alfred-owino-a4a34021b



