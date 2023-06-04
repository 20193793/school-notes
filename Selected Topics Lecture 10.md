up: [[Selected Topics]]

# Network Monitoring
Operations of network:
- Traffic flow
- Bandwidth usage
- Resource access

Common methods used to capture traffic and send it to the network monitoring devices: 
- Network taps (TAPs (Test Access Points))
- Traffic mirroring using SPAN (Switch Port Analyzer)

## Network TAPs

> [!DEFINE] Network TAPs
> A passive splitting device implemented inline between a device of interest and the network, that forwards all traffic to an analysis device while allowing the traffic to reach its intended destination

Taps sends both TX and RX data streams on separate dedicated channels, this ensures all data arrives at the monitor at real time

Taps are fail-safe

## Traffic Mirroring and SPAN
Special techniques such as port mirroring must be used to bypass network segmentation

Port mirroring enables the switch to copy frames to Switch Port Analyzer (SPAN) 

Ingress traffic --> Entering
Egress traffic --> Leaving

> [!DEFINE] SPAN Session
> Association between source and destination ports

Single session --> one or multiple ports

Cisco switches --> Session traffic can be copied to more than one destination port

A source VLAN can be specified in which all ports in the source VLAN become sources of SPAN traffic

RSPAN (Remote SPAN) --> Use flexibility of VLANs

# Network Security Monitoring Tools
- Network protocol analyzers --> Wireshark and Tcpdump
- NetFlow
- SIEMS (Security Information and Event Management)

> [!NOTE]
> Security analysts rely on log files and SNMP for network behavior discovery

> [!DEFINE] Network Protocol Analyzers (Packet Sniffer)
> Programs used to capture traffic

## Wireshark
Packet capture application
Used for security analysis, troubleshooting, software and protocol development and education

Frames captured by Wireshark saved in a PCAP file

Wireshark can open files from other software such as tcpdump

## NetFlow
Provides 24x7 statistics on packets that flow through a Cisco router or multilayer switch

