# 📝 Etiquetas Semánticas HTML5 - Listado Completo

**Fecha:** 15 de octubre de 2025  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End  
**Tema:** Etiquetas Semánticas HTML5

---

## 🎯 ¿Qué son las Etiquetas Semánticas?

Las etiquetas semánticas son elementos HTML que tienen un **significado específico** y describen claramente su contenido tanto para los desarrolladores como para los navegadores y motores de búsqueda.

### Diferencia con Etiquetas No Semánticas

**No Semántico (div y span):**

- No indican qué tipo de contenido contienen
- Solo sirven para agrupar elementos visualmente
- No aportan información sobre su propósito

**Semántico:**

- Describe claramente el tipo de contenido
- Mejora la accesibilidad
- Facilita el SEO
- Hace el código más legible y mantenible

---

## 📋 Etiquetas Semánticas Principales

### 🏗️ Estructura de Página

#### 1. **header**

- **Propósito:** Cabecera de la página o sección
- **Contenido típico:** Logo, navegación principal, título del sitio
- **Ubicación:** Parte superior de la página o inicio de una sección
- **Puede repetirse:** Sí (una por página/sección)
- **Uso común:** Encabezado principal del sitio web

#### 2. **nav**

- **Propósito:** Bloque de navegación principal
- **Contenido típico:** Menús, enlaces de navegación
- **Ubicación:** Generalmente en header o sidebar
- **Puede repetirse:** Sí (pero solo para navegación importante)
- **Uso común:** Menú principal, breadcrumbs, paginación

#### 3. **main**

- **Propósito:** Contenido principal del documento
- **Contenido típico:** El tema central de la página
- **Ubicación:** Entre header y footer
- **Puede repetirse:** NO - Solo una vez por página
- **Uso común:** Área de contenido único de cada página

#### 4. **aside**

- **Propósito:** Contenido complementario o tangencial
- **Contenido típico:** Barras laterales, widgets, enlaces relacionados
- **Ubicación:** Lateral o dentro de main
- **Puede repetirse:** Sí
- **Uso común:** Sidebar, anuncios, información adicional

#### 5. **footer**

- **Propósito:** Pie de página
- **Contenido típico:** Copyright, enlaces legales, redes sociales, información de contacto
- **Ubicación:** Parte inferior de la página o sección
- **Puede repetirse:** Sí (una por página/sección)
- **Uso común:** Pie de página del sitio

---

### 📄 Contenido y Agrupación

#### 6. **section**

- **Propósito:** Sección temática del documento
- **Contenido típico:** Agrupación de contenido relacionado
- **Características:** Generalmente tiene un encabezado
- **Uso común:** Dividir página en secciones lógicas
- **Ejemplo de uso:** Sección "Sobre nosotros", "Servicios", "Testimonios"

#### 7. **article**

- **Propósito:** Contenido independiente y autocontenido
- **Contenido típico:** Artículos de blog, noticias, posts, comentarios
- **Características:** Puede funcionar por sí solo fuera del contexto
- **Uso común:** Entradas de blog, productos, noticias
- **Sindicalizable:** Sí (puede distribuirse en RSS, por ejemplo)

#### 8. **div**

- **Propósito:** Contenedor genérico sin significado semántico
- **Contenido típico:** Cualquier contenido que necesite agrupación visual
- **Cuándo usar:** Cuando NO existe una etiqueta semántica apropiada
- **Uso común:** Contenedores para estilos CSS, layouts
- **Nota:** Usar solo si no hay alternativa semántica

---

### 📰 Contenido Específico

#### 9. **figure**

- **Propósito:** Contenido ilustrativo referenciado desde el contenido principal
- **Contenido típico:** Imágenes, diagramas, gráficos, código
- **Acompaña con:** figcaption para descripción
- **Uso común:** Ilustraciones con leyenda
- **Característica:** Puede moverse sin afectar el flujo del documento

#### 10. **figcaption**

- **Propósito:** Leyenda o descripción de un figure
- **Contenido típico:** Texto descriptivo de la imagen o contenido
- **Ubicación:** Dentro de figure (al inicio o al final)
- **Uso común:** Pie de foto, título de diagrama
- **Nota:** Opcional pero recomendado

#### 11. **mark**

- **Propósito:** Texto resaltado o destacado
- **Contenido típico:** Términos relevantes, resultados de búsqueda
- **Apariencia:** Generalmente con fondo amarillo
- **Uso común:** Resaltar palabras clave, coincidencias de búsqueda
- **Diferencia con strong:** mark es para relevancia contextual, strong para importancia

#### 12. **time**

- **Propósito:** Fecha, hora o duración
- **Contenido típico:** Fechas de publicación, horarios, eventos
- **Atributo importante:** datetime (formato ISO)
- **Uso común:** Timestamps, fechas de artículos
- **Beneficio:** Máquinas pueden entender y procesar la fecha

---

### 📝 Detalles y Definiciones

#### 13. **details**

