# Malware

> [!DEFINE] Malware
> A malicious software that damages or disables computer systems giving limited or full control of the system for the purpose of theft or fraud

Examples of malware:
- Trojan Horse
- Backdoor
- Rootkit
- Ransomware
- Adware
- Virus
- Worms
- Spyware
- Botnet
- Crypter

Ways malware can get into a system:
- Instant message app
- Portable/removable devices
- Browser and email bugs
- Insecure patch management
- Rogue/decoy apps
- Untrusted sites
- Downloading from internet
- Email attachments
- Network propagation
- File sharing services
- Installation by other malware
- Bluetooth and wireless networks

techniques to distribute malware
- Blackhat SEO --> Ranking malware pages highly in search results
- Social Engineered click-jacking --> Tricking users into clicking on innocent-looking webpages
- Spearphishing sites --> Mimick legitimate websites
- Malvertising --> Embedding malware into ads 
- Compromised legitimate websites --> Hosting malware to unsuspecting visitors
- Drive-by downloads --> Exploiting flaws in browser to install malware just by visiting web page
- Spam emails --> Attaching malware to emails

## Trojan

> [!DEFINE] Trojan Horse 
> A program which contains malicious or harmful code that seems harmless from the outside and is used to get control or cause damage

Trojans get activated upon certain predefined actions by the user and upon activation

Indication of trojan horse attack is abnormal system and network activities

Trojans create covert communication channels for transferring sensitive data

### How Hackers Use Trojan
1. Create Trojan packet using Trojan Horse Construction Kit
2. Create a dropper, which installs the malicious code
3. Create wrapper to Install Trojan on the victim's computer
4. Propagate trojan
5. Execute droppper
6. Execute damage routine

### Evading Anti-virus
- Break the trojan file into multiple pieces and zip them into a single file
- Always write your own Trojan
- Change trojan's syntax
- Change content of trojan using hex editor and checksum and encrypt the file

## Viruses

> [!DEFINE] Viruses
> Self-replicating program that produces its own copies by attaching to another program, computer... etc

### Characteristics of Viruses
- Infects other programs
- Transform, encrypts itself
- Alter data
- Corrupt
- Self-replicating

### Indication of a Virus Attack
- Processes take longer to load
- Computer beeps with no display
- Drive label changes
- Unable to load operating system
- Constant anti-virus alerts
- Computer freezes
- Files and folders are missing
- Suspicious activity
- Browser window freezes
- Lack of storage space
- Unwanted ads and pop-up windows

A virus can be created by 
- Writing virus program
- Using virus maker tools

## Worms

> [!DEFINE] Worms
> A malicious program that replicate, execute and spread across networks independently

Attackers use worm payload to install backdoors which turn infected computers into zombies and creates botnets

## Worms VS Trojan
Worm replicate on its own and doesn't attach itself to any programs
Worms spreads through infected networks but a virus can't

# Malware Analysis

> [!DEFINE] Malware Analysis
> Process of reverse engineering a piece of malware to determine its origin, functionalities and potential impact on the targeted system

- Determine exactly what happened
- Determine malicious intent of malware
- Identify indicators of compromise
- Determine complexity level
- Identify exploited vulnerability
- Identify extent of damage caused by intrusion
- Catch perpetrator accountable for installing software

## Types of Malware Analysis
### Static malware analysis 
also known as code analysis, analyse code of malicious program without executing it
- File fingerprinting
- Local and online malware scanning
- String search
- Identifying packing/obfuscation methods
- Finding portable executables (PE) info
- Identify file dependencies
- Malware disassembly

### Dynamic malware analysis 
Behavioral analysis, involves executing the malware code to know how it interacts with the host and its impact

Consists of two stages:
- System baselining --> Take a snapshot of system at the time the malware analysis ==begin== to identify significant changes from baseline state
- Host integrity monitoring --> Take snapshots of system state ==before and after analysis== to detect changes made

## Preparing Testbed
1. Allocate physical system
2. Install virtual machine
3. Install guest OSs
4. Isolate system from network by ensuring NIC card is in host only mode
5. Simulate internet services
6. Disable shared folders and guest isolation
7. Install malware analysis tool
8. Generate hash value of each OS and tool
9. Copy malware over to guest OS