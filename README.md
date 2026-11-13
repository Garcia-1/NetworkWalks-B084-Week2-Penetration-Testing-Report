# Week 2 Penetration Testing Report

## Networkwalks Cybersecurity Internship Program (Batch B084)

### Overview

This repository contains the documentation and evidence collected during **Week 2** of the **Networkwalks Cybersecurity Internship Program (Batch B084)**. The project focused on **Reconnaissance and Network Scanning**, introducing the process of gathering publicly available information about the target, **networkwalks.com**, and perform network discovery within a controlled lab environment.

**Disclaimer:** All activities documented in this report were performed in an authorized educational environment. Reconnaissance activities against **networkwalks.com** were limited to publicly available information and conducted for training purposes as part of the internship program.


---

# Target Information

| Item | Detail |
| --- | --- |
|Pentester Name| Garcia Forrest|
|Date| 13 November 2026|
|Modules Completed|W2-PM1 - Multiple Kali Tools & W2-PM5 - Zenmap Scanning |
| Target | networkwalks.com (authorised permission granted) and a personally controlled virtualized Local Area Network (LAN) used for host discovery and network scanning exercises |
|Permission Secured| Yes|
| Assessment Type | Passive Reconnaissance |
| Scope | Publicly Available Information Gathering |
| Assessment Environment | Authorized Training Lab |
|Phasese Covered| Phase 1: Reconnaissance & Footprinting and Phase 2: Scanning & Network Discovery|

---

# Objectives

The objectives of this project were to:

- Gather publicly available information about **networkwalks.com**.
- Identify DNS and domain\-related information.
- Enumerate web technologies used by the target website.
- Detect potential security controls protecting web assets.
- Perform host discovery and network scanning in a virtual lab environment.
- Document findings in a professional penetration testing report.

---

# Methodology

## Phase 1: Target Reconnaissance (networkwalks.com)

Using Kali Linux, the following reconnaissance activities were performed against **networkwalks.com**:

### WHOIS

Collected publicly available domain registration information.

### NSLookup

Queried DNS records associated with **networkwalks.com**.

### DNSRecon

Performed DNS enumeration to identify available DNS\-related information.

### WhatWeb

Identified technologies, frameworks, and web server characteristics associated with **networkwalks.com**.

### cURL

Retrieved HTTP response information and examined web headers.

### WAFW00F

Checked for the presence of web application firewalls protecting the website.


---

# Phase 2: Network Discovery Activities

Separate from the reconnaissance activities against **networkwalks.com**, a Windows 10 virtual machine was used within the lab environment to perform network enumeration and host discovery exercises.

### Windows Command Prompt

The following information was identified:

- IPv4 Address
- MAC Address
- Default Gateway
- Network Adapter Information

Commands executed:

``` ipconfig /all```

### Zenmap Scan

A Ping Scan was conducted against the lab network using Zenmap to identify live hosts and verify connectivity within the virtualized environment.

---

# Tools Utilized

## Reconnaissance Tools (Kali Linux)

### WHOIS

Used to gather public registration information associated with a domain, including registrar details and registration records.

### WhatWeb

Used to identify web technologies, frameworks, servers, and applications running on a target website.

### NSLookup

Used to query DNS records and verify hostname\-to\-IP address mappings.

### cURL

Used to retrieve web content, inspect HTTP headers, and interact with web services from the command line.

### WAFW00F

Used to detect the presence of Web Application Firewalls (WAFs) protecting web applications.

### DNSRecon

Used to perform DNS enumeration and gather detailed DNS\-related information.

---

## Network Scanning Tool

### Zenmap

Zenmap, the graphical interface for Nmap, was used to perform a Ping Scan to identify active hosts on the network.

---

## Windows Command Prompt Utilities

The Windows Command Prompt was used to identify:

- Local IPv4 Address
- Subnet Information
- Default Gateway
- Physical (MAC) Address

### Commands Executed

``` ipconfig /all ```

---

# Tasks Performed

## Footprinting and Reconnaissance

Information gathering activities were performed using multiple Kali Linux utilities to collect publicly available information about the target.

Activities included:

1. Domain registration research
2. DNS enumeration
3. Technology stack identification
4. Web server analysis
5. Firewall detection
6. HTTP header inspection

---

## Local Network Enumeration

The Windows 10 virtual machine was analyzed to determine:

- Assigned IP address
- MAC address
- Network adapter details
- Gateway configuration

Evidence was captured using Command Prompt outputs.

---

## Network Scanning with Zenmap

Zenmap was used to perform host discovery through a Ping Scan.

### Sample Scan Type

nmap \-sn <target\-network>Purpose:

- Identify active hosts
- Verify network connectivity
- Prepare for future enumeration activities

---

# Findings Summary

| Category | Information Collected |
| --- | --- |
| Domain Information | WHOIS records |
| DNS Information | DNS records and hostname information |
| Web Technologies | Server and application details |
| Security Controls | Potential WAF detection |
| HTTP Data | Response headers and web content |
| Local Host Information | IP address and MAC address |
| Network Hosts | Live systems discovered through Ping Scan |

---

# Evidence

## Screenshots Included

### Reconnaissance Evidence

- WHOIS results
- WhatWeb output
- DNSRecon output
- NSLookup results
- cURL responses
- WAFW00F detection results

### Windows Enumeration Evidence

- ``` ipconfig /all ```

### Network Scanning Evidence

- Zenmap Ping Scan results
- Host discovery results

---

# Key Lessons Learned

### 1\. Reconnaissance Is Critical

Passive reconnaissance enables security professionals to gather valuable intelligence before any active interaction occurs with a target environment.

### 2\. Different Tools Provide Different Perspectives

No single tool provides a complete picture. Combining multiple reconnaissance techniques produces a more comprehensive assessment.

### 3\. Network Discovery Is Foundational

Understanding host availability and network structure is a prerequisite for further security analysis.

### 4\. Ethics Matter

Security assessments should only be conducted with proper authorization and within approved environments.

---

# Challenges Encountered

- Understanding the different purposes of reconnaissance tools.
- Interpreting DNS and WHOIS outputs.
- Correlating information gathered across multiple tools.
- Learning how network scanning complements reconnaissance activities.

---

# Conclusion

This project provided hands-on experience with reconnaissance and network scanning methodologies commonly used during the early phases of a penetration test. Through the use of Kali Linux reconnaissance tools, Windows networking utilities, and Zenmap, I gained practical knowledge in information gathering, network discovery, and professional security documentation.

---

# Acknowledgements

Thanks to **Waqas Karim (CCIE)** and the **Networkwalks Team** for their guidance, structured learning materials, and support throughout the internship program.

---

## Author

**Garcia Forrest**

Cybersecurity Student (CC) B084

LinkedIn: www.linkedin.com/in/garcia-forrest

