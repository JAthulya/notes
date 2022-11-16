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
