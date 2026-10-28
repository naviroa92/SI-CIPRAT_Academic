Generado desde: monorepo SI-CIPRAT rama develop commit 56d3f33 (2026-07-17 10:20:06 -0500) · 2026-10-28

# Ruta 09 · Consulta — Departamentos

## Ficha de la ruta

| Campo | Valor |
|---|---|
| Número | 09 |
| Rol | Consulta |
| Subrol | Departamentos |
| Alcance | Departamentos asignados · solo lectura |
| Descripción corta | Consulta las alertas, recomendaciones, planes, informes y oficios de sus departamentos, sin modificar datos. |
| Módulos | 10 |
| Modalidad | Autoaprendizaje |
| Prerrequisitos de la ruta | Cuenta activa con rol Consulta Departamentos y al menos un departamento asignado. |

## Definición del rol

Rol de solo lectura. Consulta alertas, recomendaciones, planes de acción, seguimiento, informes de seguimiento y oficios de consumación, y descarga archivos y listados, sin crear, editar ni aprobar registros de negocio. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:18-29,71-82,101-112,156-167`, `dashboard/src/components/ui/UserFormModal.tsx:434-440`. Tiene tres subroles que se distinguen por el alcance de los datos: Global, Entidad y Departamentos.

**Criterio técnico:** Tres valores del enumerado con el mismo prefijo y los mismos permisos de lectura: `CONSULTA_GLOBAL` (sin filtro), `CONSULTA_ENTIDAD` (filtro por entidad, `main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:16-21`) y `CONSULTA_DEPARTAMENTOS` (filtro por departamentos, `main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:16-21`) (`main-api/CipratApi/Modelos/Enums.cs:41-48`). Se modelan como un rol con tres subroles.

**Subroles de este rol:** Global, Entidad, Departamentos.

**Quién lo ocupa:** [INFERIDO] Funcionarios de gobernaciones, entidades territoriales u organismos que hacen seguimiento a un territorio sin registrar información. Base: el texto de ayuda "Solo lectura filtrado por departamentos asignados." (`dashboard/src/components/ui/UserFormModal.tsx:440`).

**Cómo se asigna:** Lo asigna un Super Administrador o un Administrador al invitar al usuario con **Rol** "Consulta Departamentos". En pantalla los **Departamentos** son obligatorios ("Debe seleccionar al menos un departamento", `dashboard/src/components/ui/UserFormModal.tsx:259-263`); el servidor solo los exige a Monitor y Líder de Macrozona (`main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:83-97`).

## Definición del subrol

Usuario de consulta limitado a uno o varios departamentos. El sistema lo identifica con el valor `CONSULTA_DEPARTAMENTOS` y la lista de departamentos de su usuario. Ve las alertas que tienen al menos un municipio en esos departamentos (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:16-21,79-88`). No ve el menú *Planes de acción*, pero la ruta de esa pantalla no lo bloquea (`dashboard/src/components/layout/Sidebar.tsx:50-55`, `dashboard/src/App.tsx:56`; riesgo R11).

## Objetivo de capacitación

Al terminar esta ruta, el usuario de Consulta — Departamentos podrá encontrar, leer e interpretar la información de las alertas, recomendaciones, seguimiento, informes de seguimiento y oficios de consumación de sus departamentos, descargar listados y archivos, consultar el historial de las alertas y el detalle de las actividades, y saber a qué rol acudir cuando necesita que se modifique un dato.

## Permisos por módulo

| Módulo | Acciones disponibles |
|---|---|
| Acceso a la plataforma | Iniciar sesión con correo y contraseña; Validar el código de verificación; Reenviar el código de verificación; Activar la cuenta desde la invitación; Solicitar el restablecimiento de la contraseña; Restablecer la contraseña con el enlace; Cerrar sesión; Cierre automático de la sesión por inactividad o vencimiento; Consultar los Términos de uso; Contactar al soporte técnico; Consultar Mi perfil |
| Inicio | Consultar los indicadores del Inicio (consulta); Consultar la última alerta emitida (consulta); Consultar "Alertas por departamento" (Top 10) (consulta); Consultar "Alertas recientes" (consulta); Consultar el "Porcentaje de Avance Global" (consulta); Consultar el mapa de municipios con alertas (consulta); Consultar el tablero público sin iniciar sesión; Usar el panel de accesibilidad; Usar el menú lateral |
| Alertas tempranas | Listar alertas (consulta); Buscar alertas (consulta); Filtrar alertas (consulta); Ver el detalle de una alerta (consulta); Descargar el PDF de la alerta (consulta); Consultar el historial de actividades de la alerta (consulta); Descargar el listado de alertas (CSV) (consulta) |
| Recomendaciones | Listar las recomendaciones de una alerta (consulta); Buscar y filtrar recomendaciones (consulta); Ver el detalle de una recomendación (consulta); Descargar las recomendaciones (CSV) (consulta); Asignar el código RC (consulta) |
| Seguimiento | Listar los planes en Seguimiento (consulta); Buscar y filtrar planes en Seguimiento (consulta); Descargar el listado de Seguimiento (CSV) (consulta); Consultar recomendaciones, actividades e informes en Seguimiento (consulta) |
| Informes de seguimiento | Listar los informes de seguimiento (consulta); Buscar y filtrar informes por alerta (consulta); Ver el detalle de un informe de seguimiento (consulta); Descargar el PDF del informe de seguimiento (consulta) |
| Oficios de consumación | Listar los oficios de consumación (consulta); Buscar y filtrar oficios por alerta (consulta); Ver el detalle de un oficio (consulta); Descargar el PDF del oficio (consulta) |
| Notificaciones | Abrir el panel de Notificaciones (consulta); Buscar en el panel de Notificaciones (consulta); Cargar más notificaciones (consulta); Recibir el correo de invitación; Recibir el correo con el código de verificación; Recibir el correo de restablecimiento de contraseña |
| Interoperabilidad X-Road (SISAT) | Recibir alertas tempranas por X-Road (consulta); Recibir informes de seguimiento por X-Road (consulta); Recibir oficios de consumación por X-Road (consulta) |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (consulta); Recalcular estados y porcentajes de cumplimiento (consulta); Calcular el próximo informe al aprobar un informe (consulta) |

## Matriz de capacidades en la plataforma

Fuente: `analisis/09_capacidades_CD.md`. Total de funcionalidades: 145 | Puede: 17 | Puede con restricción: 0 | Solo consulta: 39 | No puede: 89.

### Qué SÍ puede hacer el usuario de Consulta — Departamentos

| Módulo | Funcionalidad | Definición | Tipo | Condición o alcance | Dónde se explica |
|---|---|---|---|---|---|
| Acceso a la plataforma | Iniciar sesión con correo y contraseña (F-ACC-01) ✔ | Verifica el correo y la contraseña y, si son correctos, envía al correo del usuario un código de verificación de 4 dígitos. | Estado | Sin restricción adicional | Módulo 01 — Actividad 2 |
| Acceso a la plataforma | Validar el código de verificación (F-ACC-02) ✔ | Valida el código de 4 dígitos recibido por correo y abre la sesión con el rol y el alcance del usuario. | Estado | Sin restricción adicional | Módulo 01 — Actividad 2 |
| Acceso a la plataforma | Reenviar el código de verificación (F-ACC-03) ✔ | Genera y envía un nuevo código de verificación cuando el anterior no llegó o venció. | Estado | Sin restricción adicional | Módulo 01 — Actividad 2 |
| Acceso a la plataforma | Activar la cuenta desde la invitación (F-ACC-04) ✔ | Desde el enlace del correo de invitación, el usuario crea su contraseña y su cuenta pasa a Activo. | U | Sin restricción adicional | Módulo 01 — Actividad 1 |
| Acceso a la plataforma | Solicitar el restablecimiento de la contraseña (F-ACC-05) ✔ | Envía al correo un enlace para crear una contraseña nueva. | U | Sin restricción adicional | Módulo 01 — Actividad 3 |
| Acceso a la plataforma | Restablecer la contraseña con el enlace (F-ACC-06) ✔ | Crea una contraseña nueva que cumpla las reglas y no repita las 5 anteriores. | U | Sin restricción adicional | Módulo 01 — Actividad 3 |
| Acceso a la plataforma | Cerrar sesión (F-ACC-07) ✔ | Termina la sesión del usuario desde el menú de su nombre. | Estado | Sin restricción adicional | Módulo 01 — Actividad 4 |
| Acceso a la plataforma | Cierre automático de la sesión por inactividad o vencimiento (F-ACC-08) ✔ | Cierra la sesión tras 60 minutos sin actividad o cuando vence el token, y avisa con un mensaje. | Automática | Sin restricción adicional | Módulo 01 — Actividad 4 |
| Acceso a la plataforma | Consultar los Términos de uso (F-ACC-09) ✔ | Muestra los términos y condiciones de uso de la plataforma, con el correo de soporte. | R | Sin restricción adicional | Módulo 01 — Actividad 5 |
| Acceso a la plataforma | Contactar al soporte técnico (F-ACC-10) ✔ | Abre un correo dirigido a la cuenta de soporte de la plataforma. | R | Sin restricción adicional | Módulo 01 — Actividad 5 |
| Acceso a la plataforma | Consultar Mi perfil (F-ACC-12) ✔ | Muestra los datos de la cuenta: Información General, Entidad y Acceso y Asignaciones. | R | Sin restricción adicional | Módulo 01 — Actividad 6 |
| Inicio | Consultar los indicadores del Inicio (F-INI-01) 👁 | Muestra Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales y Alertas cerradas, con la tendencia "vs ultimo mes". | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 1 |
| Inicio | Consultar la última alerta emitida (F-INI-02) 👁 | Muestra el banner "Se ha emitido la Alerta Temprana…" con la alerta activa más reciente y el botón **Ver Alerta**. | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 2 |
| Inicio | Consultar "Alertas por departamento" (Top 10) (F-INI-03) 👁 | Ranking de los 10 departamentos con más alertas y su porcentaje del total. | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 2 |
| Inicio | Consultar "Alertas recientes" (F-INI-04) 👁 | Lista las 9 alertas más recientes por fecha de la alerta. | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 2 |
| Inicio | Consultar el "Porcentaje de Avance Global" (F-INI-05) 👁 | Promedio del porcentaje de cumplimiento de las alertas (no borradores) y total de actividades ejecutadas frente a programadas. | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 1 |
| Inicio | Consultar el mapa de municipios con alertas (F-INI-06) 👁 | Mapa de Colombia con los municipios que tienen alertas (rojo: inminencia; azul: estructural) y tabla accesible con los mismos datos. | R | Solo alertas con municipios en sus departamentos | Módulo 02 — Actividad 2 |
| Inicio | Consultar el tablero público sin iniciar sesión (F-INI-07) ✔ | La página de inicio pública (`/`) muestra los mismos bloques con la información nacional, sin filtro de rol. | R | Sin restricción adicional | Módulo 02 — Actividad 4 |
| Inicio | Usar el panel de accesibilidad (F-INI-08) ✔ | Activa o desactiva el alto contraste y aumenta o reduce el tamaño de letra. | U | Sin restricción adicional | Módulo 02 — Actividad 3 |
| Inicio | Usar el menú lateral (F-INI-09) ✔ | Navega entre los módulos visibles para el rol; el menú se puede ocultar. | R | Sin restricción adicional | Módulo 02 — Actividad 3 |
| Notificaciones | Abrir el panel de Notificaciones (F-NOT-01) 👁 | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Solo alertas con municipios en sus departamentos | Módulo 08 — Actividad 1 |
| Notificaciones | Buscar en el panel de Notificaciones (F-NOT-02) 👁 | Filtra el historial por texto. | R | Solo alertas con municipios en sus departamentos | Módulo 08 — Actividad 1 |
| Notificaciones | Cargar más notificaciones (F-NOT-03) 👁 | Trae 10 registros más del historial. | R | Solo alertas con municipios en sus departamentos | Módulo 08 — Actividad 1 |
| Notificaciones | Recibir el correo de invitación (F-NOT-04) ✔ | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Sin restricción adicional | Módulo 01 — Actividad 1; Módulo 08 — Actividad 2 |
| Notificaciones | Recibir el correo con el código de verificación (F-NOT-05) ✔ | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Sin restricción adicional | Módulo 01 — Actividad 2; Módulo 08 — Actividad 2 |
| Notificaciones | Recibir el correo de restablecimiento de contraseña (F-NOT-06) ✔ | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Sin restricción adicional | Módulo 01 — Actividad 3; Módulo 08 — Actividad 2 |
| Alertas tempranas | Listar alertas (F-ALE-01) 👁 | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 1 |
| Alertas tempranas | Buscar alertas (F-ALE-02) 👁 | Busca por número o texto de la alerta. | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 1 |
| Alertas tempranas | Filtrar alertas (F-ALE-03) 👁 | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 1 |
| Alertas tempranas | Ver el detalle de una alerta (F-ALE-04) 👁 | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 2 |
| Alertas tempranas | Descargar el PDF de la alerta (F-ALE-05) 👁 | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 2 |
| Alertas tempranas | Consultar el historial de actividades de la alerta (F-ALE-06) 👁 | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 3 |
| Alertas tempranas | Descargar el listado de alertas (CSV) (F-ALE-07) 👁 | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 4 |
| Recomendaciones | Listar las recomendaciones de una alerta (F-REC-01) 👁 | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Solo alertas con municipios en sus departamentos | Módulo 03 — Actividad 5; Módulo 04 — Actividad 1 |
| Recomendaciones | Buscar y filtrar recomendaciones (F-REC-02) 👁 | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Solo alertas con municipios en sus departamentos | Módulo 04 — Actividad 1 |
| Recomendaciones | Ver el detalle de una recomendación (F-REC-03) 👁 | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Solo alertas con municipios en sus departamentos | Módulo 04 — Actividad 2 |
| Recomendaciones | Descargar las recomendaciones (CSV) (F-REC-04) 👁 | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Solo alertas con municipios en sus departamentos | Módulo 04 — Actividad 3 |
| Recomendaciones | Asignar el código RC (F-REC-08) 👁 | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Ve el código asignado | Módulo 04 — Actividad 1 |
| Seguimiento | Listar los planes en Seguimiento (F-SEG-01) 👁 | Pantalla "Seguimiento de Planes": por alerta muestra Ejecutado vs programado, Plan de acción e Informe, y la acción para confirmar el plan. | R | Solo alertas con municipios en sus departamentos | Módulo 05 — Actividad 1 |
| Seguimiento | Buscar y filtrar planes en Seguimiento (F-SEG-02) 👁 | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento. | R | Solo alertas con municipios en sus departamentos | Módulo 05 — Actividad 1 |
| Seguimiento | Descargar el listado de Seguimiento (CSV) (F-SEG-03) 👁 | Descarga el listado de planes visible. | Archivo | Solo alertas con municipios en sus departamentos | Módulo 05 — Actividad 1 |
| Seguimiento | Consultar recomendaciones, actividades e informes en Seguimiento (F-SEG-04) 👁 | Recorre alerta › recomendaciones › actividades en modo seguimiento, con el panel "Información Actividades" y los "Informes de ejecución". | R | Solo alertas con municipios en sus departamentos | Módulo 05 — Actividad 2 |
| Informes de seguimiento | Listar los informes de seguimiento (F-ISE-01) 👁 | Tabla con Informe, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Ve todos (el listado no filtra por departamentos) | Módulo 06 — Actividad 1 |
| Informes de seguimiento | Buscar y filtrar informes por alerta (F-ISE-02) 👁 | Busca por número y filtra por Alerta asociada. | R | Ve todos (el listado no filtra por departamentos) | Módulo 06 — Actividad 1 |
| Informes de seguimiento | Ver el detalle de un informe de seguimiento (F-ISE-03) 👁 | Muestra Informacion basica, Detalles del seguimiento y Archivo adjunto. | R | Ve todos (el listado no filtra por departamentos) | Módulo 06 — Actividad 1 |
| Informes de seguimiento | Descargar el PDF del informe de seguimiento (F-ISE-04) 👁 | Descarga el archivo del informe. | Archivo | Ve todos (el listado no filtra por departamentos) | Módulo 06 — Actividad 1 |
| Oficios de consumación | Listar los oficios de consumación (F-OFI-01) 👁 | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Ve todos (el listado no filtra por departamentos) | Módulo 07 — Actividad 1 |
| Oficios de consumación | Buscar y filtrar oficios por alerta (F-OFI-02) 👁 | Busca por radicado y filtra por Alerta asociada. | R | Ve todos (el listado no filtra por departamentos) | Módulo 07 — Actividad 1 |
| Oficios de consumación | Ver el detalle de un oficio (F-OFI-03) 👁 | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Ve todos (el listado no filtra por departamentos) | Módulo 07 — Actividad 1 |
| Oficios de consumación | Descargar el PDF del oficio (F-OFI-04) 👁 | Descarga el archivo del oficio. | Archivo | Ve todos (el listado no filtra por departamentos) | Módulo 07 — Actividad 1 |
| Interoperabilidad X-Road (SISAT) | Recibir alertas tempranas por X-Road (F-INT-01) 👁 | SISAT envía la alerta con sus municipios y recomendaciones; el sistema crea la alerta y las recomendaciones automáticas y notifica a las entidades. | Automática | Ve el resultado en Alertas tempranas (modo de creación automático) | Módulo 03 — Actividad 1 |
| Interoperabilidad X-Road (SISAT) | Recibir informes de seguimiento por X-Road (F-INT-02) 👁 | SISAT envía informes de seguimiento, que pueden cerrar la alerta o modificarla. | Automática | Ve el resultado en Informes de seguimiento | Módulo 06 — Actividad 1 |
| Interoperabilidad X-Road (SISAT) | Recibir oficios de consumación por X-Road (F-INT-03) 👁 | SISAT envía oficios de consumación. | Automática | Ve el resultado en Oficios de consumación | Módulo 07 — Actividad 1 |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01) 👁 | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Ve el resultado en Seguimiento | Módulo 05 — Actividad 2 |
| Tareas programadas | Recalcular estados y porcentajes de cumplimiento (F-TAR-03) 👁 | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Ve los estados y porcentajes recalculados | Módulo 02 — Actividad 1; Módulo 05 — Actividad 2 |
| Tareas programadas | Calcular el próximo informe al aprobar un informe (F-TAR-04) 👁 | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Ve los estados y porcentajes recalculados | Módulo 05 — Actividad 2 |

### Qué NO puede hacer el usuario de Consulta — Departamentos

| Módulo | Funcionalidad | Definición | Cómo lo impide el sistema | Qué hacer si lo necesita |
|---|---|---|---|---|
| Acceso a la plataforma | Cambiar la contraseña con la contraseña actual (F-ACC-11) ✖ | Servicio del servidor para cambiar la contraseña indicando la actual. Existe en la API, pero ninguna pantalla lo usa. | UI: no existe una pantalla que use este servicio (`main-api/CipratApi/Controladores/AutenticacionControlador.cs:147`; solo `dashboard/src/contexts/AuthContext.tsx` lo referencia) | Use **¿Has olvidado tu contraseña?** para cambiarla |
| Acceso a la plataforma | Editar los datos del propio perfil (F-ACC-13) ✖ | Servicio del servidor para actualizar los datos del propio usuario. En la pantalla Mi perfil los campos están deshabilitados. | UI: los campos de Mi perfil están deshabilitados (`dashboard/src/pages/MyProfile.tsx:124-183`) | Pida el cambio a quien administra los usuarios (Super Administrador o Administrador) |
| Acceso a la plataforma | Consultar el historial de cambios de contraseña (F-ACC-14) ✖ | Servicio del servidor que informa la fecha y el método del último cambio de contraseña. Ninguna pantalla lo muestra. | UI: el hook `usePasswordHistory` existe, pero Mi perfil no lo muestra (`dashboard/src/hooks/usePasswordHistory.ts:20`, `dashboard/src/pages/MyProfile.tsx`) | No disponible en la interfaz |
| Notificaciones | Recibir el correo de recomendación asignada (F-NOT-07) ✖ | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" a las entidades principal y asociadas. | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte las recomendaciones en la plataforma |
| Notificaciones | Recibir el correo de recomendación actualizada (F-NOT-08) ✖ | Correo "SI-CIPRAT - Recomendacion Actualizada: {código}". | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte el historial de la alerta |
| Notificaciones | Recibir el correo de validación del plan de acción (F-NOT-09) ✖ | Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" cuando se confirma el plan. | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte el estado del plan en Seguimiento o Planes de acción |
| Notificaciones | Recibir el recordatorio de informe de ejecución (F-NOT-10) ✖ | Correo "Recordatorio vencimiento plazo presentación de informe de ejecución - Alerta Temprana N° {número}" cuando faltan 30 días o menos. | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte la columna "Próximo Informe" |
| Notificaciones | Recibir el correo de informe de seguimiento (F-NOT-11) ✖ | Correo "Notificación informe de seguimiento – Alerta Temprana N° {número}". | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte *Informes de seguimiento* |
| Notificaciones | Recibir el correo de oficio de consumación (F-NOT-12) ✖ | Correo "Notificación Oficio de Consumación – Alerta(s) Temprana(s) N° {números} en sistema SI-CIPRAT". | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte *Oficios de consumación* |
| Notificaciones | Recibir el correo de reporte de ejecución pendiente (F-NOT-13) ✖ | Correo "Reporte de ejecución pendiente de su aprobación – SI-CIPRAT" al aprobador designado. | Regla: solo usuarios activos con permiso de aprobar reportes pueden ser aprobadores (`main-api/CipratApi/Servicios/BusquedaUsuariosServicio.cs:223-235`) | El aprobador designado (Líder de Macrozona o Super Administrador) |
| Usuarios y entidades | Listar usuarios e invitaciones (F-USU-01) ✖ | Muestra los usuarios activos e inactivos y las invitaciones, con las pestañas Todos, Entidades Territoriales, Administradores, Monitores e Invitaciones. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Buscar y filtrar usuarios (F-USU-02) ✖ | Busca por nombre y filtra por Rol, Nivel, Estado y Categoría. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Ver el detalle de un usuario (F-USU-03) ✖ | Muestra "Información de Usuario": rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, apellidos, cargo y correo. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Invitar un usuario (F-USU-04) ✖ | Crea el usuario con su rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, cargo y correo, y le envía la invitación. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Invitar un Super Administrador (F-USU-05) ✖ | Crea otro usuario con rol Super Administrador. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador |
| Usuarios y entidades | Editar un usuario (F-USU-06) ✖ | Cambia los datos del usuario (incluido el rol y su alcance) desde el detalle. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Activar o inactivar un usuario (F-USU-07) ✖ | Cambia el interruptor **Activo** del usuario: un usuario inactivo no puede iniciar sesión. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Reenviar una invitación (F-USU-08) ✖ | Genera un enlace nuevo y vuelve a enviar el correo de invitación. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Eliminar una invitación (F-USU-09) ✖ | Elimina una invitación que no ha sido aceptada. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Listar entidades centrales y subdirecciones (F-USU-10) ✖ | Muestra las entidades con las vistas **Centrales** y **Subdirecciones**: nombre, subdirecciones, usuarios, categoría y fecha de creación. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Buscar y filtrar entidades (F-USU-11) ✖ | Busca por nombre y filtra por Categoría. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Ver el detalle de una entidad (F-USU-12) ✖ | Muestra la entidad central, su categoría y sus subdirecciones, con búsqueda. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Ver los usuarios asignados a una entidad (F-USU-13) ✖ | Al pasar el cursor sobre el número de usuarios muestra hasta 5 usuarios asignados. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Agregar una entidad con sus subdirecciones (F-USU-14) ✖ | Crea una entidad central con su categoría y, si aplica, sus subdirecciones. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Editar una entidad y sus subdirecciones (F-USU-15) ✖ | Cambia el nombre o la categoría y agrega o elimina subdirecciones. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Usuarios y entidades | Eliminar una entidad (F-USU-16) ✖ | Elimina una entidad que no tiene usuarios, subdirecciones, alertas ni recomendaciones. | UI y API: sin menú, `AdminRoute` y `RequireAdmin` (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `main-api/CipratApi/Controladores/PerfilControlador.cs:178-179`) | Super Administrador o Administrador |
| Agentes IA | Crear una alerta desde PDF con el Agente IA (F-AGE-01) ✖ | Envía el PDF de la alerta al agente, que extrae los datos y crea la alerta en estado Borrador. | UI y API: sin menú *Agentes* y `RequireSuperAdmin` (`dashboard/src/components/layout/Sidebar.tsx:75`, `main-api/CipratApi/Controladores/AlertasControlador.cs:409-410,1322-1323`) | Super Administrador |
| Agentes IA | Consultar el Historial de Procesamiento (F-AGE-02) ✖ | Lista los eventos del agente: Fecha, Evento (PDF Enviado, Alerta Creada, Error, Entidad No Encontrada, Municipio No Encontrado), Mensaje y Archivo / Alerta. | UI y API: sin menú *Agentes* y `RequireSuperAdmin` (`dashboard/src/components/layout/Sidebar.tsx:75`, `main-api/CipratApi/Controladores/AlertasControlador.cs:409-410,1322-1323`) | Super Administrador |
| Alertas tempranas | Reportar una alerta temprana (F-ALE-08) ✖ | Registra manualmente una alerta en 6 pasos (Información general, Lugar de advertencia, Conflicto, Conductas vulneratorias, Población afectada, Subsunción) y la deja Activa. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador o Administrador |
| Alertas tempranas | Adjuntar el PDF de la alerta y el Adjunto (F-ALE-09) ✖ | Sube el "PDF de la alerta" y un "Adjunto" (solo PDF, hasta 20 MB) al crear o editar la alerta. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador |
| Alertas tempranas | Editar una alerta (F-ALE-10) ✖ | Modifica los datos de la alerta en el mismo formulario de 6 pasos. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador o Administrador |
| Alertas tempranas | Cambiar el número de una alerta manual (F-ALE-11) ✖ | Edita el campo "Número y fecha de alerta" de una alerta creada manualmente. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador |
| Alertas tempranas | Publicar una alerta en borrador (F-ALE-12) ✖ | Al guardar la edición con "Publicar alerta al guardar" activo, la alerta pasa de Borrador a Activa. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador o Administrador |
| Alertas tempranas | Subsumir otras alertas (F-ALE-13) ✖ | Marca alertas existentes como subsumidas por la alerta que se registra o edita; las subsumidas pasan a Cerrada. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador o Administrador |
| Alertas tempranas | Eliminar una alerta (F-ALE-14) ✖ | Elimina (borrado lógico) una alerta. Para el Super Administrador el sistema no aplica las reglas de estado: puede eliminar alertas automáticas, con recomendaciones, cerradas o con plan confirmado. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador |
| Alertas tempranas | Reemplazar o eliminar los archivos de la alerta (F-ALE-15) ✖ | En la edición, quita el PDF o el adjunto existente y sube uno nuevo. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador |
| Alertas tempranas | Cerrar alertas (F-ALE-16) ✖ | Cierra una o varias alertas activas con el consecutivo y la fecha de notificación del informe de la Defensoría, y opcionalmente su PDF. | UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`) | Super Administrador |
| Recomendaciones | Agregar una recomendación (F-REC-05) ✖ | Registra en 2 pasos el eje temático, la descripción, una o varias entidades principales y sus entidades asociadas; se crea una recomendación por cada entidad principal. | UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`) | Super Administrador o Administrador |
| Recomendaciones | Editar una recomendación (F-REC-06) ✖ | Modifica eje, descripción y entidades. | UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`) | Super Administrador o Administrador |
| Recomendaciones | Eliminar una recomendación (F-REC-07) ✖ | Elimina (borrado lógico) una recomendación de una alerta abierta cuyo plan no está confirmado. El servidor no verifica si la recomendación es automática ni si tiene actividades. | UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`) | Super Administrador |
| Planes de acción | Listar las alertas con plan de acción (F-PLA-01) ✖ | Pestaña **Alertas**: por alerta muestra Ejecutado vs programado, % de cumplimiento, estado del Plan de acción y estado del Informe. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Buscar y filtrar planes de acción (F-PLA-02) ✖ | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento (0-30, 31-50, 51-80, 81-100). | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Ver el detalle y el historial del plan de una alerta (F-PLA-03) ✖ | Abre la ficha con "Información de alerta" e "Historial Plan de acción". | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Descargar el listado de planes (CSV) (F-PLA-04) ✖ | Descarga Número de Alerta, Cumplimiento (%) y Plan de Acción de las alertas visibles. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Ver las recomendaciones del plan de una alerta (F-PLA-05) ✖ | Desde **Ir al plan de acción**, lista las recomendaciones con Actividades (Aprobadas / Total) y Ejecución; **Ver Actividades** abre las actividades. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Consultar la pestaña global de Recomendaciones (F-PLA-06) ✖ | Pestaña **Recomendaciones** con todas las recomendaciones del alcance, filtros (alerta, eje, entidad) y descarga. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Consultar la pestaña global de Actividades (F-PLA-07) ✖ | Pestaña **Actividades** con todas las actividades del alcance: Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe, Próximo Informe; filtros y descarga. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Listar las actividades de una recomendación (F-PLA-08) ✖ | Muestra Actividad, Objetivo, Descripción, Número Actividades, Ejecución (Ejecutadas / Programadas), Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; busca por objetivo y filtra por Estado, Instrumento de Planeación y Recursos. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Ver el detalle de una actividad (F-PLA-09) ✖ | Abre "Detalle de Actividad": Recomendación, campos de la actividad, Estado Informe, Ejecución y Próximo Informe. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Descargar las actividades (CSV) (F-PLA-10) ✖ | Descarga Número de Alerta, Código de Recomendación, Objetivo, Descripción, Número de Actividades, Plazo, Instrumento, Recursos, Estado, Observaciones y fechas. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Agregar una actividad (F-PLA-11) ✖ | Registra en 2 pasos el Objetivo y la información de la actividad (Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos, Observaciones). | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable de la recomendación |
| Planes de acción | Agregar una actividad a un plan confirmado (F-PLA-12) ✖ | Si el plan ya está confirmado, el sistema advierte "Agregar actividad a plan confirmado" y, al continuar, desconfirma el plan. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable |
| Planes de acción | Editar una actividad (F-PLA-13) ✖ | Modifica los campos de una actividad pendiente de aprobación. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable |
| Planes de acción | Eliminar una actividad (F-PLA-14) ✖ | Elimina una actividad pendiente de aprobación. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable |
| Planes de acción | Ver y escribir comentarios de una actividad (F-PLA-15) ✖ | Abre la conversación de la actividad y agrega comentarios (hasta 2.000 caracteres). | UI: el botón **Comentarios** solo aparece a quien formula actividades en Planes de acción o aprueba en Seguimiento (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:395-510`, `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:569-711`); la API sí lo permitiría (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:77-83`) | La Entidad Territorial, el Monitor o el Líder de Macrozona |
| Planes de acción | Eliminar un comentario propio (F-PLA-16) ✖ | Servicio del servidor que permite al autor eliminar su comentario. La ventana de comentarios no tiene esa opción. | UI: la ventana "Comentarios" no ofrece eliminar (`dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`); la API lo permite al autor (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:140`) | No disponible en la interfaz |
| Planes de acción | Reportar un informe de ejecución (F-PLA-17) ✖ | Registra lo ejecutado en el ciclo: actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades y el PDF de soporte. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable |
| Planes de acción | Editar un informe de ejecución pendiente (F-PLA-18) ✖ | Corrige el informe y su PDF mientras no esté aprobado. | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | La Entidad Territorial responsable |
| Planes de acción | Consultar los informes de ejecución y descargar su PDF (F-PLA-19) ✖ | En el detalle de la recomendación (pestaña de actividades) muestra "Informes de ejecución" con todos sus campos y el archivo "Informe.pdf". | UI: el menú no muestra *Planes de acción* (`dashboard/src/components/layout/Sidebar.tsx:50-55`); consulta esta información en *Seguimiento* | Consúltelo en *Seguimiento* |
| Planes de acción | Eliminar un informe de ejecución (F-PLA-20) ✖ | La matriz de permisos define el permiso, pero no existe servicio ni botón para eliminar informes de ejecución. | NO ENCONTRADO: no hay endpoint DELETE en `main-api/CipratApi/Controladores/InformesEjecucionControlador.cs` aunque `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191` define `EliminarInformeEjecucion` | Corrija el informe con **Editar Informe** mientras esté pendiente |
| Seguimiento | Marcar una actividad como revisada (F-SEG-05) ✖ | Deja constancia (usuario y fecha) de que revisó la actividad; no cambia su estado. | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar una actividad (F-SEG-06) ✖ | Aprueba la actividad pendiente; si es la última pendiente, la recomendación y el plan pasan a Aprobado. | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Descartar la aprobación de una actividad (F-SEG-07) ✖ | Devuelve una actividad aprobada a "Pendiente de aprobación". | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Validar si el plan se puede confirmar (F-SEG-08) ✖ | Al abrir la confirmación, el sistema muestra el resumen (Total de recomendaciones, de actividades y de actividades programadas) o lo que falta ("El plan de acción tiene N actividades pendientes de aprobación y N recomendaciones sin actividades"). | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Confirmar el plan de acción (F-SEG-09) ✖ | Confirma el plan completo de la alerta cuando todas sus actividades están aprobadas; habilita los informes de ejecución y notifica a las entidades. | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar un informe de ejecución (F-SEG-10) ✖ | Aprueba el informe pendiente y el sistema fija la fecha del próximo informe. | UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Informe de recomendaciones | Consultar el Informe de recomendaciones (F-IRE-01) ✖ | Tablero con Información alertas, Información recomendaciones, Información actividades y Cumplimiento por Entidad Principal y por Eje Temático. | API: `RequireReportes` y sin menú *Planes de acción* (`main-api/CipratApi/Controladores/ReportesControlador.cs:39-40`) | Pida el consolidado a un Monitor, Líder de Macrozona o Administrador |
| Informe de recomendaciones | Filtrar el Informe de recomendaciones por alerta (F-IRE-02) ✖ | Cambia el consolidado de "Todas las alertas" a una alerta. | API: `RequireReportes` y sin menú *Planes de acción* (`main-api/CipratApi/Controladores/ReportesControlador.cs:39-40`) | Pida el consolidado a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Listar los reportes de ejecución (F-REP-01) ✖ | Pantalla "Reportes de ejecución" con las pestañas Todos, Alerta, Entidad y Regional y la tabla Informe, Tipo, Publicado, Estado y Aprobador. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Buscar y filtrar reportes (F-REP-02) ✖ | Busca por nombre y filtra por Tipo, Estado, Alerta asociada, Entidad, Departamento y Municipio. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Ver el detalle de un reporte (F-REP-03) ✖ | Muestra Nombre del reporte, Etiqueta (tipo), Fecha de publicacion, Estado, Descripcion, Adjunto y Aprobador. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Descargar un reporte (F-REP-04) ✖ | Descarga el PDF del reporte. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Cargar un reporte de ejecución (F-REP-05) ✖ | Registra el tipo (Alerta, Entidad, Depto, Municipio), su alcance, la fecha, el aprobador, la descripción y el PDF. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Editar un reporte de ejecución (F-REP-06) ✖ | Modifica los datos o el PDF del reporte desde su detalle. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Eliminar un reporte de ejecución (F-REP-07) ✖ | Elimina un reporte que no está aprobado. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Super Administrador |
| Reportes | Aprobar un reporte de ejecución (F-REP-08) ✖ | El aprobador designado aprueba el reporte. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | El aprobador designado (Líder de Macrozona o Super Administrador) |
| Reportes | Generar un informe ejecutivo en Word (Panel de consultas) (F-REP-09) ✖ | Genera y descarga un documento Word por Alerta, Entidad, Depto, Municipio o General. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Informes de seguimiento | Cargar un informe de seguimiento (F-ISE-05) ✖ | Registra en 2 pasos el número, la alerta, las fechas, el radicado y el PDF, y las modificaciones a la alerta. | UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`) | Super Administrador o Administrador |
| Informes de seguimiento | Modificar municipios y agregar recomendaciones desde el informe (F-ISE-06) ✖ | En el paso 2 marca municipios como cerrados, agrega municipios y agrega recomendaciones nuevas. | UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`) | Super Administrador o Administrador |
| Informes de seguimiento | Cerrar la alerta con el informe de seguimiento (F-ISE-07) ✖ | Marca "Cerrar la alerta con este informe" para que la alerta quede Cerrada al guardar. | UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`) | Super Administrador |
| Informes de seguimiento | Editar un informe de seguimiento (F-ISE-08) ✖ | Modifica los datos del informe (la alerta asociada no se cambia). | UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`) | Super Administrador o Administrador |
| Informes de seguimiento | Eliminar un informe de seguimiento (F-ISE-09) ✖ | Elimina un informe cuya alerta no está cerrada. | UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`) | Super Administrador |
| Oficios de consumación | Cargar un oficio de consumación (F-OFI-05) ✖ | Registra en 2 pasos el radicado, las fechas, el tema clave, las alertas asociadas y el PDF, y las modificaciones por alerta. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Modificar municipios y agregar recomendaciones desde el oficio (F-OFI-06) ✖ | Para cada alerta asociada, marca municipios como cerrados, agrega municipios y agrega recomendaciones. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Editar un oficio de consumación (F-OFI-07) ✖ | Modifica los datos del oficio. | UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`) | Super Administrador |
| Oficios de consumación | Eliminar un oficio de consumación (F-OFI-08) ✖ | Elimina el oficio. | UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`) | Super Administrador |
| Interoperabilidad X-Road (SISAT) | Entregar el plan estratégico a la Defensoría (F-INT-04) ✖ | La Defensoría consulta por X-Road el plan de acción de una alerta. | Proceso entre sistemas con llave de API X-Road; no es una acción de usuario (`main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:720`) | Lo ejecuta la Defensoría por X-Road |
| Interoperabilidad X-Road (SISAT) | Entregar archivos a la Defensoría (F-INT-05) ✖ | La Defensoría descarga por X-Road archivos de SI-CIPRAT. | Proceso entre sistemas con llave de API X-Road; no es una acción de usuario (`main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:762`) | Lo ejecuta la Defensoría por X-Road |
| Tareas programadas | Enviar el recordatorio de informe de ejecución (F-TAR-02) ✖ | Cada día a las 00:01 envía el recordatorio cuando faltan 30 días o menos para el próximo informe (una vez por ciclo). | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte la columna "Próximo Informe" |

