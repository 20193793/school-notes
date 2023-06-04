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