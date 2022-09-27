# JaWT Scratchpad

## Objetivos
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864


## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ nano hash                                            
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cat hash        
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoidmljZW50ZSJ9.dAc8a-hPoR6DDoNxlZeObXWrsZ8HyEYDf9zorKSHers
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists
amass  dirb  dirbuster  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt.gz  sqlmap.txt  wfuzz  wifite.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for kali: 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists                         
amass  dirb  dirbuster  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt  sqlmap.txt  wfuzz  wifite.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo apt install john                           
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
john is already the newest version (1.9.0-Jumbo-1+git20211102-0kali3+b1).
john set to manually installed.
The following packages were automatically installed and are no longer required:
  libev4 libexporter-tiny-perl libfmt8 libhttp-server-simple-perl libilmbase25 liblerc3 liblist-moreutils-perl liblist-moreutils-xs-perl libopenexr25 libpoppler118 libpython3.9-minimal libpython3.9-stdlib libsvtav1enc0
  libwebsockets16 python3-dataclasses-json python3-limiter python3-marshmallow-enum python3-mypy-extensions python3-responses python3-spyse python3-token-bucket python3-typing-inspect python3.9 python3.9-minimal
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ john hash -w-/usr/share/wordlists/rockyou.txt
picoCTF{jawt_was_just_what_you_thought_1ca14548}
                                                                                

```

## Notas adicionales 
https://jwt.io/
https://github.com/openwall/john
idor
hackeron
brupsuite

Al logearnos tenemos nos da un token que podemos utilizarlo,por ejemplo guardarlo en un archivo y utilizar una herramienta llamada John the riper y así hacer una atque de diccionario; encontramos que se utilizo Ilovepico así nuestro token se modifica podemos copparlo pegar en token en la la app cookie editor y tenemos la bandera 