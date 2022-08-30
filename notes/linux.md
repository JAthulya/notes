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

__Common directories__
/etc
>This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system.

/var
>The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (**/var/log**), or other data that is not necessarily associated with a specific user

/root
>Unlike the **/home** directory, the **/root** folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "**/home/root**" by default.

/tmp
>This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.






