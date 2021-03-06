![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/leccion3.png)

# Lección 3: Uso de formularios en Flask

Mostraremos **cómo integrar formularios web en una aplicación Flask.** Los formularios son una parte muy importante de cualquier aplicación. A través de los formularios los usuarios pueden interactuar con la aplicación enviando cualquier tipo de información al servidor. Por ejemplo, gracias a ellos, un usuario se puede autenticar en una web, puede realizar una reservación o puede añadir un producto al carrito de compra.

Crearemos los siguientes formularios:

- Un formulario para que los usuarios invitados se puedan registrar en el blog.
- Un formulario para que el administrador pueda crear nuevas entradas en el blog.

## Índice

1. Normalmente los formularios se envían en el cuerpo de la petición
2. Accediendo a los datos de una petición en Flask
3. Procesando los formularios al desnudo
4. Manejando los formularios con Flask-WTF

## Normalmente los formularios se envían en el cuerpo de la petición

El protocolo HTTP define una serie de métodos de petición, conocidos como  «verbos HTTP», para indicar la acción que se desea realizar sobre un recurso determinado. Cada uno de estos verbos tiene una semántica diferente, siendo los más comunes los métodos GET y POST.

**GET debe emplearse para solicitar un recurso,** por lo tanto, las peticiones realizadas con este método solo deben recuperar datos (y no modificarlos).

En cambio **POST se utiliza para enviar una entidad a un recurso específico, de manera que se envían datos al servidor donde son procesados.** Es por ello que, por regla general, siempre que necesitemos enviar datos a un servidor para ser manipulados lo haremos a través de método POST (esto es una simplificación de por qué enviar los datos usando POST).

### El formulario de registro de usuario

Vamos a comenzar por implementar el formulario de registro de usuarios.

Para ello, lo primero que vamos a hacer es crear una nueva plantilla en el directorio <code>templates</code>. Llamaremos a esta plantilla <code>signup_form.html</code> y su contenido será el siguiente:

```
{% extends "base_template.html" %}

{% block title %}Registro de usuarios{% endblock %}

{% block content %}
    <form action="" method="post">
      <label for="name">Nombre: </label>
      <input type="text" id="name" name="name"><br>
      <label for="email">Email: </label>
      <input type="text" id="email" name="email"><br>
      <label for="password">Contraseña: </label>
      <input type="password" id="password" name="password"><br>
      <input type="submit" id="send-signup" name="signup" value="Registrar">
    </form>
{% endblock %}
```

Del código anterior destacamos tres cosas:

- La plantilla hereda de la plantilla base de nuestro proyecto.
- Para crear un formulario en HTML se usa la etiqueta <code>form</code>. En el atributo <code>action</code> se undica la URL a la que se enviarán los datos del formulario. Si este campo se deja vacío la URL será la misma desde ka que se descargó el recurso. En el atributo <code>method</code> indicamos el método a usar al enviar el formulario. En este caso <code>POST</code>, como ya se comento.
- Para procesar posteriormente los campos del formulario, se debe indicar el nombre con el que los identificará el servidor a través del atributo <code>name</code>.

Lo siguiente que haremos para mostrar el formulario y procesarlo será añadir una nueva vista al final del fichero <code>run.py</code> que estará asociada a la URL <code>/signup/</code>:

```
@app.route("/signup/")
def show_signup_form():
    return render_template("signup_form.html")
```

Esta vista lo único que hace es mostrar la plantilla que contiene el formulario.

Si accedemos a la dirección <code>http://localhost:5000/signup/</code>, veremos el formulario en el navegodor:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/form.png)

Si intentamos enviar el formulario pulsando sobre el botón Registrar, nos encontramos con el siguiente error:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/submit.png)

¿Por qué? Esto es así en **Flask, por defecto, cualquier vista solo responde ante peticiones GET**. Si queremos responder ante otro tipo de peticiones, debemos indicarlo en el parámetro <code>methods</code> del decorador <code>route</code>:

