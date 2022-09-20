# where are the robots

## Objetivos
`https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830


## Solución 
```bash
https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
User-agent: *
Disallow: /1bb4c.html

https://jupiter.challenges.picoctf.org/problem/56830//1bb4c.html
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}
```

## Notas adicionales
Un archivo robots.txt indica a los rastreadores de los buscadores a qué URLs de tu sitio pueden acceder. Principalmente, se utiliza para evitar que las solicitudes que recibe tu sitio lo sobrecarguen; **no es un mecanismo para impedir que una página web aparezca en Google**. Si quieres que una página web no aparezca en Google, [bloquea la indexación con `noindex`](https://developers.google.com/search/docs/crawling-indexing/block-indexing?hl=es) o protege la página con una contraseña.