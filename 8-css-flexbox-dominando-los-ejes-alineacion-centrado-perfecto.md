# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 📐 Entendiendo Flexbox

Flexbox está basado en dos conceptos clave: el **Contenedor** y los **Items** (elementos hijos).

### 1\. El Contenedor Flexible (Flex Container)

Para empezar a usar Flexbox, solo necesitas aplicar una propiedad a la caja principal que contiene los elementos que quieres organizar:

```css
.contenedor-padre {
    display: flex;
}
```

  * Al establecer `display: flex;`, la caja principal se convierte en el **Contenedor Flexible**, y todos sus hijos directos se convierten automáticamente en **Items Flexibles**.

### 2\. Los Ejes de Flexbox

Flexbox organiza el contenido a lo largo de dos ejes:

  * **Eje Principal (`Main Axis`)**: Es la dirección principal en la que se colocan los items. Por defecto, es **horizontal** (de izquierda a derecha).
  * **Eje Cruzado (`Cross Axis`)**: Es el eje perpendicular al principal. Por defecto, es **vertical** (de arriba abajo).

-----

## ⚙️ Propiedades Clave del Contenedor

Estas propiedades se aplican al **Contenedor Padre** (`display: flex;`) y controlan la dirección y alineación de todos sus hijos.

### A. Dirección (`flex-direction`)

Define el Eje Principal (la dirección en la que se ordenan los items).

| Valor | Dirección del Eje Principal |
| :--- | :--- |
| `row` (Por defecto) | Horizontal, de izquierda a derecha. |
| `column` | Vertical, de arriba a abajo. |

### B. Justificación (`justify-content`)

Controla cómo los items se distribuyen y se alinean a lo largo del **Eje Principal**. Ideal para centrar horizontalmente o distribuir el espacio.

| Valor | Resultado |
| :--- | :--- |
| `flex-start` (Por defecto) | Agrupa los items al inicio del eje. |
| **`center`** | **Centra** todos los items en el eje principal. |
| `space-between` | Distribuye el espacio **entre** los items (los extremos tocan los bordes). |
| `space-around` | Distribuye el espacio alrededor de cada item (hay medio espacio en los extremos). |

### C. Alineación (`align-items`)

Controla cómo los items se alinean a lo largo del **Eje Cruzado**. Ideal para centrar verticalmente.

| Valor | Resultado |
| :--- | :--- |
| `flex-start` | Agrupa los items al inicio del eje cruzado. |
| **`center`** | **Centra** los items en el eje cruzado. |
| `stretch` (Por defecto) | Los items se estiran para llenar el contenedor. |

-----

## 🛠️ Ejemplo Práctico: Centrado Perfecto

Un problema común en CSS es **centrar** algo perfectamente (horizontal y verticalmente). Con Flexbox es trivial.

### HTML (El contenedor y el Item a centrar):

```html
<div class="contenedor-padre">
    <div class="caja-centrada">
        Centrado Perfecto
    </div>
</div>
```

### CSS (Aplicamos las propiedades al Contenedor Padre):

```css
.contenedor-padre {
    display: flex;             /* 1. Habilita Flexbox */
    height: 300px;             /* 2. Le damos altura para demostrar el centrado vertical */
    border: 2px solid #333;

    justify-content: center;   /* 3. Centra en el Eje Principal (Horizontal) */
    align-items: center;       /* 4. Centra en el Eje Cruzado (Vertical) */
}

.caja-centrada {
    padding: 20px;
    background-color: lightcoral;
    color: white;
}
```

Al aplicar estas cuatro líneas al contenedor, el texto "Centrado Perfecto" queda justo en el medio.

Flexbox es un tema extenso y muy poderoso, pero dominar estas tres propiedades (`display: flex;`, `justify-content`, y `align-items`) te permitirá resolver el **90%** de los problemas de diseño y maquetación web.

