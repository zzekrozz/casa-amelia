# Casa Amelí — Landing

Landing de una sola página para Casa Amelí. Es un sitio **estático** (solo HTML/CSS/JS), sin backend, listo para desplegar en Vercel.

---

## 📁 Estructura del proyecto

```
casa-ameli/
├── index.html          ← La web. Todo el HTML, CSS y JS está aquí.
├── images/             ← Tus fotos. Mete aquí los .jpg/.webp/.png.
├── vercel.json         ← Configuración de Vercel.
├── .gitignore          ← Archivos que no se suben a Git.
├── STRIPE.md           ← Guía paso a paso para enlazar los Payment Links.
└── README.md           ← Este archivo.
```

---

## 🚀 Subir a GitHub y desplegar en Vercel

### Paso 1 — Subir a GitHub

1. Crea una cuenta en https://github.com si no la tienes.
2. Crea un repositorio nuevo (botón verde **"New"**). Llámalo, por ejemplo, `casa-ameli`. Déjalo **público** o privado, ambos funcionan con Vercel.
3. Sube todos los archivos de esta carpeta al repositorio. Tienes dos opciones:

   **A) Más fácil (arrastrar archivos en la web):**
   - En tu repo recién creado, pulsa `Add file` → `Upload files`.
   - Arrastra todos los archivos y la carpeta `images/`.
   - Pulsa `Commit changes`.

   **B) Con terminal (si te manejas con Git):**
   ```bash
   git init
   git add .
   git commit -m "Casa Amelí landing inicial"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/casa-ameli.git
   git push -u origin main
   ```

### Paso 2 — Desplegar en Vercel

1. Entra en https://vercel.com y crea cuenta (puedes usar tu GitHub para entrar).
2. Pulsa **"Add New..."** → **"Project"**.
3. Selecciona tu repositorio `casa-ameli`.
4. Vercel detecta que es un sitio estático automáticamente. No tienes que tocar nada.
5. Pulsa **"Deploy"**.
6. En 1–2 minutos tendrás tu web en una URL tipo `casa-ameli.vercel.app`.

### Paso 3 — Dominio propio (opcional)

Si quieres usar `casaameli.com` o similar:
1. En tu proyecto de Vercel → pestaña **"Domains"** → añade tu dominio.
2. Vercel te da los DNS que tienes que poner en tu proveedor (Namecheap, GoDaddy, etc).

---

## 🔄 Cómo actualizar la web

Cada vez que **modifiques un archivo y lo subas a GitHub**, Vercel volverá a desplegarla automáticamente en menos de un minuto. Sin tocar nada.

- Cambiar un texto → editas `index.html`, lo subes a GitHub, Vercel actualiza solo.
- Cambiar una foto → la sustituyes en `images/`, lo subes a GitHub, listo.

---

## 🖼️ Añadir tus fotos

1. Mete tus fotos en la carpeta `images/`. Recomendado:
   - Formato **WebP** o **JPG** (más ligeros que PNG).
   - Tamaño **máximo 1500px de ancho**, calidad 80%.
   - Nombres en minúsculas, sin espacios, sin acentos. Ej: `hero.webp`, `bolsita-natural.jpg`.

2. Abre `index.html` y busca los placeholders. Reemplaza cada uno por la ruta `images/tu-foto.jpg`:

| Placeholder en el HTML | Sustituye por (ejemplo) |
|---|---|
| `IMAGEN_HERO_PRODUCTO` | `images/hero.webp` |
| `IMAGEN_PULSERA` | `images/pulsera.webp` |
| `IMAGEN_BOLSITA_NATURAL` | `images/bolsita-natural.webp` |
| `IMAGEN_BOLSITA_NEGRA` | `images/bolsita-negra.webp` |
| `IMAGEN_TARJETA` | `images/tarjeta.webp` |
| `IMAGEN_PACK_COMPLETO` | `images/pack-completo.webp` |
| `IMAGEN_SOBRE` | `images/sobre.webp` |

**Truco rápido:** abre `index.html` en cualquier editor (incluso Bloc de notas) y usa **Buscar y reemplazar** (Ctrl+H) para cambiar `IMAGEN_HERO_PRODUCTO` por `images/hero.webp` de una vez.

---

## 💳 Enlazar Stripe (Payment Links)

Cuando tengas creados tus Payment Links en Stripe, consulta el archivo **`STRIPE.md`** para ver paso a paso cómo conectarlos.

Resumen rápido: hay 4 placeholders en el HTML que tienes que reemplazar:
- `STRIPE_LINK_BASICO`
- `STRIPE_LINK_PERSONALIZADO`
- `STRIPE_LINK_PACK_2_BASICO`
- `STRIPE_LINK_PACK_DUO`

---

## ✏️ Otros datos editables

Busca y reemplaza también:
- `EMAIL_CONTACTO` → tu email (ej: `hola@casaameli.com`)
- `WHATSAPP_LINK` → tu link de WhatsApp (ej: `https://wa.me/34612345678`)
- `SOCIAL_LINK` → tu Instagram o TikTok (ej: `https://instagram.com/casaameli`)

---

## ❓ Soporte

Todo el código está comentado en `index.html`. Si quieres tocar algo y no encuentras dónde, busca el bloque comentado tipo:

```html
<!-- ============ NAV ============ -->
<!-- ============ HERO ============ -->
<!-- ============ PACKS ============ -->
```

Hecho con cariño para Casa Amelí 🤍
