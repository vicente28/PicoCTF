# Wave a flag

## Objetivos
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm) has extraordinarily helpful information...


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm 
zsh: permission denied: ./warm
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x ./warm 
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm         
Hello user! Pass me a -h to learn what I can do!
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}

```

## Notas adicionales 
EN este nivel descargamos la bandera, desupes la ejectuamos pero notamos que tenemos los permisos denejados, cambiomos los perimisos de ejecución con el comando `chmod +x`  