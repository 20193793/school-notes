up: [[Selected Topics]] 

# Transport Layer
## Role of Transport Layer
- Responsible for logical communication between applications running on different hosts
- The link between application-layer and the lower layers

## Transport Layer Responsibilities
- Add header information
- Tracking individual conversations
- Identify, separate and manage multiple conversations
- Segmenting and reassembling data
- Enable communication conversations to be interleaved using segmentation and multiplexing

Transport layer protocols specify how to transfer messages between hosts

## Transportation of Data
Transport layer includes TCP and UDP

TCP is a stateful protocol, means that it keeps track of state

### TCP (Transmission Control Protocol)
TCP provides reliability and flow control

TCP basic operations:
- Number and track data segments
- Acknowledge received data
- Retransmit any unacknowledged data
- Sequence data that might arrive in the wrong order
- Send data at an efficient rate

#### TCP Features
- Establishes a Session --> TCP is a Connection-oriented protocol
- Ensures reliable delivery
- Provides same-order delivery --> Due to multiple routes, data can arrive in the wrong order
- Supports flow control --> Resources are limited, TCP can reduce the rate of data flow to avoid overtaxing

### UDP (User Datagram Protocol)
Provides basic functions for delivering datagrams between apps with little overhead and data checking

Connectionless Protocol
Doesn't acknowledge

#### UDP Features
- Data is reconstructed as the order that it is received
- No reliable delivery
- No session establishment
- No flow control

DNS and DHCP uses UDP

UDP dynamically selects a port number from the range of port numbers which are usually well-known or registered port numbers

## TCP Connection Establishment
1. Initiating client requests a client-to-server session
2. Server acknowledge session
3. Client acknowledge server-to-client session

## TCP Session Termination
1. Client has no more data --> send FIN to server
2. Server sends ACK to acknowledge the FIN
3. Server sends FIN to client to terminate session
4. Client responds with ACK to acknowledge the FIN sent by server

# Network Layer
## Basic Operations of Network Layer Protocol
- Addressing of end devices (IP addresses)
- Encapsulation --> PDU into a packet, by adding an IP header
- Routing --> Selects best path
- De-capsulation --> By destination

## Characteristics of IP
- Connectionless (Uses UDP)
- Best effort --> reliable (Uses UDP)
- Media independent

## IPv4 Packet Header Fields
- Version
- DS
- Header checksum
- TTL
- Protocols
- Source address
- Destination adddress

## IP Addressing Basics
To assign IPv4 address it requires:
- IPv4 address --> Host address
- Subnet mask --> Network/host portion

To get the network address = IPv4 host address AND Subnet mask (In binary)

> [!DEFINE] Prefix Length
> Number of bits set to 1 in the subnet mask

## Subnetting

> [!DEFINE] Subnetting
> Process of reducing the size of network to create smaller broadcast domains

Subnetting reduces overall network traffic and improves network performance

## IPv4 Address Classes
Class A --> 0.0.0.0/8 to 127.0.0.0/8 --> Support extremely large networks
Class B --> 128.0.0.0/16 to 191.255.0.0/16 --> Support moderate networks
Class B --> 192.0.0.0/24 to 233.255.255.0/24 --> Support small networks with maximum of 254 hosts
Class D --> Multicast block
Class E --> Experimental

50% class A, 25% class B, 12.5% class C, 12.5% class D & E

NAT is used to translate between private IPv4 and public IPv4 addresses

## Host Forwarding
Role of network layer is to direct packets between hosts, a host can send a packet to itself, local host or remote host

Determine if its sent to local or remote host
IPv4 --> Subnet mask
IPv6 --> Local router

### Default Gateway
A network device that can direct traffic to other networks

Its usually a router with these features:
- Send and receive data, accept and forward
- Routes and directs traffic to other networks
- Has a local IP address in the same range of other IP addresses in the local network

# Ethernet
Ethernet operates in the data link and physical layer 

Ethernet frame size is between 64 to 1518 bytes
Smaller than 64 is discarded, more than 1518 are considered jumbo or baby giant frames

MAC address is expressed in hexadecimal