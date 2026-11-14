# Week 2 Penetration Testing Report

## Reconnaissance, Footprinting & Network Host Discovery

## Overview

This repository contains the documentation and evidence collected during **Week 2** of the **Networkwalks Cybersecurity Internship Program (Batch B084)**. The project focused on **Reconnaissance and Network Scanning**, introducing the process of gathering publicly available information about the target, **networkwalks.com**, and perform network discovery using a personally controlled virtual LAN.

**Liability Disclaimer:**  All assessment activities documented in this report were conducted within authorised environments, including personally owned systems and systems for which written authorisation was provided. The information presented is intended solely for educational, research, and professional development purposes. Readers must ensure that any security testing is performed only with proper authorisation from the system owner. Individuals who engage in unauthorised access, scanning, or testing activities may be subject to criminal charges, financial fines, and other legal consequences. Compliance with all applicable laws, regulations, and ethical standards remains the sole responsibility of the reader.

---

# Target Information

| Item | Detail |
| --- | --- |
|Pentester Name| Garcia Forrest|
|Date| 13 November 2026|
|Modules Completed|W2-PM1 - Multiple Kali Tools & W2-PM5 - Zenmap Scanning |
| Target | networkwalks.com (authorised permission granted) and a personally controlled virtualized Local Area Network (LAN) used for host discovery and network scanning exercises |
|Permission Secured| Yes|
|Phasese Covered| Phase 1: Reconnaissance & Footprinting and Phase 2: Scanning & Network Discovery|

---
# Summary

This Week 2 exercise examined public information about networkwalks.com and, separately, performed basic host discovery in a personally controlled virtualized network. Evidence includes Kali Linux tool outputs, a Windows 10 ipconfig capture, Zenmap screenshots, and a topology export.
The external investigation collected domain registration, DNS, web technology, HTTP response, and WAF fingerprints. The Zenmap scan identified four responsive IP addresses in the 10.0.0.0/24 subnet. The activity did not include application exploitation, credential testing, full service/port enumeration, or independent validation of vulnerabilities.

---

# Methodology & Evidence Collected

## W2-PM1-Multiple Kali Tools: Target Reconnaissance (networkwalks.com)

Using Kali Linux, the following reconnaissance activities were performed against **networkwalks.com**:

### WHOIS

Used to gather public registration information associated with a domain, including registrar details and registration records.

<img width="1273" height="792" alt="whois-results" src="https://github.com/user-attachments/assets/8520ad99-8dcd-4fca-a126-fb36212d1db2" />

### NSLookup

Queried DNS records associated with **networkwalks.com**.

<img width="1277" height="798" alt="nslookup-results" src="https://github.com/user-attachments/assets/02992b59-a002-4a49-9a05-17077147badd" />

### DNSRecon

Performed DNS enumeration to identify available DNS-related information.

<img width="1270" height="796" alt="dnsrecon-results" src="https://github.com/user-attachments/assets/4be9bacd-9e96-4a95-89ee-a18c4e50ee74" />

### WhatWeb

Identified technologies, frameworks, and web server characteristics associated with **networkwalks.com**.

<img width="1277" height="792" alt="whatweb-results" src="https://github.com/user-attachments/assets/6ea51a42-ccda-4b7f-8674-bb4827fc48be" />

### cURL -l

Retrieved HTTP response information and examined web headers.

<img width="1278" height="798" alt="curl-results" src="https://github.com/user-attachments/assets/2fe6b141-548f-4b00-8082-8d6a5a482fbf" />

### WAFW00F

Used to detect the presence of Web Application Firewalls (WAFs) protecting web applications.

<img width="1272" height="792" alt="wafw00f-results" src="https://github.com/user-attachments/assets/1dd1bab8-aed0-4716-9daa-a4ce3d18ae9a" />

---

# W2-PM5-Zenmap Scanning: Network Discovery Activities

Separate from the reconnaissance activities against **networkwalks.com**, a Windows 10 virtual machine was used within the lab environment to perform network enumeration and host discovery exercises.

### Windows Command Prompt Utilities

The Windows Command Prompt was used to identify:

- Local IPv4 Address
- Subnet Information
- Default Gateway
- Physical (MAC) Address

Command executed:

``` ipconfig /all```

<img width="1033" height="734" alt="windows-cmd-results" src="https://github.com/user-attachments/assets/dd9610b5-449f-4c89-83f4-6287313fe8a1" />

---

## Network Scanning with Zenmap
Zenmap, the graphical interface for Nmap, was installed and used to perform a Ping Scan to identify active hosts on the network.

<img width="1032" height="725" alt="zenmap-installation" src="https://github.com/user-attachments/assets/c777501a-9050-42f6-86ff-b3b43d765d53" />

### Ping Scan

```nmap -sn 10.0.0.10/24``` 
Purpose:
- Identify active hosts
- Verify network connectivity
- Prepare for future enumeration activities

<img width="1022" height="734" alt="zenmap-Ping-scan-results" src="https://github.com/user-attachments/assets/1d6581fc-88a7-4b28-9442-62c20a32642f" />


#### Zenmap Legend and Topology
<img width="1027" height="728" alt="zenmap-legend-and-topology" src="https://github.com/user-attachments/assets/1a8ab438-73de-4c3a-ab83-974ab211a6b7" />

---

# Findings Summary

**Domain registration and DNS:**  The WHOIS record lists GoDaddy.com, LLC as registrar and ns6135.hostgator.com / ns6136.hostgator.com as name servers. WHOIS reports “DNSSEC: unsigned”. DNSRecon and NSLookup show an A-address of 192.232.216.135; DNSRecon also displayed MX, SPF TXT and SRV records. These are point-in-time records, not proof of DNS hosting design or mail-system security.
**Website technology footprint:**  WhatWeb identified Apache, WordPress 7.1.4, WordPress Download Manager 3.3.76, Bootstrap 7.1.4, and jQuery 3.7.1. These version strings are externally reported fingerprints; direct verification and patch-state assessment were not performed.
**HTTP metadata:**  The captured curl -I https://networkwalks.com response returned HTTP/1.1 200 OK. The sample includes Referrer-Policy: no-referrer-when-downgrade and a __wpdm_client cookie marked Secure and HttpOnly.
**WAF detection:**  WAFW00F identified ModSecurity (SpiderLabs) and reported two requests. This confirms a tool detection result, not the effectiveness, configuration, or coverage of the protection.

---

# Key Lessons Learned

### 1\. Reconnaissance Is Critical

Passive reconnaissance enables security professionals to gather valuable intelligence before any active interaction occurs with a target environment.

### 2\. Different Tools Provide Different Perspectives

No single tool provides a complete picture. Combining multiple reconnaissance techniques produces a more comprehensive assessment.

### 3\. Network Discovery Is Foundational

Understanding host availability and network structure is a prerequisite for further security analysis.

### 4\. Ethics Matter

Security assessments should only be conducted with proper authorisation and within approved environments.

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

