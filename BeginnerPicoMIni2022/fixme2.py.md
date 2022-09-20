# fixme2.py

## Objetivos
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/66/fixme2.py)


## Solución 
```bash
──(kali㉿kali)-[~/Downloads]
└─$ python fixme2.py 
  File "/home/kali/Downloads/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ nano fixme2.py 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}


```

## Notas adicionales 
AL igual que el anterior problema, aquí arreglamos un  script de python donde el prblema esta en un IF donde la compración debe ser == 