## Segmentación de visualización

- **Inicio:** indicadores, ranking, alertas recientes y mapa calculados sobre las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`) (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores.
- **Alertas tempranas:** ve las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`).
- **Recomendaciones de una alerta:** ve todas las recomendaciones de cada alerta que está en su alcance.
- **Planes de acción:** no aparece en su menú (`dashboard/src/components/layout/Sidebar.tsx:50-55`).
- **Seguimiento:** ve los planes de las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`).
- **Reportes:** no tiene acceso (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`).
- **Informes de seguimiento:** ve todos los registrados en el país: este listado no aplica el filtro por departamentos (`main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:266-279`).
- **Oficios de consumación:** ve todos los registrados en el país: este listado no aplica el filtro por departamentos (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`).
- **Notificaciones (panel):** ve el historial de actividad de las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`) (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`).
- **Usuarios y entidades:** no aparece en su menú (`dashboard/src/components/layout/Sidebar.tsx:38-42`).

## Ruta de aprendizaje

### Módulo 00 — Contexto de la plataforma SI-CIPRAT

**Prerrequisitos:** Ninguno.

**Definición del módulo:** Módulo introductorio que presenta qué es SI-CIPRAT, quiénes intervienen, cómo avanza una alerta temprana de la fase E0 a la E6 y qué papel cumple el usuario de Consulta — Departamentos en ese ciclo.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda explicar qué es SI-CIPRAT, cómo avanza una alerta de E0 a E6 y en qué momentos interviene su rol.

**Contexto del módulo:** Antes de operar, el usuario de Consulta — Departamentos necesita entender en qué parte del ciclo actúa, qué recibe de otros actores y qué entrega, porque el sistema le habilita o le bloquea acciones según el estado de cada alerta, recomendación, actividad e informe.

**Funcionalidades disponibles:** Ninguna funcionalidad del sistema (módulo conceptual).

#### Actividad 1 — Conocer qué es SI-CIPRAT y para qué existe

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda explicar qué es SI-CIPRAT, a qué institución sirve y qué componentes tiene.

**Pasos:**

##### Paso 1.1 — Leer el propósito de la plataforma
**Objetivo del paso:** Entender para qué existe el sistema.
**Qué hacer:** Lea: SI-CIPRAT es el Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT), del Ministerio del Interior. Registra las alertas tempranas que emite la Defensoría del Pueblo, las recomendaciones que se derivan de ellas, los planes de acción con que las entidades responden y los informes de su ejecución, hasta el cierre de la alerta.
**Resultado esperado:** Puede explicar en una frase para qué sirve la plataforma.

##### Paso 1.2 — Identificar a los actores institucionales
**Objetivo del paso:** Saber quién hace qué fuera y dentro del sistema.
**Qué hacer:** Distinga: la Defensoría del Pueblo emite las alertas, los informes de seguimiento y los oficios de consumación (no es usuario de SI-CIPRAT: su información llega por X-Road o la registra el Ministerio); la Secretaría Técnica de la CIPRAT administra la plataforma, registra y supervisa; las entidades responsables formulan y ejecutan los planes.
**Resultado esperado:** Identifica a la Defensoría, la Secretaría Técnica y las entidades.

##### Paso 1.3 — Reconocer los componentes del sistema
**Objetivo del paso:** Saber de dónde viene la información que verá.
**Qué hacer:** Identifique: la aplicación web (dashboard), el servicio de la API, la interoperabilidad X-Road con SISAT, el Agente IA que lee PDF y las tareas programadas diarias (00:01) que manejan los vencimientos de informes y los recordatorios.
**Resultado esperado:** Sabe que algunas alertas y recomendaciones llegan solas ("Automática") y que hay procesos que corren cada noche.

#### Actividad 2 — Comprender los actores y el ciclo de vida de una alerta temprana (E0–E6), incluidos los puntos donde el código muestra que el flujo sale de la plataforma

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda describir las fases E0 a E6 del ciclo de una alerta, sus actores y los puntos donde el flujo sale de la plataforma.

Puntos donde el flujo sale de la plataforma (solo lo que muestra el código):

| Secuencia | Acción | ⤴ Qué ocurre por fuera y qué vuelve | Evidencia |
|---|---|---|---|
| E1.1 | Envío de la alerta por X-Road (con sus recomendaciones) | La alerta se emite en el sistema de la Defensoría y llega por X-Road | main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:603-614 |
| E1.2 | Crear Alerta desde PDF (Agente IA) | El PDF llega por fuera de la plataforma | main-api/CipratApi/Controladores/AlertasControlador.cs:409-489 |
| E1.3 | Reportar alerta › Enviar Alerta (6 pasos) | El documento de la alerta llega por fuera de la plataforma | main-api/CipratApi/Controladores/AlertasControlador.cs:336-387 |
| E2.2 | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" | El correo se recibe fuera de la plataforma; la respuesta vuelve como actividades | main-api/CipratApi/Servicios/EmailService.cs:151 |
| E4.1 | Revisar: Comentarios y Marcar como Revisado | Las mesas técnicas de revisión, si existen, ocurren por fuera; vuelven como comentarios y aprobaciones | main-api/CipratApi/Controladores/RevisionesActividadControlador.cs:77-100 |
| E5.1 | Reportar Informe › Reportar informe de ejecución (con PDF) | El soporte de la ejecución se produce por fuera; vuelve como PDF | main-api/CipratApi/Controladores/InformesEjecucionControlador.cs:35-41 |
| E6.1 | Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) | El informe lo emite la Defensoría por fuera (o llega por X-Road) | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:185-265 |
| E6.2 | Cargar oficio de consumación | El oficio lo emite la Defensoría por fuera (o llega por X-Road) | main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:182-238 |
| E6.3 | Cerrar alertas | La decisión de cierre se toma por fuera; vuelve con el consecutivo y el PDF | main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:88-125 |

**Pasos:**

##### Paso 2.1 — Fase E0: Preparación del sistema (usuarios y entidades)
**Objetivo del paso:** Ubicar qué ocurre en la fase E0.
**Qué hacer:** E0.1 Agregar Entidad (entidad central y subdirecciones) (Super Administrador, Administrador); E0.2 Enviar invitación (rol, nivel de acceso, entidad, subdirección, departamentos, cargo) (Super Administrador, Administrador); E0.3 Activar cuenta (crear contraseña) (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial — Central, Entidad Territorial — Subdirección, Consulta — Global, Consulta — Entidad, Consulta — Departamentos); E0.4 Iniciar Sesión y Validar código (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial — Central, Entidad Territorial — Subdirección, Consulta — Global, Consulta — Entidad, Consulta — Departamentos); E0.5 Editar usuario, activar o inactivar, Reenviar o Eliminar invitación (Super Administrador, Administrador); E0.6 ¿Has olvidado tu contraseña? › Restablecer contraseña (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial — Central, Entidad Territorial — Subdirección, Consulta — Global, Consulta — Entidad, Consulta — Departamentos).
**Resultado esperado:** Reconoce las acciones de la fase E0 y quién las hace.

##### Paso 2.2 — Fase E1: Registro de la alerta
**Objetivo del paso:** Ubicar qué ocurre en la fase E1.
**Qué hacer:** E1.1 Envío de la alerta por X-Road (con sus recomendaciones) (Defensoría, Sistema); E1.2 Crear Alerta desde PDF (Agente IA) (Super Administrador); E1.3 Reportar alerta › Enviar Alerta (6 pasos) (Super Administrador, Administrador); E1.4 Adjuntar "PDF de la alerta" y "Adjunto" (Super Administrador); E1.5 Editar alerta y Publicar alerta al guardar (Super Administrador, Administrador); E1.6 Esta alerta subsume otras alertas (Super Administrador, Administrador); E1.7 Eliminar alerta (Super Administrador); E1–E6 Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial — Central, Entidad Territorial — Subdirección, Consulta — Global, Consulta — Entidad, Consulta — Departamentos).
**Resultado esperado:** Reconoce las acciones de la fase E1 y quién las hace.

##### Paso 2.3 — Fase E2: Recomendaciones
**Objetivo del paso:** Ubicar qué ocurre en la fase E2.
**Qué hacer:** E2.1 Agregar recomendación › Crear recomendación (Super Administrador, Administrador); E2.2 Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" (Sistema, Entidad Territorial — Central, Entidad Territorial — Subdirección); E2.3 Editar recomendación (Super Administrador, Administrador); E2.4 Eliminar recomendación (Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E2 y quién las hace.

##### Paso 2.4 — Fase E3: Plan de acción (formulación)
**Objetivo del paso:** Ubicar qué ocurre en la fase E3.
**Qué hacer:** E3.1 Consultar las recomendaciones asignadas (Ir al plan de acción) (Entidad Territorial — Central, Entidad Territorial — Subdirección); E3.2 Agregar actividad › Reportar actividad (Entidad Territorial — Central, Entidad Territorial — Subdirección, Super Administrador); E3.3 Editar Actividad / Eliminar Actividad (Entidad Territorial — Central, Entidad Territorial — Subdirección, Super Administrador); E3.4 Comentarios de la actividad (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial — Central, Entidad Territorial — Subdirección, Consulta — Global, Consulta — Entidad, Consulta — Departamentos).
**Resultado esperado:** Reconoce las acciones de la fase E3 y quién las hace.

##### Paso 2.5 — Fase E4: Aprobación y confirmación del plan
**Objetivo del paso:** Ubicar qué ocurre en la fase E4.
**Qué hacer:** E4.1 Revisar: Comentarios y Marcar como Revisado (Monitor, Líder de Macrozona, Super Administrador); E4.2 Aprobar / Descartar aprobación (Monitor, Líder de Macrozona, Super Administrador); E4.3 Confirmar Plan de Acción (Monitor, Líder de Macrozona, Super Administrador); E4.4 Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" (Sistema, Entidad Territorial — Central, Entidad Territorial — Subdirección); E4.5 Agregar actividad a plan confirmado › Continuar (Entidad Territorial — Central, Entidad Territorial — Subdirección, Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E4 y quién las hace.

##### Paso 2.6 — Fase E5: Informes de ejecución
**Objetivo del paso:** Ubicar qué ocurre en la fase E5.
**Qué hacer:** E5.1 Reportar Informe › Reportar informe de ejecución (con PDF) (Entidad Territorial — Central, Entidad Territorial — Subdirección, Super Administrador); E5.2 Editar Informe (Entidad Territorial — Central, Entidad Territorial — Subdirección, Super Administrador); E5.3 Aprobar Informe (Monitor, Líder de Macrozona, Super Administrador); E5.4 Correo "Recordatorio vencimiento plazo presentación de informe de ejecución" (Sistema, Entidad Territorial — Central, Entidad Territorial — Subdirección); E5.5 Tarea diaria 00:01: vencimiento del ciclo (Sistema); E5.6 Cargar informe (reporte de ejecución) con aprobador (Monitor, Líder de Macrozona, Administrador, Super Administrador); E5.7 Aprobar informe (reporte de ejecución) — solo el aprobador designado (Líder de Macrozona, Super Administrador); E5.8 Consultas › Generar consulta (informe ejecutivo Word) (Monitor, Líder de Macrozona, Administrador, Super Administrador); E5.9 Informe (Informe de recomendaciones) (Monitor, Líder de Macrozona, Administrador, Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E5 y quién las hace.

##### Paso 2.7 — Fase E6: Seguimiento y cierre
**Objetivo del paso:** Ubicar qué ocurre en la fase E6.
**Qué hacer:** E6.1 Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) (Super Administrador, Administrador, Defensoría); E6.2 Cargar oficio de consumación (Super Administrador, Defensoría); E6.3 Cerrar alertas (Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E6 y quién las hace.

##### Paso 2.8 — Identificar dónde el flujo sale de la plataforma
**Objetivo del paso:** Saber qué partes del proceso no quedan en el sistema.
**Qué hacer:** Lea los puntos marcados "⤴ El flujo continúa por fuera de la plataforma" en la tabla de esta actividad.
**Resultado esperado:** Identifica qué dato o archivo vuelve al sistema en cada punto.

#### Actividad 3 — Ubicar el papel de Consulta — Departamentos en el ciclo: su línea de tiempo

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda ubicar en qué momentos del ciclo actúa, qué espera de otros actores y qué entrega.

| Secuencia | Fase | Acción | Disparador | Plazo | Qué sigue y quién |
|---|---|---|---|---|---|
| E0.3 | Preparación del sistema (usuarios y entidades) | Activar cuenta (crear contraseña) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" | ≤ 7 días desde E0.2 | E0.4 el mismo usuario |
| E0.4 | Preparación del sistema (usuarios y entidades) | Iniciar Sesión y Validar código | E0.3 | Código válido 1 hora; sesión de 720 minutos; cierre a los 60 minutos de inactividad | Según el rol |
| E0.6 | Preparación del sistema (usuarios y entidades) | ¿Has olvidado tu contraseña? › Restablecer contraseña | El usuario olvidó la contraseña | Enlace válido 1 hora | E0.4 |
| E3.4 | Plan de acción (formulación) | Comentarios de la actividad | Actividad registrada | — | E3.3 o E4.2 |
| E1–E6 | Registro de la alerta | Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF | Desde E1 | Permanente | — |

**Pasos:**

##### Paso 3.1 — Leer su línea de tiempo
**Objetivo del paso:** Conocer sus momentos de intervención.
**Qué hacer:** Recorra la tabla de esta actividad en orden de secuencia.
**Resultado esperado:** Identifica sus 5 momentos de intervención.

##### Paso 3.2 — Identificar a quién espera
**Objetivo del paso:** Saber de qué depende para actuar.
**Qué hacer:** Lea la columna "Disparador" de cada fila.
**Resultado esperado:** Sabe qué debe haber pasado antes de cada acción.

##### Paso 3.3 — Identificar a quién entrega
**Objetivo del paso:** Saber qué sigue después de su acción.
**Qué hacer:** Lea la columna "Qué sigue y quién".
**Resultado esperado:** Sabe a qué actor le entrega el trabajo.

#### Actividad 4 — Conocer los módulos que usará y cómo está organizada esta ruta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda identificar los módulos de su ruta y la estructura de módulo, actividades y pasos.

| Módulo | Nombre | Objetivo |
|---|---|---|
| Módulo 01 | Acceso a la plataforma | Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. |
| Módulo 02 | Inicio | Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. |
| Módulo 03 | Alertas tempranas | Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. |
| Módulo 04 | Recomendaciones | Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. |
| Módulo 05 | Seguimiento | Revisar y aprobar el plan de acción y su ejecución, actividad por actividad, hasta confirmar el plan y aprobar cada informe. |
| Módulo 06 | Informes de seguimiento | Dejar en el sistema cada informe de seguimiento de la Defensoría y aplicar sus efectos sobre la alerta (municipios, recomendaciones nuevas o cierre). |
| Módulo 07 | Oficios de consumación | Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. |
| Módulo 08 | Notificaciones | Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. |
| Módulo 09 | Práctica con el caso AT-013-25 | Practicar todas las actividades de la ruta. |

**Pasos:**

##### Paso 4.1 — Revisar la lista de módulos
**Objetivo del paso:** Saber qué aprenderá.
**Qué hacer:** Lea la tabla de módulos de esta actividad.
**Resultado esperado:** Conoce los módulos y su objetivo.

##### Paso 4.2 — Entender la estructura de cada actividad
**Objetivo del paso:** Saber cómo leer la ruta.
**Qué hacer:** Cada actividad trae objetivo, requisitos previos (reglas RN-…), dónde, qué ve, campos, pasos con objetivo, resultado, escenarios de error, avisos ⚠️ y ejemplo.
**Resultado esperado:** Sabe dónde buscar cada tipo de información.

##### Paso 4.3 — Ubicar los bloques finales
**Objetivo del paso:** Saber dónde consultar dudas.
**Qué hacer:** Al final están Alcance y límites, Indicadores de logro, Preguntas frecuentes de uso, Errores frecuentes y cómo solucionarlos y el Glosario de la ruta.
**Resultado esperado:** Sabe dónde resolver dudas y problemas.

### Módulo 01 — Acceso a la plataforma

**Prerrequisitos:** Haber recibido el correo de invitación (lo envía el Super Administrador o el Administrador).

**Definición del módulo:** Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. También muestra los Términos de uso y el correo de soporte técnico.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda activar la cuenta desde la invitación; iniciar sesión con el código de verificación; recuperar la contraseña; cerrar sesión y entender el cierre automático; consultar los Términos de uso y contactar al soporte técnico; consultar Mi perfil y verificar el alcance asignado.

**Contexto del módulo:** Interviene en la preparación (E0.3 activación, E0.4 primer ingreso, E0.6 recuperación de la contraseña) y en cada sesión de trabajo. Recibe la invitación y los datos creados en *Usuarios y entidades* (E0.2, E0.5) y entrega al usuario la sesión con la que el sistema aplica su rol y su alcance de datos. Lo usan todos los roles y subroles, sin diferencias de alcance. Lo activan la invitación (enlace válido 7 días), el ingreso (código válido 1 hora) y la inactividad (60 minutos). Para el usuario de Consulta — Departamentos: en total, tiene 11 de las 14 funcionalidades del módulo; no tiene: cambiar la contraseña con la contraseña actual, editar los datos del propio perfil, consultar el historial de cambios de contraseña.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Iniciar sesión con correo y contraseña (F-ACC-01) | Verifica el correo y la contraseña y, si son correctos, envía al correo del usuario un código de verificación de 4 dígitos. | Estado | Módulo 01 — Actividad 2 |
| Validar el código de verificación (F-ACC-02) | Valida el código de 4 dígitos recibido por correo y abre la sesión con el rol y el alcance del usuario. | Estado | Módulo 01 — Actividad 2 |
| Reenviar el código de verificación (F-ACC-03) | Genera y envía un nuevo código de verificación cuando el anterior no llegó o venció. | Estado | Módulo 01 — Actividad 2 |
| Activar la cuenta desde la invitación (F-ACC-04) | Desde el enlace del correo de invitación, el usuario crea su contraseña y su cuenta pasa a Activo. | U | Módulo 01 — Actividad 1 |
| Solicitar el restablecimiento de la contraseña (F-ACC-05) | Envía al correo un enlace para crear una contraseña nueva. | U | Módulo 01 — Actividad 3 |
| Restablecer la contraseña con el enlace (F-ACC-06) | Crea una contraseña nueva que cumpla las reglas y no repita las 5 anteriores. | U | Módulo 01 — Actividad 3 |
| Cerrar sesión (F-ACC-07) | Termina la sesión del usuario desde el menú de su nombre. | Estado | Módulo 01 — Actividad 4 |
| Cierre automático de la sesión por inactividad o vencimiento (F-ACC-08) | Cierra la sesión tras 60 minutos sin actividad o cuando vence el token, y avisa con un mensaje. | Automática | Módulo 01 — Actividad 4 |
| Consultar los Términos de uso (F-ACC-09) | Muestra los términos y condiciones de uso de la plataforma, con el correo de soporte. | R | Módulo 01 — Actividad 5 |
| Contactar al soporte técnico (F-ACC-10) | Abre un correo dirigido a la cuenta de soporte de la plataforma. | R | Módulo 01 — Actividad 5 |
| Consultar Mi perfil (F-ACC-12) | Muestra los datos de la cuenta: Información General, Entidad y Acceso y Asignaciones. | R | Módulo 01 — Actividad 6 |
| Recibir el correo de invitación (F-NOT-04, módulo Notificaciones) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Módulo 01 — Actividad 1 |
| Recibir el correo con el código de verificación (F-NOT-05, módulo Notificaciones) | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Módulo 01 — Actividad 2 |
| Recibir el correo de restablecimiento de contraseña (F-NOT-06, módulo Notificaciones) | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Módulo 01 — Actividad 3 |

#### Actividad 1 — Activar la cuenta desde la invitación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

**Cuándo se hace y requisitos previos:** Secuencia E0.3.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para activar la cuenta, el enlace de invitación debe tener menos de 7 días y no haberse usado. | Revise la fecha del correo de invitación | Pedir que reenvíen la invitación (Super Administrador o Administrador) | RN-ACC-04 |
| La contraseña debe tener al menos 8 caracteres y al menos un carácter especial, y las dos casillas deben coincidir. | Los indicadores de la pantalla se marcan en verde | Escribir una contraseña que cumpla los indicadores de la pantalla (El propio usuario) | RN-ACC-05 |

**Dónde:** Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" › enlace › pantalla "Configura tu contraseña" (`/setup/:token`).

**Qué ve:** Una pantalla con el título "Configura tu contraseña" y el texto "Establece una contraseña para activar tu cuenta en la plataforma.", dos campos (**Nueva Contraseña** y **Confirmar Contraseña**), los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial", el botón **Activar cuenta** y el enlace "¿Necesita soporte técnico?".

**Campos a diligenciar — Activar la cuenta (Configura tu contraseña):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Nueva Contraseña (`newPassword`) | Sí | Texto oculto | Mínimo 8 caracteres y al menos un carácter especial | — | — | Prueba#2026 | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" |
| 2 | Confirmar Contraseña (`confirmPassword`) | Sí | Texto oculto | Igual a Nueva Contraseña | — | Nueva Contraseña | Prueba#2026 | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." |

- Campos que llena el sistema: El correo del usuario viene en el enlace.
- Campos que se bloquean: El enlace se invalida después de usarlo.
- Archivos: No aplica.
- Guardar o enviar con: **Activar cuenta**.

**Pasos:**

##### Paso 1.1 — Abrir el enlace de la invitación
**Objetivo del paso:** Llegar a la pantalla de activación con un enlace válido.
**Qué hacer:** Abra el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" y haga clic en el enlace. Hágalo antes de 7 días desde el envío.
**Resultado esperado:** Se abre "Configura tu contraseña". Si el enlace venció, aparece "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."

##### Paso 1.2 — Escribir la nueva contraseña
**Objetivo del paso:** Crear una contraseña que cumpla las reglas de seguridad.
**Qué hacer:** En **Nueva Contraseña** escriba al menos 8 caracteres e incluya un carácter especial (por ejemplo, # o !). Use el ícono del ojo para verificar lo escrito.
**Resultado esperado:** Los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial" se marcan como cumplidos.

##### Paso 1.3 — Confirmar la contraseña
**Objetivo del paso:** Evitar errores de digitación.
**Qué hacer:** En **Confirmar Contraseña** escriba exactamente la misma contraseña.
**Resultado esperado:** Si no coinciden, al enviar aparece "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."

##### Paso 1.4 — Activar la cuenta
**Objetivo del paso:** Dejar la cuenta en estado Activo.
**Qué hacer:** Revise que los dos campos coincidan y haga clic en **Activar cuenta**.
**Resultado esperado:** El botón muestra "Activando cuenta..." y luego la pantalla confirma; la cuenta queda Activa y puede iniciar sesión.

> 📷 **[CAPTURA MED-09-ACC-01]** — Pantalla "Configura tu contraseña"
> **Debe mostrar:** La pantalla de activación con los dos campos y los indicadores de la contraseña
> **Resaltar:** Campos Nueva Contraseña y Confirmar Contraseña; botón Activar cuenta
> **Pantalla / ruta:** `/setup/:token` (`dashboard/src/pages/auth/ResetPassword.tsx:198-317`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Invitación de prueba vigente
> **Texto alternativo:** Formulario para crear la contraseña y activar la cuenta

**Resultado de la actividad:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el enlace de invitación después de 7 días | "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador." | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Active la cuenta apenas reciba el correo. |
| Abrir un enlace de invitación incompleto o ya usado | "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada" | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | No copie el enlace a mano. |
| Crear una contraseña corta o sin símbolos | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña debe contener al menos un carácter especial") | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Revise los indicadores de la pantalla antes de enviar. |
| Escribir diferente la confirmación de la contraseña | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | — |

> 📷 **[CAPTURA MED-09-ACC-02]** — Mensaje ERR-ACC-06
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:319`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de invitación después de 7 días

> 📷 **[CAPTURA MED-09-ACC-03]** — Mensaje ERR-ACC-07
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:324`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un enlace de invitación incompleto o ya usado

> 📷 **[CAPTURA MED-09-ACC-04]** — Mensaje ERR-ACC-08
> **Debe mostrar:** La pantalla con el mensaje "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña d
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/utils/validation.ts:25-31`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Crear una contraseña corta o sin símbolos

> 📷 **[CAPTURA MED-09-ACC-05]** — Mensaje ERR-ACC-09
> **Debe mostrar:** La pantalla con el mensaje "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/auth/ResetPassword.tsx:101`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir diferente la confirmación de la contraseña

**⚠️ Atención:**
- ⚠️ El enlace vence a los 7 días y solo sirve una vez. Si vence, pida que le reenvíen la invitación.
- La contraseña es personal e intransferible (Términos de uso, numeral 4).

**Ejemplo:** Si la invitación se envió el lunes 2 de febrero de 2026, el enlace sirve hasta el lunes 9 de febrero de 2026.

#### Actividad 2 — Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.4.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para iniciar sesión, la cuenta debe estar en estado Activo. | Si puede ingresar, la cuenta está activa | Pedir la activación del usuario (Super Administrador o Administrador) | RN-ACC-01 |
| Para iniciar sesión, la entidad asignada al usuario debe estar activa. | Revise el estado o el dato en la pantalla antes de actuar | Revisar el estado de la entidad (Super Administrador o Administrador) | RN-ACC-02 |
| Para entrar, el código de verificación de 4 dígitos debe coincidir con el último enviado y tener menos de 1 hora. | Revise la hora del correo "SI-CIPRAT - Código de Verificación" | Usar el código del último correo o pedir uno nuevo con **Haz clic para reenviar** (El propio usuario) | RN-ACC-03 |

**Dónde:** Dirección de la plataforma › **Iniciar sesión** (`/signin`) › "Inicia sesión en tu cuenta".

**Qué ve:** Primera pantalla: "Sistema de Información de la Secretaría Técnica CIPRAT", "Inicia sesión en tu cuenta", campos **Correo electrónico** y **Contraseña**, enlace **¿Has olvidado tu contraseña?**, botón **Iniciar Sesión** y "¿Necesita soporte técnico?". Segunda pantalla: "Revisa tu correo electrónico", "Enviamos un enlace de verificación a {correo}", 4 casillas para el código, botón **Validar código** y "¿No recibiste el correo? **Haz clic para reenviar**".

**Campos a diligenciar — Iniciar sesión:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | — | — | consulta.departamentos.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" (mensajes en inglés de la pantalla) / "Credenciales inválidas" |
| 2 | Contraseña (`password`) | Sí | Texto oculto | La contraseña vigente | — | — | (contraseña personal) | "Password is required" / "Credenciales inválidas" |
| 3 | Código de verificación (4 casillas) (`auth_code`) | Sí | Número (4 dígitos, uno por casilla) | Solo dígitos 0-9; vigente 1 hora | — | Llega al correo después del paso 1 | 4821 | "Código de autenticación inválido" / "Código expirado" |

- Campos que llena el sistema: Ninguno.
- Campos que se bloquean: Ninguno.
- Archivos: No aplica.
- Guardar o enviar con: **Iniciar Sesión** y luego **Validar código**.

**Pasos:**

##### Paso 2.1 — Abrir la pantalla de ingreso
**Objetivo del paso:** Llegar al formulario de inicio de sesión.
**Qué hacer:** Abra la dirección de SI-CIPRAT en Chrome, Firefox o Edge actualizados y haga clic en **Iniciar sesión** (o abra directamente `/signin`).
**Resultado esperado:** Aparece "Inicia sesión en tu cuenta".

##### Paso 2.2 — Escribir correo y contraseña
**Objetivo del paso:** Identificarse ante el sistema.
**Qué hacer:** En **Correo electrónico** escriba su correo institucional (el mismo de la invitación). En **Contraseña** escriba su contraseña.
**Resultado esperado:** Los campos quedan diligenciados. Si están vacíos, la pantalla muestra "Email is required" o "Password is required".

##### Paso 2.3 — Solicitar el código
**Objetivo del paso:** Validar credenciales y recibir el código de verificación.
**Qué hacer:** Haga clic en **Iniciar Sesión**.
**Resultado esperado:** El botón muestra "Iniciando sesión..." y aparece "Revisa tu correo electrónico". Llega el correo "SI-CIPRAT - Código de Verificación". Si las credenciales no son correctas: "Credenciales inválidas".

##### Paso 2.4 — Escribir el código de 4 dígitos
**Objetivo del paso:** Comprobar que quien ingresa tiene acceso al correo.
**Qué hacer:** Abra el correo y escriba los 4 dígitos, uno en cada casilla (solo acepta números; puede pegarlos). Si no llegó, espere un minuto, revise el correo no deseado y haga clic en **Haz clic para reenviar**.
**Resultado esperado:** Las 4 casillas quedan llenas.

##### Paso 2.5 — Validar el código
**Objetivo del paso:** Abrir la sesión.
**Qué hacer:** Haga clic en **Validar código**.
**Resultado esperado:** Entra a **Inicio** con el menú lateral de su rol. Si el código no coincide: "Código de autenticación inválido"; si pasó más de 1 hora: "Código expirado".

> 🎞️ **[GIF MED-09-ACC-06]** — Ingreso con código de verificación
> **Debe mostrar:** El ingreso completo: correo y contraseña, pantalla "Revisa tu correo electrónico", escritura del código y llegada a Inicio
> **Resaltar:** Botones Iniciar Sesión y Validar código; enlace Haz clic para reenviar
> **Pantalla / ruta:** `/signin` (`dashboard/src/components/auth/LoginPanel.tsx`, `VerificationCodePanel.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Usuario de prueba del rol
> **Imagen existente:** Refenrence/img/Screenshot 2026-08-11 at 6.07.49 PM.png: sirve para el primer cuadro (pantalla "Inicia sesión en tu cuenta", igual para todos los roles). Debe actualizarse: muestra un correo personal real; tomarla de nuevo con consulta.departamentos.prueba@ejemplo.gov.co
> **Solo para GIF — Secuencia:** 1) Escribir correo y contraseña 2) Iniciar Sesión 3) Escribir el código 4) Validar código 5) Inicio · **Duración aproximada:** 20 segundos
> **Texto alternativo:** Animación del inicio de sesión con código de 4 dígitos

**Resultado de la actividad:** Sesión abierta con el rol el usuario de Consulta — Departamentos y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Escribir mal el correo o la contraseña | "Credenciales inválidas" | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | No comparta ni anote la contraseña en lugares visibles. |
| Escribir mal el código de 4 dígitos | "Código de autenticación inválido" | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Use siempre el código del correo más reciente. |
| Usar un código después de 1 hora | "Código expirado" | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Ingrese el código apenas llegue. |
| Ingresar con una cuenta inactivada | "Cuenta no activa" | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | — |
| No llega el correo con el código | No aparece mensaje: la pantalla "Revisa tu correo electrónico" queda esperando el código. | El correo puede estar en la carpeta de correo no deseado o tardar en llegar. | Revise la carpeta de correo no deseado; espere un minuto y use **Haz clic para reenviar**. | Agregue el remitente de SI-CIPRAT a sus contactos. |
| Se pierde la conexión a internet | "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo." | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Trabaje con conexión estable; los Términos de uso la exigen. |

> 📷 **[CAPTURA MED-09-ACC-07]** — Mensaje ERR-ACC-01
> **Debe mostrar:** La pantalla con el mensaje "Credenciales inválidas"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:132-141`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el correo o la contraseña

> 📷 **[CAPTURA MED-09-ACC-08]** — Mensaje ERR-ACC-02
> **Debe mostrar:** La pantalla con el mensaje "Código de autenticación inválido"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:81-84`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el código de 4 dígitos

> 📷 **[CAPTURA MED-09-ACC-09]** — Mensaje ERR-ACC-03
> **Debe mostrar:** La pantalla con el mensaje "Código expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:88-91,163`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar un código después de 1 hora

> 📷 **[CAPTURA MED-09-ACC-10]** — Mensaje ERR-ACC-04
> **Debe mostrar:** La pantalla con el mensaje "Cuenta no activa"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:144-148`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Ingresar con una cuenta inactivada

> 📷 **[CAPTURA MED-09-ACC-11]** — Mensaje ERR-GEN-06
> **Debe mostrar:** La pantalla con el mensaje "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:403`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Se pierde la conexión a internet

**⚠️ Atención:**
- El código vence 1 hora después de enviado; use siempre el del correo más reciente.
- Los mensajes de los campos vacíos de esta pantalla aparecen en inglés ("Email is required", "Please enter a valid email address", "Password is required").

**Ejemplo:** Si el código llega a las 8:05 a. m., sirve hasta las 9:05 a. m.

#### Actividad 3 — Recuperar la contraseña

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La contraseña debe tener al menos 8 caracteres y al menos un carácter especial, y las dos casillas deben coincidir. | Los indicadores de la pantalla se marcan en verde | Escribir una contraseña que cumpla los indicadores de la pantalla (El propio usuario) | RN-ACC-05 |
| Al restablecer la contraseña, no se puede repetir la actual ni ninguna de las últimas 5. | Revise el estado o el dato en la pantalla antes de actuar | Elegir una contraseña nueva (El propio usuario) | RN-ACC-06 |
| El enlace para restablecer la contraseña vence 1 hora después de enviado. | Revise el estado o el dato en la pantalla antes de actuar | Solicitar un enlace nuevo (El propio usuario) | RN-ACC-07 |

**Dónde:** Pantalla de ingreso › **¿Has olvidado tu contraseña?** (`/forgot-password`) › correo "SI-CIPRAT - Restablecer Contraseña" › "Configurar nueva contraseña" (`/reset-password/:token`).

**Qué ve:** Primera pantalla: "¿Olvidaste tu contraseña?", "No te preocupes, te enviaremos las instrucciones para restablecerla.", campo **Correo electrónico** y botón **Restablecer contraseña**. Después: "Revisa tu correo electrónico — Hemos enviado un enlace para restablecer la contraseña a {correo}". En el enlace: "Configurar nueva contraseña", "Tu nueva contraseña debe ser diferente a las contraseñas usadas anteriormente.", campos **Nueva Contraseña** y **Confirmar Contraseña** y botón **Restablecer contraseña**.

**Campos a diligenciar — Solicitar el restablecimiento:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | — | — | consulta.departamentos.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" |

- Campos que llena el sistema: —
- Campos que se bloquean: —
- Archivos: No aplica.
- Guardar o enviar con: **Restablecer contraseña**.

**Campos a diligenciar — Configurar nueva contraseña:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Nueva Contraseña (`newPassword`) | Sí | Texto oculto | Mínimo 8 caracteres, un carácter especial, distinta de las 5 anteriores | — | — | Nueva#2026 | "Debe tener al menos 8 caracteres" / "No puedes reutilizar ninguna de tus últimas 5 contraseñas" |
| 2 | Confirmar Contraseña (`confirmPassword`) | Sí | Texto oculto | Igual a Nueva Contraseña | — | Nueva Contraseña | Nueva#2026 | "Las contraseñas ingresadas no son iguales…" |

- Campos que llena el sistema: —
- Campos que se bloquean: El enlace vence en 1 hora.
- Archivos: No aplica.
- Guardar o enviar con: **Restablecer contraseña**.

**Pasos:**

##### Paso 3.1 — Abrir la recuperación
**Objetivo del paso:** Iniciar el proceso de cambio de contraseña.
**Qué hacer:** En la pantalla de ingreso haga clic en **¿Has olvidado tu contraseña?**.
**Resultado esperado:** Aparece "¿Olvidaste tu contraseña?".

##### Paso 3.2 — Escribir el correo
**Objetivo del paso:** Indicar a qué cuenta se enviará el enlace.
**Qué hacer:** En **Correo electrónico** escriba su correo institucional y haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Revisa tu correo electrónico" y llega el correo "SI-CIPRAT - Restablecer Contraseña".

##### Paso 3.3 — Abrir el enlace del correo
**Objetivo del paso:** Llegar a la pantalla de nueva contraseña antes de que venza.
**Qué hacer:** Abra el correo y haga clic en el enlace dentro de la hora siguiente.
**Resultado esperado:** Aparece "Configurar nueva contraseña". Si pasó más de 1 hora, al guardar aparece "Token inválido o expirado".

##### Paso 3.4 — Escribir y confirmar la nueva contraseña
**Objetivo del paso:** Definir una contraseña válida y distinta de las anteriores.
**Qué hacer:** Escriba en **Nueva Contraseña** al menos 8 caracteres con un carácter especial, distinta de sus últimas 5 contraseñas, y repítala en **Confirmar Contraseña**.
**Resultado esperado:** Los indicadores se marcan como cumplidos.

##### Paso 3.5 — Guardar la contraseña
**Objetivo del paso:** Dejar activa la nueva contraseña.
**Qué hacer:** Haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Contraseña restablecida — Tu contraseña se ha restablecido correctamente. Haz clic abajo para iniciar sesión." con el botón **Iniciar Sesión**.

> 🎞️ **[GIF MED-09-ACC-12]** — Recuperación de la contraseña
> **Debe mostrar:** Solicitud del enlace, mensaje "Revisa tu correo electrónico", pantalla "Configurar nueva contraseña" y mensaje "Contraseña restablecida"
> **Resaltar:** Enlace ¿Has olvidado tu contraseña?; botón Restablecer contraseña
> **Pantalla / ruta:** `/forgot-password`, `/reset-password/:token` (`dashboard/src/pages/auth/ForgotPassword.tsx`, `ResetPassword.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Usuario de prueba
> **Solo para GIF — Secuencia:** 1) ¿Has olvidado tu contraseña? 2) Correo 3) Enlace 4) Nueva contraseña 5) Restablecer contraseña · **Duración aproximada:** 25 segundos
> **Texto alternativo:** Animación del restablecimiento de la contraseña

**Resultado de la actividad:** La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Crear una contraseña corta o sin símbolos | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña debe contener al menos un carácter especial") | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Revise los indicadores de la pantalla antes de enviar. |
| Escribir diferente la confirmación de la contraseña | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | — |
| Usar una contraseña anterior al restablecerla | "No puedes reutilizar ninguna de tus últimas 5 contraseñas" o "La nueva contraseña no puede ser igual a tu contraseña actual" | El sistema guarda el historial de contraseñas. | Elija una contraseña distinta de las 5 anteriores. | — |
| Abrir el enlace de restablecimiento después de 1 hora | "Token inválido o expirado" | El enlace de restablecimiento vence en 1 hora. | Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. | Use el enlace apenas llegue. |

> 📷 **[CAPTURA MED-09-ACC-13]** — Mensaje ERR-ACC-10
> **Debe mostrar:** La pantalla con el mensaje "No puedes reutilizar ninguna de tus últimas 5 contraseñas" o "La nueva contraseña no puede ser igual a tu contraseña actual"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:378-396`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar una contraseña anterior al restablecerla

> 📷 **[CAPTURA MED-09-ACC-14]** — Mensaje ERR-ACC-11
> **Debe mostrar:** La pantalla con el mensaje "Token inválido o expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:622-628`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de restablecimiento después de 1 hora

**⚠️ Atención:**
- La plataforma no tiene una pantalla para cambiar la contraseña conociendo la actual: para cambiarla, use siempre **¿Has olvidado tu contraseña?** (el servicio `password-change` existe, pero ninguna pantalla lo usa).

**Ejemplo:** Si solicita el enlace a las 3:00 p. m., debe usarlo antes de las 4:00 p. m.

#### Actividad 4 — Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

**Cuándo se hace y requisitos previos:** Secuencia E0.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La sesión se cierra tras 60 minutos sin actividad y el acceso vence a los 720 minutos (12 horas). | Revise el estado o el dato en la pantalla antes de actuar | Volver a iniciar sesión (El propio usuario) | RN-ACC-08 |

**Dónde:** Menú lateral › parte inferior, nombre del usuario › **Cerrar sesión**.

**Qué ve:** Al pie del menú lateral, sus iniciales y su nombre; al hacer clic se despliegan **Ver Perfil** y **Cerrar sesión**.

**Pasos:**

##### Paso 4.1 — Abrir el menú del usuario
**Objetivo del paso:** Encontrar la opción de salida.
**Qué hacer:** Haga clic en su nombre, al pie del menú lateral.
**Resultado esperado:** Se despliegan **Ver Perfil** y **Cerrar sesión**.

##### Paso 4.2 — Cerrar la sesión
**Objetivo del paso:** Terminar la sesión cuando deja de trabajar.
**Qué hacer:** Haga clic en **Cerrar sesión**.
**Resultado esperado:** Vuelve a la pantalla de ingreso.

##### Paso 4.3 — Reconocer el cierre automático
**Objetivo del paso:** Saber qué hacer cuando el sistema cierra la sesión.
**Qué hacer:** Si deja la plataforma sin uso 60 minutos, o la sesión vence a las 12 horas, lea el aviso y vuelva a iniciar sesión.
**Resultado esperado:** Aparece "Sesión cerrada por inactividad" o "Sesión expirada" y la pantalla de ingreso.

> 📷 **[CAPTURA MED-09-ACC-15]** — Menú del usuario
> **Debe mostrar:** El pie del menú lateral con el nombre del usuario y las opciones Ver Perfil y Cerrar sesión
> **Resaltar:** Opción Cerrar sesión
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:425-479`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Usuario de prueba
> **Texto alternativo:** Menú del usuario con la opción Cerrar sesión

**Resultado de la actividad:** La sesión termina; los datos no guardados de un formulario abierto se pierden.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Dejar la plataforma abierta sin usarla 60 minutos | "Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente." | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Guarde los formularios antes de dejar el equipo. |
| Trabajar con una sesión vencida | "Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente." | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | — |

> 📷 **[CAPTURA MED-09-ACC-16]** — Mensaje ERR-ACC-12
> **Debe mostrar:** La pantalla con el mensaje "Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useIdleTimeout.ts:6-22`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Dejar la plataforma abierta sin usarla 60 minutos

> 📷 **[CAPTURA MED-09-ACC-17]** — Mensaje ERR-ACC-13
> **Debe mostrar:** La pantalla con el mensaje "Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useApiErrorHandler.ts:14`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Trabajar con una sesión vencida

**⚠️ Atención:**
- ⚠️ Guarde los formularios antes de dejar el equipo: el cierre por inactividad no guarda lo diligenciado.

**Ejemplo:** Si su última acción fue a las 10:00 a. m., a las 11:00 a. m. la sesión se cierra sola.

#### Actividad 5 — Consultar los Términos de uso y contactar al soporte técnico

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

**Cuándo se hace y requisitos previos:** Secuencia E0. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Pie de página › **Términos de uso** (`/terminos-de-uso`); pantallas de acceso › **¿Necesita soporte técnico?**.

**Qué ve:** "Términos y condiciones de uso de la plataforma CIPRAT", "Actualizados el 17 de septiembre del 2025", con 14 numerales (definiciones, aceptación, condiciones técnicas, cuentas de usuario, protección de datos, entre otros) y el correo de soporte "siciprat@mininterior.gov.co — Lunes a Viernes 7:00 a.m. a 7:00 p.m.".

**Pasos:**

##### Paso 5.1 — Abrir los Términos de uso
**Objetivo del paso:** Conocer sus obligaciones como usuario.
**Qué hacer:** Haga clic en **Términos de uso** al pie de la página.
**Resultado esperado:** Se abre la página de términos y condiciones.

##### Paso 5.2 — Revisar las condiciones técnicas
**Objetivo del paso:** Saber qué necesita para usar la plataforma.
**Qué hacer:** Lea el numeral "4. Condiciones técnicas de acceso y uso".
**Resultado esperado:** Identifica: conexión estable, navegadores Chrome, Firefox o Edge actualizados y credenciales personales e intransferibles.

##### Paso 5.3 — Escribir al soporte
**Objetivo del paso:** Pedir ayuda técnica.
**Qué hacer:** En las pantallas de acceso haga clic en **¿Necesita soporte técnico?**: se abre un correo a siciprat@mininterior.gov.co. Escriba qué hacía, la pantalla, la hora y adjunte una captura del mensaje.
**Resultado esperado:** Su programa de correo abre un mensaje nuevo dirigido al soporte.

> 📷 **[CAPTURA MED-09-ACC-18]** — Términos de uso
> **Debe mostrar:** La página de términos con el título y el numeral 4
> **Resaltar:** Numeral "4. Condiciones técnicas de acceso y uso" y el correo de soporte
> **Pantalla / ruta:** `/terminos-de-uso` (`dashboard/src/pages/TermsOfUse.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** No requiere datos
> **Texto alternativo:** Página de términos y condiciones de uso

**Resultado de la actividad:** Conoce las condiciones de uso y el canal de soporte.

**Escenarios de error y solución:**

No se identificaron escenarios de error en el código para esta actividad.

**⚠️ Atención:**
- El ingreso a la plataforma implica la aceptación de los Términos y Condiciones.

#### Actividad 6 — Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

**Cuándo se hace y requisitos previos:** Secuencia E0.4.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › nombre del usuario › **Ver Perfil** (`/mi-perfil`).

**Qué ve:** Un encabezado con su nombre y tres secciones con campos deshabilitados: **Información General** "Información del funcionario" (Nombres, Apellidos, Cargo, Área (opcional), Correo electrónico); **Entidad y Acceso** "Información de organización y permisos" (Entidad Central —o "Sin organización"—, Rol, Nivel de Acceso, Subdirección); **Asignaciones** "Departamentos asignados" (Departamentos).

**Pasos:**

##### Paso 6.1 — Abrir Mi perfil
**Objetivo del paso:** Llegar a la pantalla de datos de la cuenta.
**Qué hacer:** Haga clic en su nombre al pie del menú lateral y luego en **Ver Perfil**.
**Resultado esperado:** Se abre Mi perfil con "Cargando perfil..." y luego sus datos.

##### Paso 6.2 — Revisar Información General
**Objetivo del paso:** Confirmar los datos personales registrados.
**Qué hacer:** Lea Nombres, Apellidos, Cargo, Área y Correo electrónico.
**Resultado esperado:** Los datos coinciden con los suyos; los campos no se pueden editar.

##### Paso 6.3 — Revisar Entidad y Acceso y Asignaciones
**Objetivo del paso:** Confirmar el alcance de datos.
**Qué hacer:** Verifique que el Rol diga "Consulta Departamentos" y que en **Departamentos** estén los que le corresponden.
**Resultado esperado:** Confirma que verá las alertas que tienen al menos un municipio en los departamentos asignados a su usuario.

> 📷 **[CAPTURA MED-09-ACC-19]** — Mi perfil
> **Debe mostrar:** Las tres secciones de Mi perfil de un usuario de prueba con rol Consulta — Departamentos
> **Resaltar:** Campos Rol, Entidad Central, Nivel de Acceso, Subdirección y Departamentos
> **Pantalla / ruta:** `/mi-perfil` (`dashboard/src/pages/MyProfile.tsx:111-283`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Usuario de prueba de la ruta
> **Texto alternativo:** Pantalla Mi perfil con los datos de la cuenta

**Resultado de la actividad:** Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Encontrar en Mi perfil un rol, entidad, subdirección o departamentos que no corresponden | No aparece mensaje: los datos se muestran en campos deshabilitados. | El usuario fue configurado con otros datos; Mi perfil no permite editarlos. | Pida la corrección a quien administra los usuarios, indicando el dato correcto. | Revise Mi perfil después del primer ingreso. |

**⚠️ Atención:**
- Mi perfil es solo de consulta: el servicio para editar el propio perfil existe en el servidor, pero la pantalla tiene los campos deshabilitados.

### Módulo 02 — Inicio

**Prerrequisitos:** Módulo 01 (sesión abierta).

**Definición del módulo:** Tablero de entrada de la plataforma. Muestra la última alerta activa, cinco indicadores (Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales, Alertas cerradas) con su tendencia de los últimos meses, el "Porcentaje de Avance Global", el ranking "Alertas por departamento" (Top 10), las "Alertas recientes" y el mapa de municipios con alertas. La misma página, sin sesión, es la vista pública de consulta ciudadana. Incluye el panel de accesibilidad (alto contraste y tamaño de letra).

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda leer los indicadores del Inicio; consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa; navegar con el menú lateral y usar el panel de accesibilidad; consultar el tablero público sin iniciar sesión.

**Contexto del módulo:** Se consulta en todas las fases del ciclo. Recibe datos de *Alertas tempranas* (estado, tipo, fecha de notificación, municipios) y de los planes de acción (actividades programadas y ejecutadas). Con sesión, los datos se filtran por el alcance del rol (departamentos o entidad); sin sesión, muestra la información nacional pública. Los borradores no cuentan en los indicadores. Para el usuario de Consulta — Departamentos: indicadores, ranking, alertas recientes y mapa calculados sobre las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`) (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores. En total, tiene 9 de las 9 funcionalidades del módulo.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Consultar los indicadores del Inicio (F-INI-01) | Muestra Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales y Alertas cerradas, con la tendencia "vs ultimo mes". | R | Módulo 02 — Actividad 1 |
| Consultar la última alerta emitida (F-INI-02) | Muestra el banner "Se ha emitido la Alerta Temprana…" con la alerta activa más reciente y el botón **Ver Alerta**. | R | Módulo 02 — Actividad 2 |
| Consultar "Alertas por departamento" (Top 10) (F-INI-03) | Ranking de los 10 departamentos con más alertas y su porcentaje del total. | R | Módulo 02 — Actividad 2 |
| Consultar "Alertas recientes" (F-INI-04) | Lista las 9 alertas más recientes por fecha de la alerta. | R | Módulo 02 — Actividad 2 |
| Consultar el "Porcentaje de Avance Global" (F-INI-05) | Promedio del porcentaje de cumplimiento de las alertas (no borradores) y total de actividades ejecutadas frente a programadas. | R | Módulo 02 — Actividad 1 |
| Consultar el mapa de municipios con alertas (F-INI-06) | Mapa de Colombia con los municipios que tienen alertas (rojo: inminencia; azul: estructural) y tabla accesible con los mismos datos. | R | Módulo 02 — Actividad 2 |
| Consultar el tablero público sin iniciar sesión (F-INI-07) | La página de inicio pública (`/`) muestra los mismos bloques con la información nacional, sin filtro de rol. | R | Módulo 02 — Actividad 4 |
| Usar el panel de accesibilidad (F-INI-08) | Activa o desactiva el alto contraste y aumenta o reduce el tamaño de letra. | U | Módulo 02 — Actividad 3 |
| Usar el menú lateral (F-INI-09) | Navega entre los módulos visibles para el rol; el menú se puede ocultar. | R | Módulo 02 — Actividad 3 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 02 — Actividad 1 |

#### Actividad 1 — Leer los indicadores del Inicio

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Qué ve:** Título "Inicio" y el texto "Visualiza de manera centralizada el estado y la distribución de las alertas tempranas asociadas a sus departamentos". Cinco tarjetas con valor, tendencia "vs ultimo mes" y una línea de los últimos 4 meses:

| Tarjeta | Qué cuenta (alertas no borrador de sus departamentos asignados) |
|---|---|
| Total de alertas | Todas las alertas |
| Alertas activas | Alertas en estado Activa |
| Alertas de inminencia | Alertas de tipo Inminencia |
| Alertas estructurales | Alertas de tipo Estructural |
| Alertas cerradas | Alertas en estado Cerrada |

La tendencia es la diferencia entre lo notificado en el mes actual y en el mes anterior (por fecha de notificación). Debajo, el bloque **Porcentaje de Avance Global**: el promedio del % de cumplimiento de cada alerta (las alertas sin actividades cuentan como 0 %) y el total "{ejecutadas} de {programadas} actividades ejecutadas".

**Pasos:**

##### Paso 1.1 — Abrir Inicio
**Objetivo del paso:** Ver el tablero de su alcance.
**Qué hacer:** Haga clic en **Inicio** en el menú lateral.
**Resultado esperado:** Aparecen las tarjetas, el avance global, el ranking y el mapa.

##### Paso 1.2 — Leer las tarjetas y su tendencia
**Objetivo del paso:** Saber cuántas alertas hay y cómo cambió el último mes.
**Qué hacer:** Lea el valor grande de cada tarjeta y el número "vs ultimo mes".
**Resultado esperado:** Identifica, por ejemplo, que hay 2 alertas activas más que el mes anterior.

##### Paso 1.3 — Interpretar el Porcentaje de Avance Global
**Objetivo del paso:** Entender el avance de los planes de acción.
**Qué hacer:** Lea el porcentaje y la línea "X de Y actividades ejecutadas". Recuerde que es un promedio por alerta y no la división del total.
**Resultado esperado:** Puede explicar por qué el porcentaje puede ser distinto de X/Y.

> 📷 **[CAPTURA MED-09-INI-01]** — Indicadores del Inicio
> **Debe mostrar:** Las cinco tarjetas y el bloque Porcentaje de Avance Global para un usuario Consulta — Departamentos
> **Resaltar:** Valor y tendencia "vs ultimo mes" de una tarjeta; el porcentaje y la línea de actividades ejecutadas
> **Pantalla / ruta:** `/inicio` (`dashboard/src/pages/Home.tsx:340-433`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Ambiente de pruebas con alertas de varios estados
> **Texto alternativo:** Tarjetas de indicadores y porcentaje de avance global

**Resultado de la actividad:** Interpreta el estado general de las alertas de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | — |
| El tablero aparece vacío o en cero | "No hay datos de departamentos" / "No hay alertas recientes" | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | — |

> 📷 **[CAPTURA MED-09-INI-02]** — Mensaje ERR-INI-01
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar datos"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:416`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero no carga

> 📷 **[CAPTURA MED-09-INI-03]** — Mensaje ERR-INI-02
> **Debe mostrar:** La pantalla con el mensaje "No hay datos de departamentos" / "No hay alertas recientes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:212,263`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero aparece vacío o en cero

**⚠️ Atención:**
- Los borradores (alertas del Agente IA o de X-Road aún no publicadas) no cuentan en los indicadores.
- ⚠️ El "Porcentaje de Avance Global" promedia el porcentaje de cada alerta: no es igual a ejecutadas ÷ programadas del total.

**Ejemplo:** Con dos alertas: A con 10 programadas y 5 ejecutadas (50 %) y B con 2 programadas y 2 ejecutadas (100 %), el avance global es (50 + 100) ÷ 2 = 75 %, y la línea dice "7 de 12 actividades ejecutadas" (58,3 %). Una tercera alerta sin actividades (0 %) bajaría el promedio a 50 %.

#### Actividad 2 — Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Inicio**.

**Qué ve:** El banner "Se ha emitido la Alerta Temprana {número}, con fecha de difusión: {fecha}. Consulta los detalles para conocer el alcance y las acciones recomendadas." con el botón **Ver Alerta**; el bloque "Alertas por departamento" (Top 10, con bandera, número de alertas y porcentaje); "Alertas recientes" (las 9 más recientes por fecha de la alerta) y el mapa de Colombia: municipios en rojo (Inminencia) y azul (Estructural), con la leyenda "Leyenda del mapa" y una tabla accesible (Municipio, Departamento, Cantidad de Alertas, Alertas de Inminencia, Alertas Estructurales).

**Pasos:**

##### Paso 2.1 — Abrir la última alerta
**Objetivo del paso:** Conocer la alerta activa más reciente.
**Qué hacer:** Lea el banner superior y haga clic en **Ver Alerta**.
**Resultado esperado:** Se abre la alerta en *Alertas tempranas*.

##### Paso 2.2 — Revisar el ranking de departamentos
**Objetivo del paso:** Saber dónde se concentran las alertas.
**Qué hacer:** Lea "Alertas por departamento" (Top 10).
**Resultado esperado:** Identifica los departamentos con más alertas y su porcentaje.

##### Paso 2.3 — Revisar las alertas recientes
**Objetivo del paso:** Ver lo último registrado.
**Qué hacer:** Recorra "Alertas recientes".
**Resultado esperado:** Ve las últimas alertas por fecha de la alerta.

##### Paso 2.4 — Usar el mapa
**Objetivo del paso:** Ubicar los municipios con alertas.
**Qué hacer:** Pase el cursor sobre un municipio coloreado; use la tabla accesible si prefiere leer los datos.
**Resultado esperado:** Aparece el nombre del municipio, el departamento y el número de alertas.

> 📷 **[CAPTURA MED-09-INI-04]** — Mapa y ranking del Inicio
> **Debe mostrar:** El mapa con municipios en rojo y azul, la leyenda y el bloque Alertas por departamento
> **Resaltar:** Leyenda del mapa; un municipio con su tooltip; Top 10
> **Pantalla / ruta:** `/inicio` (`dashboard/src/components/map/ColombiaMap.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Ambiente de pruebas con alertas de los dos tipos
> **Texto alternativo:** Mapa de Colombia con municipios con alertas y ranking por departamento

**Resultado de la actividad:** Ubica geográficamente las alertas de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | — |
| El tablero aparece vacío o en cero | "No hay datos de departamentos" / "No hay alertas recientes" | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | — |

**⚠️ Atención:**
- El listado "Alertas recientes" no excluye borradores en el código (las tarjetas sí los excluyen): si ve un número de alerta que no está en las tarjetas, puede ser un borrador.

#### Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral; botón **Accesibilidad** (panel "Panel de accesibilidad").

**Qué ve:** El menú lateral con: Inicio, Alertas tempranas, Seguimiento, Oficios de consumación, Informes de seguimiento, Notificaciones, Ver Perfil. El botón **Ocultar** contrae el menú. El panel de accesibilidad tiene "Alternar alto contraste" (Activar/Desactivar alto contraste), "Reducir tamaño de letra" y "Aumentar tamaño de letra".

**Pasos:**

##### Paso 3.1 — Recorrer el menú
**Objetivo del paso:** Conocer los módulos de su rol.
**Qué hacer:** Haga clic en cada opción del menú lateral.
**Resultado esperado:** Se abre cada pantalla; las rutas de navegación ("migas de pan") muestran dónde está.

##### Paso 3.2 — Ocultar y mostrar el menú
**Objetivo del paso:** Ganar espacio en pantalla.
**Qué hacer:** Haga clic en **Ocultar** al pie del menú; para volver a verlo, use el botón de abrir menú.
**Resultado esperado:** El menú se contrae o se expande.

##### Paso 3.3 — Ajustar la accesibilidad
**Objetivo del paso:** Leer mejor la información.
**Qué hacer:** Abra el panel de accesibilidad y use "Activar alto contraste", "Aumentar tamaño de letra" o "Reducir tamaño de letra".
**Resultado esperado:** La pantalla cambia de contraste o de tamaño de letra.

> 📷 **[CAPTURA MED-09-INI-05]** — Menú lateral del rol
> **Debe mostrar:** El menú lateral completo de un usuario Consulta — Departamentos
> **Resaltar:** Las opciones visibles para el rol
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:16-91`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Usuario de prueba de la ruta
> **Texto alternativo:** Menú lateral con los módulos del rol

**Resultado de la actividad:** Navega con soltura por los módulos de su rol.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Escribir una dirección que no existe | "Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida." › **Volver al inicio** | La ruta no existe. | Haga clic en **Volver al inicio** y navegue desde el menú. | Use el menú lateral. |
| Abrir un formulario de registro desde un celular | "Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio." | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Planee el registro desde un computador. |
| Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error) | "No tienes permisos para realizar esta acción." | El servidor rechaza la operación para el rol (403). | Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. | Use solo los botones habilitados para su rol. |
| Repetir una acción o actuar sobre un registro que cambió de estado | "Conflicto con el estado actual del recurso." | Otro usuario o una acción anterior cambió el estado del registro (409). | Actualice la página, revise el estado actual y repita la acción si todavía aplica. | Evite el doble clic y trabaje sobre la información recién cargada. |
| El servidor no está disponible | "El servidor no está disponible. Por favor, intenta más tarde." | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Espere unos minutos e intente de nuevo. | — |
| Enviar datos con un formato que el servidor no acepta | "La solicitud no es válida. Verifica los datos e intenta de nuevo." o "Los datos enviados no son válidos." | Errores 400 o 422 de validación. | Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. | Lea la ayuda de cada campo. |

> 📷 **[CAPTURA MED-09-INI-06]** — Mensaje ERR-GEN-12
> **Debe mostrar:** La pantalla con el mensaje "Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida." › **Volver al inicio**
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/NotFound.tsx:23-45`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir una dirección que no existe

> 📷 **[CAPTURA MED-09-INI-07]** — Mensaje ERR-GEN-11
> **Debe mostrar:** La pantalla con el mensaje "Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:550-551`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un formulario de registro desde un celular

> 📷 **[CAPTURA MED-09-INI-08]** — Mensaje ERR-GEN-01
> **Debe mostrar:** La pantalla con el mensaje "No tienes permisos para realizar esta acción."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:69-70`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error)

> 📷 **[CAPTURA MED-09-INI-09]** — Mensaje ERR-GEN-03
> **Debe mostrar:** La pantalla con el mensaje "Conflicto con el estado actual del recurso."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:73-74`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Repetir una acción o actuar sobre un registro que cambió de estado

> 📷 **[CAPTURA MED-09-INI-10]** — Mensaje ERR-GEN-05
> **Debe mostrar:** La pantalla con el mensaje "El servidor no está disponible. Por favor, intenta más tarde."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:79-82`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor no está disponible

> 📷 **[CAPTURA MED-09-INI-11]** — Mensaje ERR-GEN-13
> **Debe mostrar:** La pantalla con el mensaje "La solicitud no es válida. Verifica los datos e intenta de nuevo." o "Los datos enviados no son válidos."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:65-76`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Enviar datos con un formato que el servidor no acepta

**⚠️ Atención:**
- Los formularios de registro no se abren en pantallas de celular ("Disponible en escritorio").

#### Actividad 4 — Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Dirección principal de SI-CIPRAT (`/`), sin iniciar sesión.

**Qué ve:** Los mismos bloques del Inicio (banner, tarjetas, avance global, ranking, alertas recientes y mapa) con la información nacional y el botón **Iniciar sesión**.

**Pasos:**

##### Paso 4.1 — Abrir la vista pública
**Objetivo del paso:** Ver lo que ve la ciudadanía.
**Qué hacer:** Abra la dirección de la plataforma sin iniciar sesión (o en una ventana privada).
**Resultado esperado:** Aparece el tablero público con el botón **Iniciar sesión**.

##### Paso 4.2 — Comparar con su vista
**Objetivo del paso:** Entender la diferencia de alcance.
**Qué hacer:** Compare los totales con los de su Inicio con sesión, que se calculan sobre sus departamentos asignados.
**Resultado esperado:** Los totales públicos son nacionales y pueden ser mayores que los de su vista.

> 📷 **[CAPTURA MED-09-INI-12]** — Tablero público
> **Debe mostrar:** La página pública sin sesión con el botón Iniciar sesión
> **Resaltar:** Botón Iniciar sesión
> **Pantalla / ruta:** `/` (`dashboard/src/App.tsx:40`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Ambiente de pruebas
> **Texto alternativo:** Tablero público de alertas tempranas

**Resultado de la actividad:** Sabe qué información es pública y cuál depende de su sesión.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | — |

**⚠️ Atención:**
- La vista pública no muestra recomendaciones, planes ni archivos: solo los bloques del tablero.

### Módulo 03 — Alertas tempranas

**Prerrequisitos:** Módulos 01 y 02.

**Definición del módulo:** Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. Permite listar, buscar, filtrar y descargar las alertas; ver su detalle, su PDF y su historial de actividades; reportar una alerta nueva en un formulario de 6 pasos; editarla, publicarla si está en borrador, subsumir otras alertas, eliminarla y cerrar alertas.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar, buscar y filtrar alertas tempranas; ver el detalle de una alerta y descargar su PDF; consultar el historial de actividades de una alerta; descargar el listado de alertas en CSV; ir a las recomendaciones de una alerta.

**Contexto del módulo:** Inicia el ciclo (E1) y lo termina (E6.3 cierre). Recibe alertas por X-Road o del Agente IA, o las registra el Ministerio. Entrega la alerta a *Recomendaciones* (E2), cuya existencia habilita el plan de acción, y a *Inicio* para los indicadores. Todos los roles consultan las alertas de su alcance; el registro y la edición son del Super Administrador y el Administrador; la eliminación, el cierre y la carga de archivos, solo del Super Administrador. Para el usuario de Consulta — Departamentos: ve las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`). En total, tiene 7 de las 16 funcionalidades del módulo; no tiene: reportar una alerta temprana, adjuntar el PDF de la alerta y el Adjunto, editar una alerta, cambiar el número de una alerta manual, publicar una alerta en borrador, subsumir otras alertas, eliminar una alerta, reemplazar o eliminar los archivos de la alerta, cerrar alertas.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar alertas (F-ALE-01) | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Módulo 03 — Actividad 1 |
| Buscar alertas (F-ALE-02) | Busca por número o texto de la alerta. | R | Módulo 03 — Actividad 1 |
| Filtrar alertas (F-ALE-03) | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Módulo 03 — Actividad 1 |
| Ver el detalle de una alerta (F-ALE-04) | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Módulo 03 — Actividad 2 |
| Descargar el PDF de la alerta (F-ALE-05) | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Módulo 03 — Actividad 2 |
| Consultar el historial de actividades de la alerta (F-ALE-06) | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Módulo 03 — Actividad 3 |
| Descargar el listado de alertas (CSV) (F-ALE-07) | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Módulo 03 — Actividad 4 |
| Recibir alertas tempranas por X-Road (F-INT-01, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía la alerta con sus municipios y recomendaciones; el sistema crea la alerta y las recomendaciones automáticas y notifica a las entidades. | Automática | Módulo 03 — Actividad 1 |
| Listar las recomendaciones de una alerta (F-REC-01, módulo Recomendaciones) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 03 — Actividad 5 |

#### Actividad 1 — Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Qué ve:** "Alertas Tempranas — Gestiona y monitorea la comunicación de las alertas tempranas." con las tarjetas **Total de alertas**, **Alertas activas** y **Alertas cerradas**; la sección "Alertas" con el contador y los botones **Descargar**, **Cerrar alertas** y **Reportar alerta** (los dos últimos deshabilitados para su rol); las pestañas **Todas**, **Inminencia** y **Estructurales**; el buscador "Buscar por nombre" y **Filtros**. Ve las alertas que tienen al menos un municipio en los departamentos asignados a su usuario, incluidas las alertas en Borrador de ese alcance.

| Columna | Descripción |
|---|---|
| Alerta | Número de la alerta (por ejemplo AT-013-2025) |
| Tipo | Inminencia o Estructural |
| Tema | Tema clave (descripción) |
| Estado | Borrador, Activa o Cerrada |
| Porcentaje de ejecución | % de cumplimiento del plan (ejecutadas ÷ programadas) |
| Cantidad de Recomendaciones | Recomendaciones de la alerta (para la Entidad Territorial y Consulta Entidad, solo las de su entidad) |
| Creación | Manual o Automática |
| ⋯ | Menú de acciones: Detalle, Editar, Recomendaciones, Historial de actividades, Eliminar |

Filtros: **Tipo** (Todos, Inminencia, Estructural), **Estado** (Todos, Borrador, Activa, Cerrada), **Etiqueta** (Todas, Nacional, Regional, Internacional), **Economías Ilegales**, **Grupos Armados**, **Conductas Vulneratorias** y **Población Afectada** (con buscador). Botones **Limpiar filtros** y **Aplicar filtros**. La tabla pagina de 10 en 10 (**Siguiente →**).

**Pasos:**

##### Paso 1.1 — Abrir Alertas tempranas
**Objetivo del paso:** Ver las alertas de su alcance.
**Qué hacer:** Haga clic en **Alertas tempranas** en el menú lateral.
**Resultado esperado:** Aparecen "Cargando alertas..." y luego las tarjetas y la tabla.

##### Paso 1.2 — Leer las tarjetas
**Objetivo del paso:** Conocer los totales.
**Qué hacer:** Lea Total de alertas, Alertas activas y Alertas cerradas.
**Resultado esperado:** Conoce cuántas alertas hay en cada estado.

##### Paso 1.3 — Cambiar de pestaña
**Objetivo del paso:** Separar por tipo.
**Qué hacer:** Haga clic en **Inminencia** o **Estructurales**; **Todas** quita el filtro.
**Resultado esperado:** La tabla muestra solo ese tipo.

##### Paso 1.4 — Buscar una alerta
**Objetivo del paso:** Ir directo a una alerta.
**Qué hacer:** Escriba el número (por ejemplo "AT-013") o una palabra del tema en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; sin coincidencias: "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo."

##### Paso 1.5 — Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** Haga clic en **Filtros**, elija Tipo, Estado, Etiqueta y las listas del conflicto, y haga clic en **Aplicar filtros**. Para quitar, **Limpiar filtros**.
**Resultado esperado:** El botón Filtros muestra cuántos filtros están activos y la tabla se actualiza.

##### Paso 1.6 — Abrir el menú de acciones
**Objetivo del paso:** Saber qué puede hacer con cada alerta.
**Qué hacer:** Haga clic en ⋯ al final de la fila.
**Resultado esperado:** Aparecen Detalle, Recomendaciones e Historial de actividades; Editar y Eliminar están deshabilitados ("No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas").

> 📷 **[CAPTURA MED-09-ALE-01]** — Listado de alertas
> **Debe mostrar:** La pantalla Alertas Tempranas de un usuario Consulta — Departamentos con las tarjetas, las pestañas y la tabla
> **Resaltar:** Pestañas Todas/Inminencia/Estructurales; Buscar por nombre; Filtros; menú ⋯
> **Pantalla / ruta:** `/alertas-tempranas` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** AT-013-2025 o alertas Mock
> **Texto alternativo:** Listado de alertas tempranas con filtros

**Resultado de la actividad:** Ubica la alerta y sus datos principales.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de registrar, editar, eliminar o cerrar alertas | Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No tienes permisos para cerrar alertas" | Su rol solo consulta alertas. | Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). | — |
| No encontrar una alerta que esperaba ver | No aparece mensaje o aparece "No se encontraron resultados". | La alerta está fuera de su alcance (departamentos o entidad), es un borrador o no existe. | Revise su alcance en **Ver Perfil**; si la alerta le corresponde, pida el ajuste de su usuario o de la recomendación. | — |
| El listado de alertas no carga | "Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |
| Una alerta emitida por la Defensoría no aparece en SI-CIPRAT | No aparece mensaje en la plataforma. | La alerta aún no llega por X-Road o el mensaje fue rechazado por el servidor. | Informe a la Secretaría Técnica; el Super Administrador o el Administrador pueden registrarla con **Reportar alerta** si se confirma que no llegará. | — |

> 📷 **[CAPTURA MED-09-ALE-02]** — Mensaje ERR-ALE-17
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72,181-238`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de registrar, editar, eliminar o cerrar alertas

> 📷 **[CAPTURA MED-09-ALE-03]** — Mensaje ERR-ALE-19
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:212-215`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El listado de alertas no carga

> 📷 **[CAPTURA MED-09-ALE-04]** — Mensaje ERR-GEN-07
> **Debe mostrar:** La pantalla con el mensaje "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/SearchEmptyState.tsx:9-10`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar o filtrar sin coincidencias

**⚠️ Atención:**
- La lista también muestra alertas en estado Borrador (creadas por el Agente IA o por X-Road) de su alcance: todavía no son alertas activas.

**Ejemplo:** Busque "AT-013" y verá la alerta AT-013-2025 [DATO REAL AT-013-25], tipo Estructural, etiqueta Regional según la línea base (los scripts del repositorio la cargan como "Nacional": verifique cuál muestra su ambiente), notificada el 07/10/2025.

#### Actividad 2 — Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Detalle**.

**Qué ve:** Una ventana con el número de la alerta, su tipo, la etiqueta "Borrador" si aplica y "Fecha: DD/MM/AAAA". Pestañas: **Información general** (Ejecutado / Programado, Plan de acción, "PDF de la alerta" y Descripción), **Lugar de advertencia** (tabla de municipios: Municipio / Departamento, Cod DANE, CAT, PNIS, PDET, Zona Fut.), **Conflicto** (Economías ilegales, Grupos armados ilegales), **Conductas vulneratorias e infracciones al D.I.H.**, **Población afectada** y **Alertas subsumidas** ("Alertas que subsume", "Subsumida por" o "No hay alertas subsumidas"). Botones **Cerrar** y **Editar**.

**Pasos:**

##### Paso 2.1 — Abrir el detalle
**Objetivo del paso:** Ver la ficha completa.
**Qué hacer:** En la fila, haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ficha en la pestaña Información general.

##### Paso 2.2 — Revisar Información general
**Objetivo del paso:** Conocer el avance y el tema.
**Qué hacer:** Lea Ejecutado / Programado, el estado del Plan de acción y la Descripción.
**Resultado esperado:** Conoce el avance y el estado del plan.

##### Paso 2.3 — Descargar el PDF
**Objetivo del paso:** Consultar el documento oficial.
**Qué hacer:** Haga clic en el archivo de "PDF de la alerta".
**Resultado esperado:** Se descarga el PDF. Si no hay archivo, la alerta no tiene PDF cargado.

##### Paso 2.4 — Recorrer las demás pestañas
**Objetivo del paso:** Conocer el territorio, el conflicto y la población.
**Qué hacer:** Abra Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas.
**Resultado esperado:** Ve los municipios (con CAT, PNIS, PDET y Zona Fut.), los grupos armados, las conductas, las poblaciones y las subsunciones.

##### Paso 2.5 — Cerrar la ficha
**Objetivo del paso:** Volver al listado.
**Qué hacer:** Haga clic en **Cerrar**.
**Resultado esperado:** Vuelve a la tabla de alertas.

> 📷 **[CAPTURA MED-09-ALE-05]** — Detalle de la alerta
> **Debe mostrar:** La ficha de una alerta en la pestaña Lugar de advertencia
> **Resaltar:** Pestañas; columnas CAT, PNIS, PDET y Zona Fut.; "PDF de la alerta"
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Ficha de detalle de una alerta temprana

**Resultado de la actividad:** Conoce la alerta completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

> 📷 **[CAPTURA MED-09-ALE-06]** — Mensaje ERR-GEN-02
> **Debe mostrar:** La pantalla con el mensaje "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:71-72`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un registro que ya no existe o fue eliminado

**⚠️ Atención:**
- El botón **Editar** aparece deshabilitado con "No tienes permisos para editar alertas".

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25], la pestaña Lugar de advertencia lista 1.122 municipios, por ejemplo GUAVIARE › Miraflores (95200).

#### Actividad 3 — Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Historial de actividades**.

**Qué ve:** La ventana "Historial de actividades alerta {número} — Conoce el historial de acciones realizadas sobre la alerta." con la línea de tiempo: usuario, acción, detalle y fecha; algunos eventos muestran "Consecutivo:", "Fecha notificacion:" y "Descargar archivo". Sin eventos: "No hay actividades registradas".

**Pasos:**

##### Paso 3.1 — Abrir el historial
**Objetivo del paso:** Ver la trazabilidad.
**Qué hacer:** Haga clic en ⋯ › **Historial de actividades**.
**Resultado esperado:** Se abre la línea de tiempo de la alerta.

##### Paso 3.2 — Leer los eventos
**Objetivo del paso:** Reconstruir lo ocurrido.
**Qué hacer:** Recorra los eventos y use **Mostrar 10 mas** para ver los anteriores.
**Resultado esperado:** Identifica, por ejemplo, cuándo se confirmó el plan y quién lo hizo.

##### Paso 3.3 — Descargar un archivo del evento
**Objetivo del paso:** Ver el soporte de un cierre o informe.
**Qué hacer:** Si el evento tiene "Descargar archivo", haga clic.
**Resultado esperado:** Se descarga el archivo asociado.

> 📷 **[CAPTURA MED-09-ALE-07]** — Historial de actividades
> **Debe mostrar:** La línea de tiempo con la confirmación del plan
> **Resaltar:** Evento de confirmación con usuario y fecha
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/ActivityHistoryModal.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Alerta Mock con varias acciones
> **Texto alternativo:** Historial de actividades de una alerta

**Resultado de la actividad:** Conoce la trazabilidad de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El servidor falla al procesar la solicitud | "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio — La plataforma presentó un inconveniente al procesar tu solicitud. Estamos trabajando para solucionarlo. Por favor, intenta nuevamente en unos minutos." | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | — |

> 📷 **[CAPTURA MED-09-ALE-08]** — Mensaje ERR-GEN-04
> **Debe mostrar:** La pantalla con el mensaje "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio — La plataforma presentó un inconveniente al procesar tu solicitud. Estamos 
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:77-78`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor falla al procesar la solicitud

**⚠️ Atención:**
- El historial guarda eventos, no versiones completas: no permite ver cómo estaba una actividad antes de editarla.

#### Actividad 4 — Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › **Descargar**.

**Qué ve:** El botón **Descargar** (muestra "Descargando..."). El archivo CSV (UTF-8) trae: Número de Alerta, Fecha de Alerta, Fecha de Notificación, Tipo, Estado, Descripción, Etiqueta, Cantidad de Recomendaciones, Economías Ilegales, Grupos Armados, Conductas Vulneratorias, Población Afectada y Fecha de Creación.

**Pasos:**

##### Paso 4.1 — Aplicar los filtros que necesita
**Objetivo del paso:** Descargar solo lo útil.
**Qué hacer:** Use la pestaña, el buscador y **Filtros**.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 4.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; ábralo en Excel.

> 📷 **[CAPTURA MED-09-ALE-09]** — Botón Descargar
> **Debe mostrar:** La cabecera de la tabla con el botón Descargar
> **Resaltar:** Botón Descargar
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:165-221`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Alertas Mock
> **Texto alternativo:** Botón para descargar el listado de alertas

**Resultado de la actividad:** Tiene el listado en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

> 📷 **[CAPTURA MED-09-ALE-10]** — Mensaje ERR-GEN-10
> **Debe mostrar:** La pantalla con el mensaje "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:87-88`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: La descarga del CSV falla

**⚠️ Atención:**
- Los textos salen completos (el sistema no los corta a 4.000 caracteres).
- Las fechas salen en formato AAAA-MM-DD.

#### Actividad 5 — Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Qué ve:** La pantalla de recomendaciones de la alerta con el enlace "Volver a Alertas Tempranas".

**Pasos:**

##### Paso 5.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 5.2 — Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

> 📷 **[CAPTURA MED-09-ALE-11]** — Menú ⋯ de la alerta
> **Debe mostrar:** El menú de acciones de una fila con la opción Recomendaciones
> **Resaltar:** Opción Recomendaciones
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:469-507`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Alerta Mock
> **Texto alternativo:** Menú de acciones de una alerta

**Resultado de la actividad:** Llega a las recomendaciones de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | — |

> 📷 **[CAPTURA MED-09-ALE-12]** — Mensaje ERR-REC-08
> **Debe mostrar:** La pantalla con el mensaje "La alerta solicitada no existe o ha sido eliminada."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:168`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir las recomendaciones de una alerta eliminada

### Módulo 04 — Recomendaciones

**Prerrequisitos:** Módulo 03 (la alerta debe existir y estar Activa).

**Definición del módulo:** Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). Permite listarlas, buscarlas, filtrarlas, ver su detalle y descargarlas; al Super Administrador y al Administrador, crearlas en 2 pasos (eje temático y descripción; entidades principales y asociadas) y editarlas; al Super Administrador, eliminarlas. El sistema asigna el código RC y notifica por correo a las entidades.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar, buscar y filtrar las recomendaciones de una alerta; ver el detalle de una recomendación; descargar las recomendaciones de una alerta en CSV.

**Contexto del módulo:** Corresponde a la fase E2. Requiere una alerta registrada (E1). Entrega las recomendaciones a *Planes de acción* (E3), donde la Entidad Territorial les agrega actividades, y dispara el correo "Nueva Recomendacion Asignada". Mientras el plan de acción no esté confirmado, las recomendaciones se pueden editar o eliminar. Para el usuario de Consulta — Departamentos: ve todas las recomendaciones de cada alerta que está en su alcance. En total, tiene 5 de las 8 funcionalidades del módulo; no tiene: agregar una recomendación, editar una recomendación, eliminar una recomendación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar las recomendaciones de una alerta (F-REC-01) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 03 — Actividad 5; Módulo 04 — Actividad 1 |
| Buscar y filtrar recomendaciones (F-REC-02) | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Módulo 04 — Actividad 1 |
| Ver el detalle de una recomendación (F-REC-03) | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Módulo 04 — Actividad 2 |
| Descargar las recomendaciones (CSV) (F-REC-04) | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Módulo 04 — Actividad 3 |
| Asignar el código RC (F-REC-08) | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Módulo 04 — Actividad 1 |

#### Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Alertas tempranas › ⋯ › **Recomendaciones**.

**Qué ve:** El encabezado de la alerta, el botón **Agregar recomendación** (deshabilitado para su rol: "No tienes permisos para agregar recomendaciones"), **Descargar**, "Buscar por nombre" y **Filtros** (Entidad Principal "Todas las entidades", Eje Temático, Modo de Creación Manual/Automática).

| Columna | Descripción |
|---|---|
| Recomendación | Código RC (por ejemplo RC-001-2025-013) |
| Eje tematico | Eje temático |
| Entidad Principal | Entidad que debe responder |
| Descripción | Texto de la recomendación |
| Actividades (Aprobadas / Total) | Actividades aprobadas sobre el total |
| Ejecución (Ejecutadas / Programadas) | Avance con su % de cumplimiento |
| ⋯ | Detalle, Editar, Eliminar |

Aparecen todas las recomendaciones de la alerta.

**Pasos:**

##### Paso 1.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver la lista.
**Qué hacer:** Desde la alerta, ⋯ › **Recomendaciones**.
**Resultado esperado:** Aparece "Cargando recomendaciones..." y luego la tabla.

##### Paso 1.2 — Buscar
**Objetivo del paso:** Encontrar una recomendación.
**Qué hacer:** Escriba el código (por ejemplo "RC-001") o una palabra en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra.

##### Paso 1.3 — Filtrar
**Objetivo del paso:** Ver por entidad, eje o modo.
**Qué hacer:** Haga clic en **Filtros**, elija Entidad Principal, Eje Temático o Modo de Creación y **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo lo filtrado.

##### Paso 1.4 — Leer el avance
**Objetivo del paso:** Saber cómo va cada recomendación.
**Qué hacer:** Lea Actividades (Aprobadas / Total) y Ejecución.
**Resultado esperado:** Identifica las recomendaciones sin actividades o con bajo cumplimiento.

> 📷 **[CAPTURA MED-09-REC-01]** — Recomendaciones de una alerta
> **Debe mostrar:** La tabla de recomendaciones vista por un usuario Consulta — Departamentos
> **Resaltar:** Columnas Actividades y Ejecución; Filtros
> **Pantalla / ruta:** `/alertas-tempranas/:id/recomendaciones` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Listado de recomendaciones de una alerta

**Resultado de la actividad:** Conoce las recomendaciones de la alerta y su avance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de agregar, editar o eliminar recomendaciones | Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para eliminar recomendaciones" | Solo el Super Administrador y el Administrador las registran. | Pida el cambio a la Secretaría Técnica. | — |
| Las recomendaciones no cargan | "Error al cargar las recomendaciones. Por favor, intente nuevamente." | Falla del servicio. | Recargue la página. | — |
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-09-REC-02]** — Mensaje ERR-REC-06
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para elimi
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de agregar, editar o eliminar recomendaciones

> 📷 **[CAPTURA MED-09-REC-03]** — Mensaje ERR-REC-07
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar las recomendaciones. Por favor, intente nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:238`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Las recomendaciones no cargan

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25] hay 41 recomendaciones, de RC-001-2025-013 a RC-041-2025-013; por ejemplo RC-001-2025-013, eje "Coordinación de Respuesta Rápida", Entidad Principal "MinInterior - CIPRAT".

#### Actividad 2 — Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Recomendaciones › fila › ⋯ › **Detalle**.

**Qué ve:** La ventana con "Última actualización", **Información general** (Eje temático, Entidad principal), **Descripción**, **Entidades asociadas** y la **Ejecución**; botones **Cerrar** y **Editar**.

**Pasos:**

##### Paso 2.1 — Abrir el detalle
**Objetivo del paso:** Ver la recomendación completa.
**Qué hacer:** Haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ventana.

##### Paso 2.2 — Leer las entidades
**Objetivo del paso:** Saber quién responde y quién apoya.
**Qué hacer:** Lea la Entidad principal y las Entidades asociadas.
**Resultado esperado:** Identifica a la entidad responsable del plan y a las que apoyan.

> 📷 **[CAPTURA MED-09-REC-04]** — Detalle de recomendación
> **Debe mostrar:** La ventana con Entidad principal y Entidades asociadas
> **Resaltar:** Entidades asociadas
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Recomendación Mock
> **Texto alternativo:** Detalle de una recomendación

**Resultado de la actividad:** Conoce la recomendación completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**⚠️ Atención:**
- El botón **Editar** aparece deshabilitado con "No tienes permisos para editar recomendaciones".

**Ejemplo:** RC-011-2025-013 [DATO REAL AT-013-25]: su descripción empieza "Recomendación No. 12 …", es decir, el código RC no coincide con el número de la recomendación en el documento (hallazgo H3).

#### Actividad 3 — Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda descargar las recomendaciones visibles en un archivo CSV.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Recomendaciones › **Descargar**.

**Qué ve:** El CSV trae: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. No incluye las entidades asociadas ni el estado.

**Pasos:**

##### Paso 3.1 — Filtrar
**Objetivo del paso:** Descargar lo necesario.
**Qué hacer:** Aplique búsqueda y filtros.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 3.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; si falla: "Error al descargar el archivo CSV. Por favor, intente nuevamente."

> 📷 **[CAPTURA MED-09-REC-05]** — CSV de recomendaciones
> **Debe mostrar:** El archivo CSV abierto en Excel
> **Resaltar:** Columnas
> **Pantalla / ruta:** Recomendaciones › Descargar (`main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Alerta Mock
> **Texto alternativo:** Archivo CSV de recomendaciones

**Resultado de la actividad:** Tiene las recomendaciones en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

**⚠️ Atención:**
- El texto de la descripción sale completo (sin corte a 4.000 caracteres).

### Módulo 05 — Seguimiento

**Prerrequisitos:** Módulo 03; que la Entidad Territorial haya registrado actividades (RN-PLA-01) para revisar, o informes (RN-PLA-07) para aprobar.

**Definición del módulo:** Módulo "Seguimiento de Planes": usa las mismas pantallas de Planes de acción en modo de seguimiento. Allí el Monitor, el Líder de Macrozona y el Super Administrador revisan las actividades (comentarios y "Marcar como Revisado"), las aprueban o descartan su aprobación, confirman el plan de acción de la alerta y aprueban los informes de ejecución. Los demás roles con acceso solo consultan.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar el listado de Seguimiento y encontrar lo pendiente; consultar recomendaciones, actividades e informes en Seguimiento.

**Contexto del módulo:** Corresponde a E4 (E4.1 revisión, E4.2 aprobación, E4.3 confirmación) y a E5.3 (aprobación de informes). Recibe las actividades formuladas en *Planes de acción* (E3.2) y los informes reportados (E5.1). Entrega el plan confirmado, que habilita los informes de ejecución y envía el correo de validación a las entidades, y los informes aprobados, que fijan la fecha del próximo informe. Las aprobaciones solo se pueden hacer desde este módulo. Para el usuario de Consulta — Departamentos: ve los planes de las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`). En total, tiene 4 de las 10 funcionalidades del módulo; no tiene: marcar una actividad como revisada, aprobar una actividad, descartar la aprobación de una actividad, validar si el plan se puede confirmar, confirmar el plan de acción, aprobar un informe de ejecución.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los planes en Seguimiento (F-SEG-01) | Pantalla "Seguimiento de Planes": por alerta muestra Ejecutado vs programado, Plan de acción e Informe, y la acción para confirmar el plan. | R | Módulo 05 — Actividad 1 |
| Buscar y filtrar planes en Seguimiento (F-SEG-02) | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento. | R | Módulo 05 — Actividad 1 |
| Descargar el listado de Seguimiento (CSV) (F-SEG-03) | Descarga el listado de planes visible. | Archivo | Módulo 05 — Actividad 1 |
| Consultar recomendaciones, actividades e informes en Seguimiento (F-SEG-04) | Recorre alerta › recomendaciones › actividades en modo seguimiento, con el panel "Información Actividades" y los "Informes de ejecución". | R | Módulo 05 — Actividad 2 |
| Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01, módulo Tareas programadas) | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Módulo 05 — Actividad 2 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 05 — Actividad 2 |
| Calcular el próximo informe al aprobar un informe (F-TAR-04, módulo Tareas programadas) | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Módulo 05 — Actividad 2 |

#### Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Seguimiento** (`/seguimiento`) — pantalla "Seguimiento de Planes".

**Qué ve:** "Seguimiento de Planes — Monitorea de manera organizada y eficiente todas las actividades asociadas a las recomendaciones", el botón **Informe** y las pestañas **Alertas**, **Recomendaciones** y **Actividades**, con las mismas columnas y filtros de Planes de acción y, en cada alerta, la acción **Confirmar Plan de Acción** (deshabilitada para su rol: "No tienes permisos para confirmar planes de acción").

Estados del **Plan de acción**: "Sin recomendaciones", "Sin plan" (recomendaciones sin actividades), "Pendiente" (hay actividades por aprobar), "Aprobado" (todas aprobadas; listo para confirmar), "Cerrado" (alerta cerrada). Estados del **Informe**: "Sin Informe", "Sin Completar", "Pendiente", "Aprobado", "Completado", "Cerrado".

Ve los planes de sus departamentos asignados.

**Pasos:**

##### Paso 1.1 — Abrir Seguimiento
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** Haga clic en **Seguimiento**.
**Resultado esperado:** Aparece "Seguimiento de Planes".

##### Paso 1.2 — Filtrar lo pendiente
**Objetivo del paso:** Encontrar el trabajo.
**Qué hacer:** Abra **Filtros**: Estado del Plan de Acción "Pendiente" (actividades por aprobar) o "Aprobado" (listo para confirmar); Estado del Informe "Pendiente" (informes por aprobar). **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo esos planes.

##### Paso 1.3 — Descargar el listado
**Objetivo del paso:** Llevar el control fuera de línea.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV.

##### Paso 1.4 — Entrar al plan
**Objetivo del paso:** Llegar a las actividades.
**Qué hacer:** Haga clic en **Ir al plan de acción** y luego **Ver Actividades** en la recomendación.
**Resultado esperado:** Ve las actividades en modo de seguimiento.

> 📷 **[CAPTURA MED-09-SEG-01]** — Seguimiento de Planes
> **Debe mostrar:** La pantalla Seguimiento de Planes de un usuario Consulta — Departamentos con el filtro de plan Pendiente
> **Resaltar:** Filtros; columna Plan de acción; acción Confirmar Plan de Acción
> **Pantalla / ruta:** `/seguimiento`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Planes Mock
> **Texto alternativo:** Listado de seguimiento de planes de acción

**Resultado de la actividad:** Sabe qué planes, actividades e informes requieren atención.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Seguimiento aparece vacío | "No hay alertas con planes de acción" | No hay alertas con municipios en sus departamentos, o su usuario no tiene departamentos. | Revise sus departamentos en **Ver Perfil** y pida el ajuste si hace falta. | — |
| Buscar los botones de aprobar o confirmar | Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado** | Su rol solo consulta en Seguimiento. | La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. | — |
| Hacer clic en **Informe** (Informe de recomendaciones) desde Seguimiento | "Error al cargar el informe de recomendaciones" | El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Pida el consolidado al Monitor o a la Secretaría Técnica. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-09-SEG-02]** — Mensaje ERR-SEG-13
> **Debe mostrar:** La pantalla con el mensaje "No hay alertas con planes de acción"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:198-200`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Seguimiento aparece vacío

> 📷 **[CAPTURA MED-09-SEG-03]** — Mensaje ERR-SEG-07
> **Debe mostrar:** La pantalla con el mensaje Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado**
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:75-79,331`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de aprobar o confirmar

> 📷 **[CAPTURA MED-09-SEG-04]** — Mensaje ERR-SEG-14
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar el informe de recomendaciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/InformeRecomendaciones.tsx:82`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Hacer clic en **Informe** (Informe de recomendaciones) desde Seguimiento

**⚠️ Atención:**
- Su rol solo consulta en Seguimiento.

#### Actividad 2 — Consultar recomendaciones, actividades e informes en Seguimiento

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La fecha de notificación es el día 0 del ciclo de informes; el sistema no verifica que sea posterior a la fecha de la alerta. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la fecha contra el documento (Super Administrador o Administrador) | RN-ALE-13 |
| Al aprobar un informe, el próximo informe es la fecha de notificación de la alerta + 6 meses (primer informe) o el anterior + 6 meses. | Revise el estado o el dato en la pantalla antes de actuar | — (Sistema) | RN-SEG-06 |
| Cada día a las 00:01, si el próximo informe de una actividad venció y la alerta no está cerrada, la actividad vuelve a "Sin Informe" y su Número de actividades se suma otra vez a lo programado. | Revise el estado o el dato en la pantalla antes de actuar | Reportar el informe del nuevo ciclo (Entidad Territorial) | RN-TAR-01 |

**Dónde:** Seguimiento › **Ir al plan de acción** › **Ver Actividades** › ícono **Ver detalle** de la fila.

**Qué ve:** Las tablas de recomendaciones y actividades en modo de seguimiento: la tabla de actividades no tiene botones de informe ni menú ⋯; en cada fila hay un ícono **Ver detalle**. El "Detalle de Actividad" muestra "Información Actividades", "Seleccionar actividad", los campos de la actividad y los "Informes de ejecución".

| Columna | Descripción |
|---|---|
| Actividad | "Actividad N" |
| Objetivo | Objetivo de la actividad |
| Descripción | Texto de la actividad |
| Número Actividades | Meta por ciclo de 6 meses |
| Ejecución (Ejecutadas / Programadas) | Avance acumulado y "% cumplimiento" |
| Plazo | 1 a 3, 3 a 6, 6 a 9 meses o Permanente |
| Instrumento | Sí / No |
| Recursos | Sí / No |
| Estado | Pendiente Aprobación, Aprobado, Aprobado - Sin Informe |
| Estado Informe | Sin Informe, Sin Completar, Pendiente, Aprobado |
| Próximo Informe | Fecha límite del siguiente informe |
| (ícono) | **Ver detalle** |

**Pasos:**

##### Paso 2.1 — Abrir las actividades
**Objetivo del paso:** Llegar a la información.
**Qué hacer:** En Seguimiento haga clic en **Ir al plan de acción** › **Ver Actividades**.
**Resultado esperado:** Aparece la tabla de actividades.

##### Paso 2.2 — Abrir el detalle
**Objetivo del paso:** Leer la actividad y sus informes.
**Qué hacer:** Haga clic en el ícono **Ver detalle** de la fila.
**Resultado esperado:** Se abre "Detalle de Actividad" con los informes de ejecución y su PDF.

##### Paso 2.3 — Leer los informes de ejecución
**Objetivo del paso:** Conocer lo reportado por la entidad.
**Qué hacer:** Baje a "Informes de ejecución" y descargue "Informe.pdf" si lo necesita.
**Resultado esperado:** Conoce lo ejecutado en cada ciclo.

> 📷 **[CAPTURA MED-09-SEG-05]** — Detalle de Actividad en Seguimiento
> **Debe mostrar:** El detalle de una actividad visto por un usuario Consulta — Departamentos
> **Resaltar:** Ícono Ver detalle; Informes de ejecución
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadDetailModal.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Actividad Mock
> **Texto alternativo:** Detalle de actividad en Seguimiento

**Resultado de la actividad:** Conoce el estado de las actividades y sus informes.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**⚠️ Atención:**
- La pantalla no le muestra los comentarios de las actividades ni le permite comentar (el botón **Comentarios** solo aparece a quien formula o aprueba).

### Módulo 06 — Informes de seguimiento

**Prerrequisitos:** Módulo 03 (la alerta debe existir).

**Definición del módulo:** Módulo donde se registran los informes de seguimiento que emite la Defensoría sobre una alerta. Permite listarlos, filtrarlos por alerta, ver su detalle y descargar su PDF; al Super Administrador y al Administrador, cargarlos en 2 pasos (datos del informe; modificaciones a la alerta: cerrar municipios, agregar municipios y recomendaciones) y editarlos; al Super Administrador, eliminarlos y cerrar la alerta con el informe.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar los informes de seguimiento y descargar su PDF.

**Contexto del módulo:** Ocurre después del registro de la alerta, normalmente hacia el cierre del ciclo (E6.1). Recibe la alerta y sus municipios; puede devolver el ciclo a E2 (nuevas recomendaciones, con correo a las entidades) o cerrar la alerta (E6.3). También llegan informes por X-Road. La Entidad Territorial no tiene este módulo en el menú. Para el usuario de Consulta — Departamentos: ve todos los registrados en el país: este listado no aplica el filtro por departamentos (`main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:266-279`). En total, tiene 4 de las 9 funcionalidades del módulo; no tiene: cargar un informe de seguimiento, modificar municipios y agregar recomendaciones desde el informe, cerrar la alerta con el informe de seguimiento, editar un informe de seguimiento, eliminar un informe de seguimiento.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los informes de seguimiento (F-ISE-01) | Tabla con Informe, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Módulo 06 — Actividad 1 |
| Buscar y filtrar informes por alerta (F-ISE-02) | Busca por número y filtra por Alerta asociada. | R | Módulo 06 — Actividad 1 |
| Ver el detalle de un informe de seguimiento (F-ISE-03) | Muestra Informacion basica, Detalles del seguimiento y Archivo adjunto. | R | Módulo 06 — Actividad 1 |
| Descargar el PDF del informe de seguimiento (F-ISE-04) | Descarga el archivo del informe. | Archivo | Módulo 06 — Actividad 1 |
| Recibir informes de seguimiento por X-Road (F-INT-02, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía informes de seguimiento, que pueden cerrar la alerta o modificarla. | Automática | Módulo 06 — Actividad 1 |

#### Actividad 1 — Consultar los informes de seguimiento y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral › **Informes de seguimiento** ("Encuentra los informes de seguimiento publicados por la defensoría").

**Qué ve:** La sección "Informes" con el botón **Cargar informe** (deshabilitado: "No tienes permisos para cargar informes"), "Buscar por nombre" y **Filtros** (Alerta asociada: "Todas las alertas").

| Columna | Descripción |
|---|---|
| Informe | Número del informe |
| Fecha de creación | Registro en SI-CIPRAT |
| Fecha de finalización | Fecha del informe |
| Alertas asociadas | Alerta del informe |
| Acciones | Ver detalle, Editar informe, Eliminar informe |

El detalle muestra **Informacion basica** (Numero de informe, Fecha de notificacion, Fecha de emision, Numero de radicado, Alerta asociada), **Detalles del seguimiento** (Acciones desarrolladas para el cumplimiento de las recomendaciones, Acciones complementarias, Acciones de coordinacion interinstitucional, Buenas practicas identificadas o dificultades encontradas, Instrumentos de planeacion utilizados, Resultados alcanzados) y **Archivo adjunto**.

**Pasos:**

##### Paso 1.1 — Abrir el módulo
**Objetivo del paso:** Ver los informes.
**Qué hacer:** Haga clic en **Informes de seguimiento**.
**Resultado esperado:** Aparece "Cargando informes..." y luego la tabla; sin datos: "No hay informes de seguimiento — Los informes de seguimiento publicados por la defensoría aparecerán aquí."

##### Paso 1.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** Abra **Filtros** y elija la Alerta asociada (la lista muestra alertas cerradas: "No se encontraron alertas cerradas").
**Resultado esperado:** La tabla se filtra.

##### Paso 1.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el informe.
**Qué hacer:** Haga clic en **Ver detalle** y luego en **Descargar**.
**Resultado esperado:** Se abre el detalle y se descarga el PDF.

> 📷 **[CAPTURA MED-09-ISE-01]** — Informes de seguimiento
> **Debe mostrar:** La tabla de informes y el panel de detalle abierto
> **Resaltar:** Detalles del seguimiento; Descargar
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformeSeguimientoDetailPanel.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Informe Mock
> **Texto alternativo:** Informes de seguimiento y su detalle

**Resultado de la actividad:** Conoce los informes de seguimiento.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de cargar, editar o eliminar informes | Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes" | Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. | Pida la carga a la Secretaría Técnica. | — |
| Los informes no cargan | "Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-09-ISE-02]** — Mensaje ERR-ISE-07
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49-52,121,261,288`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de cargar, editar o eliminar informes

> 📷 **[CAPTURA MED-09-ISE-03]** — Mensaje ERR-ISE-09
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/InformesDeSeguimiento.tsx:76-77`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los informes no cargan

**⚠️ Atención:**
- Este listado muestra los informes de todo el país: no se filtra por sus departamentos.
- El filtro "Alerta asociada" solo ofrece alertas cerradas.

### Módulo 07 — Oficios de consumación

**Prerrequisitos:** Módulo 03 (las alertas deben existir).

**Definición del módulo:** Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. Todos los roles los listan, filtran por alerta, consultan y descargan; solo el Super Administrador los carga en 2 pasos (información del oficio y alertas; modificaciones por alerta), los edita y los elimina.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar los oficios de consumación y descargar su PDF.

**Contexto del módulo:** Corresponde al cierre del ciclo (E6.2). Recibe las alertas asociadas y sus municipios; envía el correo "Notificación Oficio de Consumación" a las entidades. También llegan oficios por X-Road. Es visible para todos los roles. Para el usuario de Consulta — Departamentos: ve todos los registrados en el país: este listado no aplica el filtro por departamentos (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`). En total, tiene 4 de las 8 funcionalidades del módulo; no tiene: cargar un oficio de consumación, modificar municipios y agregar recomendaciones desde el oficio, editar un oficio de consumación, eliminar un oficio de consumación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los oficios de consumación (F-OFI-01) | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Módulo 07 — Actividad 1 |
| Buscar y filtrar oficios por alerta (F-OFI-02) | Busca por radicado y filtra por Alerta asociada. | R | Módulo 07 — Actividad 1 |
| Ver el detalle de un oficio (F-OFI-03) | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Módulo 07 — Actividad 1 |
| Descargar el PDF del oficio (F-OFI-04) | Descarga el archivo del oficio. | Archivo | Módulo 07 — Actividad 1 |
| Recibir oficios de consumación por X-Road (F-INT-03, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía oficios de consumación. | Automática | Módulo 07 — Actividad 1 |

#### Actividad 1 — Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.2. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral › **Oficios de consumación** ("Encuentra los oficios de consumación emitidos por la defensoría").

**Qué ve:** La sección "Oficios" con el botón **Cargar oficio** (deshabilitado: "No tienes permisos para cargar oficios"), "Buscar por nombre" y **Filtros** (Alerta asociada).

| Columna | Descripción |
|---|---|
| Oficio | Número de radicado |
| Fecha de creación | Registro en SI-CIPRAT |
| Fecha de finalización | Fecha del oficio |
| Alertas asociadas | Alertas del oficio |
| Acciones | Ver detalle, Editar, Eliminar |

El detalle muestra **Informacion basica** (Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion), **Alertas asociadas** y **Archivo adjunto** (Archivo PDF).

**Pasos:**

##### Paso 1.1 — Abrir el módulo
**Objetivo del paso:** Ver los oficios.
**Qué hacer:** Haga clic en **Oficios de consumación**.
**Resultado esperado:** Aparece la tabla; sin datos: "No hay oficios de consumación — Los oficios de consumación emitidos por la defensoría aparecerán aquí."

##### Paso 1.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** Abra **Filtros** y elija la Alerta asociada.
**Resultado esperado:** La tabla se filtra.

##### Paso 1.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el oficio.
**Qué hacer:** Haga clic en **Ver detalle** y en **Descargar**.
**Resultado esperado:** Se descarga el PDF.

> 📷 **[CAPTURA MED-09-OFI-01]** — Oficios de consumación
> **Debe mostrar:** La tabla de oficios con el detalle abierto
> **Resaltar:** Alertas asociadas; Archivo PDF
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Oficio Mock
> **Texto alternativo:** Oficios de consumación y su detalle

**Resultado de la actividad:** Conoce los oficios de consumación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de cargar, editar o eliminar oficios | Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios" | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | — |
| Los oficios no cargan o no se descargan | "Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio." | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-09-OFI-02]** — Mensaje ERR-OFI-02
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48,107,241,263`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de cargar, editar o eliminar oficios

> 📷 **[CAPTURA MED-09-OFI-03]** — Mensaje ERR-OFI-05
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/OficiosDeConsumacion.tsx:81-82,194`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los oficios no cargan o no se descargan

**⚠️ Atención:**
- Este listado muestra los oficios de todo el país: no se filtra por sus departamentos.

### Módulo 08 — Notificaciones

**Prerrequisitos:** Módulo 01.

**Definición del módulo:** Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda consultar el panel de Notificaciones; reconocer los correos que envía el sistema y qué hacer con cada uno.

**Contexto del módulo:** Acompaña todo el ciclo. Recibe eventos de todos los módulos: cada acción registrada en el historial aparece en el panel, y ciertos eventos generan correo. Los correos de negocio solo llegan a usuarios activos de Entidad Territorial (Central o Subdirección) cuya entidad es principal o asociada; el aprobador designado de un reporte de ejecución recibe su propio correo. No hay mensajes de texto (SMS). Para el usuario de Consulta — Departamentos: ve el historial de actividad de las alertas con al menos un municipio en sus departamentos asignados (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:79-88`) (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`). En total, tiene 6 de las 13 funcionalidades del módulo; no tiene: recibir el correo de recomendación asignada, recibir el correo de recomendación actualizada, recibir el correo de validación del plan de acción, recibir el recordatorio de informe de ejecución, recibir el correo de informe de seguimiento, recibir el correo de oficio de consumación, recibir el correo de reporte de ejecución pendiente.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Abrir el panel de Notificaciones (F-NOT-01) | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Módulo 08 — Actividad 1 |
| Buscar en el panel de Notificaciones (F-NOT-02) | Filtra el historial por texto. | R | Módulo 08 — Actividad 1 |
| Cargar más notificaciones (F-NOT-03) | Trae 10 registros más del historial. | R | Módulo 08 — Actividad 1 |
| Recibir el correo de invitación (F-NOT-04) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Módulo 01 — Actividad 1; Módulo 08 — Actividad 2 |
| Recibir el correo con el código de verificación (F-NOT-05) | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Módulo 01 — Actividad 2; Módulo 08 — Actividad 2 |
| Recibir el correo de restablecimiento de contraseña (F-NOT-06) | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Módulo 01 — Actividad 3; Módulo 08 — Actividad 2 |

#### Actividad 1 — Consultar el panel de Notificaciones

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Notificaciones** (panel lateral).

**Qué ve:** El panel "Notificaciones" con el buscador "Buscar por nombre" y la lista del historial de actividad de sus departamentos asignados: usuario que actuó, acción, alerta y fecha; algunos eventos muestran "Consecutivo:", "Fecha notificacion:" y el enlace "Descargar archivo". Al final, **Mostrar 10 mas**.

**Pasos:**

##### Paso 1.1 — Abrir el panel
**Objetivo del paso:** Ver la actividad reciente.
**Qué hacer:** Haga clic en **Notificaciones** en el menú lateral.
**Resultado esperado:** Se abre el panel con los eventos más recientes.

##### Paso 1.2 — Buscar un evento
**Objetivo del paso:** Encontrar lo relacionado con una alerta o persona.
**Qué hacer:** Escriba en "Buscar por nombre" (por ejemplo, el número de la alerta).
**Resultado esperado:** La lista se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 1.3 — Ver más eventos
**Objetivo del paso:** Revisar eventos anteriores.
**Qué hacer:** Haga clic en **Mostrar 10 mas** al final de la lista.
**Resultado esperado:** Se agregan 10 eventos; al final aparece "No hay mas actividades".

> 📷 **[CAPTURA MED-09-NOT-01]** — Panel Notificaciones
> **Debe mostrar:** El panel abierto con varios eventos de una alerta
> **Resaltar:** Buscador; un evento con usuario, acción y fecha; Mostrar 10 mas
> **Pantalla / ruta:** Panel lateral (`dashboard/src/components/notifications/NotificationsPanel.tsx`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Alerta Mock con historial
> **Texto alternativo:** Panel de notificaciones con el historial de actividad

**Resultado de la actividad:** Conoce lo que pasó en las alertas de su alcance; es su fuente de avisos, porque su rol no recibe los correos de negocio.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el panel sin actividad en su alcance | "No hay notificaciones" | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | — |

> 📷 **[CAPTURA MED-09-NOT-02]** — Mensaje ERR-NOT-01
> **Debe mostrar:** La pantalla con el mensaje "No hay notificaciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/notifications/NotificationsPanel.tsx:143`
> **Tomarla con:** Consulta — Departamentos · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el panel sin actividad en su alcance

**⚠️ Atención:**
- El panel no tiene marcas de leído o no leído: muestra el historial de actividad.

#### Actividad 2 — Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Los correos de negocio solo se envían a usuarios activos de Entidad Territorial (Central o Subdirección) cuya entidad o subdirección es principal o asociada. | Revise el estado o el dato en la pantalla antes de actuar | Consultar el panel Notificaciones (Sistema) | RN-NOT-01 |
| El recordatorio de informe se envía una sola vez por ciclo, cuando faltan 30 días o menos para el próximo informe. | Revise el estado o el dato en la pantalla antes de actuar | Consultar la columna Próximo Informe (Sistema) | RN-TAR-02 |

**Dónde:** Su bandeja de correo; los enlaces de los correos llevan a la plataforma.

**Qué ve:** | Correo (asunto) | Cuándo llega | Qué hacer |
|---|---|---|
| "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" | Al ser invitado o al reenviar la invitación | Activar la cuenta en 7 días |
| "SI-CIPRAT - Código de Verificación" | En cada ingreso | Escribir el código en 1 hora |
| "SI-CIPRAT - Restablecer Contraseña" | Al usar ¿Has olvidado tu contraseña? | Usar el enlace en 1 hora |

Su rol **no** recibe los correos de recomendaciones, planes, recordatorios, informes de seguimiento ni oficios: esos solo llegan a la Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`). Revise el panel **Notificaciones**.

**Pasos:**

##### Paso 2.1 — Identificar el remitente y el asunto
**Objetivo del paso:** Distinguir los correos del sistema.
**Qué hacer:** Busque en su bandeja los asuntos que empiezan por "SI-CIPRAT" o "Notificación".
**Resultado esperado:** Identifica el tipo de correo según la tabla.

##### Paso 2.2 — Actuar según el correo
**Objetivo del paso:** No dejar vencer los plazos.
**Qué hacer:** Use los correos de acceso; para lo demás revise el panel Notificaciones y los módulos.
**Resultado esperado:** Atiende cada aviso en el módulo correspondiente.

> 📷 **[CAPTURA MED-09-NOT-03]** — Correo del sistema
> **Debe mostrar:** Un correo "SI-CIPRAT - Código de Verificación" de prueba
> **Resaltar:** Asunto y enlace
> **Pantalla / ruta:** Bandeja de correo (plantillas en `main-api/CipratApi/Servicios/EmailService.cs`)
> **Tomarla con:** Consulta — Departamentos · **Datos:** Correo de prueba con datos Mock
> **Texto alternativo:** Ejemplo de correo enviado por SI-CIPRAT

**Resultado de la actividad:** Sabe qué correos esperar y qué hacer con cada uno.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Esperar un correo de negocio (recomendación, plan, recordatorio) | No aparece mensaje: el correo no llega. | Los correos de negocio solo se envían a usuarios de Entidad Territorial. | Consulte los cambios en el panel **Notificaciones** y en los módulos. | Revise el panel Notificaciones al iniciar el día. |

**⚠️ Atención:**
- Los correos de negocio se envían en lotes con copia oculta (CCO).
- No hay mensajes de texto (SMS).

**Ejemplo:** Si el informe aprobado fijó el próximo informe para el 7 de abril de 2026, el recordatorio llega a partir del 8 de marzo de 2026 (30 días antes).

### Módulo 09 — Práctica con el caso AT-013-25

**Prerrequisitos:** Haber completado los Módulos 01 a 08 de esta ruta; tener un usuario de prueba con el rol Consulta — Departamentos en el ambiente de pruebas y los valores de la línea base de la AT-013-25 o los datos Mock indicados.

**Definición del módulo:** Módulo de práctica guiada que repite, en orden cronológico, cada actividad operativa de la ruta con datos de la alerta AT-013-25 o con datos ficticios (Mock) cuando el dato real no está disponible o no está autorizado.

**Objetivo del módulo:** Que el usuario de Consulta — Departamentos pueda ejecutar en un ambiente de pruebas todas las actividades de su ruta con datos de la AT-013-25 o datos Mock.

**Contexto del módulo:** Los valores de la práctica salen de la línea base de la AT-013-25 (Riesgo Electoral Nacional 2025-2026) [DATO REAL AT-013-25]: alerta notificada el 07/10/2025, tipo Estructural, etiqueta Regional, 41 recomendaciones (RC-001-2025-013 a RC-041-2025-013) y un plan de mitigación **parcial**: 20 actividades de 5 recomendaciones (RC-003, RC-004, RC-021, RC-022 y RC-023). En el sistema la alerta se escribe AT-013-2025, porque el número exige año de 4 dígitos. Lo que la línea base no trae (las actividades de las otras recomendaciones y los informes de ejecución) se practica con datos Mock (pendiente: plan de mitigación no disponible). Antes de usar datos reales en una sesión, el Ministerio debe autorizarlos (ver `usos_datos_reales.csv`).

**Funcionalidades disponibles:** las mismas de los módulos anteriores de esta ruta, en el ambiente de pruebas.

#### Actividad 1 — Práctica: Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

**Cuándo se hace y requisitos previos:** Secuencia E0; los mismos requisitos de Módulo 01 — Actividad 4.

**Dónde:** Menú lateral › parte inferior, nombre del usuario › **Cerrar sesión**.

**Datos de la práctica:** Sesión abierta del usuario de prueba.

**Pasos:**

##### Paso 1.1 — Abrir el menú del usuario
**Objetivo del paso:** Encontrar la opción de salida.
**Qué hacer:** En el ambiente de pruebas: Haga clic en su nombre, al pie del menú lateral.
**Resultado esperado:** Se despliegan **Ver Perfil** y **Cerrar sesión**.

##### Paso 1.2 — Cerrar la sesión
**Objetivo del paso:** Terminar la sesión cuando deja de trabajar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar sesión**.
**Resultado esperado:** Vuelve a la pantalla de ingreso.

##### Paso 1.3 — Reconocer el cierre automático
**Objetivo del paso:** Saber qué hacer cuando el sistema cierra la sesión.
**Qué hacer:** En el ambiente de pruebas: Si deja la plataforma sin uso 60 minutos, o la sesión vence a las 12 horas, lea el aviso y vuelva a iniciar sesión.
**Resultado esperado:** Aparece "Sesión cerrada por inactividad" o "Sesión expirada" y la pantalla de ingreso.

**Resultado esperado de la práctica:** La sesión termina; los datos no guardados de un formulario abierto se pierden.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La sesión termina; los datos no guardados de un formulario abierto se pierden.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 4 y lo resolvió.

#### Actividad 2 — Práctica: Consultar los Términos de uso y contactar al soporte técnico

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

**Cuándo se hace y requisitos previos:** Secuencia E0; los mismos requisitos de Módulo 01 — Actividad 5.

**Dónde:** Pie de página › **Términos de uso** (`/terminos-de-uso`); pantallas de acceso › **¿Necesita soporte técnico?**.

**Datos de la práctica:** No requiere datos.

**Pasos:**

##### Paso 2.1 — Abrir los Términos de uso
**Objetivo del paso:** Conocer sus obligaciones como usuario.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Términos de uso** al pie de la página.
**Resultado esperado:** Se abre la página de términos y condiciones.

##### Paso 2.2 — Revisar las condiciones técnicas
**Objetivo del paso:** Saber qué necesita para usar la plataforma.
**Qué hacer:** En el ambiente de pruebas: Lea el numeral "4. Condiciones técnicas de acceso y uso".
**Resultado esperado:** Identifica: conexión estable, navegadores Chrome, Firefox o Edge actualizados y credenciales personales e intransferibles.

##### Paso 2.3 — Escribir al soporte
**Objetivo del paso:** Pedir ayuda técnica.
**Qué hacer:** En el ambiente de pruebas: En las pantallas de acceso haga clic en **¿Necesita soporte técnico?**: se abre un correo a siciprat@mininterior.gov.co. Escriba qué hacía, la pantalla, la hora y adjunte una captura del mensaje.
**Resultado esperado:** Su programa de correo abre un mensaje nuevo dirigido al soporte.

**Resultado esperado de la práctica:** Conoce las condiciones de uso y el canal de soporte.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce las condiciones de uso y el canal de soporte.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 5 y lo resolvió.

#### Actividad 3 — Práctica: Navegar con el menú lateral y usar el panel de accesibilidad

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 02 — Actividad 3.

**Dónde:** Menú lateral; botón **Accesibilidad** (panel "Panel de accesibilidad").

**Datos de la práctica:** No requiere datos.

**Pasos:**

##### Paso 3.1 — Recorrer el menú
**Objetivo del paso:** Conocer los módulos de su rol.
**Qué hacer:** En el ambiente de pruebas: Haga clic en cada opción del menú lateral.
**Resultado esperado:** Se abre cada pantalla; las rutas de navegación ("migas de pan") muestran dónde está.

##### Paso 3.2 — Ocultar y mostrar el menú
**Objetivo del paso:** Ganar espacio en pantalla.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ocultar** al pie del menú; para volver a verlo, use el botón de abrir menú.
**Resultado esperado:** El menú se contrae o se expande.

##### Paso 3.3 — Ajustar la accesibilidad
**Objetivo del paso:** Leer mejor la información.
**Qué hacer:** En el ambiente de pruebas: Abra el panel de accesibilidad y use "Activar alto contraste", "Aumentar tamaño de letra" o "Reducir tamaño de letra".
**Resultado esperado:** La pantalla cambia de contraste o de tamaño de letra.

**Resultado esperado de la práctica:** Navega con soltura por los módulos de su rol.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Navega con soltura por los módulos de su rol.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 3 y lo resolvió.

#### Actividad 4 — Práctica: Consultar el panel de Notificaciones

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 08 — Actividad 1.

**Dónde:** Menú lateral › **Notificaciones** (panel lateral).

**Datos de la práctica:** Buscar "AT-013" en el panel [DATO REAL AT-013-25].

**Pasos:**

##### Paso 4.1 — Abrir el panel
**Objetivo del paso:** Ver la actividad reciente.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Notificaciones** en el menú lateral.
**Resultado esperado:** Se abre el panel con los eventos más recientes.

##### Paso 4.2 — Buscar un evento
**Objetivo del paso:** Encontrar lo relacionado con una alerta o persona.
**Qué hacer:** En el ambiente de pruebas: Escriba en "Buscar por nombre" (por ejemplo, el número de la alerta).
**Resultado esperado:** La lista se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 4.3 — Ver más eventos
**Objetivo del paso:** Revisar eventos anteriores.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Mostrar 10 mas** al final de la lista.
**Resultado esperado:** Se agregan 10 eventos; al final aparece "No hay mas actividades".

**Resultado esperado de la práctica:** Conoce lo que pasó en las alertas de su alcance; es su fuente de avisos, porque su rol no recibe los correos de negocio.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce lo que pasó en las alertas de su alcance; es su fuente de avisos, porque su rol no recibe los correos de negocio.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 08 — Actividad 1 y lo resolvió.

#### Actividad 5 — Práctica: Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 08 — Actividad 2.

**Dónde:** Su bandeja de correo; los enlaces de los correos llevan a la plataforma.

**Datos de la práctica:** Correos generados en el ambiente de pruebas.

**Pasos:**

##### Paso 5.1 — Identificar el remitente y el asunto
**Objetivo del paso:** Distinguir los correos del sistema.
**Qué hacer:** En el ambiente de pruebas: Busque en su bandeja los asuntos que empiezan por "SI-CIPRAT" o "Notificación".
**Resultado esperado:** Identifica el tipo de correo según la tabla.

##### Paso 5.2 — Actuar según el correo
**Objetivo del paso:** No dejar vencer los plazos.
**Qué hacer:** En el ambiente de pruebas: Use los correos de acceso; para lo demás revise el panel Notificaciones y los módulos.
**Resultado esperado:** Atiende cada aviso en el módulo correspondiente.

**Resultado esperado de la práctica:** Sabe qué correos esperar y qué hacer con cada uno.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué correos esperar y qué hacer con cada uno.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 08 — Actividad 2 y lo resolvió.

#### Actividad 6 — Práctica: Activar la cuenta desde la invitación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

**Cuándo se hace y requisitos previos:** Secuencia E0.3; los mismos requisitos de Módulo 01 — Actividad 1.

**Dónde:** Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" › enlace › pantalla "Configura tu contraseña" (`/setup/:token`).

**Datos de la práctica:** Invitación de prueba enviada al correo del participante (Mock).

**Pasos:**

##### Paso 6.1 — Abrir el enlace de la invitación
**Objetivo del paso:** Llegar a la pantalla de activación con un enlace válido.
**Qué hacer:** En el ambiente de pruebas: Abra el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" y haga clic en el enlace. Hágalo antes de 7 días desde el envío.
**Resultado esperado:** Se abre "Configura tu contraseña". Si el enlace venció, aparece "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."

##### Paso 6.2 — Escribir la nueva contraseña
**Objetivo del paso:** Crear una contraseña que cumpla las reglas de seguridad.
**Qué hacer:** En el ambiente de pruebas: En **Nueva Contraseña** escriba al menos 8 caracteres e incluya un carácter especial (por ejemplo, # o !). Use el ícono del ojo para verificar lo escrito.
**Resultado esperado:** Los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial" se marcan como cumplidos.

##### Paso 6.3 — Confirmar la contraseña
**Objetivo del paso:** Evitar errores de digitación.
**Qué hacer:** En el ambiente de pruebas: En **Confirmar Contraseña** escriba exactamente la misma contraseña.
**Resultado esperado:** Si no coinciden, al enviar aparece "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."

##### Paso 6.4 — Activar la cuenta
**Objetivo del paso:** Dejar la cuenta en estado Activo.
**Qué hacer:** En el ambiente de pruebas: Revise que los dos campos coincidan y haga clic en **Activar cuenta**.
**Resultado esperado:** El botón muestra "Activando cuenta..." y luego la pantalla confirma; la cuenta queda Activa y puede iniciar sesión.

**Resultado esperado de la práctica:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 1 y lo resolvió.

#### Actividad 7 — Práctica: Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01 — Actividad 2.

**Dónde:** Dirección de la plataforma › **Iniciar sesión** (`/signin`) › "Inicia sesión en tu cuenta".

**Datos de la práctica:** Usuario de prueba de la ruta (consulta.departamentos.prueba@ejemplo.gov.co).

**Pasos:**

##### Paso 7.1 — Abrir la pantalla de ingreso
**Objetivo del paso:** Llegar al formulario de inicio de sesión.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de SI-CIPRAT en Chrome, Firefox o Edge actualizados y haga clic en **Iniciar sesión** (o abra directamente `/signin`).
**Resultado esperado:** Aparece "Inicia sesión en tu cuenta".

##### Paso 7.2 — Escribir correo y contraseña
**Objetivo del paso:** Identificarse ante el sistema.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional (el mismo de la invitación). En **Contraseña** escriba su contraseña.
**Resultado esperado:** Los campos quedan diligenciados. Si están vacíos, la pantalla muestra "Email is required" o "Password is required".

##### Paso 7.3 — Solicitar el código
**Objetivo del paso:** Validar credenciales y recibir el código de verificación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Iniciar Sesión**.
**Resultado esperado:** El botón muestra "Iniciando sesión..." y aparece "Revisa tu correo electrónico". Llega el correo "SI-CIPRAT - Código de Verificación". Si las credenciales no son correctas: "Credenciales inválidas".

##### Paso 7.4 — Escribir el código de 4 dígitos
**Objetivo del paso:** Comprobar que quien ingresa tiene acceso al correo.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y escriba los 4 dígitos, uno en cada casilla (solo acepta números; puede pegarlos). Si no llegó, espere un minuto, revise el correo no deseado y haga clic en **Haz clic para reenviar**.
**Resultado esperado:** Las 4 casillas quedan llenas.

##### Paso 7.5 — Validar el código
**Objetivo del paso:** Abrir la sesión.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Validar código**.
**Resultado esperado:** Entra a **Inicio** con el menú lateral de su rol. Si el código no coincide: "Código de autenticación inválido"; si pasó más de 1 hora: "Código expirado".

**Resultado esperado de la práctica:** Sesión abierta con el rol el usuario de Consulta — Departamentos y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sesión abierta con el rol el usuario de Consulta — Departamentos y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 2 y lo resolvió.

#### Actividad 8 — Práctica: Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01 — Actividad 6.

**Dónde:** Menú lateral › nombre del usuario › **Ver Perfil** (`/mi-perfil`).

**Datos de la práctica:** Usuario de prueba configurado con el alcance de la ruta.

**Pasos:**

##### Paso 8.1 — Abrir Mi perfil
**Objetivo del paso:** Llegar a la pantalla de datos de la cuenta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en su nombre al pie del menú lateral y luego en **Ver Perfil**.
**Resultado esperado:** Se abre Mi perfil con "Cargando perfil..." y luego sus datos.

##### Paso 8.2 — Revisar Información General
**Objetivo del paso:** Confirmar los datos personales registrados.
**Qué hacer:** En el ambiente de pruebas: Lea Nombres, Apellidos, Cargo, Área y Correo electrónico.
**Resultado esperado:** Los datos coinciden con los suyos; los campos no se pueden editar.

##### Paso 8.3 — Revisar Entidad y Acceso y Asignaciones
**Objetivo del paso:** Confirmar el alcance de datos.
**Qué hacer:** En el ambiente de pruebas: Verifique que el Rol diga "Consulta Departamentos" y que en **Departamentos** estén los que le corresponden.
**Resultado esperado:** Confirma que verá las alertas que tienen al menos un municipio en los departamentos asignados a su usuario.

**Resultado esperado de la práctica:** Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 6 y lo resolvió.

#### Actividad 9 — Práctica: Recuperar la contraseña

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.6; los mismos requisitos de Módulo 01 — Actividad 3.

**Dónde:** Pantalla de ingreso › **¿Has olvidado tu contraseña?** (`/forgot-password`) › correo "SI-CIPRAT - Restablecer Contraseña" › "Configurar nueva contraseña" (`/reset-password/:token`).

**Datos de la práctica:** Usuario de prueba consulta.departamentos.prueba@ejemplo.gov.co; contraseña nueva "Nueva#2026" (Mock).

**Pasos:**

##### Paso 9.1 — Abrir la recuperación
**Objetivo del paso:** Iniciar el proceso de cambio de contraseña.
**Qué hacer:** En el ambiente de pruebas: En la pantalla de ingreso haga clic en **¿Has olvidado tu contraseña?**.
**Resultado esperado:** Aparece "¿Olvidaste tu contraseña?".

##### Paso 9.2 — Escribir el correo
**Objetivo del paso:** Indicar a qué cuenta se enviará el enlace.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional y haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Revisa tu correo electrónico" y llega el correo "SI-CIPRAT - Restablecer Contraseña".

##### Paso 9.3 — Abrir el enlace del correo
**Objetivo del paso:** Llegar a la pantalla de nueva contraseña antes de que venza.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y haga clic en el enlace dentro de la hora siguiente.
**Resultado esperado:** Aparece "Configurar nueva contraseña". Si pasó más de 1 hora, al guardar aparece "Token inválido o expirado".

##### Paso 9.4 — Escribir y confirmar la nueva contraseña
**Objetivo del paso:** Definir una contraseña válida y distinta de las anteriores.
**Qué hacer:** En el ambiente de pruebas: Escriba en **Nueva Contraseña** al menos 8 caracteres con un carácter especial, distinta de sus últimas 5 contraseñas, y repítala en **Confirmar Contraseña**.
**Resultado esperado:** Los indicadores se marcan como cumplidos.

##### Paso 9.5 — Guardar la contraseña
**Objetivo del paso:** Dejar activa la nueva contraseña.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Contraseña restablecida — Tu contraseña se ha restablecido correctamente. Haz clic abajo para iniciar sesión." con el botón **Iniciar Sesión**.

**Resultado esperado de la práctica:** La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 3 y lo resolvió.

#### Actividad 10 — Práctica: Leer los indicadores del Inicio

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 1.

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25] y alertas Mock.

**Pasos:**

##### Paso 10.1 — Abrir Inicio
**Objetivo del paso:** Ver el tablero de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inicio** en el menú lateral.
**Resultado esperado:** Aparecen las tarjetas, el avance global, el ranking y el mapa.

##### Paso 10.2 — Leer las tarjetas y su tendencia
**Objetivo del paso:** Saber cuántas alertas hay y cómo cambió el último mes.
**Qué hacer:** En el ambiente de pruebas: Lea el valor grande de cada tarjeta y el número "vs ultimo mes".
**Resultado esperado:** Identifica, por ejemplo, que hay 2 alertas activas más que el mes anterior.

##### Paso 10.3 — Interpretar el Porcentaje de Avance Global
**Objetivo del paso:** Entender el avance de los planes de acción.
**Qué hacer:** En el ambiente de pruebas: Lea el porcentaje y la línea "X de Y actividades ejecutadas". Recuerde que es un promedio por alerta y no la división del total.
**Resultado esperado:** Puede explicar por qué el porcentaje puede ser distinto de X/Y.

**Resultado esperado de la práctica:** Interpreta el estado general de las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Interpreta el estado general de las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 1 y lo resolvió.

#### Actividad 11 — Práctica: Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 2.

**Dónde:** Menú lateral › **Inicio**.

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 11.1 — Abrir la última alerta
**Objetivo del paso:** Conocer la alerta activa más reciente.
**Qué hacer:** En el ambiente de pruebas: Lea el banner superior y haga clic en **Ver Alerta**.
**Resultado esperado:** Se abre la alerta en *Alertas tempranas*.

##### Paso 11.2 — Revisar el ranking de departamentos
**Objetivo del paso:** Saber dónde se concentran las alertas.
**Qué hacer:** En el ambiente de pruebas: Lea "Alertas por departamento" (Top 10).
**Resultado esperado:** Identifica los departamentos con más alertas y su porcentaje.

##### Paso 11.3 — Revisar las alertas recientes
**Objetivo del paso:** Ver lo último registrado.
**Qué hacer:** En el ambiente de pruebas: Recorra "Alertas recientes".
**Resultado esperado:** Ve las últimas alertas por fecha de la alerta.

##### Paso 11.4 — Usar el mapa
**Objetivo del paso:** Ubicar los municipios con alertas.
**Qué hacer:** En el ambiente de pruebas: Pase el cursor sobre un municipio coloreado; use la tabla accesible si prefiere leer los datos.
**Resultado esperado:** Aparece el nombre del municipio, el departamento y el número de alertas.

**Resultado esperado de la práctica:** Ubica geográficamente las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica geográficamente las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 2 y lo resolvió.

#### Actividad 12 — Práctica: Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 4.

**Dónde:** Dirección principal de SI-CIPRAT (`/`), sin iniciar sesión.

**Datos de la práctica:** Ventana privada del navegador.

**Pasos:**

##### Paso 12.1 — Abrir la vista pública
**Objetivo del paso:** Ver lo que ve la ciudadanía.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de la plataforma sin iniciar sesión (o en una ventana privada).
**Resultado esperado:** Aparece el tablero público con el botón **Iniciar sesión**.

##### Paso 12.2 — Comparar con su vista
**Objetivo del paso:** Entender la diferencia de alcance.
**Qué hacer:** En el ambiente de pruebas: Compare los totales con los de su Inicio con sesión, que se calculan sobre sus departamentos asignados.
**Resultado esperado:** Los totales públicos son nacionales y pueden ser mayores que los de su vista.

**Resultado esperado de la práctica:** Sabe qué información es pública y cuál depende de su sesión.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué información es pública y cuál depende de su sesión.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 4 y lo resolvió.

#### Actividad 13 — Práctica: Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03 — Actividad 1.

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Datos de la práctica:** Buscar "AT-013" [DATO REAL AT-013-25].

**Pasos:**

##### Paso 13.1 — Abrir Alertas tempranas
**Objetivo del paso:** Ver las alertas de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Alertas tempranas** en el menú lateral.
**Resultado esperado:** Aparecen "Cargando alertas..." y luego las tarjetas y la tabla.

##### Paso 13.2 — Leer las tarjetas
**Objetivo del paso:** Conocer los totales.
**Qué hacer:** En el ambiente de pruebas: Lea Total de alertas, Alertas activas y Alertas cerradas.
**Resultado esperado:** Conoce cuántas alertas hay en cada estado.

##### Paso 13.3 — Cambiar de pestaña
**Objetivo del paso:** Separar por tipo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inminencia** o **Estructurales**; **Todas** quita el filtro.
**Resultado esperado:** La tabla muestra solo ese tipo.

##### Paso 13.4 — Buscar una alerta
**Objetivo del paso:** Ir directo a una alerta.
**Qué hacer:** En el ambiente de pruebas: Escriba el número (por ejemplo "AT-013") o una palabra del tema en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; sin coincidencias: "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo."

##### Paso 13.5 — Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Tipo, Estado, Etiqueta y las listas del conflicto, y haga clic en **Aplicar filtros**. Para quitar, **Limpiar filtros**.
**Resultado esperado:** El botón Filtros muestra cuántos filtros están activos y la tabla se actualiza.

##### Paso 13.6 — Abrir el menú de acciones
**Objetivo del paso:** Saber qué puede hacer con cada alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ al final de la fila.
**Resultado esperado:** Aparecen Detalle, Recomendaciones e Historial de actividades; Editar y Eliminar están deshabilitados ("No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas").

**Resultado esperado de la práctica:** Ubica la alerta y sus datos principales.

**Lista de verificación:**
- [ ] Completó los 6 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica la alerta y sus datos principales.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 1 y lo resolvió.

#### Actividad 14 — Práctica: Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03 — Actividad 2.

**Dónde:** Alertas tempranas › fila › ⋯ › **Detalle**.

**Datos de la práctica:** Abrir la AT-013-2025 y revisar GUAVIARE › Miraflores (95200) [DATO REAL AT-013-25].

**Pasos:**

##### Paso 14.1 — Abrir el detalle
**Objetivo del paso:** Ver la ficha completa.
**Qué hacer:** En el ambiente de pruebas: En la fila, haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ficha en la pestaña Información general.

##### Paso 14.2 — Revisar Información general
**Objetivo del paso:** Conocer el avance y el tema.
**Qué hacer:** En el ambiente de pruebas: Lea Ejecutado / Programado, el estado del Plan de acción y la Descripción.
**Resultado esperado:** Conoce el avance y el estado del plan.

##### Paso 14.3 — Descargar el PDF
**Objetivo del paso:** Consultar el documento oficial.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el archivo de "PDF de la alerta".
**Resultado esperado:** Se descarga el PDF. Si no hay archivo, la alerta no tiene PDF cargado.

##### Paso 14.4 — Recorrer las demás pestañas
**Objetivo del paso:** Conocer el territorio, el conflicto y la población.
**Qué hacer:** En el ambiente de pruebas: Abra Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas.
**Resultado esperado:** Ve los municipios (con CAT, PNIS, PDET y Zona Fut.), los grupos armados, las conductas, las poblaciones y las subsunciones.

##### Paso 14.5 — Cerrar la ficha
**Objetivo del paso:** Volver al listado.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar**.
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Conoce la alerta completa.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la alerta completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 2 y lo resolvió.

#### Actividad 15 — Práctica: Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03 — Actividad 3.

**Dónde:** Alertas tempranas › fila › ⋯ › **Historial de actividades**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 15.1 — Abrir el historial
**Objetivo del paso:** Ver la trazabilidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Historial de actividades**.
**Resultado esperado:** Se abre la línea de tiempo de la alerta.

##### Paso 15.2 — Leer los eventos
**Objetivo del paso:** Reconstruir lo ocurrido.
**Qué hacer:** En el ambiente de pruebas: Recorra los eventos y use **Mostrar 10 mas** para ver los anteriores.
**Resultado esperado:** Identifica, por ejemplo, cuándo se confirmó el plan y quién lo hizo.

##### Paso 15.3 — Descargar un archivo del evento
**Objetivo del paso:** Ver el soporte de un cierre o informe.
**Qué hacer:** En el ambiente de pruebas: Si el evento tiene "Descargar archivo", haga clic.
**Resultado esperado:** Se descarga el archivo asociado.

**Resultado esperado de la práctica:** Conoce la trazabilidad de la alerta.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la trazabilidad de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 3 y lo resolvió.

#### Actividad 16 — Práctica: Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03 — Actividad 4.

**Dónde:** Alertas tempranas › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 16.1 — Aplicar los filtros que necesita
**Objetivo del paso:** Descargar solo lo útil.
**Qué hacer:** En el ambiente de pruebas: Use la pestaña, el buscador y **Filtros**.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 16.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; ábralo en Excel.

**Resultado esperado de la práctica:** Tiene el listado en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene el listado en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 4 y lo resolvió.

#### Actividad 17 — Práctica: Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2; los mismos requisitos de Módulo 03 — Actividad 5.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 17.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 17.2 — Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** En el ambiente de pruebas: Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Llega a las recomendaciones de la alerta.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Llega a las recomendaciones de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 5 y lo resolvió.

#### Actividad 18 — Práctica: Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04 — Actividad 1.

**Dónde:** Alertas tempranas › ⋯ › **Recomendaciones**.

**Datos de la práctica:** Recomendaciones de la AT-013-2025: RC-001-2025-013 a RC-041-2025-013 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 18.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver la lista.
**Qué hacer:** En el ambiente de pruebas: Desde la alerta, ⋯ › **Recomendaciones**.
**Resultado esperado:** Aparece "Cargando recomendaciones..." y luego la tabla.

##### Paso 18.2 — Buscar
**Objetivo del paso:** Encontrar una recomendación.
**Qué hacer:** En el ambiente de pruebas: Escriba el código (por ejemplo "RC-001") o una palabra en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra.

##### Paso 18.3 — Filtrar
**Objetivo del paso:** Ver por entidad, eje o modo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Entidad Principal, Eje Temático o Modo de Creación y **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo lo filtrado.

##### Paso 18.4 — Leer el avance
**Objetivo del paso:** Saber cómo va cada recomendación.
**Qué hacer:** En el ambiente de pruebas: Lea Actividades (Aprobadas / Total) y Ejecución.
**Resultado esperado:** Identifica las recomendaciones sin actividades o con bajo cumplimiento.

**Resultado esperado de la práctica:** Conoce las recomendaciones de la alerta y su avance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce las recomendaciones de la alerta y su avance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 1 y lo resolvió.

#### Actividad 19 — Práctica: Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04 — Actividad 2.

**Dónde:** Recomendaciones › fila › ⋯ › **Detalle**.

**Datos de la práctica:** RC-011-2025-013 ("Recomendación No. 12…") [DATO REAL AT-013-25].

**Pasos:**

##### Paso 19.1 — Abrir el detalle
**Objetivo del paso:** Ver la recomendación completa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ventana.

##### Paso 19.2 — Leer las entidades
**Objetivo del paso:** Saber quién responde y quién apoya.
**Qué hacer:** En el ambiente de pruebas: Lea la Entidad principal y las Entidades asociadas.
**Resultado esperado:** Identifica a la entidad responsable del plan y a las que apoyan.

**Resultado esperado de la práctica:** Conoce la recomendación completa.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la recomendación completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 2 y lo resolvió.

#### Actividad 20 — Práctica: Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, descargar las recomendaciones visibles en un archivo CSV.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04 — Actividad 3.

**Dónde:** Recomendaciones › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 20.1 — Filtrar
**Objetivo del paso:** Descargar lo necesario.
**Qué hacer:** En el ambiente de pruebas: Aplique búsqueda y filtros.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 20.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; si falla: "Error al descargar el archivo CSV. Por favor, intente nuevamente."

**Resultado esperado de la práctica:** Tiene las recomendaciones en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene las recomendaciones en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 3 y lo resolvió.

#### Actividad 21 — Práctica: Consultar el listado de Seguimiento y encontrar lo pendiente

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5; los mismos requisitos de Módulo 05 — Actividad 1.

**Dónde:** Menú lateral › **Seguimiento** (`/seguimiento`) — pantalla "Seguimiento de Planes".

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 21.1 — Abrir Seguimiento
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Seguimiento**.
**Resultado esperado:** Aparece "Seguimiento de Planes".

##### Paso 21.2 — Filtrar lo pendiente
**Objetivo del paso:** Encontrar el trabajo.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros**: Estado del Plan de Acción "Pendiente" (actividades por aprobar) o "Aprobado" (listo para confirmar); Estado del Informe "Pendiente" (informes por aprobar). **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo esos planes.

##### Paso 21.3 — Descargar el listado
**Objetivo del paso:** Llevar el control fuera de línea.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV.

##### Paso 21.4 — Entrar al plan
**Objetivo del paso:** Llegar a las actividades.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ir al plan de acción** y luego **Ver Actividades** en la recomendación.
**Resultado esperado:** Ve las actividades en modo de seguimiento.

**Resultado esperado de la práctica:** Sabe qué planes, actividades e informes requieren atención.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué planes, actividades e informes requieren atención.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 1 y lo resolvió.

#### Actividad 22 — Práctica: Consultar recomendaciones, actividades e informes en Seguimiento

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5; los mismos requisitos de Módulo 05 — Actividad 2.

**Dónde:** Seguimiento › **Ir al plan de acción** › **Ver Actividades** › ícono **Ver detalle** de la fila.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 22.1 — Abrir las actividades
**Objetivo del paso:** Llegar a la información.
**Qué hacer:** En el ambiente de pruebas: En Seguimiento haga clic en **Ir al plan de acción** › **Ver Actividades**.
**Resultado esperado:** Aparece la tabla de actividades.

##### Paso 22.2 — Abrir el detalle
**Objetivo del paso:** Leer la actividad y sus informes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono **Ver detalle** de la fila.
**Resultado esperado:** Se abre "Detalle de Actividad" con los informes de ejecución y su PDF.

##### Paso 22.3 — Leer los informes de ejecución
**Objetivo del paso:** Conocer lo reportado por la entidad.
**Qué hacer:** En el ambiente de pruebas: Baje a "Informes de ejecución" y descargue "Informe.pdf" si lo necesita.
**Resultado esperado:** Conoce lo ejecutado en cada ciclo.

**Resultado esperado de la práctica:** Conoce el estado de las actividades y sus informes.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el estado de las actividades y sus informes.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 2 y lo resolvió.

#### Actividad 23 — Práctica: Consultar los informes de seguimiento y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1; los mismos requisitos de Módulo 06 — Actividad 1.

**Dónde:** Menú lateral › **Informes de seguimiento** ("Encuentra los informes de seguimiento publicados por la defensoría").

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 23.1 — Abrir el módulo
**Objetivo del paso:** Ver los informes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Informes de seguimiento**.
**Resultado esperado:** Aparece "Cargando informes..." y luego la tabla; sin datos: "No hay informes de seguimiento — Los informes de seguimiento publicados por la defensoría aparecerán aquí."

##### Paso 23.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros** y elija la Alerta asociada (la lista muestra alertas cerradas: "No se encontraron alertas cerradas").
**Resultado esperado:** La tabla se filtra.

##### Paso 23.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el informe.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalle** y luego en **Descargar**.
**Resultado esperado:** Se abre el detalle y se descarga el PDF.

**Resultado esperado de la práctica:** Conoce los informes de seguimiento.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los informes de seguimiento.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 1 y lo resolvió.

#### Actividad 24 — Práctica: Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Consulta — Departamentos pueda practicar, en el ambiente de pruebas, encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.2; los mismos requisitos de Módulo 07 — Actividad 1.

**Dónde:** Menú lateral › **Oficios de consumación** ("Encuentra los oficios de consumación emitidos por la defensoría").

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 24.1 — Abrir el módulo
**Objetivo del paso:** Ver los oficios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Oficios de consumación**.
**Resultado esperado:** Aparece la tabla; sin datos: "No hay oficios de consumación — Los oficios de consumación emitidos por la defensoría aparecerán aquí."

##### Paso 24.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros** y elija la Alerta asociada.
**Resultado esperado:** La tabla se filtra.

##### Paso 24.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el oficio.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalle** y en **Descargar**.
**Resultado esperado:** Se descarga el PDF.

**Resultado esperado de la práctica:** Conoce los oficios de consumación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los oficios de consumación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 07 — Actividad 1 y lo resolvió.

## Alcance y límites

- Alcance de datos: las alertas que tienen al menos un municipio en los departamentos asignados a su usuario.
- Acciones que comparte con otros roles (cada uno con su alcance): iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad.
- ⚠️ Acciones irreversibles que puede hacer: activar la cuenta desde la invitación.
- Módulos a los que no tiene acceso: Usuarios y entidades, Agentes IA, Planes de acción, Informe de recomendaciones, Reportes.
- No puede: cambiar la contraseña con la contraseña actual; editar los datos del propio perfil; consultar el historial de cambios de contraseña; listar usuarios e invitaciones; buscar y filtrar usuarios; ver el detalle de un usuario; invitar un usuario; invitar un super administrador; editar un usuario; activar o inactivar un usuario; reenviar una invitación; eliminar una invitación; listar entidades centrales y subdirecciones; buscar y filtrar entidades; ver el detalle de una entidad; y las demás de la tabla "Qué NO puede hacer".
- La pantalla no le muestra los comentarios de revisión de las actividades: esa conversación es entre la Entidad Territorial y quien aprueba.

## Indicadores de logro

- [ ] Puede activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace (Módulo 01 — Actividad 1).
- [ ] Puede ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo (Módulo 01 — Actividad 2).
- [ ] Puede crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo (Módulo 01 — Actividad 3).
- [ ] Puede cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo (Módulo 01 — Actividad 4).
- [ ] Puede conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema (Módulo 01 — Actividad 5).
- [ ] Puede verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve (Módulo 01 — Actividad 6).
- [ ] Puede interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance (Módulo 02 — Actividad 1).
- [ ] Puede ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa (Módulo 02 — Actividad 2).
- [ ] Puede moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra (Módulo 02 — Actividad 3).
- [ ] Puede reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión (Módulo 02 — Actividad 4).
- [ ] Puede revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo) (Módulo 08 — Actividad 1).
- [ ] Puede identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno (Módulo 08 — Actividad 2).
- [ ] Puede encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros (Módulo 03 — Actividad 1).
- [ ] Puede leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF (Módulo 03 — Actividad 2).
- [ ] Puede saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre) (Módulo 03 — Actividad 3).
- [ ] Puede descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados (Módulo 03 — Actividad 4).
- [ ] Puede pasar de una alerta a su lista de recomendaciones (Módulo 03 — Actividad 5).
- [ ] Puede ver las recomendaciones de una alerta con su entidad, sus actividades y su avance (Módulo 04 — Actividad 1).
- [ ] Puede leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas (Módulo 04 — Actividad 2).
- [ ] Puede descargar las recomendaciones visibles en un archivo CSV (Módulo 04 — Actividad 3).
- [ ] Puede ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance (Módulo 05 — Actividad 1).
- [ ] Puede leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución (Módulo 05 — Actividad 2).
- [ ] Puede encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento (Módulo 06 — Actividad 1).
- [ ] Puede encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento (Módulo 07 — Actividad 1).

## Preguntas frecuentes de uso

### Mi rol y lo que veo

**¿Qué puedo hacer con mi rol?**
Rol de solo lectura. Consulta alertas, recomendaciones, planes de acción, seguimiento, informes de seguimiento y oficios de consumación, y descarga archivos y listados, sin crear, editar ni aprobar registros de negocio. En la plataforma puede, entre otras: iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad. *Se explica en: Módulo 00 — Actividad 3.*

**¿Qué información veo y por qué?**
Ve las alertas que tienen al menos un municipio en los departamentos asignados a su usuario. El sistema aplica ese filtro en el servidor según los datos de su usuario. *Se explica en: Módulo 01 — Actividad 6.*

**¿Por qué mi rol es Consulta — Departamentos?**
Usuario de consulta limitado a uno o varios departamentos. El sistema lo identifica con el valor `CONSULTA_DEPARTAMENTOS` y la lista de departamentos de su usuario. *Se explica en: Módulo 00 — Actividad 3.*

**¿Cómo verifico con qué datos fui configurado?**
En **Ver Perfil** (Mi perfil) revise Rol, Nivel de Acceso, Entidad Central, Subdirección y Departamentos. Si algo no corresponde, pida la corrección a quien administra los usuarios. *Se explica en: Módulo 01 — Actividad 6.*

### Módulos y funcionalidades

**¿Para qué sirve el módulo Acceso a la plataforma?**
Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. *Se explica en: Módulo 01 — Actividad 1.*

**¿Para qué sirve el módulo Inicio?**
Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. Tablero de entrada de la plataforma. *Se explica en: Módulo 02 — Actividad 1.*

**¿Para qué sirve el módulo Alertas tempranas?**
Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. *Se explica en: Módulo 03 — Actividad 1.*

**¿Para qué sirve el módulo Recomendaciones?**
Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). *Se explica en: Módulo 04 — Actividad 1.*

**¿Para qué sirve el módulo Seguimiento?**
Revisar y aprobar el plan de acción y su ejecución, actividad por actividad, hasta confirmar el plan y aprobar cada informe. Módulo "Seguimiento de Planes": usa las mismas pantallas de Planes de acción en modo de seguimiento. *Se explica en: Módulo 05 — Actividad 1.*

**¿Para qué sirve el módulo Informes de seguimiento?**
Dejar en el sistema cada informe de seguimiento de la Defensoría y aplicar sus efectos sobre la alerta (municipios, recomendaciones nuevas o cierre). Módulo donde se registran los informes de seguimiento que emite la Defensoría sobre una alerta. *Se explica en: Módulo 06 — Actividad 1.*

**¿Para qué sirve el módulo Oficios de consumación?**
Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. *Se explica en: Módulo 07 — Actividad 1.*

**¿Para qué sirve el módulo Notificaciones?**
Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).. *Se explica en: Módulo 08 — Actividad 1.*

**¿Cuándo debo consultar, buscar y filtrar alertas tempranas?**
En la secuencia E1–E6 del ciclo. Ubica la alerta y sus datos principales.. *Se explica en: Módulo 03 — Actividad 1.*

**¿Cuándo debo ver el detalle de una alerta y descargar su PDF?**
En la secuencia E1–E6 del ciclo. Conoce la alerta completa.. *Se explica en: Módulo 03 — Actividad 2.*

**¿Cuándo debo consultar el historial de actividades de una alerta?**
En la secuencia E1–E6 del ciclo. Conoce la trazabilidad de la alerta.. *Se explica en: Módulo 03 — Actividad 3.*

**¿Cuándo debo descargar el listado de alertas en CSV?**
En la secuencia E1–E6 del ciclo. Tiene el listado en un archivo.. *Se explica en: Módulo 03 — Actividad 4.*

**¿Cuándo debo ir a las recomendaciones de una alerta?**
En la secuencia E2 del ciclo. Llega a las recomendaciones de la alerta.. *Se explica en: Módulo 03 — Actividad 5.*

**¿Cuándo debo consultar, buscar y filtrar las recomendaciones de una alerta?**
En la secuencia E2–E6 del ciclo. Conoce las recomendaciones de la alerta y su avance.. *Se explica en: Módulo 04 — Actividad 1.*

**¿Cuándo debo ver el detalle de una recomendación?**
En la secuencia E2–E6 del ciclo. Conoce la recomendación completa.. *Se explica en: Módulo 04 — Actividad 2.*

**¿Cuándo debo descargar las recomendaciones de una alerta en CSV?**
En la secuencia E2–E6 del ciclo. Tiene las recomendaciones en un archivo.. *Se explica en: Módulo 04 — Actividad 3.*

**¿Cuándo debo consultar el listado de Seguimiento y encontrar lo pendiente?**
En la secuencia E4–E5 del ciclo. Sabe qué planes, actividades e informes requieren atención.. *Se explica en: Módulo 05 — Actividad 1.*

**¿Cuándo debo consultar recomendaciones, actividades e informes en Seguimiento?**
En la secuencia E4–E5 del ciclo. Conoce el estado de las actividades y sus informes.. *Se explica en: Módulo 05 — Actividad 2.*

**¿Cuándo debo consultar los informes de seguimiento y descargar su PDF?**
En la secuencia E6.1 del ciclo. Conoce los informes de seguimiento.. *Se explica en: Módulo 06 — Actividad 1.*

**¿Cuándo debo consultar los oficios de consumación y descargar su PDF?**
En la secuencia E6.2 del ciclo. Conoce los oficios de consumación.. *Se explica en: Módulo 07 — Actividad 1.*

### Ciclo de la alerta y estados

**¿Qué significa el estado "Borrador"?**
Alerta creada por el Agente IA o por X-Road que aún no se publica; no cuenta en los indicadores. *Se explica en: Módulo 03 — Actividad 1.*

**¿Qué significa el estado "Activa"?**
Alerta vigente sobre la que se trabajan recomendaciones, plan e informes. *Se explica en: Módulo 03 — Actividad 1.*

**¿Qué significa el estado "Cerrada"?**
Alerta terminada; no se edita ni se reabre. *Se explica en: Módulo 03 — Actividad 1.*

**¿Qué significa el estado "Sin plan"?**
Ninguna recomendación de la alerta tiene actividades. *Se explica en: Módulo 05 — Actividad 1.*

**¿Qué significa el estado "Pendiente"?**
Hay actividades (o informes) por aprobar. *Se explica en: Módulo 05 — Actividad 1.*

**¿Qué significa el estado "Aprobado"?**
Todas las actividades están aprobadas; el plan se puede confirmar. *Se explica en: Módulo 05 — Actividad 1.*

**¿Qué significa el estado "Sin Informe"?**
La actividad debe reportar el informe del ciclo. *Se explica en: Módulo 05 — Actividad 1.*

**¿Qué pasa después de que se confirma el plan de acción?**
Las actividades quedan "Sin Informe", la Entidad Territorial recibe el correo de validación y puede reportar informes de ejecución; la alerta, sus recomendaciones y actividades ya no se editan. *Se explica en: Módulo 00 — Actividad 2.*

**¿Qué pasa si una entidad agrega una actividad a un plan confirmado?**
El plan se desconfirma: vuelve a "Pendiente", la nueva actividad debe aprobarse y el plan debe confirmarse otra vez. Lo existente no cambia. *Se explica en: Módulo 00 — Actividad 2.*

### Lo que puedo y no puedo hacer

**¿Puedo reportar una alerta temprana?**
No. UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin`. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo eliminar una alerta?**
No. UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin`. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cerrar alertas?**
No. UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin`. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo agregar una recomendación?**
No. UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin`. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo agregar una actividad?**
No. UI: el menú no muestra *Planes de acción*. Lo hace: La Entidad Territorial responsable de la recomendación. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo reportar un informe de ejecución?**
No. UI: el menú no muestra *Planes de acción*. Lo hace: La Entidad Territorial responsable. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar una actividad?**
No. UI y API: el botón no se muestra y no tiene el permiso. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo confirmar el plan de acción?**
No. UI y API: el botón no se muestra y no tiene el permiso. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar un informe de ejecución?**
No. UI y API: el botón no se muestra y no tiene el permiso. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un reporte de ejecución?**
No. UI y API: sin menú, ruta bloqueada y `RequireReportes`. Lo hace: Pida la información a un Monitor, Líder de Macrozona o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar un reporte de ejecución?**
No. UI y API: sin menú, ruta bloqueada y `RequireReportes`. Lo hace: El aprobador designado (Líder de Macrozona o Super Administrador). *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un informe de seguimiento?**
No. UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento`. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un oficio de consumación?**
No. UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación". Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo invitar un usuario?**
No. UI y API: sin menú, `AdminRoute` y `RequireAdmin`. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo adjuntar el PDF de la alerta y el Adjunto?**
No. UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin`. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo ver y escribir comentarios de una actividad?**
No. UI: el botón **Comentarios** solo aparece a quien formula actividades en Planes de acción o aprueba en Seguimiento. Lo hace: La Entidad Territorial, el Monitor o el Líder de Macrozona. *Se explica en: Matriz de capacidades de esta ruta.*

### Plazos y vigencias

**¿Cuánto dura la invitación?**
7 días desde el envío. Por ejemplo, si se envió el 2 de febrero de 2026, sirve hasta el 9 de febrero de 2026. *Se explica en: Módulo 01 — Actividad 1.*

**¿Cuánto dura el código de verificación?**
1 hora. Si llega a las 8:05 a. m., sirve hasta las 9:05 a. m. *Se explica en: Módulo 01 — Actividad 2.*

**¿Cuánto dura mi sesión?**
Se cierra a los 60 minutos sin actividad y vence a los 720 minutos (12 horas). *Se explica en: Módulo 01 — Actividad 4.*

**¿Cada cuánto se reportan los informes de ejecución?**
Cada 6 meses por actividad. El primer próximo informe se fija al aprobar el primer informe: fecha de notificación de la alerta + 6 meses (para la AT-013-2025, notificada el 07/10/2025, el 07/04/2026 [DATO REAL AT-013-25]); luego +6 meses sobre el anterior. *Se explica en: Módulo 00 — Actividad 2.*

**¿El plazo de implementación de una actividad genera vencimientos?**
No. Es informativo (1 a 3, 3 a 6, 6 a 9 meses o Permanente); los vencimientos solo los genera el Próximo Informe. *Se explica en: Módulo 05 — Actividad 2.*

### Notificaciones

**¿Qué avisos voy a recibir y qué debo hacer con cada uno?**
Solo los correos de acceso (invitación, código y restablecimiento). Lo demás lo ve en el panel Notificaciones. *Se explica en: Módulo 08 — Actividad 2.*

**¿Qué muestra el panel Notificaciones?**
El historial de actividad de las alertas de su alcance: quién hizo qué, cuándo y sobre qué alerta. No tiene marcas de leído. *Se explica en: Módulo 08 — Actividad 1.*

### Indicadores

**¿Cómo se calcula el % de cumplimiento?**
Actividades ejecutadas ÷ programadas × 100. Ejemplo: 3 ejecutadas de 4 programadas = 75 %. Cada 6 meses la meta se suma otra vez a lo programado: con 4 actividades por ciclo, en el segundo ciclo son 8 programadas. *Se explica en: Módulo 05 — Actividad 2.*

**¿Cómo se calcula el "Porcentaje de Avance Global" del Inicio?**
Es el promedio del % de cumplimiento de cada alerta (no borrador) de su alcance; las alertas sin actividades cuentan como 0 %. Con A = 50 % y B = 100 %, el avance es 75 %. *Se explica en: Módulo 02 — Actividad 1.*

### Datos y formularios

**¿Qué campos son obligatorios en "Activar la cuenta (Configura tu contraseña)"?**
Nueva Contraseña; Confirmar Contraseña. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01 — Actividad 1.*

**¿Qué campos son obligatorios en "Iniciar sesión"?**
Correo electrónico; Contraseña; Código de verificación (4 casillas). Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01 — Actividad 2.*

**¿Qué campos son obligatorios en "Solicitar el restablecimiento"?**
Correo electrónico. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01 — Actividad 3.*

**¿Qué campos son obligatorios en "Configurar nueva contraseña"?**
Nueva Contraseña; Confirmar Contraseña. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01 — Actividad 3.*

## Errores frecuentes y cómo solucionarlos

### Acceso y sesión

**Me aparece «El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador.»**
**Causa:** La invitación vence a los 7 días. **Solución:** Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Active la cuenta apenas reciba el correo. *Relacionado con: Módulo 01 — Actividad 1 (ERR-ACC-06).*

**Me aparece «El enlace de invitación es inválido. Verifica que el enlace esté completo.»**
**Causa:** El enlace se cortó al copiarlo o la cuenta ya se activó. **Solución:** Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** No copie el enlace a mano. *Relacionado con: Módulo 01 — Actividad 1 (ERR-ACC-07).*

**Me aparece «Credenciales inválidas»**
**Causa:** El correo no existe o la contraseña no corresponde. **Solución:** Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** No comparta ni anote la contraseña en lugares visibles. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-01).*

**Me aparece «Código de autenticación inválido»**
**Causa:** El código no coincide con el último enviado. **Solución:** Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use siempre el código del correo más reciente. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-02).*

**Me aparece «Código expirado»**
**Causa:** El código vence 1 hora después de enviado. **Solución:** Haga clic en **Haz clic para reenviar** y use el código nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Ingrese el código apenas llegue. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-03).*

**Me aparece «Cuenta no activa»**
**Causa:** El administrador cambió el estado del usuario a Inactivo. **Solución:** Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). **Si no se resuelve:** Super Administrador o Administrador de la plataforma **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-04).*

**No llega el correo con el código y no aparece ningún mensaje**
**Causa:** El correo puede estar en la carpeta de correo no deseado o tardar en llegar. **Solución:** Revise la carpeta de correo no deseado; espere un minuto y use **Haz clic para reenviar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co) **Cómo prevenirlo:** Agregue el remitente de SI-CIPRAT a sus contactos. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-14).*

**Me aparece «Token inválido o expirado»**
**Causa:** El enlace de restablecimiento vence en 1 hora. **Solución:** Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use el enlace apenas llegue. *Relacionado con: Módulo 01 — Actividad 3 (ERR-ACC-11).*

**Me aparece «Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente.»**
**Causa:** Cierre automático por inactividad de 60 minutos. **Solución:** Inicie sesión de nuevo (correo, contraseña y código). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Guarde los formularios antes de dejar el equipo. *Relacionado con: Módulo 01 — Actividad 4 (ERR-ACC-12).*

**Me aparece «Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente.»**
**Causa:** El token de la sesión venció (720 minutos) o no es válido. **Solución:** Inicie sesión de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01 — Actividad 4 (ERR-ACC-13).*

### Formularios

**Me aparece «Debe tener al menos 8 caracteres»**
**Causa:** La contraseña no cumple las reglas. **Solución:** Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los indicadores de la pantalla antes de enviar. *Relacionado con: Módulo 01 — Actividad 1 (ERR-ACC-08).*

**Me aparece «Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente.»**
**Causa:** Los dos campos no coinciden. **Solución:** Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01 — Actividad 1 (ERR-ACC-09).*

**Me aparece «No puedes reutilizar ninguna de tus últimas 5 contraseñas»**
**Causa:** El sistema guarda el historial de contraseñas. **Solución:** Elija una contraseña distinta de las 5 anteriores. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01 — Actividad 3 (ERR-ACC-10).*

**Me aparece «La solicitud no es válida. Verifica los datos e intenta de nuevo.»**
**Causa:** Errores 400 o 422 de validación. **Solución:** Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Lea la ayuda de cada campo. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-13).*

### Permisos y alcance

**Encontrar en Mi perfil un rol, entidad, subdirección o departamentos que no corresponden y no aparece ningún mensaje**
**Causa:** El usuario fue configurado con otros datos; Mi perfil no permite editarlos. **Solución:** Pida la corrección a quien administra los usuarios, indicando el dato correcto. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise Mi perfil después del primer ingreso. *Relacionado con: Módulo 01 — Actividad 6 (ERR-ACC-15).*

**Me aparece «No tienes permisos para realizar esta acción.»**
**Causa:** El servidor rechaza la operación para el rol (403). **Solución:** Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co) con la pantalla, la hora y una captura **Cómo prevenirlo:** Use solo los botones habilitados para su rol. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-01).*

**Me aparece Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No tienes permisos para cerrar alertas"**
**Causa:** Su rol solo consulta alertas. **Solución:** Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 1 (ERR-ALE-17).*

**Me aparece Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para eliminar recomendaciones"**
**Causa:** Solo el Super Administrador y el Administrador las registran. **Solución:** Pida el cambio a la Secretaría Técnica. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 1 (ERR-REC-06).*

**Me aparece Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado****
**Causa:** Su rol solo consulta en Seguimiento. **Solución:** La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 1 (ERR-SEG-07).*

**Me aparece «Error al cargar el informe de recomendaciones»**
**Causa:** El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. **Solución:** Pida el consolidado al Monitor o a la Secretaría Técnica. **Si no se resuelve:** Monitor, Líder de Macrozona o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 1 (ERR-SEG-14).*

**Me aparece Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes"**
**Causa:** Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. **Solución:** Pida la carga a la Secretaría Técnica. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06 — Actividad 1 (ERR-ISE-07).*

**Me aparece Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"**
**Causa:** Solo el Super Administrador gestiona oficios. **Solución:** Pida la carga al Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07 — Actividad 1 (ERR-OFI-02).*

**No veo, o aparece deshabilitada, la opción para cambiar la contraseña con la contraseña actual**
**Causa:** Su rol no tiene esta funcionalidad: UI: no existe una pantalla que use este servicio (`main-api/CipratApi/Controladores/AutenticacionControlador.cs:147`; solo `dashboard/src/contexts/AuthContext.tsx` lo referencia). **Solución:** No es un error de la plataforma. La realiza: Use **¿Has olvidado tu contraseña?** para cambiarla. **Si no se resuelve:** Use **¿Has olvidado tu contraseña?** para cambiarla **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-11).*

**No veo, o aparece deshabilitada, la opción para editar los datos del propio perfil**
**Causa:** Su rol no tiene esta funcionalidad: UI: los campos de Mi perfil están deshabilitados (`dashboard/src/pages/MyProfile.tsx:124-183`). **Solución:** No es un error de la plataforma. La realiza: Pida el cambio a quien administra los usuarios (Super Administrador o Administrador). **Si no se resuelve:** Pida el cambio a quien administra los usuarios (Super Administrador o Administrador) **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-13).*

**No veo, o aparece deshabilitada, la opción para consultar el historial de cambios de contraseña**
**Causa:** Su rol no tiene esta funcionalidad: UI: el hook `usePasswordHistory` existe, pero Mi perfil no lo muestra (`dashboard/src/hooks/usePasswordHistory.ts:20`, `dashboard/src/pages/MyProfile.tsx`). **Solución:** No es un error de la plataforma. La realiza: No disponible en la interfaz. **Si no se resuelve:** No disponible en la interfaz **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-14).*

**No veo, o aparece deshabilitada, la opción para reportar una alerta temprana**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-08).*

**No veo, o aparece deshabilitada, la opción para adjuntar el PDF de la alerta y el Adjunto**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-09).*

**No veo, o aparece deshabilitada, la opción para editar una alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-10).*

**No veo, o aparece deshabilitada, la opción para cambiar el número de una alerta manual**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-11).*

**No veo, o aparece deshabilitada, la opción para publicar una alerta en borrador**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-12).*

**No veo, o aparece deshabilitada, la opción para subsumir otras alertas**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-13).*

**No veo, o aparece deshabilitada, la opción para eliminar una alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-14).*

**No veo, o aparece deshabilitada, la opción para reemplazar o eliminar los archivos de la alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-15).*

**No veo, o aparece deshabilitada, la opción para cerrar alertas**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-ALE-16).*

**No veo, o aparece deshabilitada, la opción para agregar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-REC-05).*

**No veo, o aparece deshabilitada, la opción para editar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-REC-06).*

**No veo, o aparece deshabilitada, la opción para eliminar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-REC-07).*

**No veo, o aparece deshabilitada, la opción para marcar una actividad como revisada**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-05).*

**No veo, o aparece deshabilitada, la opción para aprobar una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-06).*

**No veo, o aparece deshabilitada, la opción para descartar la aprobación de una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-07).*

**No veo, o aparece deshabilitada, la opción para validar si el plan se puede confirmar**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-08).*

**No veo, o aparece deshabilitada, la opción para confirmar el plan de acción**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-09).*

**No veo, o aparece deshabilitada, la opción para aprobar un informe de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón no se muestra y no tiene el permiso (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:100-105`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-SEG-10).*

**No veo, o aparece deshabilitada, la opción para cargar un informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-ISE-05).*

**No veo, o aparece deshabilitada, la opción para modificar municipios y agregar recomendaciones desde el informe**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-ISE-06).*

**No veo, o aparece deshabilitada, la opción para cerrar la alerta con el informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-ISE-07).*

**No veo, o aparece deshabilitada, la opción para editar un informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-ISE-08).*

