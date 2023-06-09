up: [[Selected Topics]]

# Security Onion

> [!DEFINE] Security Onion
> Open source suite of NSM (Network Security Monitoring) tools that run on Ubuntu Linux

Provides three core functions for cybersecurity analyst such as:
- Full packet capture and data types
- Network-based and host-based IDSs
- Alert analyst tools

Can be installed as a standalone or a sensor and server

# Detection Tools for Collecting Alert Data
- CapME --> Allow viewing of pcap transcripts rendered with tcpflow or zeek tools
- Snort --> NIDS, source of alert data indexed in Sguil
- Zeek --> Formerly known as Bro, NIDS that uses behavior-based approach
- Suricata --> NIDS that uses signature-based approach and inline intrusion prevention
- OSSEC --> HIDS
- Wazuh --> host logfile analysis, file integrity monitoring, vulnerability detection, configuration assessment and incident response

# Analysis Tools
- Sguil --> Provide high level console for investigating security alerts
- Kibana --> Interactive dashboard to Elasticsearch data. Allows querying of NSM data and provides flexible visualizations of that data. Possible to pivot from Sguil
- [[Selected Topics Lecture 10#Wireshark|Wireshark]]
- Zeek --> Network traffic analyzer, and pivotable from Sguil

# Alert Generation
ST --> Status of event
CNT --> Count of alert from the same source and destination IP
Sensor --> The agent reporting the event
Alert ID --> Two-part number represents the sensor that reported the problem + the event number for that sensor
Date/Time --> Timestamp
Event message --> The identifying text for the event

# Snort Rule Structure
Consists of two sections --> rule header and rule options

# Alert Evaluation
 The Need for Alert Evaluation:
- Threat landscape is constantly changing
- Threat actors learned quickly how to vary their exploits
- Better to have alerts that are sometimes generated by innocent traffic

## Alerts Classification
ALert:
- True positive --> Alert verified to be an actual security incident (Desirable)
- False positive --> The alert doesn't indicate actual security incident (Benign) (Not desirable)
No Alert:
- True negative --> No security incident has occured (Desirable)
- False negative --> An undetected incident occured (Dangerous)

> [!DEFINE] Benign Event
> An event that shouldn't trigger alerts

False negatives can be detected long after security breach has occured using RSA (Retrospective Security Analysis)

# ELK (Elasticsearch, Logstash, Kibana)
Elasticsearch --> Search and analyze data
Logstash --> Enables collection and normalization of network data into indexes
Kibana --> Graphical interface to data complied by elasticsearch
Beats --> Software plugins that send different types of data

> [!DEFINE] Data Normalization 
> The process of combining data from a number of sources into a known common format

## Pivoting from Sguil
Sguil pivots to PRADS (Passive Real-time Asset Detection System) and SANCP (Security Analyst Network Connection Profiler)

Sguil contains 7 pre-build categories

## Queries in ELK
Elasticsearch is built on Apache Lucene --> Lucene has its own query languagge based on JSON called query DSL (Domain Specific Language) 

Elasticsearch to interface with users using web-based clients that follow the HTTP REST framework

Methods to execute queries URI, cURL, JSON, Dev tools

## Investigations
OSSEC rules detect changes in host-based parameters
OOSEC rules will trigger an alert in Siguil

Squert --> provide visual interface to NSM data