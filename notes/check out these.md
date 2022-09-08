cobit framework
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

DNS spoofing(DNS cache poisoning) is entering false information into DNS cache. so the DNS queries return an incorrect response and users are directed to the wrong websites.(DNSSEC canbe used.DNSSEC uses public key cryptography), DNS traffic filtering.
DNS servers use UDP. 
attackers can impersonate as DNS nameservers. forge the reply when DNS resolver queries from nameserver. this is possible because DNS servers use UDP and there is no verification.


-what is mac spoofing

-what is arp poisoning
https://www.varonis.com/blog/arp-poisoning
arp is layer 2 
arp(address resolution protocol) is a protocol that connect IP addresses to a fixed physical machine address(MAC) in LAN.
MAC address is known as data link layer which establish the connection between two physically connected devices. IP address is referred to as the network layer. ARP works between these layers.
IP address of the host or computer which is connected to the network needs to be translated to a hardware address(MAC). without ARP, host would not be able to figure out the hardware address of another host. the LAN keeps a table or directory that maps IP addresses to MAC addresses of the different devices including both endpoints and routers on that network. 

ARP poisoning is cyber criminal sends fake ARP messages to a target LAN with the intention of linking their MAC address with the IP address of a legitimate device or server within the network. the link allows for data from the victims computer to be sent to the attackers computer instead of the original destination. 

-three main data transmission methods in layer 2
unicast
multicast
broadcast

-what is a MAC address

-what is DHCP
DHCP works in application layer
network layer protocol that assign IP addresses dynamically to hosts.
DHCP server is a network server that automatically provides and assigns IP addresses, default gateways and other network parameters to client devices. it relies on the standard protocol known as Dynamic Host configuration protocol.
DHCP send UDP messages.
DHCP spoofing attack is an attack in which attackers set up a rogue DHCP server and use that to send forged DHCP responses to devices in a network. use this attack to replace the IP addresses of Default gateway and DNS servers thereby divert traffic to malicious servers.
DHCP spoofing occurs when an attacker attempts to respond to DHCP requests and trying to list themselves as the default gateway or DNS server. initiating man in the middle attack.
it is possible that they can intercept traffic from users before forwarding to the real gateway or perform DoS by flooding the real DHCP server with request to choke ip address resources.

to dynamically obtain IP address information, a client makes a DHCP request. A DHCP server sends back a DHCP response in which includes information as an IP address, subnet mask, and default gateway. If an attacker puts and false DHCP server in our LAN network, the rogue DHCP server can respond to a client’s DHCP request. Even if the rogue DHCP server and the actual DHCP server both respond to the request of our PC, the PC will use the rogue DHCP server’s response if it reaches the PC faster than actual DHCP server.
**DHCP snooping**

The DHCP snooping feature on Cisco and Juniper switches can be used to mitigate a DHCP server spoofing attack. With this mechanism switch ports are configured in two different state, the trusted and untrusted state. If a port is configured to be trusted, it can receive DHCP responses. In other way, if a port is untrusted, it is not allowed to receive DHCP responses, and if a false attackers DHCP response attempts to enter an untrusted port, the port will be disabled.

**DHCP Snooping** is a security technology on a Layer 2 network switch that can prevent unauthorized DHCP servers from accessing your network. It is a protection from the untrusted hosts that want to become DHCP servers. DHCP Snooping works as a protection from man-in-the-middle attacks. DHCP itself operates on Layer 3 of the OSI layer while DHCP snooping operates on Layer 2 devices to filter the traffic that is coming from DHCP clients.

In Cisco switches, DHCP snooping is enabled manually. Trusted ports should be manually configured and the rest unconfigured ports are considered untrusted ports. Most devices connected to trusted ports are routers, switches, and servers. DHCP clients like PC and laptops are commonly connected to an untrusted port.

How it works is that it will allow DHCP server messages like DHCPOFFER and DHCPACK that are coming from a trusted source. If the DHCP server messages are coming from untrusted ports, it will discard the DHCP traffic. The switch creates a table called the DHCP Snooping Binding Database. The DHCP snooping database registers the source MAC address and IP address of the hosts that are connected to an untrusted port.

-what is a VLAN
logical grouping of network devices in the same broadcast domain. 
tagged vlan
native vlan

-what is SSH and port number
default port 22
*start ssh service* - sudo service ssh start
*check the status* - sudo service ssh status
*create a root pswd* - sudo -i
*edit ssh configuration file* - nano /etc/ssh/sshd_config -> "PermitRootLogin yes"
*restart ssh service* - sudo service ssh restart
*to protect more change the port number in config/everytime after a change restart*
*ssh server run after the rebooting* - sudo systemctl enable ssh

*log into ssh* - ssh [ip address] 
*change port number to login if its changed* - ssh [ip address] -p [port number]

-what is TLS

-what is telnet
port 23. client server protocol. open command line in remoter server. tcp(connection oriented)

-what is ICMP

-what is SMTP

-what is HTTP
is protocol viewing web pages.

-what is SMTP

-what tools are commonly used to secure a standard network
firewall 
IDS
IPS
end point antivirus
password manager/securiy

-how do u update on security news



