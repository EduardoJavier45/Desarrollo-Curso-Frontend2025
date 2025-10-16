# 04 - Multimedia: Imágenes, Audio y Video (Guía completa)

**Fecha:** 15 de octubre de 2025
**Módulo:** 2 - Fundamentos de Desarrollo Front-End

---

## Introducción

En esta guía veremos cómo manejar contenido multimedia en la web: imágenes, audio y video. Veremos prácticas modernas para rendimiento, accesibilidad y compatibilidad, y ejemplos prácticos con HTML5, CSS y JavaScript. Los ejemplos están pensados para usarse en proyectos reales y para comprender las mejores prácticas actuales.

---

## 1. Imágenes

### 1.1. Elementos básicos

- `<img>`: el elemento estándar para imágenes.
- Atributos importantes: `src`, `alt`, `width`, `height`, `loading`, `decoding`, `sizes`, `srcset`.

Ejemplo básico:

```html
<img
  src="/imagenes/ejemplo.jpg"
  alt="Descripción de la imagen"
  width="600"
  height="400"
/>
```

**Nota:** Siempre incluir `alt` para accesibilidad. Es recomendable especificar `width` y `height` para evitar el reflow.

---

### 1.2. Imágenes responsivas: `srcset` y `sizes`

`srcset` permite ofrecer varias resoluciones de la misma imagen para dispositivos con diferentes densidades de píxeles (1x, 2x) o anchos.

```html
<img
  src="/imagenes/ejemplo-800.jpg"
  srcset="
    /imagenes/ejemplo-400.jpg   400w,
    /imagenes/ejemplo-800.jpg   800w,
    /imagenes/ejemplo-1200.jpg 1200w
  "
  sizes="(max-width: 600px) 100vw, 600px"
  alt="Paisaje hermoso"
/>
```

- `w` indica ancho en píxeles declarado para cada imagen.
- `sizes` describe cuánto espacio ocupará la imagen en diferentes condiciones de viewport.

---

### 1.3. Elemento `<picture>` para control más fino

Útil para cambiar no solo resolución, sino recorte o formato (AVIF/WebP) según soporte del navegador.

```html
<picture>
  <source srcset="/imagenes/ejemplo.avif" type="image/avif" />
  <source srcset="/imagenes/ejemplo.webp" type="image/webp" />
  <img
    src="/imagenes/ejemplo.jpg"
    alt="Ejemplo con picture"
    loading="lazy"
    width="800"
    height="600"
  />
</picture>
```

**Recomendación:** ofrecer WebP/AVIF y fallback JPEG/PNG.

---

### 1.4. Lazy loading

Evita cargar imágenes fuera de la pantalla hasta que sean necesarias.

```html
<img src="/imagenes/hero.jpg" alt="Hero" loading="lazy" />
```

**Nota:** `loading="lazy"` es soportado en la mayoría de navegadores modernos.

---

### 1.5. Optimización de imágenes

- Comprimir y generar múltiples tamaños.
- Usar formatos modernos: WebP, AVIF.
- Usar CDN o servicio de imágenes (ImageKit, Cloudinary).
- Evitar imágenes demasiado grandes; servir tamaños apropiados.

---

### 1.6. CSS y efectos

Ejemplo de placeholder y efecto de carga:

```html
<style>
  .img-placeholder {
    background: linear-gradient(90deg, #f0f0f0 25%, #e8e8e8 50%, #f0f0f0 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
  }
  @keyframes shimmer {
    100% {
      background-position: -200% 0;
    }
  }
  img.loaded {
    opacity: 1;
    transition: opacity 0.3s ease-in;
  }
  img {
    opacity: 0;
    display: block;
    width: 100%;
    height: auto;
  }
</style>

<div class="img-placeholder" style="width:400px; height:250px;">
  <img data-src="/imagenes/grande.jpg" alt="Ejemplo" class="lazy" />
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const lazyImages = document.querySelectorAll("img.lazy");
    if ("IntersectionObserver" in window) {
      const obs = new IntersectionObserver((entries, observer) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.addEventListener("load", () => img.classList.add("loaded"));
            observer.unobserve(img);
          }
        });
      });
      lazyImages.forEach((img) => obs.observe(img));
    } else {
      // Fallback: cargar todas
      lazyImages.forEach((img) => {
        img.src = img.dataset.src;
        img.classList.add("loaded");
      });
    }
  });
</script>
```

---

## 2. Audio

### 2.1. Elemento `<audio>` básico

