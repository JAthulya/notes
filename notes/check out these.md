https://tryhackme.com/resources/blog/free_path
-different between cryptography and hashing
-symmentric key/asymmetric key/cyphers
-check security protocols and port numbers(remote protocol portnumber)
-cross site request forgery
-proxy server/dns server
-DMZ in network/firewall where to put

-3 main transmission modes - simple,half duplex, full duplex
simple- a -> b (one direction only)
half duplex a->b, a<-b (a sending b receiving/ b sending a receiving)
full duplex a<>b (two way directional communication)

-what are the communication networks- 
lan - local area network 
man - metropolitan area network
wan - wide area network
personal area network

-what is data center multi tier model design- 
core
aggregation
access

-what is tcp
transmission control protocol
used for host to host communication
connection orientated

-what are tcp header flags
SYN
ACK
RST
fin
urg
psh

-what is ssdp
simple service discovery protocol allows devices to connect and communicate easily over a network. basis for universal plug and play architecture.

-few UDP header field
source port , destination port, udp length, udp checksum

-two intrution detection methods
signature based detection/ anomaly based detection

-what is snmp
simple network management protocol.is an application layer protocol for exchange data between network devices. manages and monitor network elements.

protocol manage network devices. every network devices contain snmp agent that connects with an independent snmp manager.

1. snmp manager - gets responses from agents
2. snmp agent - collect management information about its local environment.
3. managed devices - ex-routers,switches,servers
4. MIB(management information database) - every SNMP agent maintains an information database describing parameters. managers request from these databases.

-what are the two types of sniffing attacks
passive sniffing
active sniffing - DNS poisoning 

-what is DNS
dns helps to find the ip address based on the name. 
1. DNS resolver -  receive the query from the DNS client
2. root nameserver - respond to the resolver with the address of top level domain DNS server(.com, .net)
3. TLD server - responds with the IP address of the domain's authoritative nameserver. 

DNS spoofing(DNS cache poisoning) is entering false information into DNS cache. so the DNS queries return an incorrect response and users are directed to the wrong websites.(DNSSEC canbe used.DNSSEC uses public key cryptography)
DNS servers use UDP. 
attackers can impersonate as DNS nameservers. forge the reply when DNS resolver queries from nameserver. this is possible because DNS servers use UDP and there is no verification.
-what is mac spoofing

-what is arp poisoning

-three main data transmission methods in layer 2
unicast
multicast
broadcast

-what is a MAC address

-what is DHCP
network layer protocol that assign IP addresses dynamically to hosts.

-what is a VLAN
logical grouping of network devices in the same broadcast domain. 
tagged vlan
native vlan

-what is SSH and port number

-what is telnet

-what tools are commonly used to secure a standard network
firewall 
IDS
IPS
end point antivirus
password manager/securiy

-how do u update on security news



