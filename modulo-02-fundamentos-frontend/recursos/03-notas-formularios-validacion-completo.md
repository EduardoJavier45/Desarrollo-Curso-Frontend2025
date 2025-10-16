# 📝 Formularios HTML5 y Validación - Guía Completa

**Fecha:** 15 de octubre de 2025  
**Módulo:** 2 - Fundamentos de Desarrollo Front-End  
**Tema:** Formularios HTML5 y Validación

---

## 🎯 ¿Qué son los Formularios HTML?

Los formularios son elementos interactivos que permiten a los usuarios enviar información al servidor. Son fundamentales para:

- Registro de usuarios
- Inicio de sesión
- Búsquedas
- Comentarios
- Compras online
- Encuestas
- Cualquier interacción que requiera entrada de datos

---

## 📋 Estructura Básica de un Formulario

### Etiqueta `<form>`

La etiqueta `<form>` es el contenedor principal que agrupa todos los campos del formulario.

**Atributos principales:**

- **`action`:** URL donde se enviarán los datos
- **`method`:** Método HTTP (GET o POST)
- **`enctype`:** Tipo de codificación (para archivos)
- **`autocomplete`:** Activar/desactivar autocompletado
- **`novalidate`:** Desactivar validación HTML5

**Ejemplo básico:**

```html
<form action="/procesar-datos" method="POST">
  <!-- Campos del formulario aquí -->
</form>
```

---

## 🔤 Tipos de Campos de Entrada (Input Types)

### 1. **Text** - Texto Simple

**Uso:** Nombres, apellidos, textos cortos

```html
<label for="nombre">Nombre:</label>
<input type="text" id="nombre" name="nombre" placeholder="Ingresa tu nombre" />
```

**Atributos útiles:**

- `maxlength`: Máximo de caracteres
- `minlength`: Mínimo de caracteres
- `pattern`: Expresión regular
- `placeholder`: Texto de ayuda

---

### 2. **Email** - Correo Electrónico

**Uso:** Direcciones de email con validación automática

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email" required />
```

**Características:**

- Valida formato de email automáticamente
- Teclado especial en móviles (@, .com)
- Acepta: usuario@dominio.com

**Ejemplo con múltiples emails:**

```html
<input type="email" name="emails" multiple />
<!-- Permite: email1@example.com, email2@example.com -->
```

---

### 3. **Password** - Contraseña

**Uso:** Campos de contraseña (texto oculto)

```html
<label for="password">Contraseña:</label>
<input type="password" id="password" name="password" minlength="8" required />
```

**Características:**

- Oculta el texto con asteriscos/puntos
- No se autocompleta por defecto
- Útil para seguridad

**Ejemplo con requisitos:**

```html
<input
  type="password"
  name="password"
  minlength="8"
  pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
  title="Debe contener al menos un número, una mayúscula, una minúscula y 8 caracteres"
/>
```

---

### 4. **Number** - Números

**Uso:** Cantidades, edades, números enteros o decimales

```html
<label for="edad">Edad:</label>
<input type="number" id="edad" name="edad" min="18" max="100" step="1" />
```

**Atributos:**

- `min`: Valor mínimo
- `max`: Valor máximo
- `step`: Incremento (1 = enteros, 0.01 = decimales)

**Ejemplo con decimales:**

```html
<label for="precio">Precio:</label>
<input type="number" name="precio" min="0" step="0.01" placeholder="0.00" />
```

---

### 5. **Tel** - Teléfono

**Uso:** Números telefónicos

```html
<label for="telefono">Teléfono:</label>
<input
  type="tel"
  id="telefono"
  name="telefono"
  pattern="[0-9]{9}"
  placeholder="912345678"
/>
```

**Características:**

- Teclado numérico en móviles
- No valida automáticamente (usar pattern)

**Ejemplo con formato específico:**

```html
<input
  type="tel"
  name="telefono"
  pattern="\+56[0-9]{9}"
  placeholder="+56912345678"
  title="Formato: +56XXXXXXXXX"
