# c0rrupt

## Objetivos
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd  mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor mystery                      

00000000  89 50 4E 47  0D 0A 1A 01   00 00 00 0D  43 22 44 52    
.PNG........C"DR
																												   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd  mystery | head
00000000: 8950 4e47 0d0a 1a01 0000 000d 4322 4452  .PNG........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*3o.[U.== ..


00000000  89 50 4E 47  0D 0A 1A 01   00 00 00 0D  49 48 44 52   

┌──(kali㉿kali)-[~/Downloads]
└─$ file mystery     
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install pngcheck

┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v mystery                                 
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery

00000040  00 09 70 48  59 73 AA 00   16 25 00 00  16 25 01 49                                      ..pHYs...%...%.I

┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor mystery  
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).

┌──(kali㉿kali)-[~/Downloads]
└─$ open mystery   

picoCTF{C0rrupt10n_1847995}

```

## Notas adicionales 
Por la cabecera del archivo Mysterí podemos ver que se trata de un PNG entonces obsevando la pagina podemos editar los Bits de acuerdo al tipo de archivo podemos ir a a la pagina de wikipedia de PNG ahí enocontramos lo valores hexadeximales 

00000000: 8950 4e47 0d0a 1a01 0000 000d 4322 4452  .PNG........C"DR

podemos ver que nuestra imagen al final encontramos los caracteres C''DR y deber se IHDR

00000000  89 50 4E 47  0D 0A 1A 01   00 00 00 0D  49 48 44 52   

Intalamos PNG chech Una herramienta que nos permite checar la integridad de los archivos png y nos ayudara a verificar que esta mal 

00000040  00 09 70 48  59 73 AA 00   16 25 00 00  16 25 01 49                                      ..pHYs...%...%.I

los valores de phys vemos que son grandes y debemos modificarlo 

Entonces también vemos errores en los chunks IDAT y vemos que es grande para esto cambiamos AA por 00 y listo ya no tenemos errores detectados en nuestra imagen 

https://es.wikipedia.org/wiki/Portable_Network_Graphics