**No veo, o aparece deshabilitada, la opción para eliminar un informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar informes") y sin permiso `CrearInformeSeguimiento` (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:54-58`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-ISE-09).*

**No veo, o aparece deshabilitada, la opción para cargar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-OFI-05).*

**No veo, o aparece deshabilitada, la opción para modificar municipios y agregar recomendaciones desde el oficio**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-OFI-06).*

**No veo, o aparece deshabilitada, la opción para editar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-OFI-07).*

**No veo, o aparece deshabilitada, la opción para eliminar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-OFI-08).*

### Estados

**Me aparece «Conflicto con el estado actual del recurso.»**
**Causa:** Otro usuario o una acción anterior cambió el estado del registro (409). **Solución:** Actualice la página, revise el estado actual y repita la acción si todavía aplica. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Evite el doble clic y trabaje sobre la información recién cargada. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-03).*

### Integraciones

**Esperar un correo de negocio (recomendación, plan, recordatorio) y no aparece ningún mensaje**
**Causa:** Los correos de negocio solo se envían a usuarios de Entidad Territorial. **Solución:** Consulte los cambios en el panel **Notificaciones** y en los módulos. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise el panel Notificaciones al iniciar el día. *Relacionado con: Módulo 08 — Actividad 2 (ERR-NOT-02).*

