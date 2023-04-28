up: [[Selected Topics]]

# ICMP
ICMP messages are not required and often are not allowed within a network for security reasons

Messages:
- Host confirmation --> host is operational, if host is availabe, host send an echo reply
- destination or service unreachable --> 
	- 0 Net
	- 1 Host
	- 2 Protocol
	- 3 Port
- Time exceeded --> TTL == 0
- Route redirection

0 Echo reply
3 Destination unreachable
5 Redirect
8 Echo request
11 Time exceeded

# Ping
Tests:
- Pinging local loopback
- Pinging default gateway
- Pinging remote host

# Traceroute
A utility that generates list of hops that were successfully reached along the path

Traceroute provides RTT (Round Trip Time) for each hop which is the time a packet takes to reach the remote host and for the response from the host to return

# Destination on Same Network
Physical Address (MAC) --> Ethernet NIC
Logical Address (IP) --> Used to send packet from source to destination

# ARP (Address Resolution Protocol)
Devices uses ARP to determine destination MAC address

ARP resolve IPv4 address to MAC address and maintain a table of mappings

ARP cache timer removes entries after it hasn't been used in a certain amount of time

# Three Layer Network Design Model
- Access --> Provide endpoints and direct access to network
- Distribution --> Aggregates access layers and provide connectivity
- Core --> Connectivity distribution for large LAN environments

But can be made into two-tier Core and Distribution layers are collapsed

# Firewall
Permitting or denying traffic
Public network --> untrusted
Private network --> trusted

## Firewall Type Descriptions
- Packet filtering (stateless) firewall --> layer 3, 4, uses lookup table
- Stateful firewalls --> Most versatile and most common, layer 3,4,5, use packet connection information
- Application gateway firewall (proxy firewall) --> layer 3,4,5,7, done in software
- Next-generation firewall (NGFW) --> Integrated intrusion prevention, app awareness and control, upgrade paths, techniques to address evolving security threats

## Common Firewall Properties
- Resistant to network attacks
- Only transit point between internal and external networks
- Enforces access control policy

## Common Security Architectures
- DMZ (Demilitarized Zone) --> Inside interface connected private network, outside interface connected to public network and a DMZ interface
- ZPFs (Zone-based Policy Firewall) --> Uses concept of zones which is a group of interfaces

# IDS and IPS
- IDS (Intrusion Detection System) --> No impact on network, cannot stop trigger packets, correct tuning is required for response action, more vulnerable to evasion techniques
- IPS (Intrusion Prevention System) --> Stops trigger packets and can use stream normalization techniques, but might affect network trafic and have impact on network

## IPS 
Types:
- Host-based IPS --> specific for host, disadvantage --> OS dependant and must be installed on all hosts
- Network-based IPS 

# SNMP (Simple Network Management Protocol)
Application layer protocol that provides message format
Allows admins to do the following:
- Manage end devices
- Monitor and manage network performance
- find and solve network problems
- Plan for network growth

Manager --> Run SNMP management software
Agent --> Nodes

# NetFlow
Developed by CISCO and provides statistics on packet flow
Provide data to enable:
- Network and security monitoring
- Network planning 
- Traffic analysis
- IP accounting for billing purposes

# Port Mirroring
Create duplicate copies of traffic passing through a switch

# Syslog Servers
Network devices to send system messages

Provides three primary functions:
- Gather logging information for monitoring and troubleshooting
- Select type of logging information
- Specify destination of captured syslog messages
- Ability to specify the destination of captured syslog messages

# NTP (Network Time Protocol)
Synchronise the time across all devices on a network

Stratum 0 --> Gets time from authoritative time sources
Stratum 1 --> Devices are directly connected to authoritative time sources
Stratum 2 --> 