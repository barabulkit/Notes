`cut -d (delimiter) " " -f (fields) 2` - split string by space char, and gets second index of resulting array
so basicly
`echo "hello world" | cut -d " " -f 1`
will output **hello**
`tr -d (delete) ":"` - will remove all **:** symbols from input
**seq 1 254** - outputs numbers from 1 to 254 including both

# Script start
Bash scripts should starts with path to bash
`#!/bin/bash

# Arguments
you can provide arguments to script
to access them you use `$1` and so on inside
you can get number of arguments with `$#`

# Conditions
```
if [ "$1" == "" ]
then
echo "You forgot to specify IP address"
else
echo "ok"
fi
```

# For loop
```
for ip in  `seq 1 254` ;  do
ping -c $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done
```

# Full ipsweep.sh script
```
if [ "$1" == "" ]
then

echo "You forgot to specify IP address"
echo "Syntax is ./ipsweep.sh 192.168.1"

else

for ip in  `seq 1 254` ;  do
ping -c $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done

fi
```
ampersand in the end of for statement makes it so that you don't wait until this statement completes, you going straigth to running next for cycle

# Simple bash oneliner
```
for ip in `./ipsweep.sh 192.168.1`; do nmap $ip & done
```