**Una alerta emitida por la Defensoría no aparece en SI-CIPRAT y no aparece ningún mensaje**
**Causa:** La alerta aún no llega por X-Road o el mensaje fue rechazado por el servidor. **Solución:** Informe a la Secretaría Técnica; el Super Administrador o el Administrador pueden registrarla con **Reportar alerta** si se confirma que no llegará. **Si no se resuelve:** Super Administrador / equipo técnico de interoperabilidad **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 1 (ERR-INT-01).*

### Sistema y conexión

**Me aparece «No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo.»**
**Causa:** Sin conexión o red bloqueada. **Solución:** Revise la conexión, recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Trabaje con conexión estable; los Términos de uso la exigen. *Relacionado con: Módulo 01 — Actividad 2 (ERR-GEN-06).*

**Me aparece «Error al cargar datos»**
**Causa:** Falla del servicio del tablero. **Solución:** Recargue la página; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 1 (ERR-INI-01).*

**Me aparece «Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio.»**
**Causa:** Los formularios de registro se bloquean en pantallas pequeñas. **Solución:** Use un computador de escritorio o portátil. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Planee el registro desde un computador. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-11).*

**Me aparece «El servidor no está disponible. Por favor, intenta más tarde.»**
**Causa:** Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). **Solución:** Espere unos minutos e intente de nuevo. **Si no se resuelve:** Soporte técnico si dura más de 30 minutos **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-05).*

