![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/lesson1.png)

# Lección 1: La primera aplicación Flask

### Preparando el entorno de programación

Antes de entrar en materia, vamos a configurar nuestros entorno de programación. Voy a suponer que tienes Python instalado asi como <a href="https://github.com/gabrielfernando01/basics_in_python/tree/master/virtualenv">virtualenv</a>. No obtante, para resumir, te diré que virtualenv nos permite aislar nuestra aplicación junto con todas sus dependencias de otras aplicaciones Python que tengamos en nuestro sistema, de manera que las librerías de cada una de las aplicaciones no entren en conflicto.

Realizada esta aclaración, procedemos con el primer paso que será el directorio "tutorial\_flask". Una vez dentro, inicializaremos nuestro entorno Python. Para ello, entramos en el terminal, nos situamos dentro del directorio «tutorial\_flask» y escribimos:

```
virtualenv env
```

Una vez que hemos creado nuestro entorno, debemos indicarle al terminal que queremos hacer uso del mismo y no del entorno Python global del sistema. Por tanto:

Ejecutamos el siguiente comando si estamos en Linux/Mac:

```
source env/bin/activate
```

Si estamos en Windows ejecutaremos:

```
env\Scripts\activate.bat
```

Sabremos que el entorno está activado porque el prompt comienza con la palabra «(env)», como muestra la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/env.png)

Como ya lo comentamos, vamos a desarrollar un miniblog usando el framework Flask, asi que el siguiente paso será instalar dicho framework junto con sus dependencias.

Para instalar Flask (versión 1.x) escribimos en el terminal el siguiente comando:

```
pip install Flask
```

De manera que dentro de nuestro entorno «env», se instalarán el framework y las librerías que necesite.

Podemos ver todas las dependencias de nuestra aplicación si ejecutamos el siguiente comando desde el terminal:

```
pip freeze
```

Con esto ya tenemos todo listo para crear nuestra primera aplicación Flask.

## Creando la primera aplicación Flask

Lo siguiente que haremos será crear un nuevo fichero que llamaremos <code>run.py</code> en el directorio <code>tutorial_flask</code>. Después añadimos el siguiente código:

```
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello world'
```

¿Qué significa cada una de las líneas de código?

1. Toda aplicación Flask es una instancia WSGI de la clase <code>Flask</code>. Por tanto, importamos dicha clase y creamos una instancia que en este caso he llamado <code>app</code>. Para crear dicha instancia, debemos pasar como primer argumento el nombre del módulo o paquete de la aplicación. Para estar seguros de ellom utilizamos la palabra reservada <code>\_name\_</code>.

Esto es necesario para que Flask sepa, por ejemplo, donde encontrar las plantillas de nuestra aplicación o los ficheros estáticos.

2. Una característica de Flask es que tendremos métodos asociados a las distintas URLs que componen nuestra aplicación. **Es estos métodos donde ocurre toda la magia y toda la lógica que queramos implementar.** Dentro del patron <a href="https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador">MVC<a>, esta parte del código se correspondería con el controlador. **Flask se encarga de hacernos transparente el cómo a parir de una petición a una URL se ejecuta finalmente nuestra rutina.** Lo único que tendremos que hacer nosotros será añadir un decorador a nuestra función. En nuestro caso, hemos llamado a nuestra función <code>hello_world</code> que será inovcada cada vez que se haga una petición a la URL raíz de nuestra aplicación.

3. El decorador <code>route</code> de la aplicación (app) es el encargado de decirle a Flask qué URL debe ejecutar su correspondiente función.

4. El nombre que le demos a nuestra función será usado para generar internamente URLs a partir de dicha función.

5. Finalmente, la función debe devolver la respuesta que será mostrada en el navegador del usuario.

***
Hay que tener cuidado con **no** nombrar al fichero que instancia nuestra aplicación «flask.py» ya que entraría en conflicto con el propio Flask.
***

## Probando la aplicación Flask: Lanzando el servidor interno que viene con Flask

