# Tab, Tab, Attack

## Objetivos
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
Addadshashanammu.zip  Obsidian-0.15.9.AppImage
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ 


```

## Notas adicionales 
Para este nivel descomprimimos el archivo zip utilizando el comando `unzip` y abrimos el ultimo archivo,  donde encontraremos la bandera