# Bitácora de Errores Conocidos y Prevención (Gotchas) - Cuotin

## Gotchas Típicos de Maquetado y Soluciones

### 1. Desborde Horizontal en Celulares (`overflow-x`)
- **Problema**: Tablas, tarjetas o contenedores con anchos fijos que rompen el viewport en móviles generando scroll horizontal no deseado.
- **Prevención**: Aplicar `overflow-x-hidden` en el contenedor `<body>` y `<main>`, utilizando clases responsivas `w-full` y `max-w-md` / `max-w-7xl`.

### 2. Pérdida de Contraste en Modo Oscuro (Textos Invisibles)
- **Problema**: Textos que quedan con color oscuro sobre fondo slate oscuro al alternar clases del tema.
- **Prevención**: Enforzar la regla auxiliar `.force-text-white` (`color: #ffffff !important`) en botones y encabezados críticos sobre degradados o fondos oscuros.

### 3. Recarga Involuntaria al Enviar Formulario
- **Problema**: El comportamiento predeterminado del HTML `<form>` envía una petición GET/POST y refresca la página, destruyendo el estado SPA.
- **Prevención**: Invocar siempre `e.preventDefault()` en la primera línea del controlador de JS (`handleAgregarGasto`).

### 4. Ausencia de Retroalimentación en Estados Vacíos
- **Problema**: Al cambiar a un mes donde no hay cuotas activas, la pantalla queda vacía desconcertando al usuario.
- **Prevención**: Renderizado condicional del componente `state-empty` que informa explícitamente *"¡Sin cuotas registradas en este mes!"*.

### 5. Elementos Cliqueables No Accesibles
- **Problema**: Usar etiquetas `<div>` o `<span>` con evento `onclick` que no reciben foco por teclado ni lectores de pantalla.
- **Prevención**: Usar etiquetas `<button>` nativas con tipo explícito (`type="button"` o `type="submit"`).
