# SB Seguridad — Landing Page

## Proyecto
Landing page profesional para **Seguridad Protección Blindados y Asesorías (SB)**, empresa hondureña de seguridad privada.  
Archivo principal: `index.html` (HTML + Tailwind CSS vía CDN + Lucide icons).  
Sin framework, sin build step.

---

## Datos del Proyecto

| Ítem | Valor |
|------|-------|
| Ruta | `C:\Users\Carlos Matute\Documents\seguridadsb\` |
| HTML | `index.html` |
| Assets | `assets/hero_video.mp4`, `assets/escudo.png` |
| Documentación | `PROYECTO.md`, `CONTEXTO.md` |

---

## Paleta de Colores

| Nombre | Hex | Uso |
|--------|-----|-----|
| `negro` | `#141414` | Fondo general |
| `naranja` | `#E47A13` | Acentos, botones, badges |
| `naranja-dark` | `#C76A10` | Hover de botones |
| `caqui` | `#BEA082` | Secundario (poco usado) |
| `gris` | `#929292` | Texto secundario, bordes |

---

## Estructura de Secciones (de arriba a abajo)

1. **Header / Navbar** — sticky, fondo oscuro semi-transparente, logo + nombre, nav links, botón "Cotizar Ahora"
2. **Hero Section** — video background, gradiente oscuro, badge, escudo + título apilado, línea animada, slogan, 2 botones CTA
3. **Servicios** — grilla 4 tarjetas: Oficiales, Escoltas, Blindados, Tecnología
4. **Sobre Nosotros** — imagen + texto con viñetas de diferenciadores
5. **Misión / Visión / Valores** — 3 columnas
6. **Estándares de Blindaje** — tabla Nivel III/III-A, IV, V/VI
7. **Contacto** — info (ubicación, teléfono, email) + formulario
8. **Footer** — logo, copyright, redes sociales
9. **Back to Top** — botón flotante naranja (esquina inferior derecha)

---

## Comportamiento Responsivo

### Mobile (< 640px)
- **Header**: hamburguesa (☰) toggle, menú desplegable con links + "Cotizar Ahora"
- **Hero**: `h-auto min-h-[780px]`, escudo arriba, título abajo (`flex-col`)
- **Servicios**: 1 columna
- **Nosotros**: imagen arriba, texto abajo
- **Misión/Visión/Valores**: 1 columna
- **Contacto**: formulario debajo de info
- **Botón "Cotizar Ahora"**: dentro del menú móvil (oculto en navbar)

### Tablet (≥ 768px)
- Header: nav visible
- Hero: `sm:h-[60vh]`, escudo + título lado a lado (`flex-row`)
- Servicios: grid 2 columnas
- Contacto: grid 2 columnas

### Desktop (≥ 1024px)
- Hero: `lg:h-[55vh]`
- Servicios: grid 4 columnas
- Misión/Visión/Valores: 3 columnas

### Landscape (teléfonos/tablets)
- `@media (orientation: landscape) and (max-height: 600px)`:
  - Hero: `100dvh`, contenido reducido (escudo 2rem, texto 0.875rem, gap 0.25rem)
  - Sin margen superior
- `@media (orientation: landscape) and (min-height: 601px) and (max-height: 768px)`:
  - Escudo 3.5rem, título 1.25rem

---

## Hero Section — Detalle

```
<section id="inicio" class="hero-section relative h-auto min-h-[780px] sm:min-h-0 sm:h-[60vh] lg:h-[55vh] flex flex-col items-start sm:items-center justify-start sm:justify-center overflow-hidden">
```

- **Background**: `<video autoplay muted loop playsinline>` con `object-cover`
- **Gradiente**: `bg-gradient-to-r from-negro via-negro/70 via-30% to-transparent`
- **Badge**: "TU SEGURIDAD, NUESTRA PRIORIDAD" (negro + white sobre naranja)
- **Título**: 4 líneas "SEGURIDAD / PROTECCIÓN / BLINDADOS / Y ASESORÍAS", intercalando `text-gris` en líneas pares
- **Escudo**: `assets/escudo.png`, responsive `h-28 sm:h-28 md:h-40 lg:h-64`
- **Línea naranja**: `h-0.5 bg-naranja .line-draw` (animation drawLine: 0 → 33.3% width, 0.8s, delay 0.5s)
- **Slogan**: "PROTEGEMOS LO QUE MÁS TE IMPORTA" con "MÁS TE IMPORTA" en naranja

---

## Componentes Clave

### Header (sticky)
```html
<header class="sticky top-0 z-50 w-full bg-negro/90 backdrop-blur-sm border-b border-gris/20">
```
- `sticky top-0`: en flujo normal, se pega arriba al hacer scroll
- Mobile: hamburger toggle `#menuBtn` + panel `#mobileMenu` (clase `hidden` toggleada con JS)
- Desktop: nav visible con links + botón "Cotizar Ahora"

### Back to Top
```css
.back-to-top { position: fixed; bottom: 2rem; right: 2rem; opacity: 0; visibility: hidden; }
.back-to-top.visible { opacity: 1; visibility: visible; }
```
- Aparece al scrollear > 400px
- Chevron SVG hacia arriba

### Smooth Scroll
- `html { scroll-behavior: smooth; }`
- `section[id] { scroll-margin-top: 5rem; }`
- JS: intercepta clicks en `a[href^="#"]`, previene default, usa `scrollIntoView({ behavior: 'smooth' })`

---

## Assets

| Archivo | Origen | Uso |
|---------|--------|-----|
| `assets/hero_video.mp4` | Copiado de `Proyecto_Landing_Seguridad\video_202607091259.mp4` | Fondo del hero |
| `assets/escudo.png` | Copiado de fuente del proyecto | Favicon, logo navbar, footer, hero |

---

## Tech Stack

| Tecnología | Versión/Detalle |
|------------|-----------------|
| HTML5 | Semántico |
| Tailwind CSS | CDN (`cdn.tailwindcss.com`), config inline con colores custom |
| Lucide Icons | CDN (`unpkg.com/lucide@latest`), `data-lucide` atributos |
| Google Fonts | Inter (400, 600, 700, 800) |
| JavaScript | Vanilla ES6, sin dependencias |

---

## JavaScript — Funciones

1. **lucide.createIcons()** — reemplaza `<i data-lucide="...">` por SVGs
2. **Mobile menu toggle** — click en `#menuBtn` togglea clase `hidden` en `#mobileMenu`, cierra al clickear link
3. **Back to top** — evento `scroll`, agrega/remueve clase `visible` según `scrollY > 400`
4. **Smooth scroll** — intercepta `a[href^="#"]`, previene default, scroll suave

---

## Historial de Cambios Recientes

- Header cambiado de `fixed` a `sticky top-0` (no más superposición con hero)
- Menú móvil con hamburguesa y panel toggle
- Botón flotante "Volver arriba"
- Hero en móvil: `h-auto min-h-[780px]` para que botones no se desborden
- Hero en desktop: `sm:h-[60vh] lg:h-[55vh]`
- Video y escudo copiados a `assets/`
