personal firewalls/enterprise firewall
basic method- allow or deny the connection

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