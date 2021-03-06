![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/metadata.png)

# Metadatos

Los metadatos son elementos HTML que muestran información sobre la página web. Y son usados por los buscadores para definir información principal del sitio web. Ejemplos de metadatos son, palabras clave, imágenes, temática y estos elementos <code>\<meta\></code> se encuentran contenidos dentro del elemento <code>\<head\></code>.

Ya hemos usado al elemento <code>\<meta\></code> que fue el caso de:

```
<meta charset="UTF-8">
```

El cual nos sirve para usar la codificación UTF-8, en particular lo usamos para usar acentos. Aunque existen varias etiquetas del tipo <code>\<meta\></code> las cuales ayudan a clasificarlas según su contenido.

Pensemos que estos elementos sirven para que los motores de búsqueda (Google, Bing, Yahoo!, etc), les sea más fácil encontrar una página y colocarla con cierta preferencia.

Los ejemplos que veremos en esta sección están en el directorio **examples,** de esta misma carpeta.

Empecemos copiando el siguiente código en un editor de texto plano:

```
<!DOCTYPE html>
<html>

  <head>
    <title>My first page</title>
    <meta charset="UTF-8">
  </head>

  </body>
    <h1>Menu principal</h1>
  </body>

</html>
```

Guardamos como: indice.html
y lo abrimos en el browser para verificar que funcione.

### Atributo name y content

La etiqueta meta lleva normalmente dos atributos. El atributo <code>name</code>, indica el tipo de información, y el atributo <code>content</code>, indica el contenido de dicha información.

Ahora escribimos en seguida de la línea meta:

```
<meta name="keywords" content="programming, html, css, sql">
<meta name="description" content="Este canal contiene tutoriales de diseño web, frontend">
<meta name="author" content="Grupo 614">
```

Con esta metaetiqueta se controla cómo deben rastrear e indexar el contenido los buscadores.

**Usar la etiqueta \<meta name="robots"\>**

```
<meta name="robots" content="noindex">
```

En este ejemplo, la etiqueta <code>meta name="robots"</code> indica a los buscadores que no muestren esa página en los resultados de búsqueda. Como el atributo <code>name</code> tiene el valor <code>robots</code>, la directiva se aplica a todos los rastreadores.

Guardamos y cerramos el archivo.

# Listas

Creamos un nuevo archivo con los elementos básicos:

```
<!DOCTYPE html>
<html>

  <head>
    <title>Learning computer topics</title>
    <meta charset="UTF-8">
  </head>

  </body>
    <h1>Menu principal</h1>
  </body>

</html>
```

Guardamos como: listas.html

Vamos a ocupar las listas para presentar la información de la página que sabemos tiene una temática, empecemos guardando la información de manera desordenada con la etiqueta <code>\<ul\></code>, para enumerar los elementos de la lista usamos la etiqueta <code>\<li\></code>. Copiamos el siguiente código en seguida de <code>\<h1\></code>:

```
<ul>
  <li>Home</li>
  <li>About me</li>
  <li>Courses</li>
  <li>Contact me</li>
</ul>
```

Para cambiar a una lista ordenada, basta cambiar <code>\<ul\></code> por <code>\<ol\></code>.

## Lista anidadas

Podemos capturar listas dentro de las listas, es decir, listas anidadas:

```
   <ul>
	<li>Home</li>
	<li>About me</li>
	<li>Courses</li>
	  <ul>
	    <li>Mathematics</li>
	    <li>Design web</li>
	    <li>Networks</li>
	  </ul>
	<li>Contact me</li>
   </ul> 		
```

Guardamos y cerramos el archivo.

# Etiquetas para la creación de texto

Creamos un nuevo archivo con los elementos básicos:

```
<!DOCTYPE html>
<html>

  <head>
    <title>Curso de historia</title>
    <meta charset='UTF-8'>
  </head>

  <body>
    <h1>Historia del hombre</h1>
  <body>

</html>
```

Guardamos con el nombre: historia.html

Ahora insertamos el siguiente párrafo dentro de la etiqueta <code>\<body\></code> usando la etiqueta <code>\<p\></code>:

```
<p>La especie humana ha evolucionado de otras especies que no eran humanas. Para entender nuestra naturaleza, debemos conocer sus orígenes y su historia biológica. Esta historia ha sido reconstruida con la ayuda de muchas disciplinas científicas: la paleontología, el estudio comparativo de los organismos vivos, la antropología y en épocas recientes, la biología molecular.</p>
```

