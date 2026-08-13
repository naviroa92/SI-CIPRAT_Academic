# Rol: Super Administrador — Plan de Capacitación

## Introducción — ¿Qué es SI-CIPRAT?

SI-CIPRAT es el **Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas**, desarrollado por el **Ministerio del Interior de Colombia**. Es la plataforma digital que centraliza el monitoreo y seguimiento a las alertas tempranas emitidas por la Defensoría del Pueblo, articulando la respuesta de las entidades del nivel central y territorial.

### Contexto

El Ministerio del Interior gestiona más de 100 alertas tempranas activas que deben ser monitoreadas a nivel territorial. Antes de SI-CIPRAT, esta gestión enfrentaba retos críticos:

- Ausencia de una fuente de información confiable, unificada y escalable
- Deficiencias en la comunicación entre el nivel central y el nivel territorial
- Procesos manuales con escasa automatización, generando reprocesos y demoras
- Acceso limitado a información en tiempo real, afectando la oportunidad en la toma de decisiones

### Objetivo

Garantizar la articulación entre las entidades del orden territorial, el nivel central y las subdirecciones, mediante una fuente de información unificada y alineada con la gestión y ejecución territorial de las alertas tempranas, permitiendo una coordinación eficiente, el intercambio oportuno de información y la toma de decisiones basadas en datos confiables para la prevención y atención integral de los riesgos identificados.

### Funcionalidades principales

- **Gestión de acceso y autenticación** — Acceso seguro por perfil con roles y permisos diferenciados por entidad
- **Gestión y notificación de alertas tempranas** — Centraliza la recepción de alertas de la Defensoría y genera notificaciones automáticas a las entidades CIPRAT
- **Gestión de planes de acción** — Permite crear, compartir y aprobar planes de acción con recordatorios automáticos
- **Seguimiento y reporte de actividades** — Generación de reportes periódicos con evidencias y medición del avance de ejecución
- **Tableros de control con georreferenciación** — Visualización en tiempo real de información georreferenciada, exportable en Excel y PDF
- **Exportación y visualización de reportes** — Consulta de alertas en mapas y tableros integrados

---


## Perfil del Rol

| Campo | Detalle |
|-------|---------|
| **Rol** | Super Administrador |
| **Alcance** | Nacional — acceso total al sistema |
| **Objetivo principal** | Administrar técnica y operativamente la totalidad de la plataforma SI-CIPRAT |
| **Quién ocupa este rol** | Personal TI o enlace técnico del Ministerio del Interior |

---

## Objetivo de Capacitación

Al finalizar la formación, el Super Administrador podrá gestionar de forma autónoma todos los módulos de la plataforma: configurar usuarios y entidades, administrar alertas tempranas, gestionar recomendaciones y planes de acción, aprobar informes, ejecutar reportes y supervisar la interoperabilidad con SISAT.

---

## Alcance en la Plataforma

### Módulos con acceso completo (visualización + gestión)

| Módulo | Acciones disponibles |
|--------|----------------------|
| Usuarios y Organizaciones | Invitar, editar, activar/desactivar usuarios; crear, editar y eliminar entidades |
| Gestión de Alertas Tempranas | Crear, editar, cerrar, eliminar alertas; gestionar recomendaciones; descargar; ver historial |
| Planes de Acción | Ver, aprobar, observar planes; gestionar actividades e informes |
| Seguimiento y Monitoreo | Aprobar actividades e informes de seguimiento |
| Informes de Seguimiento | Visualizar y subir informes de seguimiento |
| Reportes | Consultar y cargar informes; aprobar informes |
| Visualización Geográfica | Mapa interactivo y mapas estáticos |
| Procesamiento con IA | Acceso completo |
| Notificaciones | Todas las notificaciones del sistema |
| Interoperabilidad X-ROAD | Supervisión de endpoints y datos recibidos |
| Oficios de Consumación | Subir y visualizar oficios |
| Inicio de Plataforma | Vista global nacional |

### Capacidades exclusivas del Super Administrador

- Eliminar alertas y recomendaciones
- Cerrar alertas
- Editar o escalar usuarios al rol Super Administrador
- Gestionar otros Super Administradores
- Subir oficios de consumación

---

## Segmentación de Visualización

- **Dashboard de inicio**: Vista global nacional (todas las alertas, todos los departamentos).
- **Alertas**: Sin filtro de restricción — ve todas las alertas del sistema.
- **Planes de acción**: Visualización filtrada por alerta/entidad, sin restricción geográfica.
- **Reportes**: Acceso total sin segmentación.

