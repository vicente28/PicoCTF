## Objetivos

Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/114/disk.img.gz)
-   Access checker program: `nc saturn.picoctf.net 52279`

## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/Sleuthkit]
└─$ ls
disk.img.gz
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Sleuthkit]
└─$ gzip -d disk.img.gz                          
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Sleuthkit]
└─$ ls -lah  
total 101M
drwxr-xr-x 2 kali kali 4.0K Oct 18 16:41 .
drwxr-xr-x 6 kali kali  28K Oct 18 16:36 ..
-rw-r--r-- 1 kali kali 100M Oct 18 16:36 disk.img

┌──(kali㉿kali)-[~/Downloads/Sleuthkit]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

┌──(kali㉿kali)-[~/Downloads/Sleuthkit]
└─$ nc saturn.picoctf.net 52279
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}


```

## Notas adicionales 
https://www.sleuthkit.org/

sleuthkit es una herramienta open source para analisis forense digital, es una coleccion de comandos y herramientas y una libreria en c que permite analizar imagenes de los discos y recuperar archivos. 

utilizamos la herramienta mmls nos sirve para despelgar de como estan configuradas las particiones en el disco de imagen