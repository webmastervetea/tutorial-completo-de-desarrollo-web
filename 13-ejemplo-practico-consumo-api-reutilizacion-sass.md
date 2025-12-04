# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 1\. 🚀 Ejemplo Práctico de JavaScript Asíncrono (`async/await`)

Usaremos la función `fetch` para simular la obtención de datos de una API (una tarea que siempre toma tiempo) y veremos cómo `await` nos permite manejar esos datos de manera limpia.

### A. Estructura HTML (`datos.html`)

Necesitamos un botón para iniciar la acción y un área donde mostraremos los datos obtenidos.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Asincronía JS</title>
</head>
<body>
    <h1>Información de Usuario Asíncrona</h1>
    <button id="btnCargar">Cargar Usuario</button>
    
    <div id="infoUsuario">
        <p>Presiona el botón para cargar los datos del usuario 1.</p>
    </div>

    <script src="script-async.js"></script>
</body>
</html>
```

### B. Código JavaScript (`script-async.js`)

Usaremos `async/await` y la API pública JSONPlaceholder para simular la obtención de un usuario.

```javascript
const btnCargar = document.getElementById("btnCargar");
const infoUsuarioDiv = document.getElementById("infoUsuario");

// 1. Definición de la función asíncrona
async function cargarDatosUsuario() {
    
    // Mostramos un mensaje de carga mientras esperamos la respuesta
    infoUsuarioDiv.innerHTML = "Cargando datos..."; 

    try {
        // 'await' espera la respuesta del servidor (la Promesa se resuelve)
        const respuesta = await fetch("https://jsonplaceholder.typicode.com/users/1");

        // Verificación de error de la red (ej. 404, 500)
        if (!respuesta.ok) {
            throw new Error(`Error HTTP: ${respuesta.status}`);
        }

        // 'await' espera a que la respuesta se convierta a JSON
        const usuario = await respuesta.json(); 

        // 2. Manipulación del DOM con los datos obtenidos
        infoUsuarioDiv.innerHTML = `
            <h2>${usuario.name}</h2>
            <p><strong>Username:</strong> ${usuario.username}</p>
            <p><strong>Email:</strong> ${usuario.email}</p>
            <p><strong>Ciudad:</strong> ${usuario.address.city}</p>
        `;

    } catch (error) {
        // Captura cualquier error (de red o de la promesa)
        infoUsuarioDiv.innerHTML = `<p style="color: red;">Ocurrió un error: ${error.message}</p>`;
        console.error("Fallo al cargar datos:", error);
    }
}

// 3. Asignación del evento
btnCargar.addEventListener("click", cargarDatosUsuario);
```

**Resultado:** Al hacer clic en el botón, el código muestra "Cargando datos..." y, después de unos milisegundos (el tiempo que tarda la red), el contenido del `div` se reemplaza con la información real del usuario obtenida del servidor.

-----

## 2\. 🧱 Ejemplo Práctico de Mixin en SASS/SCSS

Un **Mixin** es una herramienta poderosa para no repetir código CSS. Usaremos un Mixin para crear un efecto de **sombra de caja** con todos los prefijos de navegador necesarios.

### A. Configuración

Asumimos que estás usando un compilador (como Node-SASS o Live SASS Compiler en VS Code) y que tienes un archivo `.scss` que se compila a un archivo `.css`.

### B. Código SCSS (`estilos.scss`)

Definimos el Mixin para la sombra y lo reutilizamos en dos elementos diferentes.

```scss
/* 1. Definición del Mixin para la Sombra */
// El mixin acepta tres parámetros: color, desplazamiento X y desplazamiento Y
@mixin sombra-caja($color, $x, $y) {
  // Aquí se incluyen todos los prefijos que a veces son necesarios
  -webkit-box-shadow: $x $y 10px $color;
  -moz-box-shadow: $x $y 10px $color;
  box-shadow: $x $y 10px $color;
}

/* 2. Uso del Mixin en diferentes elementos */

.caja-clara {
  background-color: white;
  padding: 20px;
  
  // Incluimos el mixin con parámetros específicos
  @include sombra-caja(rgba(0, 0, 0, 0.2), 0px, 4px);
}

.caja-oscura {
  background-color: #333;
  color: white;
  padding: 20px;
  
  // Lo reutilizamos con otros parámetros para un look diferente
  @include sombra-caja(rgba(0, 123, 255, 0.4), 2px, 8px);
}
```

### C. CSS Compilado (Lo que el Navegador ve)

El compilador de SASS genera este CSS automáticamente, eliminando la necesidad de que tú escribas los prefijos repetidamente:

```css
.caja-clara {
  background-color: white;
  padding: 20px;
  -webkit-box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  -moz-box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
}

.caja-oscura {
  background-color: #333;
  color: white;
  padding: 20px;
  -webkit-box-shadow: 2px 8px 10px rgba(0, 123, 255, 0.4);
  -moz-box-shadow: 2px 8px 10px rgba(0, 123, 255, 0.4);
  box-shadow: 2px 8px 10px rgba(0, 123, 255, 0.4);
}
```

El Mixin te permite **cambiar la definición de sombra** en un solo lugar (`@mixin sombra-caja`) y ese cambio se aplicará automáticamente a todos los elementos que lo usen (`.caja-clara` y `.caja-oscura`).