/>
```

---

### 6. **URL** - Dirección Web

**Uso:** Páginas web, enlaces

```html
<label for="sitio">Sitio Web:</label>
<input type="url" id="sitio" name="sitio" placeholder="https://ejemplo.com" />
```

**Características:**

- Valida formato de URL
- Debe incluir protocolo (http://, https://)

---

### 7. **Date** - Fecha

**Uso:** Selección de fechas

```html
<label for="nacimiento">Fecha de Nacimiento:</label>
<input
  type="date"
  id="nacimiento"
  name="nacimiento"
  min="1900-01-01"
  max="2024-12-31"
/>
```

**Atributos:**

- `min`: Fecha mínima
- `max`: Fecha máxima
- Formato: YYYY-MM-DD

**Ejemplo con fecha actual por defecto:**

```html
<input type="date" name="fecha" value="2025-10-15" />
```

---

### 8. **Time** - Hora

**Uso:** Selección de hora

```html
<label for="hora">Hora:</label>
<input type="time" id="hora" name="hora" min="09:00" max="18:00" />
```

**Formato:** HH:MM (24 horas)

---

### 9. **Datetime-local** - Fecha y Hora

**Uso:** Fecha y hora sin zona horaria

```html
<label for="cita">Fecha y Hora de Cita:</label>
<input type="datetime-local" id="cita" name="cita" />
```

**Formato:** YYYY-MM-DDTHH:MM

---

### 10. **Month** - Mes

**Uso:** Selección de mes y año

```html
<label for="mes">Mes:</label> <input type="month" id="mes" name="mes" />
```

**Formato:** YYYY-MM

---

### 11. **Week** - Semana

**Uso:** Selección de semana del año

```html
<label for="semana">Semana:</label>
<input type="week" id="semana" name="semana" />
```

**Formato:** YYYY-W##

---

### 12. **Color** - Selector de Color

**Uso:** Elegir colores

```html
<label for="color">Color Favorito:</label>
<input type="color" id="color" name="color" value="#ff0000" />
```

**Características:**

- Abre selector de color nativo
- Valor en formato hexadecimal (#RRGGBB)

---

### 13. **Range** - Rango/Deslizador

**Uso:** Selección de valores en un rango

```html
<label for="volumen">Volumen:</label>
<input
  type="range"
  id="volumen"
  name="volumen"
  min="0"
  max="100"
  value="50"
  step="10"
/>
<output for="volumen">50</output>
```

**Atributos:**

- `min`, `max`, `value`, `step`
- Útil con JavaScript para mostrar valor

---

### 14. **File** - Subida de Archivos

**Uso:** Cargar archivos

```html
<label for="archivo">Subir archivo:</label>
<input type="file" id="archivo" name="archivo" accept="image/*" />
```

**Atributos:**

- `accept`: Tipos de archivo permitidos
- `multiple`: Permitir múltiples archivos

**Ejemplos de accept:**

```html
<!-- Solo imágenes -->
<input type="file" accept="image/*" />

<!-- Solo PDF -->
<input type="file" accept=".pdf" />

<!-- Imágenes y PDF -->
<input type="file" accept="image/*, .pdf" />

<!-- Múltiples archivos -->
<input type="file" multiple />
```

---

### 15. **Hidden** - Campo Oculto

**Uso:** Datos no visibles para el usuario

```html
<input type="hidden" name="usuario_id" value="12345" />
```

**Uso común:**

- IDs de sesión
- Tokens CSRF
- Datos de seguimiento

---

### 16. **Search** - Búsqueda

**Uso:** Campos de búsqueda

```html
<label for="buscar">Buscar:</label>
<input type="search" id="buscar" name="q" placeholder="¿Qué buscas?" />
```

**Características:**

- Botón de borrar (X) incluido
- Comportamiento especial en algunos navegadores

---

### 17. **Checkbox** - Casilla de Verificación

**Uso:** Opciones múltiples (sí/no, verdadero/falso)

```html
<label>
  <input type="checkbox" name="terminos" value="aceptado" required />
  Acepto los términos y condiciones
</label>
```

**Múltiples checkboxes:**

```html
<fieldset>
  <legend>Intereses:</legend>
  <label
    ><input type="checkbox" name="intereses" value="deportes" /> Deportes</label
  >
  <label
    ><input type="checkbox" name="intereses" value="musica" /> Música</label
  >
  <label
    ><input type="checkbox" name="intereses" value="tecnologia" />
    Tecnología</label
  >
