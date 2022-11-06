# asm3

## Objetivos
What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat test.S                          
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xb]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xd]
        <+15>:  add    ah,BYTE PTR [ebp+0xc]
        <+18>:  xor    ax,WORD PTR [ebp+0x12]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret    

┌──(kali㉿kali)-[~/Downloads]
└─$ cat test.S | cut -d ':' -f2 > chal.s  

┌──(kali㉿kali)-[~/Downloads]
└─$ cat chal.s 
.intel_syntax noprefix
.global asm3

asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xb]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xd]
        add    ah,BYTE PTR [ebp+0xc]
        xor    ax,WORD PTR [ebp+0x12]
        nop
        pop    ebp
        ret    

┌──(kali㉿kali)-[~/Downloads]
└─$ nano solve.c

┌──(kali㉿kali)-[~/Downloads]
└─$ cat solve.c   
#include <stdio.h>

int asm3(int, int, int);

int main() {
    printf("The flag is 0x%x\n", asm3(0xba6c5a02,0xd101e3dd,0xbb86a173));
    return 0;
}

┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -c chal.s -o chal.o                                                              
                                                                                                                                      
┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -c solve.c -o solve.o -w                                                         
                                                                                                                                      
┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -o a.out solve.o chal.o                                                          
/usr/bin/ld: warning: chal.o: missing .note.GNU-stack section implies executable stack
/usr/bin/ld: NOTE: This behaviour is deprecated and will be removed in a future version of the linker
                                                                                                                                      
┌──(kali㉿kali)-[~/Downloads]
└─$ ./a.out                                                                                   
The flag is 0x669b
                    





```

## Notas adicionales 
https://carlosrafaelgn.com.br/Asm86/