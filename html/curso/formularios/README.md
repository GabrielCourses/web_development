![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/formulario.png)

# Formularios. Parte I.

Los formulario son elementos de html que nos ayudan a acopiar información de los usuarios, como datos personales, encuestas de satisfacción, compras en línea, etc. Dicha información va ser enviada a algún servidor.

¿Que atributos tiene un formulario?

- campos de texto
- contraseñas
- checkbox
- botones

***
**Nota:** Con html solo vamos a crear la interfaz del formulario, no se puede procesar la información, para ello necesitamos otro lenguaje el cual se ejecute dentro del servidor como por ejemplo **PHP.**
***

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/form_atributes.png)

Vamos crear un archivo con los elementos básicos y agregamos también una línea de código con el elemento <code>\<form\></code> con el cual ejecutamos el elemento formulario.

```
<!DOCTYPE html>
<html>

  <head>
    <title>Mi formulario</title>
    <meta charset="UTF-8">
  </head>
	
  <body>
    <form action="registrodedatos.php" method="post">

    </form>  
  </body>

</html>
```

Guardamos el archivo como: miformulario.html

Lo ejecutamos dentro de un navegador para verificar que todo este bien.

Ahora puedes notar que el elemento <code>form</code>, cuenta con 2 atributos <code>action</code> y <code>method</code>, de momento no vamos a dar alguna explicación de que hacen estos atributos, ya que aún no hemos abordado el tema de PHP.

## El elemento input

Dentro de él elemento <code>\<form\></code> empezamos llamando al elemento <code>\<input\></code> el cual nos va ayudar con los campos de entrada, es decir, debemos entender que el elemento <code>input</code> tiene atributos para colocar, cajas de texto, checkbox, ratios, etc.

Empezamos colocando un tipo de entrada del tipo <code>"text"</code>.

```
Ingresa tu nombre completo:
<input type="text" name="name" value="Default text" size="20"><br><br>
```

En este caso definimos un texto por defecto, si no lo queremos hacer basta con dejar comillas dobles <code>""</code>.

Insertemas otra caja de texto, en este caso de tipo <code>"email"</code>:

```
Ingresa tu correo:
<input type="email" name="correo" value="" size="25">
```

Insertamos otro caja de texto de tipo <code>"password"</code>

```
Ingresa tu contraseña:
<input type="password" name="pass" value="" size="20"><br><br>
```

Seguido de las cajas de texto ya capturadas, ahora usamos el atributo <code>type="radio"</code>:

```
Selecciona el curso de tu interés: <br>
<input type="radio" name="oop">Programación Orientada a Objetos<br>
<input type="radio" name="datascience">Ciencia de datos<br>
<input type="radio" name="ml">Machine Learning<br>
<input type="radio" name="data">Data Engineering<br>
```

Guarda y recarga en el navegador, enseguida agregamos el atributo <code>type="checkbox"</code>

```
Selecciona el curso de tu interés: <br>
<input type="checkbox" name="oop">Programación Orientada a Objetos<br>
<input type="checkbox" name="datascience">Ciencia de datos<br>
<input type="checkbox" name="ml">Machine Learning<br>
<input type="checkbox" name="data">Data Engineering<br>
```

Guardamos y cerramos

# Formularios. Parte II.  

Creamos un archivo html con los elementos básicos incluido la etiqueta <code>form</code>:

```
<!DOCTYPE html>
<html>
	
  <head>
    <title>Curso Formularios</title>
    <meta charset="UTF-8">
  </head>
	
  <body>
    <form action="registrodedatos.php" method="post">
    
    </form>
  </body>
	
</html>
```

- Guardamos como: formulario2.html
- Cargamos en el navegador.

Comenzamos ingresando una caja de texto, en seguida del elemento <code>form</code>:

```
Ingresa tu nombre:
<input type="text" name="nombre" size="30"><br>
```

**El elemento** <code>select</code>

Una tarea común en los formularios es validar la información de entrada, es decir, restringir la entrada del campo a solo unas cuantas opciones. Lo anterior lo conseguimos en html con el elemento <coe>select</code>.

```
Selecciona tu deporte favorito:
<select name="sport">
	<option value="1">Beisbol</option>
	<option value="2">Futbol soccer</option>
	<option value="3">Baloncesto</option>
	<option value="4">Voleibol</option>
</select>
```

**El atributo** <code>type="submit"</code>

Como ya hemos comentado, conjuntamente con html trabajan otros lenguajes para darle diseño y funcionalidad, en este caso insertaremos un botón que ejecutara una acción aunque por si sola no realizará aún la tarea, es decir, de momento continuamos con la parte de construir la estructura de nuestra página.

En seguida del cierre de la etiqueta <code>select</code> insertamos la siguiente línea de código

```
<input type="submit" value="Envío de datos">
```

Guardamos, cargamos en el navegador y cerramos.

