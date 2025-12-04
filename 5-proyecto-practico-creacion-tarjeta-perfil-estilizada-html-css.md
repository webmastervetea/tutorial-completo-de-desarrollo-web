# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## 💻 El Ejemplo Práctico: Tarjeta de Perfil

### Paso 1: Crea la Estructura HTML

Crea un archivo llamado `perfil.html`. Usaremos las etiquetas semánticas de HTML5 (`<section>`, `<h1>`, `<p>`) y, crucialmente, la etiqueta `<link>` para conectar nuestro CSS, además de un atributo `class` para poder aplicar estilos específicos.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Tarjeta de Perfil</title>
    
    <link rel="stylesheet" href="estilos.css">
    
</head>
<body>
    <div class="tarjeta-perfil">
        
        <img src="https://via.placeholder.com/150" alt="Foto de perfil del usuario" class="foto-perfil">
        
        <h1>Ana García</h1>
        
        <h2>Desarrolladora Web Jr.</h2>
        
        <p class="descripcion">
            Apasionada por el diseño web y las interfaces de usuario. 
            Me encanta aprender nuevas tecnologías y crear soluciones accesibles.
        </p>
        
        <p class="contacto">
            📧 ana.garcia@email.com
        </p>
    </div>
</body>
</html>
```

-----

### Paso 2: Aplica los Estilos CSS

Crea un segundo archivo llamado `estilos.css` en la misma carpeta que `perfil.html`. Estos estilos transformarán la estructura anterior en una tarjeta visualmente atractiva.

```css
/* 1. Estilos Globales para el cuerpo */
body {
    background-color: #f0f2f5; /* Fondo gris claro */
    font-family: 'Helvetica Neue', sans-serif;
    display: flex; /* Centra el contenido horizontal y verticalmente */
    justify-content: center;
    align-items: center;
    height: 100vh; /* Ocupa el 100% de la altura de la ventana */
    margin: 0;
}

/* 2. Estilos para la Tarjeta de Perfil */
.tarjeta-perfil {
    background-color: white; /* Fondo blanco para la tarjeta */
    padding: 30px;
    border-radius: 12px; /* Esquinas redondeadas */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Sombra suave para darle profundidad */
    text-align: center;
    width: 300px;
}

/* 3. Estilos para la Imagen */
.foto-perfil {
    width: 120px;
    height: 120px;
    border-radius: 50%; /* Esto hace que la imagen sea perfectamente circular */
    border: 4px solid #007bff; /* Borde azul para destacar */
    margin-bottom: 20px;
}

/* 4. Estilos para los Textos */
h1 {
    color: #333;
    font-size: 1.8em;
    margin-bottom: 5px;
}

h2 {
    color: #007bff; /* Título secundario en color azul */
    font-size: 1em;
    font-weight: normal;
    margin-top: 0;
    margin-bottom: 15px;
}

.descripcion {
    color: #666;
    line-height: 1.5;
    font-size: 0.9em;
}

.contacto {
    margin-top: 25px;
    padding-top: 15px;
    border-top: 1px dashed #ccc; /* Línea de separación */
    color: #007bff;
    font-weight: bold;
}
```

### ✨ Resultado Final

Cuando abras el archivo `perfil.html` en tu navegador, la estructura simple de HTML se transformará en una **tarjeta centrada**, con **esquinas redondeadas**, una **sombra suave**, una **foto circular** con un borde azul y colores definidos para los textos.

Este ejemplo ilustra cómo:

1.  **HTML** (con la clase `tarjeta-perfil` y la clase `foto-perfil`) **define la estructura** y el propósito del contenido.
2.  **CSS** (`estilos.css`) **define la apariencia** (tamaño, color, posición, bordes, sombras) de esos elementos estructurales.

