# Secrets

## Objetivos
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:61481/).


## Solución 
```bash
[secret/assets/index.css](view-source:http://saturn.picoctf.net:61481/secret/assets/index.css)
http://saturn.picoctf.net:61481/secret/

view-source:http://saturn.picoctf.net:61481/secret/hidden/superhidden/

picoCTF{succ3ss_@h3n1c@10n_39849bcf}

```

## Notas adicionales 

Para este nivel como pista tenmos la frase "folders folders folders" lo que indica que tenemos que navegar entre estos,  al entrar al source de la pagina encontramos un link a "secret/assets/index.css" si borramos la extension o nos vamos al link "secret" encontraremos un gif indicando que estamos cerca, al ver el source de ese link, encontramos otro link href llamado "superhidden/login.css" quitando la hoja de estilos quidandonos solo con el link a la carpeta superhidden y observamos el source de esa pagina encontraremos la bandera 