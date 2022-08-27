personal firewalls/enterprise firewall
basic method- allow or deny the connection
traditional firewall-> works on network layer

netcat- windows start a listner(in cmd)
-ncat -l 4545

in linux- nc (ip address) 4545 -> to send the msg

zedlan(windows DNS log analyser) -> to analyse firewall records
log file location- windows/system32/logfiles/firewall/pfirewall.log

linux firewall - iptables
1. chain input - what address or ports can data come into the computer
sudo iptables -A INPUT -s 10.0.2.4 -j DROP

2.chaing forward
3. chain output

--iptables rules--
1. limit access to the local network
sudo iptables -A INPUT -s 10.0.2.0/24 -p tcp --dport 22 -m connlimit --connlimit-above 2 -j REJECT
sudo iptables -A INPUT -s 10.0.2.0/24 -p tcp --dport 22 -j ACCEPT

2. allow HTTP/HTTPS and limit the traffic rate
sudo iptables -A INPUT -p tcp -m multiport --dports 80,443 -m limit --limit 120/minute --limit-burst 250 -j ACCEPT

3. divert telnet traffic to the honeypot
sudo iptables -t nat -A PREROUTING -p tcp --dport 23 -j DNAT --to 10.0.2.199

4. log any drop packet
sudo iptables -A INPUT -j LOG --log-prefix "ipt-block:"
cat /var/log/kern.log

5. block anyother input
sudo iptables -A INPUT -j DROP
sudo iptables -L -n

6. check the nat table
sudo iptables -t nat -L -n


firewall builder -> make it easy to manage firewalls

GNS3 emulator -> https://github.com/GNS3/gns3-gui/releases?after=v1.5.0rc1
CIsco ASA router

WAF- web application firewall
ex - imperva

Honeypots -> honeynet.org
ex- dockpot/ cowrie
honeyscore.shodan.io

sabsa.org -> leading security architecture framework

IDS - network based ids or host based ids
IPS - ex- virus guard
ADS - anomaly detection system 
1.protocol content or behavior anomalies   /   2.statistical anomalies

snort - network based IDS using rules based detection
apt-get install snort

suricata-
security onion-

einstein - intrusion detection/intrusion prevention/security analytics/information sharing

msf venom - creating a payload
cloack - creating python payload

fileless attacks - powershell can be used to execute scripts in memory
(python -m SimpleHTTPServer)

hiding with the cloack of invisibility - ex- cd History(in windows)

embedding malware in an alternate data stream - windows can see $DATA section in NTFS cant see alternate data streams

hide text file.
type file1.txt > file2.txt:hidden.txt
more < file2.txt:hidden.txt