# Forbidden Paths

## Objetivos
Can you get the flag? Here's the [website](http://saturn.picoctf.net:49700/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?


## Solución 
```bash
../../../../flag.txt en la entrada de texto

picoCTF{7h3_p47h_70_5ucc355_6db46514}
```

## Notas adicionales 
Indicamos la cantidad de directorios qque tiene que recorrer el path para llegar a la bandera 