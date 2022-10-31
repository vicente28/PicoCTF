# rail-fence

## Objetivos
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://artifacts.picoctf.net/c/272/message.txt). Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.


## Solución 
```bash
T . . . .a . . . .  . . . ._. . . . . 7 . . . ..N. . . . . 6 . . . . D . . . . 5 . . . . 4
 h . . .l.g. . . . . w. . .3.D. . . ._.H. . ._.H. . .3.C. . . 3.1. . .N ._. . ._.  . . .1.0
. .e.f. . .  .s. . . .H.R. .  .0.5 . . . 3 .F . . . 3 . 8. . . N. 4 . . . 3.D . . . 2.8
. . .  . .  .i . . . . 3 . . . .3 . . . . ._. . . . ._. . . . ._. . . . . N . . . . .2 

The_flag_is:_WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997
```

## Notas adicionale

Para este reto podemos hacerlo manual guiandonos en la pagina de wikipedia que nos proporcionan o utilizando un desencriptador web como es https://www.dcode.fr/rail-fence-cipher