```html
<audio controls>
  <source src="/audio/podcast.mp3" type="audio/mpeg" />
  <source src="/audio/podcast.ogg" type="audio/ogg" />
  Tu navegador no soporta audio HTML5.
</audio>
```

- `controls` muestra controles nativos.
- Ofrecer múltiples formatos para compatibilidad.

---

### 2.2. Atributos importantes

- `autoplay` - reproducir automáticamente (usar con precaución y preferir `muted` para videos)
- `loop` - repetir
- `muted` - silenciar
- `preload` - `none`, `metadata`, `auto`

```html
<audio controls preload="metadata">
  <source src="audio.mp3" type="audio/mpeg" />
</audio>
```

---

### 2.3. Usar la Web Audio API (ejemplo simple)

La Web Audio API permite analizar y procesar audio en tiempo real.

```html
<button id="play">Reproducir</button>
<script>
  async function setupAudio() {
    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    const response = await fetch("/audio/pista.mp3");
    const arrayBuffer = await response.arrayBuffer();
    const audioBuffer = await audioCtx.decodeAudioData(arrayBuffer);
    const source = audioCtx.createBufferSource();
    source.buffer = audioBuffer;
    source.connect(audioCtx.destination);
    source.start();
  }
  document.getElementById("play").addEventListener("click", setupAudio);
</script>
```

**Nota de seguridad:** los navegadores requieren interacción del usuario para iniciar audio sin `muted`.

---

### 2.4. Accesibilidad para audio

- Proveer transcripciones cuando el contenido es informativo.
- Controlar volumen y ofrecer subtítulos/lectura si es necesario.

---

## 3. Video

### 3.1. Elemento `<video>` básico

```html
<video controls width="640">
  <source src="/video/promo.mp4" type="video/mp4" />
  <source src="/video/promo.webm" type="video/webm" />
  Tu navegador no soporta video HTML5.
</video>
```

---

### 3.2. Subtítulos y accesibilidad: `<track>`

```html
<video controls>
  <source src="/video/promo.mp4" type="video/mp4" />
  <track
    kind="captions"
    srclang="es"
    label="Español"
    src="/video/subs-es.vtt"
    default
  />
</video>
```

- Crear archivos WebVTT (`.vtt`) para subtítulos.

Ejemplo simple de `.vtt`:

```
WEBVTT

00:00:00.000 --> 00:00:05.000
Bienvenidos al curso de Frontend.
```

---

### 3.3. Atributos clave

- `controls`, `autoplay`, `loop`, `muted`, `playsinline`, `preload`
- `poster` - imagen previa antes de reproducir

```html
<video controls poster="/imagenes/poster.jpg" muted playsinline>
  <source src="video.mp4" type="video/mp4" />
</video>
```

**Nota:** `playsinline` es importante en iOS para evitar que el video salga a pantalla completa.

---

### 3.4. Reproducción adaptativa y fuentes múltiples

Ofrecer varias fuentes/formats.

```html
<video controls>
  <source src="/video/clip-1080.mp4" type="video/mp4" />
  <source src="/video/clip-720.webm" type="video/webm" />
  <p>Tu navegador no soporta video HTML5.</p>
</video>
```

Para reproducción adaptativa real (bitrate adaptativo), usar HLS/DASH con players como hls.js o dash.js.

---

### 3.5. Controles con JavaScript (ejemplo)

```html
<video id="miVideo" width="640" controls>
  <source src="/video/ejemplo.mp4" type="video/mp4" />
</video>
<button id="playBtn">Reproducir</button>
<button id="pauseBtn">Pausar</button>

<script>
  const video = document.getElementById("miVideo");
  document
    .getElementById("playBtn")
    .addEventListener("click", () => video.play());
  document
    .getElementById("pauseBtn")
    .addEventListener("click", () => video.pause());
</script>
```

---

### 3.6. Capturar video con MediaDevices (webcam)

```html
<video id="webcam" autoplay playsinline width="320" height="240"></video>
<button id="start">Iniciar cámara</button>

<script>
  const videoEl = document.getElementById("webcam");
  document.getElementById("start").addEventListener("click", async () => {
    try {
      const stream = await navigator.mediaDevices.getUserMedia({
        video: true,
        audio: false,
      });
      videoEl.srcObject = stream;
    } catch (e) {
      console.error("Error accediendo a la cámara", e);
    }
  });
</script>
```

---

### 3.7. Grabar audio/video (MediaRecorder)

