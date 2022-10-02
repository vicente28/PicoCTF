# Glory of the Garden

## Objetivos
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.



## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ la          
garden.jpg  Obsidian-0.15.9.AppImage
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd garden.jpg 

00230550: a2bb bdac 9687 98e4 d3b2 e87f ffd9 4865  ..............He
00230560: 7265 2069 7320 6120 666c 6167 2022 7069  re is a flag "pi
00230570: 636f 4354 467b 6d6f 7265 5f74 6861 6e5f  coCTF{more_than_
00230580: 6d33 3374 735f 7468 655f 3379 3333 6464  m33ts_the_3y33dd
00230590: 3265 4546 357d 220a                      2eEF5}".

```

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ strings garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"
                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

## Notas adicionales 

Un editor hexadecimal es un tipo de programa informático que permite a un usuario modificar archivos binarios. Los editores hexadecimales fueron diseñados para editar sectores de datos de disquetes o discos duros por lo que a veces se llaman "editores de sectores".