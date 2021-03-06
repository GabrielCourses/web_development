![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/header.png)

# HTML

HTML por sus siglas en inglés, significa Hypertext Markup Language. Es decir, un lenguaje de marcado para elaborar páginas webs.

Para comenzar a explorar esta lenguaje de etiquetado (aclarar que no es un lenguaje de programación) vamos iniciar creando un fichero en un editor de texto plano llamado: ejercicio1.html 

En mi caso, estoy usando Vim, pero puedes usar otro como el que trae Windows por defecto que es el Bloc de Notas, o, NotePad++, SublimeText, u otros. Los archivos los puedes consultar en la carpeta <a href="https://github.com/GabrielCourses/web_development/tree/main/html/ejemplo" target="_PLANK">ejemplo.</a>

### ¿Pero qué es una etiqueta en HTML?

Las etiquetas HTML son fragmentos de código que permiten crear elementos HTML, estructuras básicas HTML. Por ejemplo, podríamos crear un párrafo con la etiqueta <code>\<p\></code>.

```
<!DOCTYPE html>
<html>

  <head>
  </head>

  <body>
    <p>
      Esto es un párrafo
    <p>
  <body>

<html>
```

Si notas el etiquetado anterior, verás que <code>\<p\></code> esta dentro de la etiqueta <code>\<body\></code> que a su vez esta dentro de la etiqueta <code>\<html\></code>.

### La etiqueta \<title\>

Para editar el titulo de nuestra página ocupamos la etiqueta <code>\<title\></code> como se nota en la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/title.png)
	
Es decir, el título de la página, estará dentro de la etiqueta de apertura <code>\<title\></code> y la etiqueta de cierre <code>\</title\></code>.

Ahora, si queremos usar caracteres especiales, en particular el acento usado en el español, agregamos la etiqueta <code>\<meta\></code> junto con el atributo <code>charset</code>. 

### La etiqueta \<body\>

Dentro de la etiqueta <code>\<body\></code> se sitúa el contenido de la página web.

Dentro de la etiqueta <code>\<h1\></code> de apertura y <code>\</h1\></code> de cierre, estará el título del contenido. De la misma manera puedo ir poniendo subtítulos con <code>\<h2\></code>, <code>\<h3\></code>, ..., <code>\<h6\></code>.

```
 <body>
    <h1>Aprendiendo programación</h1>
    <h2>Lenguaje de programación</h2>
    <h3>Mensaje de prueba</h3>
  </body>
```

Vamos a darle color a nuestra página, lo haremos creando un archivo con extensión css llamado: estilo.css 

Si queremos que todo el contenido de nuestra página sea de un solo color, digamos azul

```
* {

    color: blue

}
```

Para enlazar nuestros 2 archivos ejercicio1.html y estilo.css agregamos dentro de <code>\<head\></code> la siguiente línea de código: 

```
<link rel="stylesheet" type="text/css" href="estilo.css">
```

***
**Nota:** cada atributo que estamos ocupando no es necesario que lo comprendas del todo ya que aún no revisamos la parte de **estilo en cascada CSS**. Guardamos los cambios y le damos un **refresh** a la página en nuestro navegador, entonces obtenemos:
***

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/blue.png)

Ahora, si solo quiero quiero que el primer título de nuestra página sea azul, y los demás me aparezcan con el color que viene por defecto, el negro, entonces, cambio el asterisco del archivo estilo.css por <code>h1</code>.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/h1.png)

Y si queremos pintar a <code>h2</code> de rojo y a <code>h3</code> de naranja, editamos nuestro archivo: estilo.css

```
h1 {
	color: blue
}

h2 {
	color: red
}

h3 {
	color: orange
}
``` 

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/colors.png)

Recapitulando HTML nos ayuda a darle estructura a la página, en otras palabras serían las cajas como, texto, imágenes, videos, links. Con CSS podemos darle un estilo propio, es decir, la apariencia. Finalmente con JavaScript vamos a darle la funcionalidad, es decir, crear un método para un botón, crear un formulario, etc.

## CSS

CSS, en español 'Hojas de estilo en cascada', es un lenguaje de diseño gráfico para definir y crear la presentación de un documento estructurado escrito en un lenguaje de marcado.

## JavaScript

JavaScript es un lenguaje de programación, con el cual vamos a darle funcionalidad a nuestra página web.

# Contenido

Para que tengas una guía de como leer este repositorio te comparto la lista de contenidos.


1. html
	- README.md
	- ejemplo
		+ ejemplo.html
		+ estilo.css
2. curso
	- README.md
	- ficheros
3. metadatos
	- README.md
	- examples
4. formularios
	- README.md
	- ejercicios
		+ miformulario.html
		+ formulario2.html
		+ multiple.html
		+ controles_agrup.html
5. tablas
	- README.md
	- tabla.html