```
@app.route("/signup/", methods=["GET", "POST"])
def show_signup_form():
   return render_template("signup_form.html")
```

**Ahora nuestra vista acepta peticiones <code>POST</code>**. No obstante, por el momento, en cualquier de los dos casos siempre se mostrará el formulario de registro.

## Accediendo a los datos de un petición en Flask

Antes de seguir con una de las partes más importantes de este tutorial, procesar los datos del formulario para su manipulación, quiero introducirte el objeto <code>request</code> de _Flask_.

Básicamente, el objeto <code>request</code> **contiene toda la información que el cliente (por ejemplo el navegador web) envía al servidor**, en nuestro caso, nuestra aplicación Flask. Entre esta información se encuentran las cabeceras HTTP, los parámetros de la URL, la codificación preferida y, como no, los datos se envían a través de un formulario.

Imaginemos que tenemos la siguiente URL en nuestro blog <code>/?page=1&list=10</code>.Como vimos, la URL <code>/</code> del miniblog listaba todos los post. Los parámetros <code>page</code> y <code>list</code> los podríamos utilizar para paginar el listado, de manera que en este caso estamos pidiendo la primera página y los primeros diez post. ¿Cómo procesamos esto en nuestra vista? Accediendo al atributo <code>args</code> del objeto <code>request</code> del siguiente modo:

```
from flask import request

@app.route("/")
def index():
    page=request.args.get('page', 1)
    list=request.args.get('list', 20)
    ...
```

**Los campos enviados a través de un formulario se acceden por medio del atributo <code>form</code> del objeto <code>request</code>.**

## Procesando los formularios al desnudo

Continuamos, ahora si, procesando los datos enviados a través del formulario de registro.

***
Todavía los datos que obtengamos de los formularios no serán guardados en ningún sistema persistente, como puede ser una base de datos. Esto lo veremos en la Lección 5, Añadiendo una base de datos: SQLAlchemy.

Vamos a modificar la vista <code>show\_signup\_form()</code> como indico a continuación (recuerda importar el objeto <code>request</code> del módulo <code>flask</code>:

```
from flask import render_template, request, redirect, url_for

@app.route("/signup/", methods=["GET","POST"])
def show_signup_form():
    if request method == 'POST':
        name = request.form['name']
        email = request.form['email']
        password = request.form['password']

        next = request.args.get('next', None)
        if next:
            return redirect(next)
        return redirect(url_for('index'))
    return render_template("signup_form.html")
```

¿Qué destacaríamos del código anterior?

- La primera línea de código de la vista <code>show\_signup\_form()</code> accede al atributo <code>method</code> del objeto <code>request</code>. Esta nos permite identificar si el cliente ha enviado los datos del formulario (<code>POST</code>) o, por el contrario, quiere mostrar el formulario del registro (<code>GET</code>).
- Si se ha enviado el formulario, se recupera cada uno de los campos del mismo por medio del diccionario <code>form</code> del objeto <code>request</code>. Recuerda que el nombre de los campos es aquel que indicamos con el atributo <code>name</code> en la plantilla del formulario de registro.
- Luego comprobaremos si se pasó por la URL el parámetro <code>next</code>. Este parámetro lo usaremos para redirigir al usuario a la página que se indica en el mismo. Si no se especifica, simplemente lo redirigimos a al página de inicio.
- En caso de que no se haya enviado el formulario, se devuelve como respuesta la página que muestra el formulario de registro.  
- Siempre que se procesa un formulario correctamente, **es una buena práctica hacer un redirect para evitar duplicados de datos** si el usuario recarga la página o hace clic en el botón _atrás_ del navegador.

Como vemos, el procesamiento del formulario es muy sencillo y, en la mayoría de los casos, seguirá el patrón definido aquí. Sin embargo, **hemos dejado muchos cabos sueltos.** Por ejemplo: **¿qué debe ocurrir si un usuario no introduce su nombre? ¿Y si el email no es en realidad un email?** Ante estas situaciones **debemos validar siempre los campos del realidad un email?** Ante estas situaciones **debemos validar siempre los campos del formulario** y, en caso de detectar algún error, se lo debemos indicar al usuario.

Como puedes comprobar, las cosas se complica y el código de nuestra vista se «ensuciaría» añadiendo todas la validaciones necesarias.

Nuestra solución se llama _**WTForms**. Concretamente Flask-WTF. **Flask-WTF es una extensión de Flask** basada en <a href="https://wtforms.readthedocs.io/en/stable/">WTForms</a> **que nos ayudará con el manejo de formularios en nuestra aplicación.** Las extensiones permiten ampliar las funcionalidades base que trae por defecto Flask. Existen muchas de ellas y son de gran utilidad, por ejemplo, para manejo de base de datos SQL, para la internacionalización o para la creación de APIs.

## Manejando los formularios con Flask-WFT

Lo primero que hay que hacer es una aplicación Flask antes de usar cualquier extensión es instalarla en el sistema, en nuestro caso, en el entorno Python del proyecto.

Para instalar la extensión Flask-WFT, «activa» el entorno y ejecuta en la terminal:

```
pip install Flask-WTF
pip install email-validator
```

Una vez instalada, debemos hacer una serie de cambios en el proyecto. Lo veremos a continuación paso a paso.

### Formulario de registro usando Flask-WTF

Al usar Flask-WTF, todo formulario se representa a través de una clase. Esta clase hereda del objeto <code>FlaskForm</code> y en ellas se definen los campos del formulario como variables de clase.

#### SignupForm

Vamos a crear el formulario de registro tomando como referencia el formulario que implementamos en el apartado anterior. Añade un nuevo fichero al proyecto llamado <code>forms.py</code> al mismo nivel que <code>run,py</code>:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/forms.png)

