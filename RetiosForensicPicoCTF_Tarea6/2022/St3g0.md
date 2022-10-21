# St3g0

## Objetivos
Download this image and find the flag.

-   [Download image](https://artifacts.picoctf.net/c/421/pico.flag.png)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads/stego]
└─$ python3 stego.py pico.flag.png
--Welcome to $t3g0--
1: Encode
2: Decode
2 
Enter Source Image Path
pico.flag.png   
Decoding...
Hidden Message: picoCTF{7h3r3_15_n0_5p00n_96ae0ac1}
                                                                                                                    
┌──(ka
```

## Notas adicionales 
https://medium.com/swlh/lsb-image-steganography-using-python-2bbbee2c69a2
https://github.com/djrobin17/image-stego-tool
