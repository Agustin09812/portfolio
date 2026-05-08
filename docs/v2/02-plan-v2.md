# Plan de Implementacion - Portfolio v2.0

Fecha: 2026-05-08  
Objetivo: construir v2.0 con nuevo look and feel, sin perder funcionalidades actuales ni responsividad mobile, reutilizando librerias de `assets/vendor`.

## 1) Principios de trabajo

1. No regresion funcional: cada feature de `main.js` debe mantenerse operativa.
2. Compatibilidad mobile first: diseño validado en 320/375/768 antes de cerrar cambios.
3. Reutilizacion de vendor existente: no reemplazar librerias salvo necesidad tecnica comprobada.
4. Migracion incremental: cambios por bloques, verificables y reversibles.

## 2) Arquitectura objetivo (sin framework)

Mantener stack estatico y ordenar capas:

1. `index.html`: estructura semantica limpia, secciones/componentes revisados.
2. `assets/css/main.css`: mantener como base estable de produccion.
3. `assets/css/v2.css`: capa de nuevo diseño (tokens, layout, componentes v2).
4. `assets/js/main.js`: mantener logica funcional.
5. `assets/js/v2.js` (opcional): solo mejoras no cubiertas por `main.js`.

Regla: si un componente depende de una clase/atributo para JS, no se elimina; se estiliza o se mapea.

## 3) Fases de ejecucion

## Fase 1 - Baseline y contratos (hecha)

1. Inventario funcional.
2. Mapa de riesgos.
3. Checklist no-regresion.

Salida:

1. `docs/v2/01-auditoria-v1.md`.

## Fase 2 - Blueprint v2 (en curso)

1. Definir sistema visual v2:
   - paleta, tipografia, espaciado, radios, sombras, motion.
2. Definir estrategia de CSS:
   - variables de design tokens + componentes por seccion.
3. Definir backlog tecnico de correcciones (contacto, links internos, placeholders).

Salida:

1. `docs/v2/02-plan-v2.md`.
2. Documento de diseño/tokens v2.

## Fase 3 - Implementacion UI v2 por bloques

Orden recomendado:

1. Header + nav mobile + hero.
2. About + stats + skills.
3. Resume + services.
4. Portfolio (masonry/filtros/lightbox).
5. Testimonials (swiper).
6. Contact + footer.

Criterio de salida por bloque:

1. Visual v2 aplicado.
2. Funcionalidades JS intactas.
3. Responsive validado en 320/375/768/1024/1440.

## Fase 4 - Hardening tecnico

1. Corregir ruta/form backend (`forms/contact.php` o alternativa).
2. Arreglar nav en paginas internas para apuntar a `index.html#seccion`.
3. Reducir carga innecesaria por pagina (solo librerias usadas).
4. Limpieza de placeholders y links vacios.

## Fase 5 - QA y cierre

1. Pasada completa de checklist de no-regresion.
2. Validacion visual cross-device.
3. Entrega de changelog v2.

## 4) Backlog priorizado

## Prioridad P0

1. Contact form funcional real (actualmente roto por backend ausente).
2. Navegacion consistente entre paginas (links internos corregidos).

## Prioridad P1

1. Rediseño visual v2 completo.
2. QA responsive exhaustivo.
3. Normalizar contenido de marca y datos reales.

## Prioridad P2

1. Optimizacion de carga por pagina.
2. Micro-accesibilidad (foco visible, `aria-label` en icon links, contrastes).

## 5) Definition of Done (v2.0)

1. Todas las features v1 siguen funcionando.
2. Mobile sin regresiones de layout/interaccion.
3. Contacto operativo.
4. Navegacion interna y externa sin links muertos.
5. Estilo v2 consistente en todas las paginas.
6. Carga de assets racionalizada sin romper funcionalidades.

## 6) Siguiente paso inmediato

Implementar el bloque `Header + Hero v2` sobre `index.html` + `assets/css/v2.css`, preservando:

1. `#header`, `.header-toggle`, `#navmenu`.
2. `.typed` + `data-typed-items`.
3. `#preloader` y `.scroll-top`.