</fieldset>
```

**Atributo `checked`:**

```html
<input type="checkbox" name="newsletter" checked />
```

---

### 18. **Radio** - Botón de Opción

**Uso:** Selección única entre opciones

```html
<fieldset>
  <legend>Género:</legend>
  <label
    ><input type="radio" name="genero" value="masculino" required />
    Masculino</label
  >
  <label
    ><input type="radio" name="genero" value="femenino" required />
    Femenino</label
  >
  <label><input type="radio" name="genero" value="otro" required /> Otro</label>
</fieldset>
```

**Importante:**

- Mismo `name` para agrupar opciones
- Solo uno puede estar seleccionado
- Usar `required` en uno para validar el grupo

---

## 📝 Otros Elementos de Formulario

### **Textarea** - Área de Texto

**Uso:** Textos largos, comentarios, descripciones

```html
<label for="comentario">Comentario:</label>
<textarea
  id="comentario"
  name="comentario"
  rows="5"
  cols="50"
  maxlength="500"
  placeholder="Escribe tu comentario aquí..."
></textarea>
```

**Atributos:**

- `rows`: Filas visibles
- `cols`: Columnas (ancho)
- `maxlength`: Máximo de caracteres
- `wrap`: Comportamiento del salto de línea

---

### **Select** - Lista Desplegable

**Uso:** Selección de opciones predefinidas

```html
<label for="pais">País:</label>
<select id="pais" name="pais" required>
  <option value="">-- Selecciona un país --</option>
  <option value="cl">Chile</option>
  <option value="ar">Argentina</option>
  <option value="pe">Perú</option>
  <option value="mx">México</option>
</select>
```

**Con opción preseleccionada:**

```html
<option value="cl" selected>Chile</option>
```

**Con grupos (optgroup):**

```html
<select name="ubicacion">
  <optgroup label="América">
    <option value="cl">Chile</option>
    <option value="ar">Argentina</option>
  </optgroup>
  <optgroup label="Europa">
    <option value="es">España</option>
    <option value="fr">Francia</option>
  </optgroup>
</select>
```

**Selección múltiple:**

```html
<select name="idiomas" multiple size="4">
  <option value="es">Español</option>
  <option value="en">Inglés</option>
  <option value="fr">Francés</option>
  <option value="de">Alemán</option>
</select>
```

---

### **Button** - Botones

#### Submit - Enviar Formulario

```html
<button type="submit">Enviar</button>
<!-- o -->
<input type="submit" value="Enviar" />
```

#### Reset - Limpiar Formulario

```html
<button type="reset">Limpiar</button>
```

#### Button - Botón Genérico

```html
<button type="button" onclick="miFuncion()">Hacer algo</button>
```

**Diferencia entre button e input:**

- `<button>` puede contener HTML (imágenes, iconos)
- `<input type="submit">` solo puede tener texto en value

**Ejemplo con icono:**

```html
<button type="submit">
  <img src="enviar-icon.svg" alt="" /> Enviar Formulario
</button>
```

---

### **Fieldset y Legend** - Agrupar Campos

**Uso:** Agrupar campos relacionados

```html
<fieldset>
  <legend>Información Personal</legend>
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" />

  <label for="apellido">Apellido:</label>
  <input type="text" id="apellido" name="apellido" />
</fieldset>

<fieldset>
  <legend>Información de Contacto</legend>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" />

  <label for="telefono">Teléfono:</label>
  <input type="tel" id="telefono" name="telefono" />
</fieldset>
```

**Fieldset deshabilitado:**

```html
<fieldset disabled>
  <!-- Todos los campos dentro estarán deshabilitados -->
</fieldset>
```

---

### **Datalist** - Autocompletado

**Uso:** Lista de sugerencias para inputs

```html
<label for="navegador">Navegador favorito:</label>
<input type="text" id="navegador" name="navegador" list="navegadores" />
<datalist id="navegadores">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
  <option value="Safari"></option>
  <option value="Edge"></option>
  <option value="Opera"></option>
