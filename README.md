# Javascript Document Object Model (DOM)
## Metodos más utilizados
### En esta lista cubriremos lo esencial para trabajar con el DOM de manera efectiva y clara para un principiante. Con ella podremos:
- Seleccionar elementos: `1 getElementById()`, `2 querySelector()`, `3 querySelectorAll()`.
- Crear elementos: `13 createElement()`, `20 createTextNode()`, `18 cloneNode()`.
- Navegación: `14 parentElement`, `15 children`, `16 firstElementChild`, `16 lastElementChild`, `17 nextElementSibling`, `17 lastElementSibling`.
- Manipular contenido: `4 textContent`, `5 innerHTML`, `6 innerText`.
- Manipular estilos y clases: `7 style`, `8 classList`.
- Atributos: `9 setAttribute()`, `9 getAttribute()`.
- Manipular el DOM: `10 appendChild()`, `11 remove()`, `19 removeChild()`.
- Escuchar eventos: `12 addEventListener()`.
  
&emsp;
### 1. `document.getElementById()`:
- Descripción: Selecciona un elemento HTML por su atributo id. Es muy rápido y eficiente para seleccionar elementos específicos.
- Uso: Modificar el contenido, cambiar estilos, añadir clases, etc.
- Ejemplo de uso: 
```html
<p id="miParrafo">Texto original</p>
```
```javascript
  const parrafo = document.getElementById('miParrafo');
  parrafo.textContent = 'Texto modificado';
```
&emsp;
### 2. `document.querySelector()`:
- Descripción: Selecciona el primer elemento que coincida con un selector CSS (por ejemplo, #id, .clase, elemento)
- Uso: Flexibilidad para seleccionar elementos utilizando cualquier selector CSS.
- Ejemplo de uso: 
```html
<p class="mensaje">Mensaje 1</p>
<p class="mensaje">Mensaje 2</p>
```
```javascript
  const primerMensaje = document.querySelector('.mensaje');
  primerMensaje.textContent = 'Nuevo mensaje';
```
&emsp;
### 3. `document.querySelectorAll()`:
- Descripción: Selecciona todos los elementos que coincidan con un selector CSS y devuelve una lista (NodeList) de ellos.
- Uso: Aplicar cambios a múltiples elementos.
- Ejemplo de uso: 
```html
<p class="mensaje">Mensaje 1</p>
<p class="mensaje">Mensaje 2</p>
```
```javascript
  const mensajes = document.querySelectorAll('.mensaje');
  mensajes.forEach((mensaje) => {
    mensaje.style.color = 'red';
  });
```
&emsp;
### 4. `element.textContent()`:
- Descripción: Obtiene o establece el contenido textual de un elemento.
- Uso: Cambiar o leer el texto dentro de un elemento.
- Ejemplo de uso: 
```html
<p id="miParrafo">Texto inicial</p>
```
```javascript
  const parrafo = document.getElementById('miParrafo');
  console.log(parrafo.textContent);  // Imprime "Texto inicial"
  parrafo.textContent = 'Texto actualizado';
```
&emsp;
### 5. `element.innerHTML()`:
- Descripción: Obtiene o establece el contenido HTML dentro de un elemento. Permite insertar elementos HTML.
- Uso: Insertar o modificar contenido con etiquetas HTML.
- Ejemplo de uso: 
```html
<div id="contenedor"></div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  contenedor.innerHTML = '<p>Este es un párrafo dentro del contenedor</p>';
```
&emsp;
### 6. `element.innerText`:
- Descripción: Similar a `textContent`, pero tiene en cuenta el estilo y solo muestra el texto visible. También puede provocar un reflow (volver a calcular la disposición de los elementos de la web), lo que puede hacerla menos eficiente que `textContent`.
- Uso: Obtener o establecer solo el texto visible de un elemento.
- Ejemplo de uso: 
```html
<p id="textoOculto" style="display:none">Este texto está oculto</p>
```
```javascript
  const textoOculto = document.getElementById('textoOculto');
  console.log(textoOculto.textContent);  // Imprime el texto aunque esté oculto
  console.log(textoOculto.innerText);    // No imprime nada porque está oculto
```
&emsp;
### 7. `element.style`:
- Descripción: Permite cambiar estilos CSS en línea de un elemento HTML.
- Uso: Cambiar el aspecto visual de un elemento directamente desde JavaScript.
- Ejemplo de uso: 
```html
<p id="miParrafo">Texto con estilo</p>
```
```javascript
  const parrafo = document.getElementById('miParrafo');
  parrafo.style.color = 'blue';
  parrafo.style.fontSize = '20px';
```
&emsp;
### 8. `element.classList`:
- Descripción: Permite agregar (.add), eliminar (.remove) o alternar (.toggle) clases CSS en un elemento.
- Uso: Manipular clases para aplicar o eliminar estilos.
- Ejemplo de uso: 
```html
<p id="miParrafo" class="rojo">Texto con clase</p>
```
```javascript
  const parrafo = document.getElementById('miParrafo');
  parrafo.classList.add('negrita');  // Agrega la clase 'negrita'
  parrafo.classList.remove('rojo');  // Elimina la clase 'rojo'
  parrafo.classList.toggle('oculto');  // Alterna la clase 'oculto'
```
&emsp;
### 9. `element.setAttribute() & element.getAttribute()`:
- Descripción: Establece o obtiene el valor de un atributo de un elemento HTML.
- Uso: Manipular atributos como 'src', 'alt', 'href'...
- Ejemplo de uso: 
```html
<img id="miImagen" src="imagen1.jpg" alt="Imagen 1">
```
```javascript
  const imagen = document.getElementById('miImagen');
  imagen.setAttribute('src', 'imagen2.jpg');  // Cambia la imagen
  console.log(imagen.getAttribute('alt'));    // Obtiene el atributo 'alt'
```
&emsp;
### 10. `element.appendChild()`:
- Descripción: Añade un nodo hijo (elemento) al final de la lista de hijos de un elemento padre.
- Uso: Insertar nuevos elementos dinámicamente.
- Ejemplo de uso: 
```html
<div id="contenedor"></div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  const nuevoParrafo = document.createElement('p');
  nuevoParrafo.textContent = 'Nuevo párrafo';
  contenedor.appendChild(nuevoParrafo);  // Añade el párrafo al contenedor
```
&emsp;
### 11. `element.remove()`:
- Descripción: Elimina un elemento del DOM.
- Uso: Quitar elementos de la página.
- Ejemplo de uso: 
```html
<p id="miParrafo">Texto a eliminar</p>
```
```javascript
  const parrafo = document.getElementById('miParrafo');
  parrafo.remove();  // Elimina el párrafo del DOM
```
&emsp;
### 12. `element.addEventListener()`:
- Descripción: Añade un "escuchador" de eventos a un elemento. Escucha eventos como clics, teclas, etc.
- Uso: Responder a eventos del usuario como clics o cambios de formularios.
- Ejemplo de uso: 
```html
<button id="miBoton">Haz clic</button>
```
```javascript
  const boton = document.getElementById('miBoton');
  boton.addEventListener('click', () => {
    alert('¡Botón pulsado!');
  });
```
&emsp;
### 13. `element.createElement()`:
- Descripción: Crea un nuevo elemento HTML.
- Uso: Generar elementos de forma dinámica en el DOM.
- Ejemplo de uso: 
```html
<div id="contenedor"></div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  const nuevoElemento = document.createElement('p');
  nuevoElemento.textContent = 'Soy un nuevo párrafo';
  contenedor.appendChild(nuevoElemento);  // Añade el nuevo párrafo
```
&emsp;
### 14. `element.parentElement`:
- Descripción: Devuelve el elemento padre inmediato de un nodo en el DOM.
- Uso: Subir en la jerarquía del DOM para acceder a elementos padres.
- Ejemplo de uso: 
```html
<div id="padre">
  <p id="hijo">Soy el hijo</p>
```
```javascript
  const hijo = document.getElementById('hijo');
  console.log(hijo.parentElement.id);  // Imprime "padre"
```
&emsp;
### 15. `element.children`:
- Descripción: Devuelve una colección HTML de los elementos hijos de un nodo.
- Uso: Acceder a todos los elementos hijos dentro de un contenedor.
- Ejemplo de uso: 
```html
<div id="contenedor">
  <p>Hijo 1</p>
  <p>Hijo 2</p>
</div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  console.log(contenedor.children);  // Devuelve una colección con los dos <p>
```
&emsp;
### 16. `element.firstElementChild & element.lastElementChild`:
- Descripción: Devuelve el primer y último elemento hijo de un nodo, respectivamente.
- Uso: Rápido acceso al primer o último hijo de un contenedor.
- Ejemplo de uso: 
```html
<div id="contenedor">
  <p>Primer hijo</p>
  <p>Último hijo</p>
</div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  console.log(contenedor.firstElementChild.textContent);  // Imprime "Primer hijo"
  console.log(contenedor.lastElementChild.textContent);   // Imprime "Último hijo"
```
&emsp;
### 17. `element.nextElementSibling & element.previousElementSibling`:
- Descripción: Devuelven el siguiente y anterior hermano (elemento) de un nodo en el DOM.
- Uso: Navegar entre elementos hermanos.
- Ejemplo de uso: 
```html
<div>
  <p id="primero">Primero</p>
  <p id="segundo">Segundo</p>
  <p id="tercero">Tercero</p>
</div>
```
```javascript
  const segundo = document.getElementById('segundo');
  console.log(segundo.previousElementSibling.textContent);  // Imprime "Primero"
  console.log(segundo.nextElementSibling.textContent);      // Imprime "Tercero"
```
&emsp;
### 18. `element.cloneNode()`:
- Descripción: Clona un nodo, con la opción de clonar también sus elementos hijos (deep clone).
- Uso: Duplicar elementos sin modificar el original.
- Ejemplo de uso: 
```html
<div id="original">Texto original</div>
```
```javascript
  const original = document.getElementById('original');
  const copia = original.cloneNode(true);  // Clona el div con su contenido
  document.body.appendChild(copia);        // Añade la copia al final del body
```
&emsp;
### 19. `element.removeChild()`:
- Descripción: Elimina un nodo hijo específico de un elemento padre.
- Uso: Quitar un elemento hijo de su elemento padre.
- Ejemplo de uso: 
```html
<div id="contenedor">
  <p id="hijo">Soy el hijo</p>
</div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  const hijo = document.getElementById('hijo');
  contenedor.removeChild(hijo);  // Elimina el párrafo del contenedor
```
&emsp;
### 20. `createTextNode()`:
- Descripción: Crea un nodo de texto. Útil si quieres añadir texto sin usar `innerHTML` o `textContent`.
- Uso: Añadir nodos de texto puro al DOM.
- Ejemplo de uso: 
```html
<div id="contenedor"></div>
```
```javascript
  const contenedor = document.getElementById('contenedor');
  const texto = document.createTextNode('Este es un texto creado');
  contenedor.appendChild(texto);  // Añade el nodo de texto al contenedor
```
