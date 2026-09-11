# Historial de Memoria Continua (Engram Protocol) - Cuotin

Este documento registra la memoria viva del agente **Antigravity** durante el ciclo de vida del proyecto **Cuotin**, asegurando trazabilidad, persistencia de acuerdos de diseño y registro de hitos según la metodología SDD Adaptativa.

---

## 1. Contexto Activo (`mem_context`)
- **Proyecto:** Cuotin (Simulador de Finanzas Personales & Control de Cuotas de Tarjeta de Crédito en Argentina).
- **Rol del Agente:** Senior Product Engineer.
- **Enfoque:** Arquitectura limpia SPA en cliente único (`index.html`), diseño visual premium Fintech Dark / Light con TailwindCSS, cero recargas de página y cumplimiento estricto de la Definition of Done (DoD).
- **Alcance de la Sesión de Cierre:**
  - Garantizar los 5 requisitos obligatorios del proyecto final.
  - Maquetar 6 elementos de catálogo con fotos reales de alta calidad (Unsplash) y atributos accesibles.
  - Implementar formulario dual con pestañas (Contacto / Inscripción a Alertas + Alta de Gasto en Cuotas).
  - Implementar y verificar los 4 estados de interfaz de usuario (Loading, Empty, Error, Success).
  - Generar el reporte formal de verificación `REPORTE_VERIFICACION_SDD.md`.

---

## 2. Acuerdos y Aprendizajes Persistidos (`mem_save`)

### [MEM-SAVE-001] Navegación SPA sin Recargas
- **Decisión:** Ocultamiento y despliegue condicional de vistas (`#view-hero`, `#view-resumen`, `#view-agregar`) mediante la clase `hidden` y transición suave `.transition-spa`.
- **Regla:** Prohibido el uso de `window.location` o enlaces con `href` externos que recarguen el documento. Todo formulario intercepta el evento con `e.preventDefault()`.

### [MEM-SAVE-002] Regla de Contraste `.force-text-white`
- **Aprendizaje:** Al conmutar entre modo claro y oscuro, los textos superpuestos en botones o fondos degradados (ej: `bg-emerald-500`) pueden perder contraste si no se fuerza explícitamente el color blanco.
- **Regla:** Utilizar `.force-text-white` (`color: #ffffff !important`) en botones primarios, badges sobre imágenes y toasts flotantes.

### [MEM-SAVE-003] Resiliencia y Manejo de Estados UI (DoD)
- **Aprendizaje:** Un catálogo dinámico debe anticipar casos de mes sin cuotas (Empty state), demoras en lectura (Loading skeleton) y fallos en la persistencia local (Error state).
- **Regla:** Diseñar e implementar los 4 estados visuales de forma explícita, dotando al estado de error de botones de reintento y restauración de datos seguros.

### [MEM-SAVE-004] Accesibilidad en Modales Emergentes
- **Regla:** Los modales deben cerrarse por 4 vías:
  1. Botón de cruz superior (`fa-xmark`).
  2. Botón inferior de confirmación ("Cerrar detalle" / "Entendido").
  3. Clic en el fondo oscuro translúcido (backdrop).
  4. Presión de la tecla `Escape` en el teclado.

---

## 3. Resúmenes de Hitos de Sesión (`mem_session_summary`)

### Hito 1: Creación de la Estructura Base y Contexto SDD
- Creación de los 6 documentos de Master Context en `docs/contexto/` (`arquitectura.md`, `convenciones.md`, `decisiones.md`, `errores-conocidos.md`, `flujo-de-trabajo.md`, `glosario.md`).
- Vinculación en `GEMINI.md` de las reglas globales y los documentos maestros.

### Hito 2: Maquetación SPA e Interactividad Inicial
- Maquetación de la portada fintech en `index.html`.
- Integración de TailwindCSS CDN, Google Fonts Inter y FontAwesome v6.5.
- Implementación de la lógica de cálculo de cuotas y meses vigentes en JavaScript Vanilla.

### Hito 3: Adecuación Final, Catálogo con Fotos y Cierre de DoD (100% Cumplido)
- Maquetación de 6 tarjetas de catálogo con imágenes Unsplash reales, títulos, avances de cuotas y descripciones.
- Implementación del modal de detalle con foto ampliada y desglose completo.
- Implementación del Formulario de Contacto / Inscripción a Alertas Financieras junto con el registro de consumos en un selector de pestañas accesible.
- Incorporación del 4to estado UI (Error) con simulador interactivo para evaluadores (`[Ver Estado Error (DoD)]`).
- Redacción y entrega del reporte técnico `REPORTE_VERIFICACION_SDD.md`.
- Conclusión exitosa con validación de sintaxis limpia y cero errores en consola.

### Hito 4: Reestructuración a Resumen de Gastos y Formulario de Alta Exclusivo (Sin Imágenes)
- Transformación de la pestaña "Catálogo de Tarjetas" en "Resumen", mostrando métricas financieras, selector de mes y tarjetas de gasto en cuotas sin imágenes.
- Transformación de la pestaña "Contacto" en "Agregar", eliminando por completo los formularios de contacto e inscripción.
- Formulario de gasto exclusivo con los campos requeridos: Nombre/Concepto, Precio/Monto Total, Cantidad de Cuotas, Categoría y Mes de Inicio, con cálculo automático en vivo de la cuota mensual.
- Eliminación integral del uso y dependencia de imágenes externas (Unsplash) en tarjetas, modales y datos semilla (`INITIAL_GASTOS`).
- Preservación íntegra de los 4 estados UI de la Definition of Done (Loading, Empty, Error, Success) y del cumplimiento de las rúbricas del proyecto final.
