![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/header_html5.jpeg)

# Introducción a HTML5

Cuando accedemos a una página web, debemos tener en cuenta que lo que realmente está ocurriendo es que nuestro navegador web está pidiendo un documento de texto al sistema (_máquina_) donde está almacenada esa página web.

En cualquier navegador, existe una opción para ver el **código fuente** de la página web, la cuál nos mostrará exactamente el texto de dicho documento. El navegador normalmente no nos muestra esa información literalmente, sino que la interpreta y va dibujando los elementos de la página web.

El documetnto que lee el navegador está escrito en un **lenguaje de marcado** llamado **HTML**, que son las siglas de **HyperText Markup Language** (_Lenguaje de marcas de hipertexto_), o lo que es lo mismo, un lenguaje de etiquetas que permite incluir o hacer referencia a todo tipo de información.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/doc_html.png)

## ¿Qué es una etiqueta HTML?

En el navegador Chrome, puedes pulsar la combinación de teclas <code>Ctrl + U</code> para ver el código fuente de la página en la que te encuentras. Dicho documento esta formado por **etiquetas,** que son la base del **lenguaje HTML.**

Existen muchas etiquetas y cada una se utiliza para contener información y darle un cierto significado a dicha información, dependiendo de la etiqueta que se trate. Las etiquetas HTML tienen la sigiente estructura:

```
<etiqueta>contenido</etiqueta>
```  

En **HTML** no se puede utilizar cualquier palabra como etiqueta. En su lugar, existen una serie de etiquetas concretas, cada una de ellas con su finalidad y características propias, que tendremos que utilizar según requiera la ocasión. Por norma general, las etiquetas deben cerrarse para indicar donde finaliza su contenido.

## ¿Qué es la semántica?

Uno de los principales objetivos de HTML5 es introducir información en un documento HTML5 de forma que sea semántico y no visual. Con esto queremos decir que todos los aspectos visuales deben dejarse para el apartado de presentación que se gestiona desde un <a href="https://github.com/GabrielCourses/web_development/tree/main/css">lenguaje CSS</a>.