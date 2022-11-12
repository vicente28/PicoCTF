# file-run2

## Objetivos
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"? Download the program [here](https://artifacts.picoctf.net/c/351/run).


## Solución 
```bash

```┌──(kali㉿kali)-[~/Downloads]
└─$ ls -la      
total 132116
drwxr-xr-x  3 kali kali    28672 Nov 12 15:35 .
drwxr-xr-x 28 kali kali     4096 Nov 12 15:27 ..
-rw-r--r--  1 kali kali    16816 Mar 15  2022 run
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x run                                
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ./run                                       
Run this file with only one argument.
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ./run hola
Wont you say 'Hello!' to me first?
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ ./run Hello!             
The flag is: picoCTF{F1r57_4rgum3n7_be0714da}                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```


## Notas adicionales 

De la misma forma que el reto anterior tenmos que cambiar los permisos de ejecución del programa 