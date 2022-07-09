# HomeLab-Setup
HomeLab Setup with a Firewall, SIEM Solution, Exploitable machines and an Attacker.

# What is a Homelab?
A Homelab is an environment meant to simulate enterprise components and configuration. The goal here is to understand the process of installing, configuring, maintaining and updating this entire infrastructure. We are building a virtualized Homelab as it is beginner friendly and easier to configure and spin up.

# Tools
- Attacker - Parrot Security OS
- Firewall - pfSense
- IDS - SecurityOnion
- SIEM - Splunk
- Hypervisor - VMWare/Virtualbox
- Domain Controller - Windows Active Directory
- Vulnerable Machines - Ubuntu, Windows, DVWA

# Network Design
![Network Design & Topology](/img/HomeLab.jpg)

# Guide
## Selecting and Downloading a Hypervisor
We will need a Hypervisor to install all of our tools and services.

I'll be using VMWare Workstation, being a student I get a license for it for free. Although VirtualBox is also a great free alternative as a Hypervisor. 

You can download VMWare Workstation at -

[VMWare Workstation Download](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html)

You can download VirtualBox at - 

[Virtualbox Download](https://www.virtualbox.org/wiki/Downloads)

## Installing and Configuring the Firewall - pfsense
pfsense will act as the edge of our Homelab virtual network and will be only accessible from the Parrot Machine. 

pfsense community edition can be downloaded from - [pfsense community edition ISO](https://www.pfsense.org/download/)

You can follow these steps to install & configure pfsense -
1. Open VMWare Workstation & Create a new Virtual Machine with the "Typical (recommended)" setting. 
   
2. Browse the pfsense CE ISO file and select Next. 
   (You might need to extract the ISO file from your pfsense download as it is usually zipped.)
   ![pfsense New VM](./img/pfsense/pfsense_1.png)

3. Change your VM name to "pfsense" & click Next.
   
4. Leave the disk size to 20GB and ensure split virtual disk into multiple files option is selected.
    ![pfsense Disk Size](./img/pfsense/pfsense_2.png)

5. Click on customize hardware and increase the memory limit to 1GB.

6. Add 5 Network Adapters and correspond them with a VMnet interface as per the image by selecting Custom specific Virtual Network. 
    ![pfsense Network Adapters](./img/pfsense/pfsense_3.png)

7. Select Finish. The pfsense machine will power on and you can accept all the default values, after that pfsense will reboot.

8.
