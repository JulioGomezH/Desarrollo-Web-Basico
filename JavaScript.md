## Que es Javascript
Es un lenguaje de programacion que se utiliza principalmente para crear paginas web dinamicas.
Una pagina web dinamica es aquella que incorpora efectos como texto que aparece y desaparece, animaciones, acciones que se activan al pulsar botones y ventanas con mensajes de aviso al usuario.

JavaScript es un lenguaje de programacion interpretado, por lo que no es necesario compilar los programas para ejecutarlos. Los programas escritos en js se pueden probar directamente en cualquier navegador sin necesidad de procesos intermedios.

## DOM
La creacion del **Document Object Model** o DOM es una de las innovaciones que mas ha influido en el desarrollo de las paginas web dinamicas y de las aplicaciones web mas complejas.

DOM permite a los programadores web acceder y manipular las paginas XHTML como si fueran documentos xml. DOM se diseño originalmente para manipular de forma sencilla los documentos XML.
### Árbol de nodos
Una de las tareas habituales en la programacion de aplicaciones web con javascript consiste en la manipulacion de las paginas web. De esta forma 

#### Función para cargar contenido via AJAx

```js
// Funcion para cargar contenido via AJAx
function loadcontent(page){
	const xhr = new XMLHttpRequest();
	xhr.open('GET', page + '.php', true);
	xhr.onload = function() {
		if(xhr.status === 200) {
		document.getElementById('main-content').innerHTML = xhr.responseText;
		} else {
			document.getElementById('main-content').innerHTML = '<p> Error al cargar el contenido. </p>'
		}
	};
	xhr.send();
}

// Capturamos los enlaces del sidebar
document.querySelectorAll('.load-content').forEach(function(link) {
	link.addEventListener('click', function(e){
		e.preventDefault();
		
		const page = this.getAttribute('data-page');
		loadcontent(page);
		});
});
```
