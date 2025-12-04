# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 🧭 Barra de Navegación con Flexbox

Vamos a crear una barra de navegación con un logotipo a la izquierda y los enlaces de navegación a la derecha, garantizando que el diseño sea fácil de mantener y responsivo.

### Paso 1: Estructura HTML (`nav.html`)

Usaremos la etiqueta semántica `<nav>` como nuestro **Contenedor Flexible** y una lista desordenada `<ul>` para los enlaces, lo que es una buena práctica de accesibilidad.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Barra de Navegación Flexbox</title>
    <link rel="stylesheet" href="nav-estilos.css">
</head>
<body>
    <nav class="navbar">
        <div class="logo">Mi Marca</div>
        
        <ul class="nav-links">
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#productos">Productos</a></li>
            <li><a href="#servicios">Servicios</a></li>
            <li><a href="#contacto">Contacto</a></li>
        </ul>
    </nav>
</body>
</html>
```

-----

### Paso 2: Estilos CSS (`nav-estilos.css`)

Aquí aplicamos `display: flex;` al contenedor principal (`.navbar`) y utilizamos `justify-content` para la distribución.

```css
/* 1. Estilos de Reseteo Básico */
body {
    margin: 0;
    font-family: Arial, sans-serif;
}

/* 2. EL CONTENEDOR FLEXIBLE */
.navbar {
    background-color: #333;
    padding: 15px 30px;
    color: white;
    
    /* ¡LA CLAVE DE FLEXBOX! */
    display: flex; 
    
    /* Distribuye los elementos en el Eje Principal (horizontal): 
       'Mi Marca' (izquierda) y 'nav-links' (derecha) */
    justify-content: space-between; 
    
    /* Centra los elementos a lo largo del Eje Cruzado (vertical) */
    align-items: center; 
}

/* 3. Estilos de la Lista de Enlaces (UL) */
.nav-links {
    list-style: none; /* Elimina las viñetas */
    margin: 0;
    padding: 0;
    
    /* Aplicamos Flexbox también a la lista para alinear los LI horizontalmente */
    display: flex;
}

/* 4. Estilos de cada Elemento de Lista (LI) */
.nav-links li {
    margin-left: 20px; /* Espacio entre cada enlace */
}

/* 5. Estilos de los Enlaces (A) */
.nav-links a {
    color: white;
    text-decoration: none; /* Elimina el subrayado */
    padding: 5px 10px;
}

/* 6. Efecto Hover para Interactividad */
.nav-links a:hover {
    background-color: #555;
    border-radius: 4px;
}
```

-----

### 💡 Análisis del Código Flexbox

El corazón del diseño es el estilo aplicado a `.navbar`:

  * `display: flex;`: Convierte el `nav` en un contenedor flexible.
  * `justify-content: space-between;`: Esto toma los dos elementos hijos (`.logo` y `.nav-links`) y los empuja a los extremos opuestos del contenedor, dejando el espacio en el medio.
  * `align-items: center;`: Asegura que el logotipo y la lista de enlaces estén perfectamente **centrados verticalmente** uno con respecto al otro.

Además, aplicamos `display: flex;` a la lista (`.nav-links`) para que sus elementos hijos (`<li>`) se coloquen también en línea recta, uno al lado del otro.

Al combinar Flexbox con la estructura semántica de HTML, obtienes un diseño de barra de navegación robusto y muy fácil de modificar.