</datalist>
```

**Características:**

- Usuario puede escribir o elegir de la lista
- No restringe valores
- Útil para sugerencias

---

### **Output** - Resultado de Cálculo

**Uso:** Mostrar resultado de operación

```html
<form oninput="resultado.value = parseInt(a.value) + parseInt(b.value)">
  <input type="number" id="a" value="0" /> +
  <input type="number" id="b" value="0" /> =
  <output name="resultado" for="a b">0</output>
</form>
```

---

## ✅ Atributos de Validación HTML5

### 1. **required** - Campo Obligatorio

```html
<input type="text" name="nombre" required />
<textarea name="mensaje" required></textarea>
<select name="pais" required>
  <option value="">Selecciona...</option>
  <option value="cl">Chile</option>
</select>
```

**Efecto:** El formulario no se envía si está vacío

---

### 2. **minlength y maxlength** - Longitud de Texto

```html
<!-- Mínimo 3 caracteres, máximo 20 -->
<input type="text" name="usuario" minlength="3" maxlength="20" required />

<!-- Mensaje entre 10 y 500 caracteres -->
<textarea name="mensaje" minlength="10" maxlength="500"></textarea>
```

---

### 3. **min y max** - Valores Numéricos y Fechas

```html
<!-- Edad entre 18 y 100 -->
<input type="number" name="edad" min="18" max="100" />

<!-- Fecha entre 2020 y 2025 -->
<input type="date" name="fecha" min="2020-01-01" max="2025-12-31" />

<!-- Precio mínimo $10 -->
<input type="number" name="precio" min="10" step="0.01" />
```

---

### 4. **pattern** - Expresión Regular

```html
<!-- Solo letras (mayúsculas y minúsculas) -->
<input type="text" name="nombre" pattern="[A-Za-z]+" title="Solo letras" />

<!-- Código postal chileno (7 dígitos) -->
<input type="text" name="codigo_postal" pattern="[0-9]{7}" title="7 dígitos" />

<!-- RUT chileno (formato XX.XXX.XXX-X) -->
<input
  type="text"
  name="rut"
  pattern="[0-9]{1,2}\.[0-9]{3}\.[0-9]{3}-[0-9Kk]"
  title="Formato: 12.345.678-9"
/>

<!-- Contraseña fuerte (mínimo 8 caracteres, 1 mayúscula, 1 minúscula, 1 número) -->
<input
  type="password"
  name="password"
  pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
  title="Mínimo 8 caracteres, incluir mayúscula, minúscula y número"
/>

<!-- Nombre de usuario (alfanumérico, guión bajo, 3-16 caracteres) -->
<input
  type="text"
  name="username"
  pattern="[a-zA-Z0-9_]{3,16}"
  title="3-16 caracteres alfanuméricos"
/>
```

---

### 5. **step** - Incrementos Válidos

```html
<!-- Solo números pares -->
<input type="number" name="numero" step="2" />

<!-- Solo múltiplos de 5 -->
<input type="number" name="cantidad" min="0" max="100" step="5" />

<!-- Decimales con 2 dígitos -->
<input type="number" name="precio" step="0.01" />

<!-- Intervalos de 15 minutos -->
<input type="time" name="hora" step="900" />
```

---

### 6. **placeholder** - Texto de Ayuda

```html
<input type="email" name="email" placeholder="usuario@ejemplo.com" />
<input type="tel" name="telefono" placeholder="+56 9 1234 5678" />
<textarea name="mensaje" placeholder="Escribe tu mensaje aquí..."></textarea>
```

**Nota:** Placeholder NO reemplaza a label

---

### 7. **autocomplete** - Autocompletado

```html
<!-- Activar -->
<input type="text" name="nombre" autocomplete="on" />

<!-- Desactivar -->
<input type="password" name="password" autocomplete="off" />

