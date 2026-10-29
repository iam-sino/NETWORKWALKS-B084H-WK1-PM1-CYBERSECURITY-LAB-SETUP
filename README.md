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


  
  Host OS:           	Windows 11
  
  Host RAM:    	      16 GB
  
  Processor:         	Intel Core i5
  
  Security OS:	        Kali Linux 2026.3
  
  Virtual Network:	    NAT Network
  
  Network Address:   	10.0.0.0/24
  
  Kali IP Address:   	10.0.0.2/24
  
  Default Gateway:   	10.0.0.1
  
  DNS Server:	        10.0.0.1
  


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

![Screenshot 2](Screenshot%202.png)


## Step 3. Configure the Kali Linux Network

After connecting Kali Linux to the NAT Network, I proceeded to configure its IPv4 network settings by assigning a consistent IP address and specifying the appropriate subnet mask, default gateway, and DNS server.

The configuration details are as follows:

- IP Address: 10.0.0.2
- Subnet Mask (Netmask): 255.255.255.0 (/24)
- Default Gateway: 10.0.0.1
- DNS Server: 10.0.0.1

**Note:** The subnet mask `255.255.255.0` is equivalent to the CIDR prefix `/24`. Both represent the same network prefix length.

![Screenshot 3](Screenshot%203.png)

![Screenshot 4](Screenshot%204.png)


## Step 4. Internet Connection Confirmation

After completing the network configuration and establishing the connection, I tested the internet connectivity of the Kali Linux virtual machine to confirm that it could access external networks. The connection was successful. I also executed a ping command to `google.com` in the Kali Linux terminal to verify network communication and DNS resolution. The test was successful, confirming that the virtual machine could resolve the domain name and communicate with the external network.

![Screenshot 5](Screenshot%205.png)

![Screenshot 6](Screenshot%206.png)


## Step 5. Creation of a Clean VM Snapshot

After completing the initial configuration, I created a new snapshot of the Kali Linux virtual machine specifically for this project. Although an existing snapshot was already available for my other projects, I decided to create a separate one to maintain a clear distinction between the different laboratory environments.

The snapshot serves as a baseline recovery point, preserving the virtual machine's state at the time it was created. If future cybersecurity exercises result in unwanted changes or configuration issues, the virtual machine can be restored to this saved state, provided the snapshot remains available.

![Screenshot 7](Screenshot%207.png)


## Problems Encountered & Solutions
### -Internet Connectivity After Static IP Configuration
Following the manual configuration of the IPv4 settings, an internet connectivity issue occurred in the Kali Linux virtual machine.

### Solution

I restored the virtual machine to its previously created snapshot and changed the DNS server address from `8.8.8.8` to `10.0.0.1`. After applying this change, the connectivity issue was resolved, and the virtual machine was able to access the internet successfully.


## What I Learned

This project provided practical experience in setting up and managing a virtual environment for cybersecurity training. It also improved my understanding of virtual networking, IP configuration, system recovery, and technical documentation.

The key lessons gained from the project are outlined below.

### 1. Difference Between NAT and NAT Network

I learned that NAT and NAT Network operate differently in VirtualBox. While a standard NAT configuration generally provides network access for an individual virtual machine, a NAT Network allows multiple connected virtual machines to communicate with one another while also supporting external network access.

This makes NAT Network suitable for developing a laboratory with multiple virtual machines for cybersecurity practice.

### 2. Virtual Machine Network Configuration

I gained a better understanding of how VirtualBox network adapters connect virtual machines to virtual networks. I also learned that selecting and configuring the appropriate network settings is essential for establishing communication and internet access.

### 3. Static IPv4 Address Configuration

I learned how to configure IPv4 network settings in Kali Linux, including the IP address, subnet mask, default gateway, and DNS server. I also gained practical experience in troubleshooting connectivity issues that may arise from incorrect network settings.

### 4. Virtual Machine Snapshots and Recovery

I learned the importance of creating snapshots to preserve a known working state of a virtual machine. A suitable baseline snapshot provides a recovery point that can be used to restore the machine if future experiments cause configuration problems. Creating a snapshot before potentially disruptive activities is therefore an important practice.

### 5. Technical Documentation

I learned that proper documentation is an essential part of a cybersecurity project. Recording configuration settings, commands, screenshots, challenges, and solutions makes the process easier to understand, reproduce, and troubleshoot in the future.
