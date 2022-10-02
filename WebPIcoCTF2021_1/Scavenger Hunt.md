# Scavenger Hunt

## Objetivos
There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?


## Solución 
```html
<!doctype html>
<html>
  <head>
    <title>Scavenger Hunt</title>
    <link href="[https://fonts.googleapis.com/css?family=Open+Sans|Roboto](view-source:https://fonts.googleapis.com/css?family=Open+Sans|Roboto)" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="[mycss.css](view-source:http://mercury.picoctf.net:44070/mycss.css)">
    <script type="application/javascript" src="[myjs.js](view-source:http://mercury.picoctf.net:44070/myjs.js)"></script>
  </head>

  <body>
    <div class="container">
      <header>
		<h1>Just some boring HTML</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

      <div id="tabintro" class="tabcontent">
		<h3>How</h3>
		<p>How do you like my website?</p>
      </div>

      <div id="tababout" class="tabcontent">
		<h3>What</h3>
		<p>I used these to make this site: <br/>
		  HTML <br/>
		  CSS <br/>
		  JS (JavaScript)
		</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      </div>

    </div>

  </body>
</html>
```

``` css

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

```

``` 
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?


```

``` 
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.


```

``` 
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}.


```

## Notas adicionales 

Viendo el source de la pagina podemos encontrar partes de la bandera, en el html y la hoja de estilos.

pero para la parte 3 y demás no la enontramos en el archivo.js entonces podemos hacer uso de robots, que podemos mantener a google fuera de indexar cierta parte  del sitio 

Ahora para la parte 4 necesitamos acceder al servidor apache para ello hacemos uso de .htaccess

Para la parte 5 de nuestra bandera nos deja una pista , lo que nos lleva a .DS_Store el cual almacena información de la carpeta donde este el archivo y información visual 

