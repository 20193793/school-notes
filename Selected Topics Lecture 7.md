up: [[Selected Topics]]

> [!DEFINE] IP
> Designed for layer 3 connection-less protocol, provides the necessary functions to deliver a packet from source to destination

IP doesn't make any effort to validate that the packet actually comes from the source it claims to come from

# IPv4 Packet Headers
- Version --> 4-bit identify this packet as IPv4
- Internet header length --> 4-bit length of IP header, minimum length is 20 bytes
- Differentiated Services or DiffServ (DS) --> ToS, 8-bit field used to determine the priority of each packet, First six --> DSCP, last two are ECN bits
- Total length --> Length of IP packet + IP header + user data, max is 2^6 bytes
- Id, flag, fragment offset --> Used to fragment and reassemble packets
- TTL (Time-to-live) --> Limit the lifetime of a packet, decreased by one each time a packet is processed by a router, if time exceeded, send an ICMP time exceeded message
- Protocol --> Identify the next level protocol, ICMP, TCP or UDP
- Header checksum --> Used to determine if any errors has been introduced
- Source IP --> 32-bit binary value, always unicast address
- Destination IP --> 32-bit binary value
- Options and padding --> Varies in length, 0s are added or padded to ensure it contains a multiple of 32-bits

# IP Vulnerabilities
ICMP attack --> Threat actors ICMP messages echo packets to discover subnets and hosts, to generate DoS attacks and alter host routing tables
DoS attack --> Prevent legit users from accessing
DDoS attack --> Like DoS but from multiple sources
Address spoofing attacks --> Spoof source IP address to perform blind or non-blind spoofing
Man-in-middle attack --> Threat actors position themselves between source and destination to monitor capture and control communication, eavesdrop or alter packets
Session hijacking --> Threat actor gain access to the physical network and use MiTM attack to hijack session

## ICMP Attacks
ICMP --> Carry diagnostic messages and reports

Ping command (echo request) is used to verify connectivity to a destination

Threat actors use ICMP for reconnaissance and scanning attacks, DoS and DDoS attacks

Networks should have strict ACL (Access Control List)

ICMP echo request and echo reply --> Perform host verification and DoS attacks
ICMP Unreachable --> Perform reconnaissance and scanning attacks
ICMP mask reply --> Map an internal IP network
ICMP redirects --> Lure a target host into sending traffic
ICMP router discovery --> Inject bogus route entries into the routing table of a target host

## Amplification and Reflection Attacks
Used in DoS attacks

Amplification --> The threat actor forwards ICMP echo request to many hosts which contains the source IP address of the victim
Reflection --> These hosts reply to the victim and overwhelm him

Use resource exhaustion attack

## Address Spoofing Attacks
Blind Spoofing --> Cannot see the traffic that is being sent between host and the target, used in DoS attacks
Non-blind spoofing --> Can see the traffic, use them to inspect the reply packets. Determines the state of a firewall and sequence number prediction and used to hijack authorized sessions

### MAC Address Spoofing Attack
MAC address spoofing attacks are used when threat actors have access to the internal network

- Threat actor alter the MAC address of their host to match the MAC of a target 
- The attacking host then send a frame 
- The switch examines the frame
- The switch overwrites the current CAM table entry and assigns the MAC address to the new port
- Then forwards the frames

Used in MiTM attacks

# TCP and UDP Vulnerabilities
## TCP Segment Header
Appears after IP header
URG --> Specifies if the packet is urgent
ACK --> Acknowledgement
PSH --> Push function
SYN --> Synchronise sequence numbers
FIN --> No more data from sender

TCP provides:
- Reliable delivery
- Flow control --> Multiple segments can have one ack
- Stateful communication --> Three-way handshake

TCP Three-way handshake:
- Initiate client-to-server request
- Server ack request
- Initiate server-to-client ack

## TCP Attacks
### TCP SYN Flood Attack
- TCP SYN Flood attack exploits the three-way handshake
- Denies access to legit users by sending SYN-ACK packets

### TCP RST Attack
- Used to terminate TCP communications between two hosts
- A threat actor would do a TCP reset attack and send a spoofed packet containing a TCP RST to one or both endpoints

### TCP Session Hijacking
Threat actor takes over an already authenticated host and spoof the IP address of one host, predict the next sequence number and then send an ACK

If successful, threat actor could send but not receive	

## UDP Segment Header and Operation
UDP is commonly used by DNS, DHCP, TFTP, NFS, SNMP and in real time apps such as streaming or Voip

UDP is connection-less

UDP is unreliable, means that this function is not provided in the transport layer and must be implemented somewhere else

## UDP Flood Attacks 
UDP is not protected by encryption

In a flood attack all resources on a network are consumed

Try to find closed ports which will cause server to send ICMP port unreachable message which creates a lot of traffic, very similar to DoS attack