**Me aparece «Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 1 (ERR-ALE-19).*

**Me aparece «El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose.»**
**Causa:** El registro fue eliminado o el servidor no responde (404). **Solución:** Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. **Si no se resuelve:** Soporte técnico, con el número de la alerta y la hora **Cómo prevenirlo:** No use enlaces antiguos guardados en el navegador. *Relacionado con: Módulo 03 — Actividad 2 (ERR-GEN-02).*

**Me aparece «Error interno del servidor. Por favor, intenta más tarde.»**
**Causa:** Error 500 del servidor. **Solución:** Espere unos minutos e intente de nuevo; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico, con la pantalla, la acción, la hora y una captura **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 3 (ERR-GEN-04).*

**Me aparece «Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo.»**
**Causa:** Falla al generar el archivo o al conectarse. **Solución:** Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Filtre antes de descargar. *Relacionado con: Módulo 03 — Actividad 4 (ERR-GEN-10).*

**Me aparece «Error al cargar las recomendaciones. Por favor, intente nuevamente.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 1 (ERR-REC-07).*

**Me aparece «Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06 — Actividad 1 (ERR-ISE-09).*

**Me aparece «Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07 — Actividad 1 (ERR-OFI-05).*

### Sin resultados

**Me aparece «No hay datos de departamentos»**
**Causa:** No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. **Solución:** Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 1 (ERR-INI-02).*

