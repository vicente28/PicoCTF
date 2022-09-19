# plumbing

## Objetivos
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.



## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 4427 | grep picoCTF
picoCTF{digital_plumb3r_5ea1fbd7}


```

## Notas adicionales 
En este nivel nos conectamos al puerto indicado, si nosotros ingresamos solamente o nos conectamos al enlace, nos apareceran muchas cadenas de texto por lo que un vez ingresado la conexión, antes de oprimir enter tenmos que filtrar la frase que estamos buscando con nuestro conocidicimo comando `grep` seguido de la frase que vamos a filtrar 