# Table of Contents
- [Section 1: Introduction](#sec-1-introduction)
- [Section 2: Cyber Kill Chain](#sec-2-cyber-kill-chain)

# Sec 1 Introduction
## Types of SOC Models
- In-house
- Virtual
- Co-Managed
- Command
## Types of SOC Roles
- SOC Analyst: L1-3. Classify Alerts -> Identify cause -> Advise on remediation
- Incident Responder: Performs initial assessment of security breaches.
- Threat Hunter: Proactly seeks out and investigates potential threats and vulnerabilities within an org network/system by using techniques to...
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
- Endpoint security solution that continous monitor and collect endpoint data and rule-based automated response and analysis capabilities.
- Common EDR solutions: CarbonBlack, SentinelOne, and FireEye HX.
- Steps:
  1. Analysis endpoint details.
  2. Investigate endpoint information for mailicious activities.
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
  - Preparation, Detection/Analysis, Containment / Eradicationand Recovery, Post-Event Activity

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

## Sec 3: MITRE ATT&CK
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
- 



