1. first of all did the nmap scan and there were lot of open ssh ports. every ssh port gave a message saying lower or higher. so bash script was written to identify the exact ssh port.

[ssh -o HostKeyAlgorithms=+ssh-rsa -o StrictHostKeyChecking=no 10.10.140.7 -p 9160]

2. after that there was a puzzle in the ssh port. it was encrypted. to decrypt it lots of method was being tried. 

[sudo apt install bsdgames] - can download decryting ways
[cat 'encryptedtext' | rot13]
[cat 'encryptedtext' | caesar 1]
[caesar 13 is rot13]
[boxentriq.com] - cipher ditector
[quipquip] - site which can use to identify the cipher
[dcode.fr] - site which can use to decrypt vigenere cipher

3. what i did was i went to boxentriq.com site and it identify this as vigenere cipher. then i cracked the key with max keylength=20. then with that key i went for dcode.fr site and decrypted the cipher. 

4. i had to write a python+bash script to find the ssh port once again. i think it changes everytime.
5. after solving the puzzle i got some password phrase. after applied it to the ssh question i got another passprase.  it was the password for jabberwock@ip.

6. user key is in jabberwock user. its in reverse. use this command

[echo 'flag' | rev]

7. cronjob that will run script as tweedledum after reboot

[cat /etc/crontab]

8.  since after the reboot this run as the other user i'm going to right a reverse shell . this is in pentest monkey. we have root priviledge to run reboot. otherwise we have to enter the passwords.

[sudo reboot]

9.  it has a humptydumpty.txt

[https://crackstation.net/]- password hash cracker

[cat humptydumpty.txt | xxd -r -p] - convert hex to ascii

10. using that key you can log as humptydumpty user. 

[su humptydumpty]

11. alice home directory is weird. it has given executable permission to everyone.  but we can find the user private key to ssh

[cat .ssh/id_rsa]

12. now we logged as alice. read sudoers.d file

[nano /etc/hosts]
[nano /etc/hostname]

[cd /etc/sudoers.d]

13. take that /etc/sudeors.d/alice atvantage. if alice and hostname= (looking-glass reverse word) same can run /bin/bash as root priviledge.

[sudo -h hostname /bin/bash -p]

[python3 /root/passwords/passGenerator.py > /home/tryhackme/passwd; (cat /home/tryhackme/passwd; cat /home/tryhackme/passwd) | passwd jabberwock
]
] - don't know what this do but i think it used to change ssh passwds.

