# Cronograma Ágil de Desarrollo: Fytrac

Este documento detalla el plan de desarrollo de la plataforma financiera híbrida **Fytrac**, estructurado bajo la metodología Scrum con *Sprints* de 2 semanas.

## Ceremonias Scrum (Por Sprint)
*   **Sprint Planning:** Lunes de la Semana 1 (Planificación de las historias de usuario a abordar).
*   **Daily Standup:** 15 minutos diarios de sincronización técnica.
*   **Sprint Review:** Viernes de la Semana 2 (Demostración de las funcionalidades terminadas).
*   **Sprint Retrospective:** Viernes de la Semana 2 (Evaluación de mejora continua para el equipo).

---

## Planificación de Sprints

### Sprint 0: Arquitectura y Diseño Base (Semanas 1 - 2)
**Objetivo:** Establecer los cimientos técnicos, entornos y diseño de interfaz.
*   Diseño de la arquitectura *Local-First* y selección de la tecnología de sincronización.
*   Modelado del esquema relacional (PostgreSQL) para el servidor central.
*   Configuración del repositorio, tableros Kanban y pipelines de CI/CD.
*   Creación de wireframes y flujos de usuario (UI/UX).
*   **RNF-02:** Definición de políticas de encriptación y cumplimiento normativo.

### Sprint 1: Motor Local y Gestión de Cuentas (Semanas 3 - 4)
**Objetivo:** Entregar la aplicación funcionando offline con creación de cuentas y categorías.
*   **RNF-07:** Implementación de la base de datos local en el dispositivo.
*   **RF-01:** Módulo de creación y edición de cuentas (Banco, Billetera, Efectivo).
*   **RF-03:** Módulo de categorías y subcategorías dinámicas.
*   Lógica de bloqueo de eliminación para categorías con integridad referencial activa.

### Sprint 2: Transacciones y Flujo de Crédito (Semanas 5 - 6)
**Objetivo:** Permitir el registro manual de movimientos y resolver la contabilidad compleja de las tarjetas.
*   Formulario de registro manual de ingresos, gastos y transferencias.
*   **RF-02:** Implementación de la lógica contable de crédito (separar deuda de flujo de caja).
*   Validaciones de montos y cálculos de saldos en tiempo real.
*   Sincronización inicial bidireccional entre la base de datos local y PostgreSQL.

### Sprint 3: Presupuestos y Automatización Básica (Semanas 7 - 8)
**Objetivo:** Activar las herramientas de control y advertencia de gastos.
*   **RF-04:** Interfaz y lógica para el *Zero-Based Budgeting* por categoría.
*   **RF-05:** Motor de cálculo de uso de presupuesto y disparadores de alertas (umbrales 50%, 75%, 90%, 100%).
*   **RF-06:** Automatización del registro de gastos fijos y suscripciones.

### Sprint 4: Trazabilidad Automática - Billetera Digital (Semanas 9 - 10)
**Objetivo:** Reducir la fricción del usuario mediante la captura pasiva de transacciones móviles.
*   **RNF-05 & RNF-06:** Implementación del *Notification Listener* (entorno Sandbox) para captura de pagos.
*   **RF-10:** Registro automático del movimiento localmente a partir del evento.
*   **RF-11:** Algoritmo de auto-etiquetado según los metadatos del comercio.

### Sprint 5: Análisis, Metas y Proyecciones (Semanas 11 - 12)
**Objetivo:** Entregar valor analítico avanzado y visión financiera a futuro.
*   **RF-07:** Módulo de metas y cálculo inteligente del Fondo de Emergencia.
*   **RF-08:** Algoritmo de proyecciones a 48 meses de patrimonio y deuda.
*   **RNF-04:** Renderizado asíncrono de gráficos interactivos en el Dashboard.

### Sprint 6: Interoperabilidad, Seguridad y Cierre (Semanas 13 - 14)
**Objetivo:** Blindar la aplicación, habilitar la migración de datos y preparar el lanzamiento.
*   **RF-09:** Funcionalidad de exportación CSV e importación/exportación JSON.
*   **RNF-03:** Configuración final de la capa de red (mitigación de fuerza bruta y escaneo en el backend).
*   Pruebas de estrés de la sincronización *offline-online*.
*   QA general, corrección de bugs y despliegue a producción.