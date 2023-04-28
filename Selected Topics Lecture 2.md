# Networks Sizes
Small Home Network --> Connect few computers to each other and to internet
SOHO --> Home office or remote office to connect to corporate network or access centralized, shared resources
Medium to Large Network --> Used by corporations and schools and can have many locations and interconnected hosts
World Wide Network --> The internet

# Client-Server Communications

> [!DEFINE] Hosts
> All computers connected to the network, also known as end-points, end devices or nodes

> [!DEFINE] Server
> Computers with specialized software that provides information to other endpoints in the network

# Protocols

> [!DEFINE] Protocols
> Set of rules that govern communication done by a network and define communication methods and features

Protocols dictate message encoding, formatting, encapsulation, size, timing and delivery options, common formatting and rules for exchanging messages

HTTP (Hypertext Transfer Protocol), TCP (Transmission Control Protocol) and Internet Protocol (IP)

> [!DEFINE] Information Sharing 
> How error and system messages are passed between devices

> [!DEFINE] Session Management 
> Manages the setup and termination of data transfer sessions

## TCP/IP Protocol Suite (Internet Model)
Two aspects of TCP/IP:
- Open standard protocol suite --> Freely available to the public
- Standards-based protocol suite --> Endorsed by networking industry and approved by a standards organization

Layers:
4. Application --> Represent data to user
3. Transport --> Support communication between devices
2. Internet --> Determine best path
1. Network Access --> Control hardware devices

### Application Layer

> [!DEFINE] DNS (Domain Name System)
> Translates domain name to IP addresses

![[Pasted image 20230427235942.png]]

#### DNS Lookup Process
- Search cache, if nothing is found, query will be issued
- If mapping is not found, query other higher-level servers, this is known as Recursive Queries

> [!DEFINE] Zone Transfer
> The process of transferring DNS data between servers

#### DNS Message Format
DNS uses UDP port 53
If DNS response exceeds 512 bytes --> DDNS is used

#### Dynamic DNS
Allows a user to register IP address with a domain name as in DNS
The subdomain is mapped to the IP address of the user

#### WHOIS Protocol
TCP-based protocol used to identify the owners of internet domains
Uses a query in the form of FQDN

#### Host Config 

> [!DEFINE] 
> DHCPv4 (Dynamic Host Configuration Protocol for IPv4): Dynamically (automates) assigns IPv4 addressing information to DHCPv4 clients
> DHCPv6 (Dynamic Host Configuration Protocol for IPv6)
> SLAAC (Stateless Address Autoconfiguration): Obtain IPv6 Info without using DHCPv6 server

> [!DEFINE] 
> Pool: Configured range of addresses
> Lease period: Time that DHCP can allocate IP addresses

DHCPDISCOVERY --> Identify any available DHCP servers on the networks
DHCPOFFER --> Lease to the client
DHCPREQUEST --> Identifies the explicit server and lease offer that the client is accepting
DHCPNAK --> Offer no longer valid
DHCPACK --> Offer is available

#### Email

> [!DEFINE]
> SMTP (Simple Mail Transfer Protocol): Clients can send email and servers to send email to other servers
> POP3 (Post Office Protocol Version 3): Enable clients to retrieve mail from servers
> IMAP (Internet Message Access Protocol): Enables clients to retrieve, access email stored on server as well as maintain email on server

SMTP uses port 25
POP3 uses TCP port 110

#### Web and Web Service 

> [!DEFINE]
> HTTP (Hypertext Transfer Protocol): Rules for exchanging multimedia files
> HTTPS (Hypertext Transfer Protocol Secure) 
> REST (Representational State Transfer): Uses APIs and HTTP requests to create web apps

1. The browser interprets the three parts of the url
2. Initiate HTTP request by sending GET request
3. In response, the server sends the HTML code containing the content of the webpage

`?` --> Query string
`#` --> Fragment, subordinate part of the resource

