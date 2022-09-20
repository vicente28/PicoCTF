# Glitch Cat

## Objetivos
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 65353`


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 65353
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ python3           
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'


```

## Notas adicionales 
Al entar al net nos aparece en pantalla codigo de python que al correr en el shell python pegamos el codigo y tenemos la clave