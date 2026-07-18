---
name: web-design-guidelines
description: >
  Usar siempre que se necesiten guias de diseño web profesionales: sistemas de diseño,
  componentes atomicos, accesibilidad WCAG, design tokens, arquitectura CSS, rendimiento
  visual y principios de UX. Inspirado en los estandares de Vercel, Linear y Stripe.
  Activar cuando el usuario pida "siguiendo buenas practicas", "diseño consistente",
  "sistema de diseño", "componentes reutilizables", "accesibilidad" o "design tokens".
---

# Skill: Web Design Guidelines — Estandares y Sistemas de Diseño

## Proposito

Garantizar que toda interfaz web producida siga **principios de diseño sistematico**, sea accesible, mantenible y consistente. Esta skill complementa a `frontend-design` (estetica) con **arquitectura y reglas** de diseño.

---

## 1. Arquitectura de Design Tokens

Los design tokens son la unica fuente de verdad para todos los valores visuales. Nunca hardcodear colores, tamaños o sombras directamente en componentes.

### Jerarquia de Tokens

```
Tokens Primitivos (valores crudos)
  └── Tokens Semanticos (significado)
        └── Tokens de Componente (uso especifico)
```

### Tokens Primitivos
```css
:root {
  /* Escala de color cruda */
  --blue-50:  hsl(214, 100%, 97%);
  --blue-100: hsl(214, 95%, 93%);
  --blue-500: hsl(217, 91%, 60%);
  --blue-600: hsl(221, 83%, 53%);
  --blue-900: hsl(224, 71%, 4%);

  /* Escala de grises */
  --gray-50:  hsl(210, 40%, 98%);
  --gray-100: hsl(210, 40%, 96%);
  --gray-200: hsl(214, 32%, 91%);
  --gray-300: hsl(213, 27%, 84%);
  --gray-400: hsl(215, 20%, 65%);
  --gray-500: hsl(215, 16%, 47%);
  --gray-600: hsl(215, 19%, 35%);
  --gray-700: hsl(215, 25%, 27%);
  --gray-800: hsl(217, 33%, 17%);
  --gray-900: hsl(222, 47%, 11%);
  --gray-950: hsl(229, 84%, 5%);

  /* Escala de espaciado (base 4px) */
  --space-1:  4px;
  --space-2:  8px;
  --space-3:  12px;
  --space-4:  16px;
  --space-5:  20px;
  --space-6:  24px;
  --space-8:  32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;

  /* Escala tipografica (Major Third 1.25) */
  --text-xs:   0.64rem;   /* 10px */
  --text-sm:   0.8rem;    /* 13px */
  --text-base: 1rem;      /* 16px */
  --text-lg:   1.25rem;   /* 20px */
  --text-xl:   1.563rem;  /* 25px */
  --text-2xl:  1.953rem;  /* 31px */
  --text-3xl:  2.441rem;  /* 39px */
  --text-4xl:  3.052rem;  /* 49px */
  --text-5xl:  3.815rem;  /* 61px */

  /* Radios */
  --radius-none: 0;
  --radius-sm:   4px;
  --radius-md:   8px;
  --radius-lg:   12px;
  --radius-xl:   16px;
  --radius-2xl:  24px;
  --radius-full: 9999px;

  /* Duraciones de animacion */
  --duration-fast:   150ms;
  --duration-normal: 250ms;
  --duration-slow:   400ms;
  --duration-slower: 700ms;

  /* Easings */
  --ease-in:      cubic-bezier(0.4, 0, 1, 1);
  --ease-out:     cubic-bezier(0, 0, 0.2, 1);
  --ease-in-out:  cubic-bezier(0.4, 0, 0.2, 1);
  --ease-spring:  cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-bounce:  cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

### Tokens Semanticos (Dark Mode)
```css
[data-theme="dark"], .dark {
  --color-bg:         var(--gray-950);
  --color-bg-subtle:  var(--gray-900);
  --color-bg-muted:   var(--gray-800);
  --color-border:     var(--gray-800);
  --color-border-strong: var(--gray-700);
  --color-text:       var(--gray-50);
  --color-text-soft:  var(--gray-400);
  --color-text-muted: var(--gray-600);
  --color-accent:     var(--blue-500);
  --color-accent-soft: hsl(217, 91%, 60%, 0.15);
}

