# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 1\. 🌐 JavaScript Avanzado: Asincronía y APIs

La **asincronía** es esencial porque en el desarrollo web moderno, la mayoría de las operaciones clave (como cargar datos de un servidor, descargar imágenes o esperar la respuesta de un usuario) toman tiempo.

Si estas operaciones fueran **síncronas** (una detrás de la otra), la página web se "congelaría" hasta que cada tarea terminara. La asincronía permite que el navegador **continúe ejecutando otras tareas** mientras espera que las tareas lentas finalicen.

### A. El Problema: Bloqueo Síncrono

Imagina que le pides a un chef (el navegador) que haga dos cosas: cortar verduras (rápido) y asar un pavo (lento).

  * **Síncrono:** El chef se queda quieto esperando que el pavo se ase antes de hacer cualquier otra cosa.
  * **Asíncrono:** El chef pone el pavo en el horno y, **mientras espera**, corta las verduras y prepara la mesa.

### B. Solución JS: `Promises` y `async/await`

Las **Promises** son objetos que representan la eventual finalización (o falla) de una operación asíncrona.

La sintaxis moderna y más legible para manejar esto es **`async/await`**:

```javascript
// La función declarada como 'async' indica que contendrá operaciones asíncronas
async function obtenerDatos() {
    console.log("1. Empezando a obtener datos...");
    
    // 'await' pausa la ejecución de esta función hasta que la 'fetch' termine (sin bloquear el navegador)
    const respuesta = await fetch("https://jsonplaceholder.typicode.com/users/1"); 
    
    // Una vez que tenemos la respuesta, la convertimos a formato JSON, también asíncrono
    const datosUsuario = await respuesta.json(); 
    
    console.log("2. Datos obtenidos:", datosUsuario.name);
}

// 3. El código fuera de la función se ejecuta inmediatamente
console.log("3. Mientras tanto, este código sigue corriendo.");

obtenerDatos(); 
// La salida en la consola será:
// 1. Empezando a obtener datos...
// 3. Mientras tanto, este código sigue corriendo.
// 2. Datos obtenidos: Leanne Graham (cuando el servidor responda)
```

### C. Web APIs (APIs del Navegador)

Las **APIs** (Interfaces de Programación de Aplicaciones) son conjuntos de reglas que permiten que diferentes programas o servicios se comuniquen entre sí.

  * **APIs del Navegador/Web APIs:** Son funcionalidades incorporadas en los navegadores. Ejemplos incluyen el **DOM**, la API de **`Geolocation`** (para obtener la ubicación del usuario) o, la más común para obtener datos: **`fetch`**.
  * **APIs Externas/De Terceros:** Servicios externos (como las APIs de Twitter, Google Maps o bases de datos) a las que accedemos usando la función `fetch` (como en el ejemplo de arriba) para obtener información.

-----

## 2\. 💅 CSS Avanzado: Preprocesadores (SASS/SCSS)

A medida que los proyectos CSS crecen, pueden volverse repetitivos y difíciles de mantener. Los **Preprocesadores de CSS** te permiten usar programación lógica dentro de tu código de estilos.

El más popular es **SASS** (Syntactically Awesome Stylesheets).

**¿Cómo funcionan?**
Tú escribes código en formato SASS/SCSS. Luego, una herramienta externa (un **compilador**) lo **traduce** a CSS puro, que es lo que el navegador realmente entiende.

### A. Funcionalidades Clave de SASS

#### 1\. Variables

Te permiten almacenar valores (colores, tamaños de fuente) y reutilizarlos. Si necesitas cambiar el color principal de tu sitio, lo cambias en un solo lugar.

**SCSS:**

```scss
$color-principal: #007bff;
$fuente-base: 16px;

.boton {
  background-color: $color-principal;
  font-size: $fuente-base;
}

.enlace {
  color: $color-principal;
  font-size: $fuente-base;
}
```

**CSS Compilado:**

```css
.boton {
  background-color: #007bff;
  font-size: 16px;
}

.enlace {
  color: #007bff;
  font-size: 16px;
}
```

#### 2\. Anidamiento (`Nesting`)

Permite anidar selectores de CSS unos dentro de otros, reflejando la estructura del HTML y reduciendo la repetición de selectores padres.

**SCSS:**

```scss
.navbar {
  background-color: #333;

  ul { // Aplica a ul dentro de .navbar
    margin: 0;
    
    li { // Aplica a li dentro de .navbar ul
        list-style: none;
    }
  }
}
```

**CSS Compilado:**

```css
.navbar {
  background-color: #333;
}
.navbar ul {
  margin: 0;
}
.navbar ul li {
  list-style: none;
}
```

#### 3\. Mixins

Permiten definir un bloque de código CSS reutilizable (similar a una función en JavaScript) que puedes incluir en cualquier selector. Son muy útiles para prefijos de navegadores o estilos complejos.

**SCSS:**

```scss
@mixin borde-redondo($radio) {
  -webkit-border-radius: $radio;
  -moz-border-radius: $radio;
  border-radius: $radio;
}

.caja-perfil {
  @include borde-redondo(10px);
  padding: 20px;
}
```

Dominar la asincronía en JavaScript y los preprocesadores en CSS son hitos clave que te permitirán crear aplicaciones web mucho más robustas y fáciles de mantener.

