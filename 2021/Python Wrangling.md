# Python Wrangling

## Objetivos
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py) using [this password](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt) to get [the flag](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en)?


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
ende.py  flag.txt.en  Obsidian-0.15.9.AppImage  pw.txt
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ cat pw.txt 
aa821c16aa821c16aa821c16aa821c16
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ python ende.py -d flag.txt.en 
Please enter the password:aa821c16aa821c16aa821c16aa821c16
picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
                                        
```

## Notas adicionales 
Para este nivel descargamos el python script, la vandera y la contraseña
