# Documento de Especificación de Requerimientos: Fytrac

## 1. Descripción del Sistema
**Fytrac** es una app financiera híbrida que garantiza la trazabilidad total de tu patrimonio. Automatiza la captura de gastos desde tu billetera digital, gestiona presupuestos mediante umbrales y proyecta tu flujo de caja. Funciona offline de manera instantánea y sincroniza en la nube bajo estrictos protocolos de encriptación y privacidad.

## 2. Matriz de Requerimientos

### 2.1 Requerimientos Funcionales (RF)

| ID | Módulo / Categoría | Descripción |
| :--- | :--- | :--- |
| **RF-01** | Cuentas y Transacciones | Creación de múltiples cuentas (banco, efectivo, billetera digital) con saldos independientes. |
| **RF-02** | Cuentas y Transacciones | Manejo de deuda separada del flujo de caja; pagos de tarjeta registrados como transferencias, no gastos duplicados. |
| **RF-03** | Cuentas y Transacciones | Creación, edición y eliminación de categorías dinámicas, con bloqueo de borrado si existe integridad referencial. |
| **RF-04** | Planificación y Presupuestos | Asignación de montos límite por categoría (Zero-Based Budgeting) con cálculo de uso en tiempo real. |
| **RF-05** | Planificación y Presupuestos | Emisión de alertas automatizadas al alcanzar umbrales de gasto configurables (ej. 50%, 75%, 90%, 100%). |
| **RF-06** | Planificación y Presupuestos | Registro automático de gastos fijos y suscripciones en sus fechas de vencimiento, programando el siguiente ciclo. |
| **RF-07** | Metas y Proyecciones | Cálculo del objetivo del fondo de emergencia basado en la multiplicación de gastos esenciales por meses configurables. |
| **RF-08** | Metas y Proyecciones | Generación de simulaciones a futuro (hasta 48 meses) de patrimonio, deuda y metas según tasas de ahorro actuales. |
| **RF-09** | Interoperabilidad | Exportación tabular de movimientos (CSV) e importación/exportación de la estructura completa (JSON). |
| **RF-10** | Captura Automática | Registro automático de transacciones realizadas mediante la billetera digital nativa del smartphone (pagos sin contacto). |
| **RF-11** | Captura Automática | Lectura de metadatos del comercio y asignación automática de categorías basada en el historial o envío a revisión. |

### 2.2 Requerimientos No Funcionales (RNF)

| ID | Módulo / Categoría | Descripción |
| :--- | :--- | :--- |
| **RNF-01** | Arquitectura y Datos | Estructuración central en un motor de base de datos relacional (ej. PostgreSQL) para asegurar persistencia global y transacciones ACID. |
| **RNF-02** | Seguridad y Privacidad | Cumplimiento de normativas de protección de datos personales, cifrado de información financiera y roles de auditoría. |
| **RNF-03** | Seguridad y Privacidad | Implementación de mitigación en la capa de red para bloquear intentos de fuerza bruta o escaneos anómalos. |
| **RNF-04** | Rendimiento | Renderizado asíncrono para gráficos y cruces de datos masivos, evitando el bloqueo de la interfaz de usuario. |
| **RNF-05** | Integración de Sistema | Uso de herramientas pasivas (como *Notification Listener*) u Open Banking para extraer montos y comercios de la billetera. |
| **RNF-06** | Integración de Sistema | Aislamiento estricto (Sandbox) del módulo de lectura para operar sin acceso a tokens criptográficos ni credenciales bancarias. |
| **RNF-07** | Arquitectura y Datos | **Implementación de base de datos local híbrida sincrónica, garantizando disponibilidad offline inmediata y consistencia bidireccional con el servidor central.** |