# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 🖱️ Manipulación del DOM con un Botón

### Paso 1: Estructura HTML (`dom-interactivo.html`)

Aquí necesitamos tres cosas:

1.  Un título para mostrar el texto original.
2.  Un párrafo que usaremos como **área de cambio**. Le daremos un **`id="texto-dinamico"`** para que JavaScript pueda encontrarlo fácilmente.
3.  Un botón. Le daremos un **`id="boton-cambio"`** para que JavaScript pueda "escuchar" el evento `click`.

<!-- end list -->

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Interacción JS</title>
</head>
<body>
    <h1>Ejemplo de Manipulación DOM</h1>

    <p id="texto-dinamico">
        Este es el texto original. Haz clic en el botón para cambiarlo.
    </p>

    <button id="boton-cambio">Cambiar Texto</button>

    <script src="script.js"></script>
</body>
</html>
```

-----

### Paso 2: El Código JavaScript (`script.js`)

En este archivo, haremos tres pasos clave: **Seleccionar**, **Definir la Función** y **Asignar el Evento**.

```javascript
// 1. SELECCIONAR ELEMENTOS (Obtener las referencias del DOM)
// Usamos const porque estas referencias no van a cambiar.

// Referencia al párrafo (el elemento que vamos a modificar)
const parrafo = document.getElementById("texto-dinamico");

// Referencia al botón (el elemento que va a desencadenar la acción)
const boton = document.getElementById("boton-cambio");


// 2. DEFINIR LA FUNCIÓN (La acción que queremos realizar)
function cambiarContenido() {
    // Verificamos cuál es el texto actual y lo cambiamos por el opuesto.
    if (parrafo.textContent === "¡El contenido ha sido modificado por JavaScript!") {
        parrafo.textContent = "¡Volvimos al texto original! Vuelve a hacer clic.";
        parrafo.style.color = "black";
    } else {
        parrafo.textContent = "¡El contenido ha sido modificado por JavaScript!";
        // También podemos usar JS para modificar estilos CSS directamente:
        parrafo.style.color = "blue";
    }
}


// 3. ASIGNAR EL EVENTO (Conectar la función al botón)
// Le decimos al botón: "Cuando ocurra un 'click', ejecuta la función cambiarContenido"
boton.addEventListener("click", cambiarContenido);
```

-----

### ✨ Resultado:

Al guardar estos dos archivos y abrir `dom-interactivo.html` en tu navegador, y luego hacer clic en el botón:

  * JavaScript **selecciona** los elementos por su `id`.
  * El `addEventListener` detecta el **evento** `click`.
  * Se ejecuta la función `cambiarContenido()`, que manipula el **DOM** usando la propiedad `textContent` para cambiar el texto y la propiedad `style.color` para cambiar el color.

Esto te muestra el poder de JS para reaccionar a la interacción del usuario y modificar cualquier parte de tu página.
