# Multielectronic Salamanca — Sitio Web

Página web informativa para **Multielectronic Salamanca** (tecnología, seguridad, climatización, servicio técnico y tintas).

## 📁 Archivos

| Archivo | Descripción |
|---|---|
| `index.html` | Página principal (la que ven los usuarios) |
| `gracias.html` | Pantalla a la que llega el usuario tras enviar el formulario |
| `logo.jpg` | Logo de la marca |
| `img/` | Carpeta con 6 imágenes de muestra + 1 SVG decorativo |

Todo está en un único HTML autocontenido (CSS y JS embebidos). No requiere build ni dependencias.

---

## ✏️ ANTES DE PUBLICAR — Cambios obligatorios

Abre `index.html` y reemplaza estos 2 valores:

### 1. Email del formulario (FormSubmit.co)

Busca esta línea (en el `<form>`):
```html
<form class="form-card"
      action="https://formsubmit.co/TU-EMAIL@DOMINIO.CL"
      method="POST">
```

Cambia `TU-EMAIL@DOMINIO.CL` por tu correo real (ej: `contacto@multielectronic.cl`).

### 2. URL de la página de gracias

Busca:
```html
<input type="hidden" name="_next" value="https://TU-DOMINIO.CL/gracias.html" />
```

Reemplaza por tu dominio final (ej: `https://multielectronic.cl/gracias.html`).

> 📌 **Si todavía no tienes dominio**, deja `https://tusitio.netlify.app/gracias.html` mientras lo consigues.

### 3. (Opcional) Email visible en la sección de contacto

Busca `contacto@multielectronic.cl` y cámbialo por el real.

---

## 🚀 CÓMO PUBLICAR (3 opciones de menor a mayor costo)

### Opción A — **GRATIS** · Netlify Drop (1 minuto, sin cuenta)

1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `multielectronic-salamanca` completa
3. Listo. Te dan una URL tipo `https://random-name-123.netlify.app`
4. (Opcional) Créate una cuenta gratis para renombrar el sitio y agregar dominio propio.

**Ventaja:** HTTPS automático, formulario Netlify integrado, rápido.

### Opción B — **GRATIS** · GitHub Pages

1. Crea un repo en GitHub, por ejemplo `multielectronic-web`
2. Sube estos 3 archivos
3. Settings → Pages → Source: `main` branch, `/ (root)`
4. Tu sitio queda en `https://tu-usuario.github.io/multielectronic-web`

**Ventaja:** versioning gratis, fácil de actualizar.

### Opción C — **GRATIS** · Cloudflare Pages

1. Sube el código a un repo de GitHub o GitLab
2. Ve a https://pages.cloudflare.com/ → "Create a project"
3. Conecta el repo y despliega
4. Cloudflare te da una URL `*.pages.dev` y puedes conectar dominio propio con 1 click.

**Ventaja:** la CDN más rápida, dominio custom fácil.

---

## 🌐 DOMINIO — ¿Cuánto cuesta?

| Opción | Precio aprox. | Tiempo |
|---|---|---|
| `.cl` (Chile) en **NIC Chile** | ~$10.000 CLP/año (≈$11 USD) | 1-3 días |
| `.com` en **Cloudflare Registrar** | **$9.15 USD/año** al costo | 5 min |
| `.com` en **Porkbun** | $9.73 USD/año | 5 min |
| Subdominio gratis (`tusitio.netlify.app`) | $0 | 0 min |

**Mi recomendación:** empieza con la URL gratis de Netlify/Cloudflare Pages. Cuando el negocio crezca y quieras algo más serio, compra un `.cl` en NIC Chile o un `.com` en Cloudflare.

---

## ⚙️ CÓMO FUNCIONA EL FORMULARIO (FormSubmit.co)

El formulario está integrado con **FormSubmit.co** — no necesitas backend ni registrarte:

1. El usuario llena el formulario en `index.html`
2. FormSubmit recibe los datos y los envía al correo que configuraste
3. El usuario es redirigido a `gracias.html`
4. **Primer envío:** te llega un email de confirmación a tu correo → haces clic en el link → queda activo para siempre.
5. Después funciona solo, sin hacer nada más.

**Límite gratis:** 50 mensajes/mes. Si excedes, FormSubmit cobra $8 USD/mes (plan Pro). Para más, puedes cambiar a **Web3Forms** (250/mes gratis) o **Netlify Forms** (100/mes gratis con Netlify).

### Alternativa: solo WhatsApp

Si no quieres email, abre `index.html`, busca la sección `<form class="form-card"` y reemplaza todo el `<form>...</form>` por:

```html
<a href="https://wa.me/56931053539?text=Hola%2C%20necesito%20una%20cotizaci%C3%B3n"
   class="btn btn-wsp"
   style="width:100%; padding:1.2rem; font-size:1.1rem; text-align:center;">
  💬 Cotizar por WhatsApp
</a>
```

---

## 🛠️ PERSONALIZACIÓN RÁPIDA

| Quiero cambiar... | Dónde |
|---|---|
| Colores | Variables CSS en `:root` (línea ~14) |
| Servicios | Sección `<section class="section servicios">` |
| Galería de trabajos | Carpeta `img/` + sección `<section id="trabajos">` |
| WhatsApp / Instagram | Busca y reemplaza `56931053539` y `multielectronic_salamanca` |
| Textos del hero | `<h1>` y `<p>` de la sección `.hero` |
| Email de contacto | `contacto@multielectronic.cl` (aparece 2 veces) |

### 📸 Cómo reemplazar las imágenes de muestra por tus fotos reales

Las imágenes actuales son de **Unsplash/Pexels** (licencia libre comercial) y un SVG personalizado. Para reemplazarlas con fotos de tus instalaciones:

1. Guarda tus fotos en la carpeta `img/` con estos nombres (o cámbialos en el HTML):
   - `camaras.jpg` — Sistemas de CCTV
   - `aire.svg` o `aire.jpg` — Aire acondicionado
   - `computador.jpg` — Servicio técnico / reparación
   - `laptop.jpg` — Equipos tecnológicos
   - `impresora.jpg` — Tintas e impresión
   - `redes.jpg` — Redes / cableado
2. Mantén proporción 4:3 (ideal ~800×600 px) para que se vean bien.
3. Optimiza cada imagen con [tinypng.com](https://tinypng.com) antes de subir (mejor performance).

También puedes agregar/quitar tarjetas editando los bloques `.galeria-item` en el HTML. Cada uno es independiente.

---

## 📞 Soporte

Si te trabas en algún paso, escríbeme y te ayudo.