Ya tenemos las primeras líneas de código de nuestra aplicación. El siguiente paso es de los más emocionantes e importantes, probar que todo funciona.

Flask viene con un servidor interno que nos facilita mucho la fase de desarrollo. **No debemos usar este servidor en un entorno de producción ya que no es este su objetivo.**

En nuestro ejemplo y, dado que en estos momentos estamos en el proceso de construcción de nuestra aplicación, si haremos uso de él.

Para lanzar nuestra aplicación haciendo uso de este servidor, podemos ejecutar el comando <code>flask</code> o bien <code>python -m</code>.

Sin embargo, antes de ello debemos indicarle al servidor qué aplicación debe lanzar declarando la variable de entorno <code>FLASK_APP</code>.

Pongamos todo en orden.

Para declarar la variable <code>FLASK_APP</code> debemos modificar el fichero <code>activate</code> de nuestro entorno Python.

En Linux/Mac se encuentra en <code>env/bin/activate. Al final del fichero añadimos lo siguiente:

```
export FLASK_APP="run.py"
```

En Windows se encuentra en <code>env\Script\activate.bat</code>. Al final del fichero añadimos lo siguiente:

```
set "FLASK_APP=run.py"
```

Te debe quedar algo similar a la siguiente imagen:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/activate.png)

Para que los cambios realizados se tengan en cuenta debemos salir del entorno Python y volver a entrar. Para salir, hay que ejecutar en la terminal <code>deactivate</code>.

A coninuación, volvemos a activar el entorno con <code>source env/bin/activate</code> si estamos en Linux/Mac o <code>env\Scripts\activate.bat</code> si estamos en Windows.

Una vez que hemos definido dónde puede el servidor de Flask encontrar nuestra aplicación, lo lanzamos ejecutando:

```
flask run
```

O bien:

```
python -m flask run
```

Esto lanzará el servidor de pruebas:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/flask_run.png)

Para comprobar que, efectivamente, nuestra aplicación funciona, entramos al browser y en la barra de direcciones escribimos: <code>localhost:5000</code>. Esto nos mostrará el mensaje «Hello world» de nuestra función <code>hello_world()</code>.

Por defecto, el servidor que viene con Flask está escuchando en el puerto 5000 y solo acepta peticiones de nuestro propio ordenador.

Si queremos cambiar el puerto por cualquier motivo lo podemos hacer de dos formas distintas:

- Estableciendo la variable de entorno <code>FLASK\_RUN\_PORT</code> en un puerto diferente.
- Indicando el puerto al lanzar el servidor <code>flask run --port 6000</code>.

Para aceptar peticiones de otros ordenadores de nuestra red lanzaremos el servidor de la siguiente manera:

```
flask run --host 0.0.0.0
```

## Modo debug

Flask viene con un modulo debug que es muy útil usar mientras estamos desarrollando, ya que cada vez que hagamos un cambio en nuestro código reiniciará el servidor y no tendremos que hacerlo manualmente para que los cambios se guarden y apliquen.

Para activar el modo debug nuevamente editamos el fichero <code>env/bin/activate</code> en Linux/Mac colocando al final:

```
export FLASK_ENV="development"
```

En Windows:

```
set "FLASK_ENV=development"
```

**No usar el modo debug en un entorno de producción**

Activar el modo debug hace que:

- Se active el depurador.
- Se tengan en cuenta los cambios después de guardarlos sin tener que reiniciar manualmente el servidor.
- Activar el modo debug, de manera que si se produce una excepción o error en la aplicación veremos una traza de los mismos.

En este caso, al ejecutar el servidor veremos que estamos en modo desarrollo:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/flask_dev.png)

## Conclusión

Hemos visto cómo preparar el entorno de desarrollo e instalar las dependencias necesarias. Hemos creado una primera aplicación que muestra el mensaje «Hello world» y la hemos puesto a funcionar con el servidor que trae el propio Flask. Por último, hemos visto como activar el modo debug para usarlo durante la fase de desarrollo.