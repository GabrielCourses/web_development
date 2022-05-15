![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/header.png)

# Primeros pasos en la Web

## La historia de tu primer sitio web

Es mucho trabajo crear un sitio web profesional, así que si eres nuevo en el desarrollo web, te animamos a que empieces poco a poco. No crearás otro Facebook de inmediato, pero no es difícil tener tu propio sitio web sencillo en línea, así que comenzaremos por ahí.

Al trabajar en orden a través de los artículos que se enumeran a continuación, pasarás de la nada a tu primera página web en línea. ¡Comencemos nuestro viaje!.

### Instalación de software básico

Cuando se trata de herramientas para crear un sitio web, hay mucho para elegir. Si recién estás comenzando, es posible que te sientas confundido por la variedad de editores de código, marcos de desarrollo y herramientas de prueba que existen. 

En este curso ocuparemos:

- Vim, Neovim, Notepad++, [Brackets](https://brackets.io/) como editor de texto.
- Firefox, Chrome, como navegador web.
- Editor de gráficos o imágenes [GIMP](https://www.gimp.org/)
- **Un sitema de control de versiones,** para administrar archivos en servidores, colaborar en un proyecto con un equipo, compartir código y recursos, y evitar conflictos de edición. Hoy en día [Git](https://git-scm.com/) es el sitema de control de versiones más popular y el servicio de alojamiento de codigo [GitHub](https://github.com/), basado en Git, también es muy popular.
- **Un programa de FTP,** para cargar páginas web en un servidor para el público (Git está reemplazando cada vez más a FTP para este fin). Algunos de estos programas disponibles son: Cyberduck, Fetch, y FileZilla.
- **Un sistema de automatización,** como Grunt o Gulp para realizar tareas repetitivas de forma automática, por ejemplo minimización de código, y ejecución de prueba.
- Bibliotecas, marcos de desarrollo (frameworks), etc., para acelerar la estructura de funciones comunes. Una biblioteca tiende a ser un archivo JavaScript o CSS existente que proporciona una funcionalidad lista para usar y pruebes tu código. Un framework tiende a llevar esta idea más allá, ofreciendo un sistema completo con alguna sintaxis personalizada para que puedas escribir una aplicación web basada en él.

***
Nota: La lista parece ser compleja, pero de momento no es necesario un conocimiento previo de ninguna de estas herramientas. Incluso puedes iniciar con tan solo el editor de texto y alguna configuración en tu navegador web.
***

## ¿Cómo se configura un servidor de prueba local?

Ahora explicaremos cómo configurar un servidor de prueba local simple en su equipo y los conceptos básicos de cómo utilizarlo.

### Prerrequisitos:

**¿Cómo funciona internet?**

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/internet.png)

Internet es la columna vertebral de la Web, la infraestructura técnica que hace posible la Web. En su forma más básica, Internet es una gran red de computadoras que se comunican entre sí.

**Una red sencilla**

Cuando dos computadoras necesitan comunicarse, debe vincularlas, ya sea físicamente(generalmente con un cable Ethernet) o de forma inalámbrica (por ejemplo, con sistemas Wi-Fi o Bluetooth). Todas las computadoras modernas pueden sostener cualquiera de esas conexiones.

***
Nota: Para el resto del documento, hablaremos de conexiones indistintamente si son físicas o inalámbricas.
***

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/simple.png)

Tal red no está limitada a dos computadoras. Puede conectar tantos ordenadores como desee. Pero se complica rápidamente conectándolas con cables y enchufes para cada computadora.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/multiple.png)

Para resolver este problema, cada computadora es una red está conectada a una computadora pequeña especial llamada _router_. Este _router_ solo tiene un trabajo: como un señalizador en una estación de tren, se asegura de que un mensaje enviado desde una computadora determinada llegue a la computadora de destino correcta. Para enviar un mensaje a la computadora **B**, la computadora **A** debe enviar el mensaje al _router,_ que a su vez reenvía el mensaje a la computadora **B** y se asegura de que el mensaje no se entregue a la computadora **C.**

Una vez que agregamos un _router_ al sistema, nuestra red de 'n' computadoras solo requiere 'n' cables: un solo enchufe para cada computadora y un _router_ con 'n' enchufes.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/router.png)

**La red de redes**

Pero, ¿qué pasa con la conexión de cientos, miles, miles de millones de computadoras? Por supuesto, un solo enrutador no puede escalar tanto, pero como ya comentamos, un _router_ es solo una computadora como cualquier otra, entonces, ¿que nos impide conectar dos _routers_ juntos?. Nada, así que hagamoslo.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/two_routers.png)




# Web Development

**HTML: HyperText Markup Language**

HTML(HyperText Markup Language) is the most vasic building block of the Web. I defines the meaning and structure of web content. Other technologies besides HTML are generally used to describe a web page's appearence/presentation(CSS) or functionality/behavior(Javascript).

"Hypertext" refers to links that connect web pages to one another, either within a single website or between websites. Link are a fundamental aspect of the Web. By uploading content to the Internet and linking it to pages created by other people, you become an active participant in the World Wide Web.

# Conceptos básicos de HTML


