`nmap -F -A -T1 -v` - for slow scan over top 100 ports
`ffuf -w /usr/share/wordlists/dirb/common.txt -u http://tenet.htb/FUZZ -fc 403 -p 2` - for directory bruteforce, -p to set delay between requests, -fc to filter status codes, not include 403 in this example
`nslookup google.com`
`whois google.com`
`theHarvester -d google.com`

# Extra tools
1. wayback machine
2. tomnomnom wayback
3.  httpprobe (`cat list.urls | httpprobe`)
4. wpscan - for wordpress
