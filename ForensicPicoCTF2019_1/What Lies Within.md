# What Lies Within

## Objetivos
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?


## Solución 
```bash
picoCTF{h1d1ng_1n_th3_b1t5}

┌──(kali㉿kali)-[~/Downloads]
└─$ sudo gem  install zsteg

┌──(kali㉿kali)-[~/Downloads]
└─$ zsteg -a buildings.png | grep picoCTF
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"

```

## Notas adicionales 
Podemos instalar zteg y utilizar para leer los metadatos 

también ultilizar un decodificador  online de esteganografía, basta con subir la imagen y ya lo tenemos 
https://stylesuxx.github.io/steganography/.