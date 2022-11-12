# B1ll_Gat35

## Objetivos
Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ mv win-exec-2.exe.bin win-exec-2.exe     
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
audacity-linux-3.2.1-x64.AppImage  Metared_peru  Obsidian-1.0.0.AppImage  win-exec-1.exe  win-exec-2.exe
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ wine win-exec-2.exe 
wine: created the configuration directory '/home/kali/.wine'
Input a number between 1 and 5 digits: 01^
Initializing...
Enter the correct key to get the access codes: kl
Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}   
```

## Notas adicionales 

Para este reto nuevamente abrimos ghidra importamos el archivo 
ayudandonos de una palabra clave podemos identificar donde se encuentra el archivo
Dentro de ghidra podemos modifcar el archivo en la función que valida la conraseña en lenguaje ensamblador es un jnz y lo vamo a cambiar por un jnc y así parchar la bandera, después exportamos el archivo.