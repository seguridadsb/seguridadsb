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
| Assets | `assets/hero_video.mp4`, `assets/escudo.png`, `assets/blindados.png` |

---

## Paleta de Colores

| Nombre | Hex | Uso |
|--------|-----|-----|
| `negro` | `#141414` | Fondo general |
| `naranja` | `#E47A13` | Acentos, botones, badges |
| `naranja-dark` | `#C76A10` | Hover de botones |
| `caqui` | `#BEA082` | Separadores slider |
| `gris` | `#929292` | Texto secundario, bordes |

---

## Estructura de Secciones (de arriba a abajo)

1. **Header / Navbar** — sticky, fondo oscuro semi-transparente, logo + nombre, nav links, botón "Cotizar Ahora"
2. **Hero Section (`#inicio`)** — video background, gradiente oscuro, badge, escudo + título apilado, línea animada, slogan, 2 botones CTA
3. **Characteristics Slider** — barra horizontal animada con iconos + texto, separadores naranja, loop infinito 90s
4. **Servicios Especializados (`#servicios`)** — grilla 10 tarjetas: Confianza, Tecnología, Personal, Resultados, Profesionalismo, Capacitación, Tecnología, Mejora, Seguridad, Servicio
5. **Servicios Adicionales** — grilla 9 tarjetas (Protección, Confidencialidad, Disponibilidad, Conductores, etc.)
6. **Sobre Nosotros (`#nosotros`)** — imagen + texto con viñetas de diferenciadores
7. **Misión / Visión / Valores** — 3 columnas
8. **Valores Agregados** — grilla 2 columnas (Responsabilidad, Experiencia, Confidencialidad, etc.)
9. **Estándares de Blindaje (`#blindaje`)** — tabla Nivel III/III-A, IV, V/VI
10. **Renta de Vehículos Blindados (`#blindados`)** — imagen full-width con máscara, contenido superpuesto (cards 2×2, ventajas, CTAs)
11. **Contacto (`#contacto`)** — info (ubicación, teléfono, email) + formulario
12. **Footer** — logo, copyright, redes sociales
13. **Back to Top** — botón flotante naranja (esquina inferior derecha)

---

## Navegación

Orden del menú (desktop y mobile):

**Inicio → Servicios → Nosotros → Blindaje → Blindados → Contacto**

---

## Characteristics Slider

- Barra horizontal de loop infinito (duplicado para seamless scroll)
- Cada item: icono + texto, centrado horizontalmente, `w-[130px] md:w-[160px]`
- Separadores `|` en color naranja
- Animación `slideLoop 90s linear infinite` con `translateX(-50%)`
- Full-width, sin padding lateral

---

## Renta de Vehículos Blindados (`#blindados`)

- Imagen de fondo `assets/blindados.png` (1505×1045)
- Máscara CSS: degradado izquierdo/derecho y superior/inferior (transparente en bordes)
- Altura determinada por contenido (sin fixed height, sin scroll)
- Sin overlay oscuro — imagen a brillo completo
- Cards con `bg-negro/70 backdrop-blur-sm`
- CTAs: "Contáctanos" y "Solicita tu Cotización"

---

## Comportamiento Responsivo

### Mobile (< 640px)
- **Header**: hamburguesa (☰) toggle, menú desplegable con links + "Cotizar Ahora"
- **Hero**: `h-auto min-h-[780px]`, escudo arriba, título abajo (`flex-col`)
- **Servicios**: 1 columna
- **Nosotros**: imagen arriba, texto abajo
- **Misión/Visión/Valores**: 1 columna
- **Contacto**: formulario debajo de info

### Tablet (≥ 768px)
- Hero: `sm:h-[60vh]`, escudo + título lado a lado (`flex-row`)
- Servicios: grid 2 columnas
- Contacto: grid 2 columnas

### Desktop (≥ 1024px)
- Hero: `lg:h-[55vh]`
- Servicios: grid 5 columnas
- Misión/Visión/Valores: 3 columnas

### Landscape
- Hero se adapta con media queries para `max-height: 600px` y `601px-768px`

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

## Assets

| Archivo | Origen | Uso |
|---------|--------|-----|
| `assets/hero_video.mp4` | `Proyecto_Landing_Seguridad\video_202607091259.mp4` | Fondo del hero |
| `assets/escudo.png` | Fuente del proyecto | Favicon, logo navbar, footer, hero |
| `assets/blindados.png` | `Proyecto_Landing_Seguridad\blindados.png` | Fondo sección Blindados |