<!-- Valores específicos -->
<input type="text" name="nombre" autocomplete="name" />
<input type="email" name="email" autocomplete="email" />
<input type="tel" name="telefono" autocomplete="tel" />
<input type="text" name="direccion" autocomplete="street-address" />
<input type="text" name="ciudad" autocomplete="address-level2" />
<input type="text" name="pais" autocomplete="country" />
```

---

### 8. **disabled** - Campo Deshabilitado

```html
<input type="text" name="campo" value="No editable" disabled />
```

**Características:**

- No se puede editar
- No se envía con el formulario
- Estilo visual diferente (gris)

---

### 9. **readonly** - Solo Lectura

```html
<input type="text" name="usuario" value="admin" readonly />
```

**Diferencia con disabled:**

- Se puede seleccionar el texto
- SÍ se envía con el formulario
- Se puede hacer focus

---

### 10. **autofocus** - Foco Automático

```html
<input type="text" name="busqueda" autofocus />
```

**Nota:** Solo un campo por página debe tener autofocus

---

## 🎨 Ejemplo de Formulario Completo con Validación

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Formulario de Registro</title>
  </head>
  <body>
    <form action="/registro" method="POST" novalidate>
      <!-- Información Personal -->
      <fieldset>
        <legend>Información Personal</legend>

        <label for="nombre">Nombre Completo: *</label>
        <input
          type="text"
          id="nombre"
          name="nombre"
          required
          minlength="3"
          maxlength="50"
          placeholder="Juan Pérez"
          pattern="[A-Za-záéíóúÁÉÍÓÚñÑ\s]+"
          title="Solo letras y espacios"
        />

        <label for="email">Email: *</label>
        <input
          type="email"
          id="email"
          name="email"
          required
          placeholder="usuario@ejemplo.com"
        />

        <label for="telefono">Teléfono:</label>
        <input
          type="tel"
          id="telefono"
          name="telefono"
          pattern="[0-9]{9}"
          placeholder="912345678"
          title="9 dígitos sin espacios"
        />

        <label for="fecha_nacimiento">Fecha de Nacimiento: *</label>
        <input
          type="date"
          id="fecha_nacimiento"
          name="fecha_nacimiento"
          required
          min="1920-01-01"
          max="2007-12-31"
        />

        <label>Género: *</label>
        <label
          ><input type="radio" name="genero" value="masculino" required />
          Masculino</label
        >
        <label
          ><input type="radio" name="genero" value="femenino" required />
          Femenino</label
        >
        <label
          ><input type="radio" name="genero" value="otro" required />
          Otro</label
        >
      </fieldset>

      <!-- Dirección -->
      <fieldset>
        <legend>Dirección</legend>

        <label for="direccion">Dirección:</label>
        <input
          type="text"
          id="direccion"
          name="direccion"
          autocomplete="street-address"
        />

        <label for="ciudad">Ciudad:</label>
        <input
          type="text"
          id="ciudad"
          name="ciudad"
          autocomplete="address-level2"
        />

        <label for="pais">País: *</label>
        <select id="pais" name="pais" required>
          <option value="">-- Selecciona un país --</option>
          <option value="cl">Chile</option>
          <option value="ar">Argentina</option>
          <option value="pe">Perú</option>
          <option value="mx">México</option>
          <option value="co">Colombia</option>
        </select>
      </fieldset>

      <!-- Cuenta -->
      <fieldset>
        <legend>Crear Cuenta</legend>

        <label for="usuario">Nombre de Usuario: *</label>
        <input
          type="text"
          id="usuario"
          name="usuario"
          required
          minlength="4"
          maxlength="16"
          pattern="[a-zA-Z0-9_]+"
          placeholder="usuario123"
          title="4-16 caracteres: letras, números y guión bajo"
        />

        <label for="password">Contraseña: *</label>
        <input
          type="password"
          id="password"
          name="password"
          required
          minlength="8"
          pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
          title="Mínimo 8 caracteres con mayúscula, minúscula y número"
        />

        <label for="password_confirm">Confirmar Contraseña: *</label>
        <input
          type="password"
          id="password_confirm"
          name="password_confirm"
          required
        />
      </fieldset>

      <!-- Preferencias -->
      <fieldset>
        <legend>Preferencias</legend>

        <label for="biografia">Biografía (opcional):</label>
        <textarea
          id="biografia"
          name="biografia"
          rows="5"
          maxlength="500"
          placeholder="Cuéntanos sobre ti..."
        ></textarea>

        <label>Intereses:</label>
        <label
          ><input type="checkbox" name="intereses" value="deportes" />
          Deportes</label
        >
        <label
          ><input type="checkbox" name="intereses" value="tecnologia" />
          Tecnología</label
        >
        <label
          ><input type="checkbox" name="intereses" value="musica" />
          Música</label
        >
        <label
          ><input type="checkbox" name="intereses" value="viajes" />
          Viajes</label
        >

        <label for="color_favorito">Color Favorito:</label>
        <input
          type="color"
          id="color_favorito"
          name="color_favorito"
          value="#3498db"
        />

        <label for="sitio_web">Sitio Web (opcional):</label>
        <input
          type="url"
          id="sitio_web"
          name="sitio_web"
          placeholder="https://ejemplo.com"
        />
      </fieldset>

      <!-- Términos -->
      <fieldset>
        <legend>Términos y Condiciones</legend>

        <label>
          <input type="checkbox" name="terminos" value="aceptado" required />
          Acepto los
          <a href="/terminos" target="_blank">términos y condiciones</a> *
        </label>

        <label>
          <input type="checkbox" name="newsletter" value="si" />
          Deseo recibir noticias y promociones
        </label>
      </fieldset>

      <!-- Botones -->
      <div>
        <button type="submit">Registrarse</button>
        <button type="reset">Limpiar Formulario</button>
      </div>

      <p><small>* Campos obligatorios</small></p>
    </form>
  </body>
</html>
```

