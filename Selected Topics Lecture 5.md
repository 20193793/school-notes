up: [[Selected Topics]]

# Cyber Kill Chain
> [!DEFINE] Cyber Kill Chain
> Developed to identify and prevent cyber intrusions and consists of 7 steos

When responding to security incident, the objective is to detect and stop the attack as soon as possible in the kill chain progression

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control (CnC)
7. Actions on objectives

## Reconnaissance
Threat actor perform research, gathers intelligence and selects targets
Attacker will choose targets who have been neglected or unprotected

### Techniques
Information query --> Initial information about the target, tools include basic Google search, organizations websites, whois... etc, also might reveal target network address

Ping Sweep --> Determine which IP addresses are active

Port Scan --> Determine which ports or services are available, using tools like SuperScan, Angry IP Scanner and NetScan Tools

Run Vulnerability Scanners --> Determine type and version of operating system and applications, using tools like Nipper, Secuna PSI, Core Impact, Nessus v6, SAINT, and Open VAS

## Weaponization
Uses information from reconnaissance to develop a weapon against the target
It's better to use zero-day attack to avoid detection

## Delivery
Weapon is transmitted to the target using a delivery vector
Additional methods can be used to increase the odds of success of delivery such as:
- Encryption
- Make code look legitimate
- Obfuscating the code

## Exploitation
After delivery, the threat actor breaks vulnerability and gain control of target
The most common exploit targets are applications, OS and users

## Installation
Threat actor establishes a backdoor into the system to allow continued access to the target
Remote access must not alert cybersecurity analysts or users, and must survive antimalware and rebooting

## Command and Control (CnC)
Issue commands to the software the threat was installed on

## Actions on objectives
Final step, threat actor is deeply rooted into the system and hide their movements
Extremely difficult to remove threat at this point