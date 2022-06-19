![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/lesson2.png)

# Lección 2: Uso de plantillas para las páginas HTML

Vamos aprender el **uso de plantillas para la generación de contenido HTML dinámico**. Pero antes de esto es necesario que conozcas cómo Flask asocia una URL a un determinado script o cómo envía una respuesta al navegador.

En la primera lección vimo como instalar Flask y hacerlo funcionar usando el servidor que viene con el propio framework. En este tutorial vamos a continuar con nuestro proyecto por donde lo dejamos. **Recuerda que el próposito es desarrollar un miniblog.**

Los objetivos de esta lección son los siguientes:

- Crear la página home de nuestro blog. En ella se listará todos los post de más reciente a más antiguo.
- Crear la página para visualizar un post. Se accederá a ella al hacer clic sobre el título de un post desde la página home.
- Diseñar una página desde la que crea o editar un post.

Dado que nos encontramos al inicio del tutorial sobre Flask, nuestro código no se integrará con ninguna base de datos ni crearemos los correspondientes formularios. El objetivo es ver cómo Flask maneja las peticiones del usuario y las plantillas HTML para generar contenido dinámico. En lugar de usar una base de datos, simularemos el listado de posts con una lista en memoria.

## Índice

- Routing
- Respuestas
- Renderizando una página HTML
- Plantillas
- Ficheros estáticos
- Creando nuestra plantilla para el miniblog

## Routing

En la lección 1 vimos de manera muy rápida cómo Flask asocia una URL con un método de nuestro código. Para ello, simplemente tenemos que añadir el docorador <code>route()</code> a la función que queramos ejecutar cuando se hace una petición a una determinada URL. En Flask, por convención, a las funciones que están asociadas a una URL se les llama «vistas».

### Creando la vista de la página home

Vamos a ello con nuestra página principal. La URL de esta página será <code>"/"</code> y, como te indiqué anteriormente, en ella se mostrará el listado de posts de nuestro blog. De momento, los posts se almacenarán en una lista en memoria.

Abrimos el fichero <code>run.py</code> que creamos en la lección anterior, borramos la función <code>hello_world</code> y añadimos el código a continuación:

```
post = []

@app.route("/")
def index():
    return "{} post".format(len(post))
```

¿Qué esta ocurriendo aquí? Primero hemos creado una variable llamada <code>posts</code>. Esta variable es una lista que almacenará los posts que vayamos creando. En segundo lugar hemos creado la función </code>index()</code>, que es la responsable de mostrar los posts de nuestro blog. Pero en esta primera aproximación lo único que hace es mostrar en el navegador el número de posts que contiene la variable <code>post</code>. Además, a la función se le ha añadido el decorador <code>route</code> junto con el paramentro <code>"/"</code>. Esto hará que cuando se acceda a la página principal, se ejecute la función <code>index()</code>.

Técnicamente **esto es lo fundamental que debes saber sobre cómo Flask asocia una URL a una función de nuestra aplicación.** Aunque apenas estamos iniciando.

### Creando la vista que muestra el detalle de un post

En una aplicación web no todas las páginas tienen URL definida de antemano, como es el caso de la página principal. Por ejemplo, en nuestro blog cada post tendrá una URL única que se generá dinámicamente. Sin embargo, no vamos a tener una vista por cada URL que se genere. Vamos a tener una única vista que se encargará de recoger un parámetro que identifique al post que queremos mostrar y, en base a dicho parámetro, recuperar el post para finalmente mostrarlo al usuario.

Para hacer esto, **a una URL le podemos añadir secciones variables o parametrizadas** con <code>\<param\></code>. La vista recibirá <code>\<param\></code> como un parámetro con ese mismo nombre. Opcionalmente se puede indicar un conversor (_converter_) para especificar el tipo de dicho parámetro así <code>\<converter:param\></code>.

Por defecto, en Flask existen los siguientes conversores:

- **string**: Es el conversor por defecto. Acepta cualquier cadena que no contenga el carácter <code>'/'</code>.
- **int**: Acepta números enteros positivos.
- **path**: Es como string pero acepta cadenas con el carácter <code>'/'</code>.
- **uuid**: Acepta cadenas con formato UUID.

