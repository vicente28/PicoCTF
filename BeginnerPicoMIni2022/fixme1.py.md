# fixme1.py

## Objetivos
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/37/fixme1.py)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ python fixme1.py  
  File "/home/kali/Downloads/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ nano fixme1.py    
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ python fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
                                                                                                                                                                                                                                           



```

## Notas adicionales 
En este ejercicio consite en arreflar un script de python, simplemente con nano abrimos el editor de archivos y corregimos en esta caso un problema de identación en el print