**Me aparece «Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida.»**
**Causa:** La ruta no existe. **Solución:** Haga clic en **Volver al inicio** y navegue desde el menú. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use el menú lateral. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-12).*

**Me aparece «No hay notificaciones»**
**Causa:** No hay acciones registradas en las alertas de su alcance. **Solución:** No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 08 — Actividad 1 (ERR-NOT-01).*

**No encontrar una alerta que esperaba ver y no aparece ningún mensaje**
**Causa:** La alerta está fuera de su alcance (departamentos o entidad), es un borrador o no existe. **Solución:** Revise su alcance en **Ver Perfil**; si la alerta le corresponde, pida el ajuste de su usuario o de la recomendación. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 1 (ERR-ALE-18).*

**Me aparece «No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo.»**
**Causa:** No hay registros que cumplan la búsqueda dentro de su alcance. **Solución:** Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque por número de alerta o código. *Relacionado con: Módulo 03 — Actividad 1 (ERR-GEN-07).*

**Me aparece «La alerta solicitada no existe o ha sido eliminada.»**
**Causa:** La alerta ya no existe. **Solución:** Vuelva con **Volver a Alertas Tempranas**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 5 (ERR-REC-08).*

**Me aparece «No hay alertas con planes de acción»**
**Causa:** No hay alertas con municipios en sus departamentos, o su usuario no tiene departamentos. **Solución:** Revise sus departamentos en **Ver Perfil** y pida el ajuste si hace falta. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 1 (ERR-SEG-13).*

