## ¿Qué es Html?
HTML (HyperText Markup Language) es un lenguaje compuesto por un grupo de etiquetas definidas con un nombre rodeado de paréntesis angulares <>. Los paréntesis angulares delimitan la etiqueta y el nombre define el tipo de contenido que representa.

La etiqueta `<html>` indica que el código es html. Algunas de estas etiquetas son declaradas individualmente (por ejemplo: `<br>`) y otros son declaradas en pares, que incluyen una apertura y otra de cierre, como `<html><html/>` (en la etiqueta  de cierre el nombre va precedido por una barra invertida)

Las etiquetas individuales y las de apertura pueden incluir atributos para ofrecer información adicional acerca de sus contenidos (por ejemplo `<html lang="es">`).

Las etiquetas individuales y la combinación de etiquetas de apertura y cierre se llaman **elementos**.
```html
<br>    <!-- Etiqueta Individual---->

<html>  <!-- Etiqueta de Apertura---->

<html/> <!-- Etiqueta de Cierre---->
```

## Html5
Html5 es la quinta revisión del lenguaje de pr

## Elementos
El HTML consiste en una serie de elementos que se usan para encerrar o unir diferentes partes del contenido para que aparezca o actué de una manera determinada. Los elementos HTML estan delineados con etiquetas escritas con corchetes angulares `< >`.

Los elementos compuestos por una solo etiqueta se usan para modificar el contenido que los rodea o incluir recursos externos, mientras que los elementos que incluyen etiquetas de apertura y cierre se utiliza para delimitar el contenido del documento, tal como se muestra en la figura 1.

![[figura1.png]]
Los elementos y las etiquetas no son exactamente los mismo, aunque muchas personas usan los términos de manera indistinta.
- El nombre de la **etiqueta** es el contenido que esta entre corchetes angulares. La etiqueta incluye los corchetes en este caso: `<h1>.
- Un **elemento** son las etiquetas de apertura y cierre, y todo el contenido entre ellas, incluidos los elementos anidados, como se presenta en el siguiente ejemplo.

```html
<p>Este es un ejemplo de elemento
  <strong><em>Con elementos anidados</em></strong>  
</p>
```

Este elemento de párrafo tiene otros elementos anidados. Cuando se anidan elementos, es importante que estén anidados de forma correcta. Las etiquetas HTML deben cerrarse en el orden inverso del que se abrieron. En el ejemplo anterior, observa cómo `<em>` se abre y se cierra dentro de las etiquetas `<strong>` de apertura y cierre, y que `<strong>` está abierto y cerrado dentro de las etiquetas `<p>`.

## Estructura del documento
Los documentos HTML incluyen una declaración de tipo de documento y el elemento raíz `<html>`.
El encabezado y el cuerpo del documento se anidan en el elemento `<html>`.
El encabezado del documento no es visible para los usuarios, es fundamental que el sitio funcione. Ya que contiene:
- Toda la metainformación. 
- Información de los motores de búsqueda.
- Los resultados de redes sociales.
- Iconos de las pestañas del navegador.
- Acceso directo a la pantalla principal de un dispositivo móvil.
- Comportamiento y presentación del contenido de la pagina.

### `<!DOCTYPE html>`
El doctype le indica al navegador que use el modo de estándares. Si se omite, los navegadores usaran un modo de renderización diferente, conocido como modo no estándar. Al incluir el doctype ayuda a prevenir el modo no estándar.
Para asegurarnos de que el contenido de nuestros documentos sea interpretado correctamente como código html, debemos agregar la declaración `<!DOCTYPE>` al comienzo del archivo. Se requiere al comienzo de cada documento para ayudar al navegador a decidir cómo debe generar la página web.

### `<html>`
El elemento `<html>` es el elemento raíz de un documento HTML. Es el elemento superior de `<head>` y `<body>` y contiene todo lo que esta en el documento HTML, excepto el doctype. Si se omite, será implícito, pero es importante incluirlo, ya que es este elemento en el que se declara el idioma 
```html
<!DOCTYPE html>
<html lang="es">

<html/>
```
### Idioma del contenido
El atributo de idioma **lang** agregado a la etiqueta `<html>` define el idioma principal del documento, el valor del atributo **lang** es un código de idioma ISO de dos o tres letras seguidas de la legión. Es recomendable usar la región ya que la idioma puede variar entre otras regiones.
Existen varios valores disponibles para el atributo *lang*:

| **Valor** | **Pais \| Region** |
| --------- | ------------------ |
| Es - Mx   | Español - México   |
| En        | Ingles             |
| Fr        | Fránces            |
## `<head>`
El head o encabezado de metadatos del documento, contiene todos los metadatos de un sitio o una aplicación. Este elemento se usa para definir la información necesaria para configurar la pagina web, como el titulo , el tipo de codificación de caracteres y los archivos externos requeridos del documento.

```html
<!DOCTYPE html>
<html lang="es">
<head>

<head/>

<html/>
```
### Componentes obligatorios dentro de `<head>`
Los metadatos del documento, incluidos el título, el grupo de caracteres, la configuración del viewport, la descripción, la URL base, los vínculos a las hojas de estilo y los íconos, se encuentran en el elemento `<head>`. Si bien es posible que no necesites todas estas funciones, incluye siempre el grupo de caracteres, el título y la configuración del viewport.

#### Codificación de caracteres
El primer elemento de head debe ser la declaración de codificación de caracteres de charset. Se encuentra antes del titulo para garantizar que el navegador pueda procesar los caracteres de ese titulo y todos los caracteres del resto del documento.
Se debe usar UTF-8, ya que se habilita la codificación de uno a cuatro bytes para todos los caracteres, es el tipo de codificación requerida por HTML5.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"> <!-- CODIFICACION DE CARACTERES -->
</head>

</html>
```

#### Metadatos viewport
La otra metaetiqueta que debe considerarse esencial es la viewport, que ayuda a mejorar la capacidad de respuesta del sitio y permite que el contenido se procese correctamente de forma predeterminada, sin importar el ancho de la viewport.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- METAETIQUETA DE LA VENTANA DE VISUALIZACION -->
</head>

</html>
```

#### Titulo del documento
Este elemento define el titulo de la pagina

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Titutlo de página</title> <!-- TITULO DE LA PAGINA -->
</head>

</html>
```