[data-theme="light"], .light {
  --color-bg:         var(--gray-50);
  --color-bg-subtle:  white;
  --color-bg-muted:   var(--gray-100);
  --color-border:     var(--gray-200);
  --color-border-strong: var(--gray-300);
  --color-text:       var(--gray-900);
  --color-text-soft:  var(--gray-600);
  --color-text-muted: var(--gray-400);
  --color-accent:     var(--blue-600);
  --color-accent-soft: hsl(221, 83%, 53%, 0.1);
}
```

---

## 2. Sistema de Componentes Atomicos

### Principio: Atomic Design
```
Atomos -> Moleculas -> Organismos -> Plantillas -> Paginas
```

- **Atomos**: Button, Input, Label, Badge, Icon, Divider
- **Moleculas**: Form Field (Label + Input + Error), Card, Nav Item
- **Organismos**: Navbar, Hero, Feature Section, Footer, Modal
- **Plantillas**: Layout de pagina, Layout de dashboard
- **Paginas**: Instancias concretas con datos reales

### Boton — Variantes Completas
```css
/* Base */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: var(--space-2) var(--space-4);
  border-radius: var(--radius-md);
  font-size: var(--text-sm);
  font-weight: 500;
  line-height: 1;
  cursor: pointer;
  border: 1px solid transparent;
  transition: all var(--duration-fast) var(--ease-out);
  white-space: nowrap;
  user-select: none;
}

.btn:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 2px;
}

.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

/* Variantes */
.btn--primary   { background: var(--color-accent); color: white; }
.btn--secondary { background: var(--color-bg-muted); color: var(--color-text); border-color: var(--color-border); }
.btn--ghost     { background: transparent; color: var(--color-text-soft); }
.btn--danger    { background: hsl(5, 75%, 60%); color: white; }
.btn--outline   { background: transparent; border-color: var(--color-accent); color: var(--color-accent); }

/* Tamaños */
.btn--sm { padding: var(--space-1) var(--space-3); font-size: var(--text-xs); }
.btn--lg { padding: var(--space-3) var(--space-6); font-size: var(--text-base); }
.btn--xl { padding: var(--space-4) var(--space-8); font-size: var(--text-lg); }

/* Hover states */
.btn--primary:hover   { filter: brightness(1.1); box-shadow: 0 4px 12px var(--color-accent-soft); }
.btn--secondary:hover { background: var(--color-bg-muted); border-color: var(--color-border-strong); }
.btn--ghost:hover     { background: var(--color-bg-muted); color: var(--color-text); }
```

### Input — Estados Completas
```css
.input {
  width: 100%;
  padding: var(--space-2) var(--space-3);
  border-radius: var(--radius-md);
  border: 1px solid var(--color-border);
  background: var(--color-bg-subtle);
  color: var(--color-text);
  font-size: var(--text-sm);
  transition: border-color var(--duration-fast) var(--ease-out),
              box-shadow var(--duration-fast) var(--ease-out);
}

.input::placeholder { color: var(--color-text-muted); }

.input:hover  { border-color: var(--color-border-strong); }

.input:focus  {
  outline: none;
  border-color: var(--color-accent);
  box-shadow: 0 0 0 3px var(--color-accent-soft);
}

.input--error {
  border-color: hsl(5, 75%, 60%);
  box-shadow: 0 0 0 3px hsl(5, 75%, 60%, 0.15);
}
```

---

## 3. Accesibilidad WCAG 2.1 AA (OBLIGATORIO)

### Contraste Minimo
| Uso | Ratio minimo |
|-----|-------------|
| Texto normal | 4.5:1 |
| Texto grande (+18px bold) | 3:1 |
| Componentes UI (bordes, iconos) | 3:1 |
| Texto decorativo | Sin requisito |

### Reglas de Implementacion
```html
<!-- SIEMPRE usar aria-label en iconos sin texto -->
<button aria-label="Cerrar modal">
  <svg aria-hidden="true">...</svg>