---

## 🔍 Pseudo-clases CSS para Validación

HTML5 proporciona pseudo-clases CSS para estilizar campos según su estado de validación:

### Estados de Validación

```css
/* Campo válido */
input:valid {
  border: 2px solid green;
}

/* Campo inválido */
input:invalid {
  border: 2px solid red;
}

/* Campo requerido */
input:required {
  border-left: 3px solid orange;
}

/* Campo opcional */
input:optional {
  border-left: 3px solid lightblue;
}

/* Dentro del rango permitido */
input:in-range {
  border-color: green;
}

/* Fuera del rango permitido */
input:out-of-range {
  border-color: red;
}

/* Campo habilitado */
input:enabled {
  background-color: white;
}

/* Campo deshabilitado */
input:disabled {
  background-color: #f0f0f0;
  cursor: not-allowed;
}

/* Solo lectura */
input:read-only {
  background-color: #f9f9f9;
}

/* No mostrar invalid hasta que se toque el campo */
input:not(:placeholder-shown):invalid {
  border-color: red;
}
```

### Ejemplo de Estilizado Completo

```css
/* Estilos base para inputs */
input,
select,
textarea {
  width: 100%;
  padding: 10px;
  margin: 5px 0;
  border: 2px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
  transition: all 0.3s ease;
}

/* Focus */
input:focus,
select:focus,
textarea:focus {
  outline: none;
  border-color: #3498db;
  box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
}

/* Campo válido después de interactuar */
input:not(:placeholder-shown):valid {
  border-color: #2ecc71;
  background-image: url("checkmark.svg");
  background-repeat: no-repeat;
  background-position: right 10px center;
}

/* Campo inválido después de interactuar */
input:not(:placeholder-shown):invalid {
  border-color: #e74c3c;
  background-image: url("error.svg");
  background-repeat: no-repeat;
  background-position: right 10px center;
}

/* Campo requerido */
input:required {
  border-left: 4px solid #e67e22;
}

/* Campo deshabilitado */
input:disabled {
  background-color: #ecf0f1;
  cursor: not-allowed;
  opacity: 0.6;
}
```

---

## 🎯 Mensajes de Error Personalizados con JavaScript

### Método `setCustomValidity()`

