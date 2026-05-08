# Sistema Visual v2.0 (Propuesta inicial)

Fecha: 2026-05-08

## 1) Direccion estetica

Concepto: `tech-editorial`  
Objetivo: look moderno, limpio, con contraste alto, acentos calidos y jerarquia tipografica marcada.

## 2) Design tokens (CSS variables)

```css
:root {
  --v2-bg: #0d0f12;
  --v2-surface: #151922;
  --v2-surface-2: #1b2230;
  --v2-text: #eef2f7;
  --v2-text-muted: #9ca7b6;
  --v2-accent: #f59e0b;
  --v2-accent-2: #22d3ee;
  --v2-border: #2a3342;
  --v2-shadow: 0 16px 50px rgba(0, 0, 0, 0.35);
  --v2-radius-sm: 10px;
  --v2-radius-md: 18px;
  --v2-radius-lg: 28px;
}
```

Notas:

1. Mantener contraste AA en texto principal/interactivo.
2. `--v2-accent` se usa para CTA/estados activos.
3. `--v2-accent-2` solo para highlights y microdetalle.

## 3) Tipografia

Propuesta:

1. Headings: `Space Grotesk` (700/600).
2. Body/UI: `Manrope` (500/400).
3. Fallback: `system-ui, -apple-system, Segoe UI, sans-serif`.

Escala recomendada:

1. Hero title: `clamp(2rem, 5vw, 4.25rem)`.
2. Section title: `clamp(1.6rem, 2.8vw, 2.4rem)`.
3. Body: `1rem` (16px) desktop / `0.95rem` mobile.

## 4) Layout y espaciado

1. Grid base Bootstrap vigente.
2. Max-width contenido: `1200px`.
3. Espaciado seccion: `clamp(56px, 8vw, 96px)`.
4. Separacion vertical interna: `24px/32px/48px`.

## 5) Motion

1. Duraciones cortas: `180ms - 280ms`.
2. Ease principal: `cubic-bezier(0.22, 1, 0.36, 1)`.
3. Mantener AOS para reveals; evitar animaciones decorativas excesivas.

## 6) Reglas responsive

Breakpoints de control:

1. `<=575px` mobile pequeno.
2. `576-767px` mobile grande.
3. `768-991px` tablet.
4. `992-1199px` desktop compacto.
5. `>=1200px` desktop.

Criterios:

1. Nunca overflow horizontal.
2. Touch targets minimos 44px en nav y CTA.
3. Tipografia y espaciado escalables con `clamp`.
4. Portfolio cards legibles sin hover (fallback touch).

## 7) Compatibilidad funcional obligatoria

No tocar sin mapear:

1. IDs de seccion usados por nav (`#hero`, `#about`, etc.).
2. Selectores JS (`.typed`, `.purecounter`, `.isotope-layout`, `.init-swiper`, `.php-email-form`).
3. Estructura `#header`, `#preloader`, `.scroll-top`.

