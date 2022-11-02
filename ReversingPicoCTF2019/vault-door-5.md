# vault-door-5

## Objetivos
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)


## Solución 
```bash
c0nv3rt1ng_fr0m_ba5e_64_84fd5095 <---Cyberchef

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from base64 import b64decode
>>> from urllib.parse import unquote
>>> cat = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1"

>>> cad =b64decode(cat)
>>> cad
b'%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%38%34%66%64%35%30%39%35'
>>> cad = unquote(cad)
>>> cad
'c0nv3rt1ng_fr0m_ba5e_64_84fd5095'
>>> 


```

## Notas adicionales 

En este reto lo que hacemos es que al analizar el codigo vemos que al pasar por el metodo check password la hace un url encocode y luego lo transfroma en base 64 y al final lo compara con un texto o un string llamadp expected si es igual tendremos el pase. 
Esto quiero decir que si decodifcamos en base64 y luego hacemos un url decode tendremos la constraseña
Una de las formas es ir a cyberchef y decodifcar el texto primero en base64 y lugo un URLdecode; 

c0nv3rt1ng_fr0m_ba5e_64_84fd5095


