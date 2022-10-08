# WebNet1

## Objetivos
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/webnet1]
└─$ strings vulture.jpg | grep pico
picoCTF{honey.roasted.peanuts}

```

## Notas adicionales 
https://es.wikipedia.org/wiki/Seguridad_de_la_capa_de_transporte

Abrimos la cpatura de paquetes con WIreshark  inngresando la clave TLS . Y observamos que hay una imagen que se  esta descargando podemos extraerla del trafico con export Objects y desupés ir a examinar esa imagen, también desde el mismo wireshark nosotros podemos seguir el Strings de los paquetes 