## Glosario de la ruta

### Botón

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| ¿Has olvidado tu contraseña? | botón | Inicia la recuperación de la contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Activar cuenta | botón | Crea la contraseña y activa la cuenta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Agregar recomendación | botón | Abre el registro de una recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Aplicar filtros | botón | Aplica los filtros elegidos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Aprobar | botón | Aprueba la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Aprobar Informe | botón | Aprueba el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Asociar entidades | botón | Agrega entidades asociadas a la Entidad Principal. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Atrás | botón | Regresa al paso anterior. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Cancelar | botón | Cierra sin guardar. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Cargar informe | botón | Abre la carga (reporte de ejecución o informe de seguimiento). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Cargar oficio | botón | Abre o guarda la carga de un oficio. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Cerrar alertas | botón | Abre el cierre de alertas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Comentarios | botón | Abre la conversación de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Confirmar | botón | Confirma la acción de la ventana. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Confirmar Plan de Acción | botón | Abre la confirmación del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Crear nuevo registro | botón | Registra otra revisión de la misma actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Crear recomendación | botón | Guarda la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Descargar | botón | Descarga el listado en CSV o el archivo. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Descartar aprobación | botón | Devuelve la actividad aprobada a pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Editar informe | botón | Edita el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Eliminar informe | botón | Elimina el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Enviar Alerta | botón | Guarda la alerta nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Filtros | botón | Abre los filtros del listado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Guardar Cambios | botón | Guarda la edición (alerta o usuario). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Haz clic para reenviar | botón | Envía un nuevo código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Informe | botón | Abre el Informe de recomendaciones. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Iniciar Sesión | botón | Valida correo y contraseña y envía el código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Ir al plan de acción | botón | Abre las recomendaciones del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Limpiar filtros | botón | Quita todos los filtros. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Marcar como Revisado | botón | Deja constancia de la revisión (no cambia el estado). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Mostrar 10 mas | botón | Carga 10 registros más. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 08 — Actividad 1 |
| Reportar alerta | botón | Abre el registro manual de una alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Restablecer contraseña | botón | Envía el enlace o guarda la nueva contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Siguiente | botón | Avanza al siguiente paso del asistente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Validar código | botón | Valida el código de 4 dígitos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Ver Actividades | botón | Abre las actividades de la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Ver Alerta | botón | Abre la última alerta del banner. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 02 — Actividad 1 |
| Ver detalle | botón | Abre el detalle del registro. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |

### Campo

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| % cumplimiento | campo | Ejecutadas ÷ programadas × 100. | Indicador de avance de actividad, recomendación y alerta. | Módulo 05 — Actividad 1 |
| Código de verificación (4 casillas) | campo | Número (4 dígitos, uno por casilla). Solo dígitos 0-9; vigente 1 hora | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Código RC | campo | Código de la recomendación RC-{NNN}-{AAAA}-{NNN}. | Lo asigna el sistema; no corresponde al número de la recomendación en el documento. | Módulo 04 — Actividad 1 |
| Confirmar Contraseña | campo | Texto oculto. Igual a Nueva Contraseña | Obligatorio: Sí. | Módulo 01 — Actividad 1 |
| Contraseña | campo | Texto oculto. La contraseña vigente | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Correo electrónico | campo | Texto (correo). Formato de correo | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Creación: Manual / Automática | campo | Cómo se creó la alerta o la recomendación. | Las automáticas vienen de X-Road o del Agente IA. | Módulo 03 — Actividad 1 |
| Ejecutadas / Programadas | campo | Actividades ejecutadas frente a las programadas acumuladas. | Programadas suma el Número de actividades en cada ciclo. | Módulo 05 — Actividad 1 |
| Entidad Principal | campo | Entidad responsable de la recomendación y de reportar el informe de ejecución. | Sus usuarios de Entidad Territorial ven la recomendación y reciben los correos. | Módulo 04 — Actividad 1 |
| Entidades asociadas | campo | Entidades que apoyan una recomendación. | Reciben correo, pero no ven la recomendación. | Módulo 04 — Actividad 1 |
| Historial Plan de acción | campo | Eventos del plan de una alerta. | Permite ver confirmaciones y desconfirmaciones. | Módulo 05 — Actividad 1 |
| Nivel de acceso: Central / Subdirección | campo | Subdivisión del rol Entidad Territorial. | Central: entidad central; Subdirección: solo la subdirección elegida. | Módulo 01 — Actividad 1 |
| Nueva Contraseña | campo | Texto oculto. Mínimo 8 caracteres y al menos un carácter especial | Obligatorio: Sí. | Módulo 01 — Actividad 1 |
| Número de actividades | campo | Meta de la actividad por cada ciclo de 6 meses. | Se suma a lo programado en cada ciclo. | Módulo 05 — Actividad 1 |
| Porcentaje de Avance Global | campo | Promedio del % de cumplimiento de las alertas no borrador del alcance. | Las alertas sin actividades cuentan como 0 %. | Módulo 02 — Actividad 1 |
| Próximo Informe | campo | Fecha límite del siguiente informe de la actividad. | Se fija al aprobar un informe: notificación + 6 meses y luego +6; al vencer se abre un nuevo ciclo. | Módulo 05 — Actividad 1 |
| Tema Clave | campo | Descripción de la alerta. | Aparece en la columna Tema. | Módulo 03 — Actividad 1 |