```html
<form id="miFormulario">
  <label for="password">Contraseña:</label>
  <input type="password" id="password" name="password" required />

  <label for="password_confirm">Confirmar Contraseña:</label>
  <input
    type="password"
    id="password_confirm"
    name="password_confirm"
    required
  />

  <button type="submit">Enviar</button>
</form>

<script>
  const password = document.getElementById("password");
  const passwordConfirm = document.getElementById("password_confirm");

  // Validar que las contraseñas coincidan
  passwordConfirm.addEventListener("input", function () {
    if (password.value !== passwordConfirm.value) {
      passwordConfirm.setCustomValidity("Las contraseñas no coinciden");
    } else {
      passwordConfirm.setCustomValidity(""); // Limpiar error
    }
  });

  // Validar longitud mínima personalizada
  password.addEventListener("input", function () {
    if (password.value.length > 0 && password.value.length < 8) {
      password.setCustomValidity(
        "La contraseña debe tener al menos 8 caracteres"
      );
    } else if (
      password.value.length >= 8 &&
      !/(?=.*\d)(?=.*[a-z])(?=.*[A-Z])/.test(password.value)
    ) {
      password.setCustomValidity("Debe incluir mayúscula, minúscula y número");
    } else {
      password.setCustomValidity("");
    }
  });
</script>
```

---

## 🛡️ Validación Avanzada con Constraint Validation API

### Propiedades y Métodos

```javascript
const input = document.getElementById("email");

// Propiedades
input.validity.valid; // true si es válido
input.validity.valueMissing; // true si required y está vacío
input.validity.typeMismatch; // true si el tipo no coincide
input.validity.patternMismatch; // true si no cumple pattern
input.validity.tooLong; // true si excede maxlength
input.validity.tooShort; // true si no llega a minlength
input.validity.rangeUnderflow; // true si es menor que min
input.validity.rangeOverflow; // true si es mayor que max
input.validity.stepMismatch; // true si no coincide con step
input.validity.customError; // true si setCustomValidity() activo

// Métodos
input.checkValidity(); // Retorna true/false
input.reportValidity(); // Muestra mensaje de error
input.setCustomValidity("mensaje"); // Establecer error personalizado
input.validationMessage; // Mensaje de error actual
```

### Ejemplo Completo de Validación

```javascript
const form = document.getElementById("miFormulario");

form.addEventListener("submit", function (e) {
  e.preventDefault();

  // Validar todos los campos
  const inputs = form.querySelectorAll("input, select, textarea");
  let formIsValid = true;

  inputs.forEach((input) => {
    if (!input.checkValidity()) {
      formIsValid = false;

      // Mostrar error específico
      const error = input.validity;
      let mensaje = "";

      if (error.valueMissing) {
        mensaje = "Este campo es obligatorio";
      } else if (error.typeMismatch) {
        mensaje = `Por favor, ingresa un ${input.type} válido`;
      } else if (error.patternMismatch) {
        mensaje = input.title || "El formato no es correcto";
      } else if (error.tooShort) {
        mensaje = `Mínimo ${input.minLength} caracteres`;
      } else if (error.tooLong) {
        mensaje = `Máximo ${input.maxLength} caracteres`;
      } else if (error.rangeUnderflow) {
        mensaje = `El valor mínimo es ${input.min}`;
      } else if (error.rangeOverflow) {
        mensaje = `El valor máximo es ${input.max}`;
      }

      // Mostrar mensaje personalizado
      input.setCustomValidity(mensaje);
      input.reportValidity();
    }
  });

  if (formIsValid) {
    // Enviar formulario
    console.log("Formulario válido, enviando...");
    form.submit();
  }
});
```

---

## 📱 Formularios Responsivos - Mobile First

### Atributos Útiles para Móviles

```html
<!-- Teclado numérico -->
<input type="tel" name="telefono" />
<input type="number" name="cantidad" />

<!-- Teclado de email (con @ y .com) -->
<input type="email" name="email" />

<!-- Teclado de URL (con .com, http://) -->
<input type="url" name="sitio" />

<!-- Autocompletado -->
<input type="text" name="nombre" autocomplete="name" />

<!-- Capitalización automática -->
<input type="text" name="nombre" autocapitalize="words" />

<!-- Corrección ortográfica -->
<textarea name="comentario" spellcheck="true"></textarea>

<!-- Modo de entrada (para dispositivos táctiles) -->
<input type="text" inputmode="numeric" />
<!-- Teclado numérico -->
<input type="text" inputmode="email" />
<!-- Teclado de email -->
<input type="text" inputmode="tel" />
<!-- Teclado telefónico -->
<input type="text" inputmode="url" />
<!-- Teclado de URL -->
<input type="text" inputmode="search" />
<!-- Teclado de búsqueda -->
```

---

## 🔒 Seguridad en Formularios

