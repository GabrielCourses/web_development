![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/header.png)

# HTML

HTML, por sus siglas en inglés, significa Hypertext Markup Language. Es decir, un lenguaje de marcada, para elaborar páginas webs.

Para comenzar a explorar esta herramienta (aclarar que no es un lenguaje) vamos iniciar creando un fichero en un editor de texto plano llamado ejercicio1.html En mi caso, estoy usando Vim pero usted puede usar otro como NotePad++, SublimeText, u otros. Los archivos los puedes consultar en la carpeta [ficheros](https://github.com/GabrielCourses/web_development/tree/main/HTML/ficheros)

### ¿Pero qué es una etiqueta en HTML?

Las etiquetas HTML son fragmentos de código que permiten crear elementos HTML, estructuras básicas HTML. Por ejemplo, podríamos crear un párrafo con la etiqueta \<p\>.

```
<!DOCTYPE html>
<htlm>

	<head>
	</head>

	<body>	
		<p>
			Esto es un párrafo.
		</p>
	</body>

</html>
```

Si notas el etiquetado anterior, verás que \<head\> está dentro de la etiqueta \<html\> y a su vez \<p\> dentro de la etiqueta \<body\>.

### La etiqueta \<title\>

Para editar el titulo de nuestra página ocupamos la etiqueta \<title\> como se nota en la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/title.png)

Es decir, el título de la página, estará dentro de la etiqueta de apertura \<title\> y la etiqueta de cierre \</title\>.

Ahora, si queremos usar caracteres especiales, en particular el acento usado en el español, agregamos la etiqueta \<meta\> junto con el atributo charset. 

### La etiqueta \<body\>

Dentro de la etiqueta \<body\> se sitúa el contenido de la página web.

Dentro de la etiqueta \<h1\> de apertura y \<h1\> de cierre, estará el título del contenido. De la misma manera puedo ir poniendo subtitulos con \<h2\>, \<h3\>, ..., \<h6\>.

Vamos a darle color a nuestra página, lo haremos creando un archivo con extensión .css 

Si queremos que todo el contenido de nuestra página sea de un solo color, digamos azul

```
* {
	color: blue
}
```

Para enlazar nuestros 2 archivos ejercicio1.html y estilo.css agregamos dentro de \<head\> la siguiente línea de código: 

```
<link rel="stylesheet" type="text/css" href="estilo.css">
```

Nota cada atributo que estamos ocupando, no es necesario que lo comprendas del todo ya que aún no revisamos la parte de **estilo en cascada CSS**. Guardamos los cambios y le damos un **refresh** a la página en nuestro navegador, entonces obtenemos:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/blue.png)

Ahora, si solo quiero quiero que el primer título de nuestra página sea azul, y los demás me aparezcan con el color que viene por defecto, el negro, entonces, cambio el asterisco del archivo estilo.css por h1

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/h1.png)

Y si queremos pintar a h2 de rojo y a h3 de naranja, editamos nuestro archivo estilo.css

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

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/colors.png)

Recapitulando HTML nos ayuda a darle estructura a la página, en otras palabras serían las cajas como, texto, imagenes, videos, links. Con CSS podemos darle un estilo propio, es decir, la apariencia. Finalmente con JavaScript vamos a darle la funcionalidad, es decir, crear un método para un botón, crear un formulario, etc.


# CSS

CSS, en español 'Hojas de estilo en cascada', es un lenguaje de diseño gráfico para definir y crear la presentación de un documento estructurado escrito en un lenguaje de marcado.

# JavaScript

JavaScript es un lenguaje de programación, con el cual vamos a darle la funcionalidad a nuestra página web

