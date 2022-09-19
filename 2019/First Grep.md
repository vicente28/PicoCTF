# First Grep

## Objetivos
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.


## Solución 
```bash
──(kali㉿kali)-[~/Downloads]
└─$ grep picoCTF file 
picoCTF{grep_is_good_to_find_things_5af9d829}


```

## Notas adicionales 
En este nivel descargarmos el archivos al hacer una cat vemos que el contenido del archivo es mucho por lo que nuevamente hacemos uso de nuestro comando 'grep' junto con la frase picoCTF