# Roboto Sans

## Objetivos
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:65352/) out.


## Solución 
```bash
http://saturn.picoctf.net:65352/robots.txt

User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/


anMvbXlmaWxlLnR4dA==

es igula a =  js/myfile.txt

agrgamos la exensión a la pagina 
http://saturn.picoctf.net:65352/js/myfile.txt

picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

obtenemos la bandera 
```

## Notas adicionales 

Para este nivel el nombre nos da una pista de que se trata de robots, entramos a la pagina argegando robots.txt y obtenmos un codigo que al parecer esta en base64 al decodifcarlo en una pagina enontramos  'js/myfile.txt' lo agrgamos al link de la pagina y obtenemos un enlace que nos lleva a la bandera 