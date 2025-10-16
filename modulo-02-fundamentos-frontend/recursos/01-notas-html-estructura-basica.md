# 📝 Notas: Estructura Básica HTML5

**Fecha:** 15 de octubre de 2025  
**Archivo:** `01-Estructura basica.html`  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End

---

## 🏗️ Estructura Básica de un Documento HTML5

### 1. Declaración DOCTYPE

```html
<!DOCTYPE html>
```

**Explicación:**

- Declara que el documento es HTML5
- Debe ser la primera línea del archivo
- No es una etiqueta HTML, es una instrucción para el navegador
- Es **case-insensitive** (no distingue mayúsculas/minúsculas)

**Importante:** Sin esta declaración, el navegador puede entrar en "modo quirks" (modo de compatibilidad con navegadores antiguos).

---

### 2. Etiqueta `<html>`

```html
<html lang="es"></html>
```

**Explicación:**

- Etiqueta raíz que contiene todo el documento HTML
- **Atributo `lang`:** Declara el idioma del documento
  - `"es"` = Español
  - `"en"` = Inglés
  - `"fr"` = Francés

**Beneficios del atributo `lang`:**

- ✅ Mejora la accesibilidad (lectores de pantalla)
- ✅ Ayuda a los motores de búsqueda (SEO)
- ✅ Permite traducción automática del navegador
- ✅ Mejora el corrector ortográfico

---

### 3. Etiqueta `<head>`

```html
<head>
  <!-- Metadatos y recursos -->
</head>
```

**Explicación:**

- Contiene metadatos (información sobre el documento)
- **NO se muestra en la página visible**
- Incluye: título, codificación, estilos, scripts, etc.

#### 3.1 Meta Charset

```html
<meta charset="UTF-8" />
```

**Función:**

- Define la codificación de caracteres del documento
- **UTF-8:** Codificación universal que soporta todos los idiomas
- Permite usar caracteres especiales: ñ, á, é, í, ó, ú, ¿, ¡, €, etc.

**Importante:** Debe ser una de las primeras etiquetas en `<head>`.

#### 3.2 Meta Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

**Función:**

- Configura cómo se visualiza la página en dispositivos móviles
- **`width=device-width`:** Ajusta el ancho al dispositivo
- **`initial-scale=1.0`:** Nivel de zoom inicial al 100%

**Importante:** Esencial para **diseño responsive** (adaptable a móviles).

#### 3.3 Título del Documento

```html
<title>Estructura Basica HTML5</title>
```

**Función:**

- Define el título que aparece en:
  - Pestaña del navegador
  - Historial de navegación
  - Favoritos/marcadores
  - Resultados de búsqueda de Google

**Buenas prácticas:**

- Máximo 50-60 caracteres
- Descriptivo y único para cada página
- Importante para SEO

---

### 4. Etiqueta `<body>`

```html
<body>
  <!-- Contenido visible de la página -->
</body>
```

**Explicación:**

- Contiene **todo el contenido visible** de la página
- Incluye: texto, imágenes, videos, enlaces, formularios, etc.
- Solo puede haber **un `<body>` por documento**

#### Ejemplo de contenido:

```html
<body>
  <h1>Estructura Basica HTML5</h1>
  <p>Este es un documento HTML5 básico.</p>
</body>
```

---

## 📋 Estructura Completa Comentada

```html
<!DOCTYPE html>
<!-- 1. Declaración de tipo de documento -->
<html lang="es">
  <!-- 2. Etiqueta raíz con idioma -->
  <head>
    <!-- 3. Sección de metadatos -->
    <meta charset="UTF-8" />
    <!-- 4. Codificación de caracteres -->
    <meta
      name="viewport"
      content="width=device-width, 
                   initial-scale=1.0"
    />
    <!-- 5. Configuración responsive -->
    <title>Estructura Basica HTML5</title>
    <!-- 6. Título de la página -->
  </head>
  <body>
    <!-- 7. Contenido visible -->
    <h1>Estructura Basica HTML5</h1>
    <!-- 8. Encabezado principal -->
    <p>Este es un documento HTML5 básico.</p>
    <!-- 9. Párrafo -->
  </body>
</html>
```

---

## 🎯 Conceptos Clave

### Etiquetas de Apertura y Cierre

- **Etiqueta de apertura:** `<etiqueta>`
- **Etiqueta de cierre:** `</etiqueta>`
- **Auto-cierre:** `<meta />` (sin contenido interno)

### Anidamiento

Las etiquetas deben estar correctamente anidadas:

✅ **Correcto:**

```html
<html>
  <head>
    <title>Título</title>
  </head>
</html>
```

❌ **Incorrecto:**

```html
<html>
  <head>
    <title>Título</head>
  </title>
</html>
```

### Comentarios HTML

```html
<!-- Este es un comentario -->
<!-- 
  Los comentarios pueden
  ocupar múltiples líneas
-->
```

**Uso:**

- Documentar el código
- Desactivar temporalmente código
- **NO son visibles** en la página renderizada
- **SÍ son visibles** en el código fuente (F12)

---

## ✅ Checklist de Estructura Básica

Al crear un documento HTML5, verifica que tenga:

- [ ] `<!DOCTYPE html>` al inicio
- [ ] `<html lang="es">` con idioma apropiado
- [ ] `<head>` con metadatos
- [ ] `<meta charset="UTF-8" />`
- [ ] `<meta name="viewport" ...>` para responsive
- [ ] `<title>` descriptivo
- [ ] `<body>` con contenido
- [ ] Todas las etiquetas correctamente cerradas
- [ ] Indentación correcta (legibilidad)

---

## 🔍 Errores Comunes

### 1. Olvidar DOCTYPE

```html
<!-- ❌ MAL -->
<html>
  <head>
    ...
  </head>
</html>

<!-- ✅ BIEN -->
<!DOCTYPE html>
<html>
  <head>
    ...
  </head>
</html>
```

### 2. No cerrar etiquetas

```html
<!-- ❌ MAL -->
<p>
  Texto sin cerrar

  <!-- ✅ BIEN -->
</p>

<p>Texto cerrado correctamente</p>
```

### 3. Olvidar charset

```html
<!-- ❌ MAL - Los acentos pueden fallar -->
<head>
  <title>Título</title>
</head>

<!-- ✅ BIEN -->
<head>
  <meta charset="UTF-8" />
  <title>Título</title>
</head>
```

---

## 📚 Recursos Adicionales

- [MDN Web Docs - HTML](https://developer.mozilla.org/es/docs/Web/HTML)
- [W3C HTML5 Specification](https://www.w3.org/TR/html5/)
- [HTML5 Doctor](http://html5doctor.com/)
- [Can I Use - Compatibilidad HTML5](https://caniuse.com/)

---

## 💡 Tips para Practicar

1. **Crea múltiples páginas** con diferentes estructuras
2. **Valida tu HTML** en [W3C Validator](https://validator.w3.org/)
3. **Inspecciona páginas web** (F12) para ver su estructura
4. **Experimenta con meta tags** adicionales
5. **Practica la indentación** para código limpio

---

## 🎓 Siguiente Paso

Una vez domines la estructura básica, continúa con:

- Etiquetas semánticas (`<header>`, `<nav>`, `<main>`, `<footer>`)
- Encabezados (`<h1>` a `<h6>`)
- Listas (`<ul>`, `<ol>`, `<li>`)
- Enlaces (`<a>`)
- Imágenes (`<img>`)

---

**Actualizado:** 15 de octubre de 2025  
**Archivo de referencia:** `modulo-02-fundamentos-frontend/html/01-Estructura basica.html`
