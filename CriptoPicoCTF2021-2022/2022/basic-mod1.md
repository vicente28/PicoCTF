# basic-mod1

## Objetivos
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/393/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)


## Solución 
```python

datos = open('message.txt').read().split()

flag = ''
for n in datos:
        c=int(n) % 37
        if c > 0  and c < 25:
                s = chr(c+65)
        elif  c > 26 and c < 35:
                s = chr(c+22)
        else :
        
                s = '_'
        flag += s

print(f"picoCTF{{{flag}}}")


```

```shell 
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp.py 
picoCTF{R_UND_N_R_UND_7_C18FB3}

```
## Notas adicionales 