```html
<button id="startRec">Grabar</button>
<button id="stopRec">Detener</button>
<video id="playback" controls></video>

<script>
  let mediaRecorder,
    recordedChunks = [];
  document.getElementById("startRec").addEventListener("click", async () => {
    const stream = await navigator.mediaDevices.getUserMedia({
      audio: true,
      video: true,
    });
    mediaRecorder = new MediaRecorder(stream);
    mediaRecorder.ondataavailable = (e) => recordedChunks.push(e.data);
    mediaRecorder.onstop = () => {
      const blob = new Blob(recordedChunks, { type: "video/webm" });
      recordedChunks = [];
      document.getElementById("playback").src = URL.createObjectURL(blob);
    };
    mediaRecorder.start();
  });
  document
    .getElementById("stopRec")
    .addEventListener("click", () => mediaRecorder.stop());
</script>
```

---

## 4. Rendimiento y buenas prácticas

- Optimizar imágenes (múltiples tamaños, WebP/AVIF).
- Usar `loading="lazy"` para imágenes y `preload` con prudencia.
- Servir multimedia desde CDN.
- Habilitar Brotli/Gzip en servidor.
- Evitar autoplay sin `muted`.

---

## 5. Accesibilidad

- Siempre `alt` en imágenes.
- Subtítulos (`<track>`) para videos.
- Transcripciones para audio informativo.
- Controles accesibles (teclado) y roles ARIA si implementas controles personalizados.

---

## 6. Ejemplos completos

### 6.1. Ejemplo: Image responsive + lazy + placeholder

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Ejemplo Imágenes Responsivas</title>
    <style>
      .card {
        max-width: 600px;
        margin: 1rem auto;
      }
      img {
        width: 100%;
        height: auto;
        display: block;
      }
      .placeholder {
        background: #eee;
        height: 300px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: #aaa;
      }
    </style>
  </head>
  <body>
    <div class="card">
      <picture>
        <source srcset="/imagenes/landscape.avif" type="image/avif" />
        <source srcset="/imagenes/landscape.webp" type="image/webp" />
        <img
          src="/imagenes/landscape-800.jpg"
          alt="Paisaje"
          loading="lazy"
          width="800"
          height="500"
        />
      </picture>
    </div>
  </body>
</html>
```

### 6.2. Ejemplo: Player de audio simple con transcripción

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Audio</title>
  </head>
  <body>
    <h1>Podcast</h1>
    <audio controls preload="metadata">
      <source src="/audio/mi-podcast.mp3" type="audio/mpeg" />
      <source src="/audio/mi-podcast.ogg" type="audio/ogg" />
      Tu navegador no soporta audio.
    </audio>
    <h2>Transcripción</h2>
    <p>Bienvenidos al episodio 1... (transcripción completa aquí)</p>
  </body>
</html>
```

### 6.3. Ejemplo: Video con subtítulos y controles personalizados básicos

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Video con Subtítulos</title>
  </head>
  <body>
    <video id="videoDemo" width="640" controls poster="/imagenes/poster.jpg">
      <source src="/video/ejemplo.mp4" type="video/mp4" />
      <source src="/video/ejemplo.webm" type="video/webm" />
      <track
        kind="captions"
        srclang="es"
        src="/video/subs-es.vtt"
        label="Español"
        default
      />
    </video>
    <div>
      <button id="play">Reproducir</button>
      <button id="pause">Pausar</button>
      <button id="mute">Mute</button>
    </div>
    <script>
      const v = document.getElementById("videoDemo");
      document.getElementById("play").addEventListener("click", () => v.play());
      document
        .getElementById("pause")
        .addEventListener("click", () => v.pause());
      document
        .getElementById("mute")
        .addEventListener("click", () => (v.muted = !v.muted));
    </script>
  </body>
</html>
```

---

## 7. Recursos y enlaces útiles

- MDN: Media (Images, Audio, Video)
- W3C: HTML Media Elements
- WebAudio API - MDN
- HLS.js / Dash.js para streaming adaptativo

---

## 8. Conclusión

Esta guía cubre las piezas esenciales para trabajar con multimedia en la web hoy: formatos, rendimiento, accesibilidad y ejemplos prácticos. Si quieres, puedo generar también un archivo HTML de ejercicios con assets de ejemplo o integrar scripts para optimización automática (ej. scripts para generar `srcset`).

---

**Próximo paso en la TODO:** marcar la tarea 1 como completada y continuar con la 2 (agregar ejemplos avanzados y pruebas).
