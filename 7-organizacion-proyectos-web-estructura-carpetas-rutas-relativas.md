# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 📂 Organización de Proyectos Web (Estructura de Carpetas)

Cuando empiezas a construir un sitio web, es esencial mantener los diferentes tipos de archivos separados y organizados. Esto hace que sea más fácil para ti (y para cualquier otra persona que trabaje en el proyecto) encontrar y actualizar el código.



Una estructura de proyecto típica se ve así:

### 1. 📁 Carpeta Raíz (Root Folder)

Esta es la carpeta principal que contiene absolutamente todo el proyecto. Puedes llamarla como quieras (por ejemplo, `MiSitioWeb` o `ProyectoFinal`).

* **`index.html`**: Este archivo siempre va en la raíz. Es la **página de inicio** por defecto de casi cualquier sitio web.

### 2. 🎨 Carpeta `css/`

Esta carpeta almacena todas tus **hojas de estilo** (los archivos que dan diseño a tu sitio).

* `css/estilos.css` (o `css/main.css`): Aquí es donde va el CSS principal que enlazamos en el ejercicio anterior.
* `css/responsive.css`: Podrías tener un archivo separado para reglas de diseño móvil.

### 3. 🖼️ Carpeta `img/` (o `images/`)

Esta carpeta guarda todo el **contenido visual** de tu sitio que no sea código.

* `img/logo.png`
* `img/perfil.jpg`
* `img/fondo.webp`

### 4. 📝 Carpeta `pages/` (Opcional, pero Común)

Aunque las páginas pueden ir en la raíz, a veces se usan subcarpetas para organizar páginas secundarias.

* `pages/acerca-de.html`
* `pages/contacto.html`

### 5. 💡 Carpeta `js/` (JavaScript)

Esta carpeta guarda los archivos que añaden **interactividad avanzada** (como carruseles de imágenes, validaciones complejas de formularios, etc.).

* `js/scripts.js`
* `js/main.js`

---

## 🎯 Importancia de las Rutas (Paths)

Cuando organizas tus archivos de esta manera, debes asegurarte de que tus enlaces HTML y CSS apunten a la ubicación correcta usando las **rutas**.

### Tipos de Rutas

#### 1. Rutas Relativas (Recomendadas)

Una ruta relativa describe la ubicación de un archivo **en relación con el archivo actual**.

| Situación | Código de Enlace | Explicación |
| :--- | :--- | :--- |
| **Enlazar CSS** (Desde `index.html` a `css/estilos.css`) | `<link rel="stylesheet" href="css/estilos.css">` | Entra en la carpeta `css/` y busca `estilos.css`. |
| **Insertar Imagen** (Desde `index.html` a `img/logo.png`) | `<img src="img/logo.png" alt="Logo">` | Entra en la carpeta `img/` y busca `logo.png`. |
| **Subir de nivel** (Desde una página en `pages/` a `index.html`) | `<a href="../index.html">Inicio</a>` | `../` significa **"sube un nivel"** (sale de `pages/`) y luego busca `index.html`. |

#### 2. Rutas Absolutas

Una ruta absoluta es la dirección completa de un archivo, generalmente comenzando con `http://` o `https://`.

* **Ejemplo:** `<img src="https://www.misitio.com/img/foto.jpg">`

---

Saber cómo organizar tus archivos y usar rutas correctas es un paso crucial para trabajar en proyectos grandes.