- **Propósito:** Widget interactivo expandible/colapsable
- **Contenido típico:** Información adicional que puede ocultarse
- **Interactividad:** Nativa del navegador
- **Uso común:** FAQs, acordeones, información desplegable
- **Estado:** Cerrado por defecto (puede abrirse con atributo "open")

#### 14. **summary**

- **Propósito:** Título o resumen visible de details
- **Contenido típico:** Pregunta o título clickeable
- **Ubicación:** Primer hijo de details
- **Uso común:** Encabezado del acordeón
- **Interactividad:** Clickeable para abrir/cerrar

#### 15. **dialog**

- **Propósito:** Ventana de diálogo o modal
- **Contenido típico:** Mensajes, formularios, confirmaciones
- **Características:** Puede mostrarse/ocultarse
- **Uso común:** Modales, alertas, formularios emergentes
- **Métodos:** show(), showModal(), close()

---

### 🎨 Elementos Inline Semánticos

#### 16. **strong**

- **Propósito:** Texto de gran importancia
- **Significado:** Importancia, seriedad, urgencia
- **Apariencia:** Generalmente negrita
- **Uso común:** Advertencias importantes, términos clave
- **Diferencia con b:** strong tiene significado semántico, b es solo estilo

#### 17. **em**

- **Propósito:** Énfasis en el texto
- **Significado:** Cambio en el tono o énfasis al leer
- **Apariencia:** Generalmente cursiva
- **Uso común:** Énfasis en palabras, cambio de tono
- **Diferencia con i:** em tiene significado semántico, i es solo estilo

#### 18. **abbr**

- **Propósito:** Abreviatura o acrónimo
- **Contenido típico:** Siglas, abreviaturas
- **Atributo importante:** title (texto completo)
- **Uso común:** HTML, CSS, ONU, Dr., etc.
- **Accesibilidad:** Lectores de pantalla leen el title

#### 19. **code**

- **Propósito:** Código de computadora inline
- **Contenido típico:** Nombres de variables, funciones, comandos
- **Apariencia:** Fuente monoespaciada
- **Uso común:** Mencionar código dentro de párrafos
- **Para bloques:** Usar con pre

#### 20. **kbd**

- **Propósito:** Entrada de teclado del usuario
- **Contenido típico:** Teclas, atajos de teclado
- **Apariencia:** Similar a teclas de teclado
- **Uso común:** Ctrl + C, Enter, Alt + F4
- **Contexto:** Instrucciones de uso

#### 21. **samp**

- **Propósito:** Salida de muestra de un programa
- **Contenido típico:** Resultados, outputs, mensajes del sistema
- **Apariencia:** Fuente monoespaciada
- **Uso común:** Ejemplos de resultados de comandos
- **Complemento:** Usado con code y kbd

#### 22. **var**

- **Propósito:** Variable matemática o de programación
- **Contenido típico:** Nombres de variables
- **Apariencia:** Generalmente cursiva
- **Uso común:** Ecuaciones, expresiones matemáticas
- **Contexto:** Documentación técnica

---

### 📌 Citas y Referencias

#### 23. **blockquote**

- **Propósito:** Cita larga de otra fuente
- **Contenido típico:** Citas extensas, testimonios
- **Atributo útil:** cite (URL de la fuente)
- **Apariencia:** Generalmente con margen/sangría
- **Uso común:** Citas de artículos, testimonios de clientes
- **Diferencia con q:** blockquote es para citas en bloque

#### 24. **q**

- **Propósito:** Cita corta inline
- **Contenido típico:** Citas breves dentro de párrafos
- **Atributo útil:** cite (URL de la fuente)
- **Apariencia:** Entre comillas automáticas
- **Uso común:** Citas dentro del texto
- **Diferencia con blockquote:** q es inline, blockquote es bloque

#### 25. **cite**

- **Propósito:** Título de obra creativa
- **Contenido típico:** Libros, películas, canciones, artículos
- **Apariencia:** Generalmente cursiva
- **Uso común:** Referencias bibliográficas
- **Nota:** NO para nombres de personas

---

### 📍 Direcciones y Contacto

#### 26. **address**

- **Propósito:** Información de contacto
- **Contenido típico:** Dirección, email, teléfono, redes sociales
- **Contexto:** Del autor o propietario del documento
- **Ubicación:** Generalmente en footer
- **Uso común:** Datos de contacto del sitio o autor del artículo
- **Nota:** NO para direcciones postales generales

---

### 🎭 Contenido Avanzado

#### 27. **data**

- **Propósito:** Vincular contenido con valor legible por máquinas
- **Atributo importante:** value (valor procesable)
- **Contenido típico:** Datos con representación humana y de máquina
- **Uso común:** Productos, medidas, códigos
- **Ejemplo de uso:** Códigos de producto con nombres legibles

#### 28. **progress**

- **Propósito:** Indicador de progreso de tarea
- **Atributos:** value (actual), max (máximo)
- **Apariencia:** Barra de progreso
- **Uso común:** Subida de archivos, completado de formularios
- **Estado:** Determinado (con value) o indeterminado

#### 29. **meter**