### Catálogo

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Eje temático | catálogo | Lista de 14 ejes de las recomendaciones. | El servidor no valida contra la lista. | Módulo 04 — Actividad 1 |
| Etiqueta: Nacional / Regional / Internacional | catálogo | Alcance territorial de la alerta. | Las etiquetas Focalizado y Binacional solo llegan por X-Road. | Módulo 03 — Actividad 1 |
| Plazo de implementación | catálogo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente. | Solo informativo. | Módulo 05 — Actividad 1 |
| Tipo de alerta: Inminencia / Estructural | catálogo | Clasificación de la alerta por su urgencia. | Inminencia se pinta en rojo y Estructural en azul en el mapa. | Módulo 03 — Actividad 1 |

### Concepto

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Actividad | concepto | Acción que la entidad se compromete a ejecutar para una recomendación, con meta por semestre. | Se aprueba una por una y se reporta con informes de ejecución. | Módulo 05 — Actividad 1 |
| Alerta temprana | concepto | Documento de la Defensoría del Pueblo que advierte un riesgo; en SI-CIPRAT es el registro central del ciclo. | Todo el trabajo (recomendaciones, plan, informes) cuelga de una alerta. | Módulo 03 — Actividad 1 |
| Informe de ejecución | concepto | Reporte semestral de lo ejecutado en una actividad, con su PDF. | Lo aprueban el Monitor o el Líder; al aprobarlo se fija el próximo informe. | Módulo 05 — Actividad 1 |
| Informe de seguimiento | concepto | Documento de la Defensoría que hace seguimiento a una alerta. | Puede agregar municipios y recomendaciones o cerrar la alerta. | Módulo 06 — Actividad 1 |
| Oficio de consumación | concepto | Documento de la Defensoría que informa que el riesgo se consumó. | Se asocia a alertas y puede modificar sus municipios. | Módulo 07 — Actividad 1 |
| Plan de acción | concepto | Conjunto de actividades de todas las recomendaciones de una alerta. | Se confirma completo por alerta. | Módulo 05 — Actividad 1 |
| Recomendación | concepto | Acción que la alerta pide a una Entidad Principal; tiene código RC. | La Entidad Principal le formula actividades. | Módulo 04 — Actividad 1 |
| Subsunción | concepto | Una alerta nueva reemplaza a otras, que quedan cerradas. | Irreversible. | Módulo 03 — Actividad 1 |

### Estado

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Activa | estado | Alerta vigente sobre la que se trabajan recomendaciones, planes e informes. | Se le cargan recomendaciones y actividades; puede editarse mientras el plan no esté confirmado. | Módulo 03 — Actividad 1 |
| Aprobado | estado | Actividad aprobada; o plan con todas sus actividades aprobadas; o informe o reporte aprobado. | Una actividad aprobada no se edita; un plan Aprobado se puede confirmar; un informe aprobado no se edita. | Módulo 05 — Actividad 1 |
| Aprobado - Sin Informe | estado | Opción del filtro de actividades: actividad aprobada sin informe del ciclo. | La entidad debe reportar el informe. | Módulo 05 — Actividad 1 |
| Borrador | estado | Alerta creada por el Agente IA o por X-Road que aún no se publica. | No cuenta en los indicadores; se revisa y se publica con "Publicar alerta al guardar". | Módulo 03 — Actividad 1 |
| Cerrada | estado | Alerta terminada (por cierre, informe de seguimiento, subsunción o X-Road). | No se edita ni se reabre; su plan y sus informes quedan en "Cerrado". | Módulo 03 — Actividad 1 |
| Completado | estado | Informe que quedó cerrado al aprobar la actividad con un informe pendiente. | No se calcula el próximo informe en ese caso. | Módulo 05 — Actividad 1 |
| Inactivo | estado | Usuario que no puede iniciar sesión ("Cuenta no activa"). | Puede reactivarse con el interruptor. | Módulo 01 — Actividad 1 |
| Pendiente | estado | En el plan: hay actividades por aprobar. En el informe: hay informes por aprobar. | El Monitor o el Líder de Macrozona deben revisar y aprobar. | Módulo 05 — Actividad 1 |
| Pendiente Aprobación | estado | Estado de una actividad recién formulada o devuelta. | La entidad puede editarla o eliminarla; el Monitor o el Líder pueden aprobarla. | Módulo 05 — Actividad 1 |
| Plan de acción confirmado | estado | Plan cuya aprobación cerró el Monitor, el Líder o el Super Administrador con "Confirmar". | Habilita los informes de ejecución y bloquea la edición de la alerta, las recomendaciones y las actividades. | Módulo 05 — Actividad 1 |
| Sin Completar | estado | Estado de informes de la alerta cuando hay actividades sin informe del ciclo. | Faltan informes por reportar. | Módulo 05 — Actividad 1 |
| Sin Informe | estado | Actividad aprobada que aún no reporta el informe del ciclo. | La entidad puede usar "Reportar Informe". | Módulo 05 — Actividad 1 |
| Sin plan | estado | Estado del plan cuando ninguna recomendación tiene actividades. | La Entidad Territorial debe formular actividades. | Módulo 05 — Actividad 1 |
| Sin recomendaciones | estado | Estado del plan de una alerta que aún no tiene recomendaciones. | Se deben cargar recomendaciones (Super Administrador o Administrador). | Módulo 05 — Actividad 1 |

### Mensaje

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Código de autenticación inválido | mensaje | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Módulo 01 — Actividad 2 |
| Código expirado | mensaje | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Módulo 01 — Actividad 2 |
| Conflicto con el estado actual del recurso. | mensaje | Otro usuario o una acción anterior cambió el estado del registro (409). | Actualice la página, revise el estado actual y repita la acción si todavía aplica. | Módulo 02 — Actividad 3 |
| Credenciales inválidas | mensaje | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | Módulo 01 — Actividad 2 |
| Cuenta no activa | mensaje | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | Módulo 01 — Actividad 2 |
| Debe tener al menos 8 caracteres | mensaje | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Módulo 01 — Actividad 1 |
| Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio. | mensaje | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Módulo 02 — Actividad 3 |
| El enlace de invitación es inválido. Verifica que el enlace esté completo. | mensaje | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | Módulo 01 — Actividad 1 |
| El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador. | mensaje | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Módulo 01 — Actividad 1 |
| El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose. | mensaje | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | Módulo 03 — Actividad 2 |
| El servidor no está disponible. Por favor, intenta más tarde. | mensaje | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Espere unos minutos e intente de nuevo. | Módulo 02 — Actividad 3 |
| Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 03 — Actividad 1 |
| Error al cargar datos | mensaje | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | Módulo 02 — Actividad 1 |
| Error al cargar el informe de recomendaciones | mensaje | El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Pida el consolidado al Monitor o a la Secretaría Técnica. | Módulo 05 — Actividad 1 |
| Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página. | Módulo 06 — Actividad 1 |
| Error al cargar las recomendaciones. Por favor, intente nuevamente. | mensaje | Falla del servicio. | Recargue la página. | Módulo 04 — Actividad 1 |
| Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 07 — Actividad 1 |
| Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo. | mensaje | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Módulo 03 — Actividad 4 |
| Error interno del servidor. Por favor, intenta más tarde. | mensaje | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | Módulo 03 — Actividad 3 |
| La alerta solicitada no existe o ha sido eliminada. | mensaje | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | Módulo 03 — Actividad 5 |
| La solicitud no es válida. Verifica los datos e intenta de nuevo. | mensaje | Errores 400 o 422 de validación. | Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. | Módulo 02 — Actividad 3 |
| Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente. | mensaje | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | Módulo 01 — Actividad 1 |
| No hay alertas con planes de acción | mensaje | No hay alertas con municipios en sus departamentos, o su usuario no tiene departamentos. | Revise sus departamentos en **Ver Perfil** y pida el ajuste si hace falta. | Módulo 05 — Actividad 1 |
| No hay datos de departamentos | mensaje | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | Módulo 02 — Actividad 1 |
| No hay notificaciones | mensaje | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | Módulo 08 — Actividad 1 |
| No puedes reutilizar ninguna de tus últimas 5 contraseñas | mensaje | El sistema guarda el historial de contraseñas. | Elija una contraseña distinta de las 5 anteriores. | Módulo 01 — Actividad 3 |
| No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo. | mensaje | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Módulo 03 — Actividad 1 |
| No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo. | mensaje | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Módulo 01 — Actividad 2 |
| No tienes permisos para agregar recomendaciones | mensaje | Solo el Super Administrador y el Administrador las registran. | Pida el cambio a la Secretaría Técnica. | Módulo 04 — Actividad 1 |
| No tienes permisos para cargar informes | mensaje | Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. | Pida la carga a la Secretaría Técnica. | Módulo 06 — Actividad 1 |
| No tienes permisos para cargar oficios | mensaje | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | Módulo 07 — Actividad 1 |
| No tienes permisos para confirmar planes de acción | mensaje | Su rol solo consulta en Seguimiento. | La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. | Módulo 05 — Actividad 1 |
| No tienes permisos para realizar esta acción. | mensaje | El servidor rechaza la operación para el rol (403). | Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. | Módulo 02 — Actividad 3 |
| No tienes permisos para reportar alertas | mensaje | Su rol solo consulta alertas. | Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). | Módulo 03 — Actividad 1 |
| Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida. | mensaje | La ruta no existe. | Haga clic en **Volver al inicio** y navegue desde el menú. | Módulo 02 — Actividad 3 |
| Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente. | mensaje | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Módulo 01 — Actividad 4 |
| Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente. | mensaje | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | Módulo 01 — Actividad 4 |
| Token inválido o expirado | mensaje | El enlace de restablecimiento vence en 1 hora. | Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. | Módulo 01 — Actividad 3 |

### Menú o pestaña

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Alertas / Recomendaciones / Actividades | menú o pestaña | Pestañas de Planes de acción y Seguimiento. | Abre la vista correspondiente. | Módulo 05 — Actividad 1 |
| Alertas tempranas | menú o pestaña | Registro y consulta de las alertas. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Cerrar sesión | menú o pestaña | Termina la sesión. | Abre la vista correspondiente. | Módulo 01 — Actividad 1 |
| Historial de actividades | menú o pestaña | Línea de tiempo de acciones sobre una alerta. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Información / Actividades / Historial | menú o pestaña | Pestañas del detalle de una recomendación en el plan. | Abre la vista correspondiente. | Módulo 05 — Actividad 1 |
| Informes de seguimiento | menú o pestaña | Informes de seguimiento de la Defensoría. | Abre la vista correspondiente. | Módulo 06 — Actividad 1 |
| Inicio | menú o pestaña | Tablero de indicadores, mapa y alertas recientes. | Abre la vista correspondiente. | Módulo 02 — Actividad 1 |
| Notificaciones | menú o pestaña | Panel con el historial de actividad de su alcance. | Abre la vista correspondiente. | Módulo 08 — Actividad 1 |
| Oficios de consumación | menú o pestaña | Oficios de consumación del riesgo. | Abre la vista correspondiente. | Módulo 07 — Actividad 1 |
| Seguimiento | menú o pestaña | Revisión y aprobación de actividades, confirmación de planes y aprobación de informes ("Seguimiento de Planes"). | Abre la vista correspondiente. | Módulo 05 — Actividad 1 |
| Todas / Inminencia / Estructurales | menú o pestaña | Pestañas del listado de alertas por tipo. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Ver Perfil | menú o pestaña | Acceso a Mi perfil. | Abre la vista correspondiente. | Módulo 01 — Actividad 1 |

### Rol

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| Administrador | rol | Acceso nacional para visualizar alertas y gestionar planes de acción. No puede eliminar alertas ni aprobar actividades. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Consulta Departamentos | rol | Solo lectura filtrado por departamentos asignados. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Consulta Entidad | rol | Solo lectura filtrado por su entidad asignada. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Consulta Global | rol | Solo lectura a nivel nacional (sin modificar datos). (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Entidad Territorial | rol | Gestiona actividades e informes de ejecución de su entidad/subdirección. No puede aprobar. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Líder de Macrozona | rol | Supervisa alertas en departamentos asignados. Acceso total a reportes de ejecución. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Monitor | rol | Acceso departamental. Puede aprobar actividades e informes en Seguimiento. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |
| Super Administrador | rol | Acceso total a la plataforma sin restricciones. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01 — Actividad 1 |

### Sigla

| Término | Tipo | Significado | Qué implica para el usuario de Consulta — Departamentos | Dónde lo verá |
|---|---|---|---|---|
| AT | sigla | Prefijo del número de alerta temprana (AT-XXX-XXXX). | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| CAT | sigla | Categoría municipal según la Contaduría General de la Nación (ESP, 1 a 6, N/A). | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| CIPRAT | sigla | Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas. | Aparece en pantallas y documentos de la ruta. | Módulo 01 — Actividad 1 |
| CSV | sigla | Archivo de texto separado por comas que se abre en Excel. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| D.I.H. | sigla | Derecho Internacional Humanitario (paso 4 de la alerta). | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| DANE / Cod DANE | sigla | Código del municipio (5 dígitos) del DANE. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| PDET | sigla | Programa de Desarrollo con Enfoque Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| PDF | sigla | Único formato de archivo aceptado para los soportes. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| PNIS | sigla | Programa Nacional Integral de Sustitución de Cultivos de Uso Ilícito. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| RC | sigla | Prefijo del código de la recomendación. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| SI-CIPRAT | sigla | Sistema de Información de la Secretaría Técnica CIPRAT. | Aparece en pantallas y documentos de la ruta. | Módulo 01 — Actividad 1 |
| SISAT | sigla | Sistema de Alertas Tempranas de la Defensoría del Pueblo; envía información por X-Road. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| X-Road | sigla | Plataforma de interoperabilidad por la que llegan alertas, informes y oficios. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |
| Zona Fut. | sigla | Zona del Formulario Único Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 03 — Actividad 1 |

## Anexo (no se muestra en index.html)

### Trazabilidad

| Módulo | Actividad | Pasos | Funcionalidades F-… cubiertas | Evidencia |
|---|---|---|---|---|
| 01 Acceso a la plataforma | 1. Activar la cuenta desde la invitación | 4 | F-ACC-04, F-NOT-04 | main-api/CipratApi/Controladores/UsuariosControlador.cs:258-261; main-api/CipratApi/Servicios/EmailService.cs:62 |
| 01 Acceso a la plataforma | 2. Iniciar sesión con el código de verificación | 5 | F-ACC-01, F-ACC-02, F-ACC-03, F-NOT-05 | main-api/CipratApi/Controladores/AutenticacionControlador.cs:33-60; main-api/CipratApi/Servicios/ServicioAutenticacion.cs:47-110; dashboard/src/components/auth/VerificationCodePanel.tsx:216-223 |
| 01 Acceso a la plataforma | 3. Recuperar la contraseña | 5 | F-ACC-05, F-ACC-06, F-NOT-06 | main-api/CipratApi/Controladores/AutenticacionControlador.cs:204-225; main-api/CipratApi/Controladores/AutenticacionControlador.cs:239-265; main-api/CipratApi/Servicios/EmailService.cs:92 |
| 01 Acceso a la plataforma | 4. Cerrar sesión y entender el cierre automático | 3 | F-ACC-07, F-ACC-08 | dashboard/src/components/layout/Sidebar.tsx:479; dashboard/src/hooks/useIdleTimeout.ts:6-41 |
| 01 Acceso a la plataforma | 5. Consultar los Términos de uso y contactar al soporte técnico | 3 | F-ACC-09, F-ACC-10 | dashboard/src/pages/TermsOfUse.tsx:15-34; dashboard/src/components/auth/LoginPanel.tsx:195-198 |
| 01 Acceso a la plataforma | 6. Consultar Mi perfil y verificar el alcance asignado | 3 | F-ACC-12 | dashboard/src/pages/MyProfile.tsx:111-283 |
| 02 Inicio | 1. Leer los indicadores del Inicio | 3 | F-INI-01, F-INI-05, F-TAR-03 | main-api/CipratApi/Servicios/ServicioDashboardHome.cs:85-200; main-api/CipratApi/Servicios/ServicioDashboardHome.cs:288-330; main-api/CipratApi/Servicios/ServicioActividades.cs:928-966 |
| 02 Inicio | 2. Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa | 4 | F-INI-02, F-INI-03, F-INI-04, F-INI-06 | dashboard/src/pages/Home.tsx:99-136; dashboard/src/pages/Home.tsx:154-212; main-api/CipratApi/Servicios/ServicioDashboardHome.cs:268-287 |
| 02 Inicio | 3. Navegar con el menú lateral y usar el panel de accesibilidad | 3 | F-INI-08, F-INI-09 | dashboard/src/components/accessibility/AccessibilityPanel.tsx:28-80; dashboard/src/components/layout/Sidebar.tsx:16-91 |
| 02 Inicio | 4. Consultar el tablero público sin iniciar sesión | 2 | F-INI-07 | dashboard/src/App.tsx:40 |
| 08 Notificaciones | 1. Consultar el panel de Notificaciones | 3 | F-NOT-01, F-NOT-02, F-NOT-03 | dashboard/src/components/notifications/NotificationsPanel.tsx:30-113; dashboard/src/components/notifications/NotificationsPanel.tsx:128; dashboard/src/components/ui/ActivityList.tsx:77 |
| 08 Notificaciones | 2. Reconocer los correos que envía el sistema y qué hacer con cada uno | 2 | F-NOT-04, F-NOT-05, F-NOT-06 | main-api/CipratApi/Servicios/EmailService.cs:62; main-api/CipratApi/Servicios/EmailService.cs:38; main-api/CipratApi/Servicios/EmailService.cs:92 |
| 03 Alertas tempranas | 1. Consultar, buscar y filtrar alertas tempranas | 6 | F-ALE-01, F-ALE-02, F-ALE-03, F-INT-01 | main-api/CipratApi/Controladores/AlertasControlador.cs:87; dashboard/src/components/alertas-tempranas/AlertasTab.tsx:294; dashboard/src/components/alertas-tempranas/AlertFiltersModal.tsx:216-420 |
| 03 Alertas tempranas | 2. Ver el detalle de una alerta y descargar su PDF | 5 | F-ALE-04, F-ALE-05 | dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx:13-340; main-api/CipratApi/Controladores/ArchivosControlador.cs:135-170 |
| 03 Alertas tempranas | 3. Consultar el historial de actividades de una alerta | 3 | F-ALE-06 | main-api/CipratApi/Controladores/AlertasControlador.cs:627-700 |
| 03 Alertas tempranas | 4. Descargar el listado de alertas en CSV | 2 | F-ALE-07 | main-api/CipratApi/Controladores/AlertasControlador.cs:1004-1087 |
| 03 Alertas tempranas | 5. Ir a las recomendaciones de una alerta | 2 | F-REC-01 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41 |
| 04 Recomendaciones | 1. Consultar, buscar y filtrar las recomendaciones de una alerta | 4 | F-REC-01, F-REC-02, F-REC-08 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41; dashboard/src/components/recomendaciones/RecomendacionFiltersModal.tsx:198-344; main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:516-540 |
| 04 Recomendaciones | 2. Ver el detalle de una recomendación | 2 | F-REC-03 | dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx:84-207 |
| 04 Recomendaciones | 3. Descargar las recomendaciones de una alerta en CSV | 2 | F-REC-04 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566 |
| 05 Seguimiento | 1. Consultar el listado de Seguimiento y encontrar lo pendiente | 4 | F-SEG-01, F-SEG-02, F-SEG-03 | dashboard/src/contexts/ActionPlanModeContext.tsx:35-37; dashboard/src/components/planes-de-accion/ActionPlanFiltersModal.tsx:119-243; dashboard/src/pages/PlanesDeAccion.tsx:232-267 |
| 05 Seguimiento | 2. Consultar recomendaciones, actividades e informes en Seguimiento | 3 | F-SEG-04, F-TAR-01, F-TAR-03, F-TAR-04 | dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:254-795; main-api/CipratApi/Servicios/ServicioTareasWorker.cs:27-140; main-api/CipratApi/Servicios/ServicioActividades.cs:928-966 |
| 06 Informes de seguimiento | 1. Consultar los informes de seguimiento y descargar su PDF | 3 | F-ISE-01, F-ISE-02, F-ISE-03, F-ISE-04, F-INT-02 | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:127-180; dashboard/src/components/informes-seguimiento/InformesFiltersModal.tsx:97-134; dashboard/src/components/informes-seguimiento/InformeSeguimientoDetailPanel.tsx:104-276 |
| 07 Oficios de consumación | 1. Consultar los oficios de consumación y descargar su PDF | 3 | F-OFI-01, F-OFI-02, F-OFI-03, F-OFI-04, F-INT-03 | main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:47-95; dashboard/src/components/oficios-consumacion/OficiosFiltersModal.tsx:97-134; dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx:102-196 |

### Diferencias con la versión anterior de la Academia

Esta ruta no existe en la Academia (la Academia tiene 8 rutas). Diferencias con el xlsx de permisos en `analisis/02c_comparacion_academia_xlsx.md`. Puntos contrastados con el código:

- Los roles y subroles de esta versión salen del código; la Academia los toma como lista de 8 roles. Esta ruta corresponde a: ninguna ruta de la Academia (es nueva: Consulta Departamentos no está en la lista de la Academia).
- Código de verificación: 4 dígitos (`main-api/CipratApi/Servicios/ServicioAutenticacion.cs:41`), con vigencia de 1 hora; sesión de 720 minutos y cierre por inactividad a los 60 minutos.
- El aviso de los 5 meses que menciona la Academia corresponde en el código a un recordatorio cuando faltan 30 días o menos para el próximo informe, y solo llega a la Entidad Territorial (`main-api/CipratApi/Servicios/ServicioTareasWorker.cs:145-220`).

### Vacíos (NO ENCONTRADO EN CÓDIGO)

- Validación de que la fecha de notificación sea posterior a la fecha de la alerta (NO ENCONTRADO en `main-api/CipratApi/Servicios/ServicioAlertas.cs` ni en `dashboard/src/components/report-alert/ReportAlertModal.tsx`).
- Mínimo de 40 caracteres para "Actividad" y máximo de 4.000 para descripciones (NO ENCONTRADO en DTOs ni en formularios).
- Fecha límite para el primer informe de ejecución: el próximo informe solo se fija al aprobar el primer informe (`main-api/CipratApi/Servicios/ServicioInformesEjecucion.cs:337-346`).
- Servicio para eliminar informes de ejecución (permiso definido sin endpoint; `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191`).
- Pantallas para cambiar la contraseña con la actual, editar el propio perfil y borrar comentarios (los servicios existen en la API; ninguna pantalla los usa).
- Filtro por departamentos en Reportes, Informes de seguimiento y Oficios de consumación (NO ENCONTRADO: esos listados muestran todo el país).

### Apoyos visuales de la ruta

| ID | Tipo | Dónde va | Título |
|---|---|---|---|
| MED-09-ACC-01 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación | Pantalla "Configura tu contraseña" |
| MED-09-ACC-02 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-06 | Mensaje ERR-ACC-06 |
| MED-09-ACC-03 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-07 | Mensaje ERR-ACC-07 |
| MED-09-ACC-04 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-08 | Mensaje ERR-ACC-08 |
| MED-09-ACC-05 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-09 | Mensaje ERR-ACC-09 |
| MED-09-ACC-06 | GIF | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación | Ingreso con código de verificación |
| MED-09-ACC-07 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-01 | Mensaje ERR-ACC-01 |
| MED-09-ACC-08 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-02 | Mensaje ERR-ACC-02 |
| MED-09-ACC-09 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-03 | Mensaje ERR-ACC-03 |
| MED-09-ACC-10 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-04 | Mensaje ERR-ACC-04 |
| MED-09-ACC-11 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-GEN-06 | Mensaje ERR-GEN-06 |
| MED-09-ACC-12 | GIF | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña | Recuperación de la contraseña |
| MED-09-ACC-13 | Captura | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña · Escenario ERR-ACC-10 | Mensaje ERR-ACC-10 |
| MED-09-ACC-14 | Captura | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña · Escenario ERR-ACC-11 | Mensaje ERR-ACC-11 |
| MED-09-ACC-15 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático | Menú del usuario |
| MED-09-ACC-16 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-12 | Mensaje ERR-ACC-12 |
| MED-09-ACC-17 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-13 | Mensaje ERR-ACC-13 |
| MED-09-ACC-18 | Captura | 01 Acceso a la plataforma · Actividad 5 — Consultar los Términos de uso y contactar al soporte técnico | Términos de uso |
| MED-09-ACC-19 | Captura | 01 Acceso a la plataforma · Actividad 6 — Consultar Mi perfil y verificar el alcance asignado | Mi perfil |
| MED-09-INI-01 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio | Indicadores del Inicio |
| MED-09-INI-02 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio · Escenario ERR-INI-01 | Mensaje ERR-INI-01 |
| MED-09-INI-03 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio · Escenario ERR-INI-02 | Mensaje ERR-INI-02 |
| MED-09-INI-04 | Captura | 02 Inicio · Actividad 2 — Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa | Mapa y ranking del Inicio |
| MED-09-INI-05 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad | Menú lateral del rol |
| MED-09-INI-06 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-12 | Mensaje ERR-GEN-12 |
| MED-09-INI-07 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-11 | Mensaje ERR-GEN-11 |
| MED-09-INI-08 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-01 | Mensaje ERR-GEN-01 |
| MED-09-INI-09 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-03 | Mensaje ERR-GEN-03 |
| MED-09-INI-10 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-05 | Mensaje ERR-GEN-05 |
| MED-09-INI-11 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-13 | Mensaje ERR-GEN-13 |
| MED-09-INI-12 | Captura | 02 Inicio · Actividad 4 — Consultar el tablero público sin iniciar sesión | Tablero público |
| MED-09-ALE-01 | Captura | 03 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas | Listado de alertas |
| MED-09-ALE-02 | Captura | 03 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas · Escenario ERR-ALE-17 | Mensaje ERR-ALE-17 |
| MED-09-ALE-03 | Captura | 03 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas · Escenario ERR-ALE-19 | Mensaje ERR-ALE-19 |
| MED-09-ALE-04 | Captura | 03 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas · Escenario ERR-GEN-07 | Mensaje ERR-GEN-07 |
| MED-09-ALE-05 | Captura | 03 Alertas tempranas · Actividad 2 — Ver el detalle de una alerta y descargar su PDF | Detalle de la alerta |
| MED-09-ALE-06 | Captura | 03 Alertas tempranas · Actividad 2 — Ver el detalle de una alerta y descargar su PDF · Escenario ERR-GEN-02 | Mensaje ERR-GEN-02 |
| MED-09-ALE-07 | Captura | 03 Alertas tempranas · Actividad 3 — Consultar el historial de actividades de una alerta | Historial de actividades |
| MED-09-ALE-08 | Captura | 03 Alertas tempranas · Actividad 3 — Consultar el historial de actividades de una alerta · Escenario ERR-GEN-04 | Mensaje ERR-GEN-04 |
| MED-09-ALE-09 | Captura | 03 Alertas tempranas · Actividad 4 — Descargar el listado de alertas en CSV | Botón Descargar |
| MED-09-ALE-10 | Captura | 03 Alertas tempranas · Actividad 4 — Descargar el listado de alertas en CSV · Escenario ERR-GEN-10 | Mensaje ERR-GEN-10 |
| MED-09-ALE-11 | Captura | 03 Alertas tempranas · Actividad 5 — Ir a las recomendaciones de una alerta | Menú ⋯ de la alerta |
| MED-09-ALE-12 | Captura | 03 Alertas tempranas · Actividad 5 — Ir a las recomendaciones de una alerta · Escenario ERR-REC-08 | Mensaje ERR-REC-08 |
| MED-09-REC-01 | Captura | 04 Recomendaciones · Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta | Recomendaciones de una alerta |
| MED-09-REC-02 | Captura | 04 Recomendaciones · Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta · Escenario ERR-REC-06 | Mensaje ERR-REC-06 |
| MED-09-REC-03 | Captura | 04 Recomendaciones · Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta · Escenario ERR-REC-07 | Mensaje ERR-REC-07 |
| MED-09-REC-04 | Captura | 04 Recomendaciones · Actividad 2 — Ver el detalle de una recomendación | Detalle de recomendación |
| MED-09-REC-05 | Captura | 04 Recomendaciones · Actividad 3 — Descargar las recomendaciones de una alerta en CSV | CSV de recomendaciones |
| MED-09-SEG-01 | Captura | 05 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente | Seguimiento de Planes |
| MED-09-SEG-02 | Captura | 05 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente · Escenario ERR-SEG-13 | Mensaje ERR-SEG-13 |
| MED-09-SEG-03 | Captura | 05 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente · Escenario ERR-SEG-07 | Mensaje ERR-SEG-07 |
| MED-09-SEG-04 | Captura | 05 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente · Escenario ERR-SEG-14 | Mensaje ERR-SEG-14 |
| MED-09-SEG-05 | Captura | 05 Seguimiento · Actividad 2 — Consultar recomendaciones, actividades e informes en Seguimiento | Detalle de Actividad en Seguimiento |
| MED-09-ISE-01 | Captura | 06 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF | Informes de seguimiento |
| MED-09-ISE-02 | Captura | 06 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF · Escenario ERR-ISE-07 | Mensaje ERR-ISE-07 |
| MED-09-ISE-03 | Captura | 06 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF · Escenario ERR-ISE-09 | Mensaje ERR-ISE-09 |
| MED-09-OFI-01 | Captura | 07 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF | Oficios de consumación |
| MED-09-OFI-02 | Captura | 07 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-02 | Mensaje ERR-OFI-02 |
| MED-09-OFI-03 | Captura | 07 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-05 | Mensaje ERR-OFI-05 |
| MED-09-NOT-01 | Captura | 08 Notificaciones · Actividad 1 — Consultar el panel de Notificaciones | Panel Notificaciones |
| MED-09-NOT-02 | Captura | 08 Notificaciones · Actividad 1 — Consultar el panel de Notificaciones · Escenario ERR-NOT-01 | Mensaje ERR-NOT-01 |
| MED-09-NOT-03 | Captura | 08 Notificaciones · Actividad 2 — Reconocer los correos que envía el sistema y qué hacer con cada uno | Correo del sistema |
