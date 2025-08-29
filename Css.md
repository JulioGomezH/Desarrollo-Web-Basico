## Selectores
Aplican estilos a elementos HTML Específicos, permiten seleccionar elementos HTML para aplicarles estilos.
* **elemento:** selecciona todos los elementos del tipo indicado. `p {color:red;}`
* **.clase:** selecciona elementos con una clase especifica. `.clase {color:red;}`
* `#id`: selecciona un elemento con un ID único. `#main {color:red;}`
*  `*`: selecciona todos los elementos. `* {padding: 1rem;}`
* `elemento1 elemento2`: selecciona elemento2 dentro de elemento1 `div a {text-decoration:none;}`

## Color y Fondo
Permiten definir los colores de los elementos HTML
* **color:** define el color del texto `p {color:red;}`
* **background-color:** define el color de fondo `h1 {background-color:#fff;}`

## Box Model
Controla el espacio y tamaño de los elementos
![[css Figura1.png]]

## Display y Posición
Define la colocación de los elementos
### Display
* **block**: ocupa todo el ancho disponible.
* **inline**: 
* **flex**: contenedor flexible.
* **grid**: contenedor en cuadricula.
* **none**: oculta el elemento.

### Position
* **static**: posición por defecto (flujo normal)
* **relative**: se mueve respecto a su posición original.
* **absolute**: se mueve respecto al contenedor mas cercano de su posición.
* **fixed**: permanece en pantalla aunque se haga scroll (posición fijo).
* **sticky**: se mantiene fijo hasta cierto de punto del scroll.

## Flexbox
Permite distribuir y alinear elementos dentro de un contenedor flexible en una dirección.
* **display:** convierte al contenedor en flexible
* **flex-direction:** dirección en que se distribuyen los elementos.
* **Justify-content:** alinea elementos en el eje principal.
* **align-items:** alinea elementos en el eje secundario.
* **align-self:** alinea elementos en el eje secundario.
* **flex-grow:** define como un elemento crece segun el espacio disponible.
* **flex-shrink:** define como un elemento reduce su tamaño.
* **flex-basis:** tamaño inicial de un elemento antes de distribuir el espacio.
* 

## Grid
Crea diseños en dos dimensiones

* **display: grid;** activa la cuadricula.
* **grid-template-colums:** define las columnas.
* **grid-template-rows:** define las filas.
* **column-gap:** espacio entre columnas.
* **row-gap:** espacio entre filas.
* **grid-row:** coloca en filas.
* **grid-column:** coloca en columnas.
* **grid-area:** define una area.



##### ¿Qué es es rem y em?

Rem: Significa Root em y se refiere al cambio de la fuente en la raiz, es decir el tamaño que se le aplique a la etiqueta HTML.
 **Ejemplo rem**
```html
<style>
	html{
	font-size: 16px;
	}
	p {
		font-size: 1.5rem: /* 16px * 1.5rem = 24px */
	}

</style>

<html>
	<p>Texto</p>
</html>

```
em: se refiere al tamaño en relación al tamaño fuente del elemento padre, se muestra el siguiente ejemplo.
**Ejemplo em**
```html
<style>
	html{
	font-size: 14px;
	}
	div{
		font-size: 16px;
	}
	p {
		font-size: 2rem: /* 16px * 1.5rem = 24px &/
	}

</style>

<html>
	<p>Texto 1</p> <!-- 14px * 2em = 28px-->
	<div>
		<p>Texto 2</p> <!-- 16px * 2em = 32px-->
	</div>
</html>

```
##### Como Utilizar fuentes offline en css
Se crea una carpeta donde podamos guardar el archivo ttf de la fuente
```bash
/proyecto/
|-- index.html
|-- css/
|   |--estilos.css
|-- fonts/
|   |-- mifuente.ttf
```

Paso 2 .- Se declara la fuente en el archivo, se usa @font-face en el archivo css para importar la fuente.
```css
@font-face {
	font-family: 'mifuente';
	src:url('../fonts/mi_fuente.woff2') format('woff2'),
	url('../fonts/mi_fuente.woff') format('woff'),
	url('../fonts/mi_fuente.otf') format('openttype'),
	url('../fonts/mi_fuente.ttf') format('truetype');
	font-weight:normal;
	font-style:normal;
}

body{
	font-family: 'mifuente', san-serif;
}
```


