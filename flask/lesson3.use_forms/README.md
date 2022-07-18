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

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/form.png)

