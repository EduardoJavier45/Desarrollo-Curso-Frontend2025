# 01 - Introducción a CSS3: Guía Completa para Principiantes

**Fecha:** 16 de octubre de 2025  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End  
**Tema:** CSS3 - Cascading Style Sheets (Hojas de Estilo en Cascada)

---

## 📚 Índice

1. [¿Qué es CSS?](#qué-es-css)
2. [¿Por qué necesitamos CSS?](#por-qué-necesitamos-css)
3. [Cómo funciona CSS](#cómo-funciona-css)
4. [Formas de agregar CSS](#formas-de-agregar-css)
5. [Sintaxis básica de CSS](#sintaxis-básica-de-css)
6. [Selectores CSS](#selectores-css)
7. [Especificidad en CSS](#especificidad-en-css)
8. [La Cascada](#la-cascada)
9. [Herencia](#herencia)
10. [Colores en CSS](#colores-en-css)
11. [Unidades de medida](#unidades-de-medida)
12. [Modelo de Caja (Box Model)](#modelo-de-caja)
13. [Ejemplos prácticos](#ejemplos-prácticos)
14. [Buenas prácticas](#buenas-prácticas)

---

## 🎨 ¿Qué es CSS?

**CSS** significa **Cascading Style Sheets** (Hojas de Estilo en Cascada).

Es un lenguaje que se usa para **dar estilo y diseño** a las páginas web. Mientras HTML define la **estructura** y el **contenido**, CSS controla la **apariencia visual**.

### Analogía simple:

Imagina que estás construyendo una casa:

- **HTML** = La estructura (paredes, puertas, ventanas)
- **CSS** = La decoración (pintura, muebles, cortinas)
- **JavaScript** = La funcionalidad (electricidad, plomería, automatización)

### ¿Qué puedes hacer con CSS?

✅ Cambiar colores de texto y fondos  
✅ Modificar tamaños de fuente  
✅ Crear diseños y layouts  
✅ Hacer sitios web responsivos (adaptables a móviles)  
✅ Agregar animaciones y transiciones  
✅ Espaciar elementos  
✅ Controlar la posición de elementos  
✅ Hacer que tu sitio se vea profesional y atractivo

---

## 🤔 ¿Por qué necesitamos CSS?

Sin CSS, todas las páginas web se verían igual: texto negro sobre fondo blanco, sin diseño ni personalidad.

### Ejemplo visual:

**Sin CSS:**

```
Mi Página Web
Bienvenido a mi sitio
Este es un párrafo de texto.
```

**Con CSS:**

```
╔══════════════════════════════════╗
║   🌟 Mi Página Web 🌟            ║
║   ═══════════════════════        ║
║                                  ║
║   Bienvenido a mi sitio          ║
║                                  ║
║   Este es un párrafo con         ║
║   estilo, colores y diseño       ║
╚══════════════════════════════════╝
```

---

## ⚙️ Cómo funciona CSS

CSS trabaja **seleccionando elementos HTML** y aplicándoles **estilos**.

### Proceso simple:

1. **Seleccionas** un elemento HTML (ej: un párrafo)
2. **Defines** qué quieres cambiar (ej: el color)
3. **Estableces** el nuevo valor (ej: azul)

```css
p {
  color: blue;
}
```

Este código dice: "Todos los párrafos (`<p>`) deben tener texto de color azul".

---

## 📝 Formas de agregar CSS

Hay **3 formas** de agregar CSS a tu HTML:

### 1. **CSS en línea (Inline CSS)**

Se escribe directamente en el elemento HTML usando el atributo `style`.

```html
<p style="color: red; font-size: 20px;">Este texto es rojo y grande</p>
```

**Ventajas:**

- Rápido para probar algo
- Tiene la mayor prioridad

**Desventajas:**

- ❌ Difícil de mantener
- ❌ No se puede reutilizar
- ❌ Mezcla contenido con presentación
- ❌ No recomendado para proyectos reales

---

### 2. **CSS interno (Internal CSS)**

Se escribe dentro de la etiqueta `<style>` en el `<head>` del HTML.

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Mi Página</title>
    <style>
      p {
        color: blue;
        font-size: 18px;
      }
      h1 {
        color: green;
      }
    </style>
  </head>
  <body>
    <h1>Título</h1>
    <p>Este es un párrafo.</p>
  </body>
</html>
```

**Ventajas:**

- Útil para páginas pequeñas
- Todo en un solo archivo

**Desventajas:**

- ❌ No se puede reutilizar en otras páginas
- ❌ Hace el HTML más largo

---

### 3. **CSS externo (External CSS)** ⭐ RECOMENDADO

Se escribe en un archivo separado con extensión `.css` y se vincula al HTML.

**Archivo: styles.css**

```css
p {
  color: blue;
  font-size: 18px;
}

h1 {
  color: green;
}
```

**Archivo: index.html**

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Mi Página</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Título</h1>
    <p>Este es un párrafo.</p>
  </body>
</html>
```

**Ventajas:**

- ✅ Se puede reutilizar en múltiples páginas
- ✅ Código más organizado y limpio
- ✅ Fácil de mantener
- ✅ El navegador puede cachear el archivo (más rápido)

**Desventajas:**

- Requiere un archivo adicional (pero es mínimo)

---

## 🔤 Sintaxis básica de CSS

Toda regla CSS tiene esta estructura:

```css
selector {
  propiedad: valor;
  propiedad: valor;
}
```

### Partes de una regla CSS:

```css
h1 {
  color: blue;
  font-size: 24px;
}
```

1. **Selector** (`h1`): Qué elemento quieres estilizar
2. **Llaves** (`{ }`): Contienen las declaraciones
3. **Propiedad** (`color`, `font-size`): Qué aspecto quieres cambiar
4. **Valor** (`blue`, `24px`): El nuevo valor para esa propiedad
5. **Punto y coma** (`;`): Separa cada declaración

### Ejemplo completo:

```css
/* Esto es un comentario en CSS */

/* Estilizar todos los párrafos */
p {
  color: darkblue;
  font-size: 16px;
  line-height: 1.5;
}

/* Estilizar todos los encabezados h1 */
h1 {
  color: crimson;
  font-size: 32px;
  text-align: center;
}
```

---

## 🎯 Selectores CSS

Los selectores permiten **elegir qué elementos** del HTML quieres estilizar.

### 1. **Selector de Elemento (Type Selector)**

Selecciona **todos** los elementos de un tipo.

```css
/* Todos los párrafos */
p {
  color: blue;
}

/* Todos los encabezados h1 */
h1 {
  color: red;
}

/* Todos los enlaces */
a {
  color: green;
  text-decoration: none;
}
```

**HTML:**

```html
<h1>Título</h1>
<!-- Será rojo -->
<p>Párrafo 1</p>
<!-- Será azul -->
<p>Párrafo 2</p>
<!-- Será azul -->
<a href="#">Enlace</a>
<!-- Será verde sin subrayado -->
```

---

### 2. **Selector de Clase (Class Selector)**

Selecciona elementos con una **clase específica**. Se marca con un **punto** (`.`).

```css
/* Elementos con class="importante" */
.importante {
  color: red;
  font-weight: bold;
}

/* Elementos con class="destacado" */
.destacado {
  background-color: yellow;
  padding: 10px;
}
```

**HTML:**

```html
<p class="importante">Este párrafo es importante</p>
<p>Este párrafo es normal</p>
<span class="importante">Este span también es importante</span>
<div class="destacado">Este div está destacado</div>
```

**Ventajas:**

- ✅ Reutilizable (puedes usar la misma clase en múltiples elementos)
- ✅ Específico pero flexible

**Nota:** Un elemento puede tener **múltiples clases**:

```html
<p class="importante destacado">Texto importante y destacado</p>
```

---

### 3. **Selector de ID**

Selecciona un **único elemento** con un ID específico. Se marca con **almohadilla** (`#`).

```css
/* Elemento con id="encabezado-principal" */
#encabezado-principal {
  color: navy;
  font-size: 36px;
  text-align: center;
}

/* Elemento con id="pie-pagina" */
#pie-pagina {
  background-color: #333;
  color: white;
  padding: 20px;
}
```

**HTML:**

```html
<h1 id="encabezado-principal">Mi Sitio Web</h1>
<footer id="pie-pagina">Copyright 2025</footer>
```

**Regla importante:**

- ⚠️ Un ID debe ser **único** en la página
- ⚠️ No uses el mismo ID en dos elementos diferentes

---

### 4. **Selector Universal**

Selecciona **TODOS** los elementos. Se marca con **asterisco** (`*`).

```css
/* Aplicar a TODOS los elementos */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

**Uso común:** Resetear estilos por defecto del navegador.

---

### 5. **Selectores de Atributo**

Selecciona elementos basándose en sus **atributos**.

```css
/* Enlaces que van a sitios externos */
a[target="_blank"] {
  color: orange;
}

/* Inputs de tipo texto */
input[type="text"] {
  border: 2px solid blue;
}

/* Elementos con atributo title */
[title] {
  cursor: help;
}

/* Enlaces que contienen "google" en href */
a[href*="google"] {
  color: red;
}
```

**HTML:**

```html
<a href="pagina.html">Enlace interno</a>
<a href="https://ejemplo.com" target="_blank">Enlace externo</a>
<input type="text" placeholder="Nombre" />
<input type="email" placeholder="Email" />
```

---

### 6. **Selectores Descendientes (Descendant)**

Selecciona elementos que están **dentro** de otros.

```css
/* Párrafos que están dentro de un div */
div p {
  color: blue;
}

/* Enlaces que están dentro de nav */
nav a {
  color: white;
  text-decoration: none;
}

/* Spans dentro de párrafos con clase destacado */
p.destacado span {
  font-weight: bold;
}
```

**HTML:**

```html
<div>
  <p>Este párrafo será azul</p>
  <p>Este también</p>
</div>

<p>Este párrafo NO será azul (no está en un div)</p>

<nav>
  <a href="#">Inicio</a>
  <!-- Blanco sin subrayado -->
  <a href="#">Productos</a>
  <!-- Blanco sin subrayado -->
</nav>
```

---

### 7. **Selector de Hijo Directo (Child)**

Selecciona solo los **hijos directos**. Se marca con `>`.

```css
/* Solo párrafos que son hijos DIRECTOS de div */
div > p {
  color: red;
}
```

**HTML:**

```html
<div>
  <p>Este será rojo (hijo directo)</p>
  <section>
    <p>Este NO será rojo (no es hijo directo de div)</p>
  </section>
</div>
```

**Diferencia:**

- `div p` → Selecciona **todos** los `<p>` dentro de `<div>` (en cualquier nivel)
- `div > p` → Selecciona **solo** los `<p>` que son hijos directos de `<div>`

---

### 8. **Selector de Hermano Adyacente (Adjacent Sibling)**

Selecciona el **siguiente hermano** inmediato. Se marca con `+`.

```css
/* El párrafo que viene INMEDIATAMENTE después de h1 */
h1 + p {
  font-size: 20px;
  color: gray;
}
```

**HTML:**

```html
<h1>Título</h1>
<p>Este párrafo será grande y gris</p>
<p>Este párrafo será normal</p>
```

---

### 9. **Selector de Hermanos Generales (General Sibling)**

Selecciona **todos los hermanos** siguientes. Se marca con `~`.

```css
/* Todos los párrafos que vienen después de h1 */
h1 ~ p {
  color: blue;
}
```

**HTML:**

```html
<h1>Título</h1>
<p>Azul (hermano después de h1)</p>
<div>Algo más</div>
<p>Azul (también hermano después de h1)</p>
```

---

### 10. **Pseudo-clases**

Seleccionan elementos en un **estado específico**.

```css
/* Cuando pasas el mouse sobre un enlace */
a:hover {
  color: red;
  text-decoration: underline;
}

/* El primer hijo */
li:first-child {
  font-weight: bold;
}

/* El último hijo */
li:last-child {
  color: gray;
}

/* Elementos impares */
li:nth-child(odd) {
  background-color: #f0f0f0;
}

/* Elementos pares */
li:nth-child(even) {
  background-color: white;
}

/* Input cuando está enfocado */
input:focus {
  border-color: blue;
  outline: 2px solid lightblue;
}

/* Checkbox marcado */
input[type="checkbox"]:checked {
  background-color: green;
}
```

**Pseudo-clases comunes:**

- `:hover` - Mouse encima
- `:active` - Mientras se hace clic
- `:focus` - Elemento enfocado
- `:visited` - Enlace ya visitado
- `:first-child` - Primer hijo
- `:last-child` - Último hijo
- `:nth-child(n)` - Hijo número n
- `:not(selector)` - Elementos que NO coinciden

---

### 11. **Pseudo-elementos**

Permiten estilizar **partes específicas** de un elemento. Se marcan con `::`.

```css
/* Primera letra del párrafo */
p::first-letter {
  font-size: 32px;
  font-weight: bold;
  color: red;
}

/* Primera línea del párrafo */
p::first-line {
  font-weight: bold;
}

/* Insertar contenido ANTES */
h1::before {
  content: "📌 ";
}

/* Insertar contenido DESPUÉS */
h1::after {
  content: " ✨";
}

/* Texto seleccionado */
::selection {
  background-color: yellow;
  color: black;
}
```

---

### 12. **Agrupación de Selectores**

Aplicar el mismo estilo a **múltiples selectores** separados por **coma** (`,`).

```css
/* Aplicar a h1, h2 y h3 */
h1,
h2,
h3 {
  color: navy;
  font-family: Arial, sans-serif;
}

/* Aplicar a múltiples clases */
.error,
.warning,
.alert {
  padding: 10px;
  border-radius: 5px;
}
```

---

### 13. **Combinaciones Complejas**

Puedes combinar múltiples selectores:

```css
/* Párrafos con clase "intro" dentro de section */
section p.intro {
  font-size: 18px;
}

/* Enlaces con clase "activo" cuando pasas el mouse */
a.activo:hover {
  color: red;
}

/* Primer párrafo hijo directo de div con clase "contenedor" */
div.contenedor > p:first-child {
  font-weight: bold;
}
```

---

## ⚖️ Especificidad en CSS

La **especificidad** determina **qué regla CSS se aplica** cuando hay conflicto.

### ¿Por qué es importante?

Cuando múltiples reglas afectan al mismo elemento, el navegador debe decidir cuál aplicar.

```css
p {
  color: blue;
}

.importante {
  color: red;
}

#especial {
  color: green;
}
```

```html
<p id="especial" class="importante">¿De qué color será?</p>
```

**Respuesta:** Verde (porque el ID tiene mayor especificidad)

---

### Cálculo de Especificidad

La especificidad se calcula con **4 números**: `(a, b, c, d)`

| Componente | Valor | Descripción                                                       |
| ---------- | ----- | ----------------------------------------------------------------- |
| **a**      | 1000  | Estilos en línea (`style=""`)                                     |
| **b**      | 100   | IDs (`#id`)                                                       |
| **c**      | 10    | Clases (`.clase`), atributos (`[type]`), pseudo-clases (`:hover`) |
| **d**      | 1     | Elementos (`p`, `div`), pseudo-elementos (`::before`)             |

### Ejemplos de cálculo:

```css
/* (0, 0, 0, 1) = 1 */
p {
  color: blue;
}

/* (0, 0, 1, 0) = 10 */
.destacado {
  color: red;
}

/* (0, 1, 0, 0) = 100 */
#principal {
  color: green;
}

/* (0, 0, 1, 1) = 11 */
p.importante {
  color: orange;
}

/* (0, 1, 1, 0) = 110 */
#principal.destacado {
  color: purple;
}

/* (0, 0, 2, 1) = 21 */
p.importante.urgente {
  color: crimson;
}

/* (0, 0, 1, 2) = 12 */
div p.intro {
  color: navy;
}
```

### Reglas de prioridad:

1. **Estilos en línea** (1000) - Máxima prioridad
2. **IDs** (100)
3. **Clases, atributos, pseudo-clases** (10)
4. **Elementos, pseudo-elementos** (1)
5. **Selector universal** `*` (0) - Mínima prioridad

### En caso de empate:

Si dos reglas tienen la **misma especificidad**, gana **la última** que aparece en el CSS.

```css
p {
  color: blue;
}

p {
  color: red; /* Esta gana (es la última) */
}
```

---

### `!important` - El Tramposo

`!important` **anula todo** y tiene la máxima prioridad.

```css
p {
  color: blue !important;
}

#mi-parrafo {
  color: red; /* NO se aplicará */
}
```

```html
<p id="mi-parrafo" style="color: green;">
  Este texto será AZUL (por el !important)
</p>
```

**⚠️ ADVERTENCIA:**

- ❌ Evita usar `!important` en lo posible
- ❌ Dificulta el mantenimiento
- ❌ Rompe la cascada natural
- ✅ Úsalo solo para sobrescribir estilos de terceros (librerías)

---

### Tabla de Especificidad Visual

```
!important         → 🔴 10,000 (evitar)
Estilos en línea   → 🟠 1,000
ID                 → 🟡 100
Clase/Atributo     → 🟢 10
Elemento           → 🔵 1
Universal (*)      → ⚪ 0
```

**Ejemplo práctico:**

```css
/* Especificidad: 0,0,0,1 = 1 */
p {
  color: black;
}

/* Especificidad: 0,0,1,0 = 10 - GANA */
.texto {
  color: blue;
}

/* Especificidad: 0,0,1,1 = 11 - GANA */
p.texto {
  color: green;
}

/* Especificidad: 0,1,0,0 = 100 - GANA */
#parrafo {
  color: red;
}

/* Especificidad: 0,1,1,1 = 111 - GANA */
#parrafo.texto p {
  color: purple;
}

/* Especificidad: 1,0,0,0 = 1000 - GANA */
<p style="color: orange;">

/* Especificidad: INFINITO - SIEMPRE GANA */
p {
  color: yellow !important;
}
```

---

## 🌊 La Cascada

**Cascada** es el proceso por el cual el navegador decide qué estilos aplicar cuando hay múltiples reglas.

### Orden de prioridad (de menor a mayor):

1. **Estilos del navegador** (user agent)
2. **Estilos del usuario** (configuración del navegador)
3. **Estilos del autor** (tu CSS)
4. **`!important` del autor**
5. **`!important` del usuario**

### Factores que afectan la cascada:

1. **Importancia** (`!important`)
2. **Especificidad** (calculada como vimos arriba)
3. **Orden de aparición** (el último gana en empates)

---

## 👨‍👩‍👧‍👦 Herencia

Algunas propiedades CSS se **heredan** de elementos padres a hijos.

### Propiedades que se heredan:

- `color`
- `font-family`
- `font-size`
- `font-weight`
- `line-height`
- `text-align`
- `visibility`

### Ejemplo:

```css
body {
  color: darkblue;
  font-family: Arial, sans-serif;
}
```

```html
<body>
  <p>Este texto será azul oscuro y Arial</p>
  <div>
    <span>Este también heredará el color y fuente</span>
  </div>
</body>
```

### Propiedades que NO se heredan:

- `margin`
- `padding`
- `border`
- `background`
- `width`
- `height`

### Forzar herencia:

```css
div {
  border: inherit; /* Heredar el border del padre */
}
```

### Valores especiales:

- `inherit` - Hereda del padre
- `initial` - Valor por defecto del navegador
- `unset` - Hereda si es heredable, sino usa initial

---

## 🎨 Colores en CSS

Hay varias formas de especificar colores:

### 1. Nombres de colores

```css
p {
  color: red;
  background-color: lightblue;
  border-color: navy;
}
```

**Disponibles:** 140 nombres de colores (`red`, `blue`, `green`, `yellow`, `purple`, etc.)

---

### 2. Hexadecimal (Hex)

Formato: `#RRGGBB` (Rojo, Verde, Azul en hexadecimal)

```css
p {
  color: #ff0000; /* Rojo */
  color: #00ff00; /* Verde */
  color: #0000ff; /* Azul */
  color: #ffffff; /* Blanco */
  color: #000000; /* Negro */
  color: #808080; /* Gris */
}

/* Formato corto (cuando los pares son iguales) */
p {
  color: #f00; /* = #FF0000 */
  color: #0f0; /* = #00FF00 */
}
```

---

### 3. RGB

Formato: `rgb(rojo, verde, azul)` - Valores de 0 a 255

```css
p {
  color: rgb(255, 0, 0); /* Rojo */
  color: rgb(0, 255, 0); /* Verde */
  color: rgb(0, 0, 255); /* Azul */
  color: rgb(128, 128, 128); /* Gris */
}
```

---

### 4. RGBA (con transparencia)

Formato: `rgba(rojo, verde, azul, alpha)` - Alpha de 0 (transparente) a 1 (opaco)

```css
p {
  color: rgba(255, 0, 0, 1); /* Rojo opaco */
  color: rgba(255, 0, 0, 0.5); /* Rojo semi-transparente */
  color: rgba(0, 0, 0, 0.8); /* Negro con 80% opacidad */
}
```

---

### 5. HSL (Hue, Saturation, Lightness)

Formato: `hsl(matiz, saturación%, luminosidad%)`

```css
p {
  color: hsl(0, 100%, 50%); /* Rojo */
  color: hsl(120, 100%, 50%); /* Verde */
  color: hsl(240, 100%, 50%); /* Azul */
}
```

---

### 6. HSLA (con transparencia)

```css
p {
  color: hsla(0, 100%, 50%, 0.5); /* Rojo semi-transparente */
}
```

---

## 📏 Unidades de Medida

### Unidades Absolutas

No cambian según el contexto.

| Unidad | Descripción                 | Uso       |
| ------ | --------------------------- | --------- |
| `px`   | Píxeles                     | Pantallas |
| `pt`   | Puntos (1pt = 1/72 pulgada) | Impresión |
| `cm`   | Centímetros                 | Impresión |
| `mm`   | Milímetros                  | Impresión |
| `in`   | Pulgadas                    | Impresión |

```css
p {
  font-size: 16px;
  margin: 20px;
}
```

---

### Unidades Relativas ⭐ RECOMENDADO

Cambian según el contexto (más flexibles y responsivas).

| Unidad | Descripción                                               |
| ------ | --------------------------------------------------------- |
| `em`   | Relativo al tamaño de fuente del elemento padre           |
| `rem`  | Relativo al tamaño de fuente del elemento raíz (`<html>`) |
| `%`    | Porcentaje relativo al elemento padre                     |
| `vw`   | 1% del ancho del viewport (ventana)                       |
| `vh`   | 1% del alto del viewport                                  |
| `vmin` | 1% del lado más pequeño del viewport                      |
| `vmax` | 1% del lado más grande del viewport                       |

```css
html {
  font-size: 16px; /* Base */
}

h1 {
  font-size: 2rem; /* 32px (2 × 16px) */
}

p {
  font-size: 1rem; /* 16px */
  padding: 1em; /* 16px (relativo a su propio font-size) */
  width: 80%; /* 80% del ancho del padre */
}

.hero {
  height: 100vh; /* Altura completa de la pantalla */
}
```

**Recomendación:**

- Usa `rem` para tamaños de fuente (consistencia)
- Usa `em` para padding/margin relativos a fuente
- Usa `%` para anchos responsivos
- Usa `vw/vh` para secciones a pantalla completa

---

## 📦 Modelo de Caja (Box Model)

**Todos** los elementos HTML son cajas rectangulares con 4 capas:

```
┌─────────────────────────────────┐
│         MARGIN (margen)         │  ← Espacio FUERA del elemento
│  ┌──────────────────────────┐  │
│  │   BORDER (borde)         │  │  ← Línea alrededor
│  │  ┌────────────────────┐  │  │
│  │  │  PADDING (relleno) │  │  │  ← Espacio DENTRO, antes del contenido
│  │  │  ┌──────────────┐  │  │  │
│  │  │  │   CONTENT    │  │  │  │  ← El contenido real
│  │  │  │  (contenido) │  │  │  │
│  │  │  └──────────────┘  │  │  │
│  │  └────────────────────┘  │  │
│  └──────────────────────────┘  │
└─────────────────────────────────┘
```

### Propiedades:

```css
div {
  /* Contenido */
  width: 200px;
  height: 100px;

  /* Padding (relleno interno) */
  padding: 20px;
  /* o específico */
  padding-top: 10px;
  padding-right: 15px;
  padding-bottom: 10px;
  padding-left: 15px;

  /* Border (borde) */
  border: 2px solid black;
  /* o específico */
  border-width: 2px;
  border-style: solid;
  border-color: black;

  /* Margin (margen externo) */
  margin: 10px;
  /* o específico */
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;
}
```

### Shorthand (atajos):

```css
/* Todos los lados iguales */
padding: 10px;

/* Vertical | Horizontal */
padding: 10px 20px;

/* Top | Horizontal | Bottom */
padding: 10px 20px 15px;

/* Top | Right | Bottom | Left (sentido horario) */
padding: 10px 15px 20px 25px;
```

### Box-sizing

Por defecto, `width` y `height` solo afectan al contenido.

```css
/* Por defecto (content-box) */
div {
  width: 200px;
  padding: 20px;
  border: 2px solid;
  /* Ancho total = 200 + 40 (padding) + 4 (border) = 244px */
}

/* Recomendado: border-box */
div {
  box-sizing: border-box;
  width: 200px;
  padding: 20px;
  border: 2px solid;
  /* Ancho total = 200px (padding y border incluidos) */
}
```

**Reset recomendado:**

```css
* {
  box-sizing: border-box;
}
```

---

## 💡 Ejemplos Prácticos

Ver los archivos de ejemplo en la carpeta `css/`:

- `01-selectores-basicos.html`
- `02-especificidad.html`
- `03-colores-unidades.html`
- `04-modelo-caja.html`

---

## ✅ Buenas Prácticas

1. **Usa CSS externo** (archivos `.css` separados)
2. **Nombres de clases descriptivos** (`.boton-principal`, no `.bp`)
3. **Evita `!important`** (rompe la cascada)
4. **Prefiere clases sobre IDs** para estilos
5. **Usa `rem` para fuentes** (mejor escalabilidad)
6. **Aplica `box-sizing: border-box`** globalmente
7. **Organiza tu CSS** (secciones, comentarios)
8. **Mantén especificidad baja** (evita selectores muy complejos)
9. **Comenta código complejo**
10. **Usa variables CSS** (custom properties) para valores repetidos

```css
:root {
  --color-primary: #3490dc;
  --color-secondary: #6574cd;
  --font-size-base: 16px;
}

button {
  background-color: var(--color-primary);
  font-size: var(--font-size-base);
}
```

---

## 📚 Recursos Adicionales

- **MDN CSS:** https://developer.mozilla.org/es/docs/Web/CSS
- **CSS Tricks:** https://css-tricks.com/
- **Can I Use:** https://caniuse.com/ (compatibilidad)
- **CSS Specificity Calculator:** https://specificity.keegan.st/

---

## 🎯 Próximos Pasos

En los siguientes documentos veremos:

- Propiedades de texto y fuentes
- Fondos y bordes
- Flexbox para layouts
- Grid para layouts avanzados
- Posicionamiento
- Animaciones y transiciones
- Responsive design con media queries

---

**Actualizado:** 16 de octubre de 2025  
**Próximo tema:** Selectores avanzados y especificidad práctica  
**Archivos de ejemplo:** `modulo-02-fundamentos-frontend/css/`
