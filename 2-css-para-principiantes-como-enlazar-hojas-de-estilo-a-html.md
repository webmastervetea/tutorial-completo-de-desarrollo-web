# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 🎨 Enlazando CSS a tu HTML

### Paso 1: Crea tu Archivo CSS

Crea un nuevo archivo de texto y guárdalo como `estilos.css` (o cualquier nombre que elijas, siempre terminando en `.css`).

**Ejemplo de Contenido de `estilos.css`:**

```css
body {
    background-color: #f4f4f9; /* Color de fondo muy claro */
    font-family: Arial, sans-serif;
    margin: 40px;
}

h1 {
    color: #333366; /* Un color azul oscuro */
    border-bottom: 2px solid #ffaa00; /* Línea naranja debajo del título */
    padding-bottom: 10px;
}

p {
    font-size: 1.1em;
    line-height: 1.6;
}
```

### Paso 2: Enlaza el Archivo en tu HTML

En tu archivo HTML, debes usar la etiqueta `<link>` dentro de la sección `<head>`.

| Atributo | Propósito |
| :--- | :--- |
| **`rel="stylesheet"`** | Indica que el archivo enlazado es una hoja de estilos. |
| **`href="ruta/al/archivo.css"`** | Especifica la ubicación del archivo CSS. |

**Ejemplo de tu archivo `index.html`:**

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Página con Estilo</title>
    
    <link rel="stylesheet" href="estilos.css">
    
</head>
<body>
    <h1>¡Hola Mundo con Estilo!</h1>
    <p>Este texto ahora usa la fuente y el tamaño definidos en el archivo estilos.css.</p>
</body>
</html>
```

### ✨ Resultado:

Al abrir tu `index.html` en el navegador, aplicará automáticamente los estilos definidos en `estilos.css`:

  * El fondo del cuerpo (`<body>`) será gris claro.
  * El texto usará la fuente Arial.
  * El título principal (`<h1>`) será azul oscuro y tendrá una línea naranja debajo.

-----

