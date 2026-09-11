# Arquitectura del Sistema - Cuotin

## 1. Visión General
**Cuotin** es una Single Page Application (SPA) para la gestión y proyección de gastos en cuotas con tarjetas de crédito en Argentina. La arquitectura está diseñada para ejecutarse íntegramente en el cliente (*Client-Side Rendering*) sin requerir servidores ni bases de datos remotas.

## 2. Stack Tecnológico Estándar
- **Estructura**: HTML5 Semántico en archivo único `index.html`.
- **Estilos y Maquetado**: TailwindCSS v3 (vía CDN oficial script).
- **Lógica e Interactividad**: JavaScript Vanilla nativo (ES6+ sin transpilación).
- **Persistencia**: API `localStorage` del navegador.
- **Tipografía y Gráficos**: Google Fonts (`Inter`), FontAwesome v6.5 (CDN) para iconografía.

## 3. Mapa de Módulos y Componentes
```
index.html (SPA Root)
 ├── 1. Header / Navbar Superior
 │    ├── Logo Cuotin + Slogan
 │    ├── Links de Navegación Desktop (Inicio, Resumen, Agregar)
 │    ├── Botón "Más Info" (Modal Créditos/Derechos)
 │    ├── Toggle Dark/Light Mode
 │    └── Menú Hamburguesa Móvil
 ├── 2. Hero Section (#view-hero)
 │    ├── Distintivo "Finanzas en Argentina"
 │    ├── Encabezado de Impacto + Subtítulo
 │    ├── Botones CTA ("Ver mi Resumen", "Agregar Gasto")
 │    └── Tarjeta de Demostración de Resumen
 ├── 3. Vista Resumen Mensual (#view-resumen)
 │    ├── Selector de Mes Dropdown (Enero - Diciembre)
 │    ├── Tarjetas de Métricas (Total a Pagar, Cuotas Activas, Diagnóstico)
 │    └── Contenedor de 4 Estados UI (Loading, Empty, Error, Success Grid sin imágenes)
 ├── 4. Vista Agregar Gasto (#view-agregar)
 │    ├── Formulario de Alta Exclusivo (Nombre, Precio/Monto, Cuotas, Mes de Inicio, Categoría)
 │    ├── Cuadro de Vista Previa de Cuota Mensual
 │    └── Botón de Acción con Animación Feedback
 ├── 5. Modales Emergentes Popups
 │    ├── Modal "Más Info" (#modal-info): Créditos, derechos y tips
 │    └── Modal "Ver detalles" (#modal-detalle): Desglose del gasto en cuotas
 ├── 6. Notificaciones Toast (#toast-container)
 │    └── Mensajes Flotantes Verdes de Confirmación
 └── 7. Bottom Navigation Bar (Barra Inferior Móvil)
```

## 4. Tecnologías y Prácticas Prohibidas
- ❌ **Sin Frameworks JS pesados**: Prohibido React, Next.js, Vue, Angular o Svelte.
- ❌ **Sin Servidores Backend**: Prohibido Node.js, Express, Python, Django, FastAPI o PHP.
- ❌ **Sin Bases de Datos Externas**: Prohibido SQL, MongoDB, Firebase o Supabase.
- ❌ **Sin Múltiples Archivos HTML**: Navegación 100% SPA dentro de `index.html` sin `window.location` ni recargas de página.
- ❌ **Sin Estilos Inline**: Prohibido utilizar `style="..."` pegado en etiquetas HTML.