También es posible añadir tus propios conversores, pero de momento solo lo mencionamos.

Veamos todo lo anterior en acción. **Vamos a crear una vista para mostrar un post a partir del slug del título del mismo**. Un slug es una de cadena de caracteres alfanuméricos (más el carácter '-'), sin espacios, tildes ni signos de puntuación. Más adelante veremos cómo generar el slug de un post. Por ahora nos quedamos con la idea de que el slug es un string que identifica a un post en concreto. La vista que vamos a definir tendrá el siguiente aspecto:

```
@app.route("/p/<string:slug>/")
def show_post(slug):
    return "Mostrando el post {}".format(slug)
```

En esta vista hemos definido el parámetro <code>slug</code> en la URL y dicho parámetro se toma como argumento de la función <code>
show_post(slug)</code>. De momento, lo único que hace esta función es mostrar al usuario la parte de la URL que está parametrizada. Vuelve a ejecutar <code>flask run</code> pero ahora en la línea del buscador escribe <code>localhost:5000/p/mi-primer-entrada/</code>. Debes obtener algo similar a la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/slug.png)


**Nota sobre acabar las URLs con el carácter <code>'/'</code> o no hacerlo**

Al definir una URL acabada con el carácter <code>'/'</code>, si el usuario accede a esa URL sin dicho carácter, Flask lo redirigirá a la URL acabada en '/'. En cambio, si la URL se define sin acabar en <code>'/'</code> y el usuario accede indicando la <code>'/'</code> al final, Flask dará un error HTTP 404.

### Creando la vista para crear/modificar un post

Hemos visto lo fundamental sobre routing con Flask. Ahora piensa en la lógica de crear y modificar un post. Prácticamente lo que hay que hacer en ambos casos es lo mismo: recuperar los datos de un formulario, crear un objeto post, asignarle los valores de los campos del formulario y guardar el objeto post. La única diferencia es que modificar un post supone recuperarlo previamente de la base de datos.

Es decir, que es una buena práctica usar una única vista que nos valga para ambos casos, ya que no estaremos repitiendo código. En estas situaciones, lo que se suele hacer es tener dos endpoints(URLs) distintos, uno para crear un post y otro modificarlo. Podrían ser <code>/admin/post/</code> y <code>/admin/post/\<post\_id\></code>, respectivamente. ¿Cómo hacemos para asociar dos URLs diferentes a una sola vista?. Simplemente añadiendo dos decoradorea a la misma función. En nuestro caso:

```
@app.route("/admin/post/")
@app.route("/admin/post/<int:post_id>/")
def post_form(post_id=None):
    return "post_form {}".format(post_id)
```

**Ten en cuenta que hemos asignado un valor por defecto al parámetro <code>post\_id</code> para el caso en que no se pase el mismo en la URL.**

### Formar URLs en nuestro código

Flask pone a nuestra disposición el método <code>url\_for()</code> para componer una URL a partir del nombre de la vista. Esta función acepta como parámetro el nombre de una vista y un número variable de argumentos clave-valor, cada uno de ellos asociado a una parte variable de la URL. Si se pasa un argumento cuyo nombre no se corresponda con un parámetro de la parte variable, se añade a la URL como parte de la query string (la sección de la URL que viene tras el carácter '?').

Veámoslo con un ejemplo:

```
>>> print(url_for("index"))
/
>>> print(url_for("show_post", slug="lesson-1", preview=True))
/p/lesson-1/?preview=True
```

Es recomendable usar el método <code>url_for</code> en lugar de codificar directamente la URL en el código por los siguientes motivos:

- Si se cambia una URL en cualquier momento, al no estar harcodeada, esta modificación no afectará a nuestro código.
- La función escapa caracteres especiales, como los espacios, por nosotros.
- Las rutas generadas son siempre absolutas, evitándose las rutas relativas.
- Si la aplicación se sitúa bajo un contexto (por ejemplo <code>/miniblog</code>), en lugar de la ruta raíz <code>/</code>, <code>url_for()</code> gestionará esta situación por nosotros.

## Respuestas

