# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 🏷️ ¿Qué son los Atributos en HTML?

Los atributos proporcionan **información adicional** sobre un elemento HTML. Siempre se especifican en la **etiqueta de apertura** y generalmente vienen en pares de **nombre/valor** así: `nombre="valor"`.

### 1\. El Atributo `id` (Identificador)

El atributo `id` se usa para dar un **nombre único** a un elemento.

  * **Propósito:** Es crucial para CSS (para aplicar estilos muy específicos) y JavaScript (para manipular ese elemento en concreto).
  * **Regla:** Solo puede haber **un** elemento con ese `id` en toda la página.

<!-- end list -->

```html
<nav id="menu-principal">
    <a href="#inicio">Inicio</a>
    <a href="#contacto">Contacto</a>
</nav>
```

### 2\. El Atributo `class` (Clase)

El atributo `class` se usa para dar un **nombre de grupo** a uno o más elementos.

  * **Propósito:** Es la forma más común de aplicar estilos CSS, ya que permite aplicar el **mismo** estilo a múltiples elementos.
  * **Regla:** Múltiples elementos pueden tener la misma clase, y un elemento puede tener múltiples clases (separadas por espacios).

<!-- end list -->

```html
<p class="alerta">¡Atención! Hay un error en el formulario.</p>
<p>Este es un párrafo normal.</p>
<p class="alerta">Recuerda completar todos los campos.</p>
```

### 3\. El Atributo `style` (Estilo en Línea)

El atributo `style` se usa para aplicar **estilos CSS directamente** a un solo elemento HTML.

  * **Propósito:** Se usa para aplicar un estilo rápido y muy específico. **No** es la práctica recomendada para el diseño general (para eso es el archivo CSS externo), pero es útil para pruebas o excepciones.

<!-- end list -->

```html
<h2 style="color: blue; background-color: yellow;">Soy un título con estilo en línea</h2>
```

-----

## 📊 La Etiqueta `<table>` (Tablas)

Las tablas HTML se usan para mostrar **datos tabulares** (filas y columnas).

### Estructura Básica de una Tabla

| Etiqueta | Nombre | Descripción |
| :--- | :--- | :--- |
| `<table>` | Tabla | El contenedor principal de toda la tabla. |
| `<tr>` | Fila de Tabla | Define una **fila** dentro de la tabla. |
| `<th>` | Encabezado de Tabla | Define una **celda de encabezado** (generalmente se muestra en negrita y centrado). Va dentro de un `<tr>`. |
| `<td>` | Dato de Tabla | Define una **celda de datos** estándar. Va dentro de un `<tr>`. |

**Ejemplo de Código:**

```html
<table>
    <tr>
        <th>Producto</th>
        <th>Precio</th>
        <th>Stock</th>
    </tr>
    <tr>
        <td>Laptop X</td>
        <td>$1200</td>
        <td>15</td>
    </tr>
    <tr>
        <td>Monitor Z</td>
        <td>$350</td>
        <td>28</td>
    </tr>
</table>
```

### 🧑‍💻 Consejos Adicionales para Tablas

  * **`<thead>`, `<tbody>`, `<tfoot>`**: Estas etiquetas se usan para organizar la tabla semánticamente en una **cabeza** (encabezados de columna), un **cuerpo** (los datos) y un **pie** (totales o notas). Esto es útil para accesibilidad y CSS.
  * **`rowspan` y `colspan`**: Atributos que permiten que una celda se extienda a través de varias filas (`rowspan`) o varias columnas (`colspan`).

-----

