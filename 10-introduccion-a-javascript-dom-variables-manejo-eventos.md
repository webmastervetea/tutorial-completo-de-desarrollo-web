# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 💡 Introducción a JavaScript

JavaScript es un **lenguaje de programación** que te permite implementar características complejas en páginas web, desde actualizaciones de contenido dinámicas hasta mapas interactivos, animación de gráficos 2D/3D y mucho más.

  * **HTML:** El sustantivo (la estructura ósea).
  * **CSS:** El adjetivo (el look y la ropa).
  * **JavaScript:** El verbo (la acción y el comportamiento).

-----

## 🔗 Cómo Enlazar JavaScript

Al igual que con CSS, la mejor práctica es escribir el código JS en un archivo separado y enlazarlo a tu HTML.

### 1\. Crea el Archivo JS

Crea un archivo llamado `script.js`.

### 2\. Enlaza en HTML

Coloca la etiqueta `<script>` en el HTML. La práctica moderna y recomendada es ponerla **justo antes del cierre de la etiqueta `</body>`**.

```html
<body>
    <script src="script.js"></script>
</body>
</html>
```

> **¿Por qué al final del `<body>`?**
> Para asegurar que el navegador **cargue todo el contenido HTML** (como botones, textos, imágenes) antes de intentar ejecutar el código JavaScript. Si JS se carga primero e intenta modificar un elemento que aún no existe, fallará.

-----

## 💻 Conceptos Fundamentales de JS

### 1\. Variables

Las variables son contenedores para almacenar valores de datos. En JavaScript, se declaran principalmente usando `let` y `const`.

  * **`let`**: Para valores que **cambiarán** (variables).
  * **`const`**: Para valores que **no cambiarán** (constantes).

<!-- end list -->

```javascript
// Variable que puede cambiar
let nombreUsuario = "Ana";
nombreUsuario = "Carlos"; 

// Constante que no debe cambiar
const PI = 3.14159; 

// Tipos de datos comunes:
let edad = 30; // Número
let esActivo = true; // Booleano (verdadero/falso)
```

### 2\. Funciones

Una función es un bloque de código diseñado para realizar una tarea particular. Es la forma de **reutilizar** código.

```javascript
// Definición de la función
function saludar(nombre) {
    // La función hace algo
    console.log("Hola, " + nombre + "!");
}

// Llamada o ejecución de la función
saludar("Laura"); // Salida: Hola, Laura!
saludar("Pedro"); // Salida: Hola, Pedro!
```

  * `console.log()` es una herramienta para mostrar mensajes en la consola del navegador, muy útil para hacer pruebas.

### 3\. El DOM (Document Object Model)

El DOM es la **representación en árbol** de tu documento HTML. JavaScript interactúa con el DOM para **modificar el contenido, estructura y estilo** de tu página.

El paso más importante es **seleccionar** un elemento HTML para poder manipularlo.

```javascript
// 1. Seleccionar un elemento por su ID (ej. <h1 id="titulo-principal">)
const titulo = document.getElementById("titulo-principal");

// 2. Modificar el texto de ese elemento
titulo.textContent = "¡Título Modificado por JS!";

// 3. Modificar el estilo de ese elemento
titulo.style.color = "blue";
```

### 4\. Eventos

Los eventos son acciones que ocurren en el sistema (por ejemplo, el usuario haciendo clic en un botón, moviendo el ratón o presionando una tecla). JavaScript te permite "escuchar" esos eventos y ejecutar una función cuando ocurren.

**Ejemplo Práctico: Hacer algo al hacer clic en un botón**

**HTML:**

```html
<button id="miBoton">Haz clic aquí</button>
```

**JavaScript (`script.js`):**

```javascript
// 1. Seleccionamos el botón
const boton = document.getElementById("miBoton");

// 2. Agregamos un "escuchador de eventos" (event listener)
boton.addEventListener("click", function() {
    // 3. La función que se ejecuta al hacer clic
    alert("¡Botón presionado!");
});
```

Este es el mecanismo fundamental para hacer que tu barra de navegación sea interactiva, como cambiar su color al hacer *scroll*, que mencionaste antes, o mostrar/ocultar un menú móvil.
