# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 📝 Formularios (`<form>`)

Los formularios son esenciales para la **interactividad** en la web, ya que permiten a los usuarios ingresar datos (nombres, correos electrónicos, comentarios, etc.).

### Estructura Básica

La etiqueta principal es `<form>`, y contiene los elementos de entrada de datos (`<input>`, `<textarea>`, `<select>`, etc.).

| Atributo Clave de `<form>` | Propósito |
| :--- | :--- |
| **`action`** | Especifica la URL o el archivo al que se enviarán los datos del formulario al ser completado. |
| **`method`** | Define el método HTTP para enviar los datos (`GET` o `POST`). `POST` es más seguro para datos sensibles. |

### Elementos de Entrada (`<input>`)

La etiqueta `<input>` es la más versátil en los formularios. Su comportamiento se define principalmente por el atributo **`type`**.

| `type` | Descripción | Ejemplo de Uso |
| :--- | :--- | :--- |
| **`text`** | Texto simple de una línea (el valor predeterminado). | Nombre de usuario. |
| **`password`** | Oculta el texto ingresado. | Contraseña. |
| **`email`** | Valida que el texto tenga formato de correo electrónico. | Correo electrónico del usuario. |
| **`number`** | Permite solo la entrada de números. | Edad o cantidad de productos. |
| **`checkbox`** | Una casilla de selección (puede seleccionar varias). | Aceptar términos y condiciones. |
| **`radio`** | Un botón de opción (solo puede seleccionar una en un grupo). | Seleccionar género. |
| **`submit`** | El botón para enviar el formulario. | Botón "Enviar" o "Registrar". |

**Ejemplo de Formulario:**

```html
<form action="/procesar-datos" method="POST">
    
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre_usuario" required>
    
    <label for="clave">Contraseña:</label>
    <input type="password" id="clave" name="password" required>
    
    <label for="comentarios">Comentarios:</label>
    <textarea id="comentarios" name="comentario_usuario" rows="4"></textarea>
    
    <input type="submit" value="Enviar Formulario">
    
</form>
```

  * **`label`**: Asocia un texto descriptivo a un control de formulario. El atributo `for` debe coincidir con el `id` del elemento de entrada.
  * **`name`**: **Crucial**. Es el nombre que se usará para identificar el dato cuando se envíe al servidor.
  * **`required`**: Atributo booleano que obliga al usuario a llenar el campo antes de enviar.

-----

## 🎬 2. Videos y Audio

HTML5 simplificó drásticamente la inserción de contenido multimedia con las etiquetas `<video>` y `<audio>`.

### La Etiqueta `<video>`

Permite reproducir videos directamente sin necesidad de *plugins* externos (como Flash).

```html
<video width="640" height="360" controls>
    <source src="mi-video.mp4" type="video/mp4">
    <source src="mi-video.webm" type="video/webm">
    Tu navegador no soporta la etiqueta de video.
</video>
```

#### Atributos Clave de `<video>`:

  * **`controls`**: Muestra los controles de reproducción estándar del navegador (pausa, volumen, barra de progreso).
  * **`autoplay`**: Intenta reproducir el video automáticamente al cargar la página (a menudo bloqueado por navegadores).
  * **`loop`**: Hace que el video se repita indefinidamente.
  * **`poster`**: Una URL de imagen que se muestra mientras el video se está cargando o antes de que el usuario lo reproduzca.
  * **`<source>`**: Permite especificar múltiples archivos de video en diferentes formatos. Esto es crucial para la **compatibilidad**, ya que no todos los navegadores admiten los mismos formatos de video (MP4, WebM, Ogg).

### La Etiqueta `<audio>`

Funciona de manera idéntica a `<video>`, pero solo para archivos de sonido.

```html
<audio controls>
    <source src="musica-fondo.mp3" type="audio/mp3">
    <source src="musica-fondo.ogg" type="audio/ogg">
    Tu navegador no soporta el elemento de audio.
</audio>
```

