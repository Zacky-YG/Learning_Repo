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
  




