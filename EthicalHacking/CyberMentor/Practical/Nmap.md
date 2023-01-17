`nmap -T4 -p- -A 192.168.1.101`
**-T4** - defines speed of scanning 1 is the slowest and 5 is the fastest
**-p-** - will scan through all the ports
**-p 80,443** - will scan only 80 and 443 ports
**-A** - enables all info, os detection, versions of services etc.
**-Pn** - treat the host as if it is online, even if it is not responds to ping
**-sn** - ping scan, basicly ipsweep
**-sS** - only TCP SYN will be sent
**-sU** - UDP scan