# Convenciones de Código, Estilo y UI - Cuotin

## 1. Etiquetas Semánticas HTML5
- Estructuración estricta mediante: `<header>`, `<main>`, `<section>`, `<article>`, `<nav>`, `<button>`, `<footer>`.
- Prohibido el uso indiscriminado de `<div>` para elementos cliqueables; todo elemento interactivo debe ser una etiqueta `<button>` nativa.
- Inclusión obligatoria del atributo `alt="..."` en todas las imágenes o contenedores gráficos para garantizar la accesibilidad.

## 2. Paleta de Colores CSS y Clases Tailwind
- **Modo Oscuro (Predeterminado - Fintech Dark)**:
  - Fondo Principal: `bg-slate-900` (`#0f172a`)
  - Tarjetas / Contenedores: `bg-slate-800` (`#1e293b`)
  - Bordes: `border-slate-700` / `border-slate-800`
  - Textos Principales: `text-white` / `text-slate-100`
  - Textos Secundarios: `text-slate-400`
- **Colores de Acento y Categorías**:
  - Positivo / Botones CTA: `bg-emerald-500` (`#10b981`), `hover:bg-emerald-600`
  - Indumentaria: `purple-500` / `bg-purple-500/10`
  - Tecnología: `blue-500` / `bg-blue-500/10`
  - Supermercado: `emerald-500` / `bg-emerald-500/10`
  - Viajes: `sky-500` / `bg-sky-500/10`
  - Hogar: `amber-500` / `bg-amber-500/10`

## 3. Regla de Contraste Estricto
- Definición de la clase helper `.force-text-white` con `color: #ffffff !important` para asegurar legibilidad absoluta sobre fondos oscuros o degradados verdes.

## 4. Tipografía y Jerarquía Visual
- **Fuente**: Google Fonts `'Inter'` (`font-sans`).
- **Títulos Hero / H1**: `text-3xl sm:text-5xl lg:text-6xl font-extrabold`.
- **Secciones / H2**: `text-2xl font-bold`.
- **Tarjetas / H4**: `text-base font-extrabold`.
- **Etiquetas de Estado / Badges**: `text-[10px]` o `text-xs font-bold`.

## 5. Diseño Responsive y Layouts
- **Móvil (< 768px)**: 
  - Layout en 1 sola columna vertical.
  - Menú hamburguesa colapsable en la barra superior.
  - Barra de Navegación Inferior (*Bottom Navigation Bar*) fija.
  - Botones con altura y padding generoso (`py-3.5`) para facilitar el toque táctil.
- **Desktop (≥ 768px)**:
  - Grilla de tarjetas en 2 columnas.
  - Ocultamiento de la barra inferior y despliegue del menú superior completo.