- **Propósito:** Medida escalar dentro de un rango
- **Atributos:** value, min, max, low, high, optimum
- **Apariencia:** Barra con colores según rangos
- **Uso común:** Temperatura, nivel de batería, puntuación
- **Diferencia con progress:** meter es estático, progress es dinámico

---

## 🎯 Beneficios de Usar Etiquetas Semánticas

### 1. **Accesibilidad**

- Lectores de pantalla pueden navegar mejor
- Usuarios con discapacidades entienden la estructura
- Mejora la experiencia para todos

### 2. **SEO (Posicionamiento)**

- Google comprende mejor el contenido
- Mejora el ranking en búsquedas
- Rich snippets más precisos

### 3. **Mantenibilidad**

- Código más legible
- Más fácil de mantener
- Colaboración más efectiva

### 4. **Estandarización**

- Código consistente
- Mejores prácticas
- Menos ambigüedad

---

## 📊 Cuándo Usar Cada Etiqueta

### Estructura de Página

- **header** → Cabecera del sitio o sección
- **nav** → Menú de navegación
- **main** → Contenido principal único
- **aside** → Contenido complementario
- **footer** → Pie de página
- **section** → Sección temática
- **article** → Contenido independiente

### Contenido Multimedia

- **figure** → Imagen con contexto
- **figcaption** → Descripción de figure

### Texto con Significado

- **strong** → Importancia alta
- **em** → Énfasis
- **mark** → Resaltado relevante
- **abbr** → Abreviaturas
- **time** → Fechas y horas

### Código y Técnico

- **code** → Código inline
- **kbd** → Teclas de teclado
- **samp** → Salida de programa
- **var** → Variables

### Citas

- **blockquote** → Citas largas
- **q** → Citas cortas
- **cite** → Títulos de obras

### Interactivo

- **details/summary** → Acordeones
- **dialog** → Modales
- **progress** → Barras de progreso
- **meter** → Medidores

---

## ❌ Errores Comunes

### 1. Usar div para todo

**Problema:** Pierde semántica  
**Solución:** Evaluar si existe etiqueta semántica apropiada

### 2. Múltiples main

**Problema:** Solo puede haber uno por página  
**Solución:** Un solo main con todo el contenido principal

### 3. nav para cualquier enlace

**Problema:** nav es solo para navegación principal  
**Solución:** Solo usar para menús importantes

### 4. section sin encabezado

**Problema:** section debe tener título  
**Solución:** Agregar h2-h6 al inicio

### 5. article vs section confusión

**Problema:** No saber cuál usar  
**Solución:** article = independiente, section = agrupación temática

### 6. Confundir strong con b

**Problema:** Usar b cuando se necesita importancia semántica  
**Solución:** strong para importancia, b solo para estilo

### 7. Confundir em con i

**Problema:** Usar i cuando se necesita énfasis  
**Solución:** em para énfasis, i solo para estilo

---

## 🎓 Reglas de Oro

1. **Si existe una etiqueta semántica, úsala**
2. **div y span son últimos recursos**
3. **Solo un main por página**
4. **nav solo para navegación principal**
5. **section debe tener encabezado**
6. **article debe poder vivir solo**
7. **Piensa en accesibilidad primero**
8. **El SEO mejorará naturalmente**

---

## 📚 Jerarquía Típica de una Página

```
Página Web
│
├── header (cabecera del sitio)
│   ├── logo
│   └── nav (navegación principal)
│
├── main (contenido principal)
│   │
│   ├── section (sección 1)
│   │   ├── h2 (título de sección)
│   │   ├── article (artículo 1)
│   │   └── article (artículo 2)
│   │
│   ├── section (sección 2)
│   │   ├── h2
│   │   └── div (contenido)
│   │
│   └── aside (contenido relacionado)
│
└── footer (pie de página)
    ├── nav (navegación secundaria)
    ├── address (contacto)
    └── copyright
```

---

## 🔍 Recursos para Profundizar

- **MDN Web Docs:** Documentación oficial de cada etiqueta
- **HTML5 Doctor:** Guías específicas de uso
- **Can I Use:** Compatibilidad de navegadores
- **W3C HTML5 Spec:** Especificación oficial
- **WebAIM:** Guías de accesibilidad

---

## ✅ Checklist de Uso Semántico

Al crear una página, pregúntate:

- [ ] ¿Usé header para la cabecera?
- [ ] ¿Usé nav para la navegación principal?
- [ ] ¿Hay un único main?
- [ ] ¿Usé section para agrupar temáticamente?
- [ ] ¿Usé article para contenido independiente?
- [ ] ¿Usé aside para contenido complementario?
- [ ] ¿Usé footer para el pie de página?
- [ ] ¿Usé figure/figcaption para imágenes con contexto?
- [ ] ¿Evité div cuando había alternativa semántica?
- [ ] ¿El código es accesible?
- [ ] ¿Los lectores de pantalla pueden navegar bien?

---

**Actualizado:** 15 de octubre de 2025  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End  
**Próximo tema:** Implementación práctica de etiquetas semánticas
