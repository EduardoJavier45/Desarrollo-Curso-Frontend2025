# Módulo 7: Desarrollo de Aplicaciones Front-End con Framework Vue

**Duración:** 76 horas

## 📋 Objetivos

- Dominar componentización avanzada en Vue
- Consumir APIs REST con Axios
- Implementar gestión de estado con Vuex
- Realizar testing de aplicaciones Vue
- Integrar Firebase como backend

## 📚 Contenidos

### 1. Componentización Avanzada

#### Comunicación Padre-Hijo

- **Props:** pasar datos del padre al hijo
- **Emit:** enviar eventos del hijo al padre
- Validación de props
- Props default values

#### Ciclo de Vida de Componentes

```javascript
created(); // Componente creado
mounted(); // Montado en el DOM
updated(); // Datos actualizados
destroyed(); // Antes de destruir
```

#### Slots

- Slots básicos
- Named slots
- Scoped slots

#### Componentes Dinámicos

- `<component :is="componentName">`
- Keep-alive

### 2. Consumo de APIs REST

#### Conceptos REST

- Arquitectura REST
- Recursos y endpoints
- Verbos HTTP:
  - **GET:** Obtener datos
  - **POST:** Crear recursos
  - **PUT/PATCH:** Actualizar recursos
  - **DELETE:** Eliminar recursos

#### Librería Axios

```bash
npm install axios
```

**Uso básico:**

```javascript
import axios from "axios";

// GET
axios
  .get("/api/users")
  .then((response) => console.log(response.data))
  .catch((error) => console.error(error));

// POST
axios
  .post("/api/users", { name: "Juan" })
  .then((response) => console.log(response.data));
```

#### Firebase

- **Backend as a Service (BaaS)**
- Firestore Database
- Autenticación de usuarios
- Hosting
- Cloud Functions

### 3. Vuex: Gestión de Estado

#### ¿Por qué Vuex?

- Estado centralizado
- Flujo de datos predecible
- DevTools integration

#### Conceptos Core

**State:** Estado global de la aplicación

```javascript
state: {
  count: 0,
  user: null
}
```

**Mutations:** Cambios síncronos del estado

```javascript
mutations: {
  INCREMENT(state) {
    state.count++
  }
}
```

**Actions:** Lógica asíncrona

```javascript
actions: {
  async fetchUser({ commit }) {
    const user = await api.getUser()
    commit('SET_USER', user)
  }
}
```

**Getters:** Computed properties del estado

```javascript
getters: {
  isAuthenticated: (state) => !!state.user;
}
```

**Modules:** Separación del store en módulos

### 4. Testing

#### Pruebas Unitarias

**Jest:**

```bash
npm install --save-dev jest @vue/test-utils
```

**Mocha + Chai:**

```bash
npm install --save-dev mocha chai @vue/test-utils
```

**Vue Test Utils:**

- Montaje de componentes
- Simulación de eventos
- Aserciones

#### Pruebas End-to-End

**Cypress:**

```bash
npm install --save-dev cypress
```

**Nightwatch:**

```bash
npm install --save-dev nightwatch
```

## 🛠️ Proyectos

### Proyecto 1: CRUD Completo con API

Crea una aplicación CRUD conectada a una API real.

**Requisitos:**

- Axios para peticiones HTTP
- Operaciones CRUD completas
- Manejo de errores
- Loading states

### Proyecto 2: Aplicación con Vuex

Desarrolla una app con estado global usando Vuex.

**Sugerencias:**

- Carrito de compras
- Sistema de autenticación
- Dashboard con múltiples vistas

### Proyecto 3: Aplicación con Testing

Implementa una aplicación con cobertura de tests.

**Requisitos:**

- Tests unitarios de componentes
- Tests de Vuex (actions, mutations)
- Tests E2E básicos

## 📖 Recursos

### APIs y Axios

- [Axios Documentation](https://axios-http.com/)
- [RESTful API Design](https://restfulapi.net/)
- [JSONPlaceholder - Fake API](https://jsonplaceholder.typicode.com/)

### Vuex

- [Vuex Documentation](https://vuex.vuejs.org/)
- [Vuex Crash Course](https://www.youtube.com/watch?v=5lVQgZzLMHc)

### Firebase

- [Firebase Documentation](https://firebase.google.com/docs)
- [Vue + Firebase Tutorial](https://www.vuemastery.com/courses/real-world-vue-js/firebase-introduction)

### Testing

- [Jest Documentation](https://jestjs.io/)
- [Vue Test Utils](https://vue-test-utils.vuejs.org/)
- [Cypress Documentation](https://www.cypress.io/)

## ✅ Checklist

### Componentes Avanzados

- [ ] Uso props correctamente
- [ ] Emito eventos personalizados
- [ ] Aplico ciclo de vida de componentes
- [ ] Uso slots efectivamente

### APIs y Axios

- [ ] Instalo y configuro Axios
- [ ] Realizo peticiones GET, POST, PUT, DELETE
- [ ] Manejo errores en peticiones
- [ ] Trabajo con APIs reales

### Vuex

- [ ] Instalo y configuro Vuex
- [ ] Defino state, mutations y actions
- [ ] Uso getters correctamente
- [ ] Organizo store en módulos

### Firebase

- [ ] Configuro proyecto en Firebase
- [ ] Conecto Vue con Firebase
- [ ] Implemento autenticación
- [ ] Uso Firestore para datos

### Testing

- [ ] Escribo tests unitarios
- [ ] Testo componentes Vue
- [ ] Testo Vuex store
- [ ] Implemento tests E2E básicos

---

**Módulo anterior:** [Módulo 6](../modulo-06-vue-interfaces/README.md)  
**Siguiente módulo:** [Módulo 8](../modulo-08-portafolio/README.md)
