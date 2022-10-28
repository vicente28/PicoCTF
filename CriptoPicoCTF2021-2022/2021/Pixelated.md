# Pixelated

## Objetivos
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png)


## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ cd /opt 
                                                                                                                   
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar        
[sudo] password for kali: 
--2022-10-25 10:07:25--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.173.1
Connecting to www.caesum.com (www.caesum.com)|216.234.173.1|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                100%[=============================================>] 304.95K  33.6KB/s    in 10s     

2022-10-25 10:07:36 (29.2 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                                                                   
┌──(kali㉿kali)-[/opt]
└─$ chmod +x stegsolve.jar
chmod: changing permissions of 'stegsolve.jar': Operation not permitted
                                                                                                                   
                                                                            ┌──(kali㉿kali)-[/]
└─$ cd ~   
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
caxcan-club.py  mind  Obsidian-1.0.0.AppImage  stego
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ java -jar /opt/stegsolve.jar              
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true


picoCTF{1b867c3e}
```

## Notas adicionales 

https://en.wikipedia.org/wiki/Visual_cryptography

Para este reto vamos a conseguir una herramienta llamada stegsolve que noas ayuda a junar las imagenes y desifrar el mensaje 