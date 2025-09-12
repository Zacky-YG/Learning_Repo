# Frameworks
- Understanding different type of cyber security frameworks
## Pyramid of Pain
- Hash Values
  - Gain insight via hashes
  - Identify signatures to attribute payloads and artefacts to an actor.
-- IP Address
  - Fast Faux: A group of networks constantly changing their network details, making it diffcult to track and identify source.
  References:
  - https://www.akamai.com/blog/security/digging-deeper-an-in-depth-analysis-of-a-fast-flux-network
  - https://unit42.paloaltonetworks.com/fast-flux-101/
--- Domain Names
  - Name mapped to IP addresses for identification.
---- Host Artifacts
----- Network Artifacts
  - Attack using user-agent string, C2 info, or URI patterns followed by HTTP POST requests.
------ Tools
  - E.g. exe, dll, payloads etc.
  - Fuzzy Hasing / Context Triggered Piecewise Hashes
------ Tactics, Techniques & Procedures (TTPs)
  - phishing attempts to persistence and data exfiltration.

# Cyber Key Chain
## Open-Source Intelligence (OSINT)
  - An attacker studies the victim's information before proceeding with an attack plan.
## Weaponization
  - macro, payloads etc.
## Delivery
  - Method of transmitting payload.
## Exploitation
  - Using resources such as emails and phishing links to obtain victim data.
## Installation
  - Creating a backdoor after a successful attempt in accessing victim's system.
  - Timestomping: used to avoid detection by modifying create/access/change times.
## Command & Control (C2)
  - C&C or C2 Beaconing is a type of mailicious communication to establish a channel for control over victim's system.
  - DNS Tunneling: victim system makes constant DNS request to the DNS server to maintain full control.
## Actions on Objectives (Exfiltration)
  - Attacker performs their desired actions on a system such as collecting credentials or sensitive data.
### Extra Info
  - https://unifiedkillchain.com/
  - https://attack.mitre.org/

# Unified Kill Chain
  - Understand behaviors and methodlogiesof a cyber threat to establish strong cybersecurity def/posture.
## What is "Kill Chain"
  - Methodlogy/path attackers use to approach and intrude a target.
## What is "Threat Modelling"
  - Series of steps to improve system security.
## What is "Unified Kill Chain"
  - 18 Attack Phases
  - Created 2017, updated 2022.
  - meant to complement other defence framework.
  - Refer to "Paul Pols' Unified Kill Chain.png" for details on all 18 attack phases.
## Phase: In (Initial Foothold)
  - Refer to "THM - Initial Foothold.png" for chart.
  1. Reconnaissance: Gather Info on target.
  2. Weaponization: Setup infrastructure for attack.
  3. Social Engineering: Used to manipulate victims into performing certain actions to aid attack.
  4. Exploitation: Takes advantage of vulnerabilities.
  5. Persistence: Maintain backdoor.
  6. Defence Evasion: Understand blue team techniques and evade.
  7. Command & Control: Execute what had been planned during Weaponization phase.
  8. Pivoting: Reach other systems within a network through most vulnerable point.
## Phase: Through (Network Propagation)
  - Refer to "THM - Through.png" for chart.
  1. Pivoting: Staging site and tunnel between a victim's network. A distribution point for backdoor.
  2. Discovery: Uncover victim's network and other information such as active user accounts.
  3. Privilege Escalation: Attempt to gain more information via privleged access.
  4. Execution: Deploy malicious code using the pivot system as their host such as remote trojans, C2 scripts or schedule tasks to maintain persistence.
  5. Credential Access: Steals credentials to use it as a mask for more attacks.
  6. Lateral Movement: Move to another victim's system once done with current system.
## Phase: Out (Action on Objectives)
  1. Collection: Gather all valuable data of interest.
  2. Exfiltration: Attempts stealing valuable data via Command & Control (C2) channel and tunnel deployed in the earlier phases.
  3. Impact: As data lose its integrity, attacker will manipulate assets to cause business distruption. For example ransomware, denial of service (DoS) attacks.
  4. Objectives: With power and access to the system and network, attacker can choose to perform other goals which may include releasing confidential data to the public.

# Diamond Model
  - 4 Core Features
      - Adversary
      - Infrastructure
      - Capability
      - Victim
  - 2 Addon Features
      - Social,
      - Political and Technology
## Adversary
- aka attacker
## Victim
- Victim Personae: The target.
## Infrastructure
- Type 1: Controlled by adversary
- Type 2: Intermediary, infrastructure may not be aware it is a used for mailicious actions. (e.g. compromised email accounts)
## Event Meta Features (6 possible features)
1. Timestamp
2. Phase
3. Result
4. Direction
5. Methodology: Descrribe general classification of intrusion.
6. Resources: external resources used for attack to succeed.
  - Software
  - Knowledge
  - Information
  - Hardware
  - Funds
  - Facilities
## Social-Political Component
- The intent and needs of the adversary

# MITRE
```
    ATT&CK ®  ( A dversarial  T actics,  T echniques,  and   C ommon  K nowledge) Framework
    CAR ( C yber  A nalytics  R epository) Knowledge Base
    ENGAGE  (sorry, not a fancy acronym)
    D3FEND ( D etection,  D enial, and  D isruption  F ramework  E mpowering  N etwork  D efense)
    AEP ( A TT&CK  E mulation  P lans)
```
## Basic Terminology
- Advanced Persistent Threat (APT): A team/group who engages in long-term attack against organizations and/or countries.
- Tactics, Techniques, and Procedures (TTP)
  - Tactic: adversary's goal
  - Technique: how adversary achieve goals
  - Procedure: how the techniques are executed.
- Tools available: https://attack.mitre.org/resources/attack-data-and-tools/
## Cyber Analytics Repository (CAR)
- Knowlege base of analytics by MITRE.
- Used as a supplement for ATT&CK framework which is more in-depth in terms of analytics.
- Event Query Language (EQL): Used to query, parse, and organize Sysmon even data.
  - Refernce: https://eql.readthedocs.io/en/latest/
- Bro/Zeek ATT&CK-based Analytics and Reporting (BZAR): Used to detect ATT&CK-based adversarial activity; A collection of Zeek (Bro) scripts looking primarily at SMB and RPC traffic.
## MITRE Engage
- A <b>framework</b> for planning and discussing adversary engagment operations.
- An adversarary Engagment Approach done via...
  - Cyber Denial: Prevent adversary's ability to conduct their operations.
  - Cyber Deception: Plant artifacts to mislead the adversary.
- Engage has 5 categories in its matrix.
- ![Engage Matrix Image goes here](https://raw.githubusercontent.com/Zacky-YG/Learning_Repo/refs/heads/main/Tryhackme/SOC_Lvl1/THM%20-%20engage-matrix.png)
  - Prepare: Set of desired input.
  - Expose: Expose Adversaries when they trigger the deployed deception activities.
  - Affect: Cause negative impact to adversaries.
  - Elicit: Obtain information about adversary by observing and learn more about their TTP.
  - Understand: Output the outcomes of the operational actions (input)
    - Refernce: https://engage.mitre.org/wp-content/uploads/2022/04/EngageHandbook-v1.0.pdf
## Detection, Denial, and Disruption Framework Empowering Network Defense (D3FEND)
- Knowledge graph of cybersecurity countermeasures
- Still in beta.
## Center of Threat-Informed Defense (CTID)
- Formed by MITRE
- Conducts research on cyber threats and their TTPs
### ATT&CK Emulations Plans
- free public library making adversary emulation plans for blue and red teams.



