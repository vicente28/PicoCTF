# Trivial Flag Transfer Protocol

## Objetivos
Figure out how they moved the [flag](https://mercury.picoctf.net/static/4fe0f4357f7458c6892af394426eab55/tftp.pcapng).


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/trivial]
└─$ ls -la   
total 89040
drwxr-xr-x 2 kali kali     4096 Oct 11 10:12 .
drwxr-xr-x 4 kali kali    28672 Oct 18 15:11 ..
-rw-r--r-- 1 kali kali      113 Oct 11 10:12 instructions.txt
-rw-r--r-- 1 kali kali   824518 Oct 11 10:12 picture1.bmp
-rw-r--r-- 1 kali kali 36578358 Oct 11 10:12 picture2.bmp
-rw-r--r-- 1 kali kali  1466574 Oct 11 10:12 picture3.bmp
-rw-r--r-- 1 kali kali       59 Oct 11 10:12 plan
-rw-r--r-- 1 kali kali   138310 Oct 11 10:12 program.deb
-rw-r--r-- 1 kali kali 52116496 Oct 11 09:57 tftp.pcapng
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/trivial]
└─$ cat instructions.txt | tr [A-Z] [N-ZA-M]
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN

┌──(kali㉿kali)-[~/Downloads/trivial]
└─$ cat plan  | tr [A-Z] [N-ZA-M]
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS

──(kali㉿kali)-[~/Downloads/trivial]
└─$ sudo dpkg -i program.deb                                
[sudo] password for kali: 
(Reading database ... 353161 files and directories currently installed.)
Preparing to unpack program.deb ...
Unpacking steghide (0.5.1-9.1+b1) over (0.5.1-9.1+b1) ...
dpkg: dependency problems prevent configuration of steghide:
 steghide depends on libmcrypt4; however:
  Package libmcrypt4 is not installed.
 steghide depends on libmhash2; however:
  Package libmhash2 is not installed.

dpkg: error processing package steghide (--install):
 dependency problems - leaving unconfigured

┌──(kali㉿kali)-[~/Downloads/trivial]
└─$ steghide --extract -sf picture3.bmp -p DUEDILIGENCE

┌──(kali㉿kali)-[~/Downloads/trivial]
└─$ cat flag.txt
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

## Notas adicionales 
Para este reto vamos utilizar nuevamente wireshark y seguir la captura de paquetes TFPT vamos a extraer todos en la carpeta del reto y podemos salir del wireshark . encontramos mensajes donde indica que la bandera esta en alguna de las imagenes, instalamos el programa . deb que viene en el paquete para utilzar la herramienta que nos proprcionan llamada steghide 