En el fichero <code>form.py</code> vamos a crear la clase <code>SignupForm</code>:

```
from flask_wtf import FlaskForm
from wtforms import StringField, SubmitField, PasswordField
from wtforms.validators import DataRequiered, Email, Lenght

class SignupForm(FlaskForm):
    name=StringField('Nombre', validators=[DataRequired(), Length(max=64)])
    password=PasswordField('Password', validators=[DataRequired()])
    email=StringField('Email', validators=[DataRequired(), Email()])
    submit=submitField('Registrar')
```

Como se comento, la clase <code>SignupForm</code> hereda de <code>FlaskForm</code>. Además, cada uno de los campos del formulario se ha definido en el módulo <code>wtforms</code>). Esto hace que posteriormente el campo se renderice correctamente en la plantilla en función del tipo con el que lo hayamos declarado. El primer parámetro que le pasamos al campo es el nombre con el que se mostrará al usuario. Opcionalmente pasamos también un listado de validadores a cada campo, por ejemplo, para comprobar que los campos obligatorios no se dejan vacíos (<code>DataRequired</code>), restringir la longitud de los mismos (<code>Lenth()</code>) o comprobar si una cadena de texto es realmente un email (<code>Email</code>). Existen muchos más validadores y puedes definir los tuyos propios.

#### La plantilla para el formulario SignupForm

El siguiente paso será actualizar la plantilla <code>signup_form.html</code> que creamos en el apartado anterior para que haga uso de la clase <code>SignupForm</code>.

```
{% extends "base_template.html" %}

{% block title %}Registro de usuarios{% endblock %}

{% block content %}
    <form action="" method="post" novalidate>
      {{ form.hidden_tag() }}
      <div>
	{{ form.name.label }}
	{{ form.name(size=64) }}<br>
	{% for error in form.name.errors %}
  	<span style="color: red;">{{ error }}</span>
	{% endfor %}
      </div>
      <div>
	{{ form.email.label }}
	{{ form.email }}<br>
	{% for error in form.email.error %}
	<span style="color: red;">{{ error }}</span>
	{% endfor %}
      </div>
      <div>
	{{ form.password.label }}
	{{ form.password }}<br>
	{% endfor %}
      </div>
      <div>
	{{ form.password.label }}
	{{ form.password }}<br>
	{% for error in form.password.errors %}
	<span style="color: red;">{{ error }}</span>
	{% endfor %}
      </div>
      <div>
	{{ form.submit() }}
      </div>
    </form>
{% endblock %}
```

