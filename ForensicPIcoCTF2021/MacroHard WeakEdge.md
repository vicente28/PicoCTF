# MacroHard WeakEdge

## Objetivos
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c0da20f29337e87ffb58ea987d8c596e/Forensics is fun.pptm)


## Solución 
```bash
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Macrohard 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Macrohard]
└─$ ls
'[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Macrohard]
└─$ code .      
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Macrohard]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q " | tr -d " "
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Macrohard]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q " | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input

```

## Notas adicionales 


https://www.reviversoft.com/es/file-extensions/pptm

El reto consiste en descubir algun archivo que nos puda indirxar que la bandera se encuentre escondida ahí; podemos utilizar visualcode para navegar entre los archivos más rapido y más comodos

La bandera la enocntramos en un archivo llamado "hidden" que tenemos que desencriptar en base 64 