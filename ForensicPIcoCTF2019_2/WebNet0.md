# WebNet0

## Objetivos
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.


## Solución 
```bash
picoCTF{nongshim.shrimp.crackers}
```

## Notas adicionales
https://es.wikipedia.org/wiki/Seguridad_de_la_capa_de_transporte

Usando WIreShark podemos buscar la bandera dentro de los protocolos TLS 
agregamos la llave en caso de que no se pueda ver el seguimiento de los paquetes