---

## Ruta de Aprendizaje

### Módulo 0 — Contexto de la Plataforma SI-CIPRAT

**Objetivo:** Que el usuario entienda el marco institucional en el que opera y el funcionamiento de SI-CIPRAT antes de comenzar a usar la plataforma.

SI-CIPRAT es el **Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT)**, una plataforma desarrollada por el **Ministerio del Interior de Colombia** para centralizar y articular la gestión de las alertas tempranas emitidas por la Defensoría del Pueblo.

La **Comisión Intersectorial CIPRAT** reúne a entidades del nivel central y territorial con el mandato de responder de forma coordinada y oportuna ante los escenarios de riesgo identificados en el territorio nacional. Antes de SI-CIPRAT, esta coordinación dependía de procesos manuales, comunicaciones fragmentadas y ausencia de una fuente de información unificada, lo que generaba reprocesos, demoras y dificultades para tomar decisiones basadas en datos confiables y en tiempo real.

SI-CIPRAT resuelve estos retos al ofrecer un espacio digital común donde la Defensoría del Pueblo emite alertas tempranas, el Ministerio del Interior las gestiona y emite recomendaciones, y las entidades territoriales responden con planes de acción concretos que son monitoreados, aprobados y seguidos a lo largo de todo su ciclo de vida. Cada actor del ecosistema —Defensoría, Ministerio, entidades centrales, subdirecciones y monitores— tiene un rol definido dentro de la plataforma, con acceso segmentado según sus responsabilidades.

El objetivo central del sistema es garantizar la articulación entre todos estos niveles mediante una fuente de información unificada, que permita una coordinación eficiente, el intercambio oportuno de información y la toma de decisiones basadas en datos confiables para la prevención y atención integral de los riesgos identificados en el territorio.

---

### Módulo 1 — Acceso y Configuración de Cuenta
- Proceso de autenticación con 2FA (código de 4 dígitos, JWT 24h)
- Gestión del perfil personal
- Recuperación de contraseña

### Módulo 2 — Gestión de Usuarios y Entidades
- Invitar usuarios (todos los roles disponibles, excepto Super Admin)
- Ver, editar y activar/desactivar usuarios
- Eliminar invitaciones pendientes
- Crear y editar entidades territoriales centrales y subdirecciones
- Entender la estructura: Entidad Central → Subdirección → Usuarios

### Módulo 3 — Gestión de Alertas Tempranas
- Registrar una nueva alerta temprana
- Editar y eliminar alertas
- Gestionar recomendaciones (crear, editar, eliminar)
- Cerrar una alerta y generar oficio de consumación
- Consultar historial de actividades de una alerta
- Descargar listado de alertas

### Módulo 4 — Planes de Acción
- Revisar planes de acción enviados por entidades territoriales
- Aprobar o rechazar un plan de acción
- Registrar observaciones sobre actividades
- Entender el ciclo completo: recomendación → plan → aprobación → ejecución

### Módulo 5 — Seguimiento y Monitoreo
- Aprobar actividades de planes en curso
- Aprobar informes de avance
- Visualizar el estado de planes por alerta

### Módulo 6 — Informes y Reportes
- Subir informes de seguimiento
- Ejecutar consultas de reporte
- Cargar y aprobar informes de ejecución
- Descargar reportes

### Módulo 7 — Visualización Geográfica y Dashboard
- Navegar el mapa interactivo del dashboard
- Interpretar indicadores por departamento
- Consultar mapas estáticos de informes ejecutivos

### Módulo 8 — Interoperabilidad y Oficios
- Entender el flujo de datos desde SISAT vía X-Road
- Consultar oficios de consumación recibidos
- Subir oficios manualmente cuando aplica

### Módulo 9 — Administración Avanzada
- Gestión de múltiples Super Administradores
- Supervisión de notificaciones del sistema
- Buenas prácticas de administración de plataformas gubernamentales

---

## Indicadores de Logro

- [ ] Puede invitar y configurar usuarios de cualquier rol
- [ ] Puede crear y estructurar entidades con subdirecciones
- [ ] Puede registrar, editar y cerrar una alerta completa
- [ ] Puede aprobar un plan de acción e informes
- [ ] Puede ejecutar y descargar un reporte
- [ ] Puede consultar oficios de consumación y datos de interoperabilidad
- [ ] Conoce todas las restricciones de permisos por rol
