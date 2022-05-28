![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/html/image/formulario.png)

# Formularios. Parte I.

Ejemplo de un formulario, objetos en las páginas web que nos ayudan a acopiar información de los usuarios, como datos personales, cuestionarios, compras, solicitudes, etc. Dicha información va ser enviada al servidor.

¿Que objetos tiene un formulario?

- campos de texto
- contraseñas
- checkbox
- botones

**Nota:** Con html solo vamos a crear la interfaz del formulario, no se puede procesar la información, para ello necesitamos un otro lenguaje el cual se ejecute dentro del servidor como por ejemplo **PHP.**

Vamos iniciar con un archivo con los elementos básicos y agregamos tambien una línea de código con el elemento **form** con el cual mandamos llamar al objeto formulario.

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
	
<html>
```

Guardamos el archivo como: miformulario.html

Y lo ejecutamos en dentro de un navegador para verificar que todo este bien.

Ahora puedes notar que el elemento **form**, cuenta con 2 atributos, de momento no vamos a dar alguna definición de que hace estos atributos, ya que aún no hemos abordado el tema de PHP.

## El elemento input

Dentro de el elemento form empezamos llamando al elemento input el cual nos va ayudar con los campos de entrada, es decir, debemos entender que el elemento input tiene atributos para colocar, cajas de texto, checkbox, ratios, etc.

```
<!-- Destro de la etiqueta form-->
Ingresa tu nombre completo:
<input type="text" name="name" value="Default text" size="20">
```

En este caso definimos un texto por defecto, si no lo queremos hacer basta con dejar comillas dobles

Insertemos otra caja de texto, en este caso el correo electronico:

```
Ingresa tu correo:
<input type="text" name="correo" value="" size="25">
```

Insertemos otro tipo de entrada, una **constraseña:**

```
Ingresa tu contraseña:
<input type="password" name="pass" value="" size="20">	
```

**type = checkbox**

```
Selecciona el curso de tu interés: <br>
<input type="radio" name="oop">Programación Orientada a Objetos<br>
<input type="radio" name="datascience">Ciencia de datos<br>
<input type="radio" name="ml">Machine Learning<br>
<input type="radio" name="data">Data Engineering<br>
```

El tipo usado fue radio, ahora si radio lo cambio por checkbox:

```
Selecciona el curso de tu interés: <br>
<input type="checkbox" name="oop">Programación Orientada a Objetos<br>
<input type="checkbox" name="datascience">Ciencia de datos<br>
<input type="checkbox" name="ml">Machine Learning<br>
<input type="checkbox" name="data">Data Engineering<br>
```

Guardamos y cerramos

# Formularios. Parte II.  

Vamos a volver a crear un archivo html con los elementos básicos:

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

Guardamos como: formulario2.html

Y cargamos en el navegador.

Comenzamos ingresando una caja de texto:

```
<!-- Dentro de la etiqueta form insertamos -->
Ingresa tu nombre:
<input type="text" name="nombre" size="30"><br>
```

**El elemento select**

```
Selecciona tu deporte favorito:
<select name="sport">
	<option value="1">Beisbol</option>
	<option value="2">Futbol soccer</option>
	<option value="3">Baloncesto</option>
	<option value="4">Voleibol</option>
	
</select>
```

**type submit**

```
<input type="submit" value="Envío de datos">
```

## Agrupar opciones

Creamos otro archivo con los elementos ya vistos

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
	  <option value="9">Colombia</option>
	  <br>
	</optgroup>
      </select>
      <br>    
      <input type="submit" value="Enviar">
    </form>

  </body>

</html>
```

Guardamos como: option.html

Abrimos en un browser y cerramos.

# Formularios. Parte III.

**Agregar más de una opción**

Creamos un archivo html con los elementos básicos que venimos haciendo:

```



```

