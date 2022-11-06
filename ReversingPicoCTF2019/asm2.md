# asm2

## Objetivos
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)


## Solución 
```bash
ack :
[      ] < esp
[      ] < ebp - 0xc
[  0x8b] < ebp - 0x8
[ 0x2f ] < ebp - 0x4
[ ebp  ] < ebp 
[ ret  ] < ebp + 0x4
[ 0xb  ] < ebp + 0x8
[ 0x2e ] < ebp + 0xc

registers  
[ 0xf6 ] eax

asm2: (0xb,0x2e)
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave
        <+41>:  ret
0xf6

```

## Notas adicionales