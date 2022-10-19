# Includes

## Objetivos
Can you get the flag? Go to this [website](http://saturn.picoctf.net:54634/) and see what you can discover.


## Solución 
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="[style.css](view-source:http://saturn.picoctf.net:54634/style.css)">
    <title>On Includes</title>
  </head>
  <body>
    <script src="[script.js](view-source:http://saturn.picoctf.net:54634/script.js)"></script>
  
    <h1>On Includes</h1>
    <p>Many programming languages and other computer files have a directive, 
       often called include (sometimes copy or import), that causes the 
       contents of a second file to be inserted into the original file. These 
       included files are called copybooks or header files. They are often used
       to define the physical layout of program data, pieces of procedural code
       and/or forward declarations while promoting encapsulation and the reuse
       of code.</p>
    <br>
    <p> Source: Wikipedia on Include directive </p>
    <button type="button" onclick="greetings();">Say hello</button>
  </body>
</html>
```

``` css
body {
  background-color: lightblue;
}

/*    */
```

```js
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}*/
```
## Notas adicionales

Para este nivel vamos al source de la pagina ahí podemos ingresar a la hoja de estilos como al script jason donde encontaremos la bandera 