El cambio principal con respecto la versión anterior es que esta plantilla espera un objeto de la clase <code>SignupForm</code>, que hemos instanciado en la vista correspondiente, y lo hemos llamado <code>form</code>. Dicho objeto contiene los campos del formulario y sabe cómo renderizarlos. En nuestro ejemplo dejamos a _Flask-WTF_ que renderice la etiqueta de cada campo con <code>form.\<nombre_campo\>.label</code> y que genere el código del propio campo con <code>form.\<nombre\_campo\></code>.

Además, tras insertar cada campo recorremos el diccionario <code>errors</code> para mostrar al usuario los posibles errores de validación que haya en el mismo.

Para evitar que el navegador valide los campos por nosotros y delegar esta tarea a nuestra clase, hemos añadido el atributo <code>novalidate</code> a la etiqueta del formulario.

Por útlimo, un detalle que requiere una mención especial es la línea <code>{{ form.hidden_tag() }}</code>. Esto lo qeu hace es añadir todos los campos tipo <code>hidden</code> del formulario si los hubiera. **Por defecto, Flask-WTF genera para todas las instancias de la clase <code>FlaskForm</code> un campo oculto que contiene un token y sirve para proteger nuestra aplicación contra <a href="https://es.wikipedia.org/wiki/Cross-site_request_forgery">ataques CSRF</a>.**

Para poder generar este token es necesario definir un parámetro de configuración a nivel de aplicación llamado <code>SECRET_KEY</code>, cuyo valor debe ser un secreto de tipo string.

Por el momento, y para no complicarnos, modifica la línea del fichero <code>run.py</code> en la que instancias la aplicación Flask y sustitúyela por la siguiente:

```
app=Flask(__name__)
app.config['SECRET_KEY'] =
'7110c8ae51a4b5af97be6534caef90e4bb9bdcb3380af008f90b23a5d1616bf319bc298105da20fe'
```

En lecciones posteriores veremos qué es el diccionario <code>config</code> del objeto <code>app</code>. El valor de <code>SECRET_KEY</code> puede ser diferente al que se muestra arriba.

**No se sugiere desacivar esta funcionalidad**

### La vista para procesar el formulario SignupForm

Por último, vamos a modificar la vista <code>show\_signup\_form()</code>. Los cambios a realizar son muy pocos.

```
from forms import SignupForm

@app.route("/signup/", methods=["GET","POST"])
def show_signup_form():
    form=SignupForm()
    if form.validate_on_submit():
        name=form.name.data
        email=form.email.data
        password=form.password.data

        next=request.args.get('next', None)
        if next:
            return redirect(next)
        return redirect(url_for('index'))
    return render_template("signup_form.html", form-form)
```

En este caso lo primero que hacemos es instanciar un objeto de la clase <code>SingupForm()</code>. Al hacer esto puede ocurrir dos cosas en función de si la petición es <code>GET</code> o <code>POST</code>. Si el usuario simplemente ha accedido a la página que muestra el formulario de registro (GET), se crea un objeto con los campos vacíos. Por el contrario, si el usuario ha enviado el formulario (POST), se crea un objeto con los campos inicializados. El valor de estos campos es elq ue se envía en el cuerpo de la petición (recuerda que están en <code>request.form</code>).

Una vez instanciado el formulario, se llama al método <code>validate\_on\_submit()</code>. **Este método comprueba por nosotros que se ha enviado el formulario y que todos sus campos son válidos.** En este caso, podemos procesar nuestro formulario sin problema (la estructura del código es la misma que en el apartado anterior). Si no, devolveremos la plantilla que muestra el formulario (y en caso de que haya errores de validación se mostrarán al usuario).

Se repetirán los pasos para el formulario que nos permitirá dar de alta nuevas enradas en el blog.