HTTP uses TCP port 80
Six methods; GET, POST, PUT, DELETE, OPTIONS, CONNECT

1xx --> Informational
2xx --> Success
3xx --> Redirection
4xx --> Client error
5xx --> Server error

HTTPS uses encryption and authentication to secure data as it travels
Data is encrypted with SSL (Secure Socket Layer) or TLS (Transport Layer Security)

HTTPS/2 is specified to use TLS with ALPN (Application-layer Protocol Negotiation)

### Transport Layer
Connection Oriented - TCP (Connection Control Protocol): Enables reliable communication between hosts

Connectionless - UDP (User Diagram Protocol): Send process packets running on one host to another process running on another host

> [!DEFINE] 
> IPv4: Receives message segments and packages them into packets, uses 32-bit adderess
> IPv6: Uses 128-bit address
> NAT (Network Address Translation): Transfers IPv4 from a private network into globally unique public IPv4

#### Messaging

> [!DEFINE]
ICMPv4 (Internet Control Message Protocol for IPv4): Provide feedback from destination to source about errors in packet delivery
ICMPv6 (Internet Control Message Protocol for IPv6)
ICMPv6 ND (Internet Control Message Protocol for IPv6 Neighbor Discovery): Includes 4 prootcol messages that are used for address resolution and duplicate address detection

#### Routing Protocols

> [!DEFINE] 
> OSPF (Open Shortest Path First): Uses hierarchical design based on areas
> EIGRP (Enhanced Interior Gateway Routing Protocol): Uses composite metric based on bandwidth, delay, load and reliability
> BGP (Border Gateway Protocol): Open standard exterior gate-way used between internet and service providers

### Network Access Layer

> [!DEFINE]
> ARP (Address Resolution): Provides dynamic address mapping between an IPv4 address and hardware address

### Data Link Protocols

> [!DEFINE] 
> Ethernet: Rules for wiring and signaling standards of the network access layer
> WLAN: Rules for wireless signaling

# OSI Reference Model

> [!DEFINE] OSI Model
> Provide list of functions and services that can occur at each layer, prescribing what must be done but not how it should be done and also how layers interact with each other

Layers:
7. Application --> Process-to-process communication
6. Presentation --> Representation of data
5. Session --> Organize presentation layer dialogue and manage data exchange
4. Transport --> Services to segments, transfer and reassemble the data for individual communications
3. Network --> Services to exchange individual pieces of data
2. Data Link --> Methods for exchanging data frames between devices
1. Physical --> Mechanical, electrical, functional and procedural means to activate, maintain and de-activate physical connections

# Segmenting Messages
Large streams of data results in delays, Segmentation divides a stream of data into smaller units (packets) for transmission

Each packet is sent separately and the packets containing segments for the same destination can be sent over different paths.

> [!DEFINE] Encapsulation Process
> Various protocol information is added while data is transmitted across a network

> [!DEFINE] Protocol Data Unit (PDU)
> The form that a piece of data takes at any layer

The naming changes according to each layer
Data --> Application layer
Segment --> Transport layer
Packet --> Network Layer
Frames --> Data link layer
Bits --> Physical layer

Encapsulation --> send, Top-to-bottom
De-encapsulation --> receive, Bottom-to-top


# File Transfer

> [!DEFINE] File Transfer
> FTP (File Transfer Protocol): Set rules to access and transfer files
> SFTP (SSH File Transfer Protocol): Establish secure file transfer session that is encrypted
> TFTP (Trivial File Transfer Protocol): Simple and connection-less protocol with best-effort and unrecognized file delivery

## FTP
Control connection --> first connection to server to control traffic
Data connection --> data connection to server to data traffic

## SMB (Server Message Block)
Sharing protocol that describes the structure of shared network resources, request/response protocol

SMD messages can:
- Start
- Authenticate
- Control
- Terminate sessions
- Allow apps to send/receive
