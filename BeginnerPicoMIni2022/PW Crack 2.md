# PW Crack 2

## Objetivos
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level2.flag.txt.enc) in the same directory too.


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level2.py  
                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ python level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

## Notas adicionales 
Para este ejercicio abrimos con el editor nano el archivo python, pero vemos que la contraseña tiene caracteres hexadecimales ayudandons de una tabla podemos decodificar dichos caracteres 

https://www.asciitable.com/