### Formulario para dar de alta entradas en el blog

Cómo en el ejemplo anterior, comenzaremos por implementar el formulario para dar de alta entradas en el blog

#### PostForm

```
class PostForm(FlaskForm):
    title = StringField('Título', validators=[DataRequired(), Length(max=128)])
    title_slug = StringField('Título slug', validators=[Length(max=128)])
    content = TextAreaField('Contenido')
    submit = SubmitField('Enviar')
```

En este caso use el tipo de campo <code>TextAreaField</code> para tener un campo de texto apropiado con el que editar el contenido de la entrada.

### La plantilla para el formulario PostForm

A continuación modificaremos la plantilla <code>post\_form.html</code> que creamos en la lección 2 y que se encuentra en el directorio <code>templates/admin</code>.

```
{% extends "base_template.html" %}

{% block_title %}
  {% if form.title.data %}
    {{ form.title.data }}
  {% else %}
    Nueva entrada
  {% endif %}
{% endblock %}

{% block content%}
  <form action="" method="post" novalidate>
    {{ form.hidden_tag() }}
    <div>
      {{ form.title.label }}
      {{ form.title(size=128) }}<br>
      {% for error in form.title.errors %}
      <span style="color: red;">{{ error }}</span>
      {% endfor %}
    </div>
    <div>
      {{ form.title_slug.label }}
      {{ form.title_slug(size=128) }}<br>
      {% for error in form.title_slug.errors %}
      <span style="color: red;">{{ error }}</span>
      {% endfor %}
    </div>
    <div>
      {{ form.content.label }}
      {{ form.content }}<br>
      {% for error in form.content,errors %}
      <span style="color:red;">{{ error }}</span>
      {% endfor %}
      </div>
      <div>
	{{ form.submit() }}
      </div>
    </form>
  {{ endblock}}
```

Puedes comprobar que es muy similar a la del formulario de registro.

### La vista para procesar el formulario PostForm

Por último, actualizamos la vista <code>post\_form()</code> para procesar el formulario. En caso de que no haya ningún error, aprovechamos para crear un post y guardarlo en la variable en memoria <code>posts</code>.

```
from forms import SignupForm, PostForm

@app.route("/admin/post/", methods=['GET', 'POST'], defaults={'post_id': None})
@app.route("/admin/post/<int:post_id>/", methods=['GET', 'POST'])
def post_form(post_id):
    form = PostForm()
    if form.validate_on_submit():
        title= form.title.data
        title_slug = form.title_slug.data
        content = form.content.data

        post = {'title': title, 'title_slug': title_slug, 'content': content}
        post.append(post)

        return redirect(url_for('index'))
    return render_template("admin/post_form.html", form=form)

```

Como ves, hemos seguido la misma filosofía que al procesar el formulario de registro.

### ¿Quieres probar el código?

A estas alturas del tutorial ya podemos empezar a jugar con el código de la aplicación. Para que veas que todo funciona haremos unas modificaciones de manera que veas los titulos del los post en la página de inicio.

Actualiza la vista <code>index()</code> para pasarle a la plantilla la variable que contiene los post:

```
@app.route("/")
def index():
    return render_template("index.html", post=post)
```

Y modifica la plantilla <code>index.html</code> para que muestre los títulos de cada uno de los post que hay en memoria:

```
{% extend "base_template.html" %}

{% block title %}Tutorial Flask: Miniblog{% endblock %}

{% block content %}
  <ul>
    {% for post in posts %}
      <li>{{ post.title }}</li>
      {% endfor %}
      </ul>
{% endblock %}
```

### Conclusión

**Ha sido una lección itensa pero muy productiva**. En ella hemos repasado conceptos de HTML, como crear un formulario y cómo procesarlo. Después, hemos dado una pequeña introducción al objeto request de Flask. Finalmente hemos insalado la extensión Flask-WTF para facilitarmos el manejo de formularios. Como resultado, ya podemos jugar con la aplicación gracias a los formularios de registro y edición de posts. 

