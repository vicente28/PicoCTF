# Wireshark twoo twooo two twoo

## Objetivos
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/a7b4ce62a4f4313a6e5b0b03b97be953/shark2.pcapng).


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ ls
data.csv
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ cat data.csv  
"No.","Time","Source","Destination","Protocol","Length","Info"
"1637","9.440363","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x1dd2 A cGljb0NU.reddshrimpandherring.com.windomain.local"
"2046","11.972605","192.168.38.104","18.217.1.57","DNS","109","Standard query 0xabb9 A RntkbnNf.reddshrimpandherring.com.windomain.local"
"2448","14.605726","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x9e21 A M3hmMWxf.reddshrimpandherring.com.windomain.local"
"3153","16.506492","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2ee1 A ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
"3442","18.340155","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2a4b A YWRiZWVm.reddshrimpandherring.com.windomain.local"
"3982","20.369626","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x4068 A fQ==.reddshrimpandherring.com.windomain.local"
"4374","22.583745","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x7418 A fQ==.reddshrimpandherring.com.windomain.local"
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ nano data.csv 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ cat data.csv  | cut -d ' ' -f 5
cGljb0NU.reddshrimpandherring.com.windomain.local"
RntkbnNf.reddshrimpandherring.com.windomain.local"
M3hmMWxf.reddshrimpandherring.com.windomain.local"
ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
YWRiZWVm.reddshrimpandherring.com.windomain.local"
fQ==.reddshrimpandherring.com.windomain.local"
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ cat data.csv  | cut -d ' ' -f 5 | cut -d '.' -f 1
cGljb0NU
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ cat data.csv  | cut -d ' ' -f 5 | cut -d '.' -f 1 | tr -d '\n'
cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==                                                                                                                   

                                                                                ┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ cat data.csv  | cut -d ' ' -f 5 | cut -d '.' -f 1 | tr -d '\n' | base64 -d
picoCTF{dns_3xf1l_ftw_deadbeef}                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/WireSharkTwoTwo/datos]
└─$ 

```

## Notas adicionales

https://aristanetworks.force.com/AristaCommunity/s/article/DNS-Exfiltration-The-Light-at-the-End-of-the-DNS-Tunnel

para este reto nos fijaremos en el trafico los protoclos DNS parecen sospechosos por se bastantes cuando regularmente no son tanto; el  protocolo DNS busca el nombre de un dominio y nos trae la dirección ip del dominio pero por lo genaral solo se requiere un query y un response 

en wireshark hacemos una filtración de paquetes , en la infromación notamos que hay o lo que parece ser el final de una cdns && ip.dst == 18.217.1.57 && dns.qry.name contains localadena en base64

hacemos una filtracion de esta forma 
dns && ip.dst == 18.217.1.57

y filtramos los parecidos de esta froma 

dns && ip.dst == 18.217.1.57 && dns.qry.name contains local

exportamos los datos a una carpeta en formato csv y trabajamos en consola 