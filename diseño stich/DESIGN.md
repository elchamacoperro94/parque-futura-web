---
name: Innovation Ecosystem
colors:
  surface: '#101419'
  surface-dim: '#101419'
  surface-bright: '#36393f'
  surface-container-lowest: '#0a0f13'
  surface-container-low: '#181c21'
  surface-container: '#1c2025'
  surface-container-high: '#262a2f'
  surface-container-highest: '#31353a'
  on-surface: '#e0e2e9'
  on-surface-variant: '#bccac1'
  inverse-surface: '#e0e2e9'
  inverse-on-surface: '#2d3136'
  outline: '#86948c'
  outline-variant: '#3d4a43'
  surface-tint: '#59ddaf'
  primary: '#59ddaf'
  on-primary: '#003828'
  primary-container: '#00a87e'
  on-primary-container: '#003425'
  inverse-primary: '#006c50'
  secondary: '#b7c4ff'
  on-secondary: '#002682'
  secondary-container: '#0052fe'
  on-secondary-container: '#dfe3ff'
  tertiary: '#00d9ff'
  on-tertiary: '#003641'
  tertiary-container: '#00a2bf'
  on-tertiary-container: '#00323c'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#78f9ca'
  primary-fixed-dim: '#59ddaf'
  on-primary-fixed: '#002116'
  on-primary-fixed-variant: '#00513b'
  secondary-fixed: '#dde1ff'
  secondary-fixed-dim: '#b7c4ff'
  on-secondary-fixed: '#001452'
  on-secondary-fixed-variant: '#0038b6'
  tertiary-fixed: '#aeecff'
  tertiary-fixed-dim: '#00d9ff'
  on-tertiary-fixed: '#001f26'
  on-tertiary-fixed-variant: '#004e5d'
  background: '#101419'
  on-background: '#e0e2e9'
  surface-variant: '#31353a'
  futura-green: '#00A87E'
  quantum-blue: '#0052FF'
  innovation-cyan: '#00D9FF'
  deep-graphite: '#1A1E23'
  verde-bruma: '#E9F6F1'
  white-space: '#FFFFFF'
typography:
  display-lg:
    fontFamily: Montserrat
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-lg:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
  headline-md:
    fontFamily: Montserrat
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  body-lg:
    fontFamily: Montserrat
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Montserrat
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-md:
    fontFamily: Montserrat
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.05em
  caption:
    fontFamily: Montserrat
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 8px
  container-max: 1280px
  gutter: 24px
  margin-desktop: 64px
  margin-tablet: 32px
  margin-mobile: 16px
---

## Brand & Style

The brand personality is institutional yet forward-facing, balancing the rigor of a scientific park with the accessibility of a collaborative innovation hub. It evokes feelings of connectivity, growth, and technical precision.

The design style is a blend of **Corporate Modern** and **Dynamic Tech**. It utilizes structured layouts to maintain professional authority, while incorporating a "system of expanding circles" as a dynamic background pattern. These circles represent the Triple Helix model—the interaction between academia, government, and industry—creating organic, fluid textures on top of a dark, stable foundation. The interface should feel expansive, clean, and data-driven.

## Colors

The palette is rooted in **Deep Graphite**, providing a sophisticated, technical canvas that allows the chromatic brand colors to vibrate. 

- **Futura Green** is the primary driver for navigation, primary actions, and brand identification.
- **Quantum Blue** signifies technical depth and data-heavy sections.
- **Innovation Cyan** acts as a high-visibility accent for highlights and interactive feedback.
- **Verde Bruma** serves as a soft support background for light-mode components or internal card surfaces to provide subtle contrast against the main dark background.

Usage should prioritize high-contrast ratios, ensuring the vibrant greens and blues remain accessible against the graphite base.

## Typography

While the brand identity uses Futura PT Bold for its logotype and primary headings, **Montserrat** is the workhorse for the digital interface to ensure cross-platform legibility and a modern, geometric feel.

- **Headlines:** Use heavy weights (700) for "Futura" style impact. Large displays should use slight negative letter spacing to feel tight and engineered.
- **Body Text:** Standardized on Montserrat Regular for high readability in technical documentation and enterprise data.
- **Labels:** Small caps or uppercase labels with increased letter spacing should be used for metadata and category headers to provide a clear hierarchy in data-heavy tables.

## Layout & Spacing

The system uses a **Fixed Grid** model for desktop to maintain a controlled, professional presentation, transitioning to a fluid model for tablet and mobile.

- **Grid:** A 12-column grid is standard for desktop. For technical dashboards, use an 8px base unit for all padding and margins to ensure mathematical alignment.
- **Dynamic Patterning:** The "expanding circles" pattern should be applied to the background of hero sections or large landing containers. The pattern must never interfere with text legibility; it should be used as a "watermark" or decorative edge element.
- **Content Reflow:** Data tables reflow into "card stacks" on mobile, while pricing tiers transform from a horizontal comparison grid into a vertical scrollable list.

## Elevation & Depth

Hierarchy is established through **Tonal Layers** and subtle **Glassmorphism**. 

- **Surface Levels:** The base level is Deep Graphite. Primary containers (cards, sidebars) use a slightly lighter shade of the neutral palette or Verde Bruma with low opacity (10-15%) to create a "lifted" appearance without traditional heavy shadows.
- **Borders:** Use low-contrast outlines (1px solid #FFFFFF at 10% opacity) to define boundaries in data-heavy environments.
- **Backdrop Blur:** High-level modals and navigation overlays should use a backdrop filter blur (12px - 20px) to maintain the sense of depth and connection to the underlying "expanding circles" pattern.

## Shapes

The shape language is **Soft** and precise. 

- **Elements:** Standard components like buttons and input fields use a 0.25rem (4px) radius to maintain a technical, engineered appearance.
- **Containers:** Large cards and diagrams use a more pronounced 0.75rem (12px) radius to feel more approachable and modern.
- **Circles:** The dynamic background pattern utilizes perfect circles of varying scales, emphasizing the organic yet calculated nature of the innovation ecosystem.

## Components

- **Buttons:** Primary buttons are Futura Green with White Space text. Secondary buttons are outlined in Innovation Cyan. All buttons feature a 0.2s transition on hover, increasing brightness.
- **Cards:** Enterprise-grade cards feature a subtle 1px border. Backgrounds are Deep Graphite at 80% opacity with a backdrop blur to reveal the background pattern beneath.
- **Data Tables:** High-density layout. Headers should be uppercase labels in Innovation Cyan. Alternate rows use a 5% White Space tint for readability.
- **Technical Diagrams:** Triple Helix and Infrastructure models must use solid corporate colors. Lines connecting nodes should use the Innovation Cyan for a "glowing" tech aesthetic.
- **Chips/Tags:** Used for categorizing technical sectors (e.g., AI, Bio, Labs). Use Quantum Blue backgrounds with white text to differentiate from actionable buttons.
- **Inputs:** Dark-themed inputs with Futura Green focus states. Error states should use a high-contrast magenta or red that is distinct from the brand palette but clearly signals warning.