# Introduction
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
  - 