</button>

<!-- SIEMPRE asociar labels con inputs -->
<label for="email">Correo electronico</label>
<input id="email" type="email" aria-required="true">

<!-- Errores accesibles -->
<input aria-describedby="email-error" aria-invalid="true">
<p id="email-error" role="alert">Correo invalido</p>

<!-- Skip link para teclado -->
<a href="#main-content" class="skip-link">Saltar al contenido</a>
```

```css
/* Focus visible para navegacion con teclado */
:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}

/* Skip link */
.skip-link {
  position: absolute;
  transform: translateY(-100%);
  transition: transform var(--duration-fast);
}
.skip-link:focus { transform: translateY(0); }

/* Reduccion de movimiento */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 4. Arquitectura CSS — Metodologia BEM + Capas

### Capas con @layer (orden de cascada)
```css
@layer reset, tokens, base, components, utilities, overrides;

@layer reset {
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  img, video { max-width: 100%; height: auto; }
  button { cursor: pointer; font: inherit; }
}

@layer base {
  body {
    font-family: var(--font-sans);
    background: var(--color-bg);
    color: var(--color-text);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }
}
```

### Nomenclatura BEM
```css
/* Bloque */
.card { }

/* Elemento */
.card__header { }
.card__body   { }
.card__footer { }

/* Modificador */
.card--featured   { }
.card--horizontal { }
.card--sm         { }
```

### Utilidades Esenciales
```css
@layer utilities {
  .sr-only { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0,0,0,0); white-space: nowrap; }
  .truncate { overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
  .flex-center { display: flex; align-items: center; justify-content: center; }
  .grid-center { display: grid; place-items: center; }
  .full-bleed  { width: 100vw; margin-left: calc(50% - 50vw); }
}
```

---

## 5. Rendimiento Visual

### CSS Critico (above the fold)
- Inline el CSS del viewport inicial en `<style>` dentro del `<head>`
- Cargar el resto de CSS de forma asincrona

### Imagenes Optimizadas
```html
<!-- Siempre especificar width/height para evitar CLS -->
<img src="hero.webp" alt="Descripcion" width="1200" height="600" loading="lazy" decoding="async">

<!-- Imagenes responsivas -->
<picture>
  <source srcset="hero.avif" type="image/avif">
  <source srcset="hero.webp" type="image/webp">
  <img src="hero.jpg" alt="Descripcion" width="1200" height="600">
</picture>
```

### Fuentes sin Layout Shift
```html
<!-- Preconectar y precargar fuentes criticas -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<!-- font-display: swap en @font-face para evitar FOIT -->
```

### Animaciones de Alto Rendimiento
```css
/* SOLO animar estas propiedades (no causan reflow) */
/* transform, opacity, filter */

/* EVITAR animar */
/* width, height, top, left, margin, padding, border-width */

/* Forzar GPU */
.animated-element {
  will-change: transform;
  transform: translateZ(0);
}
/* Limpiar will-change despues de la animacion */
.animated-element.done { will-change: auto; }
```

---

## 6. Principios UX / Leyes de Diseño

### Ley de Fitts — Tamaños de Toque
- Area minima interactiva: **44x44px** (movil), **32x32px** (desktop)
- Entre elementos interactivos: minimo **8px** de separacion

### Ley de Hick — Reducir Opciones
- Maximo **7 items** en un menu de navegacion
- Formularios: un campo por paso en flows complejos
- CTAs: **un solo CTA primario** por seccion

### Principio de Proximidad (Gestalt)
- Elementos relacionados deben estar juntos
- `gap` entre grupo y fuera del grupo debe ser diferente (ej. 8px interno, 32px externo)

### Jerarquia de Informacion (F-Pattern / Z-Pattern)
- F-Pattern: listas, feeds, contenido denso (texto a izquierda)
- Z-Pattern: landing pages, heroes (diagonal de lectura)

