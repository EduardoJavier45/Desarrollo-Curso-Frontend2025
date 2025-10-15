# Módulo 6: Desarrollo de Interfaces Interactivas con Framework Vue

**Duración:** 72 horas

## 📋 Objetivos

- Comprender los fundamentos de Vue.js
- Crear y usar componentes Vue
- Implementar reactividad con Vue
- Utilizar directivas y binding
- Configurar y usar Vue Router

## 📚 Contenidos

### 1. Introducción a Vue.js

- ¿Qué es Vue.js?
- Framework progresivo
- Componentes web
- Single Page Applications (SPA)
- Virtual DOM

### 2. Instalación y Configuración

- **CDN:** uso rápido de Vue
- **Vue CLI:** instalación y configuración
- Estructura de un proyecto Vue
- Vue DevTools

### 3. Componentes Vue

#### Morfología de un Componente

```vue
<template>
  <!-- HTML -->
</template>

<script>
// JavaScript
</script>

<style scoped>
/* CSS */
</style>
```

#### Single File Components (SFC)

- Template
- Script
- Style (scoped/global)

### 4. Templates y Rendering

#### Interpolaciones

- Mustache syntax: `{{ variable }}`
- Expresiones JavaScript

#### Directivas

- `v-if`, `v-else-if`, `v-else`: renderizado condicional
- `v-show`: visibilidad CSS
- `v-for`: listas y loops
- `v-bind` (`:attr`): binding de atributos
- `v-on` (`@event`): manejo de eventos
- `v-model`: two-way binding

### 5. Data Binding

#### One-way Binding

- Props (padre → hijo)
- Interpolación de datos

#### Two-way Binding

- `v-model` en inputs
- Modificadores de v-model

### 6. Manejo de Eventos

- `v-on` / `@click`, `@submit`, etc.
- Modificadores de eventos (`.prevent`, `.stop`, `.once`)
- Eventos personalizados
- Event payload

### 7. Vue Router

#### Instalación y Configuración

```bash
npm install vue-router
```

#### Tipos de Rutas

- **Rutas estáticas:** URLs fijas
- **Rutas dinámicas:** con parámetros (`:id`)
- **Rutas anidadas:** subrutas
- Navigation guards

#### Componentes Router

- `<router-link>`
- `<router-view>`
- Navegación programática

## 🛠️ Proyectos

### Proyecto 1: Blog Personal

Crea un blog con Vue.js usando componentes.

**Requisitos:**

- Componentes reutilizables
- Listado de posts
- Vista detalle de post
- Formulario de comentarios

### Proyecto 2: E-commerce con Router

Desarrolla un e-commerce con múltiples páginas usando Vue Router.

**Requisitos:**

- Home page
- Listado de productos
- Detalle de producto (ruta dinámica)
- Carrito de compras
- Vue Router configurado

## 📖 Recursos

### Documentación Oficial

- [Vue.js Documentation](https://v3.vuejs.org/)
- [Vue Router Documentation](https://router.vuejs.org/)
- [Vue Mastery](https://www.vuemastery.com/)
- [Vue School](https://vueschool.io/)

### Tutoriales

- [Vue.js Course - freeCodeCamp](https://www.youtube.com/watch?v=FXpIoQ_rT_c)
- [Vue.js Crash Course](https://www.youtube.com/watch?v=qZXt1Aom3Cs)

### Herramientas

- [Vue DevTools](https://devtools.vuejs.org/)
- [Vite](https://vitejs.dev/)

## 🎯 Ejercicios Prácticos

1. **Contador Interactivo:** Crea un contador con botones +/-
2. **Lista de Tareas:** To-Do list con agregar/eliminar
3. **Calculadora:** Calculadora funcional con Vue
4. **Galería de Imágenes:** Con filtros y búsqueda
5. **Formulario de Registro:** Con validación

## ✅ Checklist

- [ ] Instalo Vue CLI correctamente
- [ ] Creo componentes Single File
- [ ] Uso interpolación y directivas
- [ ] Implemento v-if y v-show correctamente
- [ ] Itero listas con v-for
- [ ] Uso v-model para formularios
- [ ] Manejo eventos con v-on
- [ ] Instalo y configuro Vue Router
- [ ] Creo rutas estáticas y dinámicas
- [ ] Navego entre páginas con router-link

---

**Módulo anterior:** [Módulo 5](../modulo-05-javascript-avanzado/README.md)  
**Siguiente módulo:** [Módulo 7](../modulo-07-vue-aplicaciones/README.md)
