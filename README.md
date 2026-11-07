# EL AGAVE — Sitio oficial

Dominio en producción: **https://el-agave-arandas.com**

Un solo archivo HTML, sin build, listo para deploy.

## Contenido

```
pagina-agave-tlalnepantla/
  index.html              ← el sitio completo
  sitemap.xml  robots.txt
  assets/
    logo-agave.webp       ← logo en página (62 KB)
    logo-agave.png        ← logo para favicon y og:image (617 KB)
    hero-video.mp4        ← loop del hero (213 KB, 1280px, sin audio)
    birria.webp  cantarito.webp
    menu-pagina-1.webp    ← desayunos
    menu-pagina-2.webp    ← para comer
    menu-pagina-3.webp    ← bebidas sin alcohol
    menu-pagina-4.webp    ← cervezas y coctelería
    menu-pagina-5.webp    ← licores
    cantarito-hero.png  carne-en-su-jugo.png  chilaquiles.png   ← sin usar hoy
```

Los assets servidos pesan ~1.2 MB en total. Si reemplazas alguna imagen,
conviértela a WebP y mantenla por debajo de ~250 KB antes de subirla.

## Secciones del sitio

1. **Hero** con logo, "PRENDE LA NOCHE" y 2 CTAs (Reservar / Ver menú)
2. **Especialidades** — Birria Estilo Jalisco + Cantarito Cazuela 5L/10L con precios
3. **Menú visual** — galería tappable de las 5 páginas, con lightbox al tocar
4. **Sucursales** — Arboledas y Tlalnepantla Centro, cada una con Google Maps embebido, WhatsApp directo y "Cómo llegar"
5. **Horarios** — bloque por sucursal (Arboledas / Tlalnepantla Centro) + indicador dinámico "abierto ahora"
6. **Reservación** — formulario que abre WhatsApp con el mensaje pre-armado al 55 1069 9414
7. **Footer** con contacto + redes
8. **Botón flotante de WhatsApp** siempre visible

## Deploy en 30 segundos

**Opción A — Vercel (recomendada):**
1. Entra a vercel.com → New Project → Browse all templates → Other
2. Arrastra toda la carpeta `el-agave-pagina-puente`
3. Deploy. Te da un link tipo `el-agave.vercel.app`

**Opción B — Netlify Drop:**
1. app.netlify.com/drop
2. Arrastra la carpeta
3. Link instantáneo

**Opción C — GitHub Pages:**
1. Sube la carpeta a un repo
2. Settings → Pages → Source: main / root
3. Listo

## Datos que hay que mantener al día

### Horarios (sección `#horarios` del HTML)
```
ARBOLEDAS            MARTES — DOMINGO   10:00 AM — 3:00 AM  (cerrado lunes)
TLALNEPANTLA CENTRO  LUNES — DOMINGO    10:00 AM — 3:00 AM
```
Si cambian, hay que tocar tres lugares: el bloque `#horarios`, el
`openingHours` del JSON-LD en el `<head>`, y la función `isOpen()` del script
(usa hora de `America/Mexico_City`, no la del dispositivo del visitante).

### Número de WhatsApp
Hardcodeado como `525510699414`. Si cambia, buscar y reemplazar todas las
ocurrencias (`wa.me/`, `tel:`, `telephone` del JSON-LD).

### Dominio
`https://el-agave-arandas.com` aparece en `og:url`, `og:image`,
`twitter:image`, `canonical`, el JSON-LD, `sitemap.xml` y `robots.txt`.
Si se migra el dominio hay que actualizarlos todos.

### Redes
Instagram `@el_agave_arandas` y Facebook `cantaritoselagave`.

## Pendientes conocidos

- **Sin analítica.** No hay GA4 ni pixel de Meta. Indispensable antes de meter pauta pagada.
- **Tailwind por CDN** (`cdn.tailwindcss.com`): compila CSS en el navegador y
  no está pensado para producción. Cambiar a CSS compilado cuando haya tiempo.
- Tres imágenes en `assets/` no se usan en el sitio.

## Decisiones de diseño que tomé

- **Brand 70/30 respetado:** fondos negro/madera, neón solo en acentos (logo, headlines, CTAs, badges).
- **Monoton solo en hero** ("PRENDE LA NOCHE") — el manual prohíbe usarla en cuerpo.
- **Bebas Neue** para headers, badges y botones (tracking widest, todo mayúsculas).
- **Inter** para body y formulario.
- **Logo en `object-fit: contain`** en todos sus usos — nunca se deforma.
- **Glow neón flicker** sutil en el headline para sensación de letrero real.
- **Animación pulse** en los CTAs principales para llamar la conversión.
- **Lightbox** del menú para que el cliente pueda leer precios sin descargar nada.

## Lo que NO incluí (a propósito)

- **No agregué fotos de comida** — el manual dice cocina chica no se muestra en plano abierto, y aún no tenemos banco de fotos profesionales. Mejor lanzar sin fotos malas que esperar.
- **No abrí blog ni galería de Reels** — esto es página puente, no hub editorial.
- **No metí pixel de Meta ni Google Analytics** — agregar antes de meter pauta paga.

## Cuando llegue la versión profesional

Esta carpeta se reemplaza completa por la nueva. Mientras tanto cubre las preguntas que llegan por DM:
- ¿Qué tienen? → menú visual
- ¿Dónde están? → 2 mapas embebidos
- ¿A qué hora abren? → bloque de horarios + dinámico "hoy abierto"
- ¿Cómo reservo? → formulario → WhatsApp
- ¿Cuánto cuesta un cantarito? → especialidades + menú

---

**Footer del sitio:** atribución "Diseñado por Orbit Films". Si quieres quitarla, está en la última `<p>` del `<footer>`.