### 1. **Protección CSRF (Cross-Site Request Forgery)**

```html
<form action="/procesar" method="POST">
  <input type="hidden" name="csrf_token" value="TOKEN_GENERADO_EN_SERVIDOR" />
  <!-- Resto del formulario -->
</form>
```

### 2. **Sanitización de Datos**

```javascript
// Limpiar HTML peligroso
function sanitizeHTML(texto) {
  const div = document.createElement("div");
  div.textContent = texto;
  return div.innerHTML;
}
```

### 3. **Validación en Servidor**

**IMPORTANTE:** Siempre validar en el servidor, no confiar solo en validación del cliente.

### 4. **Autocomplete en Campos Sensibles**

```html
<!-- Desactivar autocomplete en contraseñas -->
<input type="password" name="password" autocomplete="new-password" />

<!-- Activar en datos no sensibles -->
<input type="text" name="nombre" autocomplete="name" />
```

---

## ✅ Mejores Prácticas

### 1. **Siempre usar etiquetas `<label>`**

```html
<!-- ✅ BIEN -->
<label for="email">Email:</label>
<input type="email" id="email" name="email" />

<!-- ❌ MAL -->
<input type="email" name="email" placeholder="Email" />
```

### 2. **Indicar campos obligatorios**

```html
<label for="nombre">Nombre: *</label>
<input type="text" id="nombre" name="nombre" required />

<p><small>* Campos obligatorios</small></p>
```

### 3. **Usar `autocomplete` apropiado**

```html
<input type="text" name="nombre" autocomplete="name" />
<input type="email" name="email" autocomplete="email" />
<input type="tel" name="telefono" autocomplete="tel" />
```

### 4. **Agrupar campos relacionados con `<fieldset>`**

### 5. **Proporcionar feedback visual**

- Usar `:valid` y `:invalid` en CSS
- Mostrar mensajes de error claros
- Indicar progreso en formularios largos

### 6. **Accesibilidad**

```html
<!-- Asociar label con input -->
<label for="campo">Etiqueta</label>
<input type="text" id="campo" name="campo" />

<!-- Usar aria-label cuando no hay label visible -->
<input type="search" aria-label="Buscar en el sitio" placeholder="Buscar..." />

<!-- Indicar errores con aria-invalid -->
<input
  type="email"
  name="email"
  aria-invalid="true"
  aria-describedby="email-error"
/>
<span id="email-error">Por favor, ingresa un email válido</span>
```

### 7. **Validación Progressive**

- No mostrar errores antes de interactuar
- Validar mientras el usuario escribe (con debounce)
- Dar feedback inmediato positivo

### 8. **Mobile First**

- Usar tipos de input apropiados
- Botones grandes y fáciles de presionar
- Formularios cortos y divididos en pasos

---

## 🎓 Resumen de Validación HTML5

| Atributo    | Descripción       | Ejemplo                           |
| ----------- | ----------------- | --------------------------------- |
| `required`  | Campo obligatorio | `<input required>`                |
| `minlength` | Longitud mínima   | `<input minlength="3">`           |
| `maxlength` | Longitud máxima   | `<input maxlength="20">`          |
| `min`       | Valor mínimo      | `<input type="number" min="0">`   |
| `max`       | Valor máximo      | `<input type="number" max="100">` |
| `pattern`   | Expresión regular | `<input pattern="[0-9]{3}">`      |
| `type`      | Tipo de dato      | `<input type="email">`            |
| `step`      | Incremento válido | `<input type="number" step="5">`  |

---

## 📚 Recursos Adicionales

- **MDN Web Docs:** [Formularios HTML](https://developer.mozilla.org/es/docs/Learn/Forms)
- **W3C:** [HTML5 Forms Specification](https://www.w3.org/TR/html5/forms.html)
- **Can I Use:** [Compatibilidad de validación HTML5](https://caniuse.com/form-validation)
- **HTML5 Pattern:** [Biblioteca de patrones](https://www.html5pattern.com/)

---

**Actualizado:** 15 de octubre de 2025  
**Archivo de referencia:** `modulo-02-fundamentos-frontend/html/03-Formularios-validacion.html`  
**Próximo tema:** Tablas HTML5
