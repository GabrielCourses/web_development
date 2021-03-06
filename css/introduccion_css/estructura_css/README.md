![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/estructura_css.png)

# Estructura CSS

Al igual que los documentos HTML, los documentos CSS son archivos de texto donde se escribe una serie de órdenes y el cliente (navegador) las interpreta y aplica a los documentos HTML asociados.

## Sintaxis básica

La **estructura CSS** se basa en reglas que tienen el siguiente formato:

![](https://raw.githubusercontent.com/GabrielCourses/web_development/main/image/selector.png)

- **Selector:** El selector es el **elemento HTML** que vamos a seleccionar del documento para aplicarle el estilo concreto. Por ejemplo, con <code>p</code> seleccionaríamos todas las etiquetas <code>\<p\></code> del HTML. Aunque esto es mucho más complejo.
- **Propiedad:** La propiedad es una de las diferentes características que brinda el lenguaje CSS y que aplicaremos al selector para darle estilo.
- **Valor:** Cada **propiedad CSS** tiene una serie de valores concretos que se le puede asignar, con los que tendrá diferentes comportamientos.

Con todo esto le iremos indicando al navegador que, para cada etiqueta (_selector especificado_) debe aplicar las reglas (_propiedad y valor_) indicadas.

Vamos a verlo con un ejemplo. Para el siguiente código HTML:

```
<!DOCTYPE html>
<html>
  <head>
    <title>Titulo de página</title>
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="first">
      <p>Párrafo</p>
    </div>
    <div id="second">
      <span>Capa</span>
    </div>
  <body>
</html>
```

