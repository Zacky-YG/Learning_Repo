# Table of Contents
- [Section 1: Introduction](#sec-1-introduction)
- [Section 2: Cyber Kill Chain](#sec-2-cyber-kill-chain)
- [Section 3: MITRE ATT&CK Framework](#sec-3-MITRE-ATT&CK-Framework)
- [Section 4: Phishing Email Analysis](#sec-4-Phishing-Email-Analysis)
- [Section 5: Detecting Web Attacks](#sec-5-Detecting-Web-Attacks)

# Sec 1 Introduction
## Types of SOC Models
- In-house
- Virtual
- Co-Managed
- Command
## Types of SOC Roles
- SOC Analyst: L1-3. Classify Alerts -> Identify cause -> Advise on remediation
- Incident Responder: Performs initial assessment of security breaches.
- Threat Hunter: Proactively seeks out and investigates potential threats and vulnerabilities within an org network/system by using techniques to...
    - Detect
    - Isolate
    - Mitigate
    - Evade
      ...Threats.
- Security Engineer: Maintain security infrastructure of SIEM solutions and SOC products.
- SOC Manager: Manage crews instead of the technical issues.
## Log Management
- Access to all logs in an environment
## Endpoint Detection and Response (EDR)
- Endpoint security solution that continuous monitor and collect endpoint data and rule-based automated response and analysis capabilities.
- Common EDR solutions: CarbonBlack, SentinelOne, and FireEye HX.
- Steps:
  1. Analysis endpoint details.
  2. Investigate endpoint information for malicious activities.
  3. Isolate endpoint for further investigation via containment.
  4. Identify any Indicator of Compromise (IoC): evidence indicating a security breach or malicious activity on endpoint/network.
## Security Orchestration Automation and Response (SOAR)
- Security products and tools in an environment working together.
- Common SOAR tools: Splunk Phantom, IBM Resilient, Logsign, Demisto.
- Saves time by automating common workflows: hash query, IP address reputation control etc.
- It is centralised solution.
## Threat Intelligence Feed
- Info on malware provided by 3rd-party.
  - Common sites: [Virtu](https://www.virustotal.com/) | [Talos Intelligence](https://talosintelligence.com/)
## Common Mistake made by SOC Analysts
- Over-reliance on VirtusTotal Results
- Hasty Analysis of Malware in a Sandbox
- Inadequate Log Analysis
- Overlooking VirusTotal Dates
## Questions
- What are the different steps of the lifecycle for the NIST, of an incident?
  - Preparation, Detection/Analysis, Containment / Eradication and Recovery, Post-Event Activity

# Sec 2: Cyber Kill Chain
- Framework by Lockheed Martin (Organization)
- Used to understand each phase and actions taken by adversary.
## Steps
1. Reconnaissance
   - 2 techniques
     - Passive: Collect info without engaging the target system. (e.g. Web archives)
     - Active: Collect info by engaging with target system directly. (e.g. submitting a request to web server to get a response.)
2. Weaponization
   - Use info from recon to create tools for attack.
3. Delivery
   - Executes the attack via techniques/tools.
4. Exploitation
   - Ensure tool/technique used is implemented smoothly in the target system.
5. Installation
    - Main persistence via techniques.
6. Command & Control (C2)
   - Adversary set-up C2 server to deliver commands to the target system.
7. Actions on Objectives
   - Through C2 server, perform multiple actions for their goals.

## Sec 3: MITRE ATT&CK Framework
- ATT&CK stands for Adversarial Tactics, Techniques, and Common Knowledge
- A knowledge database.
- Consist of 3 Matrices
  1. Enterprise: Understand cyber attacks on large org.
     - 7 Sub-matrices
       - PRE
       - Windows
       - macOS
       - Linux
       - Cloud
       - Network
       - Containers
  2. Mobile: mobile devices, generally contains less info.
     - 2 Sub-matrices
       - Android
       - iOS
  4. Industrial Control Systems (ICS): cyber security of devices in the industrial control systems.
## Mitigations
- Measures and actions that can be taken in response to techniques.

# Sec 4: Phishing Email Analysis
- Falls under delivery
- Attackers can perform spoofing to trick users.
- Prevent spoofing protocols (Not mandatory)
  - SPF: aka Sender Policy Framework
  - DKIM: DomainKeys Identified Mail (DKIM)
  - DMARC:
- Ways to determine if mail is spoof
  - Check SMTP address with domain's SPF, DKIM, DMARC, and MX records (records can be extracted using Mxtoolbox).
- Reading Email Header
  - Definition: header contains info about sender, recipient, and date. It also contains other components such as 'Return-Path'.
  - Notable components
    - From
    - To
    - Date
    - Subject:
    - Return-Path: aka Reply-To. Upon replying, it will send to the address indicated in this field.
    - Domain Key and DKIM Signatures: email signatures for authentication.
    - Message-ID: Unique Email ID
    - MIME-Version: aka Multipurpose Internet Mail Extensions; a coding standard. non-text contents converts into text and sent via SMTP (Simple Mail Transfer Protocol).
    - Received: A list of email servers which passed through before arriving recipient's inbox.
    - X-Spam Status: Spam score of email message.

# Sec 5: Detecting Web Attacks
## Types of attacks
- SQL Injection
- Cross Site Scripting
- Command Injection
- IDOR
- RFI & LFI
- File Upload (Web Shell)
## Open Worldwide Application Security Project (OWASP)
- Non-profit foundation dedicated to improving software security
- Every few years, OWASP publish top 10 web application vulnerabilities that pose the most critical security risk.
  - aka OWASP Top 10.
  - Useful resources in OWASP: https://owasp.org/projects/
## How Web Applications
- HTTP is used for web apps to communicate.
- Below is how HTTP protocol works
- ![HTTP Protocol Image goes here](https://raw.githubusercontent.com/Zacky-YG/Learning_Repo/refs/heads/main/Tryhackme/SOC%-%HTTP-Protocol-TCP-IP-Model-OSI-Model.png)
- HTTP Status Line Summary
  - 100-199: Informational responses
  - 200-299: Successful responses
  - 300-399: Redirection messages
  - 400-499: Client error responses
  - 500-599: Server error responses
## Detecting SQL Injection Attacks
- An attack vector in which web application directly includes unsanitized user provided data in SQL queries; a vulnerability which SQL injection attack make use.
- Types of SQL Injections
  - Classic/In-band: SQL query sent and respond to on the same channel.
  - Blind/Inferential: SQL queries receive a response which cannot be seen.
  - Out of Band: SQL queries received through another channel.
 ## Detecting Cross Site Scripting (XSS) Attacks
 - XSS attacks is where malicious code are executed via legitimate applications.
 - 3 types of XSS
   - Reflected XSS (Non-persistent): XSS payload must be present in the request; Most common type of XSS.
   - Stored XSS (Persistent): XSS payload is permanently uploaded in the web app; Most dangerous type of XSS.
   - DOM based XSS: XSS payload is executed upon modification in the DOM "environment" in the victim's browser; it runs the client-side code in an "unexpected" manner. (OWASP)
## Detecting Command Injection Attacks
- Occurs when data received from user is not sanitized and passed directly to the OS shell.
### How to Detect Command Injection Attacks
- Examine the whole web request.
- Look out for terminal language keywords (e.g. dir, ls, cp, mv cat etc.)
- Identify commonly used command injection payloads.
### How to Prevent Command Injection
- Sanitize data received from user.
- Limit user privileges
- Use virtualization tech such as dockers.
## Detecting Insecure Direct Object Reference (IDOR) Attacks
- Insecure Direct Object Reference (IDOR) or Broken Access Control is a vulnerability caused by absence/improper use of an authorization mechanism.
### How to Detect IDOR Attacks
- Check all parameters.
- Look at number of requests for the same page.
- Identify a pattern.
### How to Prevent IDOR
- Limit privilege access to specific users.
- Website should limit the amount of parameters allowed.


