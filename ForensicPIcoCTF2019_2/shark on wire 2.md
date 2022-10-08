# shark on wire 2

## Objetivos
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.


## Solución 
```python 
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''
for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)

print(flag)


```

```bash
┌──(kali㉿kali)-[~]
└─$ cd Downloads  
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
mystery  Obsidian-0.15.9.AppImage  sharkOnWire
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cd sharkOnWire 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/sharkOnWire]
└─$ ls
capture.pcap  exp.py
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/sharkOnWire]
└─$ python3 exp.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/sharkOnWire]
└─$ 



```

## Notas adicionales 
https://www.comparitech.com/net-admin/pcap-guide/

Para este  nivel haremos una captura de paquetes, nos ayudaremos de la herramienta wireshark; vamos a fiiltrar todos los paquetes cuyo puerto destino sea el 22 y observarmos un patron en la info en el cuando podemos encontrar  los caracteres de la bandera usando Python, pero para no hacerlo uno por uno podemos utilizar una librería en de python 

https://scapy.net/

Es un modulo de manipulación de paquetes 
