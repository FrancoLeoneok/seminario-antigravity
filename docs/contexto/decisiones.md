# Registro de Decisiones de Arquitectura (ADR) - Cuotin

> **Control de Guardas**: Cualquier alteración en reglas de negocio existentes, esquemas de datos o flujos de eventos requiere confirmación previa obligatoria por parte del usuario.

## ADR-001: Adopción del Sistema Operativo de Reglas Antigravity
- **Fecha**: 2026-08-31T23:50:00-03:00
- **Estatus**: Aprobado
- **Contexto**: Necesidad de estandarización global de calidad, flujo de trabajo SDD y memoria continua.
- **Decisión**: Configurar las reglas globales en `.agents/rules/antigravity_global_rules.md` vinculadas mediante `GEMINI.md` con trigger `always_on`.

## ADR-002: Arquitectura Single Page Application (SPA) en Archivo Único
- **Fecha**: 2026-09-01T00:06:00-03:00
- **Estatus**: Aprobado
- **Contexto**: Restricción explícita del desafío de no utilizar servidores backend ni múltiples archivos HTML.
- **Decisión**: Encapsular todas las vistas (Hero, Resumen, Agregar Gasto) en `index.html` gestionando la visibilidad dinámicamente con JavaScript Vanilla (`hidden`).

## ADR-003: Persistencia de Datos en localStorage
- **Fecha**: 2026-09-01T00:06:00-03:00
- **Estatus**: Aprobado
- **Contexto**: Garantizar que las compras cargadas por el usuario no se pierdan al cerrar o recargar el navegador sin usar bases de datos externas.
- **Decisión**: Crear un módulo de lectura y escritura en `localStorage` con datos semilla por defecto para pruebas iniciales.

## ADR-004: Adopción de TailwindCSS v3 CDN y Dark Mode Fintech
- **Fecha**: 2026-09-01T00:04:00-03:00
- **Estatus**: Aprobado
- **Contexto**: Necesidad de maquetación rápida, consistente y estética moderna tipo aplicación financiera.
- **Decisión**: Utilizar TailwindCSS v3 vía CDN oficial con paleta en tonos `slate-900` / `slate-800` y acentos `emerald-500`.

## ADR-005: Navegación Táctil Móvil con Bottom Navigation Bar
- **Fecha**: 2026-09-01T00:04:00-03:00
- **Estatus**: Aprobado
- **Contexto**: Optimización de la experiencia de usuario (UX) en dispositivos móviles, donde transita más del 70% del tráfico.
- **Decisión**: Incorporar una barra de navegación fija en la parte inferior para pantallas pequeñas y menú hamburguesa en el header.

## ADR-006: Reestructuración de Pestañas a Resumen y Agregar Gasto sin Imágenes
- **Fecha**: 2026-09-10T20:53:00-03:00
- **Estatus**: Aprobado
- **Contexto**: El producto tiene como foco central el registro y proyección de gastos en cuotas. La pestaña "Catálogo" con fotos de e-commerce y la pestaña "Contacto / Inscripción" desviaban al usuario del propósito financiero de la aplicación.
- **Decisión**:
  1. Renombrar la sección y pestaña "Catálogo" a "Resumen", desplegando métricas de cuotas y tarjetas de gasto con estética fintech sin imágenes.
  2. Renombrar "Contacto" a "Agregar", eliminando formularios de inscripción y dejando exclusivamente el formulario para registrar un nuevo gasto (nombre, precio, cantidad de cuotas, categoría y mes de inicio).
  3. Eliminar la dependencia de imágenes externas (Unsplash) en tarjetas, formularios y modales de desglose.
