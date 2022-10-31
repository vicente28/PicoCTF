# Morsecode

## Objetivos
Morse code is well known. Can you decrypt this? Download the file [here](https://artifacts.picoctf.net/c/235/morse_chal.wav). Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.


## Solución 
```bash
Input: 
.-- .... ....- --... ....  ....- --... .... ----. ----- -.. .-- ..--- ----- ..- ----. .... --...

Output:
WH47H47H90DW20U9H7

wh47_h47h_90d_w20u9h7

picoCTF{wh47_h47h_90d_w20u9h7}

```


## Notas adicionales 

Para resolver este reto tenemos un audio en codigo morse, para visualizar mejor las ondas de audio utilce el programa audacity con eso podemos obervar donde hay puntos, guiones y espacios y utilizamos un desencriptador de codigo morse como puede ser cyberchef

Ponemos los caracteres en minisculas y nos fijamos donde hay espacios más largos para los guines bajos; esto para dar el formaro de una bandera de picoCTF
