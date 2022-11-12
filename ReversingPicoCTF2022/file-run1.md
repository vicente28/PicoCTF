# file-run1

## Objetivos
A program has been provided to you, what happens if you try to run it on the command line? Download the program [here](https://artifacts.picoctf.net/c/308/run).


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ./run            
zsh: permission denied: ./run
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ls -la
total 132116
drwxr-xr-x  3 kali kali    28672 Nov 12 15:28 .
drwxr-xr-x 28 kali kali     4096 Nov 12 15:27 ..
-rwxr-xr-x  1 kali kali 45143232 Oct 31 03:19 audacity-linux-3.2.1-x64.AppImage
drwxr-xr-x  3 kali kali     4096 Nov 11 23:15 Metared_peru
-rwxr-xr-x  1 kali kali 90080316 Oct 18 21:30 Obsidian-1.0.0.AppImage
-rw-r--r--  1 kali kali    16736 Mar 15  2022 run
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x run          
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ./run       
The flag is: picoCTF{U51N6_Y0Ur_F1r57_F113_9bc52b6b}                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

## Notas adicionales 

Para este nivel solamente necesitamos cambiar los permisos de ejecución del prgrama y así poder correrl, una  vez que lo ejectuemos tendremos la bandera 