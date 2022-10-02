# Search source

## Objetivos
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:58133/)


## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ wget -r http://saturn.picoctf.net:58133/
┌──(kali㉿kali)-[~]
└─$ grep -R pico saturn.picoctf.net:58133   
saturn.picoctf.net:58133/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/

```

## Notas adicionales 

 Recursive Retrieval Options
       -r
       --recursive
           Turn on recursive retrieving. 