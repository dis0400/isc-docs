<div align="center">

# 📜 __Convenciones de Código__ 📜 

![Convenciones de Código](https://www.aluracursos.com/blog/assets/convenciones-de-nomenclaturas/imagen01portada.jpg)

</div>

## Introducción
<p style="font-size: 17px;">Este documento establece las convenciones de codificación para cada lenguaje de programación establecido. Seguir estas convenciones garantizará un código más limpio, mantenible y eficiente.</p>

### Objetivos
- <p style="font-size: 16px;">Asegurar un código estandarizado y fácil de entender.</p>
- <p style="font-size: 16px;">Evitar errores comunes mediante mejores prácticas.</p>
- <p style="font-size: 16px;">Facilitar la escalabilidad y el mantenimiento del código.</p>
- <p style="font-size: 16px;">Mejorar la colaboración en equipo mediante un estilo de codificación uniforme.</p>

### Referencias
Las convenciones presentadas en este documento han sido extraídas de las siguientes fuentes oficiales y aprobadas:
- **JavaScript:** [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- **TypeScript:** [TypeScript Best Practices 2025 - Dev.to](https://dev.to/sovannaro/typescript-best-practices-2025-elevate-your-code-quality-1gh3)
- **React:** [React Best Practices - FreeCodeCamp](https://www.freecodecamp.org/news/best-practices-for-react/)
- **HTML:** [HTML Best Practices - Kinsta](https://kinsta.com/blog/html-best-practices/)
- **CSS:** [CSS Best Practices - Andre de Sousa](https://github.com/andredesousa/css-best-practices)

---

## 📖 Índice
- [**JavaScript**](#javascript)
  - [Convenciones Generales](#convenciones-generales)
  - [Declaración de Variables](#declaracion-de-variables)
  - [Funciones](#funciones)
- [**TypeScript**](#typescript)
  - [Anotaciones de Tipo](#anotaciones-de-tipo)
  - [Interfaces y Tipos](#interfaces-y-tipos)
  - [Genéricos](#genericos)
- [**React**](#react)
  - [Componentes Funcionales](#componentes-funcionales)
  - [Manejo de Estado](#manejo-de-estado)
  - [Hooks](#hooks)
- [**HTML**](#html)
  - [Estructura del Documento](#estructura-del-documento)
  - [Semántica](#semantica)
  - [Accesibilidad](#accesibilidad)
- [**CSS**](#css)
  - [Organización del Código](#organizacion-del-codigo)
  - [Nomenclatura](#nomenclatura)
  - [Buenas Prácticas](#buenas-practicas)

---

## **JavaScript**

**Referencia:** [JavaScript Best Practices - Airbnb](https://github.com/airbnb/javascript)

### Convenciones Generales
<p style="font-size: 16px;">JavaScript es un lenguaje dinámico ampliamente utilizado en el desarrollo web. Para mantener un código limpio y legible, se deben seguir convenciones de codificación estándar que faciliten su mantenimiento.</p>

### Declaración de Variables
- <p style="font-size: 16px;">Usa `const` y `let` en lugar de `var`.</p>
- <p style="font-size: 16px;">Sigue la nomenclatura camelCase para nombres de variables.</p>

```javascript
// ❌ Incorrect
var name = "Lucia";

// ✅ Correct
const name = "Lucia";
```

### Funciones
- <p style="font-size: 16px;">Usa funciones flecha cuando sea posible.</p>
- <p style="font-size: 16px;">Evita modificar variables globales dentro de funciones.</p>

---

## **TypeScript**

**Referencia:** [TypeScript Best Practices](https://dev.to/sovannaro/typescript-best-practices-2025-elevate-your-code-quality-1gh3)

### Anotaciones de Tipo
<p style="font-size: 16px;">TypeScript permite agregar tipos estáticos a JavaScript, lo que mejora la seguridad del código y evita errores en tiempo de ejecución.</p>

### Interfaces y Tipos
- <p style="font-size: 16px;">Usa `interface` en lugar de `type` cuando sea posible.</p>

```typescript
// ❌ Incorrect
let user: any;

// ✅ Correct
interface User {
  name: string;
  age: number;
}
const user: User = { name: "Lucia", age: 20 }; 
```

### Genéricos
- <p style="font-size: 16px;">Usa genéricos para mejorar la reutilización del código en funciones y clases.</p>

---

## **React**

**Referencia:** [Best Practices for React](https://www.freecodecamp.org/news/best-practices-for-react/)

### Componentes Funcionales
<p style="font-size: 16px;">React permite el desarrollo de interfaces dinámicas mediante componentes reutilizables.</p>

### Manejo de Estado
- <p style="font-size: 16px;">Usa `useState` para gestionar el estado.</p>

### Hooks
- <p style="font-size: 16px;">Usa `useEffect` para manejar efectos secundarios.</p>

```jsx
// ❌ Incorrect
this.state = { counter: 0 };

// ✅ Correct
const [counter, setCounter] = useState(0);
```

---

## **HTML**

**Referencia:** [HTML Best Practices](https://kinsta.com/blog/html-best-practices/) 

### Estructura del Documento
<p style="font-size: 16px;">HTML define la estructura de las páginas web mediante etiquetas organizadas de manera jerárquica.</p>

### Semántica
- <p style="font-size: 16px;">Usa etiquetas como `<header>`, `<article>`, `<section>` para mejorar la legibilidad del código.</p>

### Accesibilidad
- <p style="font-size: 16px;">Usa `alt` en imágenes para facilitar la navegación a usuarios con discapacidades visuales.</p>

```html
<!-- ❌ Incorrect -->
<div class="button">Click here</div>

<!-- ✅ Correct -->
<button>Click here</button>
```

---

## **CSS**

 **Referencia:** [CSS Best Practices](https://github.com/andredesousa/css-best-practices) 

### Organización del Código
<p style="font-size: 16px;">CSS define el estilo de las páginas web y debe mantenerse organizado para facilitar su mantenimiento.</p>

### Nomenclatura
- <p style="font-size: 16px;">Usa nombres de clases claros y consistentes.</p> 

### Buenas Prácticas
- <p style="font-size: 16px;">Usa variables CSS para colores y fuentes.</p>
- <p style="font-size: 16px;">Prefiere `rem` sobre `px` para tamaños.</p>

```css
/* ❌ Incorrect */
div {
  font-size: 14px;
}

/* ✅ Correct */
:root {
  --font-size-base: 1rem;
}
div {
  font-size: var(--font-size-base);
}
```

---

##  **Conclusión**
<p style="font-size: 16px;">Mantener una base de código limpia, organizada y coherente es esencial para garantizar la eficiencia, mantenibilidad y escalabilidad de cualquier proyecto de software. La implementación de estas convenciones de codificación facilita la colaboración entre desarrolladores, reduce errores comunes y mejora la calidad del código a largo plazo.</p>

<p style="font-size: 16px;">Siguiendo estas mejores prácticas en JavaScript, TypeScript, React, HTML y CSS, aseguramos un desarrollo más estructurado y profesional. La consistencia en la escritura del código no solo optimiza el rendimiento del equipo, sino que también permite que futuros desarrolladores puedan comprender y modificar el código con facilidad.</p>