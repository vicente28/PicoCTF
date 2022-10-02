# GET aHEAD

## Objetivos
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:21939/](http://mercury.picoctf.net:21939/)


## Solución 
```bash
└─$ curl -I  http://mercury.picoctf.net:21939/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_6ef27873}
Content-type: text/html; charset=UTF-8


picoCTF{r3j3ct_th3_du4l1ty_6ef27873}

```

## Notas adicionales 

HTTP request methods: https://www.restapitutorial.com/lessons/httpmethods.html
Response code : https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
Web hacking proxy: https://learn.onemonth.com/web-hacking-tools-proxies/

Con inspector en network al apartado de resend ponemos head y enviar, ahora en headers encontraremos la bandera

En consola podemos utilizar el comando `curl -1 + link` 

También podemos utilizar la apliacación Brupsuite

