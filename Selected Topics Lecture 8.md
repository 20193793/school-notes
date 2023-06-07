up: [[Selected Topics]]

# ARP Vulnerabilities
- Hosts broadact an ARP request to other hosts to get the MAC address of a host with a particular IP address
- That host replies with a `gratitious ARP` reply

# ARP Cache Poisoning
Used to launch man-in-middle attacks
ARP request --> ARP reply --> Spoofed gratutious ARP replies

# DNS Attacks
## DNS Open Resolver Attacks
DNS resolvers are vulnerable to multiple malicious activities described in the table

> [!DEFINE]
> DNS cache poisoning attacks: Threat actors send spoofed and falsified RR to DNS resolver to redirect users from legit sites to malicious ones
> 
> DNS amplification and reflection attacks: Threat actors send DNS messages to open resolvers using the IP address of target host
> 
> DNS resource utilization attacks: DoS attack that consumes all available resources

## DNS Domain Shadowing Attacks

> [!DEFINE] Domain Shadowing
> Threat actors gather domain account credentials in order to create multiple sub domains, these domains point to malicious servers

# DHCP Attacks
## DHCP Spoofing Attack

> [!DEFINE] DHCP Spoofing Attack
> Rogue DHCP server is connected to the network and provides false IP configuration parameters to legitimate clients

Misleading information such as:
- Wrong default gateway --> Threat actor provides invalid gateway to create MITM attack
- Wrong DNS server --> Provide wrong DNS server pointing user to a malicious website 
- Wrong IP address --> Threat actor provides invalid IP address, invalid gateway or both, then creates a DoS attack on the DHCP client

# HTTP and HTTPS
Server connection logs can reveal information about the type of scan or attack

Types of connection status codes:
- Informational 1xx
- Successful 2xx
- Redirection 3xx
- Client Error 4xx

Defend against web-based attacks:
- Update OS and browsers
- Use web proxy
- Educate users

## Common HTTP Exploits
### Malicious iFrames
Threat actor insert ads from other sources into the page

As the iFrame is running on the page, it can be used to deliver malicious exploits, such as spam ads, exploit kits and other malware

Prevent malicious iFrames:
- Use web proxy
- Don't use iFrames
- Use services like Cisco Umbrella to prevent users from entering malicious websites

## HTTP 302 Cushioning

> [!DEFINE] HTTP 302 Cushioning
Threat actors use the 302 found response to direct users to new locations

Prevent 302 Cushioning Attacks:
- Use web proxy
- Use Cisco Umbrella

# Email
Examples:
- Attachment-based attacks --> Threat actors embed malicious content in business files
- Email spoofing --> Threat actors create email messages with a forged sender address that is meant to fool the recipient
- Spam email --> Threat actors send unsolicited email containing advertisements or malicious files

# Web-Exposed Databases
## Code Injection
Commands are executed through the web application and has the same permissions as the web application

Used when there is no sufficient input validation

## SQL Injection
Threat actors use SQL injections to breach relational databases or create malicious SQL queries to obtain sensitive data 

Can Read, Modify, Execute admin operations and issue commands to the OS

# XSS (Cross-side Scripting)

> [!DEFINE] XSS (Cross-side Scripting)
> Web pages that are executed on the client-side, within their own web browser, injecting with malicious scripts

Two types:
- Stored (persistent)
- Reflected (non-persistent)

Prevent XSS attacks:
- Ensure developers are aware of XSS vulnerabilities
- IPS implementation
- Web proxy
- Cisco Umbrella