## Agrupar opciones, etiqueta \<optgroup\>

Vamos a crear un nuevo archivo con el siguiente código:

```
<!DOCTYPE html>
<html>
  
  <head>
    <title>Options</title>
    <meta charset="UTF-8">
  </head>
  
  <body>
    <form action="registrodedatos.php" method="post">
      Selecciona un país:
      <select name="paises">
	    <optgroup label="Norteamerica">
	      <option value="1">Estados Unidos</option>
	      <option value="2">Canadá</option>
	      <option value="3">México</option>
		</optgroup>

		<optgroup label="Sudamerica">
		  <option value="7">Brasil</option>
		  <option value="8">Argentina</option>
		  <option value="9">Colombia</option><br>
		</optgroup>
      </select><br>
          
      <input type="submit" value="Enviar">
    </form>

  </body>

</html>
```

Guardamos como: option.html

En este caso basta con abrir el archivo en un navegador y darnos cuenta como con el elemento <code>optgroup</code> podemos agrupar la lista desplegable. Cerramos el archivo.

# Formularios. Parte III.

**Agregar más de una opción**

Creamos un archivo html con los elementos básicos que venimos haciendo:

```
<!DOCTYPE html>
<html>
	
  <head>
    <title>Selección múltiple</title>
    <meta charset="UTF-8">
  </head>
	
  <body>
    <form action="registrodedatos.php" method="post">
    
    </form>
  </body>
	
</html>
```

Guardamos el archivo como: multiple.html

Hasta ahora hemos visto como elegir una opción dentro de una lista de opciones usando el elemento <code>select</code>, pero que ocurre si queremos elegir más de una opción.

Dentro de la etiqueta <code>body</code>, en seguida del elemento <code>form</code> escribimos el siguiente código:

```
      Seleccione uno o varios platillos(Oprima la tecla Ctrl para elegir más de una opción):<br>
      <select name="platillo[]" size="6" multiple>
		<option value="1">Pozole</option>
		<option value="2">Birria</option>
		<option value="3">Tacos</option>
		<option value="4">Barbacoa</option>
		<option value="5">Tostadas</option>
		<option value="6">Chiles rellenos</option>
		<option value="7">Pollo</option>
		<option value="8">Enchiladas</option>
      </select><br>

      <input type="submit" value="Enviar">
```

En el caso del atributo <code>size</code> lo que elijo es cuantos elementos quiero mostrar en la interfaz.

El atributo <code>multiple</code>es el que me permite escoger mas de una opción.

En el caso del elemento <code>input</code> tiene dos atributos, el atributo <code>type="submit"</code> que nos permite enviar la información a un servidor y el atributo <code>value="Enviar"</code>, en el caso de <code>"Enviar"</code> podemos cambiarlo y eso sera lo que se muestre en la página. Pero también puedo usar una imagen.

Es decir, vamos a sustituir la línea de código:

```
<input type="submit" value="Enviar">
```

Para sustituir el botón de tipo <code>"submit"</code> por imágenes vamos a descargar de la carpeta **ejercicios** en la misma ubicación donde tienes el archivo multiple.html un par de imagenes: send.png y delete.png

Y en seguida de la etiqueta de cierre <code>select</code> escribimos:

```
<button type="submit"><img src="send.png" alt="envio" width="100" height="40"></button><br><br>
<button type="reset"><img src="delete.png" alt="borrar" width="100" height="40"></botton>
```

Tu código tiene que tener un aspecto similar al siguiente:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/code_botton.png)

Y tu navegador debe ser similar a este:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/browser_botton.png)

Guardamos, cargamos y cerramos.

# Formularios. Parte IV.

Iniciamos creando un archivo html con los elementos básicos:

```
<!DOCTYPE html>
<html>
	
  <head>
    <title>Selección múltiple</title>
    <meta charset="UTF-8">
  </head>
	
  <body>
    <form action="registradedatos.php" method="post">
    
    </form>
  </body>
	
</html>
```

Guardamos como: controles_agrup.html

Para empezar a agrupar controles usaremos la etiqueta <code>\<fieldset\>\</fieldset></code> la cual capturamos dentro de la etiqueta <code>form</code>:

```
<fieldset></fieldset>
<fieldset></fieldset>
```

Dentro de la primera etiqueta <code>fieldset</code> insertamos:

```
<legend>Datos personales</legend>
```

Dentro de la segunda etiqueta <code>fieldset</code> escribimos:

```
<legend>Datos de conexión</legend>
```

Guardamos y recargamos. Ahora dentro de la primera etiqueta <code>legend</code> escribimos:

```
Nombre(s):
<input type="text" name="name" size="20"><br><br>
Apellido paterno:
<input type="text" name="last_name" size="20">
Apellido materno:
<input type="text" name="second_name" size="20"><br>
```

Tu código y tu navegador deben tener un aspecto similar a la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/fieldset.png)
