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

Vamos iniciar con un archivo con los elementos básicos y agregamos también una línea de código con el elemento **form** con el cual mandamos ejecutamos el elemento formulario.

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

Y lo ejecutamos dentro de un navegador para verificar que todo este bien.

Ahora puedes notar que el elemento **form**, cuenta con 2 atributos, de momento no vamos a dar alguna explicación de que hacen estos atributos, ya que aún no hemos abordado el tema de PHP.

## El elemento input

Dentro de él elemento form empezamos llamando al elemento input el cual nos va ayudar con los campos de entrada, es decir, debemos entender que el elemento input tiene atributos para colocar, cajas de texto, checkbox, ratios, etc.

```
<!-- Destro de la etiqueta form-->
Ingresa tu nombre completo:
<input type="text" name="name" value="Default text" size="20">
```

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/form_atributes.png)

En este caso definimos un texto por defecto, si no lo queremos hacer basta con dejar comillas dobles

Insertemos otra caja de texto, en este caso el correo electrónico:

```
Ingresa tu correo:
<input type="text" name="correo" value="" size="25">
```

Insertemos otro tipo de entrada, una **constraseña:**

```
Ingresa tu contraseña:
<input type="password" name="pass" value="" size="20">	
```

**type=checkbox**

```
Selecciona el curso de tu interés: <br>
<input type="radio" name="oop">Programación Orientada a Objetos<br>
<input type="radio" name="datascience">Ciencia de datos<br>
<input type="radio" name="ml">Machine Learning<br>
<input type="radio" name="data">Data Engineering<br>
```

Guarda y recarga en el navegador, enseguida agregamos el atributo type="checkbox"

```
Selecciona el curso de tu interés: <br>
<input type="checkbox" name="oop">Programación Orientada a Objetos<br>
<input type="checkbox" name="datascience">Ciencia de datos<br>
<input type="checkbox" name="ml">Machine Learning<br>
<input type="checkbox" name="data">Data Engineering<br>
```

Guardamos y cerramos

# Formularios. Parte II.  

Creamos un archivo html con los elementos básicos includido la etiqueta form:

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

Comenzamos ingresando una caja de texto:

```
<!-- Dentro de la etiqueta form insertamos -->
Ingresa tu nombre:
<input type="text" name="nombre" size="30"><br>
```

**El elemento select**

Una tarea común en los formularios es validar la información de entrada, es decir, restringir la entrada del campo a solo unas opciones. Lo anterior lo conseguimos en html con el elemento **select.**

```
Selecciona tu deporte favorito:
<select name="sport">
	<option value="1">Beisbol</option>
	<option value="2">Futbol soccer</option>
	<option value="3">Baloncesto</option>
	<option value="4">Voleibol</option>
</select>
```

**type=submit**

Como ya hemos comentado, conjuntamente con html trabajan otros lenguajes para darle diseño y funcionalidad, en este caso insertaremos un botón que ejecutara una acción, aunque por si sola no terminará de realizar la tarea, es decir, continuamos con la parte de construir la estructura de nuestra página,

```
<input type="submit" value="Envío de datos">
```

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

En este caso basta con abrir el archivo en un navegador y darnos cuenta como con el elemento **optgroup** podemos agrupar la lista desplegable. 

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

Hasta ahora hemos visto como elegir una opción dentro de una lista de opciones usando el elemento **select**, pero que ocurre si queremos elegir más de una opción.

Dentro de la etiqueta body escribimos el siguiente código:

```
    <form action="registrodedatos.php" method="post">
      Seleccione o varios platillos(Oprima la tecla Ctrl para elegir más de una opción)<br>
      <select name="platillo[]" size="6" multiple>
		<option value="1">Pozole</option>
		<option value="2">Birria</option>
		<option value="3">Tacos</option>
		<option value="4">Barbacoa</option>
		<option value="5">Tostadas</option>
		<option value="6">Chiles rellenos</option>
		<option value="7">Pollo</option>
      </select><br>

      <input type="submit" value="Enviar">
    </form>
```

