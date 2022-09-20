# Nice netcat

## Objetivos
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 43239`, but it doesn't speak English...


## Solución 
```shell
──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 43239         
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
55 
99 
48 
56 
50 
49 
102 
53 
125 
10 
picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}
```

## Notas adicionales 
Nos conectamos al net, dentro nos da una serie de números, que resulltan ser codigo decimal, para ello lo copiamos y en mi caso utilice un converitidor de decimal a ASCII , así conseguimos la bandera