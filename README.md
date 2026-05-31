# EL AGAVE — Página Puente

Página temporal mientras llega la versión profesional. Un solo archivo HTML, sin build, lista para deploy.

## Contenido

```
el-agave-pagina-puente/
  index.html              ← el sitio
  assets/
    logo-agave.png        ← logo oficial
    menu-pagina-1.jpg     ← portada
    menu-pagina-2.jpg     ← desayunos
    menu-pagina-3.jpg     ← para comer
    menu-pagina-4.jpg     ← bebidas
    menu-pagina-5.jpg     ← mega bebidas
    menu-pagina-6.jpg     ← destilados
```

## Secciones del sitio

1. **Hero** con logo, "PRENDE LA NOCHE" y 2 CTAs (Reservar / Ver menú)
2. **Especialidades** — Birria Estilo Jalisco + Cantarito Cazuela 5L/10L con precios
3. **Menú visual** — galería tappable de las 6 páginas, con lightbox al tocar
4. **Sucursales** — Arboledas y Tlalnepantla Centro, cada una con Google Maps embebido, WhatsApp directo y "Cómo llegar"
5. **Horarios** — bloque con 3 columnas (Lun-Jue / Vie-Sáb / Dom)
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

## Cosas que conviene editar antes de publicar

### 1. Horarios (línea ~280-296 del HTML)
Puse horarios estimados de cantina. Confirmar con el socio y ajustar:
```
LUNES — JUEVES: 10:00 AM — 11:00 PM
VIERNES — SÁBADO: 10:00 AM — 2:00 AM
DOMINGO: 10:00 AM — 10:00 PM
```

### 2. Número de WhatsApp
Está hardcodeado como `525510699414` (10 dígitos + código país 52). Si cambia, busca y reemplaza todas las ocurrencias.

### 3. Instagram
Apunta a `@el_agave_arandas`. Si el socio quiere que apunte a `@cantaritoselagave` o `@Agavearboledas` también, agrégalos al footer.

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
