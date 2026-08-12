# SI-CIPRAT — Contexto General de la Plataforma

## ¿Qué es SI-CIPRAT?

SI-CIPRAT es el Sistema de Información de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas, adscrito al **Ministerio del Interior de Colombia**. Su propósito es centralizar, gestionar y dar seguimiento a las alertas tempranas emitidas por la Defensoría del Pueblo u otras fuentes, articulando la respuesta institucional de entidades territoriales, monitores y líderes de macrozona.

La plataforma permite que los actores involucrados en la respuesta rápida a alertas tempranas trabajen de forma coordinada, trazable y transparente, desde el registro de la alerta hasta la consumación del plan de acción.

---

## Módulos de la Plataforma

| # | Módulo | Descripción |
|---|--------|-------------|
| 1 | **Usuarios y Organizaciones** | Gestión de cuentas, roles, invitaciones y entidades territoriales |
| 2 | **Gestión de Alertas Tempranas** | Registro, edición, cierre e historial de alertas |
| 3 | **Planes de Acción** | Creación y gestión de actividades de respuesta por alerta |
| 4 | **Seguimiento y Monitoreo** | Aprobación de actividades e informes de avance |
| 5 | **Informes de Seguimiento** | Carga y visualización de informes periódicos |
| 6 | **Reportes** | Consultas, reportes de ejecución y carga de informes |
| 7 | **Visualización Geográfica** | Mapa interactivo (Dashboard) y mapas estáticos (Informes Ejecutivos) |
| 8 | **Procesamiento con Agente de IA** | Asistencia con procesamiento inteligente de información |
| 9 | **Consulta Ciudadana** | Vista pública con información habilitada para ciudadanos |
| 10 | **Interoperabilidad X-ROAD/SISAT** | Integración con el sistema SISAT mediante protocolo X-Road |
| 11 | **Oficios de Consumación** | Consulta de oficios recibidos por interoperabilidad |
| 12 | **Notificaciones** | Panel lateral con historial de actividades y alertas del sistema |

---

## Arquitectura de Roles

La plataforma define **8 roles** con diferentes niveles de acceso y alcance geográfico-institucional:

| Rol | Alcance | Perfil |
|-----|---------|--------|
| **Super Administrador** | Nacional — total | Administración técnica completa del sistema |
| **Administrador** | Nacional | Gestión operativa de la plataforma a nivel nacional |
| **Líder de Macrozona** | Macrozona | Supervisión y aprobación de monitores |
| **Monitor** | Departamental | Seguimiento de alertas y planes de acción en su(s) departamento(s) |
| **Entidad Territorial Central** | Entidad central | Gestión de planes de acción de su entidad |
| **Entidad Territorial Subdirección** | Subdirección | Gestión de planes de acción de su subdirección |
| **Consulta Global** | Nacional | Solo lectura a nivel nacional |
| **Consulta Entidad** | Entidad | Solo lectura a nivel de entidad central |

---

## Principios de Segmentación de Acceso

### Por nivel geográfico
- **Nacional**: Super Admin, Administrador, Líder Macrozona, Consulta Global
- **Departamental**: Monitor
- **Entidad central**: Entidad Territorial Central, Consulta Entidad
- **Subdirección**: Entidad Territorial Subdirección

### Por tipo de acción
- **Gestión (crear, editar, eliminar)**: Super Admin, Administrador
- **Operación (registrar, reportar, aprobar)**: Monitor, Entidad Territorial, Líder Macrozona
- **Consulta**: Consulta Global, Consulta Entidad

---

## Flujo General de una Alerta Temprana

```
Registro de Alerta
       ↓
Emisión de Recomendación (Admin / Super Admin)
       ↓
Plan de Acción (Entidad Territorial Central)
       ↓
Aprobación del Plan (Monitor / Super Admin)
       ↓
Ejecución y Carga de Informes (Entidad Territorial)
       ↓
Seguimiento y Aprobación de Informes (Monitor / Super Admin)
       ↓
Cierre de Alerta / Oficio de Consumación
```

---

## Autenticación

La plataforma usa autenticación de **dos factores (2FA)**:
1. Ingreso de correo electrónico y contraseña.
2. Verificación mediante código de 4 dígitos enviado al correo (vigencia: 1 hora).
3. Generación de token JWT con vigencia de 24 horas.

---

## Notificaciones del Sistema

Todos los roles reciben notificaciones para los siguientes eventos:

- Nueva alerta registrada
- Alerta cerrada
- Vencimiento próximo de informe del plan de acción (5 meses)
- Informe de seguimiento por alerta (Monitor, 5 meses)
- Observaciones sobre actividades

---

## Referencias Técnicas

- **Convención de historias de usuario**: `HU-[MÓDULO]-[NRO]` (ej. `HU-AT-001`)
- **API base**: `/api/v1/dashboard/`
- **Interoperabilidad**: `/api/v1/interoperabilidad/`
- **Documento fuente**: Entregable #38 — Historias de Usuario (v1.13, 2025-12-22)
- **Matriz de permisos**: Documento "ROLES & PERMISOS-2-3.xlsx"
