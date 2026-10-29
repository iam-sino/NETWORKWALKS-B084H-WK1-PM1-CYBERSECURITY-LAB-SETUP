# NETWORKWALKS-B084H-WK1-PM1-CYBERSECURITY-LAB-SETUP
Organized a Cybersecurity home lab.

## Project Overview

A virtual lab was created using Oracle VirtualBox and Kali Linux to simulate cybersecurity practices and penetration testing.

This lab has been created so that there is a designated space to learn and perform security related tasks such as network scanning, information gathering, vulnerability analysis and using different cybersecurity tools. Using a virtual lab allows us to practice these techniques in a safe environment.

The lab is set up on a private virtual network meaning the virtual machines can interact with each other. This can be extended in the future by adding more virtual machines to allow authorised penetration testing, security analysis and cybersecurity practices to take place.

## Project Objectives

During this project I will be achieving the following objectives;

1. Set up a virtualisation platform using Oracle VirtualBox.
2. Install and configure Kali Linux inside VirtualBox.
3. Create a specific NAT Network for use across my machines in my lab.
4. Configure the network settings on Kali Linux.
5. Assign a static IP address to the Kali Linux virtual machine to make it easier to identify on the network.
6. Verify the network connection and ensure that Domain Name Resolution is working.
7. Take a snapshot of the virtual machine to allow me to revert back to a stable point.
8. Document the installation, configuration and testing processes.
9. Provide a base to allow me to complete further Cybersecurity learning and authorised penetration testing activities.

## Lab Objective

This lab will create a safe and secure environment to gain practical experience with a range of security tools.
This will allow you to practice using a variety of security techniques like:

1. Network Discovery. Allows you to determine what devices and systems are available over a network.
2. Port Scanning. This determines what ports are available over a network.
3. Vulnerability Analysis. Determine what vulnerabilities exist on a system.
4. Packet Capture. This allows you to capture and analyse packets.
5. Web Application Testing. To identify common security issues with web applications.
6. Penetration Testing. Practice using penetration testing techniques.
7. Security Tools. Gain an understanding of security tools.

You should only perform any testing in the lab or on systems that you have been given permission to.


## Lab Configuration


## Lab Setup Procedure

## Step 1. Creation of the NAT Network, WHY?

Reason is because, the VirtualBox and Kali Linux have already been installed and configured on my computer, I proceeded directly to the next stage of the project, which involved creating an additional NAT Network.

Initially, the setup process was supposed to begin with the installation of 7-Zip, which is used to extract the Kali Linux virtual machine package. The second step was to install Oracle VirtualBox, which serves as the hypervisor for running virtual machines.

However, because both applications were already installed on my computer, I skipped these preliminary steps and proceeded to create a new NAT Network in VirtualBox. I already had an existing network named *Lab Network* for personal use, so I created a separate NAT Network specifically for this project.

The new NAT Network was configured with the following settings:

- Network Name: NAT Network
- IPv4 Prefix: 10.0.0.0/24
- DHCP: Enabled
- IPv6: Disabled

The NAT Network option has been chosen as it allows the virtual machines connected to the network to talk to each other and external networks.

This will allow new virtual machines to be added in the future. One can be used for security testing and one as the target in the lab.


![Screenshot 1](./Screenshot%201.png)




## Step 2. The network adapter of the Kali Linux virtual machine was configured.

Since Kali Linux had already been installed and imported into VirtualBox, initially I was supposed to download Kali Linux virtual machine from the official Kali Linux website and imported into VirtualBox, I proceeded directly to its network adapter settings and configured Adapter 1 as follows:

- Attached to: NAT Network
- Network Name: NatNetwork
- Adapter Type: Intel PRO/1000 MT Desktop
- Promiscuous Mode: Allow All
- Virtual Cable Connected: Enabled

![Screenshot 2](./Screenshot.png)
