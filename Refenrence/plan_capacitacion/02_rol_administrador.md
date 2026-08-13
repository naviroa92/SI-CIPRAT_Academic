# Rol: Administrador — Plan de Capacitación

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
| **Rol** | Administrador |
| **Alcance** | Nacional — gestión operativa |
| **Objetivo principal** | Gestionar operativamente la plataforma a nivel nacional: usuarios, alertas, recomendaciones y reportes |
| **Quién ocupa este rol** | Enlace o coordinador del Ministerio del Interior responsable de la operación diaria |

---

## Objetivo de Capacitación

Al finalizar la formación, el Administrador podrá gestionar usuarios, invitar actores a la plataforma, registrar y editar alertas tempranas, emitir recomendaciones, descargar reportes y hacer seguimiento al estado de planes de acción, con pleno conocimiento de los límites de su rol frente al Super Administrador.

---

## Alcance en la Plataforma

### Módulos disponibles

| Módulo | Acciones disponibles |
|--------|----------------------|
| Usuarios y Organizaciones | Invitar, editar, activar/desactivar usuarios; crear y editar entidades |
| Gestión de Alertas Tempranas | Reportar/crear alertas; editar alertas; gestionar recomendaciones; descargar; ver historial |
| Planes de Acción | Visualizar planes de acción (filtrado) |
| Seguimiento y Monitoreo | Visualizar módulo de seguimiento |
| Informes de Seguimiento | Visualizar y subir informes de seguimiento |
| Reportes | Consultar, cargar y aprobar informes |
| Visualización Geográfica | Mapa interactivo y mapas estáticos |
| Notificaciones | Todas las notificaciones del sistema |
| Inicio de Plataforma | Vista global nacional |

### Restricciones frente al Super Administrador

- **No puede** eliminar alertas ni cerrarlas
- **No puede** eliminar recomendaciones
- **No puede** aprobar planes de acción ni informes de seguimiento
- **No puede** subir oficios de consumación
- **No puede** gestionar usuarios con rol Super Administrador
- **No puede** escalar un usuario al rol Super Administrador

---

## Segmentación de Visualización

- **Dashboard de inicio**: Vista global nacional.
- **Alertas**: Sin restricción geográfica — visualiza todas las alertas del sistema.
- **Planes de acción**: Visualización disponible pero sin capacidad de aprobación.
- **Reportes**: Acceso completo para consulta y carga.

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
- Autenticación con 2FA
- Gestión del perfil personal
- Recuperación de contraseña

### Módulo 2 — Gestión de Usuarios y Entidades
- Invitar usuarios a la plataforma (roles permitidos, formulario de invitación)
- Campos requeridos según rol: cargo, área, departamentos (Monitor), subdirección (Entidad Territorial)
- Reenviar y eliminar invitaciones pendientes
- Editar información de usuarios existentes
- Activar y desactivar usuarios
- Crear entidades centrales con categorías y subdirecciones
- Editar entidades (nombre, categorías, subdirecciones)

### Módulo 3 — Gestión de Alertas Tempranas
- Registrar una nueva alerta temprana
- Editar alertas existentes
- Agregar y editar recomendaciones sobre una alerta
- Consultar historial de actividades
- Descargar listado de alertas
- Entender por qué no puede cerrar ni eliminar alertas (diferencia con Super Admin)

### Módulo 4 — Planes de Acción (solo visualización)
- Navegar los planes de acción por alerta
- Interpretar el estado de cada plan (pendiente, en ejecución, finalizado)
- Entender el flujo del plan: recomendación → plan de acción → actividades → informes

### Módulo 5 — Seguimiento y Monitoreo
- Visualizar el módulo de seguimiento
- Interpretar el estado de aprobación de actividades e informes
- Identificar qué actores tienen responsabilidad de aprobación

### Módulo 6 — Informes y Reportes
- Subir informes de seguimiento
- Ejecutar consultas de reporte
- Cargar informes de ejecución
- Aprobar informes en el módulo de reportes

### Módulo 7 — Visualización Geográfica y Dashboard
- Interpretar el mapa interactivo del dashboard
- Filtrar alertas por departamento en el mapa
- Consultar mapas estáticos de informes ejecutivos

### Módulo 8 — Notificaciones
- Entender los tipos de notificaciones del sistema
- Gestionar el panel lateral de historial de actividades
- Búsqueda por texto en el panel de notificaciones

---

## Indicadores de Logro

- [ ] Puede invitar usuarios de cualquier rol (excepto Super Admin) con los campos correctos
- [ ] Puede crear una entidad territorial con múltiples subdirecciones
- [ ] Puede registrar y editar una alerta con sus recomendaciones
- [ ] Puede navegar e interpretar los planes de acción
- [ ] Puede cargar y aprobar informes en el módulo de reportes
- [ ] Conoce las diferencias de permisos entre Administrador y Super Administrador
