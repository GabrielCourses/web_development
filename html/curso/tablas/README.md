![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/table_header.png)

# Creación de tablas

Una tabla es un arreglo de filas y columna, en esta sección aprenderemos a crear tablas.

Las filas son los registros u observaciones de nuestra tabla y las columna son las variables o campos de la tabla. Comúnmente se ocupa la primera fila de la tabla para indicar el nombre de los campos, aunque lo anterior puede ser configurado especificando si la tabla contiene cabeceras o no.

Para aprender a crear tablas vamos a copiar el siguiente código en un nuevo documento:

```
<!DOCTYPE html>
<html>
  <head>
    <title>Informática</title>
    <meta charset="UTF-8">
  </head>
  <body>
    <table border="1">
      <caption>Datos de becario</caption>

      <tr>
	<td>Número de control</td>
	<td>Nombre</td>
	<td>Edad</td>
	<td>Teléfono</td>
      </tr>
      <tr>
	<td>1000-1</td>
	<td>Juan López</td>
	<td>21</td>
	<td>5556565555</td>
      </tr>
      <tr>
	<td>1000-2</td>
	<td>Marilu Campos</td>
	<td>27</td>
	<td>5556565556</td>
      </tr>
      <tr>
	<td>1000-3</td>
	<td>Estefania Reyes</td>
	<td>19</td>
	<td>5556565550</td>
      </tr>
      <tr>
	<td>1000-4</td>
	<td>Gerardo Sánchez</td>
	<td>22</td>
	<td>5556565551</td>
      </tr>
      </table>
    </body>
</html>
```

Guardamos como: tabla.html

Abrimos el archivo en el navegador.

En el caso de la etiqueta <code>table</code> vamos a cambiar el atributo <code>border="5"</code>. Guardamos y recargamos en el browser.

Como puedes darte cuenta los elementos <code>tr</code> son las filas y dentro de ellos están los elementos <code>td</code> que corresponden a los valores de los campos.

Si quiero que la tabla este alineada al centro de la página, agrego el atributo <code>align</code> de la siguiente manera:

```
<table border="5" align="center">
```

De la misma manera, puedo elegir <code>right</code> o <code>left</code>. También como ya hemos usado anteriormente puedo cambiar el ancho de la tabla con el atributo <code>width</code>, como ejemplo agreguemos:

```
<table border="5" align="center" width="50%">
```

Donde <code>50%</code> se refiere al 50% del ancho de la pantalla.

Ahora, si quisiera alinear el contenido de la celda puedo usar el atributo <code>align</code>, como ejemplo, alineamos al centro las cabeceras, es decir, el nombre de los campos.

```
<tr>
<td align="center">Número de control</td>
<td align="center">Nombre</td>
<td align="center">Edad</td>
<td align="center">Teléfono</td>
</tr>
```

Guardamos y recargamos el navegador.