¿Por qué se muestra el texto que devolvemos en las funciones del apartado anterior como una página web?. Simplemente **Flask convierte el valor que devuelve una vista en un objeto «respuesta» (o response) por ti.**

En caso de que devolvamos un string(como ocurría en nuestros ejemplos), este string se devuelve como el cuerpo de la respuesta, con un código de estado 200 y con text/html como tipo mime.

Flask espera que el valor devuelto por una vista sea un objeto de tipo response. Si se devuelve un string, se aplica la lógica anterior. También se puede devolver una tupla con la forma <code>(response, status, headers)</code>. El valor de <code>status</code> sustituirá al código de estado por defecto, que es 200. Por su parte, <code>headers</code> puede ser una lista o un diccionario con cabeceras adicionales a devolver.

## Renderizando una página HTML

Todo esto está muy bien, pero sería muy tedioso codificar una página web completa como un string para ser devuelto por una vista. Para facilitarte la vida, Flask trae por defecto un motor de renderizado de de plantillas llamado <a href="https://jinja.palletsprojects.com/en/3.1.x/">Jinja2</a> que te ayudará a crear las páginas dinámicas de tu aplicación web.

Para renderizar una plantilla creada con Jinja2 simplemente hay que hacer uso del método <code>render_template()</code>. A este método debemos pasarle el nombre de nuestra plantilla y las variables necesarias para su renderizado como parámetros clave-valor.

Flask buscará las plantillas en el directorio <code>templetes</code> de nuestro poryecto. En el sistema de ficheros, este directorio se debe encontrar en el mismo nivel en el que hayamos definido nuestra aplicación. En nuestro caso, la aplicación se encuentra en el fichero <code>run.py</code>.

Es hora de crear este directorio y añadir las páginas <code>index.html</code>, <code>post_view.html</code> y <code>admin/post_form.html</code>. La estructura de nuestro proyecto quedaría del siguiente modo:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/directories.png)

Ahora modifiquemos el cuerpo de las vistas <code>index()</code>, <code>show_post()</code> y <code>post\_form()</code> para que muestren el resultado de renderizar las respectivas plantillas. Pero antes recuerda importar el método <code>render\_templates</code> del módelo flask: <code>from flask import render\_templetes</code>:

```
@app.route("/")
def index():
    return render_template("index.html", num_posts=len(posts))


@app.route("/p/<string:slug>/")
def show_post(slug):
    return render_template("post_view.html", slug_title=slug)


@app.route("/admin/post/")
@app.route("/admin/post/<int:post_id>/")
def post_form(post_id=None):
    return render_template("admin/post_form.html", post_id=post_id)
```

## Plantillas

Ya que hemos aprendido cómo renderizar una plantilla y dónde debe estar ubicada, tan solo nos falta modificar las plantillas que acabamos de crear para que muestren el mismo resultado que en la sección primera.

### index.html

```
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Tutorial Flask: Miniblog</title>
</head>
<body>
  {{ num_posts }} posts
</body>
</html>
```

### post_view.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>{{ slug_title }}</title>
</head>
<body>
  Mostrando el post {{ slug_title }}
</body>
</html>
```

### post_form.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>
    {% if post_id %}
      Modificando el post {{ post_id }}
    {% else %}
      Nuevo post
    {% endif %}
  </title>
</head>
<body>
{% if post_id %}
  Modificando el post {{ post_id }}
{% else %}
  Nuevo post
{% endif %}
</body>
</html>
```

Como podemos ver, el aspecto de estas páginas es similar a una página html estática con la excepción de <code>{{ num\_post}}</code> y <code>{{ slug\_title}}</code> y los caracteres <code>{%</code> y <code>%}</code>. Dentro de las llaves se usan los parámetros que se pasaron al método <code>render_template()</code>. El resultado de ello es que durante el renderizado se sustituirán las llaves por el valor de los parámetros. De este modo podemos generar contenido dinámico en nuestras páginas.

En definitiva, una plantilla Jinja2 no es más que un fichero que contiene datos estáticos junto con bloques pra generar contenido dinámico. El resultado de renderizar una plantilla es un documento html en el que los bloques de generación de contenido dinámico han sido procesados.



