# Information


## Objetivos
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/b4d62f6e431dc8e563309ea8c33a06b3/cat.jpg)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/information]
└─$ exiftool cat.jpg
ExifTool Version Number         : 12.44
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2022:10:21 01:19:06-04:00
File Inode Change Date/Time     : 2022:10:21 01:18:49-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/information]
└─$ echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d

picoCTF{the_m3tadata_1s_modified}                                                                                                                   
┌──(kali㉿kali)-[~/Downloads/information]
└─$ 

```

## Notas adicionales

para este nivel utilice la herramienta exitfool, checando los datos vemos que en la parte de 'License' podemos notar que hay un texto en base 64 copiandolo y decodificano encontramos la bandera 