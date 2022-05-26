![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/curso.png)

# Primeras etiquetas

Ahora que ya sabemos como crear y cargar nuestro primer ejemplo html vamos aprender sobre las primeras etiquetas en HTML. Para esto nuevamente iniciamos con el archivo ejercicio1.html guardando como index.html y el archivo estilo.css

### La etiqueta \<p\>

Antes de comenzar con las nuevas etiquetas, editamos el archivo. En esta ocasión solo necesitamos un encabezado dentro del body y continuamos insertando el siguiente parrafo con la etiqueta \<p\>

HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la World Wide Web, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014. 

Es decir el código tiene que tener el siguiente aspecto:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/p.png)

**Colocar texto en negritas**

Vamos a usar la etiqueta \<b\> para poner texto en negritas. En el párrafo anterior vamos a colocársela a las palabras World Wide Web:

HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la \<b\>World Wide Web\</b\>, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014. 

**Comando 'Crtl + May + i' para el navegador.**

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/tools_browser.png)

**Saltos de línea**

Para dar saltos de línea dentro de nuestro párrafo ocupamos la etiqueta \<br\>

HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la \<b\>World Wide Web\</b\>, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014. 
\<br\>Este es un salto de línea\<br\>.

Guardamos y cerramos.

## Enlaces

Los enlaces o vínculos se crean con la etiqueta \<a\>. Para esta parte vamos a crear otro archivo html. Partimos nuevamente del ejercicio1.html que tiene la siguiente estructura:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/ejercicio1.png)

Le damos un guardar como: new_page.html

Comenzamos eliminando h2, h3 y la línea de comando que enlaza nuestro archivo html con estilo.css, seguido cambiamos el \<title\> a CDMX. Para h1 lo cambiamos a Clases a distancia. Cuando recarguemos el navegador debemos de visualizar lo siguiente:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/HTML/image/cdmx.png)

**Elemento \<a\> junto con el atributo href**

Insertamos la etiqueta \<a\> una línea después de \<h1\> junto con el atributo href, al cual le vamos asignar el enlace a donde queremos que nos envíe el vinculo, para este ejemplo vamos ocupar uno de nuestros archivos html en el cual ya trabajamos.

En el archivo index.htlm insertamos después de la línea h1

```
<a href = "new_page.html">Página nueva</a>
```

Y también hacemos lo mismos con el nuestro archivo new_page.html

```
<a href = "index.html">Página indice</a>
```

En el archivo new_page.htlm seguido de nuestro enlace. Colocamos un párrafo que diga 

```
<p>Welcome to <b>New page</b>
```

Ahora podemos ir de una a otra página, aunque notemos que para el argumento href basto con poner el nombre del archivo. Esto es por que los dos archivos se encuentran en la misma carpeta.

### Enlaces entre carpetas distintas

1. Dentro de la carpeta ficheros, voy a crear una nueva carpeta llamada **directorio2**.
2. Copio el archivo new_page.html a directorio2
3. Cambio el nombre de new\_page.html a other\_page.html

Abrimos el archivo index.html y en la línea con la etiqueta \<a href = ""\> colocamos:

```
<a href="directorio2/other_page.html">Otra página</a>
```

De index.html puedo llegar a other_page.html. ¿Ahora como hago para de other\_page.html enlazar con index.html. Tengo que modificar la etiqueta \<a href = ""\> de la siguiente manera:

```
<a href="../index.html">Página indice</a>
```

Guardamos y cerramos.

## Enlaces a otras páginas de internet

Abrimos nuestra archivo index.html. Vamos insertar un enlace al video de YouTube donde se encuentra tu tarea1, no olvides incluir el protocolo https. 

Después del primer vinculo escribimos:

```
<a href = "https://www.youtube.com/watch?v=oY-rbawd3oQ&t=24s">Tarea 1 </a>
``` 

Notas que el par de vinculos estan en una misma línea en el navegador, para corregirlo ponemos un salto de línea \<br\> después del primer enlance.

## Abrir enlaces en una nueva pestaña

Con nuestro mismo archivo index.html vamos agregar otro atributo al elemento \<a\> llamado **target**. Ahora vamos a enlazar a la página del colegio.

```
<a href = "http://cdmx.conalep.edu.mx/tlalpan1/inicio" target = "_PLANK">Plantel I</a>
```