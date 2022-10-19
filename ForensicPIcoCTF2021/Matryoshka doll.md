# Matryoshka doll

## Objetivos
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ open dolls.jpg 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install binwalk 
[sudo] password for kali: 
Sorry, try again.
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
binwalk is already the newest version (2.3.3+dfsg1-2).
binwalk set to manually installed.
The following packages were automatically installed and are no longer required:
  libev4 libexporter-tiny-perl libfmt8 libhttp-server-simple-perl libilmbase25 liblerc3 liblist-moreutils-perl
  liblist-moreutils-xs-perl libopenexr25 libpoppler118 libpython3.9-minimal libpython3.9-stdlib libsvtav1enc0
  libwebsockets16 python3-dataclasses-json python3-limiter python3-marshmallow-enum python3-mypy-extensions
  python3-responses python3-spyse python3-token-bucket python3-typing-inspect python3.9 python3.9-minimal
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk dolls.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383940, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383940, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
dolls.jpg  _dolls.jpg.extracted  Obsidian-0.15.9.AppImage
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cd _dolls.jpg.extracted 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196045, uncompressed size: 201447, name: base_images/3_c.jpg
383807        0x5DB3F         End of Zip archive, footer length: 22
383918        0x5DBAE         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted  
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                   
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77653, uncompressed size: 79808, name: base_images/4_c.jpg
201425        0x312D1         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                                                   
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 64, uncompressed size: 81, name: flag.txt
79786         0x137AA         End of Zip archive, footer length: 22

                                                                                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{e3f378fe6c1ea7f6bc5ac2c3d6801c1f} 
```

## Notas adicionales 