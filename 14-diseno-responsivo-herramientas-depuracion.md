# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 📱 1. Diseño Web Responsivo (Responsive Design)

El diseño responsivo es la práctica de crear sitios web cuyo diseño se **adapta automáticamente** al tamaño de la pantalla del usuario (escritorio, tablet o móvil). Esto asegura que la experiencia sea óptima en cualquier dispositivo.

### A. La Meta Etiqueta Clave: `viewport`

El primer y más fundamental paso para que un sitio sea responsivo es incluir esta etiqueta dentro del `<head>` de tu HTML. Indica al navegador que la página debe tomar el ancho real del dispositivo.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

  * **`width=device-width`**: Establece el ancho de la página igual al ancho de la pantalla del dispositivo.
  * **`initial-scale=1.0`**: Establece el nivel de zoom inicial en 100%.

### B. La Herramienta Esencial: Media Queries

Las **Media Queries** (Consultas de Medios) son la característica de CSS que te permite aplicar estilos **solamente** si se cumplen ciertas condiciones (la más común es el ancho de la pantalla).

Se definen **puntos de interrupción** (*breakpoints*) donde el diseño cambia.

**Estructura de una Media Query:**

```css
/* Estilos para pantallas grandes (Escritorio - por defecto) */
.columna {
    width: 30%; 
    float: left; /* Usamos float o Flexbox para alinear */
}

/* --- El Breakpoint: Cuando la pantalla es MÁS PEQUEÑA que 600px --- */
@media screen and (max-width: 600px) {
    
    /* El diseño para móvil (los estilos aquí SOBREESCRIBEN los de arriba) */
    .columna {
        width: 100%; /* Las columnas ocupan todo el ancho */
        float: none; /* Desactivamos el alineamiento flotante */
    }
    
    h1 {
        font-size: 1.5em; /* Reducimos el tamaño de la fuente para móvil */
    }
}
```

  * **`@media screen and (max-width: 600px)`**: Significa "Aplica estos estilos si el dispositivo es una pantalla y el ancho máximo es de 600 píxeles".

-----

## 🛠️ 2. Herramientas de Depuración (Debugging) del Navegador

Los errores son inevitables en el desarrollo web. Las **Herramientas para Desarrolladores** (*DevTools*) integradas en los navegadores (Chrome, Firefox, Edge) son tu mejor aliado para encontrar, entender y corregir problemas de código (debugging).

Puedes abrirlas presionando la tecla **`F12`** o haciendo clic derecho en cualquier parte de la página y seleccionando **"Inspeccionar"**.

Las pestañas más importantes son:

### A. Elements (Elementos)

  * **Propósito:** Inspeccionar y modificar en tiempo real el **HTML** y **CSS**.
  * **Uso:** Puedes hacer clic en cualquier elemento de la página y ver inmediatamente qué reglas de CSS (`clase`, `id`, estilos en línea) se le están aplicando, de dónde vienen y qué otras reglas las están **sobreescribiendo**.

### B. Console (Consola)

  * **Propósito:** Depurar **JavaScript** y ver mensajes de error.
  * **Uso:**
      * Muestra los mensajes que tú envías con `console.log()` en tu código JS.
      * Muestra los **errores** de JavaScript (como `Uncaught TypeError`). Los errores aparecen en color rojo e indican la línea exacta de tu archivo `script.js` donde ocurrió el fallo.
      * Te permite **ejecutar código JS** directamente para probar funciones rápidamente.

### C. Sources (Fuentes)

  * **Propósito:** Depurar código JavaScript línea por línea.
  * **Uso:** Puedes añadir **puntos de interrupción** (*breakpoints*). Cuando el código JS llega a un *breakpoint*, se **detiene** la ejecución, lo que te permite examinar los valores de las variables (`let` o `const`) en ese momento exacto y ver cómo se ejecutan las funciones paso a paso.

### D. Network (Red)

  * **Propósito:** Monitorear todas las solicitudes (requests) que tu página hace a servidores externos.
  * **Uso:** Es esencial para el código asíncrono. Te muestra si una solicitud `fetch` falló, si fue exitosa (código 200), cuánto tiempo tardó en cargar y los datos exactos que se recibieron.

Con el **Diseño Responsivo**, tus sitios se verán bien en cualquier pantalla, y con las **Herramientas de Depuración**, siempre sabrás por qué algo no funciona.

