# Lets Warm Up

## Objetivos
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Solución 
```bash
visfx7-picoctf@webshell:~$ echo 0x70 | xxd -r -p && echo ''                   
p
visfx7-picoctf@webshell:~$ 

```
picoCTF{p}<---RESULTADO


## Notas dicionales 
Un sistema de numeración hexadecimal es ideal para grandes sistemas digitales, ya que puede contener/representar valores binarios largos. Este sistema se conoce como base-16 porque se utiliza un total combinado de 16 símbolos (digitales y alfabéticos) del 0 al F para representarlo.

Principalmente usamos el comando xxd para hacer un volcado hexadecimal de caracteres hexadecimales muestreados o revertir la acción indicada.

La opción de comando -r convierte los caracteres hexadecimales a ASCII y la opción de comando -p imprime el resultado en texto sin formato. El comando de eco final produce una nueva línea en la terminal de Linux.

https://www.linuxshelltips.com/convert-hex-to-ascii-characters-linux/#:~:text=The%20command%20option%20%2Dr%20converts,newline%20on%20the%20Linux%20terminal.&text=If%20you%20wish%20to%20convert,the%20file%20to%20xxd%20command.