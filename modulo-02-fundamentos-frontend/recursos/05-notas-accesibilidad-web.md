# 05 - Accesibilidad Web (WCAG y Mejores Prácticas)

**Fecha:** 16 de octubre de 2025  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End  
**Tema:** Accesibilidad Web (Web Accessibility)

---

## 📚 Índice

1. [¿Qué es la Accesibilidad Web?](#qué-es-la-accesibilidad-web)
2. [Principios WCAG](#principios-wcag)
3. [HTML Semántico y Accesibilidad](#html-semántico-y-accesibilidad)
4. [ARIA (Accessible Rich Internet Applications)](#aria)
5. [Navegación por Teclado](#navegación-por-teclado)
6. [Contraste y Colores](#contraste-y-colores)
7. [Formularios Accesibles](#formularios-accesibles)
8. [Imágenes y Multimedia](#imágenes-y-multimedia)
9. [Tecnologías Asistivas](#tecnologías-asistivas)
10. [Herramientas de Testing](#herramientas-de-testing)
11. [Ejemplos Prácticos](#ejemplos-prácticos)
12. [Checklist de Accesibilidad](#checklist-de-accesibilidad)

---

## 🎯 ¿Qué es la Accesibilidad Web?

La **accesibilidad web** significa que sitios web, herramientas y tecnologías están diseñados y desarrollados para que las personas con discapacidades puedan usarlos.

### Tipos de Discapacidades

- **Visual:** Ceguera, baja visión, daltonismo
- **Auditiva:** Sordera, pérdida auditiva
- **Motora:** Dificultad para usar mouse, teclado o dispositivos táctiles
- **Cognitiva:** Dislexia, TDAH, autismo
- **Neurológica:** Epilepsia (sensibilidad a destellos)

### Beneficios de la Accesibilidad

✅ **Inclusión:** Permite que todos accedan a tu contenido  
✅ **SEO:** Mejora el posicionamiento en buscadores  
✅ **Usabilidad:** Mejora la experiencia para todos los usuarios  
✅ **Legal:** Cumplimiento de normativas (ADA, Sección 508)  
✅ **Alcance:** Mayor audiencia potencial  
✅ **Reputación:** Imagen positiva de la marca

---

## 🔍 Principios WCAG (Web Content Accessibility Guidelines)

Las **WCAG 2.1** establecen 4 principios fundamentales conocidos como **POUR**:

### 1. **Perceptible** (Perceivable)

La información y los componentes de la interfaz deben ser presentados de forma que los usuarios puedan percibirlos.

**Criterios clave:**

- Proporcionar alternativas de texto para contenido no textual
- Proporcionar subtítulos y alternativas para multimedia
- Crear contenido que se pueda presentar de diferentes formas
- Hacer más fácil ver y oír el contenido

**Ejemplo:**

```html
<!-- ✅ BIEN: Imagen con alt descriptivo -->
<img
  src="grafico-ventas.png"
  alt="Gráfico de barras mostrando aumento del 30% en ventas del Q1 al Q2"
/>

<!-- ❌ MAL: Imagen sin alt -->
<img src="grafico-ventas.png" />
```

---

### 2. **Operable** (Operable)

Los componentes de la interfaz y la navegación deben ser operables.

**Criterios clave:**

- Toda funcionalidad disponible desde teclado
- Dar suficiente tiempo para leer y usar el contenido
- No diseñar contenido que pueda causar convulsiones
- Proporcionar formas de ayudar a los usuarios a navegar y encontrar contenido

**Ejemplo:**

```html
<!-- ✅ BIEN: Botón accesible por teclado -->
<button onclick="enviar()">Enviar Formulario</button>

<!-- ❌ MAL: Div que parece botón pero no es accesible -->
<div onclick="enviar()" style="cursor: pointer;">Enviar</div>
```

---

### 3. **Comprensible** (Understandable)

La información y la operación de la interfaz deben ser comprensibles.

**Criterios clave:**

- Hacer el contenido de texto legible y comprensible
- Hacer que las páginas aparezcan y operen de manera predecible
- Ayudar a los usuarios a evitar y corregir errores

**Ejemplo:**

```html
<!-- ✅ BIEN: Mensajes de error claros -->
<label for="email">Email:</label>
<input type="email" id="email" aria-describedby="email-error" required />
<span id="email-error" role="alert">
  Por favor, ingresa un email válido (ejemplo: usuario@dominio.com)
</span>

<!-- ❌ MAL: Error vago -->
<span>Error</span>
```

---

### 4. **Robusto** (Robust)

El contenido debe ser lo suficientemente robusto como para ser interpretado de forma fiable por una amplia variedad de agentes de usuario, incluidas las tecnologías asistivas.

**Criterios clave:**

- Maximizar la compatibilidad con herramientas actuales y futuras
- Usar HTML válido y semántico
- Proporcionar información suficiente para tecnologías asistivas

**Ejemplo:**

```html
<!-- ✅ BIEN: HTML válido y semántico -->
<nav aria-label="Navegación principal">
  <ul>
    <li><a href="/">Inicio</a></li>
    <li><a href="/productos">Productos</a></li>
  </ul>
</nav>

<!-- ❌ MAL: Estructura no semántica -->
<div class="nav">
  <span onclick="ir('/')">Inicio</span>
  <span onclick="ir('/productos')">Productos</span>
</div>
```

---

## 📝 Niveles de Conformidad WCAG

- **Nivel A:** Requisitos mínimos (básico)
- **Nivel AA:** Recomendado para la mayoría de sitios (estándar)
- **Nivel AAA:** Mayor nivel de accesibilidad (avanzado)

**Recomendación:** Apuntar al menos al **Nivel AA** para cumplir con la mayoría de normativas legales.

---

## 🏗️ HTML Semántico y Accesibilidad

El HTML semántico es fundamental para la accesibilidad.

### Estructura Semántica

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Título Descriptivo de la Página</title>
  </head>
  <body>
    <header>
      <h1>Título Principal del Sitio</h1>
      <nav aria-label="Navegación principal">
        <!-- Menú de navegación -->
      </nav>
    </header>

    <main>
      <article>
        <h2>Título del Artículo</h2>
        <p>Contenido...</p>
      </article>

      <aside>
        <h2>Barra Lateral</h2>
        <!-- Contenido relacionado -->
      </aside>
    </main>

    <footer>
      <p>&copy; 2025 Mi Sitio</p>
    </footer>
  </body>
</html>
```

### Jerarquía de Encabezados

```html
<!-- ✅ BIEN: Jerarquía lógica -->
<h1>Título de la Página</h1>
<h2>Sección 1</h2>
<h3>Subsección 1.1</h3>
<h3>Subsección 1.2</h3>
<h2>Sección 2</h2>
<h3>Subsección 2.1</h3>

<!-- ❌ MAL: Jerarquía rota -->
<h1>Título</h1>
<h4>Subtítulo</h4>
<h2>Otra sección</h2>
```

**Reglas:**

- Solo un `<h1>` por página
- No saltar niveles (h1 → h3)
- Mantener orden lógico

---

## ♿ ARIA (Accessible Rich Internet Applications)

ARIA proporciona atributos para hacer contenido dinámico más accesible.

### Atributos ARIA Principales

#### 1. **Roles** (`role`)

Define el tipo de elemento:

```html
<div role="navigation">
  <!-- Menú de navegación -->
</div>

<div role="alert">Error: Por favor completa todos los campos</div>

<div role="button" tabindex="0" onclick="accion()">Clic aquí</div>
```

**Roles comunes:**

- `navigation`, `main`, `complementary`, `contentinfo`
- `button`, `link`, `checkbox`, `radio`
- `alert`, `status`, `dialog`, `menu`
- `search`, `form`, `banner`

---

#### 2. **Propiedades** (`aria-*`)

##### `aria-label`

Proporciona una etiqueta cuando no hay texto visible:

```html
<button aria-label="Cerrar ventana">
  <span aria-hidden="true">&times;</span>
</button>

<nav aria-label="Paginación">
  <a href="?page=1">1</a>
  <a href="?page=2">2</a>
</nav>
```

##### `aria-labelledby`

Referencia a un elemento que actúa como etiqueta:

```html
<div id="dialog-title">Confirmar Acción</div>
<div role="dialog" aria-labelledby="dialog-title">
  <p>¿Estás seguro de eliminar este elemento?</p>
  <button>Sí</button>
  <button>No</button>
</div>
```

##### `aria-describedby`

Proporciona una descripción adicional:

```html
<label for="password">Contraseña:</label>
<input type="password" id="password" aria-describedby="password-hint" />
<span id="password-hint">Mínimo 8 caracteres con mayúsculas y números</span>
```

##### `aria-hidden`

Oculta contenido de tecnologías asistivas:

```html
<!-- Iconos decorativos -->
<button>
  <i class="icon-save" aria-hidden="true"></i>
  Guardar
</button>
```

##### `aria-live`

Anuncia cambios dinámicos:

```html
<!-- Notificaciones -->
<div aria-live="polite" aria-atomic="true">
  <p>Mensaje guardado exitosamente</p>
</div>

<!-- Alertas urgentes -->
<div aria-live="assertive" role="alert">
  <p>Error: Sesión expirada</p>
</div>
```

Valores:

- `off`: No anuncia (predeterminado)
- `polite`: Anuncia cuando el usuario termine la tarea actual
- `assertive`: Interrumpe para anunciar inmediatamente

---

#### 3. **Estados** (`aria-*`)

##### `aria-expanded`

Indica si un elemento está expandido o colapsado:

```html
<button aria-expanded="false" aria-controls="menu">Menú</button>
<ul id="menu" hidden>
  <li>Opción 1</li>
  <li>Opción 2</li>
</ul>
```

##### `aria-checked`

Estado de checkbox o radio personalizado:

```html
<div role="checkbox" aria-checked="true" tabindex="0">
  Acepto términos y condiciones
</div>
```

##### `aria-disabled`

Indica que un elemento está deshabilitado:

```html
<button aria-disabled="true" style="opacity: 0.5;">Botón Deshabilitado</button>
```

##### `aria-invalid`

Indica que un campo tiene un error:

```html
<input type="email" aria-invalid="true" aria-describedby="email-error" />
<span id="email-error" role="alert">Email inválido</span>
```

##### `aria-current`

Indica el elemento actual en una navegación:

```html
<nav>
  <a href="/" aria-current="page">Inicio</a>
  <a href="/productos">Productos</a>
  <a href="/contacto">Contacto</a>
</nav>
```

---

### ⚠️ Reglas de ARIA

1. **Primera regla de ARIA:** No usar ARIA si existe un elemento HTML nativo equivalente

   ```html
   <!-- ✅ BIEN: Usar HTML nativo -->
   <button>Enviar</button>

   <!-- ❌ MAL: ARIA innecesario -->
   <div role="button" tabindex="0">Enviar</div>
   ```

2. **No cambiar la semántica nativa**

   ```html
   <!-- ❌ MAL -->
   <h1 role="button">Esto confunde a los lectores de pantalla</h1>
   ```

3. **Elementos interactivos deben ser accesibles por teclado**

   ```html
   <!-- ✅ BIEN -->
   <div
     role="button"
     tabindex="0"
     onclick="accion()"
     onkeypress="accion()"
   ></div>
   ```

4. **No ocultar contenido interactivo**
   ```html
   <!-- ❌ MAL -->
   <button aria-hidden="true">Clic aquí</button>
   ```

---

## ⌨️ Navegación por Teclado

Muchos usuarios navegan sin mouse. Tu sitio debe ser completamente usable con teclado.

### Orden de Tabulación

```html
<!-- tabindex valores -->
<button tabindex="0">Normal (orden del DOM)</button>
<button tabindex="1">Primero (evitar)</button>
<button tabindex="-1">No tabulable, pero enfocable por JS</button>
<div tabindex="0">Div enfocable</div>
```

**Reglas:**

- `tabindex="0"`: Orden natural del DOM
- `tabindex="-1"`: Excluir de tabulación, pero puede recibir focus por JS
- `tabindex="1+"`: Evitar (altera el orden natural)

### Indicadores de Focus Visibles

```css
/* ✅ BIEN: Focus visible personalizado */
button:focus,
a:focus,
input:focus {
  outline: 3px solid #4a90e2;
  outline-offset: 2px;
}

/* ❌ MAL: Eliminar outline sin alternativa */
*:focus {
  outline: none; /* NUNCA hacer esto */
}
```

### Skip Links (Saltar al Contenido)

```html
<body>
  <a href="#main-content" class="skip-link"> Saltar al contenido principal </a>

  <nav><!-- Menú largo --></nav>

  <main id="main-content">
    <!-- Contenido principal -->
  </main>
</body>

<style>
  .skip-link {
    position: absolute;
    top: -40px;
    left: 0;
    background: #000;
    color: #fff;
    padding: 8px;
    z-index: 100;
  }

  .skip-link:focus {
    top: 0;
  }
</style>
```

### Eventos de Teclado

```javascript
// Hacer un div interactivo accesible
const div = document.querySelector(".custom-button");

div.addEventListener("click", handleAction);
div.addEventListener("keydown", (e) => {
  // Enter o Espacio activan el botón
  if (e.key === "Enter" || e.key === " ") {
    e.preventDefault();
    handleAction();
  }
});

function handleAction() {
  console.log("Acción ejecutada");
}
```

---

## 🎨 Contraste y Colores

### Ratios de Contraste WCAG

| Nivel   | Texto Normal | Texto Grande |
| ------- | ------------ | ------------ |
| **AA**  | 4.5:1        | 3:1          |
| **AAA** | 7:1          | 4.5:1        |

**Texto Grande:** 18pt (24px) o 14pt (18.66px) en negrita

### Ejemplos

```css
/* ✅ BIEN: Contraste 7:1 (AAA) */
.texto {
  color: #000000;
  background: #ffffff;
}

/* ✅ BIEN: Contraste 4.8:1 (AA) */
.texto-claro {
  color: #555555;
  background: #ffffff;
}

/* ❌ MAL: Contraste 2.5:1 (Insuficiente) */
.texto-gris {
  color: #aaaaaa;
  background: #ffffff;
}
```

### No Usar Solo Color para Información

```html
<!-- ❌ MAL: Solo color -->
<span style="color: red;">Error</span>
<span style="color: green;">Éxito</span>

<!-- ✅ BIEN: Color + icono/texto -->
<span style="color: red;">
  <span aria-hidden="true">❌</span>
  Error: Campo requerido
</span>

<span style="color: green;">
  <span aria-hidden="true">✅</span>
  Guardado exitosamente
</span>
```

### Herramientas de Verificación

- **WebAIM Contrast Checker:** https://webaim.org/resources/contrastchecker/
- **Contrast Ratio:** https://contrast-ratio.com/
- **Color Safe:** http://colorsafe.co/

---

## 📋 Formularios Accesibles

### Labels Asociados

```html
<!-- ✅ BIEN: Label asociado explícitamente -->
<label for="nombre">Nombre:</label>
<input type="text" id="nombre" name="nombre" />

<!-- ✅ BIEN: Label implícito -->
<label>
  Nombre:
  <input type="text" name="nombre" />
</label>

<!-- ❌ MAL: Sin label -->
<input type="text" placeholder="Nombre" />
```

### Grupos de Campos

```html
<fieldset>
  <legend>Información Personal</legend>

  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" required />

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required />
</fieldset>
```

### Mensajes de Error

```html
<label for="email">Email:</label>
<input
  type="email"
  id="email"
  name="email"
  aria-invalid="true"
  aria-describedby="email-error"
  required
/>
<span id="email-error" role="alert"> Por favor, ingresa un email válido </span>
```

### Instrucciones y Ayuda

```html
<label for="password">Contraseña:</label>
<input
  type="password"
  id="password"
  name="password"
  aria-describedby="password-requirements"
/>
<div id="password-requirements">
  <p>La contraseña debe contener:</p>
  <ul>
    <li>Mínimo 8 caracteres</li>
    <li>Al menos una mayúscula</li>
    <li>Al menos un número</li>
  </ul>
</div>
```

---

## 🖼️ Imágenes y Multimedia

### Texto Alternativo (Alt Text)

```html
<!-- ✅ Imagen informativa -->
<img
  src="grafico.png"
  alt="Gráfico de líneas mostrando crecimiento de usuarios del 20% en 2024"
/>

<!-- ✅ Imagen decorativa -->
<img src="decoracion.png" alt="" role="presentation" />

<!-- ✅ Imagen funcional (link) -->
<a href="/inicio">
  <img src="logo.png" alt="Inicio - Nombre de la empresa" />
</a>

<!-- ✅ Imagen compleja con longdesc -->
<img
  src="diagrama-complejo.png"
  alt="Diagrama de flujo del proceso de compra"
  longdesc="descripcion-diagrama.html"
/>

<!-- ❌ MAL: Alt genérico -->
<img src="foto.jpg" alt="imagen" />
```

### Videos Accesibles

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />

  <!-- Subtítulos -->
  <track
    kind="captions"
    srclang="es"
    src="subtitulos-es.vtt"
    label="Español"
    default
  />

  <!-- Audiodescripción -->
  <track
    kind="descriptions"
    srclang="es"
    src="audiodescripcion.vtt"
    label="Audiodescripción"
  />

  <!-- Fallback -->
  <p>
    Tu navegador no soporta video.
    <a href="video.mp4">Descargar video</a>
  </p>
</video>
```

### Audio con Transcripción

```html
<audio controls>
  <source src="podcast.mp3" type="audio/mpeg" />
  Tu navegador no soporta audio.
</audio>

<details>
  <summary>Ver transcripción</summary>
  <p>[Transcripción completa del audio...]</p>
</details>
```

---

## 🔊 Tecnologías Asistivas

### Lectores de Pantalla

- **NVDA** (Windows, gratuito)
- **JAWS** (Windows, pago)
- **VoiceOver** (Mac/iOS, integrado)
- **TalkBack** (Android, integrado)
- **Narrator** (Windows, integrado)

### Probar con Lectores de Pantalla

**Windows + NVDA:**

- Instalar NVDA (gratuito)
- `NVDA + Ctrl` = Detener lectura
- `Tecla de flecha` = Navegar por elementos

**Mac + VoiceOver:**

- `Cmd + F5` = Activar/desactivar VoiceOver
- `VO + A` = Leer página
- `VO + →` = Siguiente elemento

---

## 🧪 Herramientas de Testing

### Extensiones de Navegador

1. **axe DevTools** (Chrome/Firefox)

   - Análisis automático de accesibilidad
   - Identifica problemas y sugiere soluciones

2. **WAVE** (Web Accessibility Evaluation Tool)

   - Visualiza problemas de accesibilidad
   - Destaca errores directamente en la página

3. **Lighthouse** (Chrome DevTools)
   - Auditoría integrada en Chrome
   - Sección dedicada a Accessibility

### Herramientas Online

- **WAVE:** https://wave.webaim.org/
- **axe:** https://www.deque.com/axe/
- **AChecker:** https://achecker.ca/

### Validadores

- **HTML Validator:** https://validator.w3.org/
- **WCAG Checker:** https://www.accessibilitychecker.org/

### Testing Manual

**Checklist básica:**

1. ✓ Navegar solo con teclado (Tab, Enter, Espacio, Flechas)
2. ✓ Usar lector de pantalla
3. ✓ Aumentar zoom al 200%
4. ✓ Desactivar CSS
5. ✓ Usar escala de grises (simular daltonismo)
6. ✓ Probar en dispositivos táctiles

---

## ✅ Checklist de Accesibilidad

### HTML y Estructura

- [ ] HTML válido y semántico
- [ ] Un solo `<h1>` por página
- [ ] Jerarquía de encabezados lógica
- [ ] Atributo `lang` en `<html>`
- [ ] `<title>` descriptivo en cada página
- [ ] Estructura con `<header>`, `<nav>`, `<main>`, `<footer>`

### Teclado

- [ ] Toda funcionalidad accesible por teclado
- [ ] Orden de tabulación lógico
- [ ] Indicadores de focus visibles
- [ ] Sin trampas de teclado
- [ ] Skip links implementados

### Imágenes y Multimedia

- [ ] Todas las imágenes tienen `alt`
- [ ] Alt text descriptivo (no "imagen de...")
- [ ] Imágenes decorativas con `alt=""`
- [ ] Videos con subtítulos
- [ ] Audio con transcripciones

### Formularios

- [ ] Todos los inputs tienen `<label>` asociado
- [ ] Campos agrupados con `<fieldset>` y `<legend>`
- [ ] Mensajes de error claros y accesibles
- [ ] Validación con `aria-invalid`
- [ ] Instrucciones con `aria-describedby`

### Color y Contraste

- [ ] Ratio de contraste mínimo 4.5:1 (AA)
- [ ] No usar solo color para información
- [ ] Texto legible sobre imágenes de fondo

### ARIA

- [ ] Roles ARIA apropiados
- [ ] Estados dinámicos con `aria-live`
- [ ] Elementos interactivos etiquetados
- [ ] No usar ARIA innecesariamente

### Contenido

- [ ] Lenguaje claro y simple
- [ ] Enlaces descriptivos (no "click aquí")
- [ ] Títulos de página únicos
- [ ] Listas usadas correctamente

---

## 📚 Recursos Adicionales

### Documentación Oficial

- **WCAG 2.1:** https://www.w3.org/WAI/WCAG21/quickref/
- **MDN Accessibility:** https://developer.mozilla.org/es/docs/Web/Accessibility
- **WAI-ARIA:** https://www.w3.org/WAI/standards-guidelines/aria/

### Cursos y Guías

- **WebAIM:** https://webaim.org/
- **A11y Project:** https://www.a11yproject.com/
- **Google Web Fundamentals:** https://developers.google.com/web/fundamentals/accessibility

### Comunidad

- **A11y Slack:** https://web-a11y.slack.com/
- **Twitter:** #a11y #accessibility

---

## 🎓 Conclusión

La accesibilidad web no es opcional, es fundamental. Beneficia a:

- Personas con discapacidades permanentes
- Personas con discapacidades temporales (brazo roto, ojos cansados)
- Personas con discapacidades situacionales (luz brillante en pantalla, ambiente ruidoso)
- Todos los usuarios (mejor usabilidad)

**Recuerda:** La accesibilidad debe incorporarse desde el inicio del desarrollo, no como una corrección posterior.

---

**Próximo paso:** Crear archivo HTML con ejemplos prácticos de accesibilidad.

**Actualizado:** 16 de octubre de 2025  
**Archivo de referencia:** `modulo-02-fundamentos-frontend/html/05-Accesibilidad-web.html`
