# patchme.py

## Objetivos
Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/386/patchme.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/386/flag.txt.enc).


## Solución 

```python
  GNU nano 6.4                                    patchme.flag.py *                                            
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('flag.txt.enc', 'rb').read()

def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), "utilitarian")
        print(decryption)
        return
    print("That password is incorrect")




```
```bash┌──(kali㉿kali)-[~/Downloads]
└─$ python3 patchme.flag.py 
Please enter correct password for flag: ak98
Welcome back... your flag, user:
picoCTF{p47ch1ng_l1f3_h4ck_c4a4688b}


```

## Notas adicionales 

En este reto nos dan un archivo en python que al analizarlo vemos que tiene una función de comparación, si nuestra contraseña coincide con alguna de las siguientes entraremos 

``` python
if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
```

Podemos elegir alguna y utilizarla o hacer un cambio, ya sea poner valida otra contraseña o incluso hacer que salte, en mi caso simplemente la deje así y utilice esa contraseña 

```python
if( user_pw == "ak98")
```