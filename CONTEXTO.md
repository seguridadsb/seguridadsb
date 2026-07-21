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
| Assets | `assets/hero_video.mp4`, `assets/escudo.png`, `assets/blindados.png`, `assets/flota1-4.jpeg` |

---

## Paleta de Colores

| Nombre | Hex | Uso |
|--------|-----|-----|
| `negro` | `#141414` | Fondo general |
| `naranja` | `#E47A13` | Acentos, botones, badges |
| `naranja-dark` | `#C76A10` | Hover de botones |
| `caqui` | `#BEA082` | Separadores slider |
| `gris` | `#929292` | Texto secundario, bordes, anillo progreso |

---

## Estructura de Secciones (de arriba a abajo)

1. **Header / Navbar** — sticky, fondo oscuro semi-transparente, logo + nombre, nav links, botón "Cotizar Ahora"
2. **Hero Section (`#inicio`)** — video background, gradiente oscuro, badge, escudo + título apilado, línea animada, slogan, 2 botones CTA
3. **Characteristics Slider** — barra horizontal animada con iconos + texto, separadores naranja, loop infinito 90s
4. **Servicios Especializados (`#servicios`)** — grilla 10 tarjetas
5. **Servicios Adicionales** — grilla 9 tarjetas
6. **Sobre Nosotros (`#nosotros`)** — imagen + texto con viñetas
7. **Misión / Visión / Valores** — 3 columnas
8. **Valores Agregados** — grilla 2 columnas
9. **Renta de Vehículos Blindados (`#blindados`)** — imagen full-width con máscara, contenido superpuesto
10. **Nuestra Flota (`#flota`)** — grid 4 imágenes en collage, lightbox al hacer clic
11. **Contacto (`#contacto`)** — info + formulario
12. **Footer** — logo, enlaces, redes
13. **Back to Top** — botón flotante con anillo de progreso blanco

---

## Navegación

Orden del menú (desktop y mobile):

**Inicio → Servicios → Nosotros → Blindados → Flota → Contacto**

Scroll spy activo: el enlace de la sección visible se resalta en naranja.

---

## Características

### Characteristics Slider
- Loop infinito, separadores `|` naranja, animación 90s

### Renta de Vehículos Blindados
- Imagen `assets/blindados.png` con máscara CSS
- Altura por contenido, sin overlay oscuro
- Cards con `bg-negro/70 backdrop-blur-sm`

### Flota
- 4 imágenes en grid (2 col móvil, 4 col desktop)
- Lightbox al hacer clic (navegación, teclado, fondo negro)
- Sin video (retirado por baja calidad)

### Back to Top
- Anillo SVG de progreso (`#ffffff`) alrededor del botón naranja
- Visibilidad según scroll > 400px

### Scroll Spy
- `IntersectionObserver` con `rootMargin: -30% 0px -60% 0px`
- Agrega `text-naranja` al link activo en nav desktop y mobile

---

## Comportamiento Responsivo

### Mobile (< 640px)
- Hamburguesa toggle, hero columna, grid 1 col

### Tablet (≥ 768px)
- Hero fila, grid 2 col

### Desktop (≥ 1024px)
- Grid 4-5 col, hero 55vh

---

## Tech Stack

| Tecnología | Detalle |
|------------|---------|
| HTML5 + Tailwind CSS (CDN) | Config inline |
| Lucide Icons | CDN, `data-lucide` |
| Google Fonts | Inter |
| JavaScript | Vanilla ES6 |

---

## JavaScript

1. `lucide.createIcons()` — iconos SVG
2. Mobile menu toggle
3. Back to top + anillo de progreso
4. Smooth scroll
5. Lightbox flota
6. Scroll spy con IntersectionObserver

---

## Assets

| Archivo | Origen | Uso |
|---------|--------|-----|
| `assets/hero_video.mp4` | `Proyecto_Landing_Seguridad\video...` | Hero background |
| `assets/escudo.png` | Fuente proyecto | Logo, favicon |
| `assets/blindados.png` | `Proyecto_Landing_Seguridad\blindados.png` | Sección Blindados |
| `assets/flota1.jpeg` | `Proyecto_Landing_Seguridad\flota1.jpeg` | Galería Flota |
| `assets/flota2.jpeg` | `Proyecto_Landing_Seguridad\flota1 (2).jpeg` | Galería Flota |
| `assets/flota3.jpeg` | `Proyecto_Landing_Seguridad\flota1 (3).jpeg` | Galería Flota |
| `assets/flota4.jpeg` | `Proyecto_Landing_Seguridad\flota1 (4).jpeg` | Galería Flota |
