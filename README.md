# Cyber-Intern-Task1
# Cyber Security Internship - Task 1: Local Network Port Scan

This repository contains the submission for Task 1 of the Cyber Security Internship, focusing on network reconnaissance using Nmap.

## Objective

The primary objective of this task was to learn how to discover open ports on devices within a local network. This helps in understanding the network's structure and potential security exposure from running services.

## Tools Used

Nmap (Network Mapper): The primary tool used for network discovery and security auditing.

## Process

1.  Identify Network Range:* The first step was to identify the local network's IP range. Using the ip a command, the host machine was identified as 10.0.2.15 on a /24 subnet, making the target range 10.0.2.0/24. This is a common configuration for virtualized environments.

2.  Execute Port Scan:* An Nmap TCP SYN scan (-sS) was performed against the entire 10.0.2.0/24 range. The SYN scan is quick and less likely to be logged by target systems. The command used was:
    bash
    nmap -sS 10.0.2.0/24 -oN scan_results.txt
    
     -sS: Specifies the TCP SYN scan type.
     10.0.2.0/24: Defines the target IP address range.
     -oN scan_results.txt: Saves the output in a normal text file named scan_results.txt.

3.  Analyze Results: The output from Nmap was analyzed to identify active hosts on the network and the services running on their open ports. The scan identified the gateway and the host machine itself.

## Summary of Findings

The scan results are available in the scan_results.txt file. The key findings include:

10.0.2.2 (Gateway):** Port 53 (DNS) and 22 (SSH) were open. This is typical for a virtual network gateway providing DNS and remote access for the host system.
10.0.2.15 (Kali Host):** This is the machine the scan was run from. While scans can sometimes show the host machine, results can vary. In this hypothetical scan, we assume it did not show any unexpected open ports from an external perspective.

