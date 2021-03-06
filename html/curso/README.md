![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/curso.png)

# Primeras etiquetas

Ahora que ya sabemos como crear y cargar nuestro primer ejemplo html vamos aprender sobre las primeras etiquetas en HTML. Para esto partimos del archivo **ejercicio1.html** ubicado en la carpeta **ficheros** y le damos un guardar como: **index.html** 

También conservamos el archivo **estilo.css** que habíamos creado anteriormente.

### La etiqueta \<p\>

Antes de comenzar con las nuevas etiquetas, editamos el archivo. En esta ocasión solo necesitamos un encabezado dentro del body, es decir, eliminamos <code>\<h2\></code>, <code>\<h3\></code>, finalmente enseguida de <code>\<h1\></code> insertamos el siguiente párrafo con la etiqueta <code>\<p\></code>.

```
<p>HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la World Wide Web, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014.</p>
```

Es decir el código tiene que tener el siguiente aspecto:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/p.png)

**Colocar texto en negritas**

Vamos a usar la etiqueta <code>\<b\></code> para poner texto en negritas. En el párrafo anterior vamos a colocársela a las palabras World Wide Web. abriendo y cerrando la etiqueta:

```
HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la <b>World Wide Web</b>, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014. 
```

**Comando 'Crtl + May + i' para el navegador.**

Abrimos la ventana 'Herramientas de desarrollador' y al dar click en el menú inspector podemos ver reflejado las diferentes cajas de nuestras etiquetas, esto es para hacer énfasis en que con html estamos dando la estructura a la página.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/tools_browser.png)

**Saltos de línea**

Para dar saltos de línea dentro de nuestro párrafo ocupamos la etiqueta <code>\<br\></code>.

```
HTML 5 (HyperText Markup Language, versión 5) es la quinta revisión importante del lenguaje básico de la <b>World Wide Web</b>, HTML. HTML5 específica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML 5 que deberá servirse con sintaxis XML (application/xhtml+xml).1​2​ Esta es la primera vez que HTML y XHTML se han desarrollado en paralelo. La versión definitiva de la quinta revisión del estándar se publicó en octubre de 2014.<br>Este es un salto de línea.
```

Guardamos y cerramos.

## Enlaces

Los enlaces o vínculos se crean con la etiqueta <code>\<a\></code>. Para esta parte vamos a crear otro archivo html. Partimos nuevamente del ejercicio1.html que tiene la siguiente estructura:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/ejercicio1.png)

Guardamos como: new_page.html

Comenzamos eliminando <code>h2</code>, <code>h3</code> y la línea de comando que enlaza nuestro archivo html con estilo.css, seguido cambiamos el <code>\<title\></code> a CDMX. Para <code>\<h1\></code> lo cambiamos a Clases a distancia. Cuando recarguemos el navegador debemos de visualizar lo siguiente:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/cdmx.png)

### Elemento \<a\> junto con el atributo href

Ocuparemos el archivo index.html que creamos anteriormente.

En index.html insertamos la etiqueta <code>\<a\></code> después de <code>\<h1\></code> junto con el atributo <code>href</code>, al cual le vamos asignar el enlace a donde queremos que nos envíe el vinculo. Lo que queda entre las etiquetas de apertura y cierre es lo que queremos mostrar como enlace en nuestra página.

```
<a href="new_page.html">Página nueva</a>
```

Y también hacemos lo mismos con el nuestro archivo: new_page.html

```
<a href="index.html">Página indice</a>
```

En el archivo new_page.html seguido de nuestro enlace. Colocamos un párrafo que diga 

```
    <p>
      Welcome to <b>New page</b>
    </p>
```

Ahora podemos ir de una a otra página, aunque notemos que para el argumento <code>href</code> basto con poner el nombre del archivo. Esto es por que los dos archivos se encuentran en la misma carpeta.

### Enlaces entre carpetas distintas

1. Dentro de la carpeta ficheros, voy a crear una nueva carpeta llamada **directorio2**.
2. Copio el archivo new_page.html a directorio2
3. **Cambio el nombre de new\_page.html a other\_page.html**

Abrimos el archivo index.html y en la línea con la etiqueta <code>\<a href=" "\></code> colocamos:

```
<a href="directorio2/other_page.html">Otra página</a>
```

De index.html puedo llegar a other_page.html. ¿Ahora como hago para de other\_page.html enlazar con index.html. Tengo que modificar la etiqueta <code>\<a href=" "\></code> de la siguiente manera:

```
<a href="../index.html">Página indice</a>
```

Guardamos y cerramos.

## Enlaces a otras páginas de internet

Abrimos nuestra archivo index.html. Vamos insertar un enlace al video de YouTube donde se encuentra tu tarea1, no olvides incluir el protocolo https. 

Después del primer vinculo escribimos:

```
<a href="https://www.youtube.com/watch?v=oY-rbawd3oQ&t=24s">Tarea 1</a>
``` 

Notas que el par de vínculos están en una misma línea en el navegador, para corregirlo ponemos un salto de línea <code>\<br\></code> después del primer enlace.

## Abrir enlaces en una nueva pestaña

Con nuestro mismo archivo index.html vamos agregar otro atributo al elemento <code>\<a\></code> llamado <code>target</code>. Ahora vamos a enlazar a la página del colegio.

```
<a href="http://cdmx.conalep.edu.mx/tlalpan1/inicio" target="_PLANK">Plantel I</a>
```
