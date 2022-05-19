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

Al conectar computadoras a enrutadores, luego enrutadores a enrutadores, podemos escalar infinitamente.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/routers00.png)

Esta red se acerca mucho a lo que llamamos Internet, pero nos falta algo. Construimos esa red para nuestros propios fines. Hay otras redes por ahí: tus amigos, tus vecinos, cualquiera puede tener su propia red de computadoras. Pero en realidad no es posible instalar cables entre tu casa y el resto del mundo, entonces, ¿cómo puedes manejar esto? Bueno, ya hay cables ligados a tu casa, por ejemplo, energía eléctrica y teléfono. La infraestructura telefónica ya conecta tu casa con cualquier persona en el mundo por lo que es el cable perfecto que necesitamos. Para conectar nuestra red a la infraestructura telefónica, necesitamos un equipo especial llamado módem. Este módem convierte la información de nuestra red en información manejable por la infraestructura telefónica y viceversa.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/modem.png)

Entonces estamos conectados a la infraestructura telefónica. El siguiente paso es enviar los mensajes de nuestra red a la red a la que queremos llegar. Para ello, conectaremos nuestra red a un Internet Services Provider (ISP). Un ISP es una empresa que administra algunos enrutadores especiales que están todos vinculados entre sí y también pueden acceder a los enrutadores de otros ISP. Entonces, el mensaje de nuestra red se lleva a través de la red de redes ISP a la red de destino. Internet consiste en toda esta infraestructura de redes.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/isp.png)

## Finding computers

Si deseas enviar un mensaje a una computadora, debes especificar cuál. Por lo tanto, cualquier computadora conectada a una red tiene una dirección única que la identifica, llamada "dirección IP" (Internet Protocol). Es una dirección formada por una serie de cuatro números separados por un punto, por ejemplo: 192.168.2.10.

Para el pensamiento humano es difícil recordar estas direcciones. Para facilitar las cosas, usamos un alias como IP con un nombre legible por humanos llamado _dominio_. Por ejemplo google.com es el nombre del dominio que se utiliza sobre la dirección IP 142.250.190.78. Por lo tanto, usar el nombre de dominio es la forma más fácil de llegar a una computadora a través de Internet.

## Internet and the web

Como puedes notar, cuando navegamos por la web con un navegador web, generalmente usamos el nombre de dominio para llegar a un sitio web. ¿Significa eso que Internet y la Web son lo mismo? No es tan simple. Como vimos, Internet es una infraestructura técnica que permite conectar miles de millones de computadoras entre sí. Entre esas computadoras, algunas computadoras (llamadas servidores web) pueden enviar mensajes inteligibles para los navegadores web. Internet es una infraestructura, mientras que la Web es un servicio construido sobre la infraestructura. Vale la pena señalar que hay varios otros servicios integrados en Internet, como el correo electrónico y el IRC.

# Bibliografía

- https://www.w3schools.com/
- https://devdocs.io/








