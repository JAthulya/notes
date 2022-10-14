always go for tcp stream

cracking hashes in /etc/shadow
john -wordlist=/rockyou.txt hashfile
john hashfile --show -> to see the already cracked hashes

remove saved john hashes
sudo locate john.pot
rm location/john.pot
run the john again

analyze this later for more backdoor info
git clone https://github.com/NinjaJc01/ssh-backdoor
look into binary files in linux

sudo apt install hashcat
hashcat -m 1710 "hashvalue:salt" /opt/rockyou.txt

john
sudo john --format=dynamic_82 -wordlist=/home/kali/Desktop/wordlist/rockyou.txt hash.txt

hash.txt
username:hashvalue$saltvalue