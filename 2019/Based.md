# Based

## Objetivos
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.


## Solución 
```shell
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 29956                     
Let us see how data is stored
chair
Please give the 01100011 01101000 01100001 01101001 01110010 as a word.
...
you have 45 seconds.....

Input:
chair
Please give me the  154 151 155 145 as a word.
Input:
lime            
Please give me the 636f6e7461696e6572 as a word.
Input:
container
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

```

## Notas adicionales 
Para este ejercicio nos  conectamos al enlace con el comando nc 
Una Vez iniciamos nos propone un reto el primero es convertir un nùmero binario en ascii después un octal el texto y finalmente un número hexadecimal en texto en un tiempo de 45 segundos. 

Para este reto mi mejor opcion fue utilizar una calculadora online o convertir online

https://www.rapidtables.com/convert/number/hex-to-ascii.html