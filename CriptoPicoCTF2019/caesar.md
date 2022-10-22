# caesar

## Objetivos
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat ciphertext  
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}

picoCTF{crossingtherubicondjneoach}


```

```python
import string 
import re
abc=string.ascii_letters

encriptado  = open('ciphertext' , 'r').read()
encriptado = re.findall('\{(.*)\}', encriptado)[0]

rot = 22
salida = ''

for car in encriptado:
        salida += abc[ ( abc.find(car) + rot) % 23  ]

 
print(salida)}



```



## Notas adicionales

https://cryptii.com/pipes/caesar-cipher

el cifrado de Caesar o cifrado por desplazamiento es una de las formas de encripcion de mensaje mas vieja y más simple, es de susitución donde cada letra es remplazado por una letra corresponidente a cierto número de letras desplazadas hacía arriba o hacía abajoj 

podemos utilizar cyberchef o hacer un pequeño script en python 
