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