##### Input y estilos
Para darle color el texto de los input
```css
input{
	caret-color:red:
}
```
accent-color: le dará efecto a los checkbox, radio entre otros.
```css
input{
	accent-color:#2c7c72;
}
```
Para personalizar una lista
```css
li::marker{
	content: '*';
}
```
Para personalizar color de un rango  mínimo y máximo en los input
**html**
```html
	<input type="number" min="1" max="10" value="16">
	<input type="number" min="1" max="10" value="7">
```
**css**
```css
input:out-of-range{
	background-color: rgba(255 ,0, 0, 0.25);
	border: 2px solid red;
}

input:in-range{
	background-color: rgba(0 ,255, 0, 0.25);
}
```
Datalist: Usa la etiqueta datalist para crear el autocompletado con solo html
```html
<label>Elige tu pais: 
	<input list="lista_paises" placeholder=" Escribe o selecciona ...">
</label>

<datalist id="lista_paises">
	<option value= "Mexico">
	<option value= "USA">
	<option value= "Canada">
	<option value= "Rusia">
	<option value= "China">
	<option value= "Japon">
</datalist>
```

##### Loading animation css
html
```html
<div class="loader">
     <div class="spin"></div>
</div>
```
css
```css
.loader {
	border: 5px solid #f3f3f3;
	border-top: 5px solid #3498db;
	border-radius:50%;
	width: 30px;
	height: 30px;
	animation: spin 2s linear infinite;
}
@keyframes spin {
	0% { transport:rotate(0deg); }
	100% { transport:rotate(360deg); }
}
```

##### Glass effect
```css
.glass-effect{
	background: linear-gradient(135deg, rgba(255,255,255, 0.1),rgba(255,255,255, 0));
	-webkit-backdrop-filter: blur(20px);
	backdrop-filter: blur(20px);
	box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
	border: 1px solid rgba(255,255,255, 0.18);
	border-radius: 32px;
}
```

##### Box Shadow vs Drop Shadow
**Box shadow**
- Basado en una caja
- Soporta inset
- Soporte spread
- Hardware no acelerado
```css
.box-shadow{
	box-shadow: 0 0 20px #3d3d3d;
}
```
**Drop shadow**
- Soporta Transparencia
- No Soporta inset
- No Soporte spread
- Hardware Acelerado
```css
.drop-shadow{
	filter: drop-shadow (0 0 20px #121212);
	/* drop-shadow:( offset-x offset-y blur-radius color ); */
}
```

#### Css Shorthand
##### Background
```css
/* Ejemplo Normal */
.background-normal{
	background-color: #ooo;
	background-image: url(./img.png);
	background-repeat: no-repeat;
	background-position: center;
}

/* Ejemplo Normal */
.background-corto{
	background: #ooo url(./img.png) no-repeat center;
}
```

##### Font Shorthand
```css
/* Ejemplo Normal */
.font-normal{
	font-style: italic;
	font-variant: small-caps;
	font-weight: bold;
	font-size: 24px;
	line-height: 1.5;
	font-family: Arial, Helvetica, sans-serif;
}

/* Ejemplo Normal */
.font-corto{
	font: italic small-caps bold 24px/1.5 Arial, Helvetica, sans-serif;
	/*    style | variant | weight | size/line-height | family */
}
```

##### Border
```css
/* Ejemplo Normal */
.border-normal{
	border-width: 1px;
	border-style: solid;
	border-color: #000;
}

/* Ejemplo Normal */
.border-corto{
	border: 1px solid #000;
}
```

##### Margin
```css
/* Ejemplo Normal */
.margin-normal{
	margin-top: 10px;
	margin-right: 5px;
	margin-bottom: 15px;
	margin-left: 8px;
}

/* Ejemplo Normal */
.margin-corto{
	margen: 10px 5px 15px 8px;
	/*     top | right | bottom | left*/
}

/* Ejemplo Normal */
.margin-mascorto{
	margen: 10px 15px ;
	/*     top & bottom | right & left*/
}
```
##### :where( )
El :where() es una función pseudo-clase toma un selector de lista a un argumento , y selecciona un elemento que puede ser seleccionado por una de los selectores en la lista.
```css
/* Ejemplo Normal */
.card h1, .card h2, .card h3, .card h4{
	color:#fafafa;
}

/* Ejemplo Normal */
.card :where(h1, h2, h3, h4){
	color:#fafafa;
}
```

##### @extend in css
El Css rol @extends dice sass que un selector puede integrar los estilos de otro. por ejemplo:
```css
.button-base{
	border-radius: 4px;
	margin:5px;
	background-color: blue;
}

.menu-button {
	@extend .button-base;
	color: white;
}
```

##### Best css shortcuts
**min( )**
```css
.width{
	width: 100px;
	min-width: 50px;
}
.width-short{
	width: min(100px, 50px);
}
```
**clamp( )**
```css
.example-clamp{
	font-size: 16px;
	max-font-size: 20px;
	min-font-size: 12px;
}
.width-short{
	font-size: clamp(12px, 1rem, 20px);
}
```
##### Evitar Selección de Texto
**Ejemplo**
```css
h1{
	user-select: none;
}
```

