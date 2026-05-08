# Tenerife Richie Excursions

Sitio web turístico de excursiones en Tenerife. **Single-page** construido como un solo `index.html` autocontenido — sin build step, sin npm, sin frameworks. Solo HTML + CSS + JS vanilla.

---

## 📁 Estructura del repositorio

```
tenerife-richie/
├── .gitignore              # Archivos que Git ignora
├── README.md               # Este archivo
├── index.html              # ⭐ La web completa
├── images/                 # Imágenes de excursiones
│   ├── anaga.jpg
│   ├── banana.jpg
│   ├── buggy.jpg
│   ├── deepfishing.jpg
│   ├── flyfish.jpg
│   ├── freebird.jpg
│   ├── jetski.jpg
│   ├── kayak.jpg
│   ├── loropark.jpg
│   ├── masca.jpg
│   ├── maxicat-1.jpg
│   ├── maxicat-2.jpg
│   ├── maxicat-3.jpg
│   ├── paragliding.jpg
│   ├── parasailing.jpg
│   ├── private-charter.jpg
│   ├── self-drive-boat.jpg
│   ├── siampark.jpg
│   ├── stargazing.jpg
│   ├── teide.jpg
│   ├── trailer1-poster.jpg # Imagen de respaldo del vídeo Hero
│   └── whales.jpg
└── videos/
    └── trailer1.mp4        # Vídeo de fondo Hero (1080p, ~14 MB, sin audio)
```

⚠️ **Importante: nombres en minúsculas.** GitHub Pages y Cloudflare Pages distinguen mayúsculas/minúsculas. `Teide.jpg` y `teide.jpg` son archivos diferentes en estos servicios. Mantén siempre minúsculas.

---

## 🚀 Crear las carpetas en el repo

### Si usas la web de GitHub
1. Entra al repo → **Add file** → **Create new file**
2. En el nombre, escribe: `images/.gitkeep` y guarda (esto crea la carpeta)
3. Repite con: `videos/.gitkeep`
4. Después subes los archivos a cada carpeta con drag & drop

### Si usas la terminal (Mac/Linux/Git Bash)
```bash
mkdir -p images videos
touch images/.gitkeep videos/.gitkeep
git add .
git commit -m "Create asset folders"
git push
```

### Si usas Windows (PowerShell)
```powershell
New-Item -ItemType Directory -Path "images" -Force
New-Item -ItemType Directory -Path "videos" -Force
New-Item -ItemType File -Path "images\.gitkeep" -Force
New-Item -ItemType File -Path "videos\.gitkeep" -Force
git add .
git commit -m "Create asset folders"
git push
```

Después subes las imágenes y vídeos a sus carpetas correspondientes.

---

## 🎬 Sobre el vídeo de fondo (Hero)

El vídeo `videos/trailer1.mp4` ya viene **optimizado para web**:
- Resolución: **1920×1080** (Full HD)
- Duración: ~19 segundos (en bucle)
- Peso: **~14 MB**
- Sin pista de audio (ya silenciado)
- Codec: H.264 (compatible con todos los navegadores)
- `faststart` activado (carga rápida)

Si quieres añadir más vídeos en el futuro:
1. Comprímelos antes con [HandBrake](https://handbrake.fr) → preset *Web → Vimeo YouTube HQ 1080p60*
2. Quita la pista de audio (en HandBrake → pestaña **Audio** → eliminar)
3. Mantén el peso bajo 20 MB

---

## 🎬 Vídeos de YouTube en las tarjetas

Las tarjetas de excursión usan **embeds de YouTube** como fondo en bucle silenciado. Los IDs están dentro de cada `<div class="yt-bg">` en el HTML.

**Cómo cambiar un vídeo de una excursión:**
1. Busca en `index.html` la tarjeta (Cmd/Ctrl+F → ej. `Maxicat Catamaran`)
2. Verás dos sitios donde aparece el ID del vídeo de YouTube (en `embed/XXXXX` y `playlist=XXXXX`)
3. Reemplaza ambos con el nuevo ID
4. También cambia el atributo `data-video="XXXXX"` del `<article>`

---

## 📱 WhatsApp

El número está en el código múltiples veces. Para cambiarlo, busca y reemplaza:
- `447861305822` (sin `+`, sin espacios)

---

## 🚀 Deploy a GitHub Pages

1. Subir todos los archivos al repo
2. **Settings** → **Pages**
3. Source: **Deploy from a branch** → `main` → `/ (root)` → **Save**
4. En 1-2 minutos: `https://TU-USUARIO.github.io/tenerife-richie/`

---

## ☁️ Deploy a Cloudflare Pages

1. [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create → Pages**
2. **Connect to Git** → seleccionar el repo
3. Build settings:
   - Framework preset: **None**
   - Build command: *(vacío)*
   - Build output directory: `/`
4. **Save and Deploy**
5. Custom domain en la pestaña **Custom domains**

---

## ✏️ Editar contenido

Todo está dentro de `index.html`. Para cualquier cambio, abre el archivo con cualquier editor de texto y busca con Cmd/Ctrl+F.

### Cambiar precios
Cada excursión tiene dos sitios donde aparece el precio:
```html
<article ... data-price="79">
  ...
  <span class="ex-price">€79<small>/adult</small></span>
```
Cambia ambos para que coincidan.

### Cambiar imagen de una tarjeta
Busca `images/teide.jpg` (o el nombre de la imagen actual) y reemplaza con el nuevo nombre. Asegúrate de que el archivo nuevo esté en la carpeta `images/`.

### Añadir Google Reviews reales
En la sección de reviews, reemplaza el texto entre `<p>"..."</p>` con la review real, y cambia el nombre del autor en `<strong>...</strong>`.

---

## 🎮 Mini-juego Flappy Richie

Hay un mini-juego escondido entre las secciones (Flappy Bird con tu cara). Se inicia con la barra espaciadora o un tap, y desaparece cuando haces scroll para no molestar.

---

## ✅ Checklist antes de ir online

- [ ] Confirmar que el WhatsApp `+44 7861 305822` es el correcto
- [ ] Subir la carpeta `images/` con sus 22 imágenes
- [ ] Subir la carpeta `videos/` con `trailer1.mp4`
- [ ] Probar la web localmente abriendo `index.html` en Chrome
- [ ] Probar el modal de reserva (que abra WhatsApp con mensaje pre-rellenado)
- [ ] Reemplazar las reviews placeholder con reviews reales de Google
- [ ] Añadir links reales de Instagram / TikTok / Facebook en el footer
- [ ] (Opcional) Añadir favicon: subir `favicon.ico` a la raíz

---

Made with ☀️ in Tenerife.
