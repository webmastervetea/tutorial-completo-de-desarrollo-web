# Tutorial Completo de Desarrollo Web. [[Soporte](https://www.linkedin.com/in/oscarlizarragag/)]
## ✨ Efecto "Hover" en CSS

El pseudoclase `:hover` permite aplicar estilos a un elemento **solamente** cuando el cursor del ratón está posicionado sobre él. Es el motor detrás de la mayoría de los efectos visuales dinámicos en la web.

### Paso 1: Modificar el CSS

Añadiremos algunas reglas al final de tu archivo `estilos.css` para que la tarjeta cambie y dé una sensación de "elevación" cuando el usuario pase el ratón por encima.

```css
/* ... (el resto de tus estilos.css) ... */

/* Estilos para que la tarjeta reaccione al pasar el ratón */
.tarjeta-perfil:hover {
    /* 1. Cambio de Sombra: Hace que parezca que la tarjeta se levanta */
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2); 
    
    /* 2. Transformación: Mueve ligeramente la tarjeta hacia arriba */
    transform: translateY(-5px); 
    
    /* 3. Cambio de Fondo (Opcional): Un sutil cambio de color */
    background-color: #f7f7f7; 
}

/* 4. Transición (¡Crucial para la suavidad!) */
.tarjeta-perfil {
    /* Agregamos esta regla al estilo principal de la tarjeta para que los 
       cambios (sombra, transformación, fondo) ocurran de forma suave 
       durante 0.3 segundos, en lugar de ser instantáneos. */
    transition: all 0.3s ease;
}
```

### 💡 Explicación de las Propiedades:

1.  **`box-shadow`**: Al pasar el ratón, la sombra se hace más grande y oscura, creando un efecto visual de que la tarjeta se ha "elevado" de la página.
2.  **`transform: translateY(-5px)`**: Mueve el elemento 5 píxeles hacia arriba en el eje Y.
3.  **`transition: all 0.3s ease`**: Esta es la clave. Sin esta línea, los cambios de sombra y posición ocurrirían de forma inmediata (un "salto"). Al agregar `transition`, le dices al navegador que haga la transición de cualquier propiedad (`all`) de forma suave durante **0.3 segundos**.

-----

## 🔁 Resultado y Próximos Pasos

Guarda estos cambios en `estilos.css` y recarga tu `perfil.html`. Ahora, cuando muevas el cursor sobre la tarjeta, verás cómo se mueve suavemente y la sombra se intensifica, mejorando la experiencia del usuario.

Este es un excelente ejemplo de cómo CSS no solo se trata de estética, sino también de **interacción**.

