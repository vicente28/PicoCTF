# PW Crack 1

## Objetivos
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/53/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/53/level1.flag.txt.enc) in the same directory too.


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
level1.flag.txt.enc  level1.py  Obsidian-0.15.9.AppImage
                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ python level1.py 
Please enter correct password for flag: 60b
That password is incorrect
                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level1.flag.txt.enc   
                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level1.py          
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ python level1.py        
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}

```

## Notas adicionales 
En este nivel tenmos que ingresar al codigo con nano en mi caso, para poder dar con la contraseña que se encuentra en un IF del codigo, lo copiamos ejectuamos el archivo python y usamos la contraseña y con esto tenemos la bandera 