![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/css.png)

# Introducción a CSS

Si te gusta el mundo del **diseño web** o tienes curiosidad por empezar en este sector, probablemente ya habrás escuchado en término **CSS.** Se trata de una tecnología utilizada para dotar de **cualidades visuales y estéticas** a una página web. Si nunca has tocado esta materia, comprobarás que se trata de una forma analítica, lógica y prácticamente matemática de crear páginas web, pero gracias a ella podemos simplificar la creación de páginas y conseguir exactamente lo que buscamos.

La **curva de aprendizaje** de CSS suele ser sencilla (_es fácil aprender a hacer cosas, aunque complicado dominar_), aunque también es cierto que puede resultar complejo adaptarse si nunca has programado (_o eres totalmente ajeno a estas temáticas_), pero a medida que comentes errores y vas practicando, tu capacidad para escribir código CSS mejora progresivamente, permitiéndonos avanzar a un ritmo cada vez más veloz.

## ¿Qué es CSS?

Antes de comenzar, debes tener claro un concepto clave: una página web es realmente **un documento de texto.** En dicho documento se escribe **código HTML,** con el que crea el contenido de una web. Por otro lado, existe el **código CSS,** que unido al código HTML permite darle forma, color, posición (_y otras características visuales_) a una página.

En resumen, se trata de un idioma como podría ser el inglés o el alemán, que los navegadores web como **Chrome** o **Firefox** conocen y pueden entender. Nuestro objetivo como diseñadores y programadores web es precisamente ese: **aprender el idioma.**

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/chrome.png)

Las siglas **CSS** (Cascading Style Sheets) significa «Hojas de estilo en cascada» y parten de un concepto simple pero muy potente: aplicar **estilos** (colores, formas, márgenes, etc) a uno o varios documentos (_generalmente documentos HTML, páginas web_) de forma masiva.  

Se le denomina estilos **en cascada** porque se aplican de arriba a abajo (_siguiendo un patrón denominado **herencia**_) y en el caso de existir ambigüedad, se siguen una serie de normas para resolverla.

La idea de CSS es la de utilizar el concepto de **separación de presentación y contenido,** intentando que los documento HTML, incluyan sólo información y datos, relativos al significado de la información a transmitir (_el contenido_), y todos los aspectos relacionados con el estilo (diseño, colores, formas, etc.) se encuentren en un documento CSS independiente (_la presentación_).

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/plus.png)

De esta forma, se puede unificar todo lo relativo al diseño visual en **un solo documento CSS,** y con ello varias ventajas:

- Si necesitas hacer modificaciones **visuales** lo hacemos en **un solo lugar**. No necesitamos editar todo el HTML, en cuestión por separado.
- Se reduce la **duplicidad de estilos** en diferentes lugares, por lo que es más fácil de organizar y hacer cambios. Además, al final la información a transmitir es considerablemente menor (_las páginas se descargan más rápido_).
- Es más fácil crear **versiones diferentes** de presentación para otros tipos de dispositivos: tablets, smartphones o dispositivos móviles, etc.

## ¿Cómo usar CSS?

Antes de empezar a trabajar con **CSS** hay que conocer las diferentes formas para incluir estilos en nuestros **documentos HTML,** ya que hay varias, cada una con sus particularidades y diferencias.

En principio, tenemos **tres** formas diferentes de hacerlo, siendo la primera la más común y la última la menos habitual:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/use_css.png)

### Enlace a CSS externo (link)

En la cabecera de nuestro documento HTML, más concretamente en el bloque <code>\<head\>\</head\></code>, podemos incluir una etiqueta <code>\<link\></code> con la que establecemos una relación entre el documento actual y el archivo CSS que indicamos con el atributo <code>href</code>.

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/href.png)

De esta forma, los navegadores sabrán que deben aplicar los estilos que se encuentren en el archivo <code>index.css</code>. Se aconseja escribir esta línea lo antes posible (_sobre todo, antes de los script_), obligando así al navegador a aplicar los estilos cuanto antes y eliminar la **falsa percepción visual** de que la página está en blanco y no ha sido cargada por completo.

***
Esta es la manera recomendada de utilizar **estilos CSS** en nuestros documentos.
***

***
El atributo <code>type="text/css"</code> no es necesario en HTML5. Muchas veces se indaca para mantener retrocompatibilidad con navegadores muy antiguos, pero en la actualidad se puede omitir
***

### Incluir CSS en el HTML (style)

Otra de las formas habituales que existen para incluir estilos CSS en nuestra página es la de añadirlos directamente en el documento  HTML, a través de una etiqueta <code>\<style\></code> que contendrá el código CSS:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/style.png)

