# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]

HTML (HyperText Markup Language) es el código que se usa para estructurar una página web y su contenido. HTML5 es la versión más reciente y ampliamente utilizada.

-----

## 1\. ⚙️ HTML5 Básico: Estructura, Etiquetas y Fundamentos Semántico

Todo documento HTML debe tener una estructura básica para ser reconocido correctamente por los navegadores.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Mi Primera Página Web</title>
</head>
<body>
    </body>
</html>
```

### Explicación de las Etiquetas Clave:

  * `<!DOCTYPE html>`: Define el tipo de documento para que el navegador sepa que es **HTML5**. Siempre va al principio.
  * `<html>`: Es la etiqueta raíz que envuelve todo el contenido de la página.
  * `<head>`: Contiene **metadatos** sobre la página (información que no se muestra directamente, como el título, el juego de caracteres, enlaces a archivos CSS, etc.).
      * `<meta charset="UTF-8">`: Especifica la codificación de caracteres, que permite mostrar tildes, eñes y otros caracteres especiales.
      * `<title>...</title>`: El texto que aparece en la pestaña del navegador.
  * `<body>`: Contiene todo el **contenido visible** para el usuario: textos, imágenes, enlaces, videos, etc.

-----

## 2\. 📝 Etiquetas Comunes para Contenido

Dentro de la etiqueta `<body>`, usarás estas etiquetas para estructurar tu texto:

### Títulos y Párrafos

| Etiqueta | Nombre | Descripción |
| :--- | :--- | :--- |
| `<h1>` a `<h6>` | Encabezados/Títulos | Se utilizan para definir la importancia de los títulos. `<h1>` es el más importante, `<h6>` el menos. |
| `<p>` | Párrafo | Define un bloque de texto común. |
| `<br>` | Salto de Línea | Crea un salto de línea simple. Es una etiqueta **vacía** (no necesita etiqueta de cierre). |

**Ejemplo:**

```html
<h1>Título Principal (el más importante)</h1>
<h2>Subtítulo</h2>
<p>Este es un párrafo de texto en mi nueva página web.</p>
<p>Este es otro párrafo. Aquí hay un salto de línea:<br>Ahora seguimos en la siguiente línea.</p>
```

### Listas

| Etiqueta | Nombre | Descripción |
| :--- | :--- | :--- |
| `<ul>` | Lista Desordenada | Una lista con viñetas. |
| `<ol>` | Lista Ordenada | Una lista con números o letras. |
| `<li>` | Elemento de Lista | Define cada elemento dentro de las listas (`<ul>` o `<ol>`). |

**Ejemplo:**

```html
<h3>Lista de Compras</h3>
<ul>
    <li>Pan</li>
    <li>Leche</li>
    <li>Huevos</li>
</ul>

<h3>Pasos para el Café</h3>
<ol>
    <li>Hervir agua.</li>
    <li>Añadir café molido.</li>
    <li>Servir y disfrutar.</li>
</ol>
```

-----

## 3\. 🔗 Enlaces e Imágenes

El contenido multimedia e interactivo es fundamental en la web:

### Enlaces (Hyperlinks)

La etiqueta `<a>` (de "anchor") se usa para crear enlaces. El atributo **`href`** es obligatorio e indica la URL de destino.

```html
<p>Visita el sitio de <a href="https://www.google.com" target="_blank">Google</a>.</p>

<p><a href="acerca-de.html">Sobre mí</a></p>
```

  * El atributo **`target="_blank"`** hace que el enlace se abra en una pestaña nueva.

### Imágenes

La etiqueta `<img>` inserta una imagen. Es otra etiqueta **vacía**. Los atributos clave son:

  * **`src`** (source): La ruta (URL o ruta de archivo) donde se encuentra la imagen.
  * **`alt`** (alternative text): Texto que se muestra si la imagen no se carga y es fundamental para la accesibilidad (lectores de pantalla).

<!-- end list -->

```html
<img src="imagenes/logo.png" alt="Logotipo de la empresa">
```

-----

## 4\. 🧱 Etiquetas Semánticas de HTML5

HTML5 introdujo etiquetas que dan **significado** a las partes de la página, ayudando a los motores de búsqueda y a la accesibilidad.

| Etiqueta | Significado | Ubicación Común |
| :--- | :--- | :--- |
| `<header>` | Contenido introductorio o un grupo de navegación. | Parte superior de la página o de una sección. |
| `<nav>` | Contiene los enlaces de navegación (menús). | Dentro del `<header>`. |
| `<main>` | El contenido principal y único de la página (solo debe haber uno). | La sección más importante. |
| `<section>` | Un grupo temático de contenido. | Para agrupar contenido relacionado. |
| `<article>` | Un contenido independiente y autocontenido (como una publicación de blog). | Dentro de `<main>` o `<section>`. |
| `<aside>` | Contenido relacionado pero secundario (como una barra lateral). | Generalmente a un lado. |
| `<footer>` | Información de contacto, derechos de autor, enlaces secundarios. | Parte inferior de la página. |

**Estructura Semántica de Ejemplo:**

```html
<body>
    <header>
        <h1>Mi Blog de Viajes</h1>
        <nav>
            <a href="index.html">Inicio</a> | 
            <a href="galeria.html">Galería</a>
        </nav>
    </header>

    <main>
        <article>
            <h2>Mi Primer Viaje a Japón</h2>
            <p>...</p>
        </article>
    </main>

    <footer>
        <p>&copy; 2024 Mi Blog.</p>
    </footer>
</body>
```

-----

