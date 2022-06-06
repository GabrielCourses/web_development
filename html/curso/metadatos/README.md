![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/metadata.png)

# Metadatos

Los metadatos son elementos HTML que muestran información sobre la página web. Y son usados por los buscadores para definir información principal del sitio web. Ejemplos de metadatos son, palabras clave, imágenes, temática y estos elementos <code><meta></code> se encuentran contenidos dentro del elemento <code><head></code>.

Ya empezamos a usar el un ejemplo del elemento \<meta\> que fue el caso de:

```
<meta charset="UTF-8">
```

El cual nos sirve para usar la codificación UTF-8, en particular lo usamos para usar acentos. Aunque existen varias etiquetas del tipo \<meta\> las cuales ayudan a clasificarlas según su contenido.

Pensemos que con estos elementos para los motores de búsqueda, entendamos Google o cualquier otro, se le será más fácil encontrar una página y colocarla con cierta preferencia.

Para esta carpeta Metadatos, los ficheros con los ejemplos desarrollados, ahora los coloco en otra carpeta llamada **examples,** esto lo hago para no transpapelarnos entre varios archivos. Para empezar hacer pruebas, vamos empezar desde cero, escribiendo el siguiente código en nuestro editor de texto plano.

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
y la abrimos en el navegador para verificar que todo funcione bien.

### Atributo name y content

La etiqueta meta lleva normalmente dos atributos. El atributo **name**, indica el tipo de información, y el atributo **content,** indica el contenido de dicha información.

Ahora escribimos en seguida de la línea meta

```
<meta name="keywords" content="programming, html, css, sql">
<meta name="description" content="Este canal contiene tutoriales de diseño web, frontend">
<meta name="author" content="Grupo 614">
```

Con esta metaetiqueta se controla cómo deben rastrear e indexar el contenido los buscadores.

**¿Quiero que se muestren en el buscador mis palabras clave?**

```
<meta name="robots" content="index">
```

# Listas

Tomamos el mismo archivo indice.html y cambiamos el subtitulo h1 a "Learning computer topics"

Vamos a ocupar las listas para presentar la información de la página que sabemos tiene una temática, empecemos guardando la información de manera desordenada con la etiqueta \<ul\>.

```
<ul>
  <li>Home</li>
  <li>About me</li>
  <li>Courses</li>
  <li>Contact me</li>
</ul>
```

Para cambiar a una lista ordenada, basta cambiar \<ul\> por \<ol\>.

## Lista anidadas

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

## Etiquetas para la creación de texto

Vamos a partir de un nuevo archivo en este caso agregamos los elementos básicos:

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

Ahora insertamos en siguiente párrafo dentro de la etiqueta body:

La especie humana ha evolucionado de otras especies que no eran humanas. Para entender nuestra naturaleza, debemos conocer sus orígenes y su historia biológica. Esta historia ha sido reconstruida con la ayuda de muchas disciplinas científicas: la paleontología, la biogeografía, el estudio comparativo de los organismos vivos, la antropología y en épocas recientes, la biología molecular.

Para dar un par de saltos de línea dentro del párrafo usamos la etiqueta \<br\>

**Insertar otro subtitulo y otro párrafo.**

Lo hacemos con la etiqueta \<h2\> y con la etiqueta \<p\>. 

Ejemplo:

```
<h2>Capaces de entender</h2>
<p>	
  Los seres humanos actuales somos descendientes de los primeros Homo sapiens, cuyo nombre significa "hombre inteligente" u "hombre capaz de entender". Se sabe que ya hace 40 mil años, el Hombre de Cro-Magnon (cuyo nombre se debe al lugar donde fueron encontrados sus restos en Francia) usaba armas y herramientas hechas de piedras, huesos y cuernos, contaba con una organización social y vivía de la caza.
</p>
```

- Usar la etiqueta \<strong\>, \<b\>. Ambas etiquetas cambiaran a tipo de fuente **negrita.**
- Crear un tercer párrafo ahora con \<h3\>

```
<h3>La cultura</h3>
<p>
  Hemos hablado de los pasos más importantes de la evolución biológica de los seres humanos. Sin embargo, hay que añadir que también nos distinguen de nuestros antepasados directos diferencias no biológicas a las que podemos llamar culturales, y que son típicamente humanas, como la fabricación de herramientas, el lenguaje simbólico, el saber que nos vamos a morir algún día, una organización social basada en la división del trabajo, el desarrollo de una capacidad moral y el establecimiento de relaciones afectivas más profundas y variadas.
</p>
```


- Etiqueta \<s\>. Tachar texto.
- Etiqueta \<blockquote\>. Citar texto.
- Etiqueta \<hr/\>. Insertar o dibujar línea separadora.
- Etiqueta \<em\>\</em\>. Tipo de texto _cursiva._
- Etiqueta \<i\>\</i\>. Tipo de texto _cursiva_
- Insertar comentarios. \<!--Esto es un comentario en html--\> 

## Contenido multimedia

Volvemos a crear un archivo con los elementos básicos

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

**Insertar imagen ubicada en la misma carpeta**

Con el elemento o etiqueta **img** insertamos imágenes junto con el atributo src. Veamos el siguiente ejemplo:

```
<img src="gatito.jpeg">
```

**Insertar imagen ubicada en la otra carpeta**

Basta que al atributo src, le indiquemos cual es la ruta de la imagen. En el caso de que tengas la imagen contenida en esta carpeta como esta en el repositorio, escribiríamos:

```
<img src="imagenes/gatito2.jpeg">
```

**Usar el atributo alt**

Si por alguna razón no carga la imagen podemos usar el atributo alt para que en ausencia de la imagen aparezca un texto.

```
<img src="gatito2.jpeg" alt="Imagen de gatito2">
```

Si queremos que al pasar el cursor sobre la imagen, nos de información o el nombre de la imagen usamos el atributo **title.**

```
<img src="gatito.jpeg" title="Mi gatito">
```

Cambiar el alto y el ancho de las imágenes. Insertamos los atributos **widht** y **height**

```
<img src="gatito.jpeg" title="Mi gatito" width="400px" height="300">
```

**Insertar audio en la misma carpeta**

Para esta tarea ocupamos la etiqueta \<audio\> conjuntamente con el atributo src y el atributo controls que nos permitira manipular el archivo (pause, play)

```
<audio src="mecano.mp3" controls></audio></br>
```

**Insertar video**

```
<video src="gadgets.mp4" controls></video></br>
```

**Insertar audio en otra carpeta**

Ya hemos hecho este ejemplo con páginas y texto, ahora lo haremos con audio pero que este contenido dos carpetas hacia adelante.

```
<audio src="imagenes/audio/do_it.mp3" controls></audio></br>
```

***
**Nota:** ¿Sabrías por que ocupar esta ruta en carpetas contenidas, y no usar la ruta completa?
***

