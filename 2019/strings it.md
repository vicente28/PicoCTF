# strings it

## Objetivos
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?



## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_7f766a23}


```

## Notas adicionales 
En este nivel tenemos que descargar un archivo "strings" nos dirigimos a la ruta del archivo una vez ahí aplicamos el comando strings, pero tenmos muchas lineas, lo que nos hace imposible encontrar lo que estamos buscando, peri gracias al comando grep junto con la palabra que estamos buscando nos hace un filtrado en donde podemos encontrar la solucíon. 