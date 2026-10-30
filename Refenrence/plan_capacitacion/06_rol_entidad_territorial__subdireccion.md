Generado desde: monorepo SI-CIPRAT rama develop commit 56d3f33 (2026-07-17 10:20:06 -0500) · 2026-10-28

# Ruta 06 · Entidad Territorial (Subdirección)

## Ficha de la ruta

| Campo | Valor |
|---|---|
| Número | 06 |
| Rol | Entidad Territorial |
| Subrol | Subdirección |
| Alcance | Su subdirección · formulación y reporte |
| Descripción corta | Formula las actividades del plan de acción de las recomendaciones asignadas a su subdirección y reporta sus informes de ejecución. |
| Módulos | 9 |
| Modalidad | Autoaprendizaje |
| Prerrequisitos de la ruta | Cuenta activa con rol Entidad Territorial, nivel de acceso Subdirección, una entidad central y una subdirección asignadas. |

## Definición del rol

Rol de las entidades responsables de las recomendaciones. Formula las actividades del plan de acción, atiende los comentarios de la revisión y reporta los informes de ejecución con su soporte en PDF. No aprueba. Recibe los correos de negocio del sistema. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-139,168-192`, `main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`. Tiene dos subroles que el sistema distingue por el **Nivel de acceso** elegido al invitar: Central y Subdirección.

**Criterio técnico:** En el formulario de usuarios es un solo rol, "Entidad Territorial", con el campo **Nivel de acceso** (Central / Subdirección) (`dashboard/src/components/ui/UserFormModal.tsx:495-541`); al guardar se convierte en dos valores del enumerado, `ENTIDAD_TERRITORIAL_CENTRAL` y `ENTIDAD_TERRITORIAL_SUBDIRECCION` (`dashboard/src/pages/UsuariosYEntidades.tsx:286-293`), con la misma matriz de permisos y distinto alcance de datos (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:51-67`). Por eso se modelan como un rol con dos subroles.

**Subroles de este rol:** Central, Subdirección.

**Quién lo ocupa:** [INFERIDO] Funcionarios de una dependencia (subdirección, dirección, secretaría) de una entidad central que tiene recomendaciones asignadas directamente. Base: el texto de ayuda "Subdirección: Otorga acceso únicamente a la gestión y visualización de la subdirección seleccionada." (`dashboard/src/components/ui/UserFormModal.tsx:512`) y el filtro por subentidad (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`).

**Cómo se asigna:** Lo asigna un Super Administrador o un Administrador al invitar al usuario con **Rol** "Entidad Territorial" y **Nivel de acceso** "Subdirección". **Entidad Central**, **Subdirección** y **Cargo** son obligatorios ("organization_id y sub_organization_id son obligatorios para el rol ENTIDAD_TERRITORIAL_SUBDIRECCION", `main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:112-126`).

## Definición del subrol

Usuario de una subdirección (dirección, dependencia o secretaría) de una entidad central, que responde por las recomendaciones asignadas directamente a esa subdirección como **Entidad Principal**. El sistema lo identifica con el valor `ENTIDAD_TERRITORIAL_SUBDIRECCION` y con la subdirección guardada en su usuario (`SubEntidadId`). Ve las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`). Tiene las mismas acciones de la entidad central sobre esas recomendaciones: agregar, editar y eliminar actividades, comentar y reportar informes de ejecución. Riesgo conocido R5: el listado global de actividades se filtra con la entidad central del usuario (`EntidadId`) y no con la subdirección (`main-api/CipratApi/Servicios/ServicioActividades.cs:490-495`).

## Objetivo de capacitación

Al terminar esta ruta, el usuario de Entidad Territorial (Subdirección) podrá ubicar las recomendaciones asignadas a su subdirección, formular, editar y eliminar las actividades del plan de acción, atender los comentarios de la revisión, reportar y corregir los informes de ejecución con su soporte en PDF dentro de cada ciclo semestral, y consultar alertas, oficios de consumación y notificaciones, sabiendo qué espera de otros actores en cada momento.

## Permisos por módulo

| Módulo | Acciones disponibles |
|---|---|
| Acceso a la plataforma | Iniciar sesión con correo y contraseña; Validar el código de verificación; Reenviar el código de verificación; Activar la cuenta desde la invitación; Solicitar el restablecimiento de la contraseña; Restablecer la contraseña con el enlace; Cerrar sesión; Cierre automático de la sesión por inactividad o vencimiento; Consultar los Términos de uso; Contactar al soporte técnico; Consultar Mi perfil |
| Inicio | Consultar los indicadores del Inicio (con restricción); Consultar la última alerta emitida (con restricción); Consultar "Alertas por departamento" (Top 10) (con restricción); Consultar "Alertas recientes" (con restricción); Consultar el "Porcentaje de Avance Global" (con restricción); Consultar el mapa de municipios con alertas (con restricción); Consultar el tablero público sin iniciar sesión; Usar el panel de accesibilidad; Usar el menú lateral |
| Alertas tempranas | Listar alertas (con restricción); Buscar alertas (con restricción); Filtrar alertas (con restricción); Ver el detalle de una alerta (con restricción); Descargar el PDF de la alerta (con restricción); Consultar el historial de actividades de la alerta (con restricción); Descargar el listado de alertas (CSV) (con restricción) |
| Recomendaciones | Listar las recomendaciones de una alerta (con restricción); Buscar y filtrar recomendaciones (con restricción); Ver el detalle de una recomendación (con restricción); Descargar las recomendaciones (CSV) (con restricción); Asignar el código RC (consulta) |
| Planes de acción | Listar las alertas con plan de acción (con restricción); Buscar y filtrar planes de acción (con restricción); Ver el detalle y el historial del plan de una alerta (con restricción); Descargar el listado de planes (CSV) (con restricción); Ver las recomendaciones del plan de una alerta (con restricción); Consultar la pestaña global de Recomendaciones (con restricción); Consultar la pestaña global de Actividades (con restricción); Listar las actividades de una recomendación (con restricción); Ver el detalle de una actividad (con restricción); Descargar las actividades (CSV) (con restricción); Agregar una actividad (con restricción); Agregar una actividad a un plan confirmado (con restricción); Editar una actividad (con restricción); Eliminar una actividad (con restricción); Ver y escribir comentarios de una actividad (con restricción); Reportar un informe de ejecución (con restricción); Editar un informe de ejecución pendiente (con restricción); Consultar los informes de ejecución y descargar su PDF (con restricción) |
| Oficios de consumación | Listar los oficios de consumación (con restricción); Buscar y filtrar oficios por alerta (con restricción); Ver el detalle de un oficio (con restricción); Descargar el PDF del oficio (con restricción) |
| Notificaciones | Abrir el panel de Notificaciones (con restricción); Buscar en el panel de Notificaciones (con restricción); Cargar más notificaciones (con restricción); Recibir el correo de invitación; Recibir el correo con el código de verificación; Recibir el correo de restablecimiento de contraseña; Recibir el correo de recomendación asignada; Recibir el correo de recomendación actualizada; Recibir el correo de validación del plan de acción; Recibir el recordatorio de informe de ejecución; Recibir el correo de informe de seguimiento; Recibir el correo de oficio de consumación |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (consulta); Enviar el recordatorio de informe de ejecución; Recalcular estados y porcentajes de cumplimiento (consulta); Calcular el próximo informe al aprobar un informe (consulta) |

## Matriz de capacidades en la plataforma

Fuente: `analisis/09_capacidades_ETS.md`. Total de funcionalidades: 145 | Puede: 24 | Puede con restricción: 42 | Solo consulta: 7 | No puede: 72.

### Qué SÍ puede hacer el usuario de Entidad Territorial (Subdirección)

| Módulo | Funcionalidad | Definición | Tipo | Condición o alcance | Dónde se explica |
|---|---|---|---|---|---|
| Acceso a la plataforma | Iniciar sesión con correo y contraseña (F-ACC-01) ✔ | Verifica el correo y la contraseña y, si son correctos, envía al correo del usuario un código de verificación de 4 dígitos. | Estado | Sin restricción adicional | Módulo 01: Actividad 2 |
| Acceso a la plataforma | Validar el código de verificación (F-ACC-02) ✔ | Valida el código de 4 dígitos recibido por correo y abre la sesión con el rol y el alcance del usuario. | Estado | Sin restricción adicional | Módulo 01: Actividad 2 |
| Acceso a la plataforma | Reenviar el código de verificación (F-ACC-03) ✔ | Genera y envía un nuevo código de verificación cuando el anterior no llegó o venció. | Estado | Sin restricción adicional | Módulo 01: Actividad 2 |
| Acceso a la plataforma | Activar la cuenta desde la invitación (F-ACC-04) ✔ | Desde el enlace del correo de invitación, el usuario crea su contraseña y su cuenta pasa a Activo. | U | Sin restricción adicional | Módulo 01: Actividad 1 |
| Acceso a la plataforma | Solicitar el restablecimiento de la contraseña (F-ACC-05) ✔ | Envía al correo un enlace para crear una contraseña nueva. | U | Sin restricción adicional | Módulo 01: Actividad 3 |
| Acceso a la plataforma | Restablecer la contraseña con el enlace (F-ACC-06) ✔ | Crea una contraseña nueva que cumpla las reglas y no repita las 5 anteriores. | U | Sin restricción adicional | Módulo 01: Actividad 3 |
| Acceso a la plataforma | Cerrar sesión (F-ACC-07) ✔ | Termina la sesión del usuario desde el menú de su nombre. | Estado | Sin restricción adicional | Módulo 01: Actividad 4 |
| Acceso a la plataforma | Cierre automático de la sesión por inactividad o vencimiento (F-ACC-08) ✔ | Cierra la sesión tras 60 minutos sin actividad o cuando vence el token, y avisa con un mensaje. | Automática | Sin restricción adicional | Módulo 01: Actividad 4 |
| Acceso a la plataforma | Consultar los Términos de uso (F-ACC-09) ✔ | Muestra los términos y condiciones de uso de la plataforma, con el correo de soporte. | R | Sin restricción adicional | Módulo 01: Actividad 5 |
| Acceso a la plataforma | Contactar al soporte técnico (F-ACC-10) ✔ | Abre un correo dirigido a la cuenta de soporte de la plataforma. | R | Sin restricción adicional | Módulo 01: Actividad 5 |
| Acceso a la plataforma | Consultar Mi perfil (F-ACC-12) ✔ | Muestra los datos de la cuenta: Información General, Entidad y Acceso y Asignaciones. | R | Sin restricción adicional | Módulo 01: Actividad 6 |
| Inicio | Consultar los indicadores del Inicio (F-INI-01) ✔* | Muestra Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales y Alertas cerradas, con la tendencia "vs ultimo mes". | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 1 |
| Inicio | Consultar la última alerta emitida (F-INI-02) ✔* | Muestra el banner "Se ha emitido la Alerta Temprana…" con la alerta activa más reciente y el botón **Ver Alerta**. | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 2 |
| Inicio | Consultar "Alertas por departamento" (Top 10) (F-INI-03) ✔* | Ranking de los 10 departamentos con más alertas y su porcentaje del total. | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 2 |
| Inicio | Consultar "Alertas recientes" (F-INI-04) ✔* | Lista las 9 alertas más recientes por fecha de la alerta. | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 2 |
| Inicio | Consultar el "Porcentaje de Avance Global" (F-INI-05) ✔* | Promedio del porcentaje de cumplimiento de las alertas (no borradores) y total de actividades ejecutadas frente a programadas. | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 1 |
| Inicio | Consultar el mapa de municipios con alertas (F-INI-06) ✔* | Mapa de Colombia con los municipios que tienen alertas (rojo: inminencia; azul: estructural) y tabla accesible con los mismos datos. | R | Solo alertas con recomendaciones de su subdirección | Módulo 02: Actividad 2 |
| Inicio | Consultar el tablero público sin iniciar sesión (F-INI-07) ✔ | La página de inicio pública (`/`) muestra los mismos bloques con la información nacional, sin filtro de rol. | R | Sin restricción adicional | Módulo 02: Actividad 4 |
| Inicio | Usar el panel de accesibilidad (F-INI-08) ✔ | Activa o desactiva el alto contraste y aumenta o reduce el tamaño de letra. | U | Sin restricción adicional | Módulo 02: Actividad 3 |
| Inicio | Usar el menú lateral (F-INI-09) ✔ | Navega entre los módulos visibles para el rol; el menú se puede ocultar. | R | Sin restricción adicional | Módulo 02: Actividad 3 |
| Notificaciones | Abrir el panel de Notificaciones (F-NOT-01) ✔* | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Solo alertas con recomendaciones de su subdirección | Módulo 07: Actividad 1 |
| Notificaciones | Buscar en el panel de Notificaciones (F-NOT-02) ✔* | Filtra el historial por texto. | R | Solo alertas con recomendaciones de su subdirección | Módulo 07: Actividad 1 |
| Notificaciones | Cargar más notificaciones (F-NOT-03) ✔* | Trae 10 registros más del historial. | R | Solo alertas con recomendaciones de su subdirección | Módulo 07: Actividad 1 |
| Notificaciones | Recibir el correo de invitación (F-NOT-04) ✔ | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Sin restricción adicional | Módulo 01: Actividad 1; Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo con el código de verificación (F-NOT-05) ✔ | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Sin restricción adicional | Módulo 01: Actividad 2; Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de restablecimiento de contraseña (F-NOT-06) ✔ | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Sin restricción adicional | Módulo 01: Actividad 3; Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de recomendación asignada (F-NOT-07) ✔ | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" a las entidades principal y asociadas. | Automática | Si su subdirección es principal o asociada | Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de recomendación actualizada (F-NOT-08) ✔ | Correo "SI-CIPRAT - Recomendacion Actualizada: {código}". | Automática | Si su subdirección es principal o asociada | Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de validación del plan de acción (F-NOT-09) ✔ | Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" cuando se confirma el plan. | Automática | Si su subdirección tiene recomendaciones en la alerta | Módulo 07: Actividad 2 |
| Notificaciones | Recibir el recordatorio de informe de ejecución (F-NOT-10) ✔ | Correo "Recordatorio vencimiento plazo presentación de informe de ejecución - Alerta Temprana N° {número}" cuando faltan 30 días o menos. | Automática | Una vez por ciclo | Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de informe de seguimiento (F-NOT-11) ✔ | Correo "Notificación informe de seguimiento – Alerta Temprana N° {número}". | Automática | Sin restricción adicional | Módulo 07: Actividad 2 |
| Notificaciones | Recibir el correo de oficio de consumación (F-NOT-12) ✔ | Correo "Notificación Oficio de Consumación – Alerta(s) Temprana(s) N° {números} en sistema SI-CIPRAT". | Automática | Sin restricción adicional | Módulo 07: Actividad 2 |
| Alertas tempranas | Listar alertas (F-ALE-01) ✔* | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 1 |
| Alertas tempranas | Buscar alertas (F-ALE-02) ✔* | Busca por número o texto de la alerta. | R | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 1 |
| Alertas tempranas | Filtrar alertas (F-ALE-03) ✔* | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 1 |
| Alertas tempranas | Ver el detalle de una alerta (F-ALE-04) ✔* | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 2 |
| Alertas tempranas | Descargar el PDF de la alerta (F-ALE-05) ✔* | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 2 |
| Alertas tempranas | Consultar el historial de actividades de la alerta (F-ALE-06) ✔* | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 3 |
| Alertas tempranas | Descargar el listado de alertas (CSV) (F-ALE-07) ✔* | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Solo alertas con recomendaciones de su subdirección | Módulo 03: Actividad 4 |
| Recomendaciones | Listar las recomendaciones de una alerta (F-REC-01) ✔* | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Solo las recomendaciones cuya Entidad Principal es su subdirección | Módulo 03: Actividad 5; Módulo 04: Actividad 1 |
| Recomendaciones | Buscar y filtrar recomendaciones (F-REC-02) ✔* | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Solo las recomendaciones cuya Entidad Principal es su subdirección | Módulo 04: Actividad 1 |
| Recomendaciones | Ver el detalle de una recomendación (F-REC-03) ✔* | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Solo las recomendaciones cuya Entidad Principal es su subdirección | Módulo 04: Actividad 2 |
| Recomendaciones | Descargar las recomendaciones (CSV) (F-REC-04) ✔* | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Solo las recomendaciones cuya Entidad Principal es su subdirección | Módulo 04: Actividad 3 |
| Recomendaciones | Asignar el código RC (F-REC-08) 👁 | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Ve el código asignado | Módulo 04: Actividad 1 |
| Planes de acción | Listar las alertas con plan de acción (F-PLA-01) ✔* | Pestaña **Alertas**: por alerta muestra Ejecutado vs programado, % de cumplimiento, estado del Plan de acción y estado del Informe. | R | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 1 |
| Planes de acción | Buscar y filtrar planes de acción (F-PLA-02) ✔* | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento (0-30, 31-50, 51-80, 81-100). | R | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 1 |
| Planes de acción | Ver el detalle y el historial del plan de una alerta (F-PLA-03) ✔* | Abre la ficha con "Información de alerta" e "Historial Plan de acción". | R | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 1 |
| Planes de acción | Descargar el listado de planes (CSV) (F-PLA-04) ✔* | Descarga Número de Alerta, Cumplimiento (%) y Plan de Acción de las alertas visibles. | Archivo | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 1 |
| Planes de acción | Ver las recomendaciones del plan de una alerta (F-PLA-05) ✔* | Desde **Ir al plan de acción**, lista las recomendaciones con Actividades (Aprobadas / Total) y Ejecución; **Ver Actividades** abre las actividades. | R | Solo las recomendaciones de su subdirección | Módulo 05: Actividad 2 |
| Planes de acción | Consultar la pestaña global de Recomendaciones (F-PLA-06) ✔* | Pestaña **Recomendaciones** con todas las recomendaciones del alcance, filtros (alerta, eje, entidad) y descarga. | R | Solo las recomendaciones de su subdirección | Módulo 05: Actividad 3 |
| Planes de acción | Consultar la pestaña global de Actividades (F-PLA-07) ✔* | Pestaña **Actividades** con todas las actividades del alcance: Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe, Próximo Informe; filtros y descarga. | R | Filtra por su entidad central y no por su subdirección (riesgo R5) | Módulo 05: Actividad 3 |
| Planes de acción | Listar las actividades de una recomendación (F-PLA-08) ✔* | Muestra Actividad, Objetivo, Descripción, Número Actividades, Ejecución (Ejecutadas / Programadas), Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; busca por objetivo y filtra por Estado, Instrumento de Planeación y Recursos. | R | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 4 |
| Planes de acción | Ver el detalle de una actividad (F-PLA-09) ✔* | Abre "Detalle de Actividad": Recomendación, campos de la actividad, Estado Informe, Ejecución y Próximo Informe. | R | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 4 |
| Planes de acción | Descargar las actividades (CSV) (F-PLA-10) ✔* | Descarga Número de Alerta, Código de Recomendación, Objetivo, Descripción, Número de Actividades, Plazo, Instrumento, Recursos, Estado, Observaciones y fechas. | Archivo | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 3; Módulo 05: Actividad 4 |
| Planes de acción | Agregar una actividad (F-PLA-11) ✔* | Registra en 2 pasos el Objetivo y la información de la actividad (Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos, Observaciones). | C | Sobre las recomendaciones de su subdirección que ve en su listado; alerta no cerrada | Módulo 05: Actividad 5 |
| Planes de acción | Agregar una actividad a un plan confirmado (F-PLA-12) ✔* | Si el plan ya está confirmado, el sistema advierte "Agregar actividad a plan confirmado" y, al continuar, desconfirma el plan. | Estado | Sobre las recomendaciones de su subdirección que ve en su listado; alerta no cerrada | Módulo 05: Actividad 6 |
| Planes de acción | Editar una actividad (F-PLA-13) ✔* | Modifica los campos de una actividad pendiente de aprobación. | U | Solo actividades pendientes; plan no confirmado; alerta no cerrada | Módulo 05: Actividad 7 |
| Planes de acción | Eliminar una actividad (F-PLA-14) ✔* | Elimina una actividad pendiente de aprobación. | D | Solo actividades pendientes; plan no confirmado; alerta no cerrada | Módulo 05: Actividad 7 |
| Planes de acción | Ver y escribir comentarios de una actividad (F-PLA-15) ✔* | Abre la conversación de la actividad y agrega comentarios (hasta 2.000 caracteres). | C | Desde Planes de acción, en actividades de su subdirección y con la alerta abierta | Módulo 05: Actividad 8 |
| Planes de acción | Reportar un informe de ejecución (F-PLA-17) ✔* | Registra lo ejecutado en el ciclo: actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades y el PDF de soporte. | C | Solo con el plan confirmado y la actividad "Sin Informe" | Módulo 05: Actividad 9 |
| Planes de acción | Editar un informe de ejecución pendiente (F-PLA-18) ✔* | Corrige el informe y su PDF mientras no esté aprobado. | U | Solo informes no aprobados | Módulo 05: Actividad 10 |
| Planes de acción | Consultar los informes de ejecución y descargar su PDF (F-PLA-19) ✔* | En el detalle de la recomendación (pestaña de actividades) muestra "Informes de ejecución" con todos sus campos y el archivo "Informe.pdf". | Archivo | Solo alertas con recomendaciones de su subdirección | Módulo 05: Actividad 11 |
| Oficios de consumación | Listar los oficios de consumación (F-OFI-01) ✔* | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Solo oficios de alertas con recomendaciones de su subdirección | Módulo 06: Actividad 1 |
| Oficios de consumación | Buscar y filtrar oficios por alerta (F-OFI-02) ✔* | Busca por radicado y filtra por Alerta asociada. | R | Solo oficios de alertas con recomendaciones de su subdirección | Módulo 06: Actividad 1 |
| Oficios de consumación | Ver el detalle de un oficio (F-OFI-03) ✔* | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Solo oficios de alertas con recomendaciones de su subdirección | Módulo 06: Actividad 1 |
| Oficios de consumación | Descargar el PDF del oficio (F-OFI-04) ✔* | Descarga el archivo del oficio. | Archivo | Solo oficios de alertas con recomendaciones de su subdirección | Módulo 06: Actividad 1 |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01) 👁 | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Ve la fecha y el estado resultantes en las actividades | Módulo 05: Actividad 4; Módulo 05: Actividad 9 |
| Tareas programadas | Enviar el recordatorio de informe de ejecución (F-TAR-02) ✔ | Cada día a las 00:01 envía el recordatorio cuando faltan 30 días o menos para el próximo informe (una vez por ciclo). | Automática | Es destinataria | Módulo 07: Actividad 2 |
| Tareas programadas | Recalcular estados y porcentajes de cumplimiento (F-TAR-03) 👁 | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Ve los estados y porcentajes recalculados | Módulo 02: Actividad 1; Módulo 05: Actividad 4; Módulo 05: Actividad 5 |
| Tareas programadas | Calcular el próximo informe al aprobar un informe (F-TAR-04) 👁 | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Ve los estados y porcentajes recalculados | Módulo 05: Actividad 4; Módulo 05: Actividad 9 |

### Qué NO puede hacer el usuario de Entidad Territorial (Subdirección)

| Módulo | Funcionalidad | Definición | Cómo lo impide el sistema | Qué hacer si lo necesita |
|---|---|---|---|---|
| Acceso a la plataforma | Cambiar la contraseña con la contraseña actual (F-ACC-11) ✖ | Servicio del servidor para cambiar la contraseña indicando la actual. Existe en la API, pero ninguna pantalla lo usa. | UI: no existe una pantalla que use este servicio (`main-api/CipratApi/Controladores/AutenticacionControlador.cs:147`; solo `dashboard/src/contexts/AuthContext.tsx` lo referencia) | Use **¿Has olvidado tu contraseña?** para cambiarla |
| Acceso a la plataforma | Editar los datos del propio perfil (F-ACC-13) ✖ | Servicio del servidor para actualizar los datos del propio usuario. En la pantalla Mi perfil los campos están deshabilitados. | UI: los campos de Mi perfil están deshabilitados (`dashboard/src/pages/MyProfile.tsx:124-183`) | Pida el cambio a quien administra los usuarios (Super Administrador o Administrador) |
| Acceso a la plataforma | Consultar el historial de cambios de contraseña (F-ACC-14) ✖ | Servicio del servidor que informa la fecha y el método del último cambio de contraseña. Ninguna pantalla lo muestra. | UI: el hook `usePasswordHistory` existe, pero Mi perfil no lo muestra (`dashboard/src/hooks/usePasswordHistory.ts:20`, `dashboard/src/pages/MyProfile.tsx`) | No disponible en la interfaz |
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
| Planes de acción | Eliminar un comentario propio (F-PLA-16) ✖ | Servicio del servidor que permite al autor eliminar su comentario. La ventana de comentarios no tiene esa opción. | UI: la ventana "Comentarios" no ofrece eliminar (`dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`); la API lo permite al autor (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:140`) | No disponible en la interfaz |
| Seguimiento | Listar los planes en Seguimiento (F-SEG-01) ✖ | Pantalla "Seguimiento de Planes": por alerta muestra Ejecutado vs programado, Plan de acción e Informe, y la acción para confirmar el plan. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Consulte el estado en *Planes de acción* |
| Seguimiento | Buscar y filtrar planes en Seguimiento (F-SEG-02) ✖ | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Consulte el estado en *Planes de acción* |
| Seguimiento | Descargar el listado de Seguimiento (CSV) (F-SEG-03) ✖ | Descarga el listado de planes visible. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Consulte el estado en *Planes de acción* |
| Seguimiento | Consultar recomendaciones, actividades e informes en Seguimiento (F-SEG-04) ✖ | Recorre alerta › recomendaciones › actividades en modo seguimiento, con el panel "Información Actividades" y los "Informes de ejecución". | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Consulte el estado en *Planes de acción* |
| Seguimiento | Marcar una actividad como revisada (F-SEG-05) ✖ | Deja constancia (usuario y fecha) de que revisó la actividad; no cambia su estado. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar una actividad (F-SEG-06) ✖ | Aprueba la actividad pendiente; si es la última pendiente, la recomendación y el plan pasan a Aprobado. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Descartar la aprobación de una actividad (F-SEG-07) ✖ | Devuelve una actividad aprobada a "Pendiente de aprobación". | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Validar si el plan se puede confirmar (F-SEG-08) ✖ | Al abrir la confirmación, el sistema muestra el resumen (Total de recomendaciones, de actividades y de actividades programadas) o lo que falta ("El plan de acción tiene N actividades pendientes de aprobación y N recomendaciones sin actividades"). | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Confirmar el plan de acción (F-SEG-09) ✖ | Confirma el plan completo de la alerta cuando todas sus actividades están aprobadas; habilita los informes de ejecución y notifica a las entidades. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar un informe de ejecución (F-SEG-10) ✖ | Aprueba el informe pendiente y el sistema fija la fecha del próximo informe. | UI: el menú no muestra *Seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:58-62`) | Monitor o Líder de Macrozona del departamento |
| Informe de recomendaciones | Consultar el Informe de recomendaciones (F-IRE-01) ✖ | Tablero con Información alertas, Información recomendaciones, Información actividades y Cumplimiento por Entidad Principal y por Eje Temático. | API: `RequireReportes` responde "No tiene permisos para acceder al módulo de reportes" (`main-api/CipratApi/Controladores/ReportesControlador.cs:39-40`) | Pida el consolidado a un Monitor, Líder de Macrozona o Administrador |
| Informe de recomendaciones | Filtrar el Informe de recomendaciones por alerta (F-IRE-02) ✖ | Cambia el consolidado de "Todas las alertas" a una alerta. | API: `RequireReportes` responde "No tiene permisos para acceder al módulo de reportes" (`main-api/CipratApi/Controladores/ReportesControlador.cs:39-40`) | Pida el consolidado a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Listar los reportes de ejecución (F-REP-01) ✖ | Pantalla "Reportes de ejecución" con las pestañas Todos, Alerta, Entidad y Regional y la tabla Informe, Tipo, Publicado, Estado y Aprobador. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Buscar y filtrar reportes (F-REP-02) ✖ | Busca por nombre y filtra por Tipo, Estado, Alerta asociada, Entidad, Departamento y Municipio. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Ver el detalle de un reporte (F-REP-03) ✖ | Muestra Nombre del reporte, Etiqueta (tipo), Fecha de publicacion, Estado, Descripcion, Adjunto y Aprobador. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Descargar un reporte (F-REP-04) ✖ | Descarga el PDF del reporte. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Cargar un reporte de ejecución (F-REP-05) ✖ | Registra el tipo (Alerta, Entidad, Depto, Municipio), su alcance, la fecha, el aprobador, la descripción y el PDF. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Editar un reporte de ejecución (F-REP-06) ✖ | Modifica los datos o el PDF del reporte desde su detalle. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Reportes | Eliminar un reporte de ejecución (F-REP-07) ✖ | Elimina un reporte que no está aprobado. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Super Administrador |
| Reportes | Aprobar un reporte de ejecución (F-REP-08) ✖ | El aprobador designado aprueba el reporte. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | El aprobador designado (Líder de Macrozona o Super Administrador) |
| Reportes | Generar un informe ejecutivo en Word (Panel de consultas) (F-REP-09) ✖ | Genera y descarga un documento Word por Alerta, Entidad, Depto, Municipio o General. | UI y API: sin menú, ruta bloqueada y `RequireReportes` (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`) | Pida la información a un Monitor, Líder de Macrozona o Administrador |
| Informes de seguimiento | Listar los informes de seguimiento (F-ISE-01) ✖ | Tabla con Informe, Fecha de creación, Fecha de finalización y Alertas asociadas. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Pida la información a la Secretaría Técnica |
| Informes de seguimiento | Buscar y filtrar informes por alerta (F-ISE-02) ✖ | Busca por número y filtra por Alerta asociada. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Pida la información a la Secretaría Técnica |
| Informes de seguimiento | Ver el detalle de un informe de seguimiento (F-ISE-03) ✖ | Muestra Informacion basica, Detalles del seguimiento y Archivo adjunto. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Pida la información a la Secretaría Técnica |
| Informes de seguimiento | Descargar el PDF del informe de seguimiento (F-ISE-04) ✖ | Descarga el archivo del informe. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Pida la información a la Secretaría Técnica |
| Informes de seguimiento | Cargar un informe de seguimiento (F-ISE-05) ✖ | Registra en 2 pasos el número, la alerta, las fechas, el radicado y el PDF, y las modificaciones a la alerta. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Super Administrador o Administrador |
| Informes de seguimiento | Modificar municipios y agregar recomendaciones desde el informe (F-ISE-06) ✖ | En el paso 2 marca municipios como cerrados, agrega municipios y agrega recomendaciones nuevas. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Super Administrador o Administrador |
| Informes de seguimiento | Cerrar la alerta con el informe de seguimiento (F-ISE-07) ✖ | Marca "Cerrar la alerta con este informe" para que la alerta quede Cerrada al guardar. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Super Administrador |
| Informes de seguimiento | Editar un informe de seguimiento (F-ISE-08) ✖ | Modifica los datos del informe (la alerta asociada no se cambia). | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Super Administrador o Administrador |
| Informes de seguimiento | Eliminar un informe de seguimiento (F-ISE-09) ✖ | Elimina un informe cuya alerta no está cerrada. | UI: el menú no muestra *Informes de seguimiento* (`dashboard/src/components/layout/Sidebar.tsx:63`) | Super Administrador |
| Oficios de consumación | Cargar un oficio de consumación (F-OFI-05) ✖ | Registra en 2 pasos el radicado, las fechas, el tema clave, las alertas asociadas y el PDF, y las modificaciones por alerta. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Modificar municipios y agregar recomendaciones desde el oficio (F-OFI-06) ✖ | Para cada alerta asociada, marca municipios como cerrados, agrega municipios y agrega recomendaciones. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Editar un oficio de consumación (F-OFI-07) ✖ | Modifica los datos del oficio. | UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`) | Super Administrador |
| Oficios de consumación | Eliminar un oficio de consumación (F-OFI-08) ✖ | Elimina el oficio. | UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`) | Super Administrador |

## Segmentación de visualización

- **Inicio:** indicadores, ranking, alertas recientes y mapa calculados sobre las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`) (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores.
- **Alertas tempranas:** ve las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`).
- **Recomendaciones de una alerta:** dentro de cada alerta solo ve las recomendaciones cuya Entidad Principal es su subdirección; las de otras entidades no aparecen (`main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:144-152`).
- **Planes de acción:** ve los planes, recomendaciones y actividades de las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`).
- **Seguimiento:** no aparece en su menú (`dashboard/src/components/layout/Sidebar.tsx:58-62`).
- **Reportes:** no tiene acceso (`dashboard/src/App.tsx:64`, `main-api/CipratApi/Filtros/RequireReportesAttribute.cs:21-38`).
- **Informes de seguimiento:** no aparece en su menú (`dashboard/src/components/layout/Sidebar.tsx:63`).
- **Oficios de consumación:** ve solo los asociados a alertas con recomendaciones de su subdirección (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`).
- **Notificaciones (panel):** ve el historial de actividad de las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`) (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`).
- **Usuarios y entidades:** no aparece en su menú (`dashboard/src/components/layout/Sidebar.tsx:38-42`).

## Ruta de aprendizaje

### Módulo 00: Contexto de la plataforma SI-CIPRAT

**Prerrequisitos:** Ninguno.

**Definición del módulo:** Módulo introductorio que presenta qué es SI-CIPRAT, quiénes intervienen, cómo avanza una alerta temprana de la fase E0 a la E6 y qué papel cumple el usuario de Entidad Territorial (Subdirección) en ese ciclo.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda explicar qué es SI-CIPRAT, cómo avanza una alerta de E0 a E6 y en qué momentos interviene su rol.

**Contexto del módulo:** Antes de operar, el usuario de Entidad Territorial (Subdirección) necesita entender en qué parte del ciclo actúa, qué recibe de otros actores y qué entrega, porque el sistema le habilita o le bloquea acciones según el estado de cada alerta, recomendación, actividad e informe.

**Funcionalidades disponibles:** Ninguna funcionalidad del sistema (módulo conceptual).

#### Actividad 1: Conocer qué es SI-CIPRAT y para qué existe

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda explicar qué es SI-CIPRAT, a qué institución sirve y qué componentes tiene.

**Pasos:**

##### Paso 1.1: Leer el propósito de la plataforma
**Objetivo del paso:** Entender para qué existe el sistema.
**Qué hacer:** Lea: SI-CIPRAT es el Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT), del Ministerio del Interior. Registra las alertas tempranas que emite la Defensoría del Pueblo, las recomendaciones que se derivan de ellas, los planes de acción con que las entidades responden y los informes de su ejecución, hasta el cierre de la alerta.
**Resultado esperado:** Puede explicar en una frase para qué sirve la plataforma.

##### Paso 1.2: Identificar a los actores institucionales
**Objetivo del paso:** Saber quién hace qué fuera y dentro del sistema.
**Qué hacer:** Distinga: la Defensoría del Pueblo emite las alertas, los informes de seguimiento y los oficios de consumación (no es usuario de SI-CIPRAT: su información llega de forma automática o la registra el Ministerio); la Secretaría Técnica de la CIPRAT administra la plataforma, registra y supervisa; las entidades responsables formulan y ejecutan los planes.
**Resultado esperado:** Identifica a la Defensoría, la Secretaría Técnica y las entidades.

##### Paso 1.3: Reconocer los componentes del sistema
**Objetivo del paso:** Saber de dónde viene la información que verá.
**Resultado esperado:** Sabe que algunas alertas y recomendaciones llegan solas ("Automática") y que hay procesos que corren cada noche.

#### Actividad 2: Comprender los actores y el ciclo de vida de una alerta temprana (E0–E6), incluidos los momentos en que el proceso continúa fuera de la plataforma

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda describir las fases E0 a E6 del ciclo de una alerta, sus actores y los puntos donde el flujo sale de la plataforma.

Puntos donde el flujo sale de la plataforma (solo lo que muestra el código):

| Secuencia | Acción | ⤴ Qué ocurre por fuera y qué vuelve | Evidencia |
|---|---|---|---|
| E1.2 | Crear Alerta desde PDF (Agente IA) | El PDF llega por fuera de la plataforma | main-api/CipratApi/Controladores/AlertasControlador.cs:409-489 |
| E1.3 | Reportar alerta › Enviar Alerta (6 pasos) | El documento de la alerta llega por fuera de la plataforma | main-api/CipratApi/Controladores/AlertasControlador.cs:336-387 |
| E2.2 | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" | El correo se recibe fuera de la plataforma; la respuesta vuelve como actividades | main-api/CipratApi/Servicios/EmailService.cs:151 |
| E4.1 | Revisar: Comentarios y Marcar como Revisado | Las mesas técnicas de revisión, si existen, ocurren por fuera; vuelven como comentarios y aprobaciones | main-api/CipratApi/Controladores/RevisionesActividadControlador.cs:77-100 |
| E5.1 | Reportar Informe › Reportar informe de ejecución (con PDF) | El soporte de la ejecución se produce por fuera; vuelve como PDF | main-api/CipratApi/Controladores/InformesEjecucionControlador.cs:35-41 |
| E6.1 | Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) | El informe lo emite la Defensoría por fuera (o llega de forma automática) | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:185-265 |
| E6.2 | Cargar oficio de consumación | El oficio lo emite la Defensoría por fuera (o llega de forma automática) | main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:182-238 |
| E6.3 | Cerrar alertas | La decisión de cierre se toma por fuera; vuelve con el consecutivo y el PDF | main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:88-125 |

**Pasos:**

##### Paso 2.1: Fase E0: Preparación del sistema (usuarios y entidades)
**Objetivo del paso:** Ubicar qué ocurre en la fase E0.
**Qué hacer:** E0.1 Agregar Entidad (entidad central y subdirecciones) (Super Administrador, Administrador); E0.2 Enviar invitación (rol, nivel de acceso, entidad, subdirección, departamentos, cargo) (Super Administrador, Administrador); E0.3 Activar cuenta (crear contraseña) (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos)); E0.4 Iniciar Sesión y Validar código (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos)); E0.5 Editar usuario, activar o inactivar, Reenviar o Eliminar invitación (Super Administrador, Administrador); E0.6 ¿Has olvidado tu contraseña? › Restablecer contraseña (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos)).
**Resultado esperado:** Reconoce las acciones de la fase E0 y quién las hace.

##### Paso 2.2: Fase E1: Registro de la alerta
**Objetivo del paso:** Ubicar qué ocurre en la fase E1.
**Qué hacer:** E1.1 Envío de la alerta de forma automática (con sus recomendaciones) (Defensoría, Sistema); E1.2 Crear Alerta desde PDF (Agente IA) (Super Administrador); E1.3 Reportar alerta › Enviar Alerta (6 pasos) (Super Administrador, Administrador); E1.4 Adjuntar "PDF de la alerta" y "Adjunto" (Super Administrador); E1.5 Editar alerta y Publicar alerta al guardar (Super Administrador, Administrador); E1.6 Esta alerta subsume otras alertas (Super Administrador, Administrador); E1.7 Eliminar alerta (Super Administrador); E1–E6 Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos)).
**Resultado esperado:** Reconoce las acciones de la fase E1 y quién las hace.

##### Paso 2.3: Fase E2: Recomendaciones
**Objetivo del paso:** Ubicar qué ocurre en la fase E2.
**Qué hacer:** E2.1 Agregar recomendación › Crear recomendación (Super Administrador, Administrador); E2.2 Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" (Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección)); E2.3 Editar recomendación (Super Administrador, Administrador); E2.4 Eliminar recomendación (Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E2 y quién las hace.

##### Paso 2.4: Fase E3: Plan de acción (formulación)
**Objetivo del paso:** Ubicar qué ocurre en la fase E3.
**Qué hacer:** E3.1 Consultar las recomendaciones asignadas (Ir al plan de acción) (Entidad Territorial (Central), Entidad Territorial (Subdirección)); E3.2 Agregar actividad › Reportar actividad (Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador); E3.3 Editar Actividad / Eliminar Actividad (Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador); E3.4 Comentarios de la actividad (Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos)).
**Resultado esperado:** Reconoce las acciones de la fase E3 y quién las hace.

##### Paso 2.5: Fase E4: Aprobación y confirmación del plan
**Objetivo del paso:** Ubicar qué ocurre en la fase E4.
**Qué hacer:** E4.1 Revisar: Comentarios y Marcar como Revisado (Monitor, Líder de Macrozona, Super Administrador); E4.2 Aprobar / Descartar aprobación (Monitor, Líder de Macrozona, Super Administrador); E4.3 Confirmar Plan de Acción (Monitor, Líder de Macrozona, Super Administrador); E4.4 Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" (Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección)); E4.5 Agregar actividad a plan confirmado › Continuar (Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E4 y quién las hace.

##### Paso 2.6: Fase E5: Informes de ejecución
**Objetivo del paso:** Ubicar qué ocurre en la fase E5.
**Qué hacer:** E5.1 Reportar Informe › Reportar informe de ejecución (con PDF) (Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador); E5.2 Editar Informe (Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador); E5.3 Aprobar Informe (Monitor, Líder de Macrozona, Super Administrador); E5.4 Correo "Recordatorio vencimiento plazo presentación de informe de ejecución" (Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección)); E5.5 Tarea diaria 00:01: vencimiento del ciclo (Sistema); E5.6 Cargar informe (reporte de ejecución) con aprobador (Monitor, Líder de Macrozona, Administrador, Super Administrador); E5.7 Aprobar informe (reporte de ejecución), solo el aprobador designado (Líder de Macrozona, Super Administrador); E5.8 Consultas › Generar consulta (informe ejecutivo Word) (Monitor, Líder de Macrozona, Administrador, Super Administrador); E5.9 Informe (Informe de recomendaciones) (Monitor, Líder de Macrozona, Administrador, Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E5 y quién las hace.

##### Paso 2.7: Fase E6: Seguimiento y cierre
**Objetivo del paso:** Ubicar qué ocurre en la fase E6.
**Qué hacer:** E6.1 Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) (Super Administrador, Administrador, Defensoría); E6.2 Cargar oficio de consumación (Super Administrador, Defensoría); E6.3 Cerrar alertas (Super Administrador).
**Resultado esperado:** Reconoce las acciones de la fase E6 y quién las hace.

##### Paso 2.8: Identificar dónde el flujo sale de la plataforma
**Objetivo del paso:** Saber qué partes del proceso no quedan en el sistema.
**Qué hacer:** Lea los puntos marcados "⤴ El flujo continúa por fuera de la plataforma" en la tabla de esta actividad.
**Resultado esperado:** Identifica qué dato o archivo vuelve al sistema en cada punto.

#### Actividad 3: Ubicar el papel de Entidad Territorial (Subdirección) en el ciclo: su línea de tiempo

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ubicar en qué momentos del ciclo actúa, qué espera de otros actores y qué entrega.

| Secuencia | Fase | Acción | Disparador | Plazo | Qué sigue y quién |
|---|---|---|---|---|---|
| E0.3 | Preparación del sistema (usuarios y entidades) | Activar cuenta (crear contraseña) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" | ≤ 7 días desde E0.2 | E0.4 el mismo usuario |
| E0.4 | Preparación del sistema (usuarios y entidades) | Iniciar Sesión y Validar código | E0.3 | Código válido 1 hora; sesión de 720 minutos; cierre a los 60 minutos de inactividad | Según el rol |
| E0.6 | Preparación del sistema (usuarios y entidades) | ¿Has olvidado tu contraseña? › Restablecer contraseña | El usuario olvidó la contraseña | Enlace válido 1 hora | E0.4 |
| E2.2 | Recomendaciones | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" | E2.1 o E1.1 | Inmediato | E3.1 Entidad Territorial |
| E3.1 | Plan de acción (formulación) | Consultar las recomendaciones asignadas (Ir al plan de acción) | E2.2 | El sistema no fija plazo | E3.2 |
| E3.2 | Plan de acción (formulación) | Agregar actividad › Reportar actividad | E3.1 | El sistema no fija plazo | E4.1 Monitor o Líder de Macrozona |
| E3.3 | Plan de acción (formulación) | Editar Actividad / Eliminar Actividad | E3.2; actividad pendiente; plan sin confirmar | Antes de la aprobación | E4.1 |
| E3.4 | Plan de acción (formulación) | Comentarios de la actividad | Actividad registrada | | E3.3 o E4.2 |
| E4.4 | Aprobación y confirmación del plan | Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" | E4.3 | Inmediato | E5.1 |
| E4.5 | Aprobación y confirmación del plan | Agregar actividad a plan confirmado › Continuar | E4.3 | | E4.1-E4.3 de nuevo |
| E5.1 | Informes de ejecución | Reportar Informe › Reportar informe de ejecución (con PDF) | E4.3 (plan confirmado) | Sin fecha antes del primer informe; luego hasta el Próximo Informe | E5.3 Monitor o Líder de Macrozona |
| E5.2 | Informes de ejecución | Editar Informe | E5.1; informe no aprobado | Hasta su aprobación | E5.3 |
| E5.4 | Informes de ejecución | Correo "Recordatorio vencimiento plazo presentación de informe de ejecución" | E5.3 (hay Próximo Informe) | Cuando faltan 30 días o menos; una vez por ciclo | E5.1 del siguiente ciclo |
| E1–E6 | Registro de la alerta | Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF | Desde E1 | Permanente | |

**Pasos:**

##### Paso 3.1: Leer su línea de tiempo
**Objetivo del paso:** Conocer sus momentos de intervención.
**Qué hacer:** Recorra la tabla de esta actividad en orden de secuencia.
**Resultado esperado:** Identifica sus 14 momentos de intervención.

##### Paso 3.2: Identificar a quién espera
**Objetivo del paso:** Saber de qué depende para actuar.
**Qué hacer:** Lea la columna "Disparador" de cada fila.
**Resultado esperado:** Sabe qué debe haber pasado antes de cada acción.

##### Paso 3.3: Identificar a quién entrega
**Objetivo del paso:** Saber qué sigue después de su acción.
**Qué hacer:** Lea la columna "Qué sigue y quién".
**Resultado esperado:** Sabe a qué actor le entrega el trabajo.

#### Actividad 4: Conocer los módulos que usará y cómo está organizada esta ruta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda identificar los módulos de su ruta y la estructura de módulo, actividades y pasos.

| Módulo | Nombre | Objetivo |
|---|---|---|
| Módulo 01 | Acceso a la plataforma | Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. |
| Módulo 02 | Inicio | Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. |
| Módulo 03 | Alertas tempranas | Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. |
| Módulo 04 | Recomendaciones | Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. |
| Módulo 05 | Planes de acción | Que cada entidad responsable formule las actividades con las que atenderá sus recomendaciones y reporte periódicamente lo ejecutado. |
| Módulo 06 | Oficios de consumación | Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. |
| Módulo 07 | Notificaciones | Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. |
| Módulo 08 | Práctica con el caso AT-013-25 | Practicar todas las actividades de la ruta. |

**Pasos:**

##### Paso 4.1: Revisar la lista de módulos
**Objetivo del paso:** Saber qué aprenderá.
**Qué hacer:** Lea la tabla de módulos de esta actividad.
**Resultado esperado:** Conoce los módulos y su objetivo.

##### Paso 4.2: Entender la estructura de cada actividad
**Objetivo del paso:** Saber cómo leer la ruta.
**Qué hacer:** Cada actividad trae objetivo, requisitos previos (reglas RN-…), dónde, qué ve, campos, pasos con objetivo, resultado, escenarios de error, avisos ⚠️ y ejemplo.
**Resultado esperado:** Sabe dónde buscar cada tipo de información.

##### Paso 4.3: Ubicar los bloques finales
**Objetivo del paso:** Saber dónde consultar dudas.
**Qué hacer:** Al final están Alcance y límites, Indicadores de logro, Preguntas frecuentes de uso, Errores frecuentes y cómo solucionarlos y el Glosario de la ruta.
**Resultado esperado:** Sabe dónde resolver dudas y problemas.

### Módulo 01: Acceso a la plataforma

**Prerrequisitos:** Haber recibido el correo de invitación (lo envía el Super Administrador o el Administrador).

**Definición del módulo:** Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. También muestra los Términos de uso y el correo de soporte técnico.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda activar la cuenta desde la invitación; iniciar sesión con el código de verificación; recuperar la contraseña; cerrar sesión y entender el cierre automático; consultar los Términos de uso y contactar al soporte técnico; consultar Mi perfil y verificar el alcance asignado.

**Contexto del módulo:** Interviene en la preparación (E0.3 activación, E0.4 primer ingreso, E0.6 recuperación de la contraseña) y en cada sesión de trabajo. Recibe la invitación y los datos creados en *Usuarios y entidades* (E0.2, E0.5) y entrega al usuario la sesión con la que el sistema aplica su rol y su alcance de datos. Lo usan todos los roles y subroles, sin diferencias de alcance. Lo activan la invitación (enlace válido 7 días), el ingreso (código válido 1 hora) y la inactividad (60 minutos). Para el usuario de Entidad Territorial (Subdirección): en total, tiene 11 de las 14 funcionalidades del módulo; no tiene: cambiar la contraseña con la contraseña actual, editar los datos del propio perfil, consultar el historial de cambios de contraseña.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Iniciar sesión con correo y contraseña (F-ACC-01) | Verifica el correo y la contraseña y, si son correctos, envía al correo del usuario un código de verificación de 4 dígitos. | Estado | Módulo 01: Actividad 2 |
| Validar el código de verificación (F-ACC-02) | Valida el código de 4 dígitos recibido por correo y abre la sesión con el rol y el alcance del usuario. | Estado | Módulo 01: Actividad 2 |
| Reenviar el código de verificación (F-ACC-03) | Genera y envía un nuevo código de verificación cuando el anterior no llegó o venció. | Estado | Módulo 01: Actividad 2 |
| Activar la cuenta desde la invitación (F-ACC-04) | Desde el enlace del correo de invitación, el usuario crea su contraseña y su cuenta pasa a Activo. | U | Módulo 01: Actividad 1 |
| Solicitar el restablecimiento de la contraseña (F-ACC-05) | Envía al correo un enlace para crear una contraseña nueva. | U | Módulo 01: Actividad 3 |
| Restablecer la contraseña con el enlace (F-ACC-06) | Crea una contraseña nueva que cumpla las reglas y no repita las 5 anteriores. | U | Módulo 01: Actividad 3 |
| Cerrar sesión (F-ACC-07) | Termina la sesión del usuario desde el menú de su nombre. | Estado | Módulo 01: Actividad 4 |
| Cierre automático de la sesión por inactividad o vencimiento (F-ACC-08) | Cierra la sesión tras 60 minutos sin actividad o cuando vence el token, y avisa con un mensaje. | Automática | Módulo 01: Actividad 4 |
| Consultar los Términos de uso (F-ACC-09) | Muestra los términos y condiciones de uso de la plataforma, con el correo de soporte. | R | Módulo 01: Actividad 5 |
| Contactar al soporte técnico (F-ACC-10) | Abre un correo dirigido a la cuenta de soporte de la plataforma. | R | Módulo 01: Actividad 5 |
| Consultar Mi perfil (F-ACC-12) | Muestra los datos de la cuenta: Información General, Entidad y Acceso y Asignaciones. | R | Módulo 01: Actividad 6 |
| Recibir el correo de invitación (F-NOT-04, módulo Notificaciones) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Módulo 01: Actividad 1 |
| Recibir el correo con el código de verificación (F-NOT-05, módulo Notificaciones) | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Módulo 01: Actividad 2 |
| Recibir el correo de restablecimiento de contraseña (F-NOT-06, módulo Notificaciones) | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Módulo 01: Actividad 3 |

#### Actividad 1: Activar la cuenta desde la invitación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

**Cuándo se hace y requisitos previos:** Secuencia E0.3.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para activar la cuenta, el enlace de invitación debe tener menos de 7 días y no haberse usado. | Revise la fecha del correo de invitación | Pedir que reenvíen la invitación (Super Administrador o Administrador) | RN-ACC-04 |
| La contraseña debe tener al menos 8 caracteres y al menos un carácter especial, y las dos casillas deben coincidir. | Los indicadores de la pantalla se marcan en verde | Escribir una contraseña que cumpla los indicadores de la pantalla (El propio usuario) | RN-ACC-05 |

**Dónde:** Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" › enlace › pantalla "Configura tu contraseña" (`/setup/:token`).

**Qué ve:** Una pantalla con el título "Configura tu contraseña" y el texto "Establece una contraseña para activar tu cuenta en la plataforma.", dos campos (**Nueva Contraseña** y **Confirmar Contraseña**), los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial", el botón **Activar cuenta** y el enlace "¿Necesita soporte técnico?".

**Campos a diligenciar: Activar la cuenta (Configura tu contraseña):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Nueva Contraseña (`newPassword`) | Sí | Texto oculto | Mínimo 8 caracteres y al menos un carácter especial | |, | Prueba#2026 | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" |
| 2 | Confirmar Contraseña (`confirmPassword`) | Sí | Texto oculto | Igual a Nueva Contraseña | | Nueva Contraseña | Prueba#2026 | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." |

- Campos que llena el sistema: El correo del usuario viene en el enlace.
- Campos que se bloquean: El enlace se invalida después de usarlo.
- Archivos: No aplica.
- Guardar o enviar con: **Activar cuenta**.

**Pasos:**

##### Paso 1.1: Abrir el enlace de la invitación
**Objetivo del paso:** Llegar a la pantalla de activación con un enlace válido.
**Qué hacer:** Abra el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" y haga clic en el enlace. Hágalo antes de 7 días desde el envío.
**Resultado esperado:** Se abre "Configura tu contraseña". Si el enlace venció, aparece "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."

##### Paso 1.2: Escribir la nueva contraseña
**Objetivo del paso:** Crear una contraseña que cumpla las reglas de seguridad.
**Qué hacer:** En **Nueva Contraseña** escriba al menos 8 caracteres e incluya un carácter especial (por ejemplo, # o !). Use el ícono del ojo para verificar lo escrito.
**Resultado esperado:** Los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial" se marcan como cumplidos.

##### Paso 1.3: Confirmar la contraseña
**Objetivo del paso:** Evitar errores de digitación.
**Qué hacer:** En **Confirmar Contraseña** escriba exactamente la misma contraseña.
**Resultado esperado:** Si no coinciden, al enviar aparece "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."

##### Paso 1.4: Activar la cuenta
**Objetivo del paso:** Dejar la cuenta en estado Activo.
**Qué hacer:** Revise que los dos campos coincidan y haga clic en **Activar cuenta**.
**Resultado esperado:** El botón muestra "Activando cuenta..." y luego la pantalla confirma; la cuenta queda Activa y puede iniciar sesión.

> 📷 **[CAPTURA MED-06-ACC-01]**: Pantalla "Configura tu contraseña"
> **Debe mostrar:** La pantalla de activación con los dos campos y los indicadores de la contraseña
> **Resaltar:** Campos Nueva Contraseña y Confirmar Contraseña; botón Activar cuenta
> **Pantalla / ruta:** `/setup/:token` (`dashboard/src/pages/auth/ResetPassword.tsx:198-317`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Invitación de prueba vigente
> **Texto alternativo:** Formulario para crear la contraseña y activar la cuenta

**Resultado de la actividad:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el enlace de invitación después de 7 días | "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador." | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Active la cuenta apenas reciba el correo. |
| Abrir un enlace de invitación incompleto o ya usado | "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada" | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | No copie el enlace a mano. |
| Crear una contraseña corta o sin símbolos | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña debe contener al menos un carácter especial") | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Revise los indicadores de la pantalla antes de enviar. |
| Escribir diferente la confirmación de la contraseña | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | |

> 📷 **[CAPTURA MED-06-ACC-02]**: Mensaje ERR-ACC-06
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:319`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de invitación después de 7 días

> 📷 **[CAPTURA MED-06-ACC-03]**: Mensaje ERR-ACC-07
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:324`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un enlace de invitación incompleto o ya usado

> 📷 **[CAPTURA MED-06-ACC-04]**: Mensaje ERR-ACC-08
> **Debe mostrar:** La pantalla con el mensaje "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña d
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/utils/validation.ts:25-31`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Crear una contraseña corta o sin símbolos

> 📷 **[CAPTURA MED-06-ACC-05]**: Mensaje ERR-ACC-09
> **Debe mostrar:** La pantalla con el mensaje "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/auth/ResetPassword.tsx:101`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir diferente la confirmación de la contraseña

**⚠️ Atención:**
- ⚠️ El enlace vence a los 7 días y solo sirve una vez. Si vence, pida que le reenvíen la invitación.
- La contraseña es personal e intransferible (Términos de uso, numeral 4).

**Ejemplo:** Si la invitación se envió el lunes 2 de febrero de 2026, el enlace sirve hasta el lunes 9 de febrero de 2026.

#### Actividad 2: Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.4.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para iniciar sesión, la cuenta debe estar en estado Activo. | Si puede ingresar, la cuenta está activa | Pedir la activación del usuario (Super Administrador o Administrador) | RN-ACC-01 |
| Para iniciar sesión, la entidad asignada al usuario debe estar activa. | Revise el estado o el dato en la pantalla antes de actuar | Revisar el estado de la entidad (Super Administrador o Administrador) | RN-ACC-02 |
| Para entrar, el código de verificación de 4 dígitos debe coincidir con el último enviado y tener menos de 1 hora. | Revise la hora del correo "SI-CIPRAT - Código de Verificación" | Usar el código del último correo o pedir uno nuevo con **Haz clic para reenviar** (El propio usuario) | RN-ACC-03 |

**Dónde:** Dirección de la plataforma › **Iniciar sesión** (`/signin`) › "Inicia sesión en tu cuenta".

**Qué ve:** Primera pantalla: "Sistema de Información de la Secretaría Técnica CIPRAT", "Inicia sesión en tu cuenta", campos **Correo electrónico** y **Contraseña**, enlace **¿Has olvidado tu contraseña?**, botón **Iniciar Sesión** y "¿Necesita soporte técnico?". Segunda pantalla: "Revisa tu correo electrónico", "Enviamos un enlace de verificación a {correo}", 4 casillas para el código, botón **Validar código** y "¿No recibiste el correo? **Haz clic para reenviar**".

**Campos a diligenciar: Iniciar sesión:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | |, | entidad.subdireccion.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" (mensajes en inglés de la pantalla) / "Credenciales inválidas" |
| 2 | Contraseña (`password`) | Sí | Texto oculto | La contraseña vigente | |, | (contraseña personal) | "Password is required" / "Credenciales inválidas" |
| 3 | Código de verificación (4 casillas) (`auth_code`) | Sí | Número (4 dígitos, uno por casilla) | Solo dígitos 0-9; vigente 1 hora | | Llega al correo después del paso 1 | 4821 | "Código de autenticación inválido" / "Código expirado" |

- Campos que llena el sistema: Ninguno.
- Campos que se bloquean: Ninguno.
- Archivos: No aplica.
- Guardar o enviar con: **Iniciar Sesión** y luego **Validar código**.

**Pasos:**

##### Paso 2.1: Abrir la pantalla de ingreso
**Objetivo del paso:** Llegar al formulario de inicio de sesión.
**Qué hacer:** Abra la dirección de SI-CIPRAT en Chrome, Firefox o Edge actualizados y haga clic en **Iniciar sesión** (o abra directamente `/signin`).
**Resultado esperado:** Aparece "Inicia sesión en tu cuenta".

##### Paso 2.2: Escribir correo y contraseña
**Objetivo del paso:** Identificarse ante el sistema.
**Qué hacer:** En **Correo electrónico** escriba su correo institucional (el mismo de la invitación). En **Contraseña** escriba su contraseña.
**Resultado esperado:** Los campos quedan diligenciados. Si están vacíos, la pantalla muestra "Email is required" o "Password is required".

##### Paso 2.3: Solicitar el código
**Objetivo del paso:** Validar credenciales y recibir el código de verificación.
**Qué hacer:** Haga clic en **Iniciar Sesión**.
**Resultado esperado:** El botón muestra "Iniciando sesión..." y aparece "Revisa tu correo electrónico". Llega el correo "SI-CIPRAT - Código de Verificación". Si las credenciales no son correctas: "Credenciales inválidas".

##### Paso 2.4: Escribir el código de 4 dígitos
**Objetivo del paso:** Comprobar que quien ingresa tiene acceso al correo.
**Qué hacer:** Abra el correo y escriba los 4 dígitos, uno en cada casilla (solo acepta números; puede pegarlos). Si no llegó, espere un minuto, revise el correo no deseado y haga clic en **Haz clic para reenviar**.
**Resultado esperado:** Las 4 casillas quedan llenas.

##### Paso 2.5: Validar el código
**Objetivo del paso:** Abrir la sesión.
**Qué hacer:** Haga clic en **Validar código**.
**Resultado esperado:** Entra a **Inicio** con el menú lateral de su rol. Si el código no coincide: "Código de autenticación inválido"; si pasó más de 1 hora: "Código expirado".

> 🎞️ **[GIF MED-06-ACC-06]**: Ingreso con código de verificación
> **Debe mostrar:** El ingreso completo: correo y contraseña, pantalla "Revisa tu correo electrónico", escritura del código y llegada a Inicio
> **Resaltar:** Botones Iniciar Sesión y Validar código; enlace Haz clic para reenviar
> **Pantalla / ruta:** `/signin` (`dashboard/src/components/auth/LoginPanel.tsx`, `VerificationCodePanel.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Usuario de prueba del rol
> **Imagen existente:** Refenrence/img/Screenshot 2026-08-11 at 6.07.49 PM.png: sirve para el primer cuadro (pantalla "Inicia sesión en tu cuenta", igual para todos los roles). Debe actualizarse: muestra un correo personal real; tomarla de nuevo con entidad.subdireccion.prueba@ejemplo.gov.co
> **Solo para GIF: Secuencia:** 1) Escribir correo y contraseña 2) Iniciar Sesión 3) Escribir el código 4) Validar código 5) Inicio · **Duración aproximada:** 20 segundos
> **Texto alternativo:** Animación del inicio de sesión con código de 4 dígitos

**Resultado de la actividad:** Sesión abierta con el rol el usuario de Entidad Territorial (Subdirección) y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Escribir mal el correo o la contraseña | "Credenciales inválidas" | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | No comparta ni anote la contraseña en lugares visibles. |
| Escribir mal el código de 4 dígitos | "Código de autenticación inválido" | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Use siempre el código del correo más reciente. |
| Usar un código después de 1 hora | "Código expirado" | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Ingrese el código apenas llegue. |
| Ingresar con una cuenta inactivada | "Cuenta no activa" | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | |
| Ingresar cuando la entidad asignada no está activa | "Tu organización está suspendida. Por favor contacta al administrador." | La entidad guardada en su usuario no está en estado Activa. | Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. | |
| No llega el correo con el código | No aparece mensaje: la pantalla "Revisa tu correo electrónico" queda esperando el código. | El correo puede estar en la carpeta de correo no deseado o tardar en llegar. | Revise la carpeta de correo no deseado; espere un minuto y use **Haz clic para reenviar**. | Agregue el remitente de SI-CIPRAT a sus contactos. |
| Se pierde la conexión a internet | "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo." | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Trabaje con conexión estable; los Términos de uso la exigen. |

> 📷 **[CAPTURA MED-06-ACC-07]**: Mensaje ERR-ACC-01
> **Debe mostrar:** La pantalla con el mensaje "Credenciales inválidas"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:132-141`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el correo o la contraseña

> 📷 **[CAPTURA MED-06-ACC-08]**: Mensaje ERR-ACC-02
> **Debe mostrar:** La pantalla con el mensaje "Código de autenticación inválido"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:81-84`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el código de 4 dígitos

> 📷 **[CAPTURA MED-06-ACC-09]**: Mensaje ERR-ACC-03
> **Debe mostrar:** La pantalla con el mensaje "Código expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:88-91,163`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar un código después de 1 hora

> 📷 **[CAPTURA MED-06-ACC-10]**: Mensaje ERR-ACC-04
> **Debe mostrar:** La pantalla con el mensaje "Cuenta no activa"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:144-148`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Ingresar con una cuenta inactivada

> 📷 **[CAPTURA MED-06-ACC-11]**: Mensaje ERR-ACC-05
> **Debe mostrar:** La pantalla con el mensaje "Tu organización está suspendida. Por favor contacta al administrador."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:150-156`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Ingresar cuando la entidad asignada no está activa

> 📷 **[CAPTURA MED-06-ACC-12]**: Mensaje ERR-GEN-06
> **Debe mostrar:** La pantalla con el mensaje "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:403`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Se pierde la conexión a internet

**⚠️ Atención:**
- El código vence 1 hora después de enviado; use siempre el del correo más reciente.
- Los mensajes de los campos vacíos de esta pantalla aparecen en inglés ("Email is required", "Please enter a valid email address", "Password is required").

**Ejemplo:** Si el código llega a las 8:05 a. m., sirve hasta las 9:05 a. m.

#### Actividad 3: Recuperar la contraseña

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La contraseña debe tener al menos 8 caracteres y al menos un carácter especial, y las dos casillas deben coincidir. | Los indicadores de la pantalla se marcan en verde | Escribir una contraseña que cumpla los indicadores de la pantalla (El propio usuario) | RN-ACC-05 |
| Al restablecer la contraseña, no se puede repetir la actual ni ninguna de las últimas 5. | Revise el estado o el dato en la pantalla antes de actuar | Elegir una contraseña nueva (El propio usuario) | RN-ACC-06 |
| El enlace para restablecer la contraseña vence 1 hora después de enviado. | Revise el estado o el dato en la pantalla antes de actuar | Solicitar un enlace nuevo (El propio usuario) | RN-ACC-07 |

**Dónde:** Pantalla de ingreso › **¿Has olvidado tu contraseña?** (`/forgot-password`) › correo "SI-CIPRAT - Restablecer Contraseña" › "Configurar nueva contraseña" (`/reset-password/:token`).

**Qué ve:** Primera pantalla: "¿Olvidaste tu contraseña?", "No te preocupes, te enviaremos las instrucciones para restablecerla.", campo **Correo electrónico** y botón **Restablecer contraseña**. Después: "Revisa tu correo electrónico: Hemos enviado un enlace para restablecer la contraseña a {correo}". En el enlace: "Configurar nueva contraseña", "Tu nueva contraseña debe ser diferente a las contraseñas usadas anteriormente.", campos **Nueva Contraseña** y **Confirmar Contraseña** y botón **Restablecer contraseña**.

**Campos a diligenciar: Solicitar el restablecimiento:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | |, | entidad.subdireccion.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" |

- Campos que llena el sistema:, 
- Campos que se bloquean:, 
- Archivos: No aplica.
- Guardar o enviar con: **Restablecer contraseña**.

**Campos a diligenciar: Configurar nueva contraseña:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Nueva Contraseña (`newPassword`) | Sí | Texto oculto | Mínimo 8 caracteres, un carácter especial, distinta de las 5 anteriores | |, | Nueva#2026 | "Debe tener al menos 8 caracteres" / "No puedes reutilizar ninguna de tus últimas 5 contraseñas" |
| 2 | Confirmar Contraseña (`confirmPassword`) | Sí | Texto oculto | Igual a Nueva Contraseña | | Nueva Contraseña | Nueva#2026 | "Las contraseñas ingresadas no son iguales…" |

- Campos que llena el sistema:, 
- Campos que se bloquean: El enlace vence en 1 hora.
- Archivos: No aplica.
- Guardar o enviar con: **Restablecer contraseña**.

**Pasos:**

##### Paso 3.1: Abrir la recuperación
**Objetivo del paso:** Iniciar el proceso de cambio de contraseña.
**Qué hacer:** En la pantalla de ingreso haga clic en **¿Has olvidado tu contraseña?**.
**Resultado esperado:** Aparece "¿Olvidaste tu contraseña?".

##### Paso 3.2: Escribir el correo
**Objetivo del paso:** Indicar a qué cuenta se enviará el enlace.
**Qué hacer:** En **Correo electrónico** escriba su correo institucional y haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Revisa tu correo electrónico" y llega el correo "SI-CIPRAT - Restablecer Contraseña".

##### Paso 3.3: Abrir el enlace del correo
**Objetivo del paso:** Llegar a la pantalla de nueva contraseña antes de que venza.
**Qué hacer:** Abra el correo y haga clic en el enlace dentro de la hora siguiente.
**Resultado esperado:** Aparece "Configurar nueva contraseña". Si pasó más de 1 hora, al guardar aparece "Token inválido o expirado".

##### Paso 3.4: Escribir y confirmar la nueva contraseña
**Objetivo del paso:** Definir una contraseña válida y distinta de las anteriores.
**Qué hacer:** Escriba en **Nueva Contraseña** al menos 8 caracteres con un carácter especial, distinta de sus últimas 5 contraseñas, y repítala en **Confirmar Contraseña**.
**Resultado esperado:** Los indicadores se marcan como cumplidos.

##### Paso 3.5: Guardar la contraseña
**Objetivo del paso:** Dejar activa la nueva contraseña.
**Qué hacer:** Haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Contraseña restablecida: Tu contraseña se ha restablecido correctamente. Haz clic abajo para iniciar sesión." con el botón **Iniciar Sesión**.

> 🎞️ **[GIF MED-06-ACC-13]**: Recuperación de la contraseña
> **Debe mostrar:** Solicitud del enlace, mensaje "Revisa tu correo electrónico", pantalla "Configurar nueva contraseña" y mensaje "Contraseña restablecida"
> **Resaltar:** Enlace ¿Has olvidado tu contraseña?; botón Restablecer contraseña
> **Pantalla / ruta:** `/forgot-password`, `/reset-password/:token` (`dashboard/src/pages/auth/ForgotPassword.tsx`, `ResetPassword.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Usuario de prueba
> **Solo para GIF: Secuencia:** 1) ¿Has olvidado tu contraseña? 2) Correo 3) Enlace 4) Nueva contraseña 5) Restablecer contraseña · **Duración aproximada:** 25 segundos
> **Texto alternativo:** Animación del restablecimiento de la contraseña

**Resultado de la actividad:** La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Crear una contraseña corta o sin símbolos | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña debe contener al menos un carácter especial") | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Revise los indicadores de la pantalla antes de enviar. |
| Escribir diferente la confirmación de la contraseña | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | |
| Usar una contraseña anterior al restablecerla | "No puedes reutilizar ninguna de tus últimas 5 contraseñas" o "La nueva contraseña no puede ser igual a tu contraseña actual" | El sistema guarda el historial de contraseñas. | Elija una contraseña distinta de las 5 anteriores. | |
| Abrir el enlace de restablecimiento después de 1 hora | "Token inválido o expirado" | El enlace de restablecimiento vence en 1 hora. | Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. | Use el enlace apenas llegue. |

> 📷 **[CAPTURA MED-06-ACC-14]**: Mensaje ERR-ACC-10
> **Debe mostrar:** La pantalla con el mensaje "No puedes reutilizar ninguna de tus últimas 5 contraseñas" o "La nueva contraseña no puede ser igual a tu contraseña actual"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:378-396`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar una contraseña anterior al restablecerla

> 📷 **[CAPTURA MED-06-ACC-15]**: Mensaje ERR-ACC-11
> **Debe mostrar:** La pantalla con el mensaje "Token inválido o expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:622-628`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de restablecimiento después de 1 hora

**⚠️ Atención:**
- La plataforma no tiene una pantalla para cambiar la contraseña conociendo la actual: para cambiarla, use siempre **¿Has olvidado tu contraseña?** (el servicio `password-change` existe, pero ninguna pantalla lo usa).

**Ejemplo:** Si solicita el enlace a las 3:00 p. m., debe usarlo antes de las 4:00 p. m.

#### Actividad 4: Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

**Cuándo se hace y requisitos previos:** Secuencia E0.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La sesión se cierra tras 60 minutos sin actividad y el acceso vence a los 720 minutos (12 horas). | Revise el estado o el dato en la pantalla antes de actuar | Volver a iniciar sesión (El propio usuario) | RN-ACC-08 |

**Dónde:** Menú lateral › parte inferior, nombre del usuario › **Cerrar sesión**.

**Qué ve:** Al pie del menú lateral, sus iniciales y su nombre; al hacer clic se despliegan **Ver Perfil** y **Cerrar sesión**.

**Pasos:**

##### Paso 4.1: Abrir el menú del usuario
**Objetivo del paso:** Encontrar la opción de salida.
**Qué hacer:** Haga clic en su nombre, al pie del menú lateral.
**Resultado esperado:** Se despliegan **Ver Perfil** y **Cerrar sesión**.

##### Paso 4.2: Cerrar la sesión
**Objetivo del paso:** Terminar la sesión cuando deja de trabajar.
**Qué hacer:** Haga clic en **Cerrar sesión**.
**Resultado esperado:** Vuelve a la pantalla de ingreso.

##### Paso 4.3: Reconocer el cierre automático
**Objetivo del paso:** Saber qué hacer cuando el sistema cierra la sesión.
**Qué hacer:** Si deja la plataforma sin uso 60 minutos, o la sesión vence a las 12 horas, lea el aviso y vuelva a iniciar sesión.
**Resultado esperado:** Aparece "Sesión cerrada por inactividad" o "Sesión expirada" y la pantalla de ingreso.

> 📷 **[CAPTURA MED-06-ACC-16]**: Menú del usuario
> **Debe mostrar:** El pie del menú lateral con el nombre del usuario y las opciones Ver Perfil y Cerrar sesión
> **Resaltar:** Opción Cerrar sesión
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:425-479`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Usuario de prueba
> **Texto alternativo:** Menú del usuario con la opción Cerrar sesión

**Resultado de la actividad:** La sesión termina; los datos no guardados de un formulario abierto se pierden.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Dejar la plataforma abierta sin usarla 60 minutos | "Sesión cerrada por inactividad: Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente." | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Guarde los formularios antes de dejar el equipo. |
| Trabajar con una sesión vencida | "Sesión expirada: Tu sesión ha expirado. Por favor, inicia sesión nuevamente." | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | |

> 📷 **[CAPTURA MED-06-ACC-17]**: Mensaje ERR-ACC-12
> **Debe mostrar:** La pantalla con el mensaje "Sesión cerrada por inactividad: Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useIdleTimeout.ts:6-22`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Dejar la plataforma abierta sin usarla 60 minutos

> 📷 **[CAPTURA MED-06-ACC-18]**: Mensaje ERR-ACC-13
> **Debe mostrar:** La pantalla con el mensaje "Sesión expirada: Tu sesión ha expirado. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useApiErrorHandler.ts:14`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Trabajar con una sesión vencida

**⚠️ Atención:**
- ⚠️ Guarde los formularios antes de dejar el equipo: el cierre por inactividad no guarda lo diligenciado.

**Ejemplo:** Si su última acción fue a las 10:00 a. m., a las 11:00 a. m. la sesión se cierra sola.

#### Actividad 5: Consultar los Términos de uso y contactar al soporte técnico

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

**Cuándo se hace y requisitos previos:** Secuencia E0. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Pie de página › **Términos de uso** (`/terminos-de-uso`); pantallas de acceso › **¿Necesita soporte técnico?**.

**Qué ve:** "Términos y condiciones de uso de la plataforma CIPRAT", "Actualizados el 17 de septiembre del 2025", con 14 numerales (definiciones, aceptación, condiciones técnicas, cuentas de usuario, protección de datos, entre otros) y el correo de soporte "siciprat@mininterior.gov.co: Lunes a Viernes 7:00 a.m. a 7:00 p.m.".

**Pasos:**

##### Paso 5.1: Abrir los Términos de uso
**Objetivo del paso:** Conocer sus obligaciones como usuario.
**Qué hacer:** Haga clic en **Términos de uso** al pie de la página.
**Resultado esperado:** Se abre la página de términos y condiciones.

##### Paso 5.2: Revisar las condiciones técnicas
**Objetivo del paso:** Saber qué necesita para usar la plataforma.
**Qué hacer:** Lea el numeral "4. Condiciones técnicas de acceso y uso".
**Resultado esperado:** Identifica: conexión estable, navegadores Chrome, Firefox o Edge actualizados y credenciales personales e intransferibles.

##### Paso 5.3: Escribir al soporte
**Objetivo del paso:** Pedir ayuda técnica.
**Qué hacer:** En las pantallas de acceso haga clic en **¿Necesita soporte técnico?**: se abre un correo a siciprat@mininterior.gov.co. Escriba qué hacía, la pantalla, la hora y adjunte una captura del mensaje.
**Resultado esperado:** Su programa de correo abre un mensaje nuevo dirigido al soporte.

> 📷 **[CAPTURA MED-06-ACC-19]**: Términos de uso
> **Debe mostrar:** La página de términos con el título y el numeral 4
> **Resaltar:** Numeral "4. Condiciones técnicas de acceso y uso" y el correo de soporte
> **Pantalla / ruta:** `/terminos-de-uso` (`dashboard/src/pages/TermsOfUse.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** No requiere datos
> **Texto alternativo:** Página de términos y condiciones de uso

**Resultado de la actividad:** Conoce las condiciones de uso y el canal de soporte.

**Escenarios de error y solución:**

No se identificaron escenarios de error en el código para esta actividad.

**⚠️ Atención:**
- El ingreso a la plataforma implica la aceptación de los Términos y Condiciones.

#### Actividad 6: Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

**Cuándo se hace y requisitos previos:** Secuencia E0.4.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › nombre del usuario › **Ver Perfil** (`/mi-perfil`).

**Qué ve:** Un encabezado con su nombre y tres secciones con campos deshabilitados: **Información General** "Información del funcionario" (Nombres, Apellidos, Cargo, Área (opcional), Correo electrónico); **Entidad y Acceso** "Información de organización y permisos" (Entidad Central, o "Sin organización", , Rol, Nivel de Acceso, Subdirección); **Asignaciones** "Departamentos asignados" (Departamentos).

**Pasos:**

##### Paso 6.1: Abrir Mi perfil
**Objetivo del paso:** Llegar a la pantalla de datos de la cuenta.
**Qué hacer:** Haga clic en su nombre al pie del menú lateral y luego en **Ver Perfil**.
**Resultado esperado:** Se abre Mi perfil con "Cargando perfil..." y luego sus datos.

##### Paso 6.2: Revisar Información General
**Objetivo del paso:** Confirmar los datos personales registrados.
**Qué hacer:** Lea Nombres, Apellidos, Cargo, Área y Correo electrónico.
**Resultado esperado:** Los datos coinciden con los suyos; los campos no se pueden editar.

##### Paso 6.3: Revisar Entidad y Acceso y Asignaciones
**Objetivo del paso:** Confirmar el alcance de datos.
**Qué hacer:** Verifique que el Rol corresponda a Entidad Territorial, que el **Nivel de Acceso** sea Subdirección y que **Entidad Central** y **Subdirección** sean las suyas.
**Resultado esperado:** Confirma que verá las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección.

> 📷 **[CAPTURA MED-06-ACC-20]**: Mi perfil
> **Debe mostrar:** Las tres secciones de Mi perfil de un usuario de prueba con rol Entidad Territorial (Subdirección)
> **Resaltar:** Campos Rol, Entidad Central, Nivel de Acceso, Subdirección y Departamentos
> **Pantalla / ruta:** `/mi-perfil` (`dashboard/src/pages/MyProfile.tsx:111-283`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Usuario de prueba de la ruta
> **Texto alternativo:** Pantalla Mi perfil con los datos de la cuenta

**Resultado de la actividad:** Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Encontrar en Mi perfil un rol, entidad, subdirección o departamentos que no corresponden | No aparece mensaje: los datos se muestran en campos deshabilitados. | El usuario fue configurado con otros datos; Mi perfil no permite editarlos. | Pida la corrección a quien administra los usuarios, indicando el dato correcto. | Revise Mi perfil después del primer ingreso. |

**⚠️ Atención:**
- Mi perfil es solo de consulta: el servicio para editar el propio perfil existe en el servidor, pero la pantalla tiene los campos deshabilitados.

### Módulo 02: Inicio

**Prerrequisitos:** Módulo 01 (sesión abierta).

**Definición del módulo:** Tablero de entrada de la plataforma. Muestra la última alerta activa, cinco indicadores (Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales, Alertas cerradas) con su tendencia de los últimos meses, el "Porcentaje de Avance Global", el ranking "Alertas por departamento" (Top 10), las "Alertas recientes" y el mapa de municipios con alertas. La misma página, sin sesión, es la vista pública de consulta ciudadana. Incluye el panel de accesibilidad (alto contraste y tamaño de letra).

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda leer los indicadores del Inicio; consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa; navegar con el menú lateral y usar el panel de accesibilidad; consultar el tablero público sin iniciar sesión.

**Contexto del módulo:** Se consulta en todas las fases del ciclo. Recibe datos de *Alertas tempranas* (estado, tipo, fecha de notificación, municipios) y de los planes de acción (actividades programadas y ejecutadas). Con sesión, los datos se filtran por el alcance del rol (departamentos o entidad); sin sesión, muestra la información nacional pública. Los borradores no cuentan en los indicadores. Para el usuario de Entidad Territorial (Subdirección): indicadores, ranking, alertas recientes y mapa calculados sobre las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`) (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores. En total, tiene 9 de las 9 funcionalidades del módulo.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Consultar los indicadores del Inicio (F-INI-01) | Muestra Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales y Alertas cerradas, con la tendencia "vs ultimo mes". | R | Módulo 02: Actividad 1 |
| Consultar la última alerta emitida (F-INI-02) | Muestra el banner "Se ha emitido la Alerta Temprana…" con la alerta activa más reciente y el botón **Ver Alerta**. | R | Módulo 02: Actividad 2 |
| Consultar "Alertas por departamento" (Top 10) (F-INI-03) | Ranking de los 10 departamentos con más alertas y su porcentaje del total. | R | Módulo 02: Actividad 2 |
| Consultar "Alertas recientes" (F-INI-04) | Lista las 9 alertas más recientes por fecha de la alerta. | R | Módulo 02: Actividad 2 |
| Consultar el "Porcentaje de Avance Global" (F-INI-05) | Promedio del porcentaje de cumplimiento de las alertas (no borradores) y total de actividades ejecutadas frente a programadas. | R | Módulo 02: Actividad 1 |
| Consultar el mapa de municipios con alertas (F-INI-06) | Mapa de Colombia con los municipios que tienen alertas (rojo: inminencia; azul: estructural) y tabla accesible con los mismos datos. | R | Módulo 02: Actividad 2 |
| Consultar el tablero público sin iniciar sesión (F-INI-07) | La página de inicio pública (`/`) muestra los mismos bloques con la información nacional, sin filtro de rol. | R | Módulo 02: Actividad 4 |
| Usar el panel de accesibilidad (F-INI-08) | Activa o desactiva el alto contraste y aumenta o reduce el tamaño de letra. | U | Módulo 02: Actividad 3 |
| Usar el menú lateral (F-INI-09) | Navega entre los módulos visibles para el rol; el menú se puede ocultar. | R | Módulo 02: Actividad 3 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 02: Actividad 1 |

#### Actividad 1: Leer los indicadores del Inicio

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Qué ve:** Título "Inicio" y el texto "Visualiza de manera centralizada el estado y la distribución de las alertas tempranas asociadas a sus departamentos". Cinco tarjetas con valor, tendencia "vs ultimo mes" y una línea de los últimos 4 meses:

| Tarjeta | Qué cuenta (alertas no borrador de su subdirección) |
|---|---|
| Total de alertas | Todas las alertas |
| Alertas activas | Alertas en estado Activa |
| Alertas de inminencia | Alertas de tipo Inminencia |
| Alertas estructurales | Alertas de tipo Estructural |
| Alertas cerradas | Alertas en estado Cerrada |

La tendencia es la diferencia entre lo notificado en el mes actual y en el mes anterior (por fecha de notificación). Debajo, el bloque **Porcentaje de Avance Global**: el promedio del % de cumplimiento de cada alerta (las alertas sin actividades cuentan como 0 %) y el total "{ejecutadas} de {programadas} actividades ejecutadas".

**Pasos:**

##### Paso 1.1: Abrir Inicio
**Objetivo del paso:** Ver el tablero de su alcance.
**Qué hacer:** Haga clic en **Inicio** en el menú lateral.
**Resultado esperado:** Aparecen las tarjetas, el avance global, el ranking y el mapa.

##### Paso 1.2: Leer las tarjetas y su tendencia
**Objetivo del paso:** Saber cuántas alertas hay y cómo cambió el último mes.
**Qué hacer:** Lea el valor grande de cada tarjeta y el número "vs ultimo mes".
**Resultado esperado:** Identifica, por ejemplo, que hay 2 alertas activas más que el mes anterior.

##### Paso 1.3: Interpretar el Porcentaje de Avance Global
**Objetivo del paso:** Entender el avance de los planes de acción.
**Qué hacer:** Lea el porcentaje y la línea "X de Y actividades ejecutadas". Recuerde que es un promedio por alerta y no la división del total.
**Resultado esperado:** Puede explicar por qué el porcentaje puede ser distinto de X/Y.

> 📷 **[CAPTURA MED-06-INI-01]**: Indicadores del Inicio
> **Debe mostrar:** Las cinco tarjetas y el bloque Porcentaje de Avance Global para un usuario Entidad Territorial (Subdirección)
> **Resaltar:** Valor y tendencia "vs ultimo mes" de una tarjeta; el porcentaje y la línea de actividades ejecutadas
> **Pantalla / ruta:** `/inicio` (`dashboard/src/pages/Home.tsx:340-433`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Ambiente de pruebas con alertas de varios estados
> **Texto alternativo:** Tarjetas de indicadores y porcentaje de avance global

**Resultado de la actividad:** Interpreta el estado general de las alertas de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | |
| El tablero aparece vacío o en cero | "No hay datos de departamentos" / "No hay alertas recientes" | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | |

> 📷 **[CAPTURA MED-06-INI-02]**: Mensaje ERR-INI-01
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar datos"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:416`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero no carga

> 📷 **[CAPTURA MED-06-INI-03]**: Mensaje ERR-INI-02
> **Debe mostrar:** La pantalla con el mensaje "No hay datos de departamentos" / "No hay alertas recientes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:212,263`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero aparece vacío o en cero

**⚠️ Atención:**
- Los borradores (alertas del Agente IA o recibidas de forma automática aún no publicadas) no cuentan en los indicadores.
- ⚠️ El "Porcentaje de Avance Global" promedia el porcentaje de cada alerta: no es igual a ejecutadas ÷ programadas del total.

**Ejemplo:** Con dos alertas: A con 10 programadas y 5 ejecutadas (50 %) y B con 2 programadas y 2 ejecutadas (100 %), el avance global es (50 + 100) ÷ 2 = 75 %, y la línea dice "7 de 12 actividades ejecutadas" (58,3 %). Una tercera alerta sin actividades (0 %) bajaría el promedio a 50 %.

#### Actividad 2: Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Inicio**.

**Qué ve:** El banner "Se ha emitido la Alerta Temprana {número}, con fecha de difusión: {fecha}. Consulta los detalles para conocer el alcance y las acciones recomendadas." con el botón **Ver Alerta**; el bloque "Alertas por departamento" (Top 10, con bandera, número de alertas y porcentaje); "Alertas recientes" (las 9 más recientes por fecha de la alerta) y el mapa de Colombia: municipios en rojo (Inminencia) y azul (Estructural), con la leyenda "Leyenda del mapa" y una tabla accesible (Municipio, Departamento, Cantidad de Alertas, Alertas de Inminencia, Alertas Estructurales).

**Pasos:**

##### Paso 2.1: Abrir la última alerta
**Objetivo del paso:** Conocer la alerta activa más reciente.
**Qué hacer:** Lea el banner superior y haga clic en **Ver Alerta**.
**Resultado esperado:** Se abre la alerta en *Alertas tempranas*.

##### Paso 2.2: Revisar el ranking de departamentos
**Objetivo del paso:** Saber dónde se concentran las alertas.
**Qué hacer:** Lea "Alertas por departamento" (Top 10).
**Resultado esperado:** Identifica los departamentos con más alertas y su porcentaje.

##### Paso 2.3: Revisar las alertas recientes
**Objetivo del paso:** Ver lo último registrado.
**Qué hacer:** Recorra "Alertas recientes".
**Resultado esperado:** Ve las últimas alertas por fecha de la alerta.

##### Paso 2.4: Usar el mapa
**Objetivo del paso:** Ubicar los municipios con alertas.
**Qué hacer:** Pase el cursor sobre un municipio coloreado; use la tabla accesible si prefiere leer los datos.
**Resultado esperado:** Aparece el nombre del municipio, el departamento y el número de alertas.

> 📷 **[CAPTURA MED-06-INI-04]**: Mapa y ranking del Inicio
> **Debe mostrar:** El mapa con municipios en rojo y azul, la leyenda y el bloque Alertas por departamento
> **Resaltar:** Leyenda del mapa; un municipio con su tooltip; Top 10
> **Pantalla / ruta:** `/inicio` (`dashboard/src/components/map/ColombiaMap.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Ambiente de pruebas con alertas de los dos tipos
> **Texto alternativo:** Mapa de Colombia con municipios con alertas y ranking por departamento

**Resultado de la actividad:** Ubica geográficamente las alertas de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | |
| El tablero aparece vacío o en cero | "No hay datos de departamentos" / "No hay alertas recientes" | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | |

**⚠️ Atención:**
- El listado "Alertas recientes" también incluye borradores (las tarjetas no): si ve un número de alerta que no está en las tarjetas, puede ser un borrador.

#### Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral; botón **Accesibilidad** (panel "Panel de accesibilidad").

**Qué ve:** El menú lateral con: Inicio, Alertas tempranas, Planes de acción, Oficios de consumación, Notificaciones, Ver Perfil. El botón **Ocultar** contrae el menú. El panel de accesibilidad tiene "Alternar alto contraste" (Activar/Desactivar alto contraste), "Reducir tamaño de letra" y "Aumentar tamaño de letra".

**Pasos:**

##### Paso 3.1: Recorrer el menú
**Objetivo del paso:** Conocer los módulos de su rol.
**Qué hacer:** Haga clic en cada opción del menú lateral.
**Resultado esperado:** Se abre cada pantalla; las rutas de navegación ("migas de pan") muestran dónde está.

##### Paso 3.2: Ocultar y mostrar el menú
**Objetivo del paso:** Ganar espacio en pantalla.
**Qué hacer:** Haga clic en **Ocultar** al pie del menú; para volver a verlo, use el botón de abrir menú.
**Resultado esperado:** El menú se contrae o se expande.

##### Paso 3.3: Ajustar la accesibilidad
**Objetivo del paso:** Leer mejor la información.
**Qué hacer:** Abra el panel de accesibilidad y use "Activar alto contraste", "Aumentar tamaño de letra" o "Reducir tamaño de letra".
**Resultado esperado:** La pantalla cambia de contraste o de tamaño de letra.

> 📷 **[CAPTURA MED-06-INI-05]**: Menú lateral del rol
> **Debe mostrar:** El menú lateral completo de un usuario Entidad Territorial (Subdirección)
> **Resaltar:** Las opciones visibles para el rol
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:16-91`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Usuario de prueba de la ruta
> **Texto alternativo:** Menú lateral con los módulos del rol

**Resultado de la actividad:** Navega con soltura por los módulos de su rol.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Escribir una dirección que no existe | "Página no encontrada: Lo sentimos, la página que buscas no existe o ha sido movida." › **Volver al inicio** | La ruta no existe. | Haga clic en **Volver al inicio** y navegue desde el menú. | Use el menú lateral. |
| Abrir un formulario de registro desde un celular | "Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio." | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Planee el registro desde un computador. |
| Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error) | "No tienes permisos para realizar esta acción." | El servidor rechaza la operación para el rol (403). | Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. | Use solo los botones habilitados para su rol. |
| Repetir una acción o actuar sobre un registro que cambió de estado | "Conflicto con el estado actual del recurso." | Otro usuario o una acción anterior cambió el estado del registro (409). | Actualice la página, revise el estado actual y repita la acción si todavía aplica. | Evite el doble clic y trabaje sobre la información recién cargada. |
| El servidor no está disponible | "El servidor no está disponible. Por favor, intenta más tarde." | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Espere unos minutos e intente de nuevo. | |
| Enviar datos con un formato que el servidor no acepta | "La solicitud no es válida. Verifica los datos e intenta de nuevo." o "Los datos enviados no son válidos." | Errores 400 o 422 de validación. | Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. | Lea la ayuda de cada campo. |

> 📷 **[CAPTURA MED-06-INI-06]**: Mensaje ERR-GEN-12
> **Debe mostrar:** La pantalla con el mensaje "Página no encontrada: Lo sentimos, la página que buscas no existe o ha sido movida." › **Volver al inicio**
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/NotFound.tsx:23-45`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir una dirección que no existe

> 📷 **[CAPTURA MED-06-INI-07]**: Mensaje ERR-GEN-11
> **Debe mostrar:** La pantalla con el mensaje "Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:550-551`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un formulario de registro desde un celular

> 📷 **[CAPTURA MED-06-INI-08]**: Mensaje ERR-GEN-01
> **Debe mostrar:** La pantalla con el mensaje "No tienes permisos para realizar esta acción."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:69-70`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error)

> 📷 **[CAPTURA MED-06-INI-09]**: Mensaje ERR-GEN-03
> **Debe mostrar:** La pantalla con el mensaje "Conflicto con el estado actual del recurso."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:73-74`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Repetir una acción o actuar sobre un registro que cambió de estado

> 📷 **[CAPTURA MED-06-INI-10]**: Mensaje ERR-GEN-05
> **Debe mostrar:** La pantalla con el mensaje "El servidor no está disponible. Por favor, intenta más tarde."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:79-82`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor no está disponible

> 📷 **[CAPTURA MED-06-INI-11]**: Mensaje ERR-GEN-13
> **Debe mostrar:** La pantalla con el mensaje "La solicitud no es válida. Verifica los datos e intenta de nuevo." o "Los datos enviados no son válidos."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:65-76`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Enviar datos con un formato que el servidor no acepta

**⚠️ Atención:**
- Los formularios de registro no se abren en pantallas de celular ("Disponible en escritorio").

#### Actividad 4: Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Dirección principal de SI-CIPRAT (`/`), sin iniciar sesión.

**Qué ve:** Los mismos bloques del Inicio (banner, tarjetas, avance global, ranking, alertas recientes y mapa) con la información nacional y el botón **Iniciar sesión**.

**Pasos:**

##### Paso 4.1: Abrir la vista pública
**Objetivo del paso:** Ver lo que ve la ciudadanía.
**Qué hacer:** Abra la dirección de la plataforma sin iniciar sesión (o en una ventana privada).
**Resultado esperado:** Aparece el tablero público con el botón **Iniciar sesión**.

##### Paso 4.2: Comparar con su vista
**Objetivo del paso:** Entender la diferencia de alcance.
**Qué hacer:** Compare los totales con los de su Inicio con sesión, que se calculan sobre su subdirección.
**Resultado esperado:** Los totales públicos son nacionales y pueden ser mayores que los de su vista.

> 📷 **[CAPTURA MED-06-INI-12]**: Tablero público
> **Debe mostrar:** La página pública sin sesión con el botón Iniciar sesión
> **Resaltar:** Botón Iniciar sesión
> **Pantalla / ruta:** `/` (`dashboard/src/App.tsx:40`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Ambiente de pruebas
> **Texto alternativo:** Tablero público de alertas tempranas

**Resultado de la actividad:** Sabe qué información es pública y cuál depende de su sesión.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | |

**⚠️ Atención:**
- La vista pública no muestra recomendaciones, planes ni archivos: solo los bloques del tablero.

### Módulo 03: Alertas tempranas

**Prerrequisitos:** Módulos 01 y 02.

**Definición del módulo:** Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. Permite listar, buscar, filtrar y descargar las alertas; ver su detalle, su PDF y su historial de actividades; reportar una alerta nueva en un formulario de 6 pasos; editarla, publicarla si está en borrador, subsumir otras alertas, eliminarla y cerrar alertas.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda consultar, buscar y filtrar alertas tempranas; ver el detalle de una alerta y descargar su PDF; consultar el historial de actividades de una alerta; descargar el listado de alertas en CSV; ir a las recomendaciones de una alerta.

**Contexto del módulo:** Inicia el ciclo (E1) y lo termina (E6.3 cierre). Recibe alertas de forma automática o del Agente IA, o las registra el Ministerio. Entrega la alerta a *Recomendaciones* (E2), cuya existencia habilita el plan de acción, y a *Inicio* para los indicadores. Todos los roles consultan las alertas de su alcance; el registro y la edición son del Super Administrador y el Administrador; la eliminación, el cierre y la carga de archivos, solo del Super Administrador. Para el usuario de Entidad Territorial (Subdirección): ve las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`). En total, tiene 7 de las 16 funcionalidades del módulo; no tiene: reportar una alerta temprana, adjuntar el PDF de la alerta y el Adjunto, editar una alerta, cambiar el número de una alerta manual, publicar una alerta en borrador, subsumir otras alertas, eliminar una alerta, reemplazar o eliminar los archivos de la alerta, cerrar alertas.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar alertas (F-ALE-01) | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Módulo 03: Actividad 1 |
| Buscar alertas (F-ALE-02) | Busca por número o texto de la alerta. | R | Módulo 03: Actividad 1 |
| Filtrar alertas (F-ALE-03) | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Módulo 03: Actividad 1 |
| Ver el detalle de una alerta (F-ALE-04) | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Módulo 03: Actividad 2 |
| Descargar el PDF de la alerta (F-ALE-05) | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Módulo 03: Actividad 2 |
| Consultar el historial de actividades de la alerta (F-ALE-06) | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Módulo 03: Actividad 3 |
| Descargar el listado de alertas (CSV) (F-ALE-07) | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Módulo 03: Actividad 4 |
| Listar las recomendaciones de una alerta (F-REC-01, módulo Recomendaciones) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 03: Actividad 5 |

#### Actividad 1: Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Qué ve:** "Alertas Tempranas: Gestiona y monitorea la comunicación de las alertas tempranas." con las tarjetas **Total de alertas**, **Alertas activas** y **Alertas cerradas**; la sección "Alertas" con el contador y los botones **Descargar**, **Cerrar alertas** y **Reportar alerta** (los dos últimos deshabilitados para su rol); las pestañas **Todas**, **Inminencia** y **Estructurales**; el buscador "Buscar por nombre" y **Filtros**. Ve las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección, incluidas las alertas en Borrador de ese alcance.

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

##### Paso 1.1: Abrir Alertas tempranas
**Objetivo del paso:** Ver las alertas de su alcance.
**Qué hacer:** Haga clic en **Alertas tempranas** en el menú lateral.
**Resultado esperado:** Aparecen "Cargando alertas..." y luego las tarjetas y la tabla.

##### Paso 1.2: Leer las tarjetas
**Objetivo del paso:** Conocer los totales.
**Qué hacer:** Lea Total de alertas, Alertas activas y Alertas cerradas.
**Resultado esperado:** Conoce cuántas alertas hay en cada estado.

##### Paso 1.3: Cambiar de pestaña
**Objetivo del paso:** Separar por tipo.
**Qué hacer:** Haga clic en **Inminencia** o **Estructurales**; **Todas** quita el filtro.
**Resultado esperado:** La tabla muestra solo ese tipo.

##### Paso 1.4: Buscar una alerta
**Objetivo del paso:** Ir directo a una alerta.
**Qué hacer:** Escriba el número (por ejemplo "AT-013") o una palabra del tema en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; sin coincidencias: "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo."

##### Paso 1.5: Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** Haga clic en **Filtros**, elija Tipo, Estado, Etiqueta y las listas del conflicto, y haga clic en **Aplicar filtros**. Para quitar, **Limpiar filtros**.
**Resultado esperado:** El botón Filtros muestra cuántos filtros están activos y la tabla se actualiza.

##### Paso 1.6: Abrir el menú de acciones
**Objetivo del paso:** Saber qué puede hacer con cada alerta.
**Qué hacer:** Haga clic en ⋯ al final de la fila.
**Resultado esperado:** Aparecen Detalle, Recomendaciones e Historial de actividades; Editar y Eliminar están deshabilitados ("No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas").

> 📷 **[CAPTURA MED-06-ALE-01]**: Listado de alertas
> **Debe mostrar:** La pantalla Alertas Tempranas de un usuario Entidad Territorial (Subdirección) con las tarjetas, las pestañas y la tabla
> **Resaltar:** Pestañas Todas/Inminencia/Estructurales; Buscar por nombre; Filtros; menú ⋯
> **Pantalla / ruta:** `/alertas-tempranas` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** AT-013-2025 o alertas Mock
> **Texto alternativo:** Listado de alertas tempranas con filtros

**Resultado de la actividad:** Ubica la alerta y sus datos principales.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de registrar, editar, eliminar o cerrar alertas | Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No tienes permisos para cerrar alertas" | Su rol solo consulta alertas. | Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). | |
| No encontrar una alerta que esperaba ver | No aparece mensaje o aparece "No se encontraron resultados". | La alerta está fuera de su alcance (departamentos o entidad), es un borrador o no existe. | Revise su alcance en **Ver Perfil**; si la alerta le corresponde, pida el ajuste de su usuario o de la recomendación. | |
| El listado de alertas no carga | "Error al cargar alertas: No se pudieron cargar las alertas. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página e intente de nuevo. | |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-06-ALE-02]**: Mensaje ERR-ALE-17
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72,181-238`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de registrar, editar, eliminar o cerrar alertas

> 📷 **[CAPTURA MED-06-ALE-03]**: Mensaje ERR-ALE-19
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar alertas: No se pudieron cargar las alertas. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:212-215`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El listado de alertas no carga

> 📷 **[CAPTURA MED-06-ALE-04]**: Mensaje ERR-GEN-07
> **Debe mostrar:** La pantalla con el mensaje "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/SearchEmptyState.tsx:9-10`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar o filtrar sin coincidencias

**⚠️ Atención:**
- La lista también muestra alertas en estado Borrador (creadas por el Agente IA o recibidas de forma automática) de su alcance: todavía no son alertas activas.

**Ejemplo:** Busque "AT-013" y verá la alerta AT-013-2025 [DATO REAL AT-013-25], tipo Estructural, etiqueta Regional según la línea base (los scripts del repositorio la cargan como "Nacional": verifique cuál muestra su ambiente), notificada el 07/10/2025.

#### Actividad 2: Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Detalle**.

**Qué ve:** Una ventana con el número de la alerta, su tipo, la etiqueta "Borrador" si aplica y "Fecha: DD/MM/AAAA". Pestañas: **Información general** (Ejecutado / Programado, Plan de acción, "PDF de la alerta" y Descripción), **Lugar de advertencia** (tabla de municipios: Municipio / Departamento, Cod DANE, CAT, PNIS, PDET, Zona Fut.), **Conflicto** (Economías ilegales, Grupos armados ilegales), **Conductas vulneratorias e infracciones al D.I.H.**, **Población afectada** y **Alertas subsumidas** ("Alertas que subsume", "Subsumida por" o "No hay alertas subsumidas"). Botones **Cerrar** y **Editar**.

**Pasos:**

##### Paso 2.1: Abrir el detalle
**Objetivo del paso:** Ver la ficha completa.
**Qué hacer:** En la fila, haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ficha en la pestaña Información general.

##### Paso 2.2: Revisar Información general
**Objetivo del paso:** Conocer el avance y el tema.
**Qué hacer:** Lea Ejecutado / Programado, el estado del Plan de acción y la Descripción.
**Resultado esperado:** Conoce el avance y el estado del plan.

##### Paso 2.3: Descargar el PDF
**Objetivo del paso:** Consultar el documento oficial.
**Qué hacer:** Haga clic en el archivo de "PDF de la alerta".
**Resultado esperado:** Se descarga el PDF. Si no hay archivo, la alerta no tiene PDF cargado.

##### Paso 2.4: Recorrer las demás pestañas
**Objetivo del paso:** Conocer el territorio, el conflicto y la población.
**Qué hacer:** Abra Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas.
**Resultado esperado:** Ve los municipios (con CAT, PNIS, PDET y Zona Fut.), los grupos armados, las conductas, las poblaciones y las subsunciones.

##### Paso 2.5: Cerrar la ficha
**Objetivo del paso:** Volver al listado.
**Qué hacer:** Haga clic en **Cerrar**.
**Resultado esperado:** Vuelve a la tabla de alertas.

> 📷 **[CAPTURA MED-06-ALE-05]**: Detalle de la alerta
> **Debe mostrar:** La ficha de una alerta en la pestaña Lugar de advertencia
> **Resaltar:** Pestañas; columnas CAT, PNIS, PDET y Zona Fut.; "PDF de la alerta"
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Ficha de detalle de una alerta temprana

**Resultado de la actividad:** Conoce la alerta completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

> 📷 **[CAPTURA MED-06-ALE-06]**: Mensaje ERR-GEN-02
> **Debe mostrar:** La pantalla con el mensaje "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:71-72`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un registro que ya no existe o fue eliminado

**⚠️ Atención:**
- El botón **Editar** aparece deshabilitado con "No tienes permisos para editar alertas".

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25], la pestaña Lugar de advertencia lista 1.122 municipios, por ejemplo GUAVIARE › Miraflores (95200).

#### Actividad 3: Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Historial de actividades**.

**Qué ve:** La ventana "Historial de actividades alerta {número}: Conoce el historial de acciones realizadas sobre la alerta." con la línea de tiempo: usuario, acción, detalle y fecha; algunos eventos muestran "Consecutivo:", "Fecha notificacion:" y "Descargar archivo". Sin eventos: "No hay actividades registradas".

**Pasos:**

##### Paso 3.1: Abrir el historial
**Objetivo del paso:** Ver la trazabilidad.
**Qué hacer:** Haga clic en ⋯ › **Historial de actividades**.
**Resultado esperado:** Se abre la línea de tiempo de la alerta.

##### Paso 3.2: Leer los eventos
**Objetivo del paso:** Reconstruir lo ocurrido.
**Qué hacer:** Recorra los eventos y use **Mostrar 10 mas** para ver los anteriores.
**Resultado esperado:** Identifica, por ejemplo, cuándo se confirmó el plan y quién lo hizo.

##### Paso 3.3: Descargar un archivo del evento
**Objetivo del paso:** Ver el soporte de un cierre o informe.
**Qué hacer:** Si el evento tiene "Descargar archivo", haga clic.
**Resultado esperado:** Se descarga el archivo asociado.

> 📷 **[CAPTURA MED-06-ALE-07]**: Historial de actividades
> **Debe mostrar:** La línea de tiempo con la confirmación del plan
> **Resaltar:** Evento de confirmación con usuario y fecha
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/ActivityHistoryModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alerta Mock con varias acciones
> **Texto alternativo:** Historial de actividades de una alerta

**Resultado de la actividad:** Conoce la trazabilidad de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El servidor falla al procesar la solicitud | "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio: La plataforma presentó un inconveniente al procesar tu solicitud. Estamos trabajando para solucionarlo. Por favor, intenta nuevamente en unos minutos." | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | |

> 📷 **[CAPTURA MED-06-ALE-08]**: Mensaje ERR-GEN-04
> **Debe mostrar:** La pantalla con el mensaje "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio: La plataforma presentó un inconveniente al procesar tu solicitud. Estamos 
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:77-78`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor falla al procesar la solicitud

**⚠️ Atención:**
- El historial guarda eventos, no versiones completas: no permite ver cómo estaba una actividad antes de editarla.

#### Actividad 4: Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › **Descargar**.

**Qué ve:** El botón **Descargar** (muestra "Descargando..."). El archivo CSV (UTF-8) trae: Número de Alerta, Fecha de Alerta, Fecha de Notificación, Tipo, Estado, Descripción, Etiqueta, Cantidad de Recomendaciones, Economías Ilegales, Grupos Armados, Conductas Vulneratorias, Población Afectada y Fecha de Creación.

**Pasos:**

##### Paso 4.1: Aplicar los filtros que necesita
**Objetivo del paso:** Descargar solo lo útil.
**Qué hacer:** Use la pestaña, el buscador y **Filtros**.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 4.2: Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; ábralo en Excel.

> 📷 **[CAPTURA MED-06-ALE-09]**: Botón Descargar
> **Debe mostrar:** La cabecera de la tabla con el botón Descargar
> **Resaltar:** Botón Descargar
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:165-221`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alertas Mock
> **Texto alternativo:** Botón para descargar el listado de alertas

**Resultado de la actividad:** Tiene el listado en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

> 📷 **[CAPTURA MED-06-ALE-10]**: Mensaje ERR-GEN-10
> **Debe mostrar:** La pantalla con el mensaje "Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:87-88`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: La descarga del CSV falla

**⚠️ Atención:**
- Los textos salen completos (el sistema no los corta a 4.000 caracteres).
- Las fechas salen en formato AAAA-MM-DD.

#### Actividad 5: Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Qué ve:** La pantalla de recomendaciones de la alerta con el enlace "Volver a Alertas Tempranas".

**Pasos:**

##### Paso 5.1: Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 5.2: Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

> 📷 **[CAPTURA MED-06-ALE-11]**: Menú ⋯ de la alerta
> **Debe mostrar:** El menú de acciones de una fila con la opción Recomendaciones
> **Resaltar:** Opción Recomendaciones
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:469-507`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alerta Mock
> **Texto alternativo:** Menú de acciones de una alerta

**Resultado de la actividad:** Llega a las recomendaciones de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | |

> 📷 **[CAPTURA MED-06-ALE-12]**: Mensaje ERR-REC-08
> **Debe mostrar:** La pantalla con el mensaje "La alerta solicitada no existe o ha sido eliminada."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:168`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir las recomendaciones de una alerta eliminada

**⚠️ Atención:**
- Solo verá las recomendaciones cuya Entidad Principal es su subdirección.

### Módulo 04: Recomendaciones

**Prerrequisitos:** Módulo 03 (la alerta debe existir y estar Activa).

**Definición del módulo:** Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). Permite listarlas, buscarlas, filtrarlas, ver su detalle y descargarlas; al Super Administrador y al Administrador, crearlas en 2 pasos (eje temático y descripción; entidades principales y asociadas) y editarlas; al Super Administrador, eliminarlas. El sistema asigna el código RC y notifica por correo a las entidades.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda consultar, buscar y filtrar las recomendaciones de una alerta; ver el detalle de una recomendación; descargar las recomendaciones de una alerta en CSV.

**Contexto del módulo:** Corresponde a la fase E2. Requiere una alerta registrada (E1). Entrega las recomendaciones a *Planes de acción* (E3), donde la Entidad Territorial les agrega actividades, y dispara el correo "Nueva Recomendacion Asignada". Mientras el plan de acción no esté confirmado, las recomendaciones se pueden editar o eliminar. Para el usuario de Entidad Territorial (Subdirección): dentro de cada alerta solo ve las recomendaciones cuya Entidad Principal es su subdirección; las de otras entidades no aparecen (`main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:144-152`). En total, tiene 5 de las 8 funcionalidades del módulo; no tiene: agregar una recomendación, editar una recomendación, eliminar una recomendación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar las recomendaciones de una alerta (F-REC-01) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 03: Actividad 5; Módulo 04: Actividad 1 |
| Buscar y filtrar recomendaciones (F-REC-02) | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Módulo 04: Actividad 1 |
| Ver el detalle de una recomendación (F-REC-03) | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Módulo 04: Actividad 2 |
| Descargar las recomendaciones (CSV) (F-REC-04) | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Módulo 04: Actividad 3 |
| Asignar el código RC (F-REC-08) | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Módulo 04: Actividad 1 |

#### Actividad 1: Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

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

Solo aparecen las recomendaciones cuya Entidad Principal es su subdirección.

**Pasos:**

##### Paso 1.1: Abrir las recomendaciones
**Objetivo del paso:** Ver la lista.
**Qué hacer:** Desde la alerta, ⋯ › **Recomendaciones**.
**Resultado esperado:** Aparece "Cargando recomendaciones..." y luego la tabla.

##### Paso 1.2: Buscar
**Objetivo del paso:** Encontrar una recomendación.
**Qué hacer:** Escriba el código (por ejemplo "RC-001") o una palabra en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra.

##### Paso 1.3: Filtrar
**Objetivo del paso:** Ver por entidad, eje o modo.
**Qué hacer:** Haga clic en **Filtros**, elija Entidad Principal, Eje Temático o Modo de Creación y **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo lo filtrado.

##### Paso 1.4: Leer el avance
**Objetivo del paso:** Saber cómo va cada recomendación.
**Qué hacer:** Lea Actividades (Aprobadas / Total) y Ejecución.
**Resultado esperado:** Identifica las recomendaciones sin actividades o con bajo cumplimiento.

> 📷 **[CAPTURA MED-06-REC-01]**: Recomendaciones de una alerta
> **Debe mostrar:** La tabla de recomendaciones vista por un usuario Entidad Territorial (Subdirección)
> **Resaltar:** Columnas Actividades y Ejecución; Filtros
> **Pantalla / ruta:** `/alertas-tempranas/:id/recomendaciones` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Listado de recomendaciones de una alerta

**Resultado de la actividad:** Conoce las recomendaciones de la alerta y su avance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de agregar, editar o eliminar recomendaciones | Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para eliminar recomendaciones" | Solo el Super Administrador y el Administrador las registran. | Pida el cambio a la Secretaría Técnica. | |
| Las recomendaciones no cargan | "Error al cargar las recomendaciones. Por favor, intente nuevamente." | Falla del servicio. | Recargue la página. | |
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | |
| No ver todas las recomendaciones de una alerta | No aparece mensaje: el listado muestra solo algunas recomendaciones. | Dentro de cada alerta solo ve las recomendaciones de su entidad o subdirección. | No requiere acción; si una recomendación de su entidad no aparece, pida que se revise su Entidad Principal. | |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-06-REC-02]**: Mensaje ERR-REC-06
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para elimi
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de agregar, editar o eliminar recomendaciones

> 📷 **[CAPTURA MED-06-REC-03]**: Mensaje ERR-REC-07
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar las recomendaciones. Por favor, intente nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:238`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Las recomendaciones no cargan

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25] hay 41 recomendaciones, de RC-001-2025-013 a RC-041-2025-013; por ejemplo RC-001-2025-013, eje "Coordinación de Respuesta Rápida", Entidad Principal "MinInterior - CIPRAT".

#### Actividad 2: Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Recomendaciones › fila › ⋯ › **Detalle**.

**Qué ve:** La ventana con "Última actualización", **Información general** (Eje temático, Entidad principal), **Descripción**, **Entidades asociadas** y la **Ejecución**; botones **Cerrar** y **Editar**.

**Pasos:**

##### Paso 2.1: Abrir el detalle
**Objetivo del paso:** Ver la recomendación completa.
**Qué hacer:** Haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ventana.

##### Paso 2.2: Leer las entidades
**Objetivo del paso:** Saber quién responde y quién apoya.
**Qué hacer:** Lea la Entidad principal y las Entidades asociadas.
**Resultado esperado:** Identifica a la entidad responsable del plan y a las que apoyan.

> 📷 **[CAPTURA MED-06-REC-04]**: Detalle de recomendación
> **Debe mostrar:** La ventana con Entidad principal y Entidades asociadas
> **Resaltar:** Entidades asociadas
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Recomendación Mock
> **Texto alternativo:** Detalle de una recomendación

**Resultado de la actividad:** Conoce la recomendación completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**⚠️ Atención:**
- El botón **Editar** aparece deshabilitado con "No tienes permisos para editar recomendaciones".

**Ejemplo:** RC-011-2025-013 [DATO REAL AT-013-25]: su descripción empieza "Recomendación No. 12 …", es decir, el código RC no coincide con el número de la recomendación en el documento (hallazgo H3).

#### Actividad 3: Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda descargar las recomendaciones visibles en un archivo CSV.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Recomendaciones › **Descargar**.

**Qué ve:** El CSV trae: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. No incluye las entidades asociadas ni el estado.

**Pasos:**

##### Paso 3.1: Filtrar
**Objetivo del paso:** Descargar lo necesario.
**Qué hacer:** Aplique búsqueda y filtros.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 3.2: Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; si falla: "Error al descargar el archivo CSV. Por favor, intente nuevamente."

> 📷 **[CAPTURA MED-06-REC-05]**: CSV de recomendaciones
> **Debe mostrar:** El archivo CSV abierto en Excel
> **Resaltar:** Columnas
> **Pantalla / ruta:** Recomendaciones › Descargar (`main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alerta Mock
> **Texto alternativo:** Archivo CSV de recomendaciones

**Resultado de la actividad:** Tiene las recomendaciones en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

**⚠️ Atención:**
- El texto de la descripción sale completo (sin corte a 4.000 caracteres).

### Módulo 05: Planes de acción

**Prerrequisitos:** Módulo 04; que la Secretaría Técnica haya registrado recomendaciones con su subdirección como Entidad Principal (RN-REC-01).

**Definición del módulo:** Módulo donde se formula y se ejecuta el plan de acción. Tiene tres niveles: alertas con su plan (Ejecutado vs programado, estado del plan e informes), recomendaciones de la alerta y actividades de cada recomendación. Permite a las entidades agregar, editar y eliminar actividades, comentar y reportar o editar informes de ejecución con su PDF; a todos los roles con acceso, consultar, filtrar y descargar la información. Tiene además las pestañas globales Recomendaciones y Actividades y el acceso al Informe de recomendaciones.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda consultar y filtrar los planes de acción por alerta; recorrer las recomendaciones del plan de una alerta; consultar las pestañas globales de Recomendaciones y Actividades; consultar las actividades de una recomendación y su detalle; agregar una actividad al plan de acción; agregar una actividad a un plan ya confirmado; editar o eliminar una actividad pendiente; comentar una actividad y atender los comentarios de la revisión; reportar un informe de ejecución; editar un informe de ejecución pendiente; consultar los informes de ejecución de una actividad y descargar su PDF.

**Contexto del módulo:** Corresponde a la formulación (E3) y al reporte de ejecución (E5.1-E5.2). Recibe las recomendaciones de E2 y entrega las actividades a *Seguimiento*, donde se revisan y aprueban (E4). Los informes solo se habilitan cuando el plan está confirmado (E4.3). Lo usan la Entidad Territorial (Central y Subdirección) y el Super Administrador para registrar, y el Administrador, Consulta Global y Consulta Entidad para consultar. Monitor, Líder de Macrozona y Consulta Departamentos trabajan esta información desde *Seguimiento*. Para el usuario de Entidad Territorial (Subdirección): ve los planes, recomendaciones y actividades de las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`). En total, tiene 18 de las 20 funcionalidades del módulo; no tiene: eliminar un comentario propio, eliminar un informe de ejecución.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar las alertas con plan de acción (F-PLA-01) | Pestaña **Alertas**: por alerta muestra Ejecutado vs programado, % de cumplimiento, estado del Plan de acción y estado del Informe. | R | Módulo 05: Actividad 1 |
| Buscar y filtrar planes de acción (F-PLA-02) | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento (0-30, 31-50, 51-80, 81-100). | R | Módulo 05: Actividad 1 |
| Ver el detalle y el historial del plan de una alerta (F-PLA-03) | Abre la ficha con "Información de alerta" e "Historial Plan de acción". | R | Módulo 05: Actividad 1 |
| Descargar el listado de planes (CSV) (F-PLA-04) | Descarga Número de Alerta, Cumplimiento (%) y Plan de Acción de las alertas visibles. | Archivo | Módulo 05: Actividad 1 |
| Ver las recomendaciones del plan de una alerta (F-PLA-05) | Desde **Ir al plan de acción**, lista las recomendaciones con Actividades (Aprobadas / Total) y Ejecución; **Ver Actividades** abre las actividades. | R | Módulo 05: Actividad 2 |
| Consultar la pestaña global de Recomendaciones (F-PLA-06) | Pestaña **Recomendaciones** con todas las recomendaciones del alcance, filtros (alerta, eje, entidad) y descarga. | R | Módulo 05: Actividad 3 |
| Consultar la pestaña global de Actividades (F-PLA-07) | Pestaña **Actividades** con todas las actividades del alcance: Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe, Próximo Informe; filtros y descarga. | R | Módulo 05: Actividad 3 |
| Listar las actividades de una recomendación (F-PLA-08) | Muestra Actividad, Objetivo, Descripción, Número Actividades, Ejecución (Ejecutadas / Programadas), Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; busca por objetivo y filtra por Estado, Instrumento de Planeación y Recursos. | R | Módulo 05: Actividad 4 |
| Ver el detalle de una actividad (F-PLA-09) | Abre "Detalle de Actividad": Recomendación, campos de la actividad, Estado Informe, Ejecución y Próximo Informe. | R | Módulo 05: Actividad 4 |
| Descargar las actividades (CSV) (F-PLA-10) | Descarga Número de Alerta, Código de Recomendación, Objetivo, Descripción, Número de Actividades, Plazo, Instrumento, Recursos, Estado, Observaciones y fechas. | Archivo | Módulo 05: Actividad 3; Módulo 05: Actividad 4 |
| Agregar una actividad (F-PLA-11) | Registra en 2 pasos el Objetivo y la información de la actividad (Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos, Observaciones). | C | Módulo 05: Actividad 5 |
| Agregar una actividad a un plan confirmado (F-PLA-12) | Si el plan ya está confirmado, el sistema advierte "Agregar actividad a plan confirmado" y, al continuar, desconfirma el plan. | Estado | Módulo 05: Actividad 6 |
| Editar una actividad (F-PLA-13) | Modifica los campos de una actividad pendiente de aprobación. | U | Módulo 05: Actividad 7 |
| Eliminar una actividad (F-PLA-14) | Elimina una actividad pendiente de aprobación. | D | Módulo 05: Actividad 7 |
| Ver y escribir comentarios de una actividad (F-PLA-15) | Abre la conversación de la actividad y agrega comentarios (hasta 2.000 caracteres). | C | Módulo 05: Actividad 8 |
| Reportar un informe de ejecución (F-PLA-17) | Registra lo ejecutado en el ciclo: actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades y el PDF de soporte. | C | Módulo 05: Actividad 9 |
| Editar un informe de ejecución pendiente (F-PLA-18) | Corrige el informe y su PDF mientras no esté aprobado. | U | Módulo 05: Actividad 10 |
| Consultar los informes de ejecución y descargar su PDF (F-PLA-19) | En el detalle de la recomendación (pestaña de actividades) muestra "Informes de ejecución" con todos sus campos y el archivo "Informe.pdf". | Archivo | Módulo 05: Actividad 11 |
| Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01, módulo Tareas programadas) | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Módulo 05: Actividad 4 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 05: Actividad 4 |
| Calcular el próximo informe al aprobar un informe (F-TAR-04, módulo Tareas programadas) | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Módulo 05: Actividad 4 |

#### Actividad 1: Consultar y filtrar los planes de acción por alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Planes de acción** (`/planes-de-accion`) › pestaña **Alertas**.

**Qué ve:** "Planes de Acción: Gestionar de manera organizada y eficiente todas las actividades asociadas a las recomendaciones", el botón **Informe** y las pestañas **Alertas**, **Recomendaciones** y **Actividades**. En **Alertas**: "Alertas tempranas" con **Descargar**, "Buscar por nombre" y **Filtros**.

| Columna | Descripción |
|---|---|
| Alerta | Número y fecha de la alerta |
| Cumplimiento | Ejecutado vs programado y % |
| Plan de acción | Estado del plan |
| Informe | Estado de los informes |
| Acciones | **Ir al plan de acción** y detalle |

Estados del **Plan de acción**: "Sin recomendaciones", "Sin plan" (recomendaciones sin actividades), "Pendiente" (hay actividades por aprobar), "Aprobado" (todas aprobadas; listo para confirmar), "Cerrado" (alerta cerrada). Estados del **Informe**: "Sin Informe", "Sin Completar", "Pendiente", "Aprobado", "Completado", "Cerrado".

Filtros: **Estado del Plan de Acción**, **Estado del Informe** y **Porcentaje de Cumplimiento** (0-30, 31-50, 51-80, 81-100). Ve los planes de su subdirección.

**Pasos:**

##### Paso 1.1: Abrir Planes de acción
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** Haga clic en **Planes de acción**.
**Resultado esperado:** Aparece la pestaña **Alertas**.

##### Paso 1.2: Leer el estado y el cumplimiento
**Objetivo del paso:** Saber qué plan está pendiente o aprobado.
**Qué hacer:** Lea las columnas Cumplimiento, Plan de acción e Informe.
**Resultado esperado:** Identifica, por ejemplo, los planes "Sin plan" que aún no tienen actividades.

##### Paso 1.3: Filtrar
**Objetivo del paso:** Ver solo lo que le interesa.
**Qué hacer:** Haga clic en **Filtros**, elija Estado del Plan de Acción, Estado del Informe o Porcentaje de Cumplimiento y **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 1.4: Ver el detalle del plan
**Objetivo del paso:** Revisar la información de la alerta y el historial del plan.
**Qué hacer:** Haga clic en el ícono de detalle de la fila.
**Resultado esperado:** Se abre la ficha con "Información de alerta" e "Historial Plan de acción".

##### Paso 1.5: Descargar el listado
**Objetivo del paso:** Tener el estado en un archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga un CSV con Número de Alerta, Cumplimiento (%) y Plan de Acción.

> 📷 **[CAPTURA MED-06-PLA-01]**: Planes de acción por alerta
> **Debe mostrar:** La pestaña Alertas de Planes de acción vista por un usuario Entidad Territorial (Subdirección)
> **Resaltar:** Columnas Cumplimiento, Plan de acción e Informe; Filtros
> **Pantalla / ruta:** `/planes-de-accion` (`dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Planes Mock en distintos estados
> **Texto alternativo:** Listado de planes de acción por alerta

**Resultado de la actividad:** Conoce el estado de los planes de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Hacer clic en **Informe** (Informe de recomendaciones) sin acceso | "Error al cargar el informe de recomendaciones" | El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Pida el consolidado a la Secretaría Técnica o al Monitor. | |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |
| La descarga del CSV falla | "Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

> 📷 **[CAPTURA MED-06-PLA-02]**: Mensaje ERR-PLA-17
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar el informe de recomendaciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/InformeRecomendaciones.tsx:82`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Hacer clic en **Informe** (Informe de recomendaciones) sin acceso

**⚠️ Atención:**
- El botón **Informe** aparece, pero el Informe de recomendaciones no está disponible para su rol: muestra "Error al cargar el informe de recomendaciones".

#### Actividad 2: Recorrer las recomendaciones del plan de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Planes de acción › fila › **Ir al plan de acción** (`/planes-de-accion/:id/recomendaciones`).

**Qué ve:** La tabla de recomendaciones de la alerta (Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades Aprobadas / Total, Ejecución Ejecutadas / Programadas) con **Ver Actividades** y el ícono de detalle. El detalle abre una ventana con las pestañas **Información**, **Actividades** e **Historial** ("No hay historial disponible." si no hay eventos). Solo ve las recomendaciones de su subdirección.

**Pasos:**

##### Paso 2.1: Entrar al plan
**Objetivo del paso:** Ver las recomendaciones de la alerta.
**Qué hacer:** En la fila de la alerta haga clic en **Ir al plan de acción**.
**Resultado esperado:** Aparece la tabla de recomendaciones.

##### Paso 2.2: Abrir el detalle de una recomendación
**Objetivo del paso:** Ver su información y su historial.
**Qué hacer:** Haga clic en el ícono de detalle y recorra **Información**, **Actividades** e **Historial**.
**Resultado esperado:** Ve la recomendación, sus actividades y los eventos del plan.

##### Paso 2.3: Ir a las actividades
**Objetivo del paso:** Trabajar las actividades de la recomendación.
**Qué hacer:** Haga clic en **Ver Actividades**.
**Resultado esperado:** Se abre la lista de actividades de la recomendación.

> 📷 **[CAPTURA MED-06-PLA-03]**: Recomendaciones del plan
> **Debe mostrar:** La tabla de recomendaciones con el botón Ver Actividades
> **Resaltar:** Ver Actividades; Actividades Aprobadas / Total
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/PlanDeAccionRecomendacionesTab.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alerta Mock con dos recomendaciones
> **Texto alternativo:** Recomendaciones del plan de acción de una alerta

**Resultado de la actividad:** Llega a las actividades de la recomendación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| No ver todas las recomendaciones de una alerta | No aparece mensaje: el listado muestra solo algunas recomendaciones. | Dentro de cada alerta solo ve las recomendaciones de su entidad o subdirección. | No requiere acción; si una recomendación de su entidad no aparece, pida que se revise su Entidad Principal. | |
| Las actividades no cargan o no se eliminan | "Error al cargar las actividades" / "Error al eliminar la actividad" | Falla del servicio. | Recargue la página e intente de nuevo. | |

> 📷 **[CAPTURA MED-06-PLA-04]**: Mensaje ERR-PLA-15
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar las actividades" / "Error al eliminar la actividad"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/RecomendacionDetailModalWithTabs.tsx:95-158`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Las actividades no cargan o no se eliminan

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25], la recomendación RC-002-2025-013 tiene como Entidad Principal "MinInterior - Democracia y Participación".

#### Actividad 3: Consultar las pestañas globales de Recomendaciones y Actividades

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Planes de acción › pestañas **Recomendaciones** y **Actividades**.

**Qué ve:** En **Recomendaciones**: todas las recomendaciones (con la columna Alerta), filtros por alerta, eje, entidad y modo, y **Descargar**. En **Actividades**: todas las actividades con Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; filtros **Alerta**, **Recomendacion**, **Estado**, **Instrumento de Planeación**, **Recursos** y **Plazo de Implementación**; **Descargar**.

**Pasos:**

##### Paso 3.1: Abrir Recomendaciones
**Objetivo del paso:** Ver todas las recomendaciones.
**Qué hacer:** Haga clic en la pestaña **Recomendaciones**.
**Resultado esperado:** Aparece la tabla global.

##### Paso 3.2: Abrir Actividades
**Objetivo del paso:** Ver todas las actividades.
**Qué hacer:** Haga clic en la pestaña **Actividades**.
**Resultado esperado:** Aparece la tabla global de actividades.

##### Paso 3.3: Filtrar y descargar
**Objetivo del paso:** Obtener un listado específico.
**Qué hacer:** Use **Filtros** (por ejemplo, Estado "Pendiente Aprobación") y luego **Descargar**.
**Resultado esperado:** Se descarga el CSV filtrado.

> 📷 **[CAPTURA MED-06-PLA-05]**: Pestaña global Actividades
> **Debe mostrar:** La tabla global de actividades con el filtro de Estado
> **Resaltar:** Pestañas; Filtros; columna Próximo Informe
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/GlobalActividadesTab.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Actividades Mock
> **Texto alternativo:** Vista global de actividades

**Resultado de la actividad:** Tiene la vista global de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La pestaña global **Actividades** no muestra las actividades de su subdirección | No aparece mensaje: la pestaña aparece vacía o con otras actividades. | El listado global filtra por la entidad central del usuario y no por la subdirección (riesgo R5). | Entre por **Alertas** › **Ir al plan de acción** › **Ver Actividades** de cada recomendación. | |
| La descarga del CSV falla | "Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

**⚠️ Atención:**
- ⚠️ Riesgo conocido R5: la pestaña **Actividades** filtra por su entidad central y no por su subdirección; si no ve sus actividades, entre por **Alertas** › **Ir al plan de acción** › **Ver Actividades**.

#### Actividad 4: Consultar las actividades de una recomendación y su detalle

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda leer cada actividad de una recomendación, su estado, su avance y su próximo informe.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La fecha de notificación es el día 0 del ciclo de informes; el sistema no verifica que sea posterior a la fecha de la alerta. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la fecha contra el documento (Super Administrador o Administrador) | RN-ALE-13 |
| Al aprobar un informe, el próximo informe es la fecha de notificación de la alerta + 6 meses (primer informe) o el anterior + 6 meses. | Revise el estado o el dato en la pantalla antes de actuar |, (Sistema) | RN-SEG-06 |
| Cada día a las 00:01, si el próximo informe de una actividad venció y la alerta no está cerrada, la actividad vuelve a "Sin Informe" y su Número de actividades se suma otra vez a lo programado. | Revise el estado o el dato en la pantalla antes de actuar | Reportar el informe del nuevo ciclo (Entidad Territorial) | RN-TAR-01 |

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** (`/planes-de-accion/:id/recomendaciones/:recomendacionId/actividades`); el detalle, en el menú ⋯ › **Ver detalle**.

**Qué ve:** La tabla de actividades, "Buscar por objetivo", **Filtros** (Estado, Instrumento de Planeación, Recursos), **Descargar** y **Agregar actividad**.

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
| Acciones | **Reportar Informe** / **Editar Informe** y menú ⋯ (Ver detalle, Editar Actividad, Eliminar Actividad, Comentarios) |

El menú ⋯ › **Ver detalle** abre "Detalle de Actividad" con "Seleccionar actividad", los campos de la actividad (Número de actividades, Plazo, Instrumento de planeación, Capacidades o recursos), el Estado Informe, la Ejecución, el Próximo Informe y la sección "Informes de ejecución". Cuando la alerta está cerrada, la columna de acciones no se muestra.

**Pasos:**

##### Paso 4.1: Abrir las actividades
**Objetivo del paso:** Ver la lista.
**Qué hacer:** Haga clic en **Ver Actividades** de la recomendación.
**Resultado esperado:** Aparece "Cargando actividades..." y luego la tabla.

##### Paso 4.2: Buscar y filtrar
**Objetivo del paso:** Encontrar una actividad.
**Qué hacer:** Escriba en "Buscar por objetivo" o use **Filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 4.3: Ver el detalle
**Objetivo del paso:** Leer la actividad completa.
**Qué hacer:** Haga clic en ⋯ › **Ver detalle** en la fila de la actividad.
**Resultado esperado:** Ve el detalle de la actividad; con varias actividades puede cambiar con "Seleccionar actividad".

##### Paso 4.4: Descargar
**Objetivo del paso:** Tener las actividades en un archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV de actividades.

> 📷 **[CAPTURA MED-06-PLA-06]**: Actividades de una recomendación
> **Debe mostrar:** La tabla de actividades vista por un usuario Entidad Territorial (Subdirección)
> **Resaltar:** Columnas Estado, Estado Informe, Próximo Informe
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Actividades Mock
> **Texto alternativo:** Listado de actividades de una recomendación

**Resultado de la actividad:** Conoce el detalle y el avance de las actividades.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Las actividades no cargan o no se eliminan | "Error al cargar las actividades" / "Error al eliminar la actividad" | Falla del servicio. | Recargue la página e intente de nuevo. | |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

**⚠️ Atención:**
- Con la alerta cerrada desaparece la columna de acciones (incluidos **Ver detalle** y **Comentarios**): consulte el detalle desde el ícono de detalle de la recomendación.

#### Actividad 5: Agregar una actividad al plan de acción

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda formular una actividad del plan de acción para una recomendación de su entidad, con objetivo, meta por semestre, plazo, instrumento y recursos.

**Cuándo se hace y requisitos previos:** Secuencia E3.2.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para agregar una actividad, la recomendación debe existir y la alerta no debe estar cerrada. | La recomendación aparece en su listado de Planes de acción | Esperar a que la recomendación esté registrada (Super Administrador o Administrador) | RN-PLA-01 |
| Objetivo, Actividad, Número de actividades (entero ≥ 1), Plazo de implementación, Instrumento de planeación y Recursos son obligatorios. | Revise el estado o el dato en la pantalla antes de actuar | Completar los 2 pasos del formulario (Entidad Territorial) | RN-PLA-02 |
| El plazo de implementación solo puede ser 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente; es informativo y no genera vencimientos. | Revise el estado o el dato en la pantalla antes de actuar | Elegir una opción de la lista (Entidad Territorial) | RN-PLA-03 |
| En pantalla, solo la Entidad Territorial y el Super Administrador agregan, editan y eliminan actividades, y solo desde Planes de acción. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el registro a la Entidad Territorial responsable (Entidad Territorial) | RN-PLA-06 |
| El servidor no verifica que la entidad que registra la actividad o el informe sea la Entidad Principal de la recomendación (riesgo R7): la pantalla solo le muestra sus recomendaciones. | Revise el estado o el dato en la pantalla antes de actuar | Trabajar solo desde su listado (Entidad Territorial) | RN-PLA-13 |

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** › **Agregar actividad** › ventana "Agregar actividad: Registrar una nueva actividad asociada a la recomendación, indicando la información básica necesaria para su ejecución.".

**Qué ve:** Un asistente de 2 pasos: 1 Información general (la Recomendación y el **Objetivo**) y 2 Información de la actividad (Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos, Observaciones). Botones **Cancelar**, **Siguiente**, **Atrás** y **Reportar actividad**.

**Campos a diligenciar: Agregar actividad / Editar actividad (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Recomendación (`(solo lectura)`) | No (se muestra) | Texto de solo lectura | |, | Recomendación desde la que se abre | RC-001-2025-013 [DATO REAL AT-013-25] | |
| 2 | Objetivo (`objective`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo | |, | "Promover la actualización y armonización del marco legal en materia electoral y de coordinación institucional." (AC-003-01) [DATO REAL AT-013-25] | "El objetivo es requerido" |
| 3 | Actividad (`activity_description`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo (NO EXISTE el mínimo de 40 de la línea base) | |, | "Realizar una mesa técnica interinstitucional, con el fin de formular recomendaciones de actualización o supresión…" (AC-003-01) [DATO REAL AT-013-25] | "La descripción de la actividad es requerida" |
| 4 | Número de actividades (`number_of_activities`) | Sí | Número entero | Entero ≥ 1; es la meta de cada ciclo de 6 meses | |, | 1 (AC-003-01) [DATO REAL AT-013-25] | "El número de actividades debe ser mayor a 0" |
| 5 | Plazo de implementación (`implementation_deadline`) | Sí | Lista de selección única | Solo informativo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente | | Permanente (AC-003-01) [DATO REAL AT-013-25] | "El plazo de implementación es requerido" / "Plazo de implementación inválido: …" |
| 6 | Instrumento de planeación (`planning_instrument`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí | "Debe seleccionar una opción" |
| 7 | Recursos (`resources`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí (AC-003-01; en la línea base "SI") [DATO REAL AT-013-25] | "Debe seleccionar una opción" |
| 8 | Observaciones (`observations`) | No | Área de texto | Sin límite | |, | Se coordinará con la Secretaría de Educación (dato ficticio) | |

- Campos que llena el sistema: Estado "Pendiente Aprobación"; la meta se suma a lo programado; se recalculan la recomendación y el plan.
- Campos que se bloquean: Una actividad aprobada, o con el plan confirmado o la alerta cerrada, no se edita ni se elimina.
- Archivos: No aplica.
- Guardar o enviar con: **Reportar actividad** (edición: **Guardar cambios**); **Siguiente** / **Atrás** / **Cancelar**.

**Pasos:**

##### Paso 5.1: Abrir el formulario
**Objetivo del paso:** Iniciar la formulación.
**Qué hacer:** En las actividades de la recomendación haga clic en **Agregar actividad**.
**Resultado esperado:** Se abre el Paso 1 con la recomendación ("{código} - {nombre}"). Si el plan ya estaba confirmado, aparece primero la advertencia "Agregar actividad a plan confirmado" (actividad siguiente).

##### Paso 5.2: Escribir el Objetivo
**Objetivo del paso:** Decir para qué se hace la actividad.
**Qué hacer:** En **Objetivo** escriba el propósito que busca la actividad frente al riesgo.
**Resultado esperado:** Sin objetivo: "El objetivo es requerido".

##### Paso 5.3: Avanzar al Paso 2
**Objetivo del paso:** Pasar a la información de la actividad.
**Qué hacer:** Haga clic en **Siguiente**.
**Resultado esperado:** Aparece el Paso 2.

##### Paso 5.4: Escribir la Actividad
**Objetivo del paso:** Describir lo que se va a hacer.
**Qué hacer:** En **Actividad** describa en futuro lo que hará la entidad (no lo que ya hizo: eso va en el informe de ejecución).
**Resultado esperado:** Sin texto: "La descripción de la actividad es requerida".

##### Paso 5.5: Definir el Número de actividades
**Objetivo del paso:** Fijar la meta por semestre.
**Qué hacer:** En **Número de actividades** escriba un entero mayor que 0: es la meta de cada ciclo de 6 meses ("Número de veces que se ejecutará la actividad.").
**Resultado esperado:** Con 0: "El número de actividades debe ser mayor a 0".

##### Paso 5.6: Elegir el Plazo de implementación
**Objetivo del paso:** Indicar la duración prevista.
**Qué hacer:** Despliegue **Plazo de implementación** y elija 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente.
**Resultado esperado:** El plazo queda seleccionado (es informativo: no genera vencimientos).

##### Paso 5.7: Responder Instrumento de planeación y Recursos
**Objetivo del paso:** Indicar si la actividad está planeada y financiada.
**Qué hacer:** En **Instrumento de planeación** ("¿La actividad está relacionada en algún instrumento de planeación?") y en **Recursos** ("¿La entidad cuenta con recursos o capacidades para implementar las actividades?") elija Sí o No.
**Resultado esperado:** Sin respuesta: "Debe seleccionar una opción".

##### Paso 5.8: Escribir Observaciones (opcional)
**Objetivo del paso:** Dejar información adicional.
**Qué hacer:** En **Observaciones** escriba lo que considere necesario.
**Resultado esperado:** El texto queda registrado.

##### Paso 5.9: Revisar y guardar
**Objetivo del paso:** Registrar la actividad.
**Qué hacer:** Revise con **Atrás** y haga clic en **Reportar actividad**.
**Resultado esperado:** Aparece "Actividad creada: La actividad ha sido creada correctamente."; la actividad queda "Pendiente Aprobación".

> 🎞️ **[GIF MED-06-PLA-07]**: Agregar actividad
> **Debe mostrar:** Los dos pasos del formulario con datos Mock
> **Resaltar:** Número de actividades; Plazo; Instrumento y Recursos; Reportar actividad
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Mock
> **Solo para GIF: Secuencia:** 1) Agregar actividad 2) Objetivo 3) Siguiente 4) Actividad y número 5) Plazo, instrumento, recursos 6) Reportar actividad · **Duración aproximada:** 35 segundos
> **Texto alternativo:** Animación del registro de una actividad

**Resultado de la actividad:** La actividad queda pendiente de aprobación; la recomendación y el plan pasan a "Pendiente" y el Número de actividades se suma a lo programado. El siguiente paso lo da el Monitor o el Líder de Macrozona en Seguimiento.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Avanzar o guardar la actividad sin datos | "El objetivo es requerido", "La descripción de la actividad es requerida", "El número de actividades debe ser mayor a 0", "El plazo de implementación es requerido", "Debe seleccionar una opción" | Faltan campos obligatorios. | Complete el Objetivo (Paso 1) y Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación y Recursos (Paso 2). | |
| Agregar actividades a una alerta cerrada | Botón deshabilitado con "No se pueden agregar actividades a una alerta cerrada" (servidor: "No se pueden crear actividades porque la alerta está cerrada") | La alerta está cerrada. | No requiere acción. | |
| El servidor recibe un plazo fuera de la lista | "Plazo de implementación inválido: …" | Solo se aceptan 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente. | Elija una opción de la lista. | |
| Abrir un formulario de registro desde un celular | "Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio." | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Planee el registro desde un computador. |

> 📷 **[CAPTURA MED-06-PLA-08]**: Mensaje ERR-PLA-01
> **Debe mostrar:** La pantalla con el mensaje "El objetivo es requerido", "La descripción de la actividad es requerida", "El número de actividades debe ser mayor a 0", "El plazo de implementación es requeri
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadModal.tsx:90-120`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Avanzar o guardar la actividad sin datos

> 📷 **[CAPTURA MED-06-PLA-09]**: Mensaje ERR-PLA-02
> **Debe mostrar:** La pantalla con el mensaje Botón deshabilitado con "No se pueden agregar actividades a una alerta cerrada" (servidor: "No se pueden crear actividades porque la alerta está cerrada")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:177`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar actividades a una alerta cerrada

> 📷 **[CAPTURA MED-06-PLA-10]**: Mensaje ERR-PLA-07
> **Debe mostrar:** La pantalla con el mensaje "Plazo de implementación inválido: …"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioActividades.cs:140-144`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor recibe un plazo fuera de la lista

**⚠️ Atención:**
- ⚠️ Una recomendación sin actividades impide confirmar el plan de toda la alerta: formule al menos una actividad por cada recomendación de su entidad.
- No existe un mínimo de 40 caracteres para la Actividad: escriba una descripción clara y medible.
- El "Instrumento de planeación" de la actividad es Sí/No; el del informe de ejecución es un texto.

**Ejemplo:** AC-003-01 de RC-003-2025-013 (Entidad Principal "MinInterior - Democracia y Participación") [DATO REAL AT-013-25]: Objetivo "Promover la actualización y armonización del marco legal en materia electoral y de coordinación institucional."; Actividad "Realizar una mesa técnica interinstitucional, con el fin de formular recomendaciones de actualización o supresión normativa…"; Número de actividades 1; Plazo "Permanente"; Instrumento de planeación: vacío en la línea base, pero la pantalla exige Sí o No; Recursos "Sí" (en la línea base "SI"). Mock: Objetivo "Reducir el riesgo de reclutamiento en la zona rural"; Actividad "Realizar 4 talleres de prevención con docentes y estudiantes en las sedes rurales"; 4; 3 a 6 meses; Sí; No.

#### Actividad 6: Agregar una actividad a un plan ya confirmado

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda agregar una actividad nueva después de la confirmación del plan, sabiendo que el plan se desconfirma.

**Cuándo se hace y requisitos previos:** Secuencia E4.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Agregar una actividad a un plan confirmado lo desconfirma: vuelve a Pendiente, la nueva actividad debe aprobarse y el plan debe confirmarse otra vez; lo existente no cambia. | Revise el estado o el dato en la pantalla antes de actuar | Agregar solo si es necesario y avisar al Monitor (Entidad Territorial) | RN-PLA-05 |
| Para agregar una actividad, la recomendación debe existir y la alerta no debe estar cerrada. | La recomendación aparece en su listado de Planes de acción | Esperar a que la recomendación esté registrada (Super Administrador o Administrador) | RN-PLA-01 |

**Dónde:** Actividades de la recomendación › **Agregar actividad** (con el plan confirmado) › advertencia "Agregar actividad a plan confirmado".

**Qué ve:** La advertencia: "Al agregar una nueva actividad a la alerta {número}, el plan de acción será desconfirmado automáticamente. Esto significa que: El estado del plan volverá a "Pendiente Aprobación" · Deberá aprobarse la nueva actividad · Deberá confirmarse el plan nuevamente. Las actividades e informes existentes se mantendrán sin cambios." con **Cancelar** y **Continuar**.

**Campos a diligenciar: Agregar actividad / Editar actividad (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Recomendación (`(solo lectura)`) | No (se muestra) | Texto de solo lectura | |, | Recomendación desde la que se abre | RC-001-2025-013 [DATO REAL AT-013-25] | |
| 2 | Objetivo (`objective`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo | |, | "Promover la actualización y armonización del marco legal en materia electoral y de coordinación institucional." (AC-003-01) [DATO REAL AT-013-25] | "El objetivo es requerido" |
| 3 | Actividad (`activity_description`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo (NO EXISTE el mínimo de 40 de la línea base) | |, | "Realizar una mesa técnica interinstitucional, con el fin de formular recomendaciones de actualización o supresión…" (AC-003-01) [DATO REAL AT-013-25] | "La descripción de la actividad es requerida" |
| 4 | Número de actividades (`number_of_activities`) | Sí | Número entero | Entero ≥ 1; es la meta de cada ciclo de 6 meses | |, | 1 (AC-003-01) [DATO REAL AT-013-25] | "El número de actividades debe ser mayor a 0" |
| 5 | Plazo de implementación (`implementation_deadline`) | Sí | Lista de selección única | Solo informativo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente | | Permanente (AC-003-01) [DATO REAL AT-013-25] | "El plazo de implementación es requerido" / "Plazo de implementación inválido: …" |
| 6 | Instrumento de planeación (`planning_instrument`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí | "Debe seleccionar una opción" |
| 7 | Recursos (`resources`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí (AC-003-01; en la línea base "SI") [DATO REAL AT-013-25] | "Debe seleccionar una opción" |
| 8 | Observaciones (`observations`) | No | Área de texto | Sin límite | |, | Se coordinará con la Secretaría de Educación (dato ficticio) | |

- Campos que llena el sistema: Estado "Pendiente Aprobación"; la meta se suma a lo programado; se recalculan la recomendación y el plan.
- Campos que se bloquean: Una actividad aprobada, o con el plan confirmado o la alerta cerrada, no se edita ni se elimina.
- Archivos: No aplica.
- Guardar o enviar con: **Reportar actividad** (edición: **Guardar cambios**); **Siguiente** / **Atrás** / **Cancelar**.

**Pasos:**

##### Paso 6.1: Leer la advertencia
**Objetivo del paso:** Entender el efecto.
**Qué hacer:** Haga clic en **Agregar actividad** y lea la advertencia.
**Resultado esperado:** Conoce que el plan se desconfirmará.

##### Paso 6.2: Decidir
**Objetivo del paso:** Agregar solo si es necesario.
**Qué hacer:** Haga clic en **Continuar** para seguir, o en **Cancelar**.
**Resultado esperado:** Con Continuar se abre el formulario de la actividad.

##### Paso 6.3: Diligenciar y guardar la actividad
**Objetivo del paso:** Registrar la nueva actividad.
**Qué hacer:** Complete Recomendación, Objetivo, Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos y Observaciones, y haga clic en **Reportar actividad**.
**Resultado esperado:** La actividad queda pendiente y el plan vuelve a "Pendiente".

##### Paso 6.4: Avisar a quien aprueba
**Objetivo del paso:** Evitar que el plan quede detenido.
**Qué hacer:** Informe al Monitor o al Líder de Macrozona que agregó una actividad (el sistema no les avisa).
**Resultado esperado:** El aprobador revisa y vuelve a confirmar el plan.

> 📷 **[CAPTURA MED-06-PLA-11]**: Agregar actividad a plan confirmado
> **Debe mostrar:** La advertencia de desconfirmación
> **Resaltar:** Lista de efectos y botón Continuar
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/DesconfirmarPlanModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Plan Mock confirmado
> **Texto alternativo:** Advertencia antes de agregar una actividad a un plan confirmado

**Resultado de la actividad:** El plan queda desconfirmado hasta que se apruebe la nueva actividad y se confirme otra vez; las actividades e informes anteriores no cambian.

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `main-api/CipratApi/Servicios/ServicioActividades.cs:132-137`. El aviso al aprobador se hace por fuera de la plataforma; vuelve como una nueva aprobación y confirmación en Seguimiento.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Agregar una actividad cuando el plan ya está confirmado | Advertencia "Agregar actividad a plan confirmado: Al agregar una nueva actividad a la alerta … el plan de acción será desconfirmado automáticamente. … El estado del plan volverá a "Pendiente Aprobación" · Deberá aprobarse la nueva actividad · Deberá confirmarse el plan nuevamente. Las actividades e informes existentes se mantendrán sin cambios." | Regla de desconfirmación automática. | Haga clic en **Continuar** solo si la actividad es necesaria; si no, **Cancelar**. | Formule todas las actividades antes de la confirmación. |
| Avanzar o guardar la actividad sin datos | "El objetivo es requerido", "La descripción de la actividad es requerida", "El número de actividades debe ser mayor a 0", "El plazo de implementación es requerido", "Debe seleccionar una opción" | Faltan campos obligatorios. | Complete el Objetivo (Paso 1) y Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación y Recursos (Paso 2). | |

> 📷 **[CAPTURA MED-06-PLA-12]**: Mensaje ERR-PLA-05
> **Debe mostrar:** La pantalla con el mensaje Advertencia "Agregar actividad a plan confirmado: Al agregar una nueva actividad a la alerta … el plan de acción será desconfirmado automáticamente. … El estad
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/DesconfirmarPlanModal.tsx:96-139`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar una actividad cuando el plan ya está confirmado

**⚠️ Atención:**
- ⚠️ El mensaje de la confirmación del plan dice que "las entidades territoriales no podrán editar ni agregar actividades", pero el sistema sí lo permite y desconfirma el plan.

#### Actividad 7: Editar o eliminar una actividad pendiente

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda corregir o retirar una actividad mientras está pendiente de aprobación y el plan no está confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E3.3.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para editar o eliminar una actividad, debe estar pendiente de aprobación, el plan no debe estar confirmado y la alerta no debe estar cerrada. | La columna Estado dice "Pendiente Aprobación" | Pedir "Descartar aprobación" al Monitor o Líder (si el plan no está confirmado) (Monitor o Líder de Macrozona) | RN-PLA-04 |
| Objetivo, Actividad, Número de actividades (entero ≥ 1), Plazo de implementación, Instrumento de planeación y Recursos son obligatorios. | Revise el estado o el dato en la pantalla antes de actuar | Completar los 2 pasos del formulario (Entidad Territorial) | RN-PLA-02 |

**Dónde:** Actividades › ⋯ › **Editar Actividad** / **Eliminar Actividad** (también en "Detalle de Actividad": botones Editar y Eliminar).

**Qué ve:** El formulario "Editar actividad: Modifica la información de la actividad asociada a la recomendación." con **Guardar cambios**; para eliminar, "Eliminar actividad: Esta acción no se puede deshacer. ¿Está seguro que desea eliminar esta actividad?". Si la actividad está aprobada, los botones aparecen deshabilitados con "No se puede editar porque la actividad ya está aprobada" / "No se puede eliminar porque la actividad ya está aprobada".

**Campos a diligenciar: Agregar actividad / Editar actividad (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Recomendación (`(solo lectura)`) | No (se muestra) | Texto de solo lectura | |, | Recomendación desde la que se abre | RC-001-2025-013 [DATO REAL AT-013-25] | |
| 2 | Objetivo (`objective`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo | |, | "Promover la actualización y armonización del marco legal en materia electoral y de coordinación institucional." (AC-003-01) [DATO REAL AT-013-25] | "El objetivo es requerido" |
| 3 | Actividad (`activity_description`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo (NO EXISTE el mínimo de 40 de la línea base) | |, | "Realizar una mesa técnica interinstitucional, con el fin de formular recomendaciones de actualización o supresión…" (AC-003-01) [DATO REAL AT-013-25] | "La descripción de la actividad es requerida" |
| 4 | Número de actividades (`number_of_activities`) | Sí | Número entero | Entero ≥ 1; es la meta de cada ciclo de 6 meses | |, | 1 (AC-003-01) [DATO REAL AT-013-25] | "El número de actividades debe ser mayor a 0" |
| 5 | Plazo de implementación (`implementation_deadline`) | Sí | Lista de selección única | Solo informativo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente | | Permanente (AC-003-01) [DATO REAL AT-013-25] | "El plazo de implementación es requerido" / "Plazo de implementación inválido: …" |
| 6 | Instrumento de planeación (`planning_instrument`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí | "Debe seleccionar una opción" |
| 7 | Recursos (`resources`) | Sí | Selección única (Sí / No) | | Sí, No | | Sí (AC-003-01; en la línea base "SI") [DATO REAL AT-013-25] | "Debe seleccionar una opción" |
| 8 | Observaciones (`observations`) | No | Área de texto | Sin límite | |, | Se coordinará con la Secretaría de Educación (dato ficticio) | |

- Campos que llena el sistema: Estado "Pendiente Aprobación"; la meta se suma a lo programado; se recalculan la recomendación y el plan.
- Campos que se bloquean: Una actividad aprobada, o con el plan confirmado o la alerta cerrada, no se edita ni se elimina.
- Archivos: No aplica.
- Guardar o enviar con: **Reportar actividad** (edición: **Guardar cambios**); **Siguiente** / **Atrás** / **Cancelar**.

**Pasos:**

##### Paso 7.1: Verificar el estado
**Objetivo del paso:** Saber si se puede modificar.
**Qué hacer:** Confirme que la columna Estado diga "Pendiente Aprobación".
**Resultado esperado:** Si dice "Aprobado", no se puede editar ni eliminar.

##### Paso 7.2: Editar
**Objetivo del paso:** Corregir la actividad.
**Qué hacer:** Haga clic en ⋯ › **Editar Actividad**, ajuste Objetivo, Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos u Observaciones, y **Guardar cambios**.
**Resultado esperado:** Aparece "Actividad actualizada: La actividad ha sido actualizada correctamente."

##### Paso 7.3: Eliminar (si aplica)
**Objetivo del paso:** Retirar una actividad equivocada.
**Qué hacer:** Haga clic en ⋯ › **Eliminar Actividad** y confirme.
**Resultado esperado:** Aparece "Actividad eliminada: La actividad ha sido eliminada correctamente."

> 📷 **[CAPTURA MED-06-PLA-13]**: Botones deshabilitados en actividad aprobada
> **Debe mostrar:** El detalle de una actividad aprobada con Editar y Eliminar deshabilitados
> **Resaltar:** Mensajes de los botones
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:395-460`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Actividad Mock aprobada
> **Texto alternativo:** Actividad aprobada que no se puede editar

**Resultado de la actividad:** La actividad queda corregida o eliminada; el estado de la recomendación y del plan se recalcula.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Editar o eliminar una actividad aprobada | Botones deshabilitados con "No se puede editar porque la actividad ya está aprobada" / "No se puede eliminar porque la actividad ya está aprobada" (servidor: "No se puede editar una actividad aprobada o cerrada") | Las actividades aprobadas quedan bloqueadas. | Si debe corregirla, pida al Monitor o al Líder de Macrozona que use **Descartar aprobación** (solo si el plan no está confirmado). | Revise la actividad antes de que sea aprobada. |
| Editar o eliminar una actividad con el plan confirmado | "No se puede editar la actividad porque el plan de acción ya fue confirmado" / "No se puede eliminar la actividad porque el plan de acción ya fue confirmado" | Con el plan confirmado no se modifican actividades. | Si necesita una acción adicional, agréguela como actividad nueva (esto desconfirma el plan). | |
| Avanzar o guardar la actividad sin datos | "El objetivo es requerido", "La descripción de la actividad es requerida", "El número de actividades debe ser mayor a 0", "El plazo de implementación es requerido", "Debe seleccionar una opción" | Faltan campos obligatorios. | Complete el Objetivo (Paso 1) y Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación y Recursos (Paso 2). | |
| Las actividades no cargan o no se eliminan | "Error al cargar las actividades" / "Error al eliminar la actividad" | Falla del servicio. | Recargue la página e intente de nuevo. | |

> 📷 **[CAPTURA MED-06-PLA-14]**: Mensaje ERR-PLA-03
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No se puede editar porque la actividad ya está aprobada" / "No se puede eliminar porque la actividad ya está aprobada" (servidor: "N
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:410-440`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar o eliminar una actividad aprobada

> 📷 **[CAPTURA MED-06-PLA-15]**: Mensaje ERR-PLA-04
> **Debe mostrar:** La pantalla con el mensaje "No se puede editar la actividad porque el plan de acción ya fue confirmado" / "No se puede eliminar la actividad porque el plan de acción ya fue confirmado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioActividades.cs:226-236,315-325`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar o eliminar una actividad con el plan confirmado

**⚠️ Atención:**
- ⚠️ Eliminar una actividad no se puede deshacer.
- Si la actividad ya fue aprobada, pida al Monitor o al Líder de Macrozona que use **Descartar aprobación** (solo si el plan no está confirmado).

#### Actividad 8: Comentar una actividad y atender los comentarios de la revisión

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda leer y escribir comentarios en una actividad para acordar ajustes con quien revisa.

**Cuándo se hace y requisitos previos:** Secuencia E3.4.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada comentario admite hasta 2.000 caracteres. | Revise el estado o el dato en la pantalla antes de actuar | Dividir el comentario (Quien comenta) | RN-PLA-12 |

**Dónde:** Actividades de la recomendación › ⋯ › **Comentarios** (o "Detalle de Actividad" › ícono **Comentarios**).

**Qué ve:** La ventana "Comentarios" con la conversación de la actividad: cada comentario con autor ("Tú" para los suyos) y fecha; sin comentarios: "No hay comentarios aún". Abajo, el campo "Comentarios" y el botón de envío. Los comentarios del Monitor o del Líder de Macrozona aparecen aquí.

**Campos a diligenciar: Comentarios de la actividad:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Comentarios (`contenido`) | Sí | Texto | Máx. 2.000 caracteres (servidor) | |, | Precisar cuántas sedes rurales se atenderán (dato ficticio) | "El contenido no puede exceder 2000 caracteres" / "Error al enviar el comentario" |

- Campos que llena el sistema: Autor ("Tú" para los propios) y fecha.
- Campos que se bloquean: No hay opción para editar ni eliminar comentarios en la pantalla.
- Archivos: No aplica.
- Guardar o enviar con: Botón de envío junto al campo (o tecla Enter).

**Pasos:**

##### Paso 8.1: Abrir los comentarios
**Objetivo del paso:** Ver lo que pidió quien revisa.
**Qué hacer:** En la fila de la actividad haga clic en ⋯ › **Comentarios** (o, en el detalle, en el ícono **Comentarios**).
**Resultado esperado:** Se abre la conversación.

##### Paso 8.2: Escribir un comentario
**Objetivo del paso:** Responder o pedir aclaraciones.
**Qué hacer:** Escriba en el campo "Comentarios" (máx. 2.000 caracteres) y envíe.
**Resultado esperado:** El comentario aparece con su nombre y la fecha.

##### Paso 8.3: Ajustar la actividad
**Objetivo del paso:** Atender lo pedido.
**Qué hacer:** Si le pidieron cambios y la actividad sigue pendiente, edítela (actividad "Editar o eliminar una actividad pendiente").
**Resultado esperado:** La actividad queda lista para la aprobación.

> 📷 **[CAPTURA MED-06-PLA-16]**: Comentarios de la actividad
> **Debe mostrar:** La ventana Comentarios con una conversación entre el Monitor y la entidad
> **Resaltar:** Campo Comentarios
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Comentarios Mock
> **Texto alternativo:** Conversación de comentarios de una actividad

**Resultado de la actividad:** Queda registrada la conversación sobre la actividad.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Enviar un comentario muy largo o con falla | "El contenido no puede exceder 2000 caracteres" / "Error al enviar el comentario" | Límite de 2.000 caracteres o falla de conexión. | Divida el comentario en varios o intente de nuevo. | |

> 📷 **[CAPTURA MED-06-PLA-17]**: Mensaje ERR-PLA-08
> **Debe mostrar:** La pantalla con el mensaje "El contenido no puede exceder 2000 caracteres" / "Error al enviar el comentario"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/DTOs/ComentarioActividad/SolicitudCrearComentario.cs:13-14`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Enviar un comentario muy largo o con falla

**⚠️ Atención:**
- No hay opción para borrar comentarios en la pantalla.
- Comentar no cambia el estado de la actividad.
- Con la alerta cerrada no aparece la columna de acciones y, con ella, el acceso a **Comentarios** desde la tabla.

#### Actividad 9: Reportar un informe de ejecución

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda reportar lo ejecutado de una actividad en el ciclo, con su soporte en PDF, cuando el plan está confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E5.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para reportar un informe de ejecución, el plan de acción de la alerta debe estar confirmado. | Llegó el correo "Notificación validación Plan de Acción" o el plan aparece confirmado | Esperar la confirmación del plan (Monitor o Líder de Macrozona) | RN-PLA-07 |
| Las actividades ejecutadas no pueden superar el Número de actividades programadas del ciclo. | Revise el estado o el dato en la pantalla antes de actuar | Reportar lo ejecutado dentro de la meta (Entidad Territorial) | RN-PLA-08 |
| La fecha de fin de la ejecución debe ser igual o posterior a la fecha de inicio. | Revise el estado o el dato en la pantalla antes de actuar | Corregir las fechas (Entidad Territorial) | RN-PLA-09 |
| Actividades ejecutadas, fechas, Acciones implementadas, Buenas prácticas, Resultados y el PDF son obligatorios (el PDF, en la pantalla). | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario y adjuntar el PDF (Entidad Territorial) | RN-PLA-10 |
| Cada día a las 00:01, si el próximo informe de una actividad venció y la alerta no está cerrada, la actividad vuelve a "Sin Informe" y su Número de actividades se suma otra vez a lo programado. | Revise el estado o el dato en la pantalla antes de actuar | Reportar el informe del nuevo ciclo (Entidad Territorial) | RN-TAR-01 |
| La fecha de notificación es el día 0 del ciclo de informes; el sistema no verifica que sea posterior a la fecha de la alerta. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la fecha contra el documento (Super Administrador o Administrador) | RN-ALE-13 |
| Al aprobar un informe, el próximo informe es la fecha de notificación de la alerta + 6 meses (primer informe) o el anterior + 6 meses. | Revise el estado o el dato en la pantalla antes de actuar |, (Sistema) | RN-SEG-06 |

**Dónde:** Planes de acción › … › actividades de la recomendación › **Reportar Informe** › ventana "Cargar informe de ejecución: Reporta el avance y la ejecución de las actividades".

**Qué ve:** La ventana muestra arriba la "Descripción de la actividad", "Actividades:", "Plazo:" y "Estado:" y luego el formulario del informe. Si el plan no está confirmado, el botón **Reportar Informe** está deshabilitado con "El plan de acción debe estar confirmado para reportar informes".

**Campos a diligenciar: Cargar informe de ejecución / Editar informe de ejecución:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Actividades ejecutadas (`actividades_ejecutadas`) | Sí | Lista de selección (número) | Entero de 0 al Número de actividades | 0 … N (N = Número de actividades) | Número de actividades de la actividad | 3 (de 4) | "Las actividades ejecutadas son requeridas" / "No puede ser mayor que {N}" |
| 2 | Fecha de inicio y fin (Inicio ejecución) (`fecha_inicio`) | Sí | Fecha | |, | | 01/02/2026 | "La fecha de inicio es requerida" |
| 3 | Fecha de inicio y fin (Fin de ejecución) (`fecha_fin`) | Sí | Fecha | ≥ fecha de inicio | | Inicio ejecución | 30/06/2026 | "La fecha de fin es requerida" / "La fecha de fin debe ser posterior a la fecha de inicio" |
| 4 | Acciones implementadas (`acciones_implementadas`) | Sí | Área de texto | Mínimo 1 carácter | |, | Se realizaron 3 talleres con 85 asistentes (dato ficticio) | "Las acciones implementadas son requeridas" |
| 5 | Acciones complementarias (`acciones_complementarias`) | No | Área de texto | |, | | Campaña radial local (dato ficticio) | |
| 6 | Acciones de coordinación (`acciones_coordinacion`) | No | Área de texto | |, | | Mesa con la Personería (dato ficticio) | |
| 7 | Buenas prácticas (`buenas_practicas`) | Sí | Área de texto | Mínimo 1 carácter | |, | Convocatoria con líderes comunitarios (dato ficticio) | "Las buenas prácticas son requeridas" |
| 8 | Instrumento de planeación (`instrumento_planeacion`) | No | Área de texto | Texto libre (distinto del Sí/No de la actividad) | |, | Plan de Desarrollo Departamental (dato ficticio) | |
| 9 | Resultados (`resultados`) | Sí | Área de texto | Mínimo 1 carácter | |, | 85 estudiantes sensibilizados (dato ficticio) | "Los resultados son requeridos" |
| 10 | Dificultades (`dificultades`) | No | Área de texto | |, | | Las lluvias impidieron un taller (dato ficticio) | |
| 11 | Archivo adjunto (PDF del informe) (`pdfInforme`) | Sí (en pantalla) | Archivo | PDF ≤ 20 MB | |, | informe_ejecucion_prueba.pdf | "El archivo adjunto es requerido" / "Solo se permiten archivos PDF" |

- Campos que llena el sistema: Estado "Pendiente aprobación"; la ventana muestra la descripción de la actividad, Actividades, Plazo y Estado como referencia.
- Campos que se bloquean: Un informe aprobado no se edita.
- Archivos: Un PDF obligatorio en pantalla ("Solo se permiten archivos PDF"), hasta 20 MB.
- Guardar o enviar con: **Reportar informe de ejecución** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 9.1: Verificar que el plan esté confirmado
**Objetivo del paso:** Saber si ya puede reportar.
**Qué hacer:** Confirme que recibió el correo "Notificación validación Plan de Acción" o que el botón **Reportar Informe** esté habilitado.
**Resultado esperado:** El botón está activo.

##### Paso 9.2: Abrir el formulario
**Objetivo del paso:** Iniciar el informe.
**Qué hacer:** Haga clic en **Reportar Informe** en la fila de la actividad.
**Resultado esperado:** Se abre "Cargar informe de ejecución".

##### Paso 9.3: Elegir las actividades ejecutadas
**Objetivo del paso:** Registrar el avance del ciclo.
**Qué hacer:** En **Actividades ejecutadas** elija cuántas de las programadas se ejecutaron (de 0 al Número de actividades).
**Resultado esperado:** Si elige más de las programadas: "No puede ser mayor que {N}".

##### Paso 9.4: Elegir las fechas de ejecución
**Objetivo del paso:** Ubicar el periodo reportado.
**Qué hacer:** En **Fecha de inicio y fin** elija "Inicio ejecución" y "Fin de ejecución".
**Resultado esperado:** Si el fin es anterior al inicio: "La fecha de fin debe ser posterior a la fecha de inicio".

##### Paso 9.5: Describir las acciones
**Objetivo del paso:** Explicar lo realizado.
**Qué hacer:** Escriba **Acciones implementadas** (obligatorio), **Acciones complementarias** y **Acciones de coordinación** (opcionales).
**Resultado esperado:** Sin acciones implementadas: "Las acciones implementadas son requeridas".

##### Paso 9.6: Describir buenas prácticas e instrumento
**Objetivo del paso:** Registrar lo que funcionó y su planeación.
**Qué hacer:** Escriba **Buenas prácticas** (obligatorio) e **Instrumento de planeación** (opcional, texto).
**Resultado esperado:** Sin buenas prácticas: "Las buenas prácticas son requeridas".

##### Paso 9.7: Describir resultados y dificultades
**Objetivo del paso:** Mostrar los logros y los problemas.
**Qué hacer:** Escriba **Resultados** (obligatorio) y **Dificultades** (opcional).
**Resultado esperado:** Sin resultados: "Los resultados son requeridos".

##### Paso 9.8: Adjuntar el PDF de soporte
**Objetivo del paso:** Dejar la evidencia que exige la aprobación.
**Qué hacer:** Haga clic en el área de carga y elija el PDF del informe (hasta 20 MB).
**Resultado esperado:** Sin archivo: "El archivo adjunto es requerido"; con otro formato: "Solo se permiten archivos PDF".

##### Paso 9.9: Revisar y enviar
**Objetivo del paso:** Registrar el informe.
**Qué hacer:** Revise los textos y haga clic en **Reportar informe de ejecución**.
**Resultado esperado:** Aparece "Informe reportado: El informe de ejecución ha sido reportado correctamente."; el Estado Informe pasa a "Pendiente".

> 🎞️ **[GIF MED-06-PLA-18]**: Reportar informe de ejecución
> **Debe mostrar:** El diligenciamiento completo del informe con PDF
> **Resaltar:** Actividades ejecutadas; fechas; campos obligatorios; PDF; botón Reportar informe de ejecución
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ReportarInformeModal.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Actividad Mock con plan confirmado
> **Solo para GIF: Secuencia:** 1) Reportar Informe 2) Ejecutadas 3) Fechas 4) Acciones 5) Buenas prácticas y resultados 6) PDF 7) Reportar · **Duración aproximada:** 40 segundos
> **Texto alternativo:** Animación del reporte de un informe de ejecución

**Resultado de la actividad:** El informe queda pendiente de aprobación. El Monitor o el Líder de Macrozona lo aprueban en Seguimiento (no reciben correo: puede avisarles).

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `dashboard/src/components/planes-de-accion/ReportarInformeModal.tsx:165-173`. El soporte de la ejecución se produce fuera de la plataforma; vuelve como el PDF adjunto del informe.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Reportar un informe antes de que el plan esté confirmado | Botón deshabilitado con "El plan de acción debe estar confirmado para reportar informes" (servidor: "No se pueden crear informes de ejecución hasta que el plan de acción esté confirmado") | Los informes solo se habilitan con el plan confirmado. | Espere el correo "Notificación validación Plan de Acción" o revise el estado del plan. | |
| Guardar el informe sin datos obligatorios | "Las actividades ejecutadas son requeridas", "La fecha de inicio es requerida", "La fecha de fin es requerida", "Las acciones implementadas son requeridas", "Las buenas prácticas son requeridas", "Los resultados son requeridos", "El archivo adjunto es requerido" | Faltan datos obligatorios del informe. | Complete los campos marcados y adjunte el PDF. | Prepare el PDF de soporte antes de abrir el formulario. |
| Poner la fecha de fin antes de la de inicio | "La fecha de fin debe ser posterior a la fecha de inicio" | Rango de fechas inválido. | Corrija la fecha de inicio o de fin. | |
| Reportar más actividades ejecutadas que las programadas | "No puede ser mayor que {N}" (servidor: "El número de actividades ejecutadas (X) no puede ser mayor que el número de actividades programadas (Y)") | Lo ejecutado no puede superar el "Número de actividades" del ciclo. | Elija un número entre 0 y el número de actividades programadas; explique lo adicional en Acciones complementarias. | |
| El informe no se guarda | "Error al guardar el informe. Por favor, intente nuevamente." o el mensaje del servidor | Falla del servicio o validación del servidor. | Lea el mensaje, corrija y vuelva a hacer clic en **Reportar informe de ejecución**. | |
| Seleccionar un archivo que no es PDF | "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF") | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Prepare los soportes en PDF antes de abrir el formulario. |
| Seleccionar un PDF muy pesado | "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB") | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Escanee en resolución media y sin color cuando sea posible. |
| No llega el recordatorio de informe | No aparece mensaje. | El recordatorio solo se envía una vez por ciclo, a 30 días o menos, y depende de la tarea diaria. | Consulte la columna "Próximo Informe" de sus actividades. | Anote la fecha del próximo informe cuando le aprueben un informe. |
| Aprobar el primer informe de una actividad después de la fecha de notificación + 6 meses | No aparece mensaje: al día siguiente la actividad vuelve a "Sin Informe", el % de cumplimiento baja y se abre un nuevo ciclo. | El próximo informe se calcula desde la fecha de notificación de la alerta y no desde la aprobación; si esa fecha ya pasó, la tarea diaria abre el nuevo ciclo de inmediato. | La entidad reporta el informe del nuevo ciclo; el aprobador lo revisa en Seguimiento. | Reportar y aprobar los informes antes de la fecha de notificación + 6 meses. |

> 📷 **[CAPTURA MED-06-PLA-19]**: Mensaje ERR-PLA-09
> **Debe mostrar:** La pantalla con el mensaje Botón deshabilitado con "El plan de acción debe estar confirmado para reportar informes" (servidor: "No se pueden crear informes de ejecución hasta que el plan 
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:589`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Reportar un informe antes de que el plan esté confirmado

> 📷 **[CAPTURA MED-06-PLA-20]**: Mensaje ERR-PLA-10
> **Debe mostrar:** La pantalla con el mensaje "Las actividades ejecutadas son requeridas", "La fecha de inicio es requerida", "La fecha de fin es requerida", "Las acciones implementadas son requeridas", "La
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ReportarInformeModal.tsx:133-173`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Guardar el informe sin datos obligatorios

> 📷 **[CAPTURA MED-06-PLA-21]**: Mensaje ERR-PLA-11
> **Debe mostrar:** La pantalla con el mensaje "La fecha de fin debe ser posterior a la fecha de inicio"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ReportarInformeModal.tsx:64,149`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Poner la fecha de fin antes de la de inicio

> 📷 **[CAPTURA MED-06-PLA-22]**: Mensaje ERR-PLA-12
> **Debe mostrar:** La pantalla con el mensaje "No puede ser mayor que {N}" (servidor: "El número de actividades ejecutadas (X) no puede ser mayor que el número de actividades programadas (Y)")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioInformesEjecucion.cs:56-60`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Reportar más actividades ejecutadas que las programadas

> 📷 **[CAPTURA MED-06-PLA-23]**: Mensaje ERR-PLA-14
> **Debe mostrar:** La pantalla con el mensaje "Error al guardar el informe. Por favor, intente nuevamente." o el mensaje del servidor
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ReportarInformeModal.tsx:224-229`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El informe no se guarda

> 📷 **[CAPTURA MED-06-PLA-24]**: Mensaje ERR-GEN-08
> **Debe mostrar:** La pantalla con el mensaje "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/FileUploadField.tsx:53-64`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Seleccionar un archivo que no es PDF

> 📷 **[CAPTURA MED-06-PLA-25]**: Mensaje ERR-GEN-09
> **Debe mostrar:** La pantalla con el mensaje "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioArchivos.cs:820-827`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Seleccionar un PDF muy pesado

**⚠️ Atención:**
- ⚠️ Sin PDF, el informe no puede aprobarse por la ruta de la actividad.
- La meta (Número de actividades) se renueva cada 6 meses: lo ejecutado se compara con lo programado acumulado.

**Ejemplo:** El sistema no fija una fecha para el primer informe: la columna Próximo Informe queda vacía hasta que se aprueba el primer informe. Al aprobarlo, el próximo informe queda en la fecha de notificación + 6 meses; por ejemplo, para la AT-013-2025  (notificada el 07/10/2025), el 07/04/2026, y el siguiente el 07/10/2026. Si el primer informe se aprueba después de esa fecha, al día siguiente se abre un nuevo ciclo. Ejemplo Mock: Actividades ejecutadas 3 de 4; Inicio 01/02/2026; Fin 30/03/2026.

#### Actividad 10: Editar un informe de ejecución pendiente

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda corregir un informe o su PDF mientras no haya sido aprobado.

**Cuándo se hace y requisitos previos:** Secuencia E5.2.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Un informe aprobado no se edita: el siguiente se reporta cuando pasa la fecha del "Próximo Informe". | La columna Estado Informe dice "Aprobado" | Esperar el siguiente ciclo (Entidad Territorial) | RN-PLA-11 |
| Las actividades ejecutadas no pueden superar el Número de actividades programadas del ciclo. | Revise el estado o el dato en la pantalla antes de actuar | Reportar lo ejecutado dentro de la meta (Entidad Territorial) | RN-PLA-08 |
| La fecha de fin de la ejecución debe ser igual o posterior a la fecha de inicio. | Revise el estado o el dato en la pantalla antes de actuar | Corregir las fechas (Entidad Territorial) | RN-PLA-09 |
| Actividades ejecutadas, fechas, Acciones implementadas, Buenas prácticas, Resultados y el PDF son obligatorios (el PDF, en la pantalla). | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario y adjuntar el PDF (Entidad Territorial) | RN-PLA-10 |

**Dónde:** Actividades › **Editar Informe** › ventana "Editar informe de ejecución: Modifica los datos del informe de ejecución".

**Qué ve:** El mismo formulario con los datos del informe y el botón **Guardar cambios**. Si el informe ya está aprobado, el botón muestra "No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe."

**Campos a diligenciar: Cargar informe de ejecución / Editar informe de ejecución:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Actividades ejecutadas (`actividades_ejecutadas`) | Sí | Lista de selección (número) | Entero de 0 al Número de actividades | 0 … N (N = Número de actividades) | Número de actividades de la actividad | 3 (de 4) | "Las actividades ejecutadas son requeridas" / "No puede ser mayor que {N}" |
| 2 | Fecha de inicio y fin (Inicio ejecución) (`fecha_inicio`) | Sí | Fecha | |, | | 01/02/2026 | "La fecha de inicio es requerida" |
| 3 | Fecha de inicio y fin (Fin de ejecución) (`fecha_fin`) | Sí | Fecha | ≥ fecha de inicio | | Inicio ejecución | 30/06/2026 | "La fecha de fin es requerida" / "La fecha de fin debe ser posterior a la fecha de inicio" |
| 4 | Acciones implementadas (`acciones_implementadas`) | Sí | Área de texto | Mínimo 1 carácter | |, | Se realizaron 3 talleres con 85 asistentes (dato ficticio) | "Las acciones implementadas son requeridas" |
| 5 | Acciones complementarias (`acciones_complementarias`) | No | Área de texto | |, | | Campaña radial local (dato ficticio) | |
| 6 | Acciones de coordinación (`acciones_coordinacion`) | No | Área de texto | |, | | Mesa con la Personería (dato ficticio) | |
| 7 | Buenas prácticas (`buenas_practicas`) | Sí | Área de texto | Mínimo 1 carácter | |, | Convocatoria con líderes comunitarios (dato ficticio) | "Las buenas prácticas son requeridas" |
| 8 | Instrumento de planeación (`instrumento_planeacion`) | No | Área de texto | Texto libre (distinto del Sí/No de la actividad) | |, | Plan de Desarrollo Departamental (dato ficticio) | |
| 9 | Resultados (`resultados`) | Sí | Área de texto | Mínimo 1 carácter | |, | 85 estudiantes sensibilizados (dato ficticio) | "Los resultados son requeridos" |
| 10 | Dificultades (`dificultades`) | No | Área de texto | |, | | Las lluvias impidieron un taller (dato ficticio) | |
| 11 | Archivo adjunto (PDF del informe) (`pdfInforme`) | Sí (en pantalla) | Archivo | PDF ≤ 20 MB | |, | informe_ejecucion_prueba.pdf | "El archivo adjunto es requerido" / "Solo se permiten archivos PDF" |

- Campos que llena el sistema: Estado "Pendiente aprobación"; la ventana muestra la descripción de la actividad, Actividades, Plazo y Estado como referencia.
- Campos que se bloquean: Un informe aprobado no se edita.
- Archivos: Un PDF obligatorio en pantalla ("Solo se permiten archivos PDF"), hasta 20 MB.
- Guardar o enviar con: **Reportar informe de ejecución** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 10.1: Abrir la edición
**Objetivo del paso:** Cargar el informe.
**Qué hacer:** Haga clic en **Editar Informe** en la fila de la actividad.
**Resultado esperado:** Se abre el formulario con los datos.

##### Paso 10.2: Corregir los datos
**Objetivo del paso:** Ajustar lo pedido por el aprobador.
**Qué hacer:** Modifique Actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades o el PDF.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 10.3: Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Informe actualizado: El informe de ejecución ha sido actualizado correctamente."

> 📷 **[CAPTURA MED-06-PLA-26]**: Editar informe bloqueado
> **Debe mostrar:** El botón Editar Informe deshabilitado con su mensaje en un informe aprobado
> **Resaltar:** Mensaje "No se puede editar porque el informe ya está aprobado…"
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:636`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Informe Mock aprobado
> **Texto alternativo:** Botón de editar informe deshabilitado

**Resultado de la actividad:** El informe queda corregido y sigue pendiente de aprobación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Editar un informe ya aprobado | Botón deshabilitado con "No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe." (servidor: "No se puede modificar un informe que ya fue aprobado") | La aprobación del informe es irreversible. | Espere la fecha del "Próximo Informe" para reportar el siguiente. | Revise el informe antes de que lo aprueben. |
| Guardar el informe sin datos obligatorios | "Las actividades ejecutadas son requeridas", "La fecha de inicio es requerida", "La fecha de fin es requerida", "Las acciones implementadas son requeridas", "Las buenas prácticas son requeridas", "Los resultados son requeridos", "El archivo adjunto es requerido" | Faltan datos obligatorios del informe. | Complete los campos marcados y adjunte el PDF. | Prepare el PDF de soporte antes de abrir el formulario. |
| Poner la fecha de fin antes de la de inicio | "La fecha de fin debe ser posterior a la fecha de inicio" | Rango de fechas inválido. | Corrija la fecha de inicio o de fin. | |
| Reportar más actividades ejecutadas que las programadas | "No puede ser mayor que {N}" (servidor: "El número de actividades ejecutadas (X) no puede ser mayor que el número de actividades programadas (Y)") | Lo ejecutado no puede superar el "Número de actividades" del ciclo. | Elija un número entre 0 y el número de actividades programadas; explique lo adicional en Acciones complementarias. | |
| El informe no se guarda | "Error al guardar el informe. Por favor, intente nuevamente." o el mensaje del servidor | Falla del servicio o validación del servidor. | Lea el mensaje, corrija y vuelva a hacer clic en **Reportar informe de ejecución**. | |

> 📷 **[CAPTURA MED-06-PLA-27]**: Mensaje ERR-PLA-13
> **Debe mostrar:** La pantalla con el mensaje Botón deshabilitado con "No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe." (serv
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:636`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar un informe ya aprobado

**⚠️ Atención:**
- No existe la opción de eliminar un informe de ejecución (la matriz define el permiso, pero no hay servicio): corríjalo mientras esté pendiente.

#### Actividad 11: Consultar los informes de ejecución de una actividad y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda leer los informes reportados de una actividad, con todos sus campos y su archivo.

**Cuándo se hace y requisitos previos:** Secuencia E5. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Actividades › ⋯ › **Ver detalle** › "Detalle de Actividad" › sección **Informes de ejecución**.

**Qué ve:** Cada informe muestra su estado y: Actividades ejecutadas, Fecha de inicio, Fecha final, Total de días, Actividad implementada ("Acciones desarrolladas en cumplimiento de la recomendación."), Acciones complementarias, Acciones de coordinación, Buenas prácticas, Instrumento de planeación, Resultados, Dificultades y Adjuntos ("Informe.pdf"). Sin informes: "No hay informes de ejecución registrados para esta actividad."

**Pasos:**

##### Paso 11.1: Abrir el detalle de la actividad
**Objetivo del paso:** Llegar a los informes.
**Qué hacer:** Haga clic en ⋯ › **Ver detalle** en la fila de la actividad.
**Resultado esperado:** Ve el detalle de la actividad.

##### Paso 11.2: Leer los informes
**Objetivo del paso:** Conocer lo reportado.
**Qué hacer:** Baje a "Informes de ejecución" y lea cada informe.
**Resultado esperado:** Ve los datos y el estado de cada informe.

##### Paso 11.3: Descargar el PDF
**Objetivo del paso:** Revisar el soporte.
**Qué hacer:** Haga clic en "Informe.pdf".
**Resultado esperado:** Se descarga el archivo; sin archivo: "No hay archivos adjuntos".

> 📷 **[CAPTURA MED-06-PLA-28]**: Informes de ejecución
> **Debe mostrar:** La sección Informes de ejecución del detalle de una actividad
> **Resaltar:** Total de días; Informe.pdf
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:523-795`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Informe Mock
> **Texto alternativo:** Informes de ejecución de una actividad

**Resultado de la actividad:** Conoce los informes de la actividad y su soporte.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

### Módulo 06: Oficios de consumación

**Prerrequisitos:** Módulo 03 (las alertas deben existir).

**Definición del módulo:** Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. Todos los roles los listan, filtran por alerta, consultan y descargan; solo el Super Administrador los carga en 2 pasos (información del oficio y alertas; modificaciones por alerta), los edita y los elimina.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda consultar los oficios de consumación y descargar su PDF.

**Contexto del módulo:** Corresponde al cierre del ciclo (E6.2). Recibe las alertas asociadas y sus municipios; envía el correo "Notificación Oficio de Consumación" a las entidades. También llegan oficios de forma automática. Es visible para todos los roles. Para el usuario de Entidad Territorial (Subdirección): ve solo los asociados a alertas con recomendaciones de su subdirección (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`). En total, tiene 4 de las 8 funcionalidades del módulo; no tiene: cargar un oficio de consumación, modificar municipios y agregar recomendaciones desde el oficio, editar un oficio de consumación, eliminar un oficio de consumación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los oficios de consumación (F-OFI-01) | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Módulo 06: Actividad 1 |
| Buscar y filtrar oficios por alerta (F-OFI-02) | Busca por radicado y filtra por Alerta asociada. | R | Módulo 06: Actividad 1 |
| Ver el detalle de un oficio (F-OFI-03) | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Módulo 06: Actividad 1 |
| Descargar el PDF del oficio (F-OFI-04) | Descarga el archivo del oficio. | Archivo | Módulo 06: Actividad 1 |

#### Actividad 1: Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

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

##### Paso 1.1: Abrir el módulo
**Objetivo del paso:** Ver los oficios.
**Qué hacer:** Haga clic en **Oficios de consumación**.
**Resultado esperado:** Aparece la tabla; sin datos: "No hay oficios de consumación: Los oficios de consumación emitidos por la defensoría aparecerán aquí."

##### Paso 1.2: Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** Abra **Filtros** y elija la Alerta asociada.
**Resultado esperado:** La tabla se filtra.

##### Paso 1.3: Ver el detalle y descargar
**Objetivo del paso:** Leer el oficio.
**Qué hacer:** Haga clic en **Ver detalle** y en **Descargar**.
**Resultado esperado:** Se descarga el PDF.

> 📷 **[CAPTURA MED-06-OFI-01]**: Oficios de consumación
> **Debe mostrar:** La tabla de oficios con el detalle abierto
> **Resaltar:** Alertas asociadas; Archivo PDF
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Oficio Mock
> **Texto alternativo:** Oficios de consumación y su detalle

**Resultado de la actividad:** Conoce los oficios de consumación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de cargar, editar o eliminar oficios | Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios" | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | |
| Los oficios no cargan o no se descargan | "Error al cargar oficios: No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio." | Falla del servicio. | Recargue la página e intente de nuevo. | |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-06-OFI-02]**: Mensaje ERR-OFI-02
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48,107,241,263`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de cargar, editar o eliminar oficios

> 📷 **[CAPTURA MED-06-OFI-03]**: Mensaje ERR-OFI-05
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar oficios: No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/OficiosDeConsumacion.tsx:81-82,194`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los oficios no cargan o no se descargan

**⚠️ Atención:**
- Solo ve los oficios de alertas con recomendaciones de su subdirección.

### Módulo 07: Notificaciones

**Prerrequisitos:** Módulo 01.

**Definición del módulo:** Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda consultar el panel de Notificaciones; reconocer los correos que envía el sistema y qué hacer con cada uno.

**Contexto del módulo:** Acompaña todo el ciclo. Recibe eventos de todos los módulos: cada acción registrada en el historial aparece en el panel, y ciertos eventos generan correo. Los correos de negocio solo llegan a usuarios activos de Entidad Territorial (Central o Subdirección) cuya entidad es principal o asociada; el aprobador designado de un reporte de ejecución recibe su propio correo. No hay mensajes de texto (SMS). Para el usuario de Entidad Territorial (Subdirección): ve el historial de actividad de las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`) (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`). En total, tiene 12 de las 13 funcionalidades del módulo; no tiene: recibir el correo de reporte de ejecución pendiente.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Abrir el panel de Notificaciones (F-NOT-01) | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Módulo 07: Actividad 1 |
| Buscar en el panel de Notificaciones (F-NOT-02) | Filtra el historial por texto. | R | Módulo 07: Actividad 1 |
| Cargar más notificaciones (F-NOT-03) | Trae 10 registros más del historial. | R | Módulo 07: Actividad 1 |
| Recibir el correo de invitación (F-NOT-04) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Módulo 01: Actividad 1; Módulo 07: Actividad 2 |
| Recibir el correo con el código de verificación (F-NOT-05) | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Módulo 01: Actividad 2; Módulo 07: Actividad 2 |
| Recibir el correo de restablecimiento de contraseña (F-NOT-06) | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Módulo 01: Actividad 3; Módulo 07: Actividad 2 |
| Recibir el correo de recomendación asignada (F-NOT-07) | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" a las entidades principal y asociadas. | Automática | Módulo 07: Actividad 2 |
| Recibir el correo de recomendación actualizada (F-NOT-08) | Correo "SI-CIPRAT - Recomendacion Actualizada: {código}". | Automática | Módulo 07: Actividad 2 |
| Recibir el correo de validación del plan de acción (F-NOT-09) | Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" cuando se confirma el plan. | Automática | Módulo 07: Actividad 2 |
| Recibir el recordatorio de informe de ejecución (F-NOT-10) | Correo "Recordatorio vencimiento plazo presentación de informe de ejecución - Alerta Temprana N° {número}" cuando faltan 30 días o menos. | Automática | Módulo 07: Actividad 2 |
| Recibir el correo de informe de seguimiento (F-NOT-11) | Correo "Notificación informe de seguimiento – Alerta Temprana N° {número}". | Automática | Módulo 07: Actividad 2 |
| Recibir el correo de oficio de consumación (F-NOT-12) | Correo "Notificación Oficio de Consumación – Alerta(s) Temprana(s) N° {números} en sistema SI-CIPRAT". | Automática | Módulo 07: Actividad 2 |
| Enviar el recordatorio de informe de ejecución (F-TAR-02, módulo Tareas programadas) | Cada día a las 00:01 envía el recordatorio cuando faltan 30 días o menos para el próximo informe (una vez por ciclo). | Automática | Módulo 07: Actividad 2 |

#### Actividad 1: Consultar el panel de Notificaciones

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Notificaciones** (panel lateral).

**Qué ve:** El panel "Notificaciones" con el buscador "Buscar por nombre" y la lista del historial de actividad de su subdirección: usuario que actuó, acción, alerta y fecha; algunos eventos muestran "Consecutivo:", "Fecha notificacion:" y el enlace "Descargar archivo". Al final, **Mostrar 10 mas**.

**Pasos:**

##### Paso 1.1: Abrir el panel
**Objetivo del paso:** Ver la actividad reciente.
**Qué hacer:** Haga clic en **Notificaciones** en el menú lateral.
**Resultado esperado:** Se abre el panel con los eventos más recientes.

##### Paso 1.2: Buscar un evento
**Objetivo del paso:** Encontrar lo relacionado con una alerta o persona.
**Qué hacer:** Escriba en "Buscar por nombre" (por ejemplo, el número de la alerta).
**Resultado esperado:** La lista se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 1.3: Ver más eventos
**Objetivo del paso:** Revisar eventos anteriores.
**Qué hacer:** Haga clic en **Mostrar 10 mas** al final de la lista.
**Resultado esperado:** Se agregan 10 eventos; al final aparece "No hay mas actividades".

> 📷 **[CAPTURA MED-06-NOT-01]**: Panel Notificaciones
> **Debe mostrar:** El panel abierto con varios eventos de una alerta
> **Resaltar:** Buscador; un evento con usuario, acción y fecha; Mostrar 10 mas
> **Pantalla / ruta:** Panel lateral (`dashboard/src/components/notifications/NotificationsPanel.tsx`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Alerta Mock con historial
> **Texto alternativo:** Panel de notificaciones con el historial de actividad

**Resultado de la actividad:** Conoce lo que pasó en sus alertas, además de los correos que recibe.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el panel sin actividad en su alcance | "No hay notificaciones" | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | |

> 📷 **[CAPTURA MED-06-NOT-02]**: Mensaje ERR-NOT-01
> **Debe mostrar:** La pantalla con el mensaje "No hay notificaciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/notifications/NotificationsPanel.tsx:143`
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el panel sin actividad en su alcance

**⚠️ Atención:**
- El panel no tiene marcas de leído o no leído: muestra el historial de actividad.

#### Actividad 2: Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

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
| "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" | Cuando se crea una recomendación de su entidad (principal o asociada) | Revisar la recomendación y formular sus actividades |
| "SI-CIPRAT - Recomendacion Actualizada: {código}" | Cuando se edita | Revisar el cambio |
| "Notificación validación Plan de Acción – Alerta Temprana N° {número}" | Cuando se confirma el plan | Empezar a reportar informes de ejecución |
| "Recordatorio vencimiento plazo presentación de informe de ejecución - Alerta Temprana N° {número}" | A 30 días o menos del próximo informe | Reportar el informe |
| "Notificación informe de seguimiento – Alerta Temprana N° {número}" | Cuando se carga un informe de seguimiento | Revisar los cambios de la alerta |
| "Notificación Oficio de Consumación – Alerta(s) Temprana(s) N° {números} en sistema SI-CIPRAT" | Cuando se carga un oficio | Consultar el oficio |


**Pasos:**

##### Paso 2.1: Identificar el remitente y el asunto
**Objetivo del paso:** Distinguir los correos del sistema.
**Qué hacer:** Busque en su bandeja los asuntos que empiezan por "SI-CIPRAT" o "Notificación".
**Resultado esperado:** Identifica el tipo de correo según la tabla.

##### Paso 2.2: Abrir el enlace del correo
**Objetivo del paso:** Llegar directamente al registro.
**Qué hacer:** Haga clic en el enlace del correo e inicie sesión si se lo pide.
**Resultado esperado:** Llega a la alerta, a sus recomendaciones o a su detalle.

##### Paso 2.3: Actuar según el correo
**Objetivo del paso:** No dejar vencer los plazos.
**Qué hacer:** Formule las actividades al recibir una recomendación; reporte el informe al recibir la validación del plan y antes del próximo informe.
**Resultado esperado:** Atiende cada aviso en el módulo correspondiente.

> 📷 **[CAPTURA MED-06-NOT-03]**: Correo del sistema
> **Debe mostrar:** Un correo "Nueva Recomendacion Asignada" de prueba con su enlace
> **Resaltar:** Asunto y enlace
> **Pantalla / ruta:** Bandeja de correo (plantillas en `main-api/CipratApi/Servicios/EmailService.cs`)
> **Tomarla con:** Entidad Territorial (Subdirección) · **Datos:** Correo de prueba con datos Mock
> **Texto alternativo:** Ejemplo de correo enviado por SI-CIPRAT

**Resultado de la actividad:** Sabe qué correos esperar y qué hacer con cada uno.

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:288,371,534`. Las respuestas a los correos no vuelven al sistema: la información vuelve cuando la entidad registra actividades o informes en *Planes de acción*.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el enlace del correo de una recomendación en la que su entidad es asociada | La recomendación no aparece en el listado. | Las entidades asociadas reciben el correo, pero solo la Entidad Principal ve la recomendación (riesgo R6). | Coordine con la entidad principal; si su entidad debe responder, pida a la Secretaría Técnica que la registre como principal. | |
| No llegan los correos del sistema | No aparece mensaje. | Falla del envío de correo o usuario inactivo. | Revise la carpeta de correo no deseado y consulte la información directamente en la plataforma. | |
| No llega el recordatorio de informe | No aparece mensaje. | El recordatorio solo se envía una vez por ciclo, a 30 días o menos, y depende de la tarea diaria. | Consulte la columna "Próximo Informe" de sus actividades. | Anote la fecha del próximo informe cuando le aprueben un informe. |

**⚠️ Atención:**
- Los correos de negocio se envían en lotes con copia oculta (CCO).
- No hay mensajes de texto (SMS).

**Ejemplo:** Si el informe aprobado fijó el próximo informe para el 7 de abril de 2026, el recordatorio llega a partir del 8 de marzo de 2026 (30 días antes).

### Módulo 08: Práctica con el caso AT-013-25

**Prerrequisitos:** Haber completado los Módulos 01 a 07 de esta ruta; tener un usuario de prueba con el rol Entidad Territorial (Subdirección) en el ambiente de pruebas y los valores de la línea base de la AT-013-25 o los datos Mock indicados.

**Definición del módulo:** Módulo de práctica guiada que repite, en orden cronológico, cada actividad operativa de la ruta con datos de la alerta AT-013-25 o con datos ficticios (Mock) cuando el dato real no está disponible o no está autorizado.

**Objetivo del módulo:** Que el usuario de Entidad Territorial (Subdirección) pueda ejecutar en un ambiente de pruebas todas las actividades de su ruta con datos de la AT-013-25 o datos Mock.

**Contexto del módulo:** Los valores de la práctica salen de la línea base de la AT-013-25 (Riesgo Electoral Nacional 2025-2026) [DATO REAL AT-013-25]: alerta notificada el 07/10/2025, tipo Estructural, etiqueta Regional, 41 recomendaciones (RC-001-2025-013 a RC-041-2025-013) y un plan de mitigación **parcial**: 20 actividades de 5 recomendaciones (RC-003, RC-004, RC-021, RC-022 y RC-023). En el sistema la alerta se escribe AT-013-2025, porque el número exige año de 4 dígitos. Lo que la línea base no trae (las actividades de las otras recomendaciones y los informes de ejecución) se practica con datos Mock (pendiente: plan de mitigación no disponible). Antes de usar datos reales en una sesión, el Ministerio debe autorizarlos (ver `usos_datos_reales.csv`).

**Funcionalidades disponibles:** las mismas de los módulos anteriores de esta ruta, en el ambiente de pruebas.

#### Actividad 1: Práctica: Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

**Cuándo se hace y requisitos previos:** Secuencia E0; los mismos requisitos de Módulo 01: Actividad 4.

**Dónde:** Menú lateral › parte inferior, nombre del usuario › **Cerrar sesión**.

**Datos de la práctica:** Sesión abierta del usuario de prueba.

**Pasos:**

##### Paso 1.1: Abrir el menú del usuario
**Objetivo del paso:** Encontrar la opción de salida.
**Qué hacer:** En el ambiente de pruebas: Haga clic en su nombre, al pie del menú lateral.
**Resultado esperado:** Se despliegan **Ver Perfil** y **Cerrar sesión**.

##### Paso 1.2: Cerrar la sesión
**Objetivo del paso:** Terminar la sesión cuando deja de trabajar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar sesión**.
**Resultado esperado:** Vuelve a la pantalla de ingreso.

##### Paso 1.3: Reconocer el cierre automático
**Objetivo del paso:** Saber qué hacer cuando el sistema cierra la sesión.
**Qué hacer:** En el ambiente de pruebas: Si deja la plataforma sin uso 60 minutos, o la sesión vence a las 12 horas, lea el aviso y vuelva a iniciar sesión.
**Resultado esperado:** Aparece "Sesión cerrada por inactividad" o "Sesión expirada" y la pantalla de ingreso.

**Resultado esperado de la práctica:** La sesión termina; los datos no guardados de un formulario abierto se pierden.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La sesión termina; los datos no guardados de un formulario abierto se pierden.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 4 y lo resolvió.

#### Actividad 2: Práctica: Consultar los Términos de uso y contactar al soporte técnico

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

**Cuándo se hace y requisitos previos:** Secuencia E0; los mismos requisitos de Módulo 01: Actividad 5.

**Dónde:** Pie de página › **Términos de uso** (`/terminos-de-uso`); pantallas de acceso › **¿Necesita soporte técnico?**.

**Datos de la práctica:** No requiere datos.

**Pasos:**

##### Paso 2.1: Abrir los Términos de uso
**Objetivo del paso:** Conocer sus obligaciones como usuario.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Términos de uso** al pie de la página.
**Resultado esperado:** Se abre la página de términos y condiciones.

##### Paso 2.2: Revisar las condiciones técnicas
**Objetivo del paso:** Saber qué necesita para usar la plataforma.
**Qué hacer:** En el ambiente de pruebas: Lea el numeral "4. Condiciones técnicas de acceso y uso".
**Resultado esperado:** Identifica: conexión estable, navegadores Chrome, Firefox o Edge actualizados y credenciales personales e intransferibles.

##### Paso 2.3: Escribir al soporte
**Objetivo del paso:** Pedir ayuda técnica.
**Qué hacer:** En el ambiente de pruebas: En las pantallas de acceso haga clic en **¿Necesita soporte técnico?**: se abre un correo a siciprat@mininterior.gov.co. Escriba qué hacía, la pantalla, la hora y adjunte una captura del mensaje.
**Resultado esperado:** Su programa de correo abre un mensaje nuevo dirigido al soporte.

**Resultado esperado de la práctica:** Conoce las condiciones de uso y el canal de soporte.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce las condiciones de uso y el canal de soporte.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 5 y lo resolvió.

#### Actividad 3: Práctica: Navegar con el menú lateral y usar el panel de accesibilidad

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 02: Actividad 3.

**Dónde:** Menú lateral; botón **Accesibilidad** (panel "Panel de accesibilidad").

**Datos de la práctica:** No requiere datos.

**Pasos:**

##### Paso 3.1: Recorrer el menú
**Objetivo del paso:** Conocer los módulos de su rol.
**Qué hacer:** En el ambiente de pruebas: Haga clic en cada opción del menú lateral.
**Resultado esperado:** Se abre cada pantalla; las rutas de navegación ("migas de pan") muestran dónde está.

##### Paso 3.2: Ocultar y mostrar el menú
**Objetivo del paso:** Ganar espacio en pantalla.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ocultar** al pie del menú; para volver a verlo, use el botón de abrir menú.
**Resultado esperado:** El menú se contrae o se expande.

##### Paso 3.3: Ajustar la accesibilidad
**Objetivo del paso:** Leer mejor la información.
**Qué hacer:** En el ambiente de pruebas: Abra el panel de accesibilidad y use "Activar alto contraste", "Aumentar tamaño de letra" o "Reducir tamaño de letra".
**Resultado esperado:** La pantalla cambia de contraste o de tamaño de letra.

**Resultado esperado de la práctica:** Navega con soltura por los módulos de su rol.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Navega con soltura por los módulos de su rol.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02: Actividad 3 y lo resolvió.

#### Actividad 4: Práctica: Consultar el panel de Notificaciones

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 07: Actividad 1.

**Dónde:** Menú lateral › **Notificaciones** (panel lateral).

**Datos de la práctica:** Buscar "AT-013" en el panel [DATO REAL AT-013-25].

**Pasos:**

##### Paso 4.1: Abrir el panel
**Objetivo del paso:** Ver la actividad reciente.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Notificaciones** en el menú lateral.
**Resultado esperado:** Se abre el panel con los eventos más recientes.

##### Paso 4.2: Buscar un evento
**Objetivo del paso:** Encontrar lo relacionado con una alerta o persona.
**Qué hacer:** En el ambiente de pruebas: Escriba en "Buscar por nombre" (por ejemplo, el número de la alerta).
**Resultado esperado:** La lista se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 4.3: Ver más eventos
**Objetivo del paso:** Revisar eventos anteriores.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Mostrar 10 mas** al final de la lista.
**Resultado esperado:** Se agregan 10 eventos; al final aparece "No hay mas actividades".

**Resultado esperado de la práctica:** Conoce lo que pasó en sus alertas, además de los correos que recibe.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce lo que pasó en sus alertas, además de los correos que recibe.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 07: Actividad 1 y lo resolvió.

#### Actividad 5: Práctica: Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 07: Actividad 2.

**Dónde:** Su bandeja de correo; los enlaces de los correos llevan a la plataforma.

**Datos de la práctica:** Correos generados en el ambiente de pruebas.

**Pasos:**

##### Paso 5.1: Identificar el remitente y el asunto
**Objetivo del paso:** Distinguir los correos del sistema.
**Qué hacer:** En el ambiente de pruebas: Busque en su bandeja los asuntos que empiezan por "SI-CIPRAT" o "Notificación".
**Resultado esperado:** Identifica el tipo de correo según la tabla.

##### Paso 5.2: Abrir el enlace del correo
**Objetivo del paso:** Llegar directamente al registro.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el enlace del correo e inicie sesión si se lo pide.
**Resultado esperado:** Llega a la alerta, a sus recomendaciones o a su detalle.

##### Paso 5.3: Actuar según el correo
**Objetivo del paso:** No dejar vencer los plazos.
**Qué hacer:** En el ambiente de pruebas: Formule las actividades al recibir una recomendación; reporte el informe al recibir la validación del plan y antes del próximo informe.
**Resultado esperado:** Atiende cada aviso en el módulo correspondiente.

**Resultado esperado de la práctica:** Sabe qué correos esperar y qué hacer con cada uno.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué correos esperar y qué hacer con cada uno.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 07: Actividad 2 y lo resolvió.

#### Actividad 6: Práctica: Activar la cuenta desde la invitación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

**Cuándo se hace y requisitos previos:** Secuencia E0.3; los mismos requisitos de Módulo 01: Actividad 1.

**Dónde:** Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" › enlace › pantalla "Configura tu contraseña" (`/setup/:token`).

**Datos de la práctica:** Invitación de prueba enviada al correo del participante (Mock).

**Pasos:**

##### Paso 6.1: Abrir el enlace de la invitación
**Objetivo del paso:** Llegar a la pantalla de activación con un enlace válido.
**Qué hacer:** En el ambiente de pruebas: Abra el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" y haga clic en el enlace. Hágalo antes de 7 días desde el envío.
**Resultado esperado:** Se abre "Configura tu contraseña". Si el enlace venció, aparece "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."

##### Paso 6.2: Escribir la nueva contraseña
**Objetivo del paso:** Crear una contraseña que cumpla las reglas de seguridad.
**Qué hacer:** En el ambiente de pruebas: En **Nueva Contraseña** escriba al menos 8 caracteres e incluya un carácter especial (por ejemplo, # o !). Use el ícono del ojo para verificar lo escrito.
**Resultado esperado:** Los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial" se marcan como cumplidos.

##### Paso 6.3: Confirmar la contraseña
**Objetivo del paso:** Evitar errores de digitación.
**Qué hacer:** En el ambiente de pruebas: En **Confirmar Contraseña** escriba exactamente la misma contraseña.
**Resultado esperado:** Si no coinciden, al enviar aparece "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."

##### Paso 6.4: Activar la cuenta
**Objetivo del paso:** Dejar la cuenta en estado Activo.
**Qué hacer:** En el ambiente de pruebas: Revise que los dos campos coincidan y haga clic en **Activar cuenta**.
**Resultado esperado:** El botón muestra "Activando cuenta..." y luego la pantalla confirma; la cuenta queda Activa y puede iniciar sesión.

**Resultado esperado de la práctica:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 1 y lo resolvió.

#### Actividad 7: Práctica: Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01: Actividad 2.

**Dónde:** Dirección de la plataforma › **Iniciar sesión** (`/signin`) › "Inicia sesión en tu cuenta".

**Datos de la práctica:** Usuario de prueba de la ruta (entidad.subdireccion.prueba@ejemplo.gov.co).

**Pasos:**

##### Paso 7.1: Abrir la pantalla de ingreso
**Objetivo del paso:** Llegar al formulario de inicio de sesión.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de SI-CIPRAT en Chrome, Firefox o Edge actualizados y haga clic en **Iniciar sesión** (o abra directamente `/signin`).
**Resultado esperado:** Aparece "Inicia sesión en tu cuenta".

##### Paso 7.2: Escribir correo y contraseña
**Objetivo del paso:** Identificarse ante el sistema.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional (el mismo de la invitación). En **Contraseña** escriba su contraseña.
**Resultado esperado:** Los campos quedan diligenciados. Si están vacíos, la pantalla muestra "Email is required" o "Password is required".

##### Paso 7.3: Solicitar el código
**Objetivo del paso:** Validar credenciales y recibir el código de verificación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Iniciar Sesión**.
**Resultado esperado:** El botón muestra "Iniciando sesión..." y aparece "Revisa tu correo electrónico". Llega el correo "SI-CIPRAT - Código de Verificación". Si las credenciales no son correctas: "Credenciales inválidas".

##### Paso 7.4: Escribir el código de 4 dígitos
**Objetivo del paso:** Comprobar que quien ingresa tiene acceso al correo.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y escriba los 4 dígitos, uno en cada casilla (solo acepta números; puede pegarlos). Si no llegó, espere un minuto, revise el correo no deseado y haga clic en **Haz clic para reenviar**.
**Resultado esperado:** Las 4 casillas quedan llenas.

##### Paso 7.5: Validar el código
**Objetivo del paso:** Abrir la sesión.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Validar código**.
**Resultado esperado:** Entra a **Inicio** con el menú lateral de su rol. Si el código no coincide: "Código de autenticación inválido"; si pasó más de 1 hora: "Código expirado".

**Resultado esperado de la práctica:** Sesión abierta con el rol el usuario de Entidad Territorial (Subdirección) y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sesión abierta con el rol el usuario de Entidad Territorial (Subdirección) y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 2 y lo resolvió.

#### Actividad 8: Práctica: Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01: Actividad 6.

**Dónde:** Menú lateral › nombre del usuario › **Ver Perfil** (`/mi-perfil`).

**Datos de la práctica:** Usuario de prueba configurado con el alcance de la ruta.

**Pasos:**

##### Paso 8.1: Abrir Mi perfil
**Objetivo del paso:** Llegar a la pantalla de datos de la cuenta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en su nombre al pie del menú lateral y luego en **Ver Perfil**.
**Resultado esperado:** Se abre Mi perfil con "Cargando perfil..." y luego sus datos.

##### Paso 8.2: Revisar Información General
**Objetivo del paso:** Confirmar los datos personales registrados.
**Qué hacer:** En el ambiente de pruebas: Lea Nombres, Apellidos, Cargo, Área y Correo electrónico.
**Resultado esperado:** Los datos coinciden con los suyos; los campos no se pueden editar.

##### Paso 8.3: Revisar Entidad y Acceso y Asignaciones
**Objetivo del paso:** Confirmar el alcance de datos.
**Qué hacer:** En el ambiente de pruebas: Verifique que el Rol corresponda a Entidad Territorial, que el **Nivel de Acceso** sea Subdirección y que **Entidad Central** y **Subdirección** sean las suyas.
**Resultado esperado:** Confirma que verá las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección.

**Resultado esperado de la práctica:** Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 6 y lo resolvió.

#### Actividad 9: Práctica: Recuperar la contraseña

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.6; los mismos requisitos de Módulo 01: Actividad 3.

**Dónde:** Pantalla de ingreso › **¿Has olvidado tu contraseña?** (`/forgot-password`) › correo "SI-CIPRAT - Restablecer Contraseña" › "Configurar nueva contraseña" (`/reset-password/:token`).

**Datos de la práctica:** Usuario de prueba entidad.subdireccion.prueba@ejemplo.gov.co; contraseña nueva "Nueva#2026" (Mock).

**Pasos:**

##### Paso 9.1: Abrir la recuperación
**Objetivo del paso:** Iniciar el proceso de cambio de contraseña.
**Qué hacer:** En el ambiente de pruebas: En la pantalla de ingreso haga clic en **¿Has olvidado tu contraseña?**.
**Resultado esperado:** Aparece "¿Olvidaste tu contraseña?".

##### Paso 9.2: Escribir el correo
**Objetivo del paso:** Indicar a qué cuenta se enviará el enlace.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional y haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Revisa tu correo electrónico" y llega el correo "SI-CIPRAT - Restablecer Contraseña".

##### Paso 9.3: Abrir el enlace del correo
**Objetivo del paso:** Llegar a la pantalla de nueva contraseña antes de que venza.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y haga clic en el enlace dentro de la hora siguiente.
**Resultado esperado:** Aparece "Configurar nueva contraseña". Si pasó más de 1 hora, al guardar aparece "Token inválido o expirado".

##### Paso 9.4: Escribir y confirmar la nueva contraseña
**Objetivo del paso:** Definir una contraseña válida y distinta de las anteriores.
**Qué hacer:** En el ambiente de pruebas: Escriba en **Nueva Contraseña** al menos 8 caracteres con un carácter especial, distinta de sus últimas 5 contraseñas, y repítala en **Confirmar Contraseña**.
**Resultado esperado:** Los indicadores se marcan como cumplidos.

##### Paso 9.5: Guardar la contraseña
**Objetivo del paso:** Dejar activa la nueva contraseña.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Contraseña restablecida: Tu contraseña se ha restablecido correctamente. Haz clic abajo para iniciar sesión." con el botón **Iniciar Sesión**.

**Resultado esperado de la práctica:** La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01: Actividad 3 y lo resolvió.

#### Actividad 10: Práctica: Leer los indicadores del Inicio

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02: Actividad 1.

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25] y alertas Mock.

**Pasos:**

##### Paso 10.1: Abrir Inicio
**Objetivo del paso:** Ver el tablero de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inicio** en el menú lateral.
**Resultado esperado:** Aparecen las tarjetas, el avance global, el ranking y el mapa.

##### Paso 10.2: Leer las tarjetas y su tendencia
**Objetivo del paso:** Saber cuántas alertas hay y cómo cambió el último mes.
**Qué hacer:** En el ambiente de pruebas: Lea el valor grande de cada tarjeta y el número "vs ultimo mes".
**Resultado esperado:** Identifica, por ejemplo, que hay 2 alertas activas más que el mes anterior.

##### Paso 10.3: Interpretar el Porcentaje de Avance Global
**Objetivo del paso:** Entender el avance de los planes de acción.
**Qué hacer:** En el ambiente de pruebas: Lea el porcentaje y la línea "X de Y actividades ejecutadas". Recuerde que es un promedio por alerta y no la división del total.
**Resultado esperado:** Puede explicar por qué el porcentaje puede ser distinto de X/Y.

**Resultado esperado de la práctica:** Interpreta el estado general de las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Interpreta el estado general de las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02: Actividad 1 y lo resolvió.

#### Actividad 11: Práctica: Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02: Actividad 2.

**Dónde:** Menú lateral › **Inicio**.

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 11.1: Abrir la última alerta
**Objetivo del paso:** Conocer la alerta activa más reciente.
**Qué hacer:** En el ambiente de pruebas: Lea el banner superior y haga clic en **Ver Alerta**.
**Resultado esperado:** Se abre la alerta en *Alertas tempranas*.

##### Paso 11.2: Revisar el ranking de departamentos
**Objetivo del paso:** Saber dónde se concentran las alertas.
**Qué hacer:** En el ambiente de pruebas: Lea "Alertas por departamento" (Top 10).
**Resultado esperado:** Identifica los departamentos con más alertas y su porcentaje.

##### Paso 11.3: Revisar las alertas recientes
**Objetivo del paso:** Ver lo último registrado.
**Qué hacer:** En el ambiente de pruebas: Recorra "Alertas recientes".
**Resultado esperado:** Ve las últimas alertas por fecha de la alerta.

##### Paso 11.4: Usar el mapa
**Objetivo del paso:** Ubicar los municipios con alertas.
**Qué hacer:** En el ambiente de pruebas: Pase el cursor sobre un municipio coloreado; use la tabla accesible si prefiere leer los datos.
**Resultado esperado:** Aparece el nombre del municipio, el departamento y el número de alertas.

**Resultado esperado de la práctica:** Ubica geográficamente las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica geográficamente las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02: Actividad 2 y lo resolvió.

#### Actividad 12: Práctica: Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02: Actividad 4.

**Dónde:** Dirección principal de SI-CIPRAT (`/`), sin iniciar sesión.

**Datos de la práctica:** Ventana privada del navegador.

**Pasos:**

##### Paso 12.1: Abrir la vista pública
**Objetivo del paso:** Ver lo que ve la ciudadanía.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de la plataforma sin iniciar sesión (o en una ventana privada).
**Resultado esperado:** Aparece el tablero público con el botón **Iniciar sesión**.

##### Paso 12.2: Comparar con su vista
**Objetivo del paso:** Entender la diferencia de alcance.
**Qué hacer:** En el ambiente de pruebas: Compare los totales con los de su Inicio con sesión, que se calculan sobre su subdirección.
**Resultado esperado:** Los totales públicos son nacionales y pueden ser mayores que los de su vista.

**Resultado esperado de la práctica:** Sabe qué información es pública y cuál depende de su sesión.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué información es pública y cuál depende de su sesión.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02: Actividad 4 y lo resolvió.

#### Actividad 13: Práctica: Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03: Actividad 1.

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Datos de la práctica:** Buscar "AT-013" [DATO REAL AT-013-25].

**Pasos:**

##### Paso 13.1: Abrir Alertas tempranas
**Objetivo del paso:** Ver las alertas de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Alertas tempranas** en el menú lateral.
**Resultado esperado:** Aparecen "Cargando alertas..." y luego las tarjetas y la tabla.

##### Paso 13.2: Leer las tarjetas
**Objetivo del paso:** Conocer los totales.
**Qué hacer:** En el ambiente de pruebas: Lea Total de alertas, Alertas activas y Alertas cerradas.
**Resultado esperado:** Conoce cuántas alertas hay en cada estado.

##### Paso 13.3: Cambiar de pestaña
**Objetivo del paso:** Separar por tipo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inminencia** o **Estructurales**; **Todas** quita el filtro.
**Resultado esperado:** La tabla muestra solo ese tipo.

##### Paso 13.4: Buscar una alerta
**Objetivo del paso:** Ir directo a una alerta.
**Qué hacer:** En el ambiente de pruebas: Escriba el número (por ejemplo "AT-013") o una palabra del tema en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; sin coincidencias: "No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo."

##### Paso 13.5: Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Tipo, Estado, Etiqueta y las listas del conflicto, y haga clic en **Aplicar filtros**. Para quitar, **Limpiar filtros**.
**Resultado esperado:** El botón Filtros muestra cuántos filtros están activos y la tabla se actualiza.

##### Paso 13.6: Abrir el menú de acciones
**Objetivo del paso:** Saber qué puede hacer con cada alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ al final de la fila.
**Resultado esperado:** Aparecen Detalle, Recomendaciones e Historial de actividades; Editar y Eliminar están deshabilitados ("No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas").

**Resultado esperado de la práctica:** Ubica la alerta y sus datos principales.

**Lista de verificación:**
- [ ] Completó los 6 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica la alerta y sus datos principales.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03: Actividad 1 y lo resolvió.

#### Actividad 14: Práctica: Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03: Actividad 2.

**Dónde:** Alertas tempranas › fila › ⋯ › **Detalle**.

**Datos de la práctica:** Abrir la AT-013-2025 y revisar GUAVIARE › Miraflores (95200) [DATO REAL AT-013-25].

**Pasos:**

##### Paso 14.1: Abrir el detalle
**Objetivo del paso:** Ver la ficha completa.
**Qué hacer:** En el ambiente de pruebas: En la fila, haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ficha en la pestaña Información general.

##### Paso 14.2: Revisar Información general
**Objetivo del paso:** Conocer el avance y el tema.
**Qué hacer:** En el ambiente de pruebas: Lea Ejecutado / Programado, el estado del Plan de acción y la Descripción.
**Resultado esperado:** Conoce el avance y el estado del plan.

##### Paso 14.3: Descargar el PDF
**Objetivo del paso:** Consultar el documento oficial.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el archivo de "PDF de la alerta".
**Resultado esperado:** Se descarga el PDF. Si no hay archivo, la alerta no tiene PDF cargado.

##### Paso 14.4: Recorrer las demás pestañas
**Objetivo del paso:** Conocer el territorio, el conflicto y la población.
**Qué hacer:** En el ambiente de pruebas: Abra Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas.
**Resultado esperado:** Ve los municipios (con CAT, PNIS, PDET y Zona Fut.), los grupos armados, las conductas, las poblaciones y las subsunciones.

##### Paso 14.5: Cerrar la ficha
**Objetivo del paso:** Volver al listado.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar**.
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Conoce la alerta completa.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la alerta completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03: Actividad 2 y lo resolvió.

#### Actividad 15: Práctica: Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03: Actividad 3.

**Dónde:** Alertas tempranas › fila › ⋯ › **Historial de actividades**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 15.1: Abrir el historial
**Objetivo del paso:** Ver la trazabilidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Historial de actividades**.
**Resultado esperado:** Se abre la línea de tiempo de la alerta.

##### Paso 15.2: Leer los eventos
**Objetivo del paso:** Reconstruir lo ocurrido.
**Qué hacer:** En el ambiente de pruebas: Recorra los eventos y use **Mostrar 10 mas** para ver los anteriores.
**Resultado esperado:** Identifica, por ejemplo, cuándo se confirmó el plan y quién lo hizo.

##### Paso 15.3: Descargar un archivo del evento
**Objetivo del paso:** Ver el soporte de un cierre o informe.
**Qué hacer:** En el ambiente de pruebas: Si el evento tiene "Descargar archivo", haga clic.
**Resultado esperado:** Se descarga el archivo asociado.

**Resultado esperado de la práctica:** Conoce la trazabilidad de la alerta.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la trazabilidad de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03: Actividad 3 y lo resolvió.

#### Actividad 16: Práctica: Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 03: Actividad 4.

**Dónde:** Alertas tempranas › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 16.1: Aplicar los filtros que necesita
**Objetivo del paso:** Descargar solo lo útil.
**Qué hacer:** En el ambiente de pruebas: Use la pestaña, el buscador y **Filtros**.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 16.2: Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; ábralo en Excel.

**Resultado esperado de la práctica:** Tiene el listado en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene el listado en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03: Actividad 4 y lo resolvió.

#### Actividad 17: Práctica: Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2; los mismos requisitos de Módulo 03: Actividad 5.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 17.1: Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 17.2: Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** En el ambiente de pruebas: Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Llega a las recomendaciones de la alerta.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Llega a las recomendaciones de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03: Actividad 5 y lo resolvió.

#### Actividad 18: Práctica: Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04: Actividad 1.

**Dónde:** Alertas tempranas › ⋯ › **Recomendaciones**.

**Datos de la práctica:** Recomendaciones de la AT-013-2025: RC-001-2025-013 a RC-041-2025-013 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 18.1: Abrir las recomendaciones
**Objetivo del paso:** Ver la lista.
**Qué hacer:** En el ambiente de pruebas: Desde la alerta, ⋯ › **Recomendaciones**.
**Resultado esperado:** Aparece "Cargando recomendaciones..." y luego la tabla.

##### Paso 18.2: Buscar
**Objetivo del paso:** Encontrar una recomendación.
**Qué hacer:** En el ambiente de pruebas: Escriba el código (por ejemplo "RC-001") o una palabra en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra.

##### Paso 18.3: Filtrar
**Objetivo del paso:** Ver por entidad, eje o modo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Entidad Principal, Eje Temático o Modo de Creación y **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo lo filtrado.

##### Paso 18.4: Leer el avance
**Objetivo del paso:** Saber cómo va cada recomendación.
**Qué hacer:** En el ambiente de pruebas: Lea Actividades (Aprobadas / Total) y Ejecución.
**Resultado esperado:** Identifica las recomendaciones sin actividades o con bajo cumplimiento.

**Resultado esperado de la práctica:** Conoce las recomendaciones de la alerta y su avance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce las recomendaciones de la alerta y su avance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04: Actividad 1 y lo resolvió.

#### Actividad 19: Práctica: Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04: Actividad 2.

**Dónde:** Recomendaciones › fila › ⋯ › **Detalle**.

**Datos de la práctica:** RC-011-2025-013 ("Recomendación No. 12…") [DATO REAL AT-013-25].

**Pasos:**

##### Paso 19.1: Abrir el detalle
**Objetivo del paso:** Ver la recomendación completa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ventana.

##### Paso 19.2: Leer las entidades
**Objetivo del paso:** Saber quién responde y quién apoya.
**Qué hacer:** En el ambiente de pruebas: Lea la Entidad principal y las Entidades asociadas.
**Resultado esperado:** Identifica a la entidad responsable del plan y a las que apoyan.

**Resultado esperado de la práctica:** Conoce la recomendación completa.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la recomendación completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04: Actividad 2 y lo resolvió.

#### Actividad 20: Práctica: Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, descargar las recomendaciones visibles en un archivo CSV.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 04: Actividad 3.

**Dónde:** Recomendaciones › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 20.1: Filtrar
**Objetivo del paso:** Descargar lo necesario.
**Qué hacer:** En el ambiente de pruebas: Aplique búsqueda y filtros.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 20.2: Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; si falla: "Error al descargar el archivo CSV. Por favor, intente nuevamente."

**Resultado esperado de la práctica:** Tiene las recomendaciones en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene las recomendaciones en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04: Actividad 3 y lo resolvió.

#### Actividad 21: Práctica: Consultar y filtrar los planes de acción por alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 05: Actividad 1.

**Dónde:** Menú lateral › **Planes de acción** (`/planes-de-accion`) › pestaña **Alertas**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 21.1: Abrir Planes de acción
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Planes de acción**.
**Resultado esperado:** Aparece la pestaña **Alertas**.

##### Paso 21.2: Leer el estado y el cumplimiento
**Objetivo del paso:** Saber qué plan está pendiente o aprobado.
**Qué hacer:** En el ambiente de pruebas: Lea las columnas Cumplimiento, Plan de acción e Informe.
**Resultado esperado:** Identifica, por ejemplo, los planes "Sin plan" que aún no tienen actividades.

##### Paso 21.3: Filtrar
**Objetivo del paso:** Ver solo lo que le interesa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Estado del Plan de Acción, Estado del Informe o Porcentaje de Cumplimiento y **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 21.4: Ver el detalle del plan
**Objetivo del paso:** Revisar la información de la alerta y el historial del plan.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono de detalle de la fila.
**Resultado esperado:** Se abre la ficha con "Información de alerta" e "Historial Plan de acción".

##### Paso 21.5: Descargar el listado
**Objetivo del paso:** Tener el estado en un archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga un CSV con Número de Alerta, Cumplimiento (%) y Plan de Acción.

**Resultado esperado de la práctica:** Conoce el estado de los planes de su alcance.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el estado de los planes de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 1 y lo resolvió.

#### Actividad 22: Práctica: Recorrer las recomendaciones del plan de una alerta

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 05: Actividad 2.

**Dónde:** Planes de acción › fila › **Ir al plan de acción** (`/planes-de-accion/:id/recomendaciones`).

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 22.1: Entrar al plan
**Objetivo del paso:** Ver las recomendaciones de la alerta.
**Qué hacer:** En el ambiente de pruebas: En la fila de la alerta haga clic en **Ir al plan de acción**.
**Resultado esperado:** Aparece la tabla de recomendaciones.

##### Paso 22.2: Abrir el detalle de una recomendación
**Objetivo del paso:** Ver su información y su historial.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono de detalle y recorra **Información**, **Actividades** e **Historial**.
**Resultado esperado:** Ve la recomendación, sus actividades y los eventos del plan.

##### Paso 22.3: Ir a las actividades
**Objetivo del paso:** Trabajar las actividades de la recomendación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver Actividades**.
**Resultado esperado:** Se abre la lista de actividades de la recomendación.

**Resultado esperado de la práctica:** Llega a las actividades de la recomendación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Llega a las actividades de la recomendación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 2 y lo resolvió.

#### Actividad 23: Práctica: Consultar las pestañas globales de Recomendaciones y Actividades

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 05: Actividad 3.

**Dónde:** Planes de acción › pestañas **Recomendaciones** y **Actividades**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 23.1: Abrir Recomendaciones
**Objetivo del paso:** Ver todas las recomendaciones.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la pestaña **Recomendaciones**.
**Resultado esperado:** Aparece la tabla global.

##### Paso 23.2: Abrir Actividades
**Objetivo del paso:** Ver todas las actividades.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la pestaña **Actividades**.
**Resultado esperado:** Aparece la tabla global de actividades.

##### Paso 23.3: Filtrar y descargar
**Objetivo del paso:** Obtener un listado específico.
**Qué hacer:** En el ambiente de pruebas: Use **Filtros** (por ejemplo, Estado "Pendiente Aprobación") y luego **Descargar**.
**Resultado esperado:** Se descarga el CSV filtrado.

**Resultado esperado de la práctica:** Tiene la vista global de su alcance.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene la vista global de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 3 y lo resolvió.

#### Actividad 24: Práctica: Consultar las actividades de una recomendación y su detalle

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, leer cada actividad de una recomendación, su estado, su avance y su próximo informe.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 05: Actividad 4.

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** (`/planes-de-accion/:id/recomendaciones/:recomendacionId/actividades`); el detalle, en el menú ⋯ › **Ver detalle**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 24.1: Abrir las actividades
**Objetivo del paso:** Ver la lista.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver Actividades** de la recomendación.
**Resultado esperado:** Aparece "Cargando actividades..." y luego la tabla.

##### Paso 24.2: Buscar y filtrar
**Objetivo del paso:** Encontrar una actividad.
**Qué hacer:** En el ambiente de pruebas: Escriba en "Buscar por objetivo" o use **Filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 24.3: Ver el detalle
**Objetivo del paso:** Leer la actividad completa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Ver detalle** en la fila de la actividad.
**Resultado esperado:** Ve el detalle de la actividad; con varias actividades puede cambiar con "Seleccionar actividad".

##### Paso 24.4: Descargar
**Objetivo del paso:** Tener las actividades en un archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV de actividades.

**Resultado esperado de la práctica:** Conoce el detalle y el avance de las actividades.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el detalle y el avance de las actividades.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 4 y lo resolvió.

#### Actividad 25: Práctica: Agregar una actividad al plan de acción

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, formular una actividad del plan de acción para una recomendación de su entidad, con objetivo, meta por semestre, plazo, instrumento y recursos.

**Cuándo se hace y requisitos previos:** Secuencia E3.2; los mismos requisitos de Módulo 05: Actividad 5.

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** › **Agregar actividad** › ventana "Agregar actividad: Registrar una nueva actividad asociada a la recomendación, indicando la información básica necesaria para su ejecución.".

**Datos de la práctica:** Con un usuario de prueba de la subdirección "MinInterior - Democracia y Participación", en RC-022-2025-013 agregue AC-022-01: Objetivo "Optimizar la gestión institucional del Ministerio del Interior en el marco de los procesos electorales de 2025–2026."; Actividad "Incluir en el informe poselectoral (Decreto 0800 de 2025) un seguimiento previo, durante y después de los comicios, con información sobre comisiones…"; Número de actividades 1; Plazo de implementación "1 a 3 meses" (en la línea base dice "0-3 meses", valor que la pantalla no ofrece); Instrumento de planeación vacío en la línea base: la pantalla exige Sí o No ("Debe seleccionar una opción"); para la práctica elija "Sí" y anote que la entidad debe confirmarlo; Recursos "Sí" (texto completo en `data/03_plan_mitigacion.json`, AC-022-01) [DATO REAL AT-013-25].

**Pasos:**

##### Paso 25.1: Abrir el formulario
**Objetivo del paso:** Iniciar la formulación.
**Qué hacer:** En el ambiente de pruebas: En las actividades de la recomendación haga clic en **Agregar actividad**.
**Resultado esperado:** Se abre el Paso 1 con la recomendación ("{código} - {nombre}"). Si el plan ya estaba confirmado, aparece primero la advertencia "Agregar actividad a plan confirmado" (actividad siguiente).

##### Paso 25.2: Escribir el Objetivo
**Objetivo del paso:** Decir para qué se hace la actividad.
**Qué hacer:** En el ambiente de pruebas: En **Objetivo** escriba el propósito que busca la actividad frente al riesgo.
**Resultado esperado:** Sin objetivo: "El objetivo es requerido".

##### Paso 25.3: Avanzar al Paso 2
**Objetivo del paso:** Pasar a la información de la actividad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Siguiente**.
**Resultado esperado:** Aparece el Paso 2.

##### Paso 25.4: Escribir la Actividad
**Objetivo del paso:** Describir lo que se va a hacer.
**Qué hacer:** En el ambiente de pruebas: En **Actividad** describa en futuro lo que hará la entidad (no lo que ya hizo: eso va en el informe de ejecución).
**Resultado esperado:** Sin texto: "La descripción de la actividad es requerida".

##### Paso 25.5: Definir el Número de actividades
**Objetivo del paso:** Fijar la meta por semestre.
**Qué hacer:** En el ambiente de pruebas: En **Número de actividades** escriba un entero mayor que 0: es la meta de cada ciclo de 6 meses ("Número de veces que se ejecutará la actividad.").
**Resultado esperado:** Con 0: "El número de actividades debe ser mayor a 0".

##### Paso 25.6: Elegir el Plazo de implementación
**Objetivo del paso:** Indicar la duración prevista.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Plazo de implementación** y elija 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente.
**Resultado esperado:** El plazo queda seleccionado (es informativo: no genera vencimientos).

##### Paso 25.7: Responder Instrumento de planeación y Recursos
**Objetivo del paso:** Indicar si la actividad está planeada y financiada.
**Qué hacer:** En el ambiente de pruebas: En **Instrumento de planeación** ("¿La actividad está relacionada en algún instrumento de planeación?") y en **Recursos** ("¿La entidad cuenta con recursos o capacidades para implementar las actividades?") elija Sí o No.
**Resultado esperado:** Sin respuesta: "Debe seleccionar una opción".

##### Paso 25.8: Escribir Observaciones (opcional)
**Objetivo del paso:** Dejar información adicional.
**Qué hacer:** En el ambiente de pruebas: En **Observaciones** escriba lo que considere necesario.
**Resultado esperado:** El texto queda registrado.

##### Paso 25.9: Revisar y guardar
**Objetivo del paso:** Registrar la actividad.
**Qué hacer:** En el ambiente de pruebas: Revise con **Atrás** y haga clic en **Reportar actividad**.
**Resultado esperado:** Aparece "Actividad creada: La actividad ha sido creada correctamente."; la actividad queda "Pendiente Aprobación".

**Resultado esperado de la práctica:** La actividad queda pendiente de aprobación; la recomendación y el plan pasan a "Pendiente" y el Número de actividades se suma a lo programado. El siguiente paso lo da el Monitor o el Líder de Macrozona en Seguimiento.

**Lista de verificación:**
- [ ] Completó los 9 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La actividad queda pendiente de aprobación; la recomendación y el plan pasan a "Pendiente" y el Número de actividades se suma a lo programado. El siguiente paso lo da el Monitor o el Líder de Macrozona en Seguimiento.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 5 y lo resolvió.

#### Actividad 26: Práctica: Editar o eliminar una actividad pendiente

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, corregir o retirar una actividad mientras está pendiente de aprobación y el plan no está confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E3.3; los mismos requisitos de Módulo 05: Actividad 7.

**Dónde:** Actividades › ⋯ › **Editar Actividad** / **Eliminar Actividad** (también en "Detalle de Actividad": botones Editar y Eliminar).

**Datos de la práctica:** AC-023-01 de RC-023-2025-013, aún pendiente: la línea base deja vacío el Instrumento de planeación (observación H5); edítela para elegir Sí o No [DATO REAL AT-013-25].

**Pasos:**

##### Paso 26.1: Verificar el estado
**Objetivo del paso:** Saber si se puede modificar.
**Qué hacer:** En el ambiente de pruebas: Confirme que la columna Estado diga "Pendiente Aprobación".
**Resultado esperado:** Si dice "Aprobado", no se puede editar ni eliminar.

##### Paso 26.2: Editar
**Objetivo del paso:** Corregir la actividad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Editar Actividad**, ajuste Objetivo, Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos u Observaciones, y **Guardar cambios**.
**Resultado esperado:** Aparece "Actividad actualizada: La actividad ha sido actualizada correctamente."

##### Paso 26.3: Eliminar (si aplica)
**Objetivo del paso:** Retirar una actividad equivocada.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Eliminar Actividad** y confirme.
**Resultado esperado:** Aparece "Actividad eliminada: La actividad ha sido eliminada correctamente."

**Resultado esperado de la práctica:** La actividad queda corregida o eliminada; el estado de la recomendación y del plan se recalcula.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La actividad queda corregida o eliminada; el estado de la recomendación y del plan se recalcula.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 7 y lo resolvió.

#### Actividad 27: Práctica: Comentar una actividad y atender los comentarios de la revisión

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, leer y escribir comentarios en una actividad para acordar ajustes con quien revisa.

**Cuándo se hace y requisitos previos:** Secuencia E3.4; los mismos requisitos de Módulo 05: Actividad 8.

**Dónde:** Actividades de la recomendación › ⋯ › **Comentarios** (o "Detalle de Actividad" › ícono **Comentarios**).

**Datos de la práctica:** Responda al comentario del Monitor sobre AC-022-03: "Precisar cuántas actividades se harán por departamento" (las Observaciones de la línea base dicen "Una actividad por departamento y una por Distrito Capital. Desde la sesión departamental,…") [DATO REAL AT-013-25].

**Pasos:**

##### Paso 27.1: Abrir los comentarios
**Objetivo del paso:** Ver lo que pidió quien revisa.
**Qué hacer:** En el ambiente de pruebas: En la fila de la actividad haga clic en ⋯ › **Comentarios** (o, en el detalle, en el ícono **Comentarios**).
**Resultado esperado:** Se abre la conversación.

##### Paso 27.2: Escribir un comentario
**Objetivo del paso:** Responder o pedir aclaraciones.
**Qué hacer:** En el ambiente de pruebas: Escriba en el campo "Comentarios" (máx. 2.000 caracteres) y envíe.
**Resultado esperado:** El comentario aparece con su nombre y la fecha.

##### Paso 27.3: Ajustar la actividad
**Objetivo del paso:** Atender lo pedido.
**Qué hacer:** En el ambiente de pruebas: Si le pidieron cambios y la actividad sigue pendiente, edítela (actividad "Editar o eliminar una actividad pendiente").
**Resultado esperado:** La actividad queda lista para la aprobación.

**Resultado esperado de la práctica:** Queda registrada la conversación sobre la actividad.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Queda registrada la conversación sobre la actividad.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 8 y lo resolvió.

#### Actividad 28: Práctica: Agregar una actividad a un plan ya confirmado

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, agregar una actividad nueva después de la confirmación del plan, sabiendo que el plan se desconfirma.

**Cuándo se hace y requisitos previos:** Secuencia E4.5; los mismos requisitos de Módulo 05: Actividad 6.

**Dónde:** Actividades de la recomendación › **Agregar actividad** (con el plan confirmado) › advertencia "Agregar actividad a plan confirmado".

**Datos de la práctica:** RC-022-2025-013 con el plan ya confirmado en el ambiente de pruebas: agregue AC-022-03: Objetivo "Fortalecer las capacidades técnicas y operativas de las autoridades territoriales mediante procesos de capacitación y sensibilización sobre…"; Actividad "Realizar capacitación y sensibilización sobre las funciones de las comisiones territoriales para la coordinación y seguimiento de los procesos electorales en…"; Número de actividades 1; Plazo de implementación "1 a 3 meses" (en la línea base dice "0-3 meses", valor que la pantalla no ofrece); Instrumento de planeación vacío en la línea base: la pantalla exige Sí o No ("Debe seleccionar una opción"); para la práctica elija "Sí" y anote que la entidad debe confirmarlo; Recursos "Sí"; Observaciones "Una actividad por departamento y una por Distrito Capital. Desde la sesión departamental, se transmite virtual a todos…" (texto completo en `data/03_plan_mitigacion.json`, AC-022-03) [DATO REAL AT-013-25].

**Pasos:**

##### Paso 28.1: Leer la advertencia
**Objetivo del paso:** Entender el efecto.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Agregar actividad** y lea la advertencia.
**Resultado esperado:** Conoce que el plan se desconfirmará.

##### Paso 28.2: Decidir
**Objetivo del paso:** Agregar solo si es necesario.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Continuar** para seguir, o en **Cancelar**.
**Resultado esperado:** Con Continuar se abre el formulario de la actividad.

##### Paso 28.3: Diligenciar y guardar la actividad
**Objetivo del paso:** Registrar la nueva actividad.
**Qué hacer:** En el ambiente de pruebas: Complete Recomendación, Objetivo, Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos y Observaciones, y haga clic en **Reportar actividad**.
**Resultado esperado:** La actividad queda pendiente y el plan vuelve a "Pendiente".

##### Paso 28.4: Avisar a quien aprueba
**Objetivo del paso:** Evitar que el plan quede detenido.
**Qué hacer:** En el ambiente de pruebas: Informe al Monitor o al Líder de Macrozona que agregó una actividad (el sistema no les avisa).
**Resultado esperado:** El aprobador revisa y vuelve a confirmar el plan.

**Resultado esperado de la práctica:** El plan queda desconfirmado hasta que se apruebe la nueva actividad y se confirme otra vez; las actividades e informes anteriores no cambian.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El plan queda desconfirmado hasta que se apruebe la nueva actividad y se confirme otra vez; las actividades e informes anteriores no cambian.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 6 y lo resolvió.

#### Actividad 29: Práctica: Consultar los informes de ejecución de una actividad y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, leer los informes reportados de una actividad, con todos sus campos y su archivo.

**Cuándo se hace y requisitos previos:** Secuencia E5; los mismos requisitos de Módulo 05: Actividad 11.

**Dónde:** Actividades › ⋯ › **Ver detalle** › "Detalle de Actividad" › sección **Informes de ejecución**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible). Los informes de ejecución son Mock (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 29.1: Abrir el detalle de la actividad
**Objetivo del paso:** Llegar a los informes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Ver detalle** en la fila de la actividad.
**Resultado esperado:** Ve el detalle de la actividad.

##### Paso 29.2: Leer los informes
**Objetivo del paso:** Conocer lo reportado.
**Qué hacer:** En el ambiente de pruebas: Baje a "Informes de ejecución" y lea cada informe.
**Resultado esperado:** Ve los datos y el estado de cada informe.

##### Paso 29.3: Descargar el PDF
**Objetivo del paso:** Revisar el soporte.
**Qué hacer:** En el ambiente de pruebas: Haga clic en "Informe.pdf".
**Resultado esperado:** Se descarga el archivo; sin archivo: "No hay archivos adjuntos".

**Resultado esperado de la práctica:** Conoce los informes de la actividad y su soporte.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los informes de la actividad y su soporte.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 11 y lo resolvió.

#### Actividad 30: Práctica: Reportar un informe de ejecución

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, reportar lo ejecutado de una actividad en el ciclo, con su soporte en PDF, cuando el plan está confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E5.1; los mismos requisitos de Módulo 05: Actividad 9.

**Dónde:** Planes de acción › … › actividades de la recomendación › **Reportar Informe** › ventana "Cargar informe de ejecución: Reporta el avance y la ejecución de las actividades".

**Datos de la práctica:** Informe Mock sobre AC-022-01 con el plan confirmado: 1 de 1 ejecutada, 01/02/2026–30/03/2026, PDF informe_ejecucion_prueba.pdf (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 30.1: Verificar que el plan esté confirmado
**Objetivo del paso:** Saber si ya puede reportar.
**Qué hacer:** En el ambiente de pruebas: Confirme que recibió el correo "Notificación validación Plan de Acción" o que el botón **Reportar Informe** esté habilitado.
**Resultado esperado:** El botón está activo.

##### Paso 30.2: Abrir el formulario
**Objetivo del paso:** Iniciar el informe.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Reportar Informe** en la fila de la actividad.
**Resultado esperado:** Se abre "Cargar informe de ejecución".

##### Paso 30.3: Elegir las actividades ejecutadas
**Objetivo del paso:** Registrar el avance del ciclo.
**Qué hacer:** En el ambiente de pruebas: En **Actividades ejecutadas** elija cuántas de las programadas se ejecutaron (de 0 al Número de actividades).
**Resultado esperado:** Si elige más de las programadas: "No puede ser mayor que {N}".

##### Paso 30.4: Elegir las fechas de ejecución
**Objetivo del paso:** Ubicar el periodo reportado.
**Qué hacer:** En el ambiente de pruebas: En **Fecha de inicio y fin** elija "Inicio ejecución" y "Fin de ejecución".
**Resultado esperado:** Si el fin es anterior al inicio: "La fecha de fin debe ser posterior a la fecha de inicio".

##### Paso 30.5: Describir las acciones
**Objetivo del paso:** Explicar lo realizado.
**Qué hacer:** En el ambiente de pruebas: Escriba **Acciones implementadas** (obligatorio), **Acciones complementarias** y **Acciones de coordinación** (opcionales).
**Resultado esperado:** Sin acciones implementadas: "Las acciones implementadas son requeridas".

##### Paso 30.6: Describir buenas prácticas e instrumento
**Objetivo del paso:** Registrar lo que funcionó y su planeación.
**Qué hacer:** En el ambiente de pruebas: Escriba **Buenas prácticas** (obligatorio) e **Instrumento de planeación** (opcional, texto).
**Resultado esperado:** Sin buenas prácticas: "Las buenas prácticas son requeridas".

##### Paso 30.7: Describir resultados y dificultades
**Objetivo del paso:** Mostrar los logros y los problemas.
**Qué hacer:** En el ambiente de pruebas: Escriba **Resultados** (obligatorio) y **Dificultades** (opcional).
**Resultado esperado:** Sin resultados: "Los resultados son requeridos".

##### Paso 30.8: Adjuntar el PDF de soporte
**Objetivo del paso:** Dejar la evidencia que exige la aprobación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el área de carga y elija el PDF del informe (hasta 20 MB).
**Resultado esperado:** Sin archivo: "El archivo adjunto es requerido"; con otro formato: "Solo se permiten archivos PDF".

##### Paso 30.9: Revisar y enviar
**Objetivo del paso:** Registrar el informe.
**Qué hacer:** En el ambiente de pruebas: Revise los textos y haga clic en **Reportar informe de ejecución**.
**Resultado esperado:** Aparece "Informe reportado: El informe de ejecución ha sido reportado correctamente."; el Estado Informe pasa a "Pendiente".

**Resultado esperado de la práctica:** El informe queda pendiente de aprobación. El Monitor o el Líder de Macrozona lo aprueban en Seguimiento (no reciben correo: puede avisarles).

**Lista de verificación:**
- [ ] Completó los 9 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El informe queda pendiente de aprobación. El Monitor o el Líder de Macrozona lo aprueban en Seguimiento (no reciben correo: puede avisarles).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 9 y lo resolvió.

#### Actividad 31: Práctica: Editar un informe de ejecución pendiente

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, corregir un informe o su PDF mientras no haya sido aprobado.

**Cuándo se hace y requisitos previos:** Secuencia E5.2; los mismos requisitos de Módulo 05: Actividad 10.

**Dónde:** Actividades › **Editar Informe** › ventana "Editar informe de ejecución: Modifica los datos del informe de ejecución".

**Datos de la práctica:** El informe Mock pendiente de la actividad anterior: corrija Actividades ejecutadas y Resultados (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 31.1: Abrir la edición
**Objetivo del paso:** Cargar el informe.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Editar Informe** en la fila de la actividad.
**Resultado esperado:** Se abre el formulario con los datos.

##### Paso 31.2: Corregir los datos
**Objetivo del paso:** Ajustar lo pedido por el aprobador.
**Qué hacer:** En el ambiente de pruebas: Modifique Actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades o el PDF.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 31.3: Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Informe actualizado: El informe de ejecución ha sido actualizado correctamente."

**Resultado esperado de la práctica:** El informe queda corregido y sigue pendiente de aprobación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El informe queda corregido y sigue pendiente de aprobación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05: Actividad 10 y lo resolvió.

#### Actividad 32: Práctica: Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el usuario de Entidad Territorial (Subdirección) pueda practicar, en el ambiente de pruebas, encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.2; los mismos requisitos de Módulo 06: Actividad 1.

**Dónde:** Menú lateral › **Oficios de consumación** ("Encuentra los oficios de consumación emitidos por la defensoría").

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 32.1: Abrir el módulo
**Objetivo del paso:** Ver los oficios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Oficios de consumación**.
**Resultado esperado:** Aparece la tabla; sin datos: "No hay oficios de consumación: Los oficios de consumación emitidos por la defensoría aparecerán aquí."

##### Paso 32.2: Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros** y elija la Alerta asociada.
**Resultado esperado:** La tabla se filtra.

##### Paso 32.3: Ver el detalle y descargar
**Objetivo del paso:** Leer el oficio.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalle** y en **Descargar**.
**Resultado esperado:** Se descarga el PDF.

**Resultado esperado de la práctica:** Conoce los oficios de consumación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los oficios de consumación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06: Actividad 1 y lo resolvió.

## Alcance y límites

- Alcance de datos: las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección.
- Acciones que comparte con otros roles (cada uno con su alcance): iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad; descargar el pdf de la alerta; descargar el listado de alertas (csv); descargar las recomendaciones (csv); descargar el listado de planes (csv).
- ⚠️ Acciones irreversibles que puede hacer: activar la cuenta desde la invitación; eliminar una actividad.
- Módulos a los que no tiene acceso: Usuarios y entidades, Agentes IA, Seguimiento, Informe de recomendaciones, Reportes, Informes de seguimiento.
- No puede: cambiar la contraseña con la contraseña actual; editar los datos del propio perfil; consultar el historial de cambios de contraseña; listar usuarios e invitaciones; buscar y filtrar usuarios; ver el detalle de un usuario; invitar un usuario; invitar un super administrador; editar un usuario; activar o inactivar un usuario; reenviar una invitación; eliminar una invitación; listar entidades centrales y subdirecciones; buscar y filtrar entidades; ver el detalle de una entidad; y las demás de la tabla "Qué NO puede hacer".

## Indicadores de logro

- [ ] Puede activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace (Módulo 01: Actividad 1).
- [ ] Puede ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo (Módulo 01: Actividad 2).
- [ ] Puede crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo (Módulo 01: Actividad 3).
- [ ] Puede cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo (Módulo 01: Actividad 4).
- [ ] Puede conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema (Módulo 01: Actividad 5).
- [ ] Puede verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve (Módulo 01: Actividad 6).
- [ ] Puede interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance (Módulo 02: Actividad 1).
- [ ] Puede ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa (Módulo 02: Actividad 2).
- [ ] Puede moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra (Módulo 02: Actividad 3).
- [ ] Puede reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión (Módulo 02: Actividad 4).
- [ ] Puede revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo) (Módulo 07: Actividad 1).
- [ ] Puede identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno (Módulo 07: Actividad 2).
- [ ] Puede encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros (Módulo 03: Actividad 1).
- [ ] Puede leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF (Módulo 03: Actividad 2).
- [ ] Puede saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre) (Módulo 03: Actividad 3).
- [ ] Puede descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados (Módulo 03: Actividad 4).
- [ ] Puede pasar de una alerta a su lista de recomendaciones (Módulo 03: Actividad 5).
- [ ] Puede ver las recomendaciones de una alerta con su entidad, sus actividades y su avance (Módulo 04: Actividad 1).
- [ ] Puede leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas (Módulo 04: Actividad 2).
- [ ] Puede descargar las recomendaciones visibles en un archivo CSV (Módulo 04: Actividad 3).
- [ ] Puede ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado (Módulo 05: Actividad 1).
- [ ] Puede entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial (Módulo 05: Actividad 2).
- [ ] Puede ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas (Módulo 05: Actividad 3).
- [ ] Puede leer cada actividad de una recomendación, su estado, su avance y su próximo informe (Módulo 05: Actividad 4).
- [ ] Puede formular una actividad del plan de acción para una recomendación de su entidad, con objetivo, meta por semestre, plazo, instrumento y recursos (Módulo 05: Actividad 5).
- [ ] Puede agregar una actividad nueva después de la confirmación del plan, sabiendo que el plan se desconfirma (Módulo 05: Actividad 6).
- [ ] Puede corregir o retirar una actividad mientras está pendiente de aprobación y el plan no está confirmado (Módulo 05: Actividad 7).
- [ ] Puede leer y escribir comentarios en una actividad para acordar ajustes con quien revisa (Módulo 05: Actividad 8).
- [ ] Puede reportar lo ejecutado de una actividad en el ciclo, con su soporte en PDF, cuando el plan está confirmado (Módulo 05: Actividad 9).
- [ ] Puede corregir un informe o su PDF mientras no haya sido aprobado (Módulo 05: Actividad 10).
- [ ] Puede leer los informes reportados de una actividad, con todos sus campos y su archivo (Módulo 05: Actividad 11).
- [ ] Puede encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento (Módulo 06: Actividad 1).

## Preguntas frecuentes de uso

### Mi rol y lo que veo

**¿Qué puedo hacer con mi rol?**
Rol de las entidades responsables de las recomendaciones. Formula las actividades del plan de acción, atiende los comentarios de la revisión y reporta los informes de ejecución con su soporte en PDF. No aprueba. Recibe los correos de negocio del sistema. En la plataforma puede, entre otras: iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad. *Se explica en: Módulo 00: Actividad 3.*

**¿Qué información veo y por qué?**
Ve las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección. El sistema aplica ese filtro en el servidor según los datos de su usuario. *Se explica en: Módulo 01: Actividad 6.*

**¿Por qué mi rol es Entidad Territorial (Subdirección)?**
Usuario de una subdirección (dirección, dependencia o secretaría) de una entidad central, que responde por las recomendaciones asignadas directamente a esa subdirección como **Entidad Principal**. El sistema lo identifica con el valor `ENTIDAD_TERRITORIAL_SUBDIRECCION` y con la subdirección guardada en su usuario (`SubEntidadId`). *Se explica en: Módulo 00: Actividad 3.*

**¿Cómo verifico con qué datos fui configurado?**
En **Ver Perfil** (Mi perfil) revise Rol, Nivel de Acceso, Entidad Central, Subdirección y Departamentos. Si algo no corresponde, pida la corrección a quien administra los usuarios. *Se explica en: Módulo 01: Actividad 6.*

### Módulos y funcionalidades

**¿Para qué sirve el módulo Acceso a la plataforma?**
Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. *Se explica en: Módulo 01: Actividad 1.*

**¿Para qué sirve el módulo Inicio?**
Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. Tablero de entrada de la plataforma. *Se explica en: Módulo 02: Actividad 1.*

**¿Para qué sirve el módulo Alertas tempranas?**
Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. *Se explica en: Módulo 03: Actividad 1.*

**¿Para qué sirve el módulo Recomendaciones?**
Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). *Se explica en: Módulo 04: Actividad 1.*

**¿Para qué sirve el módulo Planes de acción?**
Que cada entidad responsable formule las actividades con las que atenderá sus recomendaciones y reporte periódicamente lo ejecutado. Módulo donde se formula y se ejecuta el plan de acción. *Se explica en: Módulo 05: Actividad 1.*

**¿Para qué sirve el módulo Oficios de consumación?**
Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. *Se explica en: Módulo 06: Actividad 1.*

**¿Para qué sirve el módulo Notificaciones?**
Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).. *Se explica en: Módulo 07: Actividad 1.*

**¿Cuándo debo consultar, buscar y filtrar alertas tempranas?**
En la secuencia E1–E6 del ciclo. Ubica la alerta y sus datos principales.. *Se explica en: Módulo 03: Actividad 1.*

**¿Cuándo debo ver el detalle de una alerta y descargar su PDF?**
En la secuencia E1–E6 del ciclo. Conoce la alerta completa.. *Se explica en: Módulo 03: Actividad 2.*

**¿Cuándo debo consultar el historial de actividades de una alerta?**
En la secuencia E1–E6 del ciclo. Conoce la trazabilidad de la alerta.. *Se explica en: Módulo 03: Actividad 3.*

**¿Cuándo debo descargar el listado de alertas en CSV?**
En la secuencia E1–E6 del ciclo. Tiene el listado en un archivo.. *Se explica en: Módulo 03: Actividad 4.*

**¿Cuándo debo ir a las recomendaciones de una alerta?**
En la secuencia E2 del ciclo. Llega a las recomendaciones de la alerta.. *Se explica en: Módulo 03: Actividad 5.*

**¿Cuándo debo consultar, buscar y filtrar las recomendaciones de una alerta?**
En la secuencia E2–E6 del ciclo. Conoce las recomendaciones de la alerta y su avance.. *Se explica en: Módulo 04: Actividad 1.*

**¿Cuándo debo ver el detalle de una recomendación?**
En la secuencia E2–E6 del ciclo. Conoce la recomendación completa.. *Se explica en: Módulo 04: Actividad 2.*

**¿Cuándo debo descargar las recomendaciones de una alerta en CSV?**
En la secuencia E2–E6 del ciclo. Tiene las recomendaciones en un archivo.. *Se explica en: Módulo 04: Actividad 3.*

**¿Cuándo debo consultar y filtrar los planes de acción por alerta?**
En la secuencia E3–E5 del ciclo. Conoce el estado de los planes de su alcance.. *Se explica en: Módulo 05: Actividad 1.*

**¿Cuándo debo recorrer las recomendaciones del plan de una alerta?**
En la secuencia E3–E5 del ciclo. Llega a las actividades de la recomendación.. *Se explica en: Módulo 05: Actividad 2.*

**¿Cuándo debo consultar las pestañas globales de Recomendaciones y Actividades?**
En la secuencia E3–E5 del ciclo. Tiene la vista global de su alcance.. *Se explica en: Módulo 05: Actividad 3.*

**¿Cuándo debo consultar las actividades de una recomendación y su detalle?**
En la secuencia E3–E5 del ciclo. Conoce el detalle y el avance de las actividades.. *Se explica en: Módulo 05: Actividad 4.*

**¿Cuándo debo agregar una actividad al plan de acción?**
En la secuencia E3.2 del ciclo. La actividad queda pendiente de aprobación; la recomendación y el plan pasan a "Pendiente" y el Número de actividades se suma a lo programado. *Se explica en: Módulo 05: Actividad 5.*

**¿Cuándo debo agregar una actividad a un plan ya confirmado?**
En la secuencia E4.5 del ciclo. El plan queda desconfirmado hasta que se apruebe la nueva actividad y se confirme otra vez; las actividades e informes anteriores no cambian.. *Se explica en: Módulo 05: Actividad 6.*

**¿Cuándo debo editar o eliminar una actividad pendiente?**
En la secuencia E3.3 del ciclo. La actividad queda corregida o eliminada; el estado de la recomendación y del plan se recalcula.. *Se explica en: Módulo 05: Actividad 7.*

**¿Cuándo debo comentar una actividad y atender los comentarios de la revisión?**
En la secuencia E3.4 del ciclo. Queda registrada la conversación sobre la actividad.. *Se explica en: Módulo 05: Actividad 8.*

**¿Cuándo debo reportar un informe de ejecución?**
En la secuencia E5.1 del ciclo. El informe queda pendiente de aprobación. *Se explica en: Módulo 05: Actividad 9.*

**¿Cuándo debo editar un informe de ejecución pendiente?**
En la secuencia E5.2 del ciclo. El informe queda corregido y sigue pendiente de aprobación.. *Se explica en: Módulo 05: Actividad 10.*

**¿Cuándo debo consultar los informes de ejecución de una actividad y descargar su PDF?**
En la secuencia E5 del ciclo. Conoce los informes de la actividad y su soporte.. *Se explica en: Módulo 05: Actividad 11.*

**¿Cuándo debo consultar los oficios de consumación y descargar su PDF?**
En la secuencia E6.2 del ciclo. Conoce los oficios de consumación.. *Se explica en: Módulo 06: Actividad 1.*

### Ciclo de la alerta y estados

**¿Qué significa el estado "Borrador"?**
Alerta creada por el Agente IA o recibida de forma automática que aún no se publica; no cuenta en los indicadores. *Se explica en: Módulo 03: Actividad 1.*

**¿Qué significa el estado "Activa"?**
Alerta vigente sobre la que se trabajan recomendaciones, plan e informes. *Se explica en: Módulo 03: Actividad 1.*

**¿Qué significa el estado "Cerrada"?**
Alerta terminada; no se edita ni se reabre. *Se explica en: Módulo 03: Actividad 1.*

**¿Qué significa el estado "Sin plan"?**
Ninguna recomendación de la alerta tiene actividades. *Se explica en: Módulo 05: Actividad 1.*

**¿Qué significa el estado "Pendiente"?**
Hay actividades (o informes) por aprobar. *Se explica en: Módulo 05: Actividad 1.*

**¿Qué significa el estado "Aprobado"?**
Todas las actividades están aprobadas; el plan se puede confirmar. *Se explica en: Módulo 05: Actividad 1.*

**¿Qué significa el estado "Sin Informe"?**
La actividad debe reportar el informe del ciclo. *Se explica en: Módulo 05: Actividad 1.*

**¿Qué pasa después de que se confirma el plan de acción?**
Las actividades quedan "Sin Informe", la Entidad Territorial recibe el correo de validación y puede reportar informes de ejecución; la alerta, sus recomendaciones y actividades ya no se editan. *Se explica en: Módulo 05: Actividad 9.*

**¿Qué pasa si una entidad agrega una actividad a un plan confirmado?**
El plan se desconfirma: vuelve a "Pendiente", la nueva actividad debe aprobarse y el plan debe confirmarse otra vez. Lo existente no cambia. *Se explica en: Módulo 05: Actividad 6.*

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
Sí, con restricción: Sobre las recomendaciones de su subdirección que ve en su listado; alerta no cerrada. *Se explica en: Módulo 05: Actividad 5.*

**¿Puedo reportar un informe de ejecución?**
Sí, con restricción: Solo con el plan confirmado y la actividad "Sin Informe". *Se explica en: Módulo 05: Actividad 9.*

**¿Puedo aprobar una actividad?**
No. UI: el menú no muestra *Seguimiento*. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo confirmar el plan de acción?**
No. UI: el menú no muestra *Seguimiento*. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar un informe de ejecución?**
No. UI: el menú no muestra *Seguimiento*. Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un reporte de ejecución?**
No. UI y API: sin menú, ruta bloqueada y `RequireReportes`. Lo hace: Pida la información a un Monitor, Líder de Macrozona o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar un reporte de ejecución?**
No. UI y API: sin menú, ruta bloqueada y `RequireReportes`. Lo hace: El aprobador designado (Líder de Macrozona o Super Administrador). *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un informe de seguimiento?**
No. UI: el menú no muestra *Informes de seguimiento*. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un oficio de consumación?**
No. UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación". Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo invitar un usuario?**
No. UI y API: sin menú, `AdminRoute` y `RequireAdmin`. Lo hace: Super Administrador o Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo adjuntar el PDF de la alerta y el Adjunto?**
No. UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin`. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo ver y escribir comentarios de una actividad?**
Sí, con restricción: Desde Planes de acción, en actividades de su subdirección y con la alerta abierta. *Se explica en: Módulo 05: Actividad 8.*

### Plazos y vigencias

**¿Cuánto dura la invitación?**
7 días desde el envío. Por ejemplo, si se envió el 2 de febrero de 2026, sirve hasta el 9 de febrero de 2026. *Se explica en: Módulo 01: Actividad 1.*

**¿Cuánto dura el código de verificación?**
1 hora. Si llega a las 8:05 a. m., sirve hasta las 9:05 a. m. *Se explica en: Módulo 01: Actividad 2.*

**¿Cuánto dura mi sesión?**
Se cierra a los 60 minutos sin actividad y vence a los 720 minutos (12 horas). *Se explica en: Módulo 01: Actividad 4.*

**¿Cada cuánto se reportan los informes de ejecución?**
Cada 6 meses por actividad. El primer próximo informe se fija al aprobar el primer informe: fecha de notificación de la alerta + 6 meses (para la AT-013-2025, notificada el 07/10/2025, el 07/04/2026 [DATO REAL AT-013-25]); luego +6 meses sobre el anterior. *Se explica en: Módulo 05: Actividad 9.*

**¿El plazo de implementación de una actividad genera vencimientos?**
No. Es informativo (1 a 3, 3 a 6, 6 a 9 meses o Permanente); los vencimientos solo los genera el Próximo Informe. *Se explica en: Módulo 05: Actividad 5.*

### Notificaciones

**¿Qué avisos voy a recibir y qué debo hacer con cada uno?**
Correos de invitación, código, restablecimiento, recomendación asignada o actualizada, validación del plan, recordatorio de informe, informe de seguimiento y oficio de consumación; cada uno indica la acción siguiente. *Se explica en: Módulo 07: Actividad 2.*

**¿Qué muestra el panel Notificaciones?**
El historial de actividad de las alertas de su alcance: quién hizo qué, cuándo y sobre qué alerta. No tiene marcas de leído. *Se explica en: Módulo 07: Actividad 1.*

### Indicadores

**¿Cómo se calcula el % de cumplimiento?**
Actividades ejecutadas ÷ programadas × 100. Ejemplo: 3 ejecutadas de 4 programadas = 75 %. Cada 6 meses la meta se suma otra vez a lo programado: con 4 actividades por ciclo, en el segundo ciclo son 8 programadas. *Se explica en: Módulo 05: Actividad 4.*

**¿Cómo se calcula el "Porcentaje de Avance Global" del Inicio?**
Es el promedio del % de cumplimiento de cada alerta (no borrador) de su alcance; las alertas sin actividades cuentan como 0 %. Con A = 50 % y B = 100 %, el avance es 75 %. *Se explica en: Módulo 02: Actividad 1.*

### Datos y formularios

**¿Qué campos son obligatorios en "Activar la cuenta (Configura tu contraseña)"?**
Nueva Contraseña; Confirmar Contraseña. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01: Actividad 1.*

**¿Qué campos son obligatorios en "Iniciar sesión"?**
Correo electrónico; Contraseña; Código de verificación (4 casillas). Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01: Actividad 2.*

**¿Qué campos son obligatorios en "Solicitar el restablecimiento"?**
Correo electrónico. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01: Actividad 3.*

**¿Qué campos son obligatorios en "Configurar nueva contraseña"?**
Nueva Contraseña; Confirmar Contraseña. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 01: Actividad 3.*

**¿Qué campos son obligatorios en "Agregar actividad / Editar actividad (2 pasos)"?**
Objetivo; Actividad; Número de actividades; Plazo de implementación; Instrumento de planeación; Recursos. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 05: Actividad 5.*

**¿Qué campos son obligatorios en "Comentarios de la actividad"?**
Comentarios. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 05: Actividad 8.*

**¿Qué campos son obligatorios en "Cargar informe de ejecución / Editar informe de ejecución"?**
Actividades ejecutadas; Fecha de inicio y fin (Inicio ejecución); Fecha de inicio y fin (Fin de ejecución); Acciones implementadas; Buenas prácticas; Resultados; Archivo adjunto (PDF del informe). Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 05: Actividad 9.*

**¿Qué archivos puedo adjuntar?**
Solo PDF, de hasta 20 MB por archivo. *Se explica en: Módulo 05: Actividad 9.*

**¿De dónde salen las opciones de las listas?**
De archivos de catálogo del sistema (ejes temáticos, opciones de la alerta, departamentos y municipios, categorías de entidad) y de la tabla de entidades. Solo las entidades se administran desde la plataforma (Usuarios y entidades). *Se explica en: Módulo 05: Actividad 5.*

## Errores frecuentes y cómo solucionarlos

### Acceso y sesión

**Me aparece «El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador.»**
**Causa:** La invitación vence a los 7 días. **Solución:** Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Active la cuenta apenas reciba el correo. *Relacionado con: Módulo 01: Actividad 1 (ERR-ACC-06).*

**Me aparece «El enlace de invitación es inválido. Verifica que el enlace esté completo.»**
**Causa:** El enlace se cortó al copiarlo o la cuenta ya se activó. **Solución:** Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** No copie el enlace a mano. *Relacionado con: Módulo 01: Actividad 1 (ERR-ACC-07).*

**Me aparece «Credenciales inválidas»**
**Causa:** El correo no existe o la contraseña no corresponde. **Solución:** Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** No comparta ni anote la contraseña en lugares visibles. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-01).*

**Me aparece «Código de autenticación inválido»**
**Causa:** El código no coincide con el último enviado. **Solución:** Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use siempre el código del correo más reciente. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-02).*

**Me aparece «Código expirado»**
**Causa:** El código vence 1 hora después de enviado. **Solución:** Haga clic en **Haz clic para reenviar** y use el código nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Ingrese el código apenas llegue. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-03).*

**Me aparece «Cuenta no activa»**
**Causa:** El administrador cambió el estado del usuario a Inactivo. **Solución:** Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). **Si no se resuelve:** Super Administrador o Administrador de la plataforma **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-04).*

**Me aparece «Tu organización está suspendida. Por favor contacta al administrador.»**
**Causa:** La entidad guardada en su usuario no está en estado Activa. **Solución:** Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-05).*

**No llega el correo con el código y no aparece ningún mensaje**
**Causa:** El correo puede estar en la carpeta de correo no deseado o tardar en llegar. **Solución:** Revise la carpeta de correo no deseado; espere un minuto y use **Haz clic para reenviar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co) **Cómo prevenirlo:** Agregue el remitente de SI-CIPRAT a sus contactos. *Relacionado con: Módulo 01: Actividad 2 (ERR-ACC-14).*

**Me aparece «Token inválido o expirado»**
**Causa:** El enlace de restablecimiento vence en 1 hora. **Solución:** Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use el enlace apenas llegue. *Relacionado con: Módulo 01: Actividad 3 (ERR-ACC-11).*

**Me aparece «Sesión cerrada por inactividad: Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente.»**
**Causa:** Cierre automático por inactividad de 60 minutos. **Solución:** Inicie sesión de nuevo (correo, contraseña y código). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Guarde los formularios antes de dejar el equipo. *Relacionado con: Módulo 01: Actividad 4 (ERR-ACC-12).*

**Me aparece «Sesión expirada: Tu sesión ha expirado. Por favor, inicia sesión nuevamente.»**
**Causa:** El token de la sesión venció (720 minutos) o no es válido. **Solución:** Inicie sesión de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01: Actividad 4 (ERR-ACC-13).*

### Formularios

**Me aparece «Debe tener al menos 8 caracteres»**
**Causa:** La contraseña no cumple las reglas. **Solución:** Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los indicadores de la pantalla antes de enviar. *Relacionado con: Módulo 01: Actividad 1 (ERR-ACC-08).*

**Me aparece «Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente.»**
**Causa:** Los dos campos no coinciden. **Solución:** Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01: Actividad 1 (ERR-ACC-09).*

**Me aparece «No puedes reutilizar ninguna de tus últimas 5 contraseñas»**
**Causa:** El sistema guarda el historial de contraseñas. **Solución:** Elija una contraseña distinta de las 5 anteriores. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01: Actividad 3 (ERR-ACC-10).*

**Me aparece «La solicitud no es válida. Verifica los datos e intenta de nuevo.»**
**Causa:** Errores 400 o 422 de validación. **Solución:** Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Lea la ayuda de cada campo. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-13).*

**Me aparece «El objetivo es requerido»**
**Causa:** Faltan campos obligatorios. **Solución:** Complete el Objetivo (Paso 1) y Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación y Recursos (Paso 2). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 5 (ERR-PLA-01).*

**Me aparece «Plazo de implementación inválido: …»**
**Causa:** Solo se aceptan 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente. **Solución:** Elija una opción de la lista. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 5 (ERR-PLA-07).*

**Me aparece «El contenido no puede exceder 2000 caracteres»**
**Causa:** Límite de 2.000 caracteres o falla de conexión. **Solución:** Divida el comentario en varios o intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 8 (ERR-PLA-08).*

**Me aparece «Las actividades ejecutadas son requeridas»**
**Causa:** Faltan datos obligatorios del informe. **Solución:** Complete los campos marcados y adjunte el PDF. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Prepare el PDF de soporte antes de abrir el formulario. *Relacionado con: Módulo 05: Actividad 9 (ERR-PLA-10).*

**Me aparece «La fecha de fin debe ser posterior a la fecha de inicio»**
**Causa:** Rango de fechas inválido. **Solución:** Corrija la fecha de inicio o de fin. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 9 (ERR-PLA-11).*

**Me aparece «No puede ser mayor que {N}»**
**Causa:** Lo ejecutado no puede superar el "Número de actividades" del ciclo. **Solución:** Elija un número entre 0 y el número de actividades programadas; explique lo adicional en Acciones complementarias. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 9 (ERR-PLA-12).*

### Permisos y alcance

**Encontrar en Mi perfil un rol, entidad, subdirección o departamentos que no corresponden y no aparece ningún mensaje**
**Causa:** El usuario fue configurado con otros datos; Mi perfil no permite editarlos. **Solución:** Pida la corrección a quien administra los usuarios, indicando el dato correcto. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise Mi perfil después del primer ingreso. *Relacionado con: Módulo 01: Actividad 6 (ERR-ACC-15).*

**Me aparece «No tienes permisos para realizar esta acción.»**
**Causa:** El servidor rechaza la operación para el rol (403). **Solución:** Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co) con la pantalla, la hora y una captura **Cómo prevenirlo:** Use solo los botones habilitados para su rol. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-01).*

**Abrir el enlace del correo de una recomendación en la que su entidad es asociada y no aparece ningún mensaje**
**Causa:** Las entidades asociadas reciben el correo, pero solo la Entidad Principal ve la recomendación (riesgo R6). **Solución:** Coordine con la entidad principal; si su entidad debe responder, pida a la Secretaría Técnica que la registre como principal. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07: Actividad 2 (ERR-NOT-03).*

**Me aparece Botones deshabilitados con "No tienes permisos para reportar alertas", "No tienes permisos para editar alertas", "No tienes permisos para eliminar alertas", "No tienes permisos para cerrar alertas"**
**Causa:** Su rol solo consulta alertas. **Solución:** Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03: Actividad 1 (ERR-ALE-17).*

**Me aparece Botones deshabilitados con "No tienes permisos para agregar recomendaciones" / "No tienes permisos para editar recomendaciones" / "No tienes permisos para eliminar recomendaciones"**
**Causa:** Solo el Super Administrador y el Administrador las registran. **Solución:** Pida el cambio a la Secretaría Técnica. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04: Actividad 1 (ERR-REC-06).*

**No ver todas las recomendaciones de una alerta y no aparece ningún mensaje**
**Causa:** Dentro de cada alerta solo ve las recomendaciones de su entidad o subdirección. **Solución:** No requiere acción; si una recomendación de su entidad no aparece, pida que se revise su Entidad Principal. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04: Actividad 1 (ERR-REC-09).*

**Me aparece «Error al cargar el informe de recomendaciones»**
**Causa:** El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. **Solución:** Pida el consolidado a la Secretaría Técnica o al Monitor. **Si no se resuelve:** Monitor, Líder de Macrozona o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 1 (ERR-PLA-17).*

**Me aparece Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"**
**Causa:** Solo el Super Administrador gestiona oficios. **Solución:** Pida la carga al Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06: Actividad 1 (ERR-OFI-02).*

**No veo, o aparece deshabilitada, la opción para cambiar la contraseña con la contraseña actual**
**Causa:** Su rol no tiene esta funcionalidad: UI: no existe una pantalla que use este servicio (`main-api/CipratApi/Controladores/AutenticacionControlador.cs:147`; solo `dashboard/src/contexts/AuthContext.tsx` lo referencia). **Solución:** No es un error de la plataforma. La realiza: Use **¿Has olvidado tu contraseña?** para cambiarla. **Si no se resuelve:** Use **¿Has olvidado tu contraseña?** para cambiarla **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01: Actividad 1 (F-ACC-11).*

**No veo, o aparece deshabilitada, la opción para editar los datos del propio perfil**
**Causa:** Su rol no tiene esta funcionalidad: UI: los campos de Mi perfil están deshabilitados (`dashboard/src/pages/MyProfile.tsx:124-183`). **Solución:** No es un error de la plataforma. La realiza: Pida el cambio a quien administra los usuarios (Super Administrador o Administrador). **Si no se resuelve:** Pida el cambio a quien administra los usuarios (Super Administrador o Administrador) **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01: Actividad 1 (F-ACC-13).*

**No veo, o aparece deshabilitada, la opción para consultar el historial de cambios de contraseña**
**Causa:** Su rol no tiene esta funcionalidad: UI: el hook `usePasswordHistory` existe, pero Mi perfil no lo muestra (`dashboard/src/hooks/usePasswordHistory.ts:20`, `dashboard/src/pages/MyProfile.tsx`). **Solución:** No es un error de la plataforma. La realiza: No disponible en la interfaz. **Si no se resuelve:** No disponible en la interfaz **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01: Actividad 1 (F-ACC-14).*

**No veo, o aparece deshabilitada, la opción para reportar una alerta temprana**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-08).*

**No veo, o aparece deshabilitada, la opción para adjuntar el PDF de la alerta y el Adjunto**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-09).*

**No veo, o aparece deshabilitada, la opción para editar una alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-10).*

**No veo, o aparece deshabilitada, la opción para cambiar el número de una alerta manual**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-11).*

**No veo, o aparece deshabilitada, la opción para publicar una alerta en borrador**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-12).*

**No veo, o aparece deshabilitada, la opción para subsumir otras alertas**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-13).*

**No veo, o aparece deshabilitada, la opción para eliminar una alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-14).*

**No veo, o aparece deshabilitada, la opción para reemplazar o eliminar los archivos de la alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-15).*

**No veo, o aparece deshabilitada, la opción para cerrar alertas**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: el botón está deshabilitado ("No tienes permisos para …") y el servidor exige `RequireAdmin` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx:66-72`, `main-api/CipratApi/Controladores/AlertasControlador.cs:336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03: Actividad 1 (F-ALE-16).*

**No veo, o aparece deshabilitada, la opción para agregar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04: Actividad 1 (F-REC-05).*

**No veo, o aparece deshabilitada, la opción para editar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador o Administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04: Actividad 1 (F-REC-06).*

**No veo, o aparece deshabilitada, la opción para eliminar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botones deshabilitados ("No tienes permisos para agregar recomendaciones") y `RequireAdmin` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:62-88`, `main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04: Actividad 1 (F-REC-07).*

**No veo, o aparece deshabilitada, la opción para eliminar un comentario propio**
**Causa:** Su rol no tiene esta funcionalidad: UI: la ventana "Comentarios" no ofrece eliminar (`dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`); la API lo permite al autor (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:140`). **Solución:** No es un error de la plataforma. La realiza: No disponible en la interfaz. **Si no se resuelve:** No disponible en la interfaz **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05: Actividad 1 (F-PLA-16).*

**No veo, o aparece deshabilitada, la opción para eliminar un informe de ejecución**

**No veo, o aparece deshabilitada, la opción para cargar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06: Actividad 1 (F-OFI-05).*

**No veo, o aparece deshabilitada, la opción para modificar municipios y agregar recomendaciones desde el oficio**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06: Actividad 1 (F-OFI-06).*

**No veo, o aparece deshabilitada, la opción para editar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06: Actividad 1 (F-OFI-07).*

**No veo, o aparece deshabilitada, la opción para eliminar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06: Actividad 1 (F-OFI-08).*

### Estados

**Me aparece «Conflicto con el estado actual del recurso.»**
**Causa:** Otro usuario o una acción anterior cambió el estado del registro (409). **Solución:** Actualice la página, revise el estado actual y repita la acción si todavía aplica. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Evite el doble clic y trabaje sobre la información recién cargada. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-03).*

**Me aparece Botón deshabilitado con "No se pueden agregar actividades a una alerta cerrada" (servidor: "No se pueden crear actividades porque la alerta está cerrada")**
**Causa:** La alerta está cerrada. **Solución:** No requiere acción. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 5 (ERR-PLA-02).*

**Me aparece Advertencia "Agregar actividad a plan confirmado: Al agregar una nueva actividad a la alerta … el plan de acción será desconfirmado automáticamente. … El estado del plan volverá a "Pendiente Aprobación" · Deberá aprobarse la nueva actividad · Deberá confirmarse el plan nuevamente. Las…**
**Causa:** Regla de desconfirmación automática. **Solución:** Haga clic en **Continuar** solo si la actividad es necesaria; si no, **Cancelar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Formule todas las actividades antes de la confirmación. *Relacionado con: Módulo 05: Actividad 6 (ERR-PLA-05).*

**Me aparece Botones deshabilitados con "No se puede editar porque la actividad ya está aprobada" / "No se puede eliminar porque la actividad ya está aprobada" (servidor: "No se puede editar una actividad aprobada o cerrada")**
**Causa:** Las actividades aprobadas quedan bloqueadas. **Solución:** Si debe corregirla, pida al Monitor o al Líder de Macrozona que use **Descartar aprobación** (solo si el plan no está confirmado). **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Revise la actividad antes de que sea aprobada. *Relacionado con: Módulo 05: Actividad 7 (ERR-PLA-03).*

**Me aparece «No se puede editar la actividad porque el plan de acción ya fue confirmado»**
**Causa:** Con el plan confirmado no se modifican actividades. **Solución:** Si necesita una acción adicional, agréguela como actividad nueva (esto desconfirma el plan). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 7 (ERR-PLA-04).*

**Me aparece Botón deshabilitado con "El plan de acción debe estar confirmado para reportar informes" (servidor: "No se pueden crear informes de ejecución hasta que el plan de acción esté confirmado")**
**Causa:** Los informes solo se habilitan con el plan confirmado. **Solución:** Espere el correo "Notificación validación Plan de Acción" o revise el estado del plan. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 9 (ERR-PLA-09).*

**Aprobar el primer informe de una actividad después de la fecha de notificación + 6 meses y no aparece ningún mensaje**
**Causa:** El próximo informe se calcula desde la fecha de notificación de la alerta y no desde la aprobación; si esa fecha ya pasó, la tarea diaria abre el nuevo ciclo de inmediato. **Solución:** La entidad reporta el informe del nuevo ciclo; el aprobador lo revisa en Seguimiento. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Reportar y aprobar los informes antes de la fecha de notificación + 6 meses. *Relacionado con: Módulo 05: Actividad 9 (ERR-SEG-15).*

**Me aparece Botón deshabilitado con "No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe." (servidor: "No se puede modificar un informe que ya fue aprobado")**
**Causa:** La aprobación del informe es irreversible. **Solución:** Espere la fecha del "Próximo Informe" para reportar el siguiente. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise el informe antes de que lo aprueben. *Relacionado con: Módulo 05: Actividad 10 (ERR-PLA-13).*

### Archivos

**Me aparece «Tipo de archivo no permitido. Solo se aceptan: .pdf»**
**Causa:** Los campos de archivo solo aceptan PDF. **Solución:** Convierta el documento a PDF y vuelva a seleccionarlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Prepare los soportes en PDF antes de abrir el formulario. *Relacionado con: Módulo 05: Actividad 9 (ERR-GEN-08).*

**Me aparece «El archivo excede el tamaño máximo de {N} MB»**
**Causa:** El servidor acepta hasta 20 MB por archivo. **Solución:** Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Escanee en resolución media y sin color cuando sea posible. *Relacionado con: Módulo 05: Actividad 9 (ERR-GEN-09).*

### Integraciones

**No llegan los correos del sistema y no aparece ningún mensaje**
**Causa:** Falla del envío de correo o usuario inactivo. **Solución:** Revise la carpeta de correo no deseado y consulte la información directamente en la plataforma. **Si no se resuelve:** Soporte técnico **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07: Actividad 2 (ERR-NOT-04).*

**No llega el recordatorio de informe y no aparece ningún mensaje**
**Causa:** El recordatorio solo se envía una vez por ciclo, a 30 días o menos, y depende de la tarea diaria. **Solución:** Consulte la columna "Próximo Informe" de sus actividades. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Anote la fecha del próximo informe cuando le aprueben un informe. *Relacionado con: Módulo 07: Actividad 2 (ERR-TAR-01).*

**Una alerta emitida por la Defensoría no aparece en SI-CIPRAT y no aparece ningún mensaje**

### Sistema y conexión

**Me aparece «No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo.»**
**Causa:** Sin conexión o red bloqueada. **Solución:** Revise la conexión, recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Trabaje con conexión estable; los Términos de uso la exigen. *Relacionado con: Módulo 01: Actividad 2 (ERR-GEN-06).*

**Me aparece «Error al cargar datos»**
**Causa:** Falla del servicio del tablero. **Solución:** Recargue la página; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02: Actividad 1 (ERR-INI-01).*

**Me aparece «Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio.»**
**Causa:** Los formularios de registro se bloquean en pantallas pequeñas. **Solución:** Use un computador de escritorio o portátil. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Planee el registro desde un computador. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-11).*

**Me aparece «El servidor no está disponible. Por favor, intenta más tarde.»**
**Causa:** Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). **Solución:** Espere unos minutos e intente de nuevo. **Si no se resuelve:** Soporte técnico si dura más de 30 minutos **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-05).*

**Me aparece «Error al cargar alertas: No se pudieron cargar las alertas. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03: Actividad 1 (ERR-ALE-19).*

**Me aparece «El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose.»**
**Causa:** El registro fue eliminado o el servidor no responde (404). **Solución:** Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. **Si no se resuelve:** Soporte técnico, con el número de la alerta y la hora **Cómo prevenirlo:** No use enlaces antiguos guardados en el navegador. *Relacionado con: Módulo 03: Actividad 2 (ERR-GEN-02).*

**Me aparece «Error interno del servidor. Por favor, intenta más tarde.»**
**Causa:** Error 500 del servidor. **Solución:** Espere unos minutos e intente de nuevo; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico, con la pantalla, la acción, la hora y una captura **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03: Actividad 3 (ERR-GEN-04).*

**Me aparece «Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo.»**
**Causa:** Falla al generar el archivo o al conectarse. **Solución:** Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Filtre antes de descargar. *Relacionado con: Módulo 03: Actividad 4 (ERR-GEN-10).*

**Me aparece «Error al cargar las recomendaciones. Por favor, intente nuevamente.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04: Actividad 1 (ERR-REC-07).*

**Me aparece «Error al cargar las actividades»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 2 (ERR-PLA-15).*

**Me aparece «Error al guardar el informe. Por favor, intente nuevamente.»**
**Causa:** Falla del servicio o validación del servidor. **Solución:** Lea el mensaje, corrija y vuelva a hacer clic en **Reportar informe de ejecución**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 9 (ERR-PLA-14).*

**Me aparece «Error al cargar oficios: No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06: Actividad 1 (ERR-OFI-05).*

### Sin resultados

**Me aparece «No hay datos de departamentos»**
**Causa:** No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. **Solución:** Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02: Actividad 1 (ERR-INI-02).*

**Me aparece «Página no encontrada: Lo sentimos, la página que buscas no existe o ha sido movida.»**
**Causa:** La ruta no existe. **Solución:** Haga clic en **Volver al inicio** y navegue desde el menú. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use el menú lateral. *Relacionado con: Módulo 02: Actividad 3 (ERR-GEN-12).*

**Me aparece «No hay notificaciones»**
**Causa:** No hay acciones registradas en las alertas de su alcance. **Solución:** No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07: Actividad 1 (ERR-NOT-01).*

**No encontrar una alerta que esperaba ver y no aparece ningún mensaje**
**Causa:** La alerta está fuera de su alcance (departamentos o entidad), es un borrador o no existe. **Solución:** Revise su alcance en **Ver Perfil**; si la alerta le corresponde, pida el ajuste de su usuario o de la recomendación. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03: Actividad 1 (ERR-ALE-18).*

**Me aparece «No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo.»**
**Causa:** No hay registros que cumplan la búsqueda dentro de su alcance. **Solución:** Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque por número de alerta o código. *Relacionado con: Módulo 03: Actividad 1 (ERR-GEN-07).*

**Me aparece «La alerta solicitada no existe o ha sido eliminada.»**
**Causa:** La alerta ya no existe. **Solución:** Vuelva con **Volver a Alertas Tempranas**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03: Actividad 5 (ERR-REC-08).*

**La pestaña global **Actividades** no muestra las actividades de su subdirección y no aparece ningún mensaje**
**Causa:** El listado global filtra por la entidad central del usuario y no por la subdirección (riesgo R5). **Solución:** Entre por **Alertas** › **Ir al plan de acción** › **Ver Actividades** de cada recomendación. **Si no se resuelve:** Soporte técnico (riesgo conocido R5) **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05: Actividad 3 (ERR-PLA-16).*

## Glosario de la ruta

### Botón

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| ¿Has olvidado tu contraseña? | botón | Inicia la recuperación de la contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Activar cuenta | botón | Crea la contraseña y activa la cuenta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Agregar actividad | botón | Abre el registro de una actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Agregar recomendación | botón | Abre el registro de una recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04: Actividad 1 |
| Aplicar filtros | botón | Aplica los filtros elegidos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Asociar entidades | botón | Agrega entidades asociadas a la Entidad Principal. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04: Actividad 1 |
| Atrás | botón | Regresa al paso anterior. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Cancelar | botón | Cierra sin guardar. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Cargar oficio | botón | Abre o guarda la carga de un oficio. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06: Actividad 1 |
| Cerrar alertas | botón | Abre el cierre de alertas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Comentarios | botón | Abre la conversación de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Continuar | botón | Acepta agregar una actividad a un plan confirmado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Crear recomendación | botón | Guarda la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04: Actividad 1 |
| Descargar | botón | Descarga el listado en CSV o el archivo. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Editar Actividad | botón | Abre la edición de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Editar Informe | botón | Abre la edición del informe pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Eliminar Actividad | botón | Elimina la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Enviar Alerta | botón | Guarda la alerta nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Filtros | botón | Abre los filtros del listado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Guardar Cambios | botón | Guarda la edición (alerta o usuario). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Haz clic para reenviar | botón | Envía un nuevo código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Informe | botón | Abre el Informe de recomendaciones. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Iniciar Sesión | botón | Valida correo y contraseña y envía el código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Ir al plan de acción | botón | Abre las recomendaciones del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Limpiar filtros | botón | Quita todos los filtros. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Mostrar 10 mas | botón | Carga 10 registros más. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07: Actividad 1 |
| Reportar actividad | botón | Guarda la actividad nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Reportar alerta | botón | Abre el registro manual de una alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Reportar Informe | botón | Abre el informe de ejecución de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Reportar informe de ejecución | botón | Guarda el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Restablecer contraseña | botón | Envía el enlace o guarda la nueva contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Siguiente | botón | Avanza al siguiente paso del asistente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03: Actividad 1 |
| Validar código | botón | Valida el código de 4 dígitos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01: Actividad 1 |
| Ver Actividades | botón | Abre las actividades de la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |
| Ver Alerta | botón | Abre la última alerta del banner. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 02: Actividad 1 |
| Ver detalle | botón | Abre el detalle del registro. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05: Actividad 1 |

### Campo

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| % cumplimiento | campo | Ejecutadas ÷ programadas × 100. | Indicador de avance de actividad, recomendación y alerta. | Módulo 05: Actividad 1 |
| Acciones complementarias | campo | Área de texto., | Obligatorio: No. | Módulo 05: Actividad 9 |
| Acciones de coordinación | campo | Área de texto., | Obligatorio: No. | Módulo 05: Actividad 9 |
| Acciones implementadas | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Actividades ejecutadas | campo | Lista de selección (número). Entero de 0 al Número de actividades | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Archivo adjunto (PDF del informe) | campo | Archivo. PDF ≤ 20 MB | Obligatorio: Sí (en pantalla). | Módulo 05: Actividad 9 |
| Buenas prácticas | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Código de verificación (4 casillas) | campo | Número (4 dígitos, uno por casilla). Solo dígitos 0-9; vigente 1 hora | Obligatorio: Sí. | Módulo 01: Actividad 2 |
| Código RC | campo | Código de la recomendación RC-{NNN}-{AAAA}-{NNN}. | Lo asigna el sistema; no corresponde al número de la recomendación en el documento. | Módulo 04: Actividad 1 |
| Confirmar Contraseña | campo | Texto oculto. Igual a Nueva Contraseña | Obligatorio: Sí. | Módulo 01: Actividad 1 |
| Contraseña | campo | Texto oculto. La contraseña vigente | Obligatorio: Sí. | Módulo 01: Actividad 2 |
| Correo electrónico | campo | Texto (correo). Formato de correo | Obligatorio: Sí. | Módulo 01: Actividad 2 |
| Creación: Manual / Automática | campo | Cómo se creó la alerta o la recomendación. | Las automáticas llegan desde otros sistemas o las crea el Agente IA. | Módulo 03: Actividad 1 |
| Dificultades | campo | Área de texto., | Obligatorio: No. | Módulo 05: Actividad 9 |
| Ejecutadas / Programadas | campo | Actividades ejecutadas frente a las programadas acumuladas. | Programadas suma el Número de actividades en cada ciclo. | Módulo 05: Actividad 1 |
| Entidad Principal | campo | Entidad responsable de la recomendación y de reportar el informe de ejecución. | Sus usuarios de Entidad Territorial ven la recomendación y reciben los correos. | Módulo 04: Actividad 1 |
| Entidades asociadas | campo | Entidades que apoyan una recomendación. | Reciben correo, pero no ven la recomendación. | Módulo 04: Actividad 1 |
| Fecha de inicio y fin (Fin de ejecución) | campo | Fecha. ≥ fecha de inicio | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Fecha de inicio y fin (Inicio ejecución) | campo | Fecha., | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Historial Plan de acción | campo | Eventos del plan de una alerta. | Permite ver confirmaciones y desconfirmaciones. | Módulo 05: Actividad 1 |
| Instrumento de planeación | campo | Selección única (Sí / No)., | Obligatorio: Sí. | Módulo 05: Actividad 5 |
| Nivel de acceso: Central / Subdirección | campo | Subdivisión del rol Entidad Territorial. | Central: entidad central; Subdirección: solo la subdirección elegida. | Módulo 01: Actividad 1 |
| Nueva Contraseña | campo | Texto oculto. Mínimo 8 caracteres y al menos un carácter especial | Obligatorio: Sí. | Módulo 01: Actividad 1 |
| Número de actividades | campo | Meta de la actividad por cada ciclo de 6 meses. | Se suma a lo programado en cada ciclo. | Módulo 05: Actividad 1 |
| Objetivo | campo | Área de texto. Mínimo 1 carácter; sin máximo | Obligatorio: Sí. | Módulo 05: Actividad 5 |
| Observaciones | campo | Área de texto. Sin límite | Obligatorio: No. | Módulo 05: Actividad 5 |
| Porcentaje de Avance Global | campo | Promedio del % de cumplimiento de las alertas no borrador del alcance. | Las alertas sin actividades cuentan como 0 %. | Módulo 02: Actividad 1 |
| Próximo Informe | campo | Fecha límite del siguiente informe de la actividad. | Se fija al aprobar un informe: notificación + 6 meses y luego +6; al vencer se abre un nuevo ciclo. | Módulo 05: Actividad 1 |
| Recursos | campo | Selección única (Sí / No)., | Obligatorio: Sí. | Módulo 05: Actividad 5 |
| Resultados | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí. | Módulo 05: Actividad 9 |
| Tema Clave | campo | Descripción de la alerta. | Aparece en la columna Tema. | Módulo 03: Actividad 1 |

### Catálogo

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Eje temático | catálogo | Lista de 14 ejes de las recomendaciones. | El servidor no valida contra la lista. | Módulo 04: Actividad 1 |
| Etiqueta: Nacional / Regional / Internacional | catálogo | Alcance territorial de la alerta. | Las etiquetas Focalizado y Binacional solo llegan de forma automática. | Módulo 03: Actividad 1 |
| Plazo de implementación | catálogo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente. | Solo informativo. | Módulo 05: Actividad 1 |
| Tipo de alerta: Inminencia / Estructural | catálogo | Clasificación de la alerta por su urgencia. | Inminencia se pinta en rojo y Estructural en azul en el mapa. | Módulo 03: Actividad 1 |

### Concepto

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Actividad | concepto | Acción que la entidad se compromete a ejecutar para una recomendación, con meta por semestre. | Se aprueba una por una y se reporta con informes de ejecución. | Módulo 05: Actividad 1 |
| Alerta temprana | concepto | Documento de la Defensoría del Pueblo que advierte un riesgo; en SI-CIPRAT es el registro central del ciclo. | Todo el trabajo (recomendaciones, plan, informes) cuelga de una alerta. | Módulo 03: Actividad 1 |
| Informe de ejecución | concepto | Reporte semestral de lo ejecutado en una actividad, con su PDF. | Lo aprueban el Monitor o el Líder; al aprobarlo se fija el próximo informe. | Módulo 05: Actividad 1 |
| Oficio de consumación | concepto | Documento de la Defensoría que informa que el riesgo se consumó. | Se asocia a alertas y puede modificar sus municipios. | Módulo 06: Actividad 1 |
| Plan de acción | concepto | Conjunto de actividades de todas las recomendaciones de una alerta. | Se confirma completo por alerta. | Módulo 05: Actividad 1 |
| Recomendación | concepto | Acción que la alerta pide a una Entidad Principal; tiene código RC. | La Entidad Principal le formula actividades. | Módulo 04: Actividad 1 |
| Subsunción | concepto | Una alerta nueva reemplaza a otras, que quedan cerradas. | Irreversible. | Módulo 03: Actividad 1 |

### Estado

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Activa | estado | Alerta vigente sobre la que se trabajan recomendaciones, planes e informes. | Se le cargan recomendaciones y actividades; puede editarse mientras el plan no esté confirmado. | Módulo 03: Actividad 1 |
| Aprobado | estado | Actividad aprobada; o plan con todas sus actividades aprobadas; o informe o reporte aprobado. | Una actividad aprobada no se edita; un plan Aprobado se puede confirmar; un informe aprobado no se edita. | Módulo 05: Actividad 1 |
| Aprobado - Sin Informe | estado | Opción del filtro de actividades: actividad aprobada sin informe del ciclo. | La entidad debe reportar el informe. | Módulo 05: Actividad 1 |
| Borrador | estado | Alerta creada por el Agente IA o recibida de forma automática que aún no se publica. | No cuenta en los indicadores; se revisa y se publica con "Publicar alerta al guardar". | Módulo 03: Actividad 1 |
| Cerrada | estado | Alerta terminada (por cierre, informe de seguimiento, subsunción o actualización automática). | No se edita ni se reabre; su plan y sus informes quedan en "Cerrado". | Módulo 03: Actividad 1 |
| Completado | estado | Informe que quedó cerrado al aprobar la actividad con un informe pendiente. | No se calcula el próximo informe en ese caso. | Módulo 05: Actividad 1 |
| Inactivo | estado | Usuario que no puede iniciar sesión ("Cuenta no activa"). | Puede reactivarse con el interruptor. | Módulo 01: Actividad 1 |
| Pendiente | estado | En el plan: hay actividades por aprobar. En el informe: hay informes por aprobar. | El Monitor o el Líder de Macrozona deben revisar y aprobar. | Módulo 05: Actividad 1 |
| Pendiente Aprobación | estado | Estado de una actividad recién formulada o devuelta. | La entidad puede editarla o eliminarla; el Monitor o el Líder pueden aprobarla. | Módulo 05: Actividad 1 |
| Plan de acción confirmado | estado | Plan cuya aprobación cerró el Monitor, el Líder o el Super Administrador con "Confirmar". | Habilita los informes de ejecución y bloquea la edición de la alerta, las recomendaciones y las actividades. | Módulo 05: Actividad 1 |
| Sin Completar | estado | Estado de informes de la alerta cuando hay actividades sin informe del ciclo. | Faltan informes por reportar. | Módulo 05: Actividad 1 |
| Sin Informe | estado | Actividad aprobada que aún no reporta el informe del ciclo. | La entidad puede usar "Reportar Informe". | Módulo 05: Actividad 1 |
| Sin plan | estado | Estado del plan cuando ninguna recomendación tiene actividades. | Debe formular las actividades de sus recomendaciones. | Módulo 05: Actividad 1 |
| Sin recomendaciones | estado | Estado del plan de una alerta que aún no tiene recomendaciones. | Se deben cargar recomendaciones (Super Administrador o Administrador). | Módulo 05: Actividad 1 |

### Mensaje

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Agregar actividad a plan confirmado: Al agregar una nueva actividad a la alerta … el plan de acción será desconfirmado automáticamente. … El estado del plan volverá a  | mensaje | Regla de desconfirmación automática. | Haga clic en **Continuar** solo si la actividad es necesaria; si no, **Cancelar**. | Módulo 05: Actividad 6 |
| Código de autenticación inválido | mensaje | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Módulo 01: Actividad 2 |
| Código expirado | mensaje | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Módulo 01: Actividad 2 |
| Conflicto con el estado actual del recurso. | mensaje | Otro usuario o una acción anterior cambió el estado del registro (409). | Actualice la página, revise el estado actual y repita la acción si todavía aplica. | Módulo 02: Actividad 3 |
| Credenciales inválidas | mensaje | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | Módulo 01: Actividad 2 |
| Cuenta no activa | mensaje | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | Módulo 01: Actividad 2 |
| Debe tener al menos 8 caracteres | mensaje | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Módulo 01: Actividad 1 |
| Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio. | mensaje | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Módulo 02: Actividad 3 |
| El archivo excede el tamaño máximo de {N} MB | mensaje | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Módulo 05: Actividad 9 |
| El contenido no puede exceder 2000 caracteres | mensaje | Límite de 2.000 caracteres o falla de conexión. | Divida el comentario en varios o intente de nuevo. | Módulo 05: Actividad 8 |
| El enlace de invitación es inválido. Verifica que el enlace esté completo. | mensaje | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | Módulo 01: Actividad 1 |
| El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador. | mensaje | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Módulo 01: Actividad 1 |
| El objetivo es requerido | mensaje | Faltan campos obligatorios. | Complete el Objetivo (Paso 1) y Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación y Recursos (Paso 2). | Módulo 05: Actividad 5 |
| El plan de acción debe estar confirmado para reportar informes | mensaje | Los informes solo se habilitan con el plan confirmado. | Espere el correo "Notificación validación Plan de Acción" o revise el estado del plan. | Módulo 05: Actividad 9 |
| El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose. | mensaje | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | Módulo 03: Actividad 2 |
| El servidor no está disponible. Por favor, intenta más tarde. | mensaje | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Espere unos minutos e intente de nuevo. | Módulo 02: Actividad 3 |
| Error al cargar alertas: No se pudieron cargar las alertas. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 03: Actividad 1 |
| Error al cargar datos | mensaje | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | Módulo 02: Actividad 1 |
| Error al cargar el informe de recomendaciones | mensaje | El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Pida el consolidado a la Secretaría Técnica o al Monitor. | Módulo 05: Actividad 1 |
| Error al cargar las actividades | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 05: Actividad 2 |
| Error al cargar las recomendaciones. Por favor, intente nuevamente. | mensaje | Falla del servicio. | Recargue la página. | Módulo 04: Actividad 1 |
| Error al cargar oficios: No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 06: Actividad 1 |
| Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo. | mensaje | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Módulo 03: Actividad 4 |
| Error al guardar el informe. Por favor, intente nuevamente. | mensaje | Falla del servicio o validación del servidor. | Lea el mensaje, corrija y vuelva a hacer clic en **Reportar informe de ejecución**. | Módulo 05: Actividad 9 |
| Error interno del servidor. Por favor, intenta más tarde. | mensaje | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | Módulo 03: Actividad 3 |
| La alerta solicitada no existe o ha sido eliminada. | mensaje | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | Módulo 03: Actividad 5 |
| La fecha de fin debe ser posterior a la fecha de inicio | mensaje | Rango de fechas inválido. | Corrija la fecha de inicio o de fin. | Módulo 05: Actividad 9 |
| La solicitud no es válida. Verifica los datos e intenta de nuevo. | mensaje | Errores 400 o 422 de validación. | Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. | Módulo 02: Actividad 3 |
| Las actividades ejecutadas son requeridas | mensaje | Faltan datos obligatorios del informe. | Complete los campos marcados y adjunte el PDF. | Módulo 05: Actividad 9 |
| Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente. | mensaje | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | Módulo 01: Actividad 1 |
| No hay datos de departamentos | mensaje | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | Módulo 02: Actividad 1 |
| No hay notificaciones | mensaje | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | Módulo 07: Actividad 1 |
| No puede ser mayor que {N} | mensaje | Lo ejecutado no puede superar el "Número de actividades" del ciclo. | Elija un número entre 0 y el número de actividades programadas; explique lo adicional en Acciones complementarias. | Módulo 05: Actividad 9 |
| No puedes reutilizar ninguna de tus últimas 5 contraseñas | mensaje | El sistema guarda el historial de contraseñas. | Elija una contraseña distinta de las 5 anteriores. | Módulo 01: Actividad 3 |
| No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo. | mensaje | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Módulo 03: Actividad 1 |
| No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo. | mensaje | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Módulo 01: Actividad 2 |
| No se puede editar la actividad porque el plan de acción ya fue confirmado | mensaje | Con el plan confirmado no se modifican actividades. | Si necesita una acción adicional, agréguela como actividad nueva (esto desconfirma el plan). | Módulo 05: Actividad 7 |
| No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe. | mensaje | La aprobación del informe es irreversible. | Espere la fecha del "Próximo Informe" para reportar el siguiente. | Módulo 05: Actividad 10 |
| No se puede editar porque la actividad ya está aprobada | mensaje | Las actividades aprobadas quedan bloqueadas. | Si debe corregirla, pida al Monitor o al Líder de Macrozona que use **Descartar aprobación** (solo si el plan no está confirmado). | Módulo 05: Actividad 7 |
| No se pueden agregar actividades a una alerta cerrada | mensaje | La alerta está cerrada. | No requiere acción. | Módulo 05: Actividad 5 |
| No tienes permisos para agregar recomendaciones | mensaje | Solo el Super Administrador y el Administrador las registran. | Pida el cambio a la Secretaría Técnica. | Módulo 04: Actividad 1 |
| No tienes permisos para cargar oficios | mensaje | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | Módulo 06: Actividad 1 |
| No tienes permisos para realizar esta acción. | mensaje | El servidor rechaza la operación para el rol (403). | Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. | Módulo 02: Actividad 3 |
| No tienes permisos para reportar alertas | mensaje | Su rol solo consulta alertas. | Pida el registro o la corrección a la Secretaría Técnica (Administrador o Super Administrador). | Módulo 03: Actividad 1 |
| Página no encontrada: Lo sentimos, la página que buscas no existe o ha sido movida. | mensaje | La ruta no existe. | Haga clic en **Volver al inicio** y navegue desde el menú. | Módulo 02: Actividad 3 |
| Plazo de implementación inválido: … | mensaje | Solo se aceptan 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente. | Elija una opción de la lista. | Módulo 05: Actividad 5 |
| Sesión cerrada por inactividad: Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente. | mensaje | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Módulo 01: Actividad 4 |
| Sesión expirada: Tu sesión ha expirado. Por favor, inicia sesión nuevamente. | mensaje | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | Módulo 01: Actividad 4 |
| Tipo de archivo no permitido. Solo se aceptan: .pdf | mensaje | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Módulo 05: Actividad 9 |
| Token inválido o expirado | mensaje | El enlace de restablecimiento vence en 1 hora. | Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. | Módulo 01: Actividad 3 |
| Tu organización está suspendida. Por favor contacta al administrador. | mensaje | La entidad guardada en su usuario no está en estado Activa. | Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. | Módulo 01: Actividad 2 |

### Menú o pestaña

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Alertas / Recomendaciones / Actividades | menú o pestaña | Pestañas de Planes de acción y Seguimiento. | Abre la vista correspondiente. | Módulo 05: Actividad 1 |
| Alertas tempranas | menú o pestaña | Registro y consulta de las alertas. | Abre la vista correspondiente. | Módulo 03: Actividad 1 |
| Cerrar sesión | menú o pestaña | Termina la sesión. | Abre la vista correspondiente. | Módulo 01: Actividad 1 |
| Historial de actividades | menú o pestaña | Línea de tiempo de acciones sobre una alerta. | Abre la vista correspondiente. | Módulo 03: Actividad 1 |
| Información / Actividades / Historial | menú o pestaña | Pestañas del detalle de una recomendación en el plan. | Abre la vista correspondiente. | Módulo 05: Actividad 1 |
| Inicio | menú o pestaña | Tablero de indicadores, mapa y alertas recientes. | Abre la vista correspondiente. | Módulo 02: Actividad 1 |
| Notificaciones | menú o pestaña | Panel con el historial de actividad de su alcance. | Abre la vista correspondiente. | Módulo 07: Actividad 1 |
| Oficios de consumación | menú o pestaña | Oficios de consumación del riesgo. | Abre la vista correspondiente. | Módulo 06: Actividad 1 |
| Planes de acción | menú o pestaña | Formulación de actividades e informes de ejecución. | Abre la vista correspondiente. | Módulo 05: Actividad 1 |
| Todas / Inminencia / Estructurales | menú o pestaña | Pestañas del listado de alertas por tipo. | Abre la vista correspondiente. | Módulo 03: Actividad 1 |
| Ver Perfil | menú o pestaña | Acceso a Mi perfil. | Abre la vista correspondiente. | Módulo 01: Actividad 1 |

### Rol

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| Administrador | rol | Acceso nacional para visualizar alertas y gestionar planes de acción. No puede eliminar alertas ni aprobar actividades. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Consulta Departamentos | rol | Solo lectura filtrado por departamentos asignados. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Consulta Entidad | rol | Solo lectura filtrado por su entidad asignada. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Consulta Global | rol | Solo lectura a nivel nacional (sin modificar datos). (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Entidad Territorial | rol | Gestiona actividades e informes de ejecución de su entidad/subdirección. No puede aprobar. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Líder de Macrozona | rol | Supervisa alertas en departamentos asignados. Acceso total a reportes de ejecución. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Monitor | rol | Acceso departamental. Puede aprobar actividades e informes en Seguimiento. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |
| Super Administrador | rol | Acceso total a la plataforma sin restricciones. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 01: Actividad 1 |

### Sigla

| Término | Tipo | Significado | Qué implica para el usuario de Entidad Territorial (Subdirección) | Dónde lo verá |
|---|---|---|---|---|
| AT | sigla | Prefijo del número de alerta temprana (AT-XXX-XXXX). | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| CAT | sigla | Categoría municipal según la Contaduría General de la Nación (ESP, 1 a 6, N/A). | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| CIPRAT | sigla | Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas. | Aparece en pantallas y documentos de la ruta. | Módulo 01: Actividad 1 |
| CSV | sigla | Archivo de texto separado por comas que se abre en Excel. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| D.I.H. | sigla | Derecho Internacional Humanitario (paso 4 de la alerta). | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| DANE / Cod DANE | sigla | Código del municipio (5 dígitos) del DANE. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| PDET | sigla | Programa de Desarrollo con Enfoque Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| PDF | sigla | Único formato de archivo aceptado para los soportes. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| PNIS | sigla | Programa Nacional Integral de Sustitución de Cultivos de Uso Ilícito. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |
| RC | sigla | Prefijo del código de la recomendación. | Aparece en pantallas y documentos de la ruta. | Módulo 04: Actividad 1 |
| SI-CIPRAT | sigla | Sistema de Información de la Secretaría Técnica CIPRAT. | Aparece en pantallas y documentos de la ruta. | Módulo 01: Actividad 1 |
| Zona Fut. | sigla | Zona del Formulario Único Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 03: Actividad 1 |

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
| 07 Notificaciones | 1. Consultar el panel de Notificaciones | 3 | F-NOT-01, F-NOT-02, F-NOT-03 | dashboard/src/components/notifications/NotificationsPanel.tsx:30-113; dashboard/src/components/notifications/NotificationsPanel.tsx:128; dashboard/src/components/ui/ActivityList.tsx:77 |
| 07 Notificaciones | 2. Reconocer los correos que envía el sistema y qué hacer con cada uno | 3 | F-NOT-04, F-NOT-05, F-NOT-06, F-NOT-07, F-NOT-08, F-NOT-09, F-NOT-10, F-NOT-11, F-NOT-12, F-TAR-02, F-INT-02 | main-api/CipratApi/Servicios/EmailService.cs:62; main-api/CipratApi/Servicios/EmailService.cs:38; main-api/CipratApi/Servicios/EmailService.cs:92 |
| 03 Alertas tempranas | 1. Consultar, buscar y filtrar alertas tempranas | 6 | F-ALE-01, F-ALE-02, F-ALE-03, F-INT-01 | main-api/CipratApi/Controladores/AlertasControlador.cs:87; dashboard/src/components/alertas-tempranas/AlertasTab.tsx:294; dashboard/src/components/alertas-tempranas/AlertFiltersModal.tsx:216-420 |
| 03 Alertas tempranas | 2. Ver el detalle de una alerta y descargar su PDF | 5 | F-ALE-04, F-ALE-05 | dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx:13-340; main-api/CipratApi/Controladores/ArchivosControlador.cs:135-170 |
| 03 Alertas tempranas | 3. Consultar el historial de actividades de una alerta | 3 | F-ALE-06 | main-api/CipratApi/Controladores/AlertasControlador.cs:627-700 |
| 03 Alertas tempranas | 4. Descargar el listado de alertas en CSV | 2 | F-ALE-07 | main-api/CipratApi/Controladores/AlertasControlador.cs:1004-1087 |
| 03 Alertas tempranas | 5. Ir a las recomendaciones de una alerta | 2 | F-REC-01 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41 |
| 04 Recomendaciones | 1. Consultar, buscar y filtrar las recomendaciones de una alerta | 4 | F-REC-01, F-REC-02, F-REC-08 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41; dashboard/src/components/recomendaciones/RecomendacionFiltersModal.tsx:198-344; main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:516-540 |
| 04 Recomendaciones | 2. Ver el detalle de una recomendación | 2 | F-REC-03 | dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx:84-207 |
| 04 Recomendaciones | 3. Descargar las recomendaciones de una alerta en CSV | 2 | F-REC-04 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566 |
| 05 Planes de acción | 1. Consultar y filtrar los planes de acción por alerta | 5 | F-PLA-01, F-PLA-02, F-PLA-03, F-PLA-04 | dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:139-334; dashboard/src/components/planes-de-accion/ActionPlanFiltersModal.tsx:119-243; dashboard/src/components/planes-de-accion/ActionPlanDetailModal.tsx:96-106 |
| 05 Planes de acción | 2. Recorrer las recomendaciones del plan de una alerta | 3 | F-PLA-05 | dashboard/src/components/planes-de-accion/PlanDeAccionRecomendacionesTab.tsx:137-245 |
| 05 Planes de acción | 3. Consultar las pestañas globales de Recomendaciones y Actividades | 3 | F-PLA-06, F-PLA-07, F-PLA-10 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:343; main-api/CipratApi/Servicios/ServicioActividades.cs:476-497; main-api/CipratApi/Controladores/ActividadesControlador.cs:496-560 |
| 05 Planes de acción | 4. Consultar las actividades de una recomendación y su detalle | 4 | F-PLA-08, F-PLA-09, F-PLA-10, F-TAR-01, F-TAR-03, F-TAR-04 | dashboard/src/pages/ActividadesRecomendacion.tsx:96-110; dashboard/src/components/planes-de-accion/ActividadDetailModal.tsx:73-163; main-api/CipratApi/Controladores/ActividadesControlador.cs:496-560 |
| 05 Planes de acción | 5. Agregar una actividad al plan de acción | 9 | F-PLA-11, F-TAR-03 | main-api/CipratApi/Controladores/ActividadesControlador.cs:103-135; main-api/CipratApi/Servicios/ServicioActividades.cs:928-966 |
| 05 Planes de acción | 6. Agregar una actividad a un plan ya confirmado | 4 | F-PLA-12 | main-api/CipratApi/Servicios/ServicioActividades.cs:132-137 |
| 05 Planes de acción | 7. Editar o eliminar una actividad pendiente | 3 | F-PLA-13, F-PLA-14 | main-api/CipratApi/Controladores/ActividadesControlador.cs:176-210; main-api/CipratApi/Controladores/ActividadesControlador.cs:245-270 |
| 05 Planes de acción | 8. Comentar una actividad y atender los comentarios de la revisión | 3 | F-PLA-15 | main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:33-83 |
| 05 Planes de acción | 9. Reportar un informe de ejecución | 9 | F-PLA-17, F-TAR-01, F-TAR-04 | main-api/CipratApi/Controladores/InformesEjecucionControlador.cs:35-41; main-api/CipratApi/Servicios/ServicioTareasWorker.cs:27-140; main-api/CipratApi/Servicios/ServicioInformesEjecucion.cs:337-352 |
| 05 Planes de acción | 10. Editar un informe de ejecución pendiente | 3 | F-PLA-18 | main-api/CipratApi/Controladores/InformesEjecucionControlador.cs:99-105 |
| 05 Planes de acción | 11. Consultar los informes de ejecución de una actividad y descargar su PDF | 3 | F-PLA-19 | dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:523-795 |
| 06 Oficios de consumación | 1. Consultar los oficios de consumación y descargar su PDF | 3 | F-OFI-01, F-OFI-02, F-OFI-03, F-OFI-04, F-INT-03 | main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:47-95; dashboard/src/components/oficios-consumacion/OficiosFiltersModal.tsx:97-134; dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx:102-196 |

### Diferencias con la versión anterior de la Academia

Se comparó con `Refenrence/plan_capacitacion/06_rol_entidad_territorial_subdireccion.md` de la Academia (7 módulos, 0 actividades) y con ROLES & PERMISOS-2-3.xlsx (detalle en `analisis/02c_comparacion_academia_xlsx.md`). Diferencias principales, contrastadas con el código:

- Los roles y subroles de esta versión salen del código; la Academia los toma como lista de 8 roles. Esta ruta corresponde a: `06_rol_entidad_territorial_subdireccion.md` de la Academia.
- La Academia lista los campos de la actividad como nombre, responsable, fecha estimada y descripción; el código tiene Objetivo, Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación (Sí/No), Recursos (Sí/No) y Observaciones (`dashboard/src/components/planes-de-accion/ActividadFormStep2.tsx`).
- Código de verificación: 4 dígitos (`main-api/CipratApi/Servicios/ServicioAutenticacion.cs:41`), con vigencia de 1 hora; sesión de 720 minutos y cierre por inactividad a los 60 minutos.
- La Academia tiene una sección "Diferencias frente al rol Entidad Territorial Central" (`06_rol_entidad_territorial_subdireccion.md:63`); esta ruta explica su propio alcance sin remitir a otra ruta.
- El aviso de los 5 meses que menciona la Academia corresponde en el código a un recordatorio cuando faltan 30 días o menos para el próximo informe, y solo llega a la Entidad Territorial (`main-api/CipratApi/Servicios/ServicioTareasWorker.cs:145-220`).

### Vacíos (NO ENCONTRADO EN CÓDIGO)

- Fecha límite para el primer informe de ejecución: el próximo informe solo se fija al aprobar el primer informe (`main-api/CipratApi/Servicios/ServicioInformesEjecucion.cs:337-346`).
- Servicio para eliminar informes de ejecución (permiso definido sin endpoint; `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191`).
- Pantallas para cambiar la contraseña con la actual, editar el propio perfil y borrar comentarios (los servicios existen en la API; ninguna pantalla los usa).

### Apoyos visuales de la ruta

| ID | Tipo | Dónde va | Título |
|---|---|---|---|
| MED-06-ACC-01 | Captura | 01 Acceso a la plataforma · Actividad 1: Activar la cuenta desde la invitación | Pantalla "Configura tu contraseña" |
| MED-06-ACC-02 | Captura | 01 Acceso a la plataforma · Actividad 1: Activar la cuenta desde la invitación · Escenario ERR-ACC-06 | Mensaje ERR-ACC-06 |
| MED-06-ACC-03 | Captura | 01 Acceso a la plataforma · Actividad 1: Activar la cuenta desde la invitación · Escenario ERR-ACC-07 | Mensaje ERR-ACC-07 |
| MED-06-ACC-04 | Captura | 01 Acceso a la plataforma · Actividad 1: Activar la cuenta desde la invitación · Escenario ERR-ACC-08 | Mensaje ERR-ACC-08 |
| MED-06-ACC-05 | Captura | 01 Acceso a la plataforma · Actividad 1: Activar la cuenta desde la invitación · Escenario ERR-ACC-09 | Mensaje ERR-ACC-09 |
| MED-06-ACC-06 | GIF | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación | Ingreso con código de verificación |
| MED-06-ACC-07 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-ACC-01 | Mensaje ERR-ACC-01 |
| MED-06-ACC-08 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-ACC-02 | Mensaje ERR-ACC-02 |
| MED-06-ACC-09 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-ACC-03 | Mensaje ERR-ACC-03 |
| MED-06-ACC-10 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-ACC-04 | Mensaje ERR-ACC-04 |
| MED-06-ACC-11 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-ACC-05 | Mensaje ERR-ACC-05 |
| MED-06-ACC-12 | Captura | 01 Acceso a la plataforma · Actividad 2: Iniciar sesión con el código de verificación · Escenario ERR-GEN-06 | Mensaje ERR-GEN-06 |
| MED-06-ACC-13 | GIF | 01 Acceso a la plataforma · Actividad 3: Recuperar la contraseña | Recuperación de la contraseña |
| MED-06-ACC-14 | Captura | 01 Acceso a la plataforma · Actividad 3: Recuperar la contraseña · Escenario ERR-ACC-10 | Mensaje ERR-ACC-10 |
| MED-06-ACC-15 | Captura | 01 Acceso a la plataforma · Actividad 3: Recuperar la contraseña · Escenario ERR-ACC-11 | Mensaje ERR-ACC-11 |
| MED-06-ACC-16 | Captura | 01 Acceso a la plataforma · Actividad 4: Cerrar sesión y entender el cierre automático | Menú del usuario |
| MED-06-ACC-17 | Captura | 01 Acceso a la plataforma · Actividad 4: Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-12 | Mensaje ERR-ACC-12 |
| MED-06-ACC-18 | Captura | 01 Acceso a la plataforma · Actividad 4: Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-13 | Mensaje ERR-ACC-13 |
| MED-06-ACC-19 | Captura | 01 Acceso a la plataforma · Actividad 5: Consultar los Términos de uso y contactar al soporte técnico | Términos de uso |
| MED-06-ACC-20 | Captura | 01 Acceso a la plataforma · Actividad 6: Consultar Mi perfil y verificar el alcance asignado | Mi perfil |
| MED-06-INI-01 | Captura | 02 Inicio · Actividad 1: Leer los indicadores del Inicio | Indicadores del Inicio |
| MED-06-INI-02 | Captura | 02 Inicio · Actividad 1: Leer los indicadores del Inicio · Escenario ERR-INI-01 | Mensaje ERR-INI-01 |
| MED-06-INI-03 | Captura | 02 Inicio · Actividad 1: Leer los indicadores del Inicio · Escenario ERR-INI-02 | Mensaje ERR-INI-02 |
| MED-06-INI-04 | Captura | 02 Inicio · Actividad 2: Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa | Mapa y ranking del Inicio |
| MED-06-INI-05 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad | Menú lateral del rol |
| MED-06-INI-06 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-12 | Mensaje ERR-GEN-12 |
| MED-06-INI-07 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-11 | Mensaje ERR-GEN-11 |
| MED-06-INI-08 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-01 | Mensaje ERR-GEN-01 |
| MED-06-INI-09 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-03 | Mensaje ERR-GEN-03 |
| MED-06-INI-10 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-05 | Mensaje ERR-GEN-05 |
| MED-06-INI-11 | Captura | 02 Inicio · Actividad 3: Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-13 | Mensaje ERR-GEN-13 |
| MED-06-INI-12 | Captura | 02 Inicio · Actividad 4: Consultar el tablero público sin iniciar sesión | Tablero público |
| MED-06-ALE-01 | Captura | 03 Alertas tempranas · Actividad 1: Consultar, buscar y filtrar alertas tempranas | Listado de alertas |
| MED-06-ALE-02 | Captura | 03 Alertas tempranas · Actividad 1: Consultar, buscar y filtrar alertas tempranas · Escenario ERR-ALE-17 | Mensaje ERR-ALE-17 |
| MED-06-ALE-03 | Captura | 03 Alertas tempranas · Actividad 1: Consultar, buscar y filtrar alertas tempranas · Escenario ERR-ALE-19 | Mensaje ERR-ALE-19 |
| MED-06-ALE-04 | Captura | 03 Alertas tempranas · Actividad 1: Consultar, buscar y filtrar alertas tempranas · Escenario ERR-GEN-07 | Mensaje ERR-GEN-07 |
| MED-06-ALE-05 | Captura | 03 Alertas tempranas · Actividad 2: Ver el detalle de una alerta y descargar su PDF | Detalle de la alerta |
| MED-06-ALE-06 | Captura | 03 Alertas tempranas · Actividad 2: Ver el detalle de una alerta y descargar su PDF · Escenario ERR-GEN-02 | Mensaje ERR-GEN-02 |
| MED-06-ALE-07 | Captura | 03 Alertas tempranas · Actividad 3: Consultar el historial de actividades de una alerta | Historial de actividades |
| MED-06-ALE-08 | Captura | 03 Alertas tempranas · Actividad 3: Consultar el historial de actividades de una alerta · Escenario ERR-GEN-04 | Mensaje ERR-GEN-04 |
| MED-06-ALE-09 | Captura | 03 Alertas tempranas · Actividad 4: Descargar el listado de alertas en CSV | Botón Descargar |
| MED-06-ALE-10 | Captura | 03 Alertas tempranas · Actividad 4: Descargar el listado de alertas en CSV · Escenario ERR-GEN-10 | Mensaje ERR-GEN-10 |
| MED-06-ALE-11 | Captura | 03 Alertas tempranas · Actividad 5: Ir a las recomendaciones de una alerta | Menú ⋯ de la alerta |
| MED-06-ALE-12 | Captura | 03 Alertas tempranas · Actividad 5: Ir a las recomendaciones de una alerta · Escenario ERR-REC-08 | Mensaje ERR-REC-08 |
| MED-06-REC-01 | Captura | 04 Recomendaciones · Actividad 1: Consultar, buscar y filtrar las recomendaciones de una alerta | Recomendaciones de una alerta |
| MED-06-REC-02 | Captura | 04 Recomendaciones · Actividad 1: Consultar, buscar y filtrar las recomendaciones de una alerta · Escenario ERR-REC-06 | Mensaje ERR-REC-06 |
| MED-06-REC-03 | Captura | 04 Recomendaciones · Actividad 1: Consultar, buscar y filtrar las recomendaciones de una alerta · Escenario ERR-REC-07 | Mensaje ERR-REC-07 |
| MED-06-REC-04 | Captura | 04 Recomendaciones · Actividad 2: Ver el detalle de una recomendación | Detalle de recomendación |
| MED-06-REC-05 | Captura | 04 Recomendaciones · Actividad 3: Descargar las recomendaciones de una alerta en CSV | CSV de recomendaciones |
| MED-06-PLA-01 | Captura | 05 Planes de acción · Actividad 1: Consultar y filtrar los planes de acción por alerta | Planes de acción por alerta |
| MED-06-PLA-02 | Captura | 05 Planes de acción · Actividad 1: Consultar y filtrar los planes de acción por alerta · Escenario ERR-PLA-17 | Mensaje ERR-PLA-17 |
| MED-06-PLA-03 | Captura | 05 Planes de acción · Actividad 2: Recorrer las recomendaciones del plan de una alerta | Recomendaciones del plan |
| MED-06-PLA-04 | Captura | 05 Planes de acción · Actividad 2: Recorrer las recomendaciones del plan de una alerta · Escenario ERR-PLA-15 | Mensaje ERR-PLA-15 |
| MED-06-PLA-05 | Captura | 05 Planes de acción · Actividad 3: Consultar las pestañas globales de Recomendaciones y Actividades | Pestaña global Actividades |
| MED-06-PLA-06 | Captura | 05 Planes de acción · Actividad 4: Consultar las actividades de una recomendación y su detalle | Actividades de una recomendación |
| MED-06-PLA-07 | GIF | 05 Planes de acción · Actividad 5: Agregar una actividad al plan de acción | Agregar actividad |
| MED-06-PLA-08 | Captura | 05 Planes de acción · Actividad 5: Agregar una actividad al plan de acción · Escenario ERR-PLA-01 | Mensaje ERR-PLA-01 |
| MED-06-PLA-09 | Captura | 05 Planes de acción · Actividad 5: Agregar una actividad al plan de acción · Escenario ERR-PLA-02 | Mensaje ERR-PLA-02 |
| MED-06-PLA-10 | Captura | 05 Planes de acción · Actividad 5: Agregar una actividad al plan de acción · Escenario ERR-PLA-07 | Mensaje ERR-PLA-07 |
| MED-06-PLA-11 | Captura | 05 Planes de acción · Actividad 6: Agregar una actividad a un plan ya confirmado | Agregar actividad a plan confirmado |
| MED-06-PLA-12 | Captura | 05 Planes de acción · Actividad 6: Agregar una actividad a un plan ya confirmado · Escenario ERR-PLA-05 | Mensaje ERR-PLA-05 |
| MED-06-PLA-13 | Captura | 05 Planes de acción · Actividad 7: Editar o eliminar una actividad pendiente | Botones deshabilitados en actividad aprobada |
| MED-06-PLA-14 | Captura | 05 Planes de acción · Actividad 7: Editar o eliminar una actividad pendiente · Escenario ERR-PLA-03 | Mensaje ERR-PLA-03 |
| MED-06-PLA-15 | Captura | 05 Planes de acción · Actividad 7: Editar o eliminar una actividad pendiente · Escenario ERR-PLA-04 | Mensaje ERR-PLA-04 |
| MED-06-PLA-16 | Captura | 05 Planes de acción · Actividad 8: Comentar una actividad y atender los comentarios de la revisión | Comentarios de la actividad |
| MED-06-PLA-17 | Captura | 05 Planes de acción · Actividad 8: Comentar una actividad y atender los comentarios de la revisión · Escenario ERR-PLA-08 | Mensaje ERR-PLA-08 |
| MED-06-PLA-18 | GIF | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución | Reportar informe de ejecución |
| MED-06-PLA-19 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-PLA-09 | Mensaje ERR-PLA-09 |
| MED-06-PLA-20 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-PLA-10 | Mensaje ERR-PLA-10 |
| MED-06-PLA-21 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-PLA-11 | Mensaje ERR-PLA-11 |
| MED-06-PLA-22 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-PLA-12 | Mensaje ERR-PLA-12 |
| MED-06-PLA-23 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-PLA-14 | Mensaje ERR-PLA-14 |
| MED-06-PLA-24 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-GEN-08 | Mensaje ERR-GEN-08 |
| MED-06-PLA-25 | Captura | 05 Planes de acción · Actividad 9: Reportar un informe de ejecución · Escenario ERR-GEN-09 | Mensaje ERR-GEN-09 |
| MED-06-PLA-26 | Captura | 05 Planes de acción · Actividad 10: Editar un informe de ejecución pendiente | Editar informe bloqueado |
| MED-06-PLA-27 | Captura | 05 Planes de acción · Actividad 10: Editar un informe de ejecución pendiente · Escenario ERR-PLA-13 | Mensaje ERR-PLA-13 |
| MED-06-PLA-28 | Captura | 05 Planes de acción · Actividad 11: Consultar los informes de ejecución de una actividad y descargar su PDF | Informes de ejecución |
| MED-06-OFI-01 | Captura | 06 Oficios de consumación · Actividad 1: Consultar los oficios de consumación y descargar su PDF | Oficios de consumación |
| MED-06-OFI-02 | Captura | 06 Oficios de consumación · Actividad 1: Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-02 | Mensaje ERR-OFI-02 |
| MED-06-OFI-03 | Captura | 06 Oficios de consumación · Actividad 1: Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-05 | Mensaje ERR-OFI-05 |
| MED-06-NOT-01 | Captura | 07 Notificaciones · Actividad 1: Consultar el panel de Notificaciones | Panel Notificaciones |
| MED-06-NOT-02 | Captura | 07 Notificaciones · Actividad 1: Consultar el panel de Notificaciones · Escenario ERR-NOT-01 | Mensaje ERR-NOT-01 |
| MED-06-NOT-03 | Captura | 07 Notificaciones · Actividad 2: Reconocer los correos que envía el sistema y qué hacer con cada uno | Correo del sistema |
