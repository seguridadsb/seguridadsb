# Plan: Landing Page for Seguridad Protección Blindados y Asesorías

## Objective
Develop a professional and modern landing page that reflects the services and visual identity presented in the provided PDF document. The page will focus on generating trust and presenting the company as a leader in security and protection.

## 1. Research and Analysis (Completed)
- **Source**: `Seguridad Protección Blindados y Asesorías.pdf`
- **Key Services Identified**:
    - Security and Surveillance (Vigilancia y Seguridad).
    - Executive Protection / Bodyguards (Protección a Personas / Escoltas).
    - Armored Vehicles (Vehículos Blindados).
    - Security Consulting and Advisory (Asesorías y Consultoría).
- **Visual Identity**:
    - **Colors**: Negro (#141414), Naranja (#E47A13), Blanco (#FFFFFF), Caqui (#BEA082), Gris (#929292).
    - **Typography**: Clean sans-serif (based on 'Aptos' font found in the document).
    - **Imagery**: Professional, high-quality images of security personnel, armored vehicles, and control centers.

## 2. Proposed Structure
- **Hero Section**: Impactful background image (armored car or security team), company logo, clear value proposition, and a "Request a Quote" CTA.
- **Services Grid**: 4 main cards detailing the services extracted from the PDF.
- **Why Us**: A section highlighting experience, technology, and certifications.
- **Testimonials/Trust Elements**: Logos of partners or client testimonials.
- **Contact Section**: A clean lead generation form and direct contact details (phone, email, address).
- **Footer**: Legal info, social links, and navigation.

## 3. Technology Stack
- **HTML5 / CSS3**: For semantic structure and custom styling.
- **Tailwind CSS (via CDN)**: For rapid, responsive development and consistent spacing/typography.
- **JavaScript (Vanilla)**: For simple interactions (form validation, smooth scrolling).
- **Icons**: Lucide or FontAwesome (via CDN).

## 4. Implementation Steps
1.  **Skeleton**: Create the basic HTML structure with Tailwind CSS integration.
2.  **Styling**: Apply the color palette and typography derived from the PDF.
3.  **Content Population**: Fill sections with the specific text and details from the PDF.
4.  **Responsiveness**: Ensure the page looks great on mobile, tablet, and desktop.
5.  **Interactivity**: Add smooth scrolling and form handling.

## 5. Verification
- Validate responsiveness on different screen sizes.
- Ensure all text matches the PDF's messaging.
- Check that all links and CTAs are functional.


## Actualización - Integración de Información Detallada
- **Investigación**: Se intentó extraer texto adicional del PDF, pero gran parte del contenido textual parece estar codificado o en formato de imagen (OCR no disponible directamente).
- **Estrategia**: Se utilizarán los servicios y la estructura principal ya identificada, enriqueciendo las descripciones con lenguaje profesional acorde al sector de seguridad ejecutiva y blindaje.
- **Implementación**: Se actualizará el HTML con secciones de Misión, Visión, Valores y una tabla de niveles de blindaje basada en estándares industriales (extraídos de la línea gráfica del PDF).



## Actualización - Menú Sticky, Botón Volver Arriba y Menú Móvil

- **Header**: Cambiado de `fixed` a `sticky top-0` — está en el flujo del documento (no monta sobre la portada) pero se mantiene visible al hacer scroll.
- **Menú móvil**: Botón hamburguesa (☰) en mobile, despliega un panel con las opciones de navegación. Se cierra al seleccionar un enlace.
- **Botón "Volver arriba"**: Botón naranja flotante en la esquina inferior derecha, aparece al bajar >400px, sube suavemente al inicio.
- **Hero mobile**: Altura `h-auto min-h-[780px]` para que los botones no se desborden. En desktop mantiene `sm:h-[60vh] lg:h-[55vh]`.
- **Video**: Hero usa `assets/hero_video.mp4` (copiado desde `Proyecto_Landing_Seguridad`).
- **Escudo**: Copiado a `assets/escudo.png`, usado como favicon, logo en navbar, footer y hero. Responsive sizing via Tailwind.

## Actualización - Contenido Corporativo y Sección Valores Agregados

- **Misión y Visión**: Textos actualizados con redacción completa del cliente.
- **Sección Valores eliminada** (antes Misión/Visión/Valores → ahora solo Misión y Visión en 2 columnas).
- **Servicios Especializados**: Cambiado de 4 cards a 10 cards en grid 5 columnas con iconos.
- **Servicios Adicionales**: Nueva sección con 9 cards (Transporte Ejecutivo, Responsabilidad Social, Blindados, Radios, Supervisión Nocturna, Coordinación Autoridades, Auditorías, Reacción Nocturna, Monitoreo Remoto).
- **Sobre Nosotros**: Texto renovado con 3 párrafos con iconos (sparkles, refresh-cw, handshake) + Propósito (target) y Compromiso (award). Imagen cambiada a `assets/sn.png`.
- **Valores Agregados**: Nueva sección con 2 columnas:
  - **Izquierda**: App Supervisión Tiempo Real (gps.png), Reportes Automáticos (2.png), Monitoreo 24/7 (3.png).
  - **Derecha**: Capacitación Continua con sublista en 2 columnas (4.png), Poligrafías (5.png), Exámenes Toxicológicos (6.png).
  - Cada item: icono circular naranja | texto | imagen cuadrada 80×64px con `object-cover`.
- **Imágenes**: Copiadas de `Proyecto_Landing_Seguridad` a `assets/`: `sn.png`, `gps.png`, `2.png`, `3.png`, `4.png`, `5.png`, `6.png`.
- **Nombre empresa resaltado**: Todas las ocurrencias de "Seguridad Protección Blindados y Asesorías" envueltas en `<strong class="text-naranja">`.
- **Seguridad JS**: `lucide.createIcons()` envuelto en try-catch, null checks en DOM queries, script Lucide con `async`.
- **Landscape**: Hero mantiene `100dvh` con contenido reducido.
