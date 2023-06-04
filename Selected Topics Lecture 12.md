up: [[Selected Topics]]

# Digital Forensics

> [!DEFINE] Digital Forensic
> The recovery and investigation of information found on digital devices as it relates to criminal activity

The digital forensics process:
- Collection --> Identification of potential sources of forensic data and acquisition, handling and storage of that data
- Examination --> Assessing and extracting of relevant information from the collected data
- Analysis --> Drawing conclusions from data and correlating data to multiple sources
- Reporting --> Preparing and presenting the concluded data

Types of evidence:
- Direct evidence --> Evidence that is indisputably in the possession of the accused
- Indirect evidence --> Evidence that establishes a hypothesis aka circumstantial evidence
- Best evidence --> Storage devices used by the accused or archives that can be proven to be unaltered
- Corroborating evidence --> Evidence that supports an assertion developed by best evidence

Collection order from most volatile to least volatile

## Chain of Custody
Involves collection, handling and storage of evidence
- Who discovered
- All details 
- Primary responsible
- Physical access

## Data Integrity and Preservation
Time stamping of files should be preserved, original evidence should be copied and analysis should be done on copies

## Attack Attribution

> [!DEFINE] Attack Attribution
> Act of determining the individual, organization, nation responsible for the attack

TTP (Tactics, Techniques, and Procedures) that were used in the incident

Aid attribution with location of host or domain, features of the code used, for internal threats, asset management can help

IP and MAC addresses and Logs can help track the origin of the attack

# Incident Response
Aims to:
- limit the impact of the attack
- Assesses the damage caused  
- Implement recovery procedures

## Incident Response Stakeholders
- Management
- Information assurance
- IT support
- Legal department
- Public affairs and media relations
- HR
- Business continuity planners
- Physical security and facilities management

CMMC (Cybersecurity Maturity Model Certification) certifies organizations by levels 

Level 2 --> Establish an incident response plan that follows the NIST process
Level 3 --> Document and report incidents to stakeholders
Level 4 --> Use knowledge of the attacker's TTP to refine the incident
Level 5 --> Utilize accepted and systematic computer forensic data gathering techniques

# NIST Incident Response Life Cycle:
- Preparation --> Prepare on how to respond to the incident 
- Detection and analysis --> Identify, analyze and validate
- Containment, eradication, recovery --> Implements procedures to contain threat, eradicate the impact and backup
- Post-incident Activities

## Detection and Analysis
Attack vendors --> Web, email, Loss or theft
Detection --> Automated detection, manual detection
Analysis --> Use network and system profiling to determine validity of incident
Scoping --> Information on containment of the incident and deeper analysis
Incident notification