### Feedback y Estados de Sistema
Toda accion del usuario debe tener respuesta visual en < 100ms:
```
Accion inmediata:  < 100ms — cambio visual instantaneo (hover)
Respuesta rapida:  < 1s    — spinner/skeleton
Proceso largo:     > 1s    — progress bar + mensaje
Error:             siempre — mensaje claro + como resolverlo
```

---

## 7. Sistema de Grid Responsivo

```css
/* Grid de 12 columnas */
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-6);
}

/* Columnas responsivas */
.col-12 { grid-column: span 12; }
.col-6  { grid-column: span 6; }
.col-4  { grid-column: span 4; }
.col-3  { grid-column: span 3; }

@media (max-width: 768px) {
  .col-6, .col-4, .col-3 { grid-column: span 12; }
}

/* Contenedor fluido con maximos */
.container {
  display: grid;
  grid-template-columns:
    [full-start] minmax(var(--space-6), 1fr)
    [content-start] min(var(--space-24) * 10, 100%) [content-end]
    minmax(var(--space-6), 1fr) [full-end];
}
.container > * { grid-column: content; }
.full-bleed    { grid-column: full; }
```

---

## 8. Dark / Light Mode con JavaScript
```javascript
// Deteccion y persistencia del tema
const getTheme = () => localStorage.getItem('theme') 
  || (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');

const applyTheme = (theme) => {
  document.documentElement.dataset.theme = theme;
  localStorage.setItem('theme', theme);
};

// Toggle
const toggleTheme = () => applyTheme(getTheme() === 'dark' ? 'light' : 'dark');
```

---

## 9. SEO y Meta Tags (plantilla completa)
```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Titulo de Pagina | Nombre del Sitio</title>
  <meta name="description" content="Descripcion de 150-160 caracteres que aparece en Google.">
  <meta name="author" content="Nombre del autor">
  
  <!-- Open Graph (redes sociales) -->
  <meta property="og:type"        content="website">
  <meta property="og:url"         content="https://tusitio.com/pagina">
  <meta property="og:title"       content="Titulo para redes sociales">
  <meta property="og:description" content="Descripcion para redes sociales.">
  <meta property="og:image"       content="https://tusitio.com/og-image.jpg">

  <!-- Canonical -->
  <link rel="canonical" href="https://tusitio.com/pagina">
</head>
```

---

## 10. Checklist Completo Antes de Entregar

### Diseño
- [ ] Design tokens definidos (primitivos + semanticos)
- [ ] Sistema de colores con dark/light mode
- [ ] Tipografia con escala modular y Google Fonts
- [ ] Espaciado consistente (multiplos de 4px)
- [ ] Estados hover, focus, active, disabled en TODOS los interactivos

### Accesibilidad
- [ ] Contraste WCAG AA en todo el texto (4.5:1 minimo)
- [ ] Skip link al contenido principal
- [ ] Labels asociados a todos los inputs
- [ ] Aria-labels en iconos sin texto visible
- [ ] Navegable completamente con teclado (Tab + Enter + Escape)
- [ ] `prefers-reduced-motion` respetado

### Rendimiento
- [ ] Imagenes con width/height explicitos (evitar CLS)
- [ ] Fuentes con `font-display: swap`
- [ ] Animaciones solo en transform/opacity
- [ ] `will-change` usado con criterio

### SEO
- [ ] Title unico por pagina
- [ ] Meta description (150-160 chars)
- [ ] Un solo h1 por pagina
- [ ] Estructura de headings logica (h1 > h2 > h3)
- [ ] Open Graph tags completos
- [ ] Link canonico

### Codigo
- [ ] CSS con @layer organizado
- [ ] BEM u otra convencion de nombres aplicada
- [ ] No hay estilos inline (excepto variables dinamicas)
- [ ] Variables CSS usadas (no valores hardcodeados)
- [ ] Responsive en 320px, 768px, 1024px, 1440px
