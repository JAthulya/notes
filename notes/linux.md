**EXPANDING hard disk size in kali linux vmware**
fdisk -l
gparted (if this doesn't work watch this- https://www.youtube.com/watch?v=DSySW9r5CIg&t=66s)
https://www.youtube.com/watch?v=NwpzYlfKnrY&t=1s - do like this
after reboot

__find something__
find by the name -> find -name passwords.txt
all txt files -> find -name * .txt

__grep - find something in content__
access certain ip address in the log file -> grep "10.0.0.2" file.log

__operators__
& - execute commands in the background
&& - run multiple commands (c1 && c2)
(>) - out put director
(>>) - write in the same file without overwrite

__SSH__ 
>ssh username@10.10.1.1

touch - create file
mkdir - create folder
cp - copy a file or folder
mv - move a file or folder
rm - remove a file or folder
file - determine the type of a file
su - switch between users
wget - wget url

default port 22
*start ssh service* - sudo service ssh start
*check the status* - sudo service ssh status
*create a root pswd* - sudo -i
*edit ssh configuration file* - nano /etc/ssh/sshd_config -> "PermitRootLogin yes"
*restart ssh service* - sudo service ssh restart
*to protect more change the port number in config/everytime after a change restart*
*ssh server run after the rebooting* - sudo systemctl enable ssh

*log into ssh* - ssh [ip address] 
*change port number to login if its changed* - ssh [ip address] -p [port number]

__Common directories__
/etc
>This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system.

/var
>The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (**/var/log**), or other data that is not necessarily associated with a specific user

/root
>Unlike the **/home** directory, the **/root** folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "**/home/root**" by default.

/tmp
>This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.

__text editors__
vim
nano - nano filename

__transferring files from ur host- SCP(SSH)__
from local to remote-
 scp file.txt ubuntu@192.168.1.30:/home/ubuntu/filename.txt
from remote to local-
 scp ubuntu@192.168.1.40:/home/ubuntu/filename.txt file.txt

__python web server__
create sercer
> python3 -m http.server

download from it
> wget http://127.0.0.1:8000/file

__processes__
ps - list of running processes
ps aux - processes run by other users and those don't run from a session
top - real time statistics about the processes running on the system
kill - kill the process ex- kill 1134

namespaces - split up the resources available on the computer

_launch apache2 on boot_ - systemct1 start apache2

__ctrl+c__ = cancel
__ctrl+z__ = run in background(ex- run scripts in background)
fg - bring background processes to foreground

__Automation__
cron
crontab -e
take backups of "documents" every 12 hours
(0 *12 * * * cp -R /home/cmnatic/Documents /var/backups/)

**metasploit**
start the service 
*service postgresql start*

search for exploits/payloads
*search type:exploit platform:windows pdf*
*use (name of the exploit/payload)*
see the options- *show options*

**export**
Export IP=10.10.10.10
now in next shell you can use $IP