Para dar un par de saltos de línea dentro del párrafo usamos la etiqueta <code>\<br\></code>. Inserta un salto de línea en algún punto del párrafo anterior, guarda y recarga la página.

**Insertar otro subtitulo y otro párrafo.**

Colocamos un segundo subtitulo con la etiqueta <code>\<h2\></code> e insertamos el siguiente párrafo <code>\<p\></code>: 

Ejemplo:

```
<h2>Capaces de entender</h2>
<p>Los seres humanos actuales somos descendientes de los primeros Homo sapiens, cuyo nombre significa "hombre inteligente" u "hombre capaz de entender". Se sabe que ya hace 40 mil años, el Hombre de Cro-Magnon (cuyo nombre se debe al lugar donde fueron encontrados sus restos en Francia) usaba armas y herramientas hechas de piedras, huesos y cuernos, contaba con una organización social y vivía de la caza.</p>
```

Tanto la etiqueta <code>\<strong\></code>, como <code>\<b\></code>,ambas etiquetas cambiaran a tipo de fuente **negrita.**

Crear un tercer párrafo ahora con <code>\<h3\></code>:

```
<h3>La cultura</h3>
<p>Hemos hablado de los pasos más importantes de la evolución biológica de los seres humanos. Sin embargo, hay que añadir que también nos distinguen de nuestros antepasados directos diferencias no biológicas a las que podemos llamar culturales, y que son típicamente humanas, como la fabricación de herramientas, el lenguaje simbólico, el saber que nos vamos a morir algún día, una organización social basada en la división del trabajo, el desarrollo de una capacidad moral y el establecimiento de relaciones afectivas más profundas y variadas.</p>
```


- Etiqueta <code>\<s\>\</s\></code>. Tachar texto.
- Etiqueta <code>\<blockquote\>\</blockquote\></code>. Citar texto.
- Etiqueta <code>\<hr/\></code>. Insertar o dibujar línea separadora.
- Etiqueta <code>\<em\>\</em\></code>. Tipo de texto _cursiva._
- Etiqueta <code>\<i\>\</i\></code>. Tipo de texto _cursiva_
- <code>\<!--Esto es un comentario en html--\></code>. Insertar comentarios.

# Contenido multimedia

Volvemos a crear un archivo con los elementos básicos:

```
<!DOCTYPE html>
<html>

  <head>
    <title>Grupo 614</title>
    <meta charset='UTF-8'>
  </head>

  <body>
    <h1>Imágenes de gatitos</h1>
  </body>

</html>
```

Guardamos como: gatitos.html

**Insertar una imagen ubicada en la misma carpeta**

Con el elemento o etiqueta <code>\<img\></code> insertamos imágenes conjuntamente con el atributo <code>src</code>. Veamos el siguiente ejemplo:

```
<img src="gatito.jpeg">
```

**Insertar imagen ubicada en otra carpeta**

Cuando la imagen se encuentra en la misma carpeta basta que al atributo <code>src</code> le indiquemos el nombre del archivo. En el caso de que tengas la imagen contenida en la siguiente carpeta de nombre 'imagenes' como esta en el repositorio, escribiríamos:

```
<img src="imagenes/gatito2.jpeg">
```

**Usar el atributo alt**

Si por alguna razón no carga la imagen podemos usar el atributo alt para que en ausencia de la imagen aparezca un texto.

```
<img src="gatito2.jpeg" alt="Imagen de gatito2">
```

Si queremos que al pasar el cursor sobre la imagen, nos de información o el nombre de la imagen usamos el atributo <code>title</code>.

```
<img src="gatito.jpeg" title="Mi gatito">
```

Cambiar el alto y el ancho de las imágenes. Insertamos los atributos <code>widht</code> y <code>height</code>

```
<img src="gatito.jpeg" title="Mi gatito" width="400px" height="300">
```

**Insertar audio en la misma carpeta**

Para esta tarea ocupamos la etiqueta <code>\<audio\></code> conjuntamente con el atributo <code>src</code> y el atributo <code>controls</code> que nos permitirá manipular el archivo (pause, play)

```
<audio src="mecano.mp3" controls></audio></br>
```

**Insertar video**

```
<video src="gadgets.mp4" controls></video></br>
```

**Insertar audio en otra carpeta**

Ya hemos hecho este ejemplo con páginas y texto, ahora lo haremos con un audio que este contenido dos carpetas hacia adelante.

```
<audio src="imagenes/audio/do_it.mp3" controls></audio></br>
```

***
**Nota:** ¿Sabrías por que ocupar esta ruta en carpetas contenidas, y no usar la ruta completa?
***

