# Lookey here

## Objetivos
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/294/anthem.flag.txt).


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ strings anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}

```

## Notas adicionales 