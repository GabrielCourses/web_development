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

