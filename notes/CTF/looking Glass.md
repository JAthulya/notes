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
6. 