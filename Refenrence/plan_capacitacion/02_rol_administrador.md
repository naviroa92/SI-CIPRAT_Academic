Generado desde: monorepo SI-CIPRAT rama develop commit 56d3f33 (2026-07-17 10:20:06 -0500) · 2026-10-28

# Ruta 02 · Administrador

## Ficha de la ruta

| Campo | Valor |
|---|---|
| Número | 02 |
| Rol | Administrador |
| Subrol | No aplica |
| Alcance | Nacional · gestión operativa |
| Descripción corta | Registra alertas, crea recomendaciones, carga informes de seguimiento y reportes de ejecución, y administra usuarios y entidades. |
| Módulos | 14 |
| Modalidad | Autoaprendizaje |
| Prerrequisitos de la ruta | Cuenta activa con rol Administrador. |

## Definición del rol

Rol de gestión operativa nacional. Registra y edita alertas, crea y edita recomendaciones, carga y edita informes de seguimiento, carga reportes de ejecución y administra usuarios y entidades. No elimina alertas ni recomendaciones, no cierra alertas, no aprueba actividades, informes ni reportes y no sube archivos de la alerta. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:30-68,83-97,140-153,193-199,254-262`.

**Criterio técnico:** Valor `ADMINISTRADOR` del enumerado `RolUsuario`. Sin subroles.

**Quién lo ocupa:** [INFERIDO] Profesionales de la Secretaría Técnica de la CIPRAT que operan el registro de alertas y recomendaciones. Base: el texto de ayuda del formulario de usuarios lo describe como "Acceso nacional para visualizar alertas y gestionar planes de acción" (`dashboard/src/components/ui/UserFormModal.tsx:425`) y la matriz le da crear y editar alertas, recomendaciones, informes de seguimiento, usuarios y entidades (`main-api/CipratApi/Servicios/ServicioPermisos.cs:30-68,83-92,271-285`).

**Cómo se asigna:** Lo asigna un Super Administrador o un Administrador al invitar al usuario en *Usuarios y entidades* (`main-api/CipratApi/Controladores/UsuariosControlador.cs:63-69`). La **Entidad Central** es opcional para este rol (`dashboard/src/components/ui/UserFormModal.tsx:564-570`); no exige departamentos ni cargo.

## Objetivo de capacitación

Al terminar esta ruta, el Administrador podrá administrar entidades, subdirecciones, usuarios e invitaciones, registrar y editar alertas tempranas, publicar borradores, subsumir alertas, crear y editar recomendaciones con sus entidades principales y asociadas, consultar los planes de acción y su seguimiento, cargar informes de seguimiento y reportes de ejecución, generar informes ejecutivos y consultar el historial y las notificaciones, conociendo lo que el sistema le impide hacer y a quién acudir en cada caso.

## Permisos por módulo

| Módulo | Acciones disponibles |
|---|---|
| Acceso a la plataforma | Iniciar sesión con correo y contraseña; Validar el código de verificación; Reenviar el código de verificación; Activar la cuenta desde la invitación; Solicitar el restablecimiento de la contraseña; Restablecer la contraseña con el enlace; Cerrar sesión; Cierre automático de la sesión por inactividad o vencimiento; Consultar los Términos de uso; Contactar al soporte técnico; Consultar Mi perfil |
| Inicio | Consultar los indicadores del Inicio; Consultar la última alerta emitida; Consultar "Alertas por departamento" (Top 10); Consultar "Alertas recientes"; Consultar el "Porcentaje de Avance Global"; Consultar el mapa de municipios con alertas; Consultar el tablero público sin iniciar sesión; Usar el panel de accesibilidad; Usar el menú lateral |
| Usuarios y entidades | Listar usuarios e invitaciones; Buscar y filtrar usuarios; Ver el detalle de un usuario; Invitar un usuario; Editar un usuario; Activar o inactivar un usuario; Reenviar una invitación; Eliminar una invitación; Listar entidades centrales y subdirecciones; Buscar y filtrar entidades; Ver el detalle de una entidad; Ver los usuarios asignados a una entidad; Agregar una entidad con sus subdirecciones; Editar una entidad y sus subdirecciones; Eliminar una entidad |
| Alertas tempranas | Listar alertas; Buscar alertas; Filtrar alertas; Ver el detalle de una alerta; Descargar el PDF de la alerta; Consultar el historial de actividades de la alerta; Descargar el listado de alertas (CSV); Reportar una alerta temprana; Editar una alerta; Publicar una alerta en borrador; Subsumir otras alertas |
| Recomendaciones | Listar las recomendaciones de una alerta; Buscar y filtrar recomendaciones; Ver el detalle de una recomendación; Descargar las recomendaciones (CSV); Agregar una recomendación; Editar una recomendación; Asignar el código RC (consulta) |
| Planes de acción | Listar las alertas con plan de acción; Buscar y filtrar planes de acción; Ver el detalle y el historial del plan de una alerta; Descargar el listado de planes (CSV); Ver las recomendaciones del plan de una alerta; Consultar la pestaña global de Recomendaciones; Consultar la pestaña global de Actividades; Listar las actividades de una recomendación; Ver el detalle de una actividad; Descargar las actividades (CSV); Consultar los informes de ejecución y descargar su PDF |
| Seguimiento | Listar los planes en Seguimiento; Buscar y filtrar planes en Seguimiento; Descargar el listado de Seguimiento (CSV); Consultar recomendaciones, actividades e informes en Seguimiento |
| Informe de recomendaciones | Consultar el Informe de recomendaciones; Filtrar el Informe de recomendaciones por alerta |
| Reportes | Listar los reportes de ejecución; Buscar y filtrar reportes; Ver el detalle de un reporte; Descargar un reporte; Cargar un reporte de ejecución; Editar un reporte de ejecución; Generar un informe ejecutivo en Word (Panel de consultas) |
| Informes de seguimiento | Listar los informes de seguimiento; Buscar y filtrar informes por alerta; Ver el detalle de un informe de seguimiento; Descargar el PDF del informe de seguimiento; Cargar un informe de seguimiento; Modificar municipios y agregar recomendaciones desde el informe; Editar un informe de seguimiento |
| Oficios de consumación | Listar los oficios de consumación; Buscar y filtrar oficios por alerta; Ver el detalle de un oficio; Descargar el PDF del oficio |
| Notificaciones | Abrir el panel de Notificaciones; Buscar en el panel de Notificaciones; Cargar más notificaciones; Recibir el correo de invitación; Recibir el correo con el código de verificación; Recibir el correo de restablecimiento de contraseña |
| Interoperabilidad X-Road (SISAT) | Recibir alertas tempranas por X-Road (consulta); Recibir informes de seguimiento por X-Road (consulta); Recibir oficios de consumación por X-Road (consulta) |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (consulta); Recalcular estados y porcentajes de cumplimiento (consulta); Calcular el próximo informe al aprobar un informe (consulta) |

## Matriz de capacidades en la plataforma

Fuente: `analisis/09_capacidades_ADM.md`. Total de funcionalidades: 145 | Puede: 93 | Puede con restricción: 0 | Solo consulta: 7 | No puede: 45.

### Qué SÍ puede hacer el Administrador

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
| Inicio | Consultar los indicadores del Inicio (F-INI-01) ✔ | Muestra Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales y Alertas cerradas, con la tendencia "vs ultimo mes". | R | Sin restricción adicional | Módulo 02 — Actividad 1 |
| Inicio | Consultar la última alerta emitida (F-INI-02) ✔ | Muestra el banner "Se ha emitido la Alerta Temprana…" con la alerta activa más reciente y el botón **Ver Alerta**. | R | Sin restricción adicional | Módulo 02 — Actividad 2 |
| Inicio | Consultar "Alertas por departamento" (Top 10) (F-INI-03) ✔ | Ranking de los 10 departamentos con más alertas y su porcentaje del total. | R | Sin restricción adicional | Módulo 02 — Actividad 2 |
| Inicio | Consultar "Alertas recientes" (F-INI-04) ✔ | Lista las 9 alertas más recientes por fecha de la alerta. | R | Sin restricción adicional | Módulo 02 — Actividad 2 |
| Inicio | Consultar el "Porcentaje de Avance Global" (F-INI-05) ✔ | Promedio del porcentaje de cumplimiento de las alertas (no borradores) y total de actividades ejecutadas frente a programadas. | R | Sin restricción adicional | Módulo 02 — Actividad 1 |
| Inicio | Consultar el mapa de municipios con alertas (F-INI-06) ✔ | Mapa de Colombia con los municipios que tienen alertas (rojo: inminencia; azul: estructural) y tabla accesible con los mismos datos. | R | Sin restricción adicional | Módulo 02 — Actividad 2 |
| Inicio | Consultar el tablero público sin iniciar sesión (F-INI-07) ✔ | La página de inicio pública (`/`) muestra los mismos bloques con la información nacional, sin filtro de rol. | R | Sin restricción adicional | Módulo 02 — Actividad 4 |
| Inicio | Usar el panel de accesibilidad (F-INI-08) ✔ | Activa o desactiva el alto contraste y aumenta o reduce el tamaño de letra. | U | Sin restricción adicional | Módulo 02 — Actividad 3 |
| Inicio | Usar el menú lateral (F-INI-09) ✔ | Navega entre los módulos visibles para el rol; el menú se puede ocultar. | R | Sin restricción adicional | Módulo 02 — Actividad 3 |
| Notificaciones | Abrir el panel de Notificaciones (F-NOT-01) ✔ | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Sin restricción adicional | Módulo 12 — Actividad 1 |
| Notificaciones | Buscar en el panel de Notificaciones (F-NOT-02) ✔ | Filtra el historial por texto. | R | Sin restricción adicional | Módulo 12 — Actividad 1 |
| Notificaciones | Cargar más notificaciones (F-NOT-03) ✔ | Trae 10 registros más del historial. | R | Sin restricción adicional | Módulo 12 — Actividad 1 |
| Notificaciones | Recibir el correo de invitación (F-NOT-04) ✔ | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Sin restricción adicional | Módulo 01 — Actividad 1; Módulo 12 — Actividad 2 |
| Notificaciones | Recibir el correo con el código de verificación (F-NOT-05) ✔ | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Sin restricción adicional | Módulo 01 — Actividad 2; Módulo 12 — Actividad 2 |
| Notificaciones | Recibir el correo de restablecimiento de contraseña (F-NOT-06) ✔ | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Sin restricción adicional | Módulo 01 — Actividad 3; Módulo 12 — Actividad 2 |
| Usuarios y entidades | Listar usuarios e invitaciones (F-USU-01) ✔ | Muestra los usuarios activos e inactivos y las invitaciones, con las pestañas Todos, Entidades Territoriales, Administradores, Monitores e Invitaciones. | R | Sin restricción adicional | Módulo 03 — Actividad 1 |
| Usuarios y entidades | Buscar y filtrar usuarios (F-USU-02) ✔ | Busca por nombre y filtra por Rol, Nivel, Estado y Categoría. | R | Sin restricción adicional | Módulo 03 — Actividad 1 |
| Usuarios y entidades | Ver el detalle de un usuario (F-USU-03) ✔ | Muestra "Información de Usuario": rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, apellidos, cargo y correo. | R | Sin restricción adicional | Módulo 03 — Actividad 2 |
| Usuarios y entidades | Invitar un usuario (F-USU-04) ✔ | Crea el usuario con su rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, cargo y correo, y le envía la invitación. | C | No puede invitar Super Administradores | Módulo 03 — Actividad 3 |
| Usuarios y entidades | Editar un usuario (F-USU-06) ✔ | Cambia los datos del usuario (incluido el rol y su alcance) desde el detalle. | U | No edita usuarios Super Administrador ni asigna ese rol | Módulo 03 — Actividad 4 |
| Usuarios y entidades | Activar o inactivar un usuario (F-USU-07) ✔ | Cambia el interruptor **Activo** del usuario: un usuario inactivo no puede iniciar sesión. | Estado | No sobre sí mismo ni sobre un Super Administrador | Módulo 03 — Actividad 5 |
| Usuarios y entidades | Reenviar una invitación (F-USU-08) ✔ | Genera un enlace nuevo y vuelve a enviar el correo de invitación. | Estado | Sin restricción adicional | Módulo 03 — Actividad 6 |
| Usuarios y entidades | Eliminar una invitación (F-USU-09) ✔ | Elimina una invitación que no ha sido aceptada. | D | Sin restricción adicional | Módulo 03 — Actividad 6 |
| Usuarios y entidades | Listar entidades centrales y subdirecciones (F-USU-10) ✔ | Muestra las entidades con las vistas **Centrales** y **Subdirecciones**: nombre, subdirecciones, usuarios, categoría y fecha de creación. | R | Sin restricción adicional | Módulo 03 — Actividad 7 |
| Usuarios y entidades | Buscar y filtrar entidades (F-USU-11) ✔ | Busca por nombre y filtra por Categoría. | R | Sin restricción adicional | Módulo 03 — Actividad 7 |
| Usuarios y entidades | Ver el detalle de una entidad (F-USU-12) ✔ | Muestra la entidad central, su categoría y sus subdirecciones, con búsqueda. | R | Sin restricción adicional | Módulo 03 — Actividad 7 |
| Usuarios y entidades | Ver los usuarios asignados a una entidad (F-USU-13) ✔ | Al pasar el cursor sobre el número de usuarios muestra hasta 5 usuarios asignados. | R | Sin restricción adicional | Módulo 03 — Actividad 7 |
| Usuarios y entidades | Agregar una entidad con sus subdirecciones (F-USU-14) ✔ | Crea una entidad central con su categoría y, si aplica, sus subdirecciones. | C | Sin restricción adicional | Módulo 03 — Actividad 8 |
| Usuarios y entidades | Editar una entidad y sus subdirecciones (F-USU-15) ✔ | Cambia el nombre o la categoría y agrega o elimina subdirecciones. | U | Sin restricción adicional | Módulo 03 — Actividad 9 |
| Usuarios y entidades | Eliminar una entidad (F-USU-16) ✔ | Elimina una entidad que no tiene usuarios, subdirecciones, alertas ni recomendaciones. | D | Sin restricción adicional | Módulo 03 — Actividad 10 |
| Alertas tempranas | Listar alertas (F-ALE-01) ✔ | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Sin restricción adicional | Módulo 04 — Actividad 1 |
| Alertas tempranas | Buscar alertas (F-ALE-02) ✔ | Busca por número o texto de la alerta. | R | Sin restricción adicional | Módulo 04 — Actividad 1 |
| Alertas tempranas | Filtrar alertas (F-ALE-03) ✔ | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Sin restricción adicional | Módulo 04 — Actividad 1 |
| Alertas tempranas | Ver el detalle de una alerta (F-ALE-04) ✔ | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Sin restricción adicional | Módulo 04 — Actividad 2 |
| Alertas tempranas | Descargar el PDF de la alerta (F-ALE-05) ✔ | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Sin restricción adicional | Módulo 04 — Actividad 2 |
| Alertas tempranas | Consultar el historial de actividades de la alerta (F-ALE-06) ✔ | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Sin restricción adicional | Módulo 04 — Actividad 3 |
| Alertas tempranas | Descargar el listado de alertas (CSV) (F-ALE-07) ✔ | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Sin restricción adicional | Módulo 04 — Actividad 4 |
| Alertas tempranas | Reportar una alerta temprana (F-ALE-08) ✔ | Registra manualmente una alerta en 6 pasos (Información general, Lugar de advertencia, Conflicto, Conductas vulneratorias, Población afectada, Subsunción) y la deja Activa. | C | Sin restricción adicional | Módulo 04 — Actividad 7 |
| Alertas tempranas | Editar una alerta (F-ALE-10) ✔ | Modifica los datos de la alerta en el mismo formulario de 6 pasos. | U | Si la alerta no está cerrada, no está subsumida y su plan no está confirmado | Módulo 04 — Actividad 8 |
| Alertas tempranas | Publicar una alerta en borrador (F-ALE-12) ✔ | Al guardar la edición con "Publicar alerta al guardar" activo, la alerta pasa de Borrador a Activa. | Estado | Solo alertas en Borrador | Módulo 04 — Actividad 9 |
| Alertas tempranas | Subsumir otras alertas (F-ALE-13) ✔ | Marca alertas existentes como subsumidas por la alerta que se registra o edita; las subsumidas pasan a Cerrada. | Estado | Solo alertas activas no subsumidas | Módulo 04 — Actividad 7; Módulo 04 — Actividad 10 |
| Recomendaciones | Listar las recomendaciones de una alerta (F-REC-01) ✔ | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Sin restricción adicional | Módulo 04 — Actividad 6; Módulo 05 — Actividad 1 |
| Recomendaciones | Buscar y filtrar recomendaciones (F-REC-02) ✔ | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Sin restricción adicional | Módulo 05 — Actividad 1 |
| Recomendaciones | Ver el detalle de una recomendación (F-REC-03) ✔ | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Sin restricción adicional | Módulo 05 — Actividad 2 |
| Recomendaciones | Descargar las recomendaciones (CSV) (F-REC-04) ✔ | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Sin restricción adicional | Módulo 05 — Actividad 3 |
| Recomendaciones | Agregar una recomendación (F-REC-05) ✔ | Registra en 2 pasos el eje temático, la descripción, una o varias entidades principales y sus entidades asociadas; se crea una recomendación por cada entidad principal. | C | Alerta no cerrada y plan no confirmado | Módulo 05 — Actividad 4 |
| Recomendaciones | Editar una recomendación (F-REC-06) ✔ | Modifica eje, descripción y entidades. | U | Alerta no cerrada y plan no confirmado | Módulo 05 — Actividad 5 |
| Recomendaciones | Asignar el código RC (F-REC-08) 👁 | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Ve el código asignado | Módulo 05 — Actividad 1; Módulo 05 — Actividad 4 |
| Planes de acción | Listar las alertas con plan de acción (F-PLA-01) ✔ | Pestaña **Alertas**: por alerta muestra Ejecutado vs programado, % de cumplimiento, estado del Plan de acción y estado del Informe. | R | Sin restricción adicional | Módulo 06 — Actividad 1 |
| Planes de acción | Buscar y filtrar planes de acción (F-PLA-02) ✔ | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento (0-30, 31-50, 51-80, 81-100). | R | Sin restricción adicional | Módulo 06 — Actividad 1 |
| Planes de acción | Ver el detalle y el historial del plan de una alerta (F-PLA-03) ✔ | Abre la ficha con "Información de alerta" e "Historial Plan de acción". | R | Sin restricción adicional | Módulo 06 — Actividad 1 |
| Planes de acción | Descargar el listado de planes (CSV) (F-PLA-04) ✔ | Descarga Número de Alerta, Cumplimiento (%) y Plan de Acción de las alertas visibles. | Archivo | Sin restricción adicional | Módulo 06 — Actividad 1 |
| Planes de acción | Ver las recomendaciones del plan de una alerta (F-PLA-05) ✔ | Desde **Ir al plan de acción**, lista las recomendaciones con Actividades (Aprobadas / Total) y Ejecución; **Ver Actividades** abre las actividades. | R | Sin restricción adicional | Módulo 06 — Actividad 2 |
| Planes de acción | Consultar la pestaña global de Recomendaciones (F-PLA-06) ✔ | Pestaña **Recomendaciones** con todas las recomendaciones del alcance, filtros (alerta, eje, entidad) y descarga. | R | Sin restricción adicional | Módulo 06 — Actividad 3 |
| Planes de acción | Consultar la pestaña global de Actividades (F-PLA-07) ✔ | Pestaña **Actividades** con todas las actividades del alcance: Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe, Próximo Informe; filtros y descarga. | R | Sin restricción adicional | Módulo 06 — Actividad 3 |
| Planes de acción | Listar las actividades de una recomendación (F-PLA-08) ✔ | Muestra Actividad, Objetivo, Descripción, Número Actividades, Ejecución (Ejecutadas / Programadas), Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; busca por objetivo y filtra por Estado, Instrumento de Planeación y Recursos. | R | Sin restricción adicional | Módulo 06 — Actividad 4 |
| Planes de acción | Ver el detalle de una actividad (F-PLA-09) ✔ | Abre "Detalle de Actividad": Recomendación, campos de la actividad, Estado Informe, Ejecución y Próximo Informe. | R | Sin restricción adicional | Módulo 06 — Actividad 4 |
| Planes de acción | Descargar las actividades (CSV) (F-PLA-10) ✔ | Descarga Número de Alerta, Código de Recomendación, Objetivo, Descripción, Número de Actividades, Plazo, Instrumento, Recursos, Estado, Observaciones y fechas. | Archivo | Sin restricción adicional | Módulo 06 — Actividad 3; Módulo 06 — Actividad 4 |
| Planes de acción | Consultar los informes de ejecución y descargar su PDF (F-PLA-19) ✔ | En el detalle de la recomendación (pestaña de actividades) muestra "Informes de ejecución" con todos sus campos y el archivo "Informe.pdf". | Archivo | Sin restricción adicional | Módulo 06 — Actividad 5 |
| Seguimiento | Listar los planes en Seguimiento (F-SEG-01) ✔ | Pantalla "Seguimiento de Planes": por alerta muestra Ejecutado vs programado, Plan de acción e Informe, y la acción para confirmar el plan. | R | Sin restricción adicional | Módulo 07 — Actividad 1 |
| Seguimiento | Buscar y filtrar planes en Seguimiento (F-SEG-02) ✔ | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento. | R | Sin restricción adicional | Módulo 07 — Actividad 1 |
| Seguimiento | Descargar el listado de Seguimiento (CSV) (F-SEG-03) ✔ | Descarga el listado de planes visible. | Archivo | Sin restricción adicional | Módulo 07 — Actividad 1 |
| Seguimiento | Consultar recomendaciones, actividades e informes en Seguimiento (F-SEG-04) ✔ | Recorre alerta › recomendaciones › actividades en modo seguimiento, con el panel "Información Actividades" y los "Informes de ejecución". | R | Sin restricción adicional | Módulo 07 — Actividad 2 |
| Informe de recomendaciones | Consultar el Informe de recomendaciones (F-IRE-01) ✔ | Tablero con Información alertas, Información recomendaciones, Información actividades y Cumplimiento por Entidad Principal y por Eje Temático. | R | Sin restricción adicional | Módulo 08 — Actividad 1 |
| Informe de recomendaciones | Filtrar el Informe de recomendaciones por alerta (F-IRE-02) ✔ | Cambia el consolidado de "Todas las alertas" a una alerta. | R | Sin restricción adicional | Módulo 08 — Actividad 1 |
| Reportes | Listar los reportes de ejecución (F-REP-01) ✔ | Pantalla "Reportes de ejecución" con las pestañas Todos, Alerta, Entidad y Regional y la tabla Informe, Tipo, Publicado, Estado y Aprobador. | R | Sin restricción adicional | Módulo 09 — Actividad 1 |
| Reportes | Buscar y filtrar reportes (F-REP-02) ✔ | Busca por nombre y filtra por Tipo, Estado, Alerta asociada, Entidad, Departamento y Municipio. | R | Sin restricción adicional | Módulo 09 — Actividad 1 |
| Reportes | Ver el detalle de un reporte (F-REP-03) ✔ | Muestra Nombre del reporte, Etiqueta (tipo), Fecha de publicacion, Estado, Descripcion, Adjunto y Aprobador. | R | Sin restricción adicional | Módulo 09 — Actividad 2 |
| Reportes | Descargar un reporte (F-REP-04) ✔ | Descarga el PDF del reporte. | Archivo | Sin restricción adicional | Módulo 09 — Actividad 2 |
| Reportes | Cargar un reporte de ejecución (F-REP-05) ✔ | Registra el tipo (Alerta, Entidad, Depto, Municipio), su alcance, la fecha, el aprobador, la descripción y el PDF. | C | Sin restricción adicional | Módulo 09 — Actividad 3 |
| Reportes | Editar un reporte de ejecución (F-REP-06) ✔ | Modifica los datos o el PDF del reporte desde su detalle. | U | Sin restricción adicional | Módulo 09 — Actividad 4 |
| Reportes | Generar un informe ejecutivo en Word (Panel de consultas) (F-REP-09) ✔ | Genera y descarga un documento Word por Alerta, Entidad, Depto, Municipio o General. | Archivo | Sin restricción adicional | Módulo 09 — Actividad 5 |
| Informes de seguimiento | Listar los informes de seguimiento (F-ISE-01) ✔ | Tabla con Informe, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Sin restricción adicional | Módulo 10 — Actividad 1 |
| Informes de seguimiento | Buscar y filtrar informes por alerta (F-ISE-02) ✔ | Busca por número y filtra por Alerta asociada. | R | Sin restricción adicional | Módulo 10 — Actividad 1 |
| Informes de seguimiento | Ver el detalle de un informe de seguimiento (F-ISE-03) ✔ | Muestra Informacion basica, Detalles del seguimiento y Archivo adjunto. | R | Sin restricción adicional | Módulo 10 — Actividad 1 |
| Informes de seguimiento | Descargar el PDF del informe de seguimiento (F-ISE-04) ✔ | Descarga el archivo del informe. | Archivo | Sin restricción adicional | Módulo 10 — Actividad 1 |
| Informes de seguimiento | Cargar un informe de seguimiento (F-ISE-05) ✔ | Registra en 2 pasos el número, la alerta, las fechas, el radicado y el PDF, y las modificaciones a la alerta. | C | Sin restricción adicional | Módulo 10 — Actividad 2 |
| Informes de seguimiento | Modificar municipios y agregar recomendaciones desde el informe (F-ISE-06) ✔ | En el paso 2 marca municipios como cerrados, agrega municipios y agrega recomendaciones nuevas. | U | Solo si la alerta no está cerrada | Módulo 10 — Actividad 2 |
| Informes de seguimiento | Editar un informe de seguimiento (F-ISE-08) ✔ | Modifica los datos del informe (la alerta asociada no se cambia). | U | Sin restricción adicional | Módulo 10 — Actividad 3 |
| Oficios de consumación | Listar los oficios de consumación (F-OFI-01) ✔ | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Sin restricción adicional | Módulo 11 — Actividad 1 |
| Oficios de consumación | Buscar y filtrar oficios por alerta (F-OFI-02) ✔ | Busca por radicado y filtra por Alerta asociada. | R | Sin restricción adicional | Módulo 11 — Actividad 1 |
| Oficios de consumación | Ver el detalle de un oficio (F-OFI-03) ✔ | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Sin restricción adicional | Módulo 11 — Actividad 1 |
| Oficios de consumación | Descargar el PDF del oficio (F-OFI-04) ✔ | Descarga el archivo del oficio. | Archivo | Sin restricción adicional | Módulo 11 — Actividad 1 |
| Interoperabilidad X-Road (SISAT) | Recibir alertas tempranas por X-Road (F-INT-01) 👁 | SISAT envía la alerta con sus municipios y recomendaciones; el sistema crea la alerta y las recomendaciones automáticas y notifica a las entidades. | Automática | Ve el resultado en Alertas tempranas (modo de creación automático) | Módulo 04 — Actividad 1; Módulo 04 — Actividad 5 |
| Interoperabilidad X-Road (SISAT) | Recibir informes de seguimiento por X-Road (F-INT-02) 👁 | SISAT envía informes de seguimiento, que pueden cerrar la alerta o modificarla. | Automática | Ve el resultado en Informes de seguimiento | Módulo 10 — Actividad 1 |
| Interoperabilidad X-Road (SISAT) | Recibir oficios de consumación por X-Road (F-INT-03) 👁 | SISAT envía oficios de consumación. | Automática | Ve el resultado en Oficios de consumación | Módulo 11 — Actividad 1 |
| Tareas programadas | Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01) 👁 | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Ve la fecha y el estado resultantes en las actividades | Módulo 06 — Actividad 4; Módulo 07 — Actividad 2 |
| Tareas programadas | Recalcular estados y porcentajes de cumplimiento (F-TAR-03) 👁 | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Ve los estados y porcentajes recalculados | Módulo 02 — Actividad 1; Módulo 06 — Actividad 4; Módulo 07 — Actividad 2 |
| Tareas programadas | Calcular el próximo informe al aprobar un informe (F-TAR-04) 👁 | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Ve los estados y porcentajes recalculados | Módulo 06 — Actividad 4; Módulo 07 — Actividad 2 |

### Qué NO puede hacer el Administrador

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
| Usuarios y entidades | Invitar un Super Administrador (F-USU-05) ✖ | Crea otro usuario con rol Super Administrador. | API y UI: la opción no aparece para el Administrador y el servidor responde "Solo un Super Administrador puede crear otros Super Administradores" (`main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:55`, `dashboard/src/components/ui/UserFormModal.tsx:332-336`) | Super Administrador |
| Agentes IA | Crear una alerta desde PDF con el Agente IA (F-AGE-01) ✖ | Envía el PDF de la alerta al agente, que extrae los datos y crea la alerta en estado Borrador. | UI y API: sin menú *Agentes* y `RequireSuperAdmin` (`dashboard/src/components/layout/Sidebar.tsx:75`, `main-api/CipratApi/Controladores/AlertasControlador.cs:409-410,1322-1323`) | Super Administrador |
| Agentes IA | Consultar el Historial de Procesamiento (F-AGE-02) ✖ | Lista los eventos del agente: Fecha, Evento (PDF Enviado, Alerta Creada, Error, Entidad No Encontrada, Municipio No Encontrado), Mensaje y Archivo / Alerta. | UI y API: sin menú *Agentes* y `RequireSuperAdmin` (`dashboard/src/components/layout/Sidebar.tsx:75`, `main-api/CipratApi/Controladores/AlertasControlador.cs:409-410,1322-1323`) | Super Administrador |
| Alertas tempranas | Adjuntar el PDF de la alerta y el Adjunto (F-ALE-09) ✖ | Sube el "PDF de la alerta" y un "Adjunto" (solo PDF, hasta 20 MB) al crear o editar la alerta. | API: el servidor exige el permiso `SubirArchivo`, que solo tiene el Super Administrador; la pantalla le muestra los campos y al final avisa "El PDF de la alerta no pudo ser subido." (`main-api/CipratApi/Servicios/ServicioPermisos.cs:254-258`, `dashboard/src/pages/AlertasTempranas.tsx:341-358`) | Super Administrador |
| Alertas tempranas | Cambiar el número de una alerta manual (F-ALE-11) ✖ | Edita el campo "Número y fecha de alerta" de una alerta creada manualmente. | UI: el campo está deshabilitado con el mensaje "No tienes permisos para editar el número de alerta" (`dashboard/src/components/report-alert/ReportAlertModal.tsx:30-45`) | Super Administrador |
| Alertas tempranas | Eliminar una alerta (F-ALE-14) ✖ | Elimina (borrado lógico) una alerta. Para el Super Administrador el sistema no aplica las reglas de estado: puede eliminar alertas automáticas, con recomendaciones, cerradas o con plan confirmado. | UI y API: opción deshabilitada ("No tienes permisos para eliminar alertas") y permiso `EliminarAlerta` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:40-44`) | Super Administrador |
| Alertas tempranas | Reemplazar o eliminar los archivos de la alerta (F-ALE-15) ✖ | En la edición, quita el PDF o el adjunto existente y sube uno nuevo. | API: permiso `EliminarArchivo` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:259-262`) | Super Administrador |
| Alertas tempranas | Cerrar alertas (F-ALE-16) ✖ | Cierra una o varias alertas activas con el consecutivo y la fecha de notificación del informe de la Defensoría, y opcionalmente su PDF. | UI y API: botón deshabilitado ("No tienes permisos para cerrar alertas") y permiso `CerrarAlerta` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:45-49`) | Super Administrador |
| Recomendaciones | Eliminar una recomendación (F-REC-07) ✖ | Elimina (borrado lógico) una recomendación de una alerta abierta cuyo plan no está confirmado. El servidor no verifica si la recomendación es automática ni si tiene actividades. | UI y API: opción deshabilitada ("No tienes permisos para eliminar recomendaciones") y permiso `EliminarRecomendacion` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:93-97`) | Super Administrador |
| Planes de acción | Agregar una actividad (F-PLA-11) ✖ | Registra en 2 pasos el Objetivo y la información de la actividad (Actividad, Número de actividades, Plazo de implementación, Instrumento de planeación, Recursos, Observaciones). | UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11) | La Entidad Territorial responsable de la recomendación |
| Planes de acción | Agregar una actividad a un plan confirmado (F-PLA-12) ✖ | Si el plan ya está confirmado, el sistema advierte "Agregar actividad a plan confirmado" y, al continuar, desconfirma el plan. | UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11) | La Entidad Territorial responsable |
| Planes de acción | Editar una actividad (F-PLA-13) ✖ | Modifica los campos de una actividad pendiente de aprobación. | UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11) | La Entidad Territorial responsable |
| Planes de acción | Eliminar una actividad (F-PLA-14) ✖ | Elimina una actividad pendiente de aprobación. | UI y API: sin botones y sin permiso `EliminarActividad` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:131-139`) | La Entidad Territorial responsable |
| Planes de acción | Ver y escribir comentarios de una actividad (F-PLA-15) ✖ | Abre la conversación de la actividad y agrega comentarios (hasta 2.000 caracteres). | UI: el botón **Comentarios** solo aparece a quien formula actividades en Planes de acción o aprueba en Seguimiento (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:395-510`, `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:569-711`); la API sí lo permitiría (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:77-83`) | La Entidad Territorial, el Monitor o el Líder de Macrozona |
| Planes de acción | Eliminar un comentario propio (F-PLA-16) ✖ | Servicio del servidor que permite al autor eliminar su comentario. La ventana de comentarios no tiene esa opción. | UI: la ventana "Comentarios" no ofrece eliminar (`dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`); la API lo permite al autor (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:140`) | No disponible en la interfaz |
| Planes de acción | Reportar un informe de ejecución (F-PLA-17) ✖ | Registra lo ejecutado en el ciclo: actividades ejecutadas, fechas, acciones, buenas prácticas, instrumento, resultados, dificultades y el PDF de soporte. | UI y API: sin botón y sin permiso `CrearInformeEjecucion` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:168-176`) | La Entidad Territorial responsable |
| Planes de acción | Editar un informe de ejecución pendiente (F-PLA-18) ✖ | Corrige el informe y su PDF mientras no esté aprobado. | UI y API: sin botón y sin permiso `CrearInformeEjecucion` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:168-176`) | La Entidad Territorial responsable |
| Planes de acción | Eliminar un informe de ejecución (F-PLA-20) ✖ | La matriz de permisos define el permiso, pero no existe servicio ni botón para eliminar informes de ejecución. | NO ENCONTRADO: no hay endpoint DELETE en `main-api/CipratApi/Controladores/InformesEjecucionControlador.cs` aunque `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191` define `EliminarInformeEjecucion` | Corrija el informe con **Editar Informe** mientras esté pendiente |
| Seguimiento | Marcar una actividad como revisada (F-SEG-05) ✖ | Deja constancia (usuario y fecha) de que revisó la actividad; no cambia su estado. | UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar una actividad (F-SEG-06) ✖ | Aprueba la actividad pendiente; si es la última pendiente, la recomendación y el plan pasan a Aprobado. | UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Descartar la aprobación de una actividad (F-SEG-07) ✖ | Devuelve una actividad aprobada a "Pendiente de aprobación". | UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Validar si el plan se puede confirmar (F-SEG-08) ✖ | Al abrir la confirmación, el sistema muestra el resumen (Total de recomendaciones, de actividades y de actividades programadas) o lo que falta ("El plan de acción tiene N actividades pendientes de aprobación y N recomendaciones sin actividades"). | UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Confirmar el plan de acción (F-SEG-09) ✖ | Confirma el plan completo de la alerta cuando todas sus actividades están aprobadas; habilita los informes de ejecución y notifica a las entidades. | UI y API: botón deshabilitado ("No tienes permisos para confirmar planes de acción") y el servidor responde "No tiene permiso para confirmar planes de acción" (`dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:75-79,331`, `main-api/CipratApi/Controladores/AlertasControlador.cs:880-893`) | Monitor o Líder de Macrozona del departamento |
| Seguimiento | Aprobar un informe de ejecución (F-SEG-10) ✖ | Aprueba el informe pendiente y el sistema fija la fecha del próximo informe. | UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`) | Monitor o Líder de Macrozona del departamento |
| Reportes | Eliminar un reporte de ejecución (F-REP-07) ✖ | Elimina un reporte que no está aprobado. | UI: el botón solo se habilita al Super Administrador ("No tienes permisos para eliminar reportes"); la API sí lo permitiría (`dashboard/src/components/reportes-ejecucion/ReportesEjecucionTab.tsx:52-53`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:227-232`) | Super Administrador |
| Reportes | Aprobar un reporte de ejecución (F-REP-08) ✖ | El aprobador designado aprueba el reporte. | UI y API: no ve el botón y no tiene el permiso `AprobarReporteEjecucion` (`dashboard/src/components/reportes-ejecucion/ReporteDetailModal.tsx:35-39`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:234-239`) | El aprobador designado (Líder de Macrozona o Super Administrador) |
| Informes de seguimiento | Cerrar la alerta con el informe de seguimiento (F-ISE-07) ✖ | Marca "Cerrar la alerta con este informe" para que la alerta quede Cerrada al guardar. | API: el servidor exige el permiso `CerrarAlerta` y responde 403 al Administrador, aunque la casilla se le muestra (`main-api/CipratApi/Controladores/AccionAlertasControlador.cs:205`, `dashboard/src/components/informes-seguimiento/InformeSeguimientoStep2Modificaciones.tsx:360`) | Super Administrador |
| Informes de seguimiento | Eliminar un informe de seguimiento (F-ISE-09) ✖ | Elimina un informe cuya alerta no está cerrada. | UI: el botón solo se habilita al Super Administrador ("No tienes permisos para eliminar informes"); la API sí lo permitiría (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:52`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:64-68`) | Super Administrador |
| Oficios de consumación | Cargar un oficio de consumación (F-OFI-05) ✖ | Registra en 2 pasos el radicado, las fechas, el tema clave, las alertas asociadas y el PDF, y las modificaciones por alerta. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Modificar municipios y agregar recomendaciones desde el oficio (F-OFI-06) ✖ | Para cada alerta asociada, marca municipios como cerrados, agrega municipios y agrega recomendaciones. | UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`) | Super Administrador |
| Oficios de consumación | Editar un oficio de consumación (F-OFI-07) ✖ | Modifica los datos del oficio. | UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`) | Super Administrador |
| Oficios de consumación | Eliminar un oficio de consumación (F-OFI-08) ✖ | Elimina el oficio. | UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`) | Super Administrador |
| Interoperabilidad X-Road (SISAT) | Entregar el plan estratégico a la Defensoría (F-INT-04) ✖ | La Defensoría consulta por X-Road el plan de acción de una alerta. | Proceso entre sistemas con llave de API X-Road; no es una acción de usuario (`main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:720`) | Lo ejecuta la Defensoría por X-Road |
| Interoperabilidad X-Road (SISAT) | Entregar archivos a la Defensoría (F-INT-05) ✖ | La Defensoría descarga por X-Road archivos de SI-CIPRAT. | Proceso entre sistemas con llave de API X-Road; no es una acción de usuario (`main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:762`) | Lo ejecuta la Defensoría por X-Road |
| Tareas programadas | Enviar el recordatorio de informe de ejecución (F-TAR-02) ✖ | Cada día a las 00:01 envía el recordatorio cuando faltan 30 días o menos para el próximo informe (una vez por ciclo). | Regla de envío: los correos de negocio solo se envían a usuarios activos de Entidad Territorial (`main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`) | Consulte la columna "Próximo Informe" |

## Segmentación de visualización

- **Inicio:** indicadores, ranking, alertas recientes y mapa calculados sobre todas las alertas del país, sin filtro (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores.
- **Alertas tempranas:** ve todas las alertas del país, sin filtro.
- **Recomendaciones de una alerta:** ve todas las recomendaciones de cada alerta que está en su alcance.
- **Planes de acción:** ve los planes, recomendaciones y actividades de todas las alertas del país, sin filtro.
- **Seguimiento:** ve los planes de todas las alertas del país, sin filtro.
- **Reportes:** ve los reportes de ejecución de todo el país.
- **Informes de seguimiento:** ve todos los registrados (`main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:266-279`).
- **Oficios de consumación:** ve todos los registrados (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`).
- **Notificaciones (panel):** ve el historial de actividad de todas las alertas del país, sin filtro (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`).
- **Usuarios y entidades:** ve todos los usuarios, invitaciones, entidades centrales y subdirecciones.

## Ruta de aprendizaje

### Módulo 00 — Contexto de la plataforma SI-CIPRAT

**Prerrequisitos:** Ninguno.

**Definición del módulo:** Módulo introductorio que presenta qué es SI-CIPRAT, quiénes intervienen, cómo avanza una alerta temprana de la fase E0 a la E6 y qué papel cumple el Administrador en ese ciclo.

**Objetivo del módulo:** Que el Administrador pueda explicar qué es SI-CIPRAT, cómo avanza una alerta de E0 a E6 y en qué momentos interviene su rol.

**Contexto del módulo:** Antes de operar, el Administrador necesita entender en qué parte del ciclo actúa, qué recibe de otros actores y qué entrega, porque el sistema le habilita o le bloquea acciones según el estado de cada alerta, recomendación, actividad e informe.

**Funcionalidades disponibles:** Ninguna funcionalidad del sistema (módulo conceptual).

#### Actividad 1 — Conocer qué es SI-CIPRAT y para qué existe

**Objetivo de la actividad:** Que el Administrador pueda explicar qué es SI-CIPRAT, a qué institución sirve y qué componentes tiene.

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

**Objetivo de la actividad:** Que el Administrador pueda describir las fases E0 a E6 del ciclo de una alerta, sus actores y los puntos donde el flujo sale de la plataforma.

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

#### Actividad 3 — Ubicar el papel de Administrador en el ciclo: su línea de tiempo

**Objetivo de la actividad:** Que el Administrador pueda ubicar en qué momentos del ciclo actúa, qué espera de otros actores y qué entrega.

| Secuencia | Fase | Acción | Disparador | Plazo | Qué sigue y quién |
|---|---|---|---|---|---|
| E0.1 | Preparación del sistema (usuarios y entidades) | Agregar Entidad (entidad central y subdirecciones) | Ninguno | Antes de la primera alerta | E0.2 Super Administrador o Administrador |
| E0.2 | Preparación del sistema (usuarios y entidades) | Enviar invitación (rol, nivel de acceso, entidad, subdirección, departamentos, cargo) | E0.1 (la entidad existe) | La invitación vence a los 7 días | E0.3 usuario invitado |
| E0.3 | Preparación del sistema (usuarios y entidades) | Activar cuenta (crear contraseña) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" | ≤ 7 días desde E0.2 | E0.4 el mismo usuario |
| E0.4 | Preparación del sistema (usuarios y entidades) | Iniciar Sesión y Validar código | E0.3 | Código válido 1 hora; sesión de 720 minutos; cierre a los 60 minutos de inactividad | Según el rol |
| E0.5 | Preparación del sistema (usuarios y entidades) | Editar usuario, activar o inactivar, Reenviar o Eliminar invitación | E0.2 | Cuando se requiera | — |
| E0.6 | Preparación del sistema (usuarios y entidades) | ¿Has olvidado tu contraseña? › Restablecer contraseña | El usuario olvidó la contraseña | Enlace válido 1 hora | E0.4 |
| E1.3 | Registro de la alerta | Reportar alerta › Enviar Alerta (6 pasos) | Se recibió el documento de la alerta | — | E1.4 Super Administrador; E2.1 |
| E1.5 | Registro de la alerta | Editar alerta y Publicar alerta al guardar | E1.1 o E1.2 (borrador) o datos por corregir | Antes de confirmar el plan | E2.1 |
| E1.6 | Registro de la alerta | Esta alerta subsume otras alertas | El documento declara alertas subsumidas | — | E2.1 |
| E2.1 | Recomendaciones | Agregar recomendación › Crear recomendación | Alerta Activa | Antes de confirmar el plan | E2.2 Entidad Territorial |
| E2.3 | Recomendaciones | Editar recomendación | E2.1 | Antes de confirmar el plan | E2.2 |
| E3.4 | Plan de acción (formulación) | Comentarios de la actividad | Actividad registrada | — | E3.3 o E4.2 |
| E5.6 | Informes de ejecución | Cargar informe (reporte de ejecución) con aprobador | Información de ejecución consolidable | El sistema no fija plazo | E5.7 aprobador designado |
| E5.8 | Informes de ejecución | Consultas › Generar consulta (informe ejecutivo Word) | Cuando se requiera | — | — |
| E5.9 | Informes de ejecución | Informe (Informe de recomendaciones) | Cuando se requiera | — | — |
| E6.1 | Seguimiento y cierre | Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) | La Defensoría emitió un informe de seguimiento | — | E2.2 (recomendaciones nuevas) o E6.3 |
| E1–E6 | Registro de la alerta | Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF | Desde E1 | Permanente | — |

**Pasos:**

##### Paso 3.1 — Leer su línea de tiempo
**Objetivo del paso:** Conocer sus momentos de intervención.
**Qué hacer:** Recorra la tabla de esta actividad en orden de secuencia.
**Resultado esperado:** Identifica sus 17 momentos de intervención.

##### Paso 3.2 — Identificar a quién espera
**Objetivo del paso:** Saber de qué depende para actuar.
**Qué hacer:** Lea la columna "Disparador" de cada fila.
**Resultado esperado:** Sabe qué debe haber pasado antes de cada acción.

##### Paso 3.3 — Identificar a quién entrega
**Objetivo del paso:** Saber qué sigue después de su acción.
**Qué hacer:** Lea la columna "Qué sigue y quién".
**Resultado esperado:** Sabe a qué actor le entrega el trabajo.

#### Actividad 4 — Conocer los módulos que usará y cómo está organizada esta ruta

**Objetivo de la actividad:** Que el Administrador pueda identificar los módulos de su ruta y la estructura de módulo, actividades y pasos.

| Módulo | Nombre | Objetivo |
|---|---|---|
| Módulo 01 | Acceso a la plataforma | Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. |
| Módulo 02 | Inicio | Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. |
| Módulo 03 | Usuarios y entidades | Preparar la plataforma con las entidades responsables y los usuarios correctos, cada uno con el rol y el alcance que le corresponde. |
| Módulo 04 | Alertas tempranas | Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. |
| Módulo 05 | Recomendaciones | Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. |
| Módulo 06 | Planes de acción | Que cada entidad responsable formule las actividades con las que atenderá sus recomendaciones y reporte periódicamente lo ejecutado. |
| Módulo 07 | Seguimiento | Revisar y aprobar el plan de acción y su ejecución, actividad por actividad, hasta confirmar el plan y aprobar cada informe. |
| Módulo 08 | Informe de recomendaciones | Ver en un solo tablero el avance consolidado de las recomendaciones por entidad y por eje temático. |
| Módulo 09 | Reportes | Consolidar y aprobar la información de ejecución para darle visibilidad institucional y producir informes ejecutivos. |
| Módulo 10 | Informes de seguimiento | Dejar en el sistema cada informe de seguimiento de la Defensoría y aplicar sus efectos sobre la alerta (municipios, recomendaciones nuevas o cierre). |
| Módulo 11 | Oficios de consumación | Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. |
| Módulo 12 | Notificaciones | Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. |
| Módulo 13 | Práctica con el caso AT-013-25 | Practicar todas las actividades de la ruta. |

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

**Objetivo del módulo:** Que el Administrador pueda activar la cuenta desde la invitación; iniciar sesión con el código de verificación; recuperar la contraseña; cerrar sesión y entender el cierre automático; consultar los Términos de uso y contactar al soporte técnico; consultar Mi perfil y verificar el alcance asignado.

**Contexto del módulo:** Interviene en la preparación (E0.3 activación, E0.4 primer ingreso, E0.6 recuperación de la contraseña) y en cada sesión de trabajo. Recibe la invitación y los datos creados en *Usuarios y entidades* (E0.2, E0.5) y entrega al usuario la sesión con la que el sistema aplica su rol y su alcance de datos. Lo usan todos los roles y subroles, sin diferencias de alcance. Lo activan la invitación (enlace válido 7 días), el ingreso (código válido 1 hora) y la inactividad (60 minutos). Para el Administrador: en total, tiene 11 de las 14 funcionalidades del módulo; no tiene: cambiar la contraseña con la contraseña actual, editar los datos del propio perfil, consultar el historial de cambios de contraseña.

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

**Objetivo de la actividad:** Que el Administrador pueda activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

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

> 📷 **[CAPTURA MED-02-ACC-01]** — Pantalla "Configura tu contraseña"
> **Debe mostrar:** La pantalla de activación con los dos campos y los indicadores de la contraseña
> **Resaltar:** Campos Nueva Contraseña y Confirmar Contraseña; botón Activar cuenta
> **Pantalla / ruta:** `/setup/:token` (`dashboard/src/pages/auth/ResetPassword.tsx:198-317`)
> **Tomarla con:** Administrador · **Datos:** Invitación de prueba vigente
> **Texto alternativo:** Formulario para crear la contraseña y activar la cuenta

**Resultado de la actividad:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el enlace de invitación después de 7 días | "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador." | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Active la cuenta apenas reciba el correo. |
| Abrir un enlace de invitación incompleto o ya usado | "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada" | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | No copie el enlace a mano. |
| Crear una contraseña corta o sin símbolos | "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña debe contener al menos un carácter especial") | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Revise los indicadores de la pantalla antes de enviar. |
| Escribir diferente la confirmación de la contraseña | "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente." | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | — |

> 📷 **[CAPTURA MED-02-ACC-02]** — Mensaje ERR-ACC-06
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:319`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de invitación después de 7 días

> 📷 **[CAPTURA MED-02-ACC-03]** — Mensaje ERR-ACC-07
> **Debe mostrar:** La pantalla con el mensaje "El enlace de invitación es inválido. Verifica que el enlace esté completo." o "Esta invitación ya ha sido utilizada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:324`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un enlace de invitación incompleto o ya usado

> 📷 **[CAPTURA MED-02-ACC-04]** — Mensaje ERR-ACC-08
> **Debe mostrar:** La pantalla con el mensaje "Debe tener al menos 8 caracteres" / "Debe contener al menos un carácter especial" (servidor: "La contraseña debe tener al menos 8 caracteres", "La contraseña d
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/utils/validation.ts:25-31`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Crear una contraseña corta o sin símbolos

> 📷 **[CAPTURA MED-02-ACC-05]** — Mensaje ERR-ACC-09
> **Debe mostrar:** La pantalla con el mensaje "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/auth/ResetPassword.tsx:101`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir diferente la confirmación de la contraseña

**⚠️ Atención:**
- ⚠️ El enlace vence a los 7 días y solo sirve una vez. Si vence, pida que le reenvíen la invitación.
- La contraseña es personal e intransferible (Términos de uso, numeral 4).

**Ejemplo:** Si la invitación se envió el lunes 2 de febrero de 2026, el enlace sirve hasta el lunes 9 de febrero de 2026.

#### Actividad 2 — Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el Administrador pueda ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

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
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | — | — | administrador.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" (mensajes en inglés de la pantalla) / "Credenciales inválidas" |
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

> 🎞️ **[GIF MED-02-ACC-06]** — Ingreso con código de verificación
> **Debe mostrar:** El ingreso completo: correo y contraseña, pantalla "Revisa tu correo electrónico", escritura del código y llegada a Inicio
> **Resaltar:** Botones Iniciar Sesión y Validar código; enlace Haz clic para reenviar
> **Pantalla / ruta:** `/signin` (`dashboard/src/components/auth/LoginPanel.tsx`, `VerificationCodePanel.tsx`)
> **Tomarla con:** Administrador · **Datos:** Usuario de prueba del rol
> **Imagen existente:** Refenrence/img/Screenshot 2026-08-11 at 6.07.49 PM.png: sirve para el primer cuadro (pantalla "Inicia sesión en tu cuenta", igual para todos los roles). Debe actualizarse: muestra un correo personal real; tomarla de nuevo con administrador.prueba@ejemplo.gov.co
> **Solo para GIF — Secuencia:** 1) Escribir correo y contraseña 2) Iniciar Sesión 3) Escribir el código 4) Validar código 5) Inicio · **Duración aproximada:** 20 segundos
> **Texto alternativo:** Animación del inicio de sesión con código de 4 dígitos

**Resultado de la actividad:** Sesión abierta con el rol el Administrador y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Escribir mal el correo o la contraseña | "Credenciales inválidas" | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | No comparta ni anote la contraseña en lugares visibles. |
| Escribir mal el código de 4 dígitos | "Código de autenticación inválido" | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Use siempre el código del correo más reciente. |
| Usar un código después de 1 hora | "Código expirado" | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Ingrese el código apenas llegue. |
| Ingresar con una cuenta inactivada | "Cuenta no activa" | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | — |
| Ingresar cuando la entidad asignada no está activa | "Tu organización está suspendida. Por favor contacta al administrador." | La entidad guardada en su usuario no está en estado Activa. | Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. | — |
| No llega el correo con el código | No aparece mensaje: la pantalla "Revisa tu correo electrónico" queda esperando el código. | El correo puede estar en la carpeta de correo no deseado o tardar en llegar. | Revise la carpeta de correo no deseado; espere un minuto y use **Haz clic para reenviar**. | Agregue el remitente de SI-CIPRAT a sus contactos. |
| Se pierde la conexión a internet | "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo." | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Trabaje con conexión estable; los Términos de uso la exigen. |

> 📷 **[CAPTURA MED-02-ACC-07]** — Mensaje ERR-ACC-01
> **Debe mostrar:** La pantalla con el mensaje "Credenciales inválidas"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:132-141`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el correo o la contraseña

> 📷 **[CAPTURA MED-02-ACC-08]** — Mensaje ERR-ACC-02
> **Debe mostrar:** La pantalla con el mensaje "Código de autenticación inválido"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:81-84`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir mal el código de 4 dígitos

> 📷 **[CAPTURA MED-02-ACC-09]** — Mensaje ERR-ACC-03
> **Debe mostrar:** La pantalla con el mensaje "Código expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:88-91,163`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar un código después de 1 hora

> 📷 **[CAPTURA MED-02-ACC-10]** — Mensaje ERR-ACC-04
> **Debe mostrar:** La pantalla con el mensaje "Cuenta no activa"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:144-148`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Ingresar con una cuenta inactivada

> 📷 **[CAPTURA MED-02-ACC-11]** — Mensaje ERR-ACC-05
> **Debe mostrar:** La pantalla con el mensaje "Tu organización está suspendida. Por favor contacta al administrador."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:150-156`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Ingresar cuando la entidad asignada no está activa

> 📷 **[CAPTURA MED-02-ACC-12]** — Mensaje ERR-GEN-06
> **Debe mostrar:** La pantalla con el mensaje "No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:403`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Se pierde la conexión a internet

**⚠️ Atención:**
- El código vence 1 hora después de enviado; use siempre el del correo más reciente.
- Los mensajes de los campos vacíos de esta pantalla aparecen en inglés ("Email is required", "Please enter a valid email address", "Password is required").

**Ejemplo:** Si el código llega a las 8:05 a. m., sirve hasta las 9:05 a. m.

#### Actividad 3 — Recuperar la contraseña

**Objetivo de la actividad:** Que el Administrador pueda crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

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
| 1 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo | — | — | administrador.prueba@ejemplo.gov.co | "Email is required" / "Please enter a valid email address" |

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

> 🎞️ **[GIF MED-02-ACC-13]** — Recuperación de la contraseña
> **Debe mostrar:** Solicitud del enlace, mensaje "Revisa tu correo electrónico", pantalla "Configurar nueva contraseña" y mensaje "Contraseña restablecida"
> **Resaltar:** Enlace ¿Has olvidado tu contraseña?; botón Restablecer contraseña
> **Pantalla / ruta:** `/forgot-password`, `/reset-password/:token` (`dashboard/src/pages/auth/ForgotPassword.tsx`, `ResetPassword.tsx`)
> **Tomarla con:** Administrador · **Datos:** Usuario de prueba
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

> 📷 **[CAPTURA MED-02-ACC-14]** — Mensaje ERR-ACC-10
> **Debe mostrar:** La pantalla con el mensaje "No puedes reutilizar ninguna de tus últimas 5 contraseñas" o "La nueva contraseña no puede ser igual a tu contraseña actual"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:378-396`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar una contraseña anterior al restablecerla

> 📷 **[CAPTURA MED-02-ACC-15]** — Mensaje ERR-ACC-11
> **Debe mostrar:** La pantalla con el mensaje "Token inválido o expirado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAutenticacion.cs:622-628`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el enlace de restablecimiento después de 1 hora

**⚠️ Atención:**
- La plataforma no tiene una pantalla para cambiar la contraseña conociendo la actual: para cambiarla, use siempre **¿Has olvidado tu contraseña?** (el servicio `password-change` existe, pero ninguna pantalla lo usa).

**Ejemplo:** Si solicita el enlace a las 3:00 p. m., debe usarlo antes de las 4:00 p. m.

#### Actividad 4 — Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el Administrador pueda cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

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

> 📷 **[CAPTURA MED-02-ACC-16]** — Menú del usuario
> **Debe mostrar:** El pie del menú lateral con el nombre del usuario y las opciones Ver Perfil y Cerrar sesión
> **Resaltar:** Opción Cerrar sesión
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:425-479`)
> **Tomarla con:** Administrador · **Datos:** Usuario de prueba
> **Texto alternativo:** Menú del usuario con la opción Cerrar sesión

**Resultado de la actividad:** La sesión termina; los datos no guardados de un formulario abierto se pierden.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Dejar la plataforma abierta sin usarla 60 minutos | "Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente." | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Guarde los formularios antes de dejar el equipo. |
| Trabajar con una sesión vencida | "Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente." | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | — |

> 📷 **[CAPTURA MED-02-ACC-17]** — Mensaje ERR-ACC-12
> **Debe mostrar:** La pantalla con el mensaje "Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useIdleTimeout.ts:6-22`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Dejar la plataforma abierta sin usarla 60 minutos

> 📷 **[CAPTURA MED-02-ACC-18]** — Mensaje ERR-ACC-13
> **Debe mostrar:** La pantalla con el mensaje "Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/hooks/useApiErrorHandler.ts:14`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Trabajar con una sesión vencida

**⚠️ Atención:**
- ⚠️ Guarde los formularios antes de dejar el equipo: el cierre por inactividad no guarda lo diligenciado.

**Ejemplo:** Si su última acción fue a las 10:00 a. m., a las 11:00 a. m. la sesión se cierra sola.

#### Actividad 5 — Consultar los Términos de uso y contactar al soporte técnico

**Objetivo de la actividad:** Que el Administrador pueda conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

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

> 📷 **[CAPTURA MED-02-ACC-19]** — Términos de uso
> **Debe mostrar:** La página de términos con el título y el numeral 4
> **Resaltar:** Numeral "4. Condiciones técnicas de acceso y uso" y el correo de soporte
> **Pantalla / ruta:** `/terminos-de-uso` (`dashboard/src/pages/TermsOfUse.tsx`)
> **Tomarla con:** Administrador · **Datos:** No requiere datos
> **Texto alternativo:** Página de términos y condiciones de uso

**Resultado de la actividad:** Conoce las condiciones de uso y el canal de soporte.

**Escenarios de error y solución:**

No se identificaron escenarios de error en el código para esta actividad.

**⚠️ Atención:**
- El ingreso a la plataforma implica la aceptación de los Términos y Condiciones.

#### Actividad 6 — Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el Administrador pueda verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

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
**Qué hacer:** Verifique que el Rol diga "Administrador". Su alcance es nacional; la Entidad Central, si aparece, es informativa.
**Resultado esperado:** Confirma que verá todas las alertas del país, sin filtro de entidad ni de departamento.

> 📷 **[CAPTURA MED-02-ACC-20]** — Mi perfil
> **Debe mostrar:** Las tres secciones de Mi perfil de un usuario de prueba con rol Administrador
> **Resaltar:** Campos Rol, Entidad Central, Nivel de Acceso, Subdirección y Departamentos
> **Pantalla / ruta:** `/mi-perfil` (`dashboard/src/pages/MyProfile.tsx:111-283`)
> **Tomarla con:** Administrador · **Datos:** Usuario de prueba de la ruta
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

**Objetivo del módulo:** Que el Administrador pueda leer los indicadores del Inicio; consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa; navegar con el menú lateral y usar el panel de accesibilidad; consultar el tablero público sin iniciar sesión.

**Contexto del módulo:** Se consulta en todas las fases del ciclo. Recibe datos de *Alertas tempranas* (estado, tipo, fecha de notificación, municipios) y de los planes de acción (actividades programadas y ejecutadas). Con sesión, los datos se filtran por el alcance del rol (departamentos o entidad); sin sesión, muestra la información nacional pública. Los borradores no cuentan en los indicadores. Para el Administrador: indicadores, ranking, alertas recientes y mapa calculados sobre todas las alertas del país, sin filtro (`main-api/CipratApi/Servicios/ServicioDashboardHome.cs:35-43`). Los borradores no cuentan en los indicadores. En total, tiene 9 de las 9 funcionalidades del módulo.

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

**Objetivo de la actividad:** Que el Administrador pueda interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Qué ve:** Título "Inicio" y el texto "Visualiza de manera centralizada el estado y la distribución de las alertas tempranas asociadas a sus departamentos". Cinco tarjetas con valor, tendencia "vs ultimo mes" y una línea de los últimos 4 meses:

| Tarjeta | Qué cuenta (alertas no borrador de nacional) |
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

> 📷 **[CAPTURA MED-02-INI-01]** — Indicadores del Inicio
> **Debe mostrar:** Las cinco tarjetas y el bloque Porcentaje de Avance Global para un usuario Administrador
> **Resaltar:** Valor y tendencia "vs ultimo mes" de una tarjeta; el porcentaje y la línea de actividades ejecutadas
> **Pantalla / ruta:** `/inicio` (`dashboard/src/pages/Home.tsx:340-433`)
> **Tomarla con:** Administrador · **Datos:** Ambiente de pruebas con alertas de varios estados
> **Texto alternativo:** Tarjetas de indicadores y porcentaje de avance global

**Resultado de la actividad:** Interpreta el estado general de las alertas de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | — |
| El tablero aparece vacío o en cero | "No hay datos de departamentos" / "No hay alertas recientes" | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | — |

> 📷 **[CAPTURA MED-02-INI-02]** — Mensaje ERR-INI-01
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar datos"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:416`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero no carga

> 📷 **[CAPTURA MED-02-INI-03]** — Mensaje ERR-INI-02
> **Debe mostrar:** La pantalla con el mensaje "No hay datos de departamentos" / "No hay alertas recientes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Home.tsx:212,263`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El tablero aparece vacío o en cero

**⚠️ Atención:**
- Los borradores (alertas del Agente IA o de X-Road aún no publicadas) no cuentan en los indicadores.
- ⚠️ El "Porcentaje de Avance Global" promedia el porcentaje de cada alerta: no es igual a ejecutadas ÷ programadas del total.

**Ejemplo:** Con dos alertas: A con 10 programadas y 5 ejecutadas (50 %) y B con 2 programadas y 2 ejecutadas (100 %), el avance global es (50 + 100) ÷ 2 = 75 %, y la línea dice "7 de 12 actividades ejecutadas" (58,3 %). Una tercera alerta sin actividades (0 %) bajaría el promedio a 50 %.

#### Actividad 2 — Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el Administrador pueda ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

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

> 📷 **[CAPTURA MED-02-INI-04]** — Mapa y ranking del Inicio
> **Debe mostrar:** El mapa con municipios en rojo y azul, la leyenda y el bloque Alertas por departamento
> **Resaltar:** Leyenda del mapa; un municipio con su tooltip; Top 10
> **Pantalla / ruta:** `/inicio` (`dashboard/src/components/map/ColombiaMap.tsx`)
> **Tomarla con:** Administrador · **Datos:** Ambiente de pruebas con alertas de los dos tipos
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

**Objetivo de la actividad:** Que el Administrador pueda moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral; botón **Accesibilidad** (panel "Panel de accesibilidad").

**Qué ve:** El menú lateral con: Inicio, Alertas tempranas, Planes de acción, Seguimiento, Reportes, Oficios de consumación, Informes de seguimiento, Notificaciones, Usuarios y entidades, Ver Perfil. El botón **Ocultar** contrae el menú. El panel de accesibilidad tiene "Alternar alto contraste" (Activar/Desactivar alto contraste), "Reducir tamaño de letra" y "Aumentar tamaño de letra".

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

> 📷 **[CAPTURA MED-02-INI-05]** — Menú lateral del rol
> **Debe mostrar:** El menú lateral completo de un usuario Administrador
> **Resaltar:** Las opciones visibles para el rol
> **Pantalla / ruta:** Menú lateral (`dashboard/src/components/layout/Sidebar.tsx:16-91`)
> **Tomarla con:** Administrador · **Datos:** Usuario de prueba de la ruta
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

> 📷 **[CAPTURA MED-02-INI-06]** — Mensaje ERR-GEN-12
> **Debe mostrar:** La pantalla con el mensaje "Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida." › **Volver al inicio**
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/NotFound.tsx:23-45`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir una dirección que no existe

> 📷 **[CAPTURA MED-02-INI-07]** — Mensaje ERR-GEN-11
> **Debe mostrar:** La pantalla con el mensaje "Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:550-551`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un formulario de registro desde un celular

> 📷 **[CAPTURA MED-02-INI-08]** — Mensaje ERR-GEN-01
> **Debe mostrar:** La pantalla con el mensaje "No tienes permisos para realizar esta acción."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:69-70`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error)

> 📷 **[CAPTURA MED-02-INI-09]** — Mensaje ERR-GEN-03
> **Debe mostrar:** La pantalla con el mensaje "Conflicto con el estado actual del recurso."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:73-74`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Repetir una acción o actuar sobre un registro que cambió de estado

> 📷 **[CAPTURA MED-02-INI-10]** — Mensaje ERR-GEN-05
> **Debe mostrar:** La pantalla con el mensaje "El servidor no está disponible. Por favor, intenta más tarde."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:79-82`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor no está disponible

> 📷 **[CAPTURA MED-02-INI-11]** — Mensaje ERR-GEN-13
> **Debe mostrar:** La pantalla con el mensaje "La solicitud no es válida. Verifica los datos e intenta de nuevo." o "Los datos enviados no son válidos."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:65-76`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Enviar datos con un formato que el servidor no acepta

**⚠️ Atención:**
- Los formularios de registro no se abren en pantallas de celular ("Disponible en escritorio").

#### Actividad 4 — Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el Administrador pueda reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

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
**Qué hacer:** Compare los totales con los de su Inicio con sesión, que se calculan sobre nacional.
**Resultado esperado:** Los totales coinciden: su alcance también es nacional.

> 📷 **[CAPTURA MED-02-INI-12]** — Tablero público
> **Debe mostrar:** La página pública sin sesión con el botón Iniciar sesión
> **Resaltar:** Botón Iniciar sesión
> **Pantalla / ruta:** `/` (`dashboard/src/App.tsx:40`)
> **Tomarla con:** Administrador · **Datos:** Ambiente de pruebas
> **Texto alternativo:** Tablero público de alertas tempranas

**Resultado de la actividad:** Sabe qué información es pública y cuál depende de su sesión.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El tablero no carga | "Error al cargar datos" | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | — |

**⚠️ Atención:**
- La vista pública no muestra recomendaciones, planes ni archivos: solo los bloques del tablero.

### Módulo 03 — Usuarios y entidades

**Prerrequisitos:** Módulo 01 (sesión abierta con rol Administrador).

**Definición del módulo:** Módulo de administración de las cuentas y de las organizaciones. En la pestaña **Usuarios** se invitan usuarios, se ven sus datos, se editan, se activan o inactivan y se reenvían o eliminan invitaciones. En la pestaña **Entidades** se crean, consultan, editan y eliminan las entidades centrales y sus subdirecciones, con su categoría.

**Objetivo del módulo:** Que el Administrador pueda consultar, buscar y filtrar usuarios e invitaciones; ver el detalle de un usuario; invitar un usuario; editar un usuario; activar o inactivar un usuario; reenviar o eliminar una invitación; consultar, buscar y filtrar entidades; agregar una entidad con sus subdirecciones; editar una entidad y sus subdirecciones; eliminar una entidad.

**Contexto del módulo:** Es la primera fase (E0) y se vuelve a usar cuando cambia el personal o las entidades. Entrega a todos los demás módulos las entidades que se asignan como principales o asociadas en las recomendaciones (E2.1) y los usuarios con su rol, entidad, subdirección y departamentos, que determinan qué ve cada uno. Lo usan el Super Administrador y el Administrador; el menú también lo muestra a Consulta Global, pero la pantalla lo rechaza. Para el Administrador: ve todos los usuarios, invitaciones, entidades centrales y subdirecciones. En total, tiene 15 de las 16 funcionalidades del módulo; no tiene: invitar un Super Administrador.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar usuarios e invitaciones (F-USU-01) | Muestra los usuarios activos e inactivos y las invitaciones, con las pestañas Todos, Entidades Territoriales, Administradores, Monitores e Invitaciones. | R | Módulo 03 — Actividad 1 |
| Buscar y filtrar usuarios (F-USU-02) | Busca por nombre y filtra por Rol, Nivel, Estado y Categoría. | R | Módulo 03 — Actividad 1 |
| Ver el detalle de un usuario (F-USU-03) | Muestra "Información de Usuario": rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, apellidos, cargo y correo. | R | Módulo 03 — Actividad 2 |
| Invitar un usuario (F-USU-04) | Crea el usuario con su rol, nivel de acceso, entidad, subdirección, área, departamentos, nombres, cargo y correo, y le envía la invitación. | C | Módulo 03 — Actividad 3 |
| Editar un usuario (F-USU-06) | Cambia los datos del usuario (incluido el rol y su alcance) desde el detalle. | U | Módulo 03 — Actividad 4 |
| Activar o inactivar un usuario (F-USU-07) | Cambia el interruptor **Activo** del usuario: un usuario inactivo no puede iniciar sesión. | Estado | Módulo 03 — Actividad 5 |
| Reenviar una invitación (F-USU-08) | Genera un enlace nuevo y vuelve a enviar el correo de invitación. | Estado | Módulo 03 — Actividad 6 |
| Eliminar una invitación (F-USU-09) | Elimina una invitación que no ha sido aceptada. | D | Módulo 03 — Actividad 6 |
| Listar entidades centrales y subdirecciones (F-USU-10) | Muestra las entidades con las vistas **Centrales** y **Subdirecciones**: nombre, subdirecciones, usuarios, categoría y fecha de creación. | R | Módulo 03 — Actividad 7 |
| Buscar y filtrar entidades (F-USU-11) | Busca por nombre y filtra por Categoría. | R | Módulo 03 — Actividad 7 |
| Ver el detalle de una entidad (F-USU-12) | Muestra la entidad central, su categoría y sus subdirecciones, con búsqueda. | R | Módulo 03 — Actividad 7 |
| Ver los usuarios asignados a una entidad (F-USU-13) | Al pasar el cursor sobre el número de usuarios muestra hasta 5 usuarios asignados. | R | Módulo 03 — Actividad 7 |
| Agregar una entidad con sus subdirecciones (F-USU-14) | Crea una entidad central con su categoría y, si aplica, sus subdirecciones. | C | Módulo 03 — Actividad 8 |
| Editar una entidad y sus subdirecciones (F-USU-15) | Cambia el nombre o la categoría y agrega o elimina subdirecciones. | U | Módulo 03 — Actividad 9 |
| Eliminar una entidad (F-USU-16) | Elimina una entidad que no tiene usuarios, subdirecciones, alertas ni recomendaciones. | D | Módulo 03 — Actividad 10 |

#### Actividad 1 — Consultar, buscar y filtrar usuarios e invitaciones

**Objetivo de la actividad:** Que el Administrador pueda encontrar a cualquier usuario o invitación y saber en qué estado está.

**Cuándo se hace y requisitos previos:** Secuencia E0.5. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral › **Usuarios y entidades** › pestaña **Usuarios**.

**Qué ve:** "Usuarios y entidades — Administra a los miembros de tu equipo y las entidades a las que pertenecen, definiendo sus permisos de acceso y roles dentro de la plataforma." con dos pestañas: **Usuarios** y **Entidades**.

En **Usuarios**: el contador, el botón **Enviar invitación**, las vistas **Todos**, **Entidades Territoriales**, **Administradores**, **Monitores** e **Invitaciones**, el buscador "Buscar por nombre" y **Filtros**.

| Columna (usuarios) | Descripción |
|---|---|
| Usuarios | Nombre y correo |
| Rol | Rol asignado |
| Nivel | Central o Subdirección (Entidad Territorial) |
| Fecha de activación | Fecha en que aceptó la invitación |
| Estado | Interruptor **Activo** |

| Columna (Invitaciones) | Descripción |
|---|---|
| Usuario | Nombre del invitado |
| Email | Correo |
| Rol | Rol asignado |
| Entidad | Entidad asignada |
| Estado | Pendiente o Expirada |
| Fecha de Expiración | Vence 7 días después del envío |

Filtros: **Rol** ("Todos los roles": Super Administrador, Administrador, Líder de Macrozona, Monitor, Consulta Global, Consulta Entidad, Consulta Departamentos, Entidad Territorial - Central, Entidad Territorial - Subdirección), **Nivel** ("Todos los niveles"), **Estado** ("Todos los estados": Activo, Inactivo, Invitación Pendiente, Invitación Expirada) y **Categoría** ("Todas las categorías"). Botones **Limpiar filtros** y **Aplicar filtros**.

**Pasos:**

##### Paso 1.1 — Abrir la pestaña Usuarios
**Objetivo del paso:** Ver los usuarios de la plataforma.
**Qué hacer:** Haga clic en **Usuarios y entidades** y luego en la pestaña **Usuarios**.
**Resultado esperado:** Aparece la tabla con "Cargando usuarios..." y luego los registros.

##### Paso 1.2 — Cambiar de vista
**Objetivo del paso:** Ver un grupo de usuarios.
**Qué hacer:** Haga clic en **Todos**, **Entidades Territoriales**, **Administradores**, **Monitores** o **Invitaciones**.
**Resultado esperado:** La tabla muestra solo ese grupo; **Invitaciones** muestra Pendiente y Expirada.

##### Paso 1.3 — Buscar por nombre
**Objetivo del paso:** Encontrar un usuario puntual.
**Qué hacer:** Escriba el nombre o el correo en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 1.4 — Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** Haga clic en **Filtros**, elija Rol, Nivel, Estado o Categoría y haga clic en **Aplicar filtros**; para quitar, **Limpiar filtros**.
**Resultado esperado:** La tabla muestra los usuarios que cumplen todos los filtros.

> 📷 **[CAPTURA MED-02-USU-01]** — Pestaña Usuarios
> **Debe mostrar:** La tabla de usuarios con las vistas y el botón Enviar invitación
> **Resaltar:** Vistas Todos…Invitaciones; Buscar por nombre; Filtros; Enviar invitación
> **Pantalla / ruta:** Usuarios y entidades › Usuarios (`dashboard/src/components/usuarios-entidades/UsuariosTab.tsx`)
> **Tomarla con:** Administrador · **Datos:** Usuarios de prueba de varios roles
> **Texto alternativo:** Listado de usuarios e invitaciones

**Resultado de la actividad:** Ubica el usuario o la invitación y su estado.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El listado de usuarios o entidades no carga | "Error al cargar usuarios" / "Error al cargar entidades" | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-USU-02]** — Mensaje ERR-USU-17
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar usuarios" / "Error al cargar entidades"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/UsuariosYEntidades.tsx:143,178`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El listado de usuarios o entidades no carga

> 📷 **[CAPTURA MED-02-USU-03]** — Mensaje ERR-GEN-07
> **Debe mostrar:** La pantalla con el mensaje "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/SearchEmptyState.tsx:9-10`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar o filtrar sin coincidencias

**⚠️ Atención:**
- El filtro **Categoría** aparece en la pantalla, pero el código lo marca como "Pendiente de clarificación" (`dashboard/src/components/ui/UserFiltersModal.tsx:396`): verifique el resultado.

#### Actividad 2 — Ver el detalle de un usuario

**Objetivo de la actividad:** Que el Administrador pueda revisar todos los datos de acceso de un usuario antes de editarlo o de responder una consulta.

**Cuándo se hace y requisitos previos:** Secuencia E0.5. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Usuarios › fila › ícono **Detalle** (en la vista Invitaciones: **Ver detalle**) › ventana "Información de Usuario — Datos asignados para el acceso a la plataforma".

**Qué ve:** La ventana muestra Rol (con el tooltip "Tipos de roles"), Nivel de acceso, Entidad Central, Subdirección, Área, Departamentos (para Monitor, Líder de Macrozona y Consulta Departamentos), Nombres, Apellidos, Cargo y Correo electrónico, con los botones **Cerrar** y **Editar**.

**Pasos:**

##### Paso 2.1 — Abrir el detalle
**Objetivo del paso:** Ver los datos completos.
**Qué hacer:** En la fila del usuario haga clic en el ícono **Detalle** (en Invitaciones, **Ver detalle**).
**Resultado esperado:** Se abre "Información de Usuario".

##### Paso 2.2 — Revisar rol y alcance
**Objetivo del paso:** Confirmar qué verá el usuario.
**Qué hacer:** Lea Rol, Nivel de acceso, Entidad Central, Subdirección y Departamentos.
**Resultado esperado:** Identifica el alcance del usuario.

##### Paso 2.3 — Cerrar o pasar a editar
**Objetivo del paso:** Terminar la consulta.
**Qué hacer:** Haga clic en **Cerrar** o en **Editar** para modificar.
**Resultado esperado:** Se cierra la ventana o se abre "Editar usuario".

> 📷 **[CAPTURA MED-02-USU-04]** — Información de Usuario
> **Debe mostrar:** La ventana de detalle de un Monitor de prueba
> **Resaltar:** Rol, Departamentos; botón Editar
> **Pantalla / ruta:** `dashboard/src/components/ui/UserDetailModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Monitor de prueba con dos departamentos
> **Texto alternativo:** Detalle de un usuario con su rol y departamentos

**Resultado de la actividad:** Conoce los datos y el alcance del usuario.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

> 📷 **[CAPTURA MED-02-USU-05]** — Mensaje ERR-GEN-02
> **Debe mostrar:** La pantalla con el mensaje "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:71-72`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir un registro que ya no existe o fue eliminado

#### Actividad 3 — Invitar un usuario

**Objetivo de la actividad:** Que el Administrador pueda crear un usuario con el rol y el alcance correctos y enviarle la invitación por correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.2.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para invitar o editar un usuario, su correo no puede estar registrado en otro usuario. | Revise el estado o el dato en la pantalla antes de actuar | Buscar el usuario existente antes de invitar (Super Administrador o Administrador) | RN-USU-01 |
| Solo un Super Administrador puede invitar, editar o asignar el rol Super Administrador. | Revise el estado o el dato en la pantalla antes de actuar | Pedir la operación a un Super Administrador (Super Administrador) | RN-USU-02 |
| Para invitar Entidad Territorial se requiere la Entidad Central (y la Subdirección si el nivel es Subdirección), activas. | La entidad aparece en la lista de Entidad Central | Crear o activar la entidad antes de invitar (Super Administrador o Administrador) | RN-USU-03 |
| Para invitar Monitor o Líder de Macrozona se requieren departamentos (en pantalla también para Consulta Departamentos). | Revise el estado o el dato en la pantalla antes de actuar | Seleccionar los departamentos (Super Administrador o Administrador) | RN-USU-04 |
| El cargo es obligatorio para Entidad Territorial, Monitor (en el servidor) y Líder de Macrozona (en pantalla). | Revise el estado o el dato en la pantalla antes de actuar | Diligenciar el cargo (Super Administrador o Administrador) | RN-USU-05 |
| Para Consulta Entidad la pantalla exige la Entidad Central; el servidor no la exige (si faltara, el usuario vería todas las alertas: riesgo R4). | Revise el estado o el dato en la pantalla antes de actuar | Seleccionar siempre la entidad (Super Administrador o Administrador) | RN-USU-06 |

**Dónde:** Usuarios y entidades › **Usuarios** › **Enviar invitación** › ventana "Enviar invitación".

**Qué ve:** La ventana "Enviar invitación — Envía una invitación por correo electrónico para que el usuario acceda a la plataforma." con el aviso "Permisos no editables — Una vez enviada la invitación, los permisos no podrán modificarse. Para cambios, deshabilita el usuario y envía una nueva invitación." y el formulario. Los campos que aparecen dependen del **Rol**.

**Campos a diligenciar — Enviar invitación / Editar usuario:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Rol (`role`) | Sí | Lista de selección única | — | Entidad Territorial, Administrador, Líder de Macrozona, Monitor, Consulta Global, Consulta Entidad, Consulta Departamentos (+ Super Administrador solo si quien invita es Super Administrador) | Define qué otros campos aparecen y cuáles son obligatorios | Monitor | "El rol es requerido" |
| 2 | Nivel de acceso (`(define ENTIDAD_TERRITORIAL_CENTRAL o _SUBDIRECCION)`) | Condicional: solo si Rol = Entidad Territorial | Lista de selección única | — | Central, Subdirección | Rol = Entidad Territorial | Central | "El nivel de acceso es requerido" |
| 3 | Entidad Central (`organization_id`) | Condicional: obligatoria para Entidad Territorial y Consulta Entidad; "(opcional)" para Administrador, Líder de Macrozona y Monitor; no aparece para los demás | Lista con búsqueda | Entidad central activa | Entidades centrales registradas | Rol; se limpia al cambiar el Nivel de acceso | Gobernación de Prueba | "La entidad central es requerida" / "organization_id es obligatorio para el rol ENTIDAD_TERRITORIAL_CENTRAL" / "La organización no existe o no está activa" |
| 4 | Subdirección (`sub_organization_id`) | Condicional: obligatoria si Nivel de acceso = Subdirección | Lista con búsqueda | Subdirección activa de la Entidad Central | Subdirecciones de la entidad elegida | Entidad Central | Secretaría de Gobierno de Prueba | "La subdirección es requerida" / "La sub-organización no existe o no está activa" |
| 5 | Área (`organization_area`) | No | Texto | — | — | — | Oficina de Paz | — |
| 6 | Departamentos (`states`) | Condicional: obligatorio para Monitor, Líder de Macrozona y Consulta Departamentos | Lista de selección múltiple con búsqueda | Al menos uno | Departamentos de Colombia (catálogo Divipola) | Rol | CAUCA, NARIÑO | "Debe seleccionar al menos un departamento" / "Los departamentos son obligatorios para el rol Monitor y Líder Macrozona" |
| 7 | Nombres y Apellidos (Nombres) (`first_name`) | Sí | Texto | No vacío | — | — | Ana | "El nombre es requerido" |
| 8 | Nombres y Apellidos (Apellidos) (`last_name`) | Sí | Texto | No vacío | — | — | Prueba | "El apellido es requerido" |
| 9 | Cargo (`position`) | Condicional: obligatorio para Entidad Territorial, Líder de Macrozona y Monitor | Texto | No vacío cuando es obligatorio | — | Rol | Profesional especializado | "El cargo es requerido" / "El cargo es obligatorio para este rol" |
| 10 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo; único | — | — | ana.prueba@ejemplo.gov.co | "El correo electrónico es requerido" / "El correo electrónico no es válido" / "El correo electrónico ya existe" |

- Campos que llena el sistema: Estado (Invitación pendiente), fecha de expiración (7 días) y fecha de activación.
- Campos que se bloquean: Al editar a un Super Administrador, el Rol queda bloqueado. El aviso "Permisos no editables" dice que los permisos no se pueden modificar, pero el servidor sí permite cambiar el rol al editar (`main-api/CipratApi/Servicios/ActualizacionUsuarioServicio.cs:130`).
- Archivos: No aplica.
- Guardar o enviar con: **Enviar Invitación** (edición: **Guardar Cambios**).

**Pasos:**

##### Paso 3.1 — Abrir el formulario
**Objetivo del paso:** Iniciar la invitación.
**Qué hacer:** En la pestaña **Usuarios** haga clic en **Enviar invitación**.
**Resultado esperado:** Se abre la ventana "Enviar invitación".

##### Paso 3.2 — Elegir el Rol
**Objetivo del paso:** Definir los permisos y qué campos se piden.
**Qué hacer:** Despliegue **Rol** y elija el rol (pase el cursor por el ícono de ayuda para leer "Tipos de roles"). La opción "Super Administrador" no aparece para su rol.
**Resultado esperado:** Según el rol aparecen o desaparecen Nivel de acceso, Entidad Central, Subdirección y Departamentos, y el Cargo se vuelve obligatorio u opcional.

##### Paso 3.3 — Definir el Nivel de acceso (solo Entidad Territorial)
**Objetivo del paso:** Distinguir entre usuario de la entidad central y de una subdirección.
**Qué hacer:** Si el rol es "Entidad Territorial", elija **Nivel de acceso**: Central o Subdirección.
**Resultado esperado:** Se limpian Entidad Central y Subdirección para elegirlas de nuevo.

##### Paso 3.4 — Elegir la Entidad Central y la Subdirección
**Objetivo del paso:** Fijar el alcance por entidad.
**Qué hacer:** Despliegue **Entidad Central**, escriba en "Buscar entidad..." y elíjala (obligatoria para Entidad Territorial y Consulta Entidad; opcional para Administrador, Líder de Macrozona y Monitor). Si el nivel es Subdirección, elija también **Subdirección**.
**Resultado esperado:** Aparece "El usuario solo tendrá acceso a las alertas de esta subdirección." cuando aplica.

##### Paso 3.5 — Escribir el Área (opcional)
**Objetivo del paso:** Registrar la dependencia interna del usuario.
**Qué hacer:** Si aplica, escriba el **Área**.
**Resultado esperado:** El campo queda diligenciado.

##### Paso 3.6 — Elegir los Departamentos (Monitor, Líder de Macrozona, Consulta Departamentos)
**Objetivo del paso:** Fijar el alcance territorial.
**Qué hacer:** Despliegue **Departamentos**, busque y marque uno o varios.
**Resultado esperado:** Aparece "El usuario solo tendrá acceso a las alertas de estos departamentos."

##### Paso 3.7 — Escribir nombres, apellidos y cargo
**Objetivo del paso:** Identificar al usuario.
**Qué hacer:** Escriba **Nombres** y **Apellidos**; escriba el **Cargo** (obligatorio para Entidad Territorial, Líder de Macrozona y Monitor).
**Resultado esperado:** Los campos quedan diligenciados.

##### Paso 3.8 — Escribir el correo
**Objetivo del paso:** Indicar a dónde llega la invitación.
**Qué hacer:** Escriba el **Correo electrónico** institucional, sin espacios.
**Resultado esperado:** Si el formato no es válido: "El correo electrónico no es válido".

##### Paso 3.9 — Revisar antes de enviar
**Objetivo del paso:** Evitar errores de permisos.
**Qué hacer:** Verifique el rol, la entidad, la subdirección, los departamentos y el correo: el aviso indica que los permisos no deberían cambiarse después.
**Resultado esperado:** Los datos están completos.

##### Paso 3.10 — Enviar la invitación
**Objetivo del paso:** Crear el usuario y enviar el correo.
**Qué hacer:** Haga clic en **Enviar Invitación**.
**Resultado esperado:** Aparece "Invitación enviada con éxito — Se ha enviado una invitación a {nombre} ({correo})." y el usuario aparece en **Invitaciones** con estado Pendiente.

> 🎞️ **[GIF MED-02-USU-06]** — Invitar un usuario
> **Debe mostrar:** El formulario "Enviar invitación" diligenciado para un Monitor
> **Resaltar:** Rol, Departamentos, Cargo, Correo; botón Enviar Invitación; mensaje de éxito
> **Pantalla / ruta:** Usuarios › Enviar invitación (`dashboard/src/components/ui/UserFormModal.tsx`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock
> **Solo para GIF — Secuencia:** 1) Enviar invitación 2) Rol Monitor 3) Departamentos 4) Nombres, Cargo, Correo 5) Enviar Invitación · **Duración aproximada:** 30 segundos
> **Texto alternativo:** Animación del envío de una invitación

**Resultado de la actividad:** El usuario queda en "Invitación pendiente" con 7 días para activar su cuenta y recibe el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas".

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Enviar la invitación con campos vacíos | "El rol es requerido", "El nivel de acceso es requerido", "La entidad central es requerida", "La subdirección es requerida", "El nombre es requerido", "El apellido es requerido", "El cargo es requerido", "Debe seleccionar al menos un departamento", "El correo electrónico es requerido", "El correo electrónico no es válido" | Faltan datos obligatorios según el rol. | Complete los campos marcados con * según el rol elegido y vuelva a hacer clic en **Enviar Invitación**. | Elija primero el **Rol**: de él dependen los demás campos. |
| Invitar o editar con un correo ya registrado | "El correo electrónico ya existe" (al editar: "Ya existe un usuario con el correo electrónico '…'") | El correo debe ser único. | Busque el usuario existente en la pestaña **Usuarios** o **Invitaciones**; si su invitación venció, use **Reenviar**. | Busque por correo antes de invitar. |
| Intentar crear o editar un Super Administrador | "Solo un Super Administrador puede crear otros Super Administradores" / "Solo Super Administradores pueden editar usuarios Super Administrador" | Restricción del rol Administrador. | Pida la operación a un Super Administrador. | — |
| El servidor rechaza la invitación por datos del rol | "El cargo es obligatorio para este rol", "Los departamentos son obligatorios para el rol Monitor y Líder Macrozona", "organization_id es obligatorio para el rol ENTIDAD_TERRITORIAL_CENTRAL", "organization_id y sub_organization_id son obligatorios para el rol ENTIDAD_TERRITORIAL_SUBDIRECCION" | Falta un dato que el servidor exige para el rol. | Complete el cargo, los departamentos, la entidad o la subdirección según el rol. | — |
| Asignar una entidad o subdirección inactiva | "La organización no existe o no está activa" / "La sub-organización no existe o no está activa" | La entidad elegida no está activa. | Elija otra entidad activa o revise la entidad en la pestaña **Entidades**. | — |
| Abrir un formulario de registro desde un celular | "Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio." | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Planee el registro desde un computador. |

> 📷 **[CAPTURA MED-02-USU-07]** — Mensaje ERR-USU-01
> **Debe mostrar:** La pantalla con el mensaje "El rol es requerido", "El nivel de acceso es requerido", "La entidad central es requerida", "La subdirección es requerida", "El nombre es requerido", "El apell
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/UserFormModal.tsx:217-271`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Enviar la invitación con campos vacíos

> 📷 **[CAPTURA MED-02-USU-08]** — Mensaje ERR-USU-02
> **Debe mostrar:** La pantalla con el mensaje "El correo electrónico ya existe" (al editar: "Ya existe un usuario con el correo electrónico '…'")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:176`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Invitar o editar con un correo ya registrado

> 📷 **[CAPTURA MED-02-USU-09]** — Mensaje ERR-USU-03
> **Debe mostrar:** La pantalla con el mensaje "Solo un Super Administrador puede crear otros Super Administradores" / "Solo Super Administradores pueden editar usuarios Super Administrador"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:55`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar crear o editar un Super Administrador

> 📷 **[CAPTURA MED-02-USU-10]** — Mensaje ERR-USU-04
> **Debe mostrar:** La pantalla con el mensaje "El cargo es obligatorio para este rol", "Los departamentos son obligatorios para el rol Monitor y Líder Macrozona", "organization_id es obligatorio para el rol
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:69-126`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor rechaza la invitación por datos del rol

> 📷 **[CAPTURA MED-02-USU-11]** — Mensaje ERR-USU-05
> **Debe mostrar:** La pantalla con el mensaje "La organización no existe o no está activa" / "La sub-organización no existe o no está activa"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:116-165`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Asignar una entidad o subdirección inactiva

**⚠️ Atención:**
- ⚠️ Un usuario de Consulta Entidad sin entidad vería todas las alertas (riesgo R4): elija siempre la entidad.
- ⚠️ Un Monitor o Líder sin departamentos no ve ninguna alerta.
- Para la Entidad Territorial con nivel Central: el sistema le muestra solo las recomendaciones cuya Entidad Principal es exactamente esa entidad, no las de sus subdirecciones.

**Ejemplo:** Monitor para Cauca y Nariño: Rol "Monitor", Departamentos CAUCA y NARIÑO, Nombres "Ana", Apellidos "Prueba", Cargo "Profesional especializado", Correo "ana.prueba@ejemplo.gov.co" (datos ficticios).

#### Actividad 4 — Editar un usuario

**Objetivo de la actividad:** Que el Administrador pueda corregir los datos de un usuario (nombres, cargo, correo, entidad, departamentos o rol).

**Cuándo se hace y requisitos previos:** Secuencia E0.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para invitar o editar un usuario, su correo no puede estar registrado en otro usuario. | Revise el estado o el dato en la pantalla antes de actuar | Buscar el usuario existente antes de invitar (Super Administrador o Administrador) | RN-USU-01 |
| Solo un Super Administrador puede invitar, editar o asignar el rol Super Administrador. | Revise el estado o el dato en la pantalla antes de actuar | Pedir la operación a un Super Administrador (Super Administrador) | RN-USU-02 |
| Para invitar Entidad Territorial se requiere la Entidad Central (y la Subdirección si el nivel es Subdirección), activas. | La entidad aparece en la lista de Entidad Central | Crear o activar la entidad antes de invitar (Super Administrador o Administrador) | RN-USU-03 |
| Para invitar Monitor o Líder de Macrozona se requieren departamentos (en pantalla también para Consulta Departamentos). | Revise el estado o el dato en la pantalla antes de actuar | Seleccionar los departamentos (Super Administrador o Administrador) | RN-USU-04 |
| El cargo es obligatorio para Entidad Territorial, Monitor (en el servidor) y Líder de Macrozona (en pantalla). | Revise el estado o el dato en la pantalla antes de actuar | Diligenciar el cargo (Super Administrador o Administrador) | RN-USU-05 |

**Dónde:** Usuarios › fila › ícono **Editar** (o **Detalle** › **Editar**) › ventana "Editar usuario".

**Qué ve:** El mismo formulario de la invitación con los datos actuales y el texto "Edita los niveles de permiso y su información personal.".

**Campos a diligenciar — Enviar invitación / Editar usuario:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Rol (`role`) | Sí | Lista de selección única | — | Entidad Territorial, Administrador, Líder de Macrozona, Monitor, Consulta Global, Consulta Entidad, Consulta Departamentos (+ Super Administrador solo si quien invita es Super Administrador) | Define qué otros campos aparecen y cuáles son obligatorios | Monitor | "El rol es requerido" |
| 2 | Nivel de acceso (`(define ENTIDAD_TERRITORIAL_CENTRAL o _SUBDIRECCION)`) | Condicional: solo si Rol = Entidad Territorial | Lista de selección única | — | Central, Subdirección | Rol = Entidad Territorial | Central | "El nivel de acceso es requerido" |
| 3 | Entidad Central (`organization_id`) | Condicional: obligatoria para Entidad Territorial y Consulta Entidad; "(opcional)" para Administrador, Líder de Macrozona y Monitor; no aparece para los demás | Lista con búsqueda | Entidad central activa | Entidades centrales registradas | Rol; se limpia al cambiar el Nivel de acceso | Gobernación de Prueba | "La entidad central es requerida" / "organization_id es obligatorio para el rol ENTIDAD_TERRITORIAL_CENTRAL" / "La organización no existe o no está activa" |
| 4 | Subdirección (`sub_organization_id`) | Condicional: obligatoria si Nivel de acceso = Subdirección | Lista con búsqueda | Subdirección activa de la Entidad Central | Subdirecciones de la entidad elegida | Entidad Central | Secretaría de Gobierno de Prueba | "La subdirección es requerida" / "La sub-organización no existe o no está activa" |
| 5 | Área (`organization_area`) | No | Texto | — | — | — | Oficina de Paz | — |
| 6 | Departamentos (`states`) | Condicional: obligatorio para Monitor, Líder de Macrozona y Consulta Departamentos | Lista de selección múltiple con búsqueda | Al menos uno | Departamentos de Colombia (catálogo Divipola) | Rol | CAUCA, NARIÑO | "Debe seleccionar al menos un departamento" / "Los departamentos son obligatorios para el rol Monitor y Líder Macrozona" |
| 7 | Nombres y Apellidos (Nombres) (`first_name`) | Sí | Texto | No vacío | — | — | Ana | "El nombre es requerido" |
| 8 | Nombres y Apellidos (Apellidos) (`last_name`) | Sí | Texto | No vacío | — | — | Prueba | "El apellido es requerido" |
| 9 | Cargo (`position`) | Condicional: obligatorio para Entidad Territorial, Líder de Macrozona y Monitor | Texto | No vacío cuando es obligatorio | — | Rol | Profesional especializado | "El cargo es requerido" / "El cargo es obligatorio para este rol" |
| 10 | Correo electrónico (`email`) | Sí | Texto (correo) | Formato de correo; único | — | — | ana.prueba@ejemplo.gov.co | "El correo electrónico es requerido" / "El correo electrónico no es válido" / "El correo electrónico ya existe" |

- Campos que llena el sistema: Estado (Invitación pendiente), fecha de expiración (7 días) y fecha de activación.
- Campos que se bloquean: Al editar a un Super Administrador, el Rol queda bloqueado. El aviso "Permisos no editables" dice que los permisos no se pueden modificar, pero el servidor sí permite cambiar el rol al editar (`main-api/CipratApi/Servicios/ActualizacionUsuarioServicio.cs:130`).
- Archivos: No aplica.
- Guardar o enviar con: **Enviar Invitación** (edición: **Guardar Cambios**).

**Pasos:**

##### Paso 4.1 — Abrir la edición
**Objetivo del paso:** Cargar los datos actuales.
**Qué hacer:** En la fila del usuario haga clic en el ícono **Editar** (o abra **Detalle** y haga clic en **Editar**).
**Resultado esperado:** Se abre "Editar usuario" con los datos actuales.

##### Paso 4.2 — Cambiar los datos
**Objetivo del paso:** Corregir lo necesario.
**Qué hacer:** Modifique los campos que correspondan, con las mismas reglas de la invitación (Rol, Nivel de acceso, Entidad Central, Subdirección, Área, Departamentos, Nombres, Apellidos, Cargo, Correo electrónico).
**Resultado esperado:** Los campos quedan con los datos nuevos.

##### Paso 4.3 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Usuario actualizado con éxito — Se han guardado los cambios de {nombre}."

> 📷 **[CAPTURA MED-02-USU-12]** — Editar usuario
> **Debe mostrar:** La ventana "Editar usuario" de un usuario de prueba
> **Resaltar:** Botón Guardar Cambios
> **Pantalla / ruta:** `dashboard/src/components/ui/UserFormModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Usuario Mock
> **Texto alternativo:** Formulario de edición de usuario

**Resultado de la actividad:** El usuario queda con los datos nuevos; el cambio de alcance aplica en su siguiente ingreso.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Enviar la invitación con campos vacíos | "El rol es requerido", "El nivel de acceso es requerido", "La entidad central es requerida", "La subdirección es requerida", "El nombre es requerido", "El apellido es requerido", "El cargo es requerido", "Debe seleccionar al menos un departamento", "El correo electrónico es requerido", "El correo electrónico no es válido" | Faltan datos obligatorios según el rol. | Complete los campos marcados con * según el rol elegido y vuelva a hacer clic en **Enviar Invitación**. | Elija primero el **Rol**: de él dependen los demás campos. |
| Invitar o editar con un correo ya registrado | "El correo electrónico ya existe" (al editar: "Ya existe un usuario con el correo electrónico '…'") | El correo debe ser único. | Busque el usuario existente en la pestaña **Usuarios** o **Invitaciones**; si su invitación venció, use **Reenviar**. | Busque por correo antes de invitar. |
| Intentar crear o editar un Super Administrador | "Solo un Super Administrador puede crear otros Super Administradores" / "Solo Super Administradores pueden editar usuarios Super Administrador" | Restricción del rol Administrador. | Pida la operación a un Super Administrador. | — |
| El servidor rechaza la invitación por datos del rol | "El cargo es obligatorio para este rol", "Los departamentos son obligatorios para el rol Monitor y Líder Macrozona", "organization_id es obligatorio para el rol ENTIDAD_TERRITORIAL_CENTRAL", "organization_id y sub_organization_id son obligatorios para el rol ENTIDAD_TERRITORIAL_SUBDIRECCION" | Falta un dato que el servidor exige para el rol. | Complete el cargo, los departamentos, la entidad o la subdirección según el rol. | — |
| Asignar una entidad o subdirección inactiva | "La organización no existe o no está activa" / "La sub-organización no existe o no está activa" | La entidad elegida no está activa. | Elija otra entidad activa o revise la entidad en la pestaña **Entidades**. | — |

**⚠️ Atención:**
- El aviso de la invitación dice que los permisos no son editables, pero la edición sí permite cambiar el rol y el servidor lo acepta (`main-api/CipratApi/Servicios/ActualizacionUsuarioServicio.cs:130`). Haga estos cambios con cuidado.
- No puede editar usuarios Super Administrador.

#### Actividad 5 — Activar o inactivar un usuario

**Objetivo de la actividad:** Que el Administrador pueda impedir o restablecer el ingreso de un usuario cambiando su estado.

**Cuándo se hace y requisitos previos:** Secuencia E0.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para activar o inactivar un usuario, no puede ser el propio, no puede ser Super Administrador y debe haber aceptado su invitación. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el cambio a otro administrador o esperar la activación (Super Administrador o Administrador) | RN-USU-07 |

**Dónde:** Usuarios › columna **Estado** › interruptor **Activo**.

**Qué ve:** En la columna Estado, un interruptor verde (Activo) o gris (Inactivo). En su propia fila el interruptor está deshabilitado con "No puedes desactivar tu propia cuenta".

**Pasos:**

##### Paso 5.1 — Ubicar al usuario
**Objetivo del paso:** Encontrar la fila correcta.
**Qué hacer:** Busque al usuario en la vista **Todos**.
**Resultado esperado:** Ve su fila con el interruptor.

##### Paso 5.2 — Cambiar el estado
**Objetivo del paso:** Activar o inactivar.
**Qué hacer:** Haga clic en el interruptor **Activo**.
**Resultado esperado:** Aparece "Estado actualizado — El usuario {nombre} ha sido {activado/desactivado} correctamente."

> 📷 **[CAPTURA MED-02-USU-13]** — Interruptor de estado
> **Debe mostrar:** La columna Estado con un usuario activo y otro inactivo
> **Resaltar:** Interruptor Activo
> **Pantalla / ruta:** `dashboard/src/components/usuarios-entidades/UsuariosTab.tsx:480-519`
> **Tomarla con:** Administrador · **Datos:** Usuarios Mock
> **Texto alternativo:** Interruptor para activar o inactivar usuarios

**Resultado de la actividad:** Un usuario inactivo no puede iniciar sesión ("Cuenta no activa").

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Intentar inactivar su propia cuenta | Interruptor deshabilitado con el mensaje "No puedes desactivar tu propia cuenta" (servidor: "No puedes cambiar tu propio estado. Por favor contacta a otro administrador.") | Nadie puede cambiar su propio estado. | Pida el cambio a otro administrador. | — |
| Intentar inactivar a un Super Administrador | "No se puede cambiar el estado de un usuario con rol SUPER_ADMINISTRADOR" | El estado de un Super Administrador no se cambia desde la plataforma. | Escale al equipo técnico si se requiere. | — |
| Intentar activar o inactivar a quien no ha aceptado la invitación | "No se puede cambiar el estado de un usuario con estado {estado}. El usuario debe aceptar su invitación primero." | El usuario está en Invitación pendiente o expirada. | Use **Reenviar** para que active su cuenta, o **Eliminar invitación**. | — |

> 📷 **[CAPTURA MED-02-USU-14]** — Mensaje ERR-USU-06
> **Debe mostrar:** La pantalla con el mensaje Interruptor deshabilitado con el mensaje "No puedes desactivar tu propia cuenta" (servidor: "No puedes cambiar tu propio estado. Por favor contacta a otro admin
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/usuarios-entidades/UsuariosTab.tsx:482`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar inactivar su propia cuenta

> 📷 **[CAPTURA MED-02-USU-15]** — Mensaje ERR-USU-07
> **Debe mostrar:** La pantalla con el mensaje "No se puede cambiar el estado de un usuario con rol SUPER_ADMINISTRADOR"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/EstadoUsuarioServicio.cs:62-66`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar inactivar a un Super Administrador

> 📷 **[CAPTURA MED-02-USU-16]** — Mensaje ERR-USU-08
> **Debe mostrar:** La pantalla con el mensaje "No se puede cambiar el estado de un usuario con estado {estado}. El usuario debe aceptar su invitación primero."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/EstadoUsuarioServicio.cs:70-76`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar activar o inactivar a quien no ha aceptado la invitación

**⚠️ Atención:**
- ⚠️ El acceso no se corta de inmediato: una sesión ya abierta sigue funcionando hasta que vence (hasta 12 horas; riesgo R9).

#### Actividad 6 — Reenviar o eliminar una invitación

**Objetivo de la actividad:** Que el Administrador pueda volver a enviar una invitación vencida o eliminar una invitación que no debe usarse.

**Cuándo se hace y requisitos previos:** Secuencia E0.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para reenviar o eliminar una invitación, debe estar Pendiente o Expirada. | La fila está en la pestaña Invitaciones | Verificar el estado en la pestaña Invitaciones (Super Administrador o Administrador) | RN-USU-08 |

**Dónde:** Usuarios › vista **Invitaciones** › **Reenviar** / **Eliminar invitación**.

**Qué ve:** En cada invitación, el estado (Pendiente o Expirada), la "Fecha de Expiración" y los botones **Ver detalle**, **Reenviar** y **Eliminar invitación**.

**Pasos:**

##### Paso 6.1 — Abrir Invitaciones
**Objetivo del paso:** Ver las invitaciones sin aceptar.
**Qué hacer:** Haga clic en la vista **Invitaciones**.
**Resultado esperado:** Aparecen las invitaciones Pendiente y Expirada.

##### Paso 6.2 — Reenviar
**Objetivo del paso:** Dar 7 días más al usuario.
**Qué hacer:** Haga clic en **Reenviar** (muestra "Reenviando...").
**Resultado esperado:** Aparece "Invitación reenviada — Se ha reenviado la invitación a {nombre} ({correo})." y la nueva fecha de expiración.

##### Paso 6.3 — Eliminar
**Objetivo del paso:** Retirar una invitación equivocada.
**Qué hacer:** Haga clic en **Eliminar invitación** y confirme en "Eliminar invitación — ¿Estás seguro de que deseas eliminar la invitación? Esta acción no se puede deshacer.".
**Resultado esperado:** Aparece "Invitación eliminada con éxito".

> 📷 **[CAPTURA MED-02-USU-17]** — Vista Invitaciones
> **Debe mostrar:** Una invitación Expirada con los botones Reenviar y Eliminar invitación
> **Resaltar:** Estado Expirada; Fecha de Expiración; Reenviar
> **Pantalla / ruta:** `dashboard/src/components/usuarios-entidades/UsuariosTab.tsx:318-405`
> **Tomarla con:** Administrador · **Datos:** Invitación Mock expirada
> **Texto alternativo:** Invitación expirada con opción de reenviar

**Resultado de la actividad:** La invitación queda vigente de nuevo o eliminada.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Reenviar o eliminar la invitación de un usuario ya activo | "Solo se pueden reenviar invitaciones a usuarios con estado Pendiente o Expirada" / "Solo se pueden eliminar invitaciones con estado Pendiente o Expirada. Este usuario ya está activo o inactivo." | El usuario ya activó su cuenta. | Si no puede ingresar, que use **¿Has olvidado tu contraseña?**; para retirarlo, inactívelo. | — |

> 📷 **[CAPTURA MED-02-USU-18]** — Mensaje ERR-USU-09
> **Debe mostrar:** La pantalla con el mensaje "Solo se pueden reenviar invitaciones a usuarios con estado Pendiente o Expirada" / "Solo se pueden eliminar invitaciones con estado Pendiente o Expirada. Este 
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/EliminacionInvitacionUsuarioServicio.cs:39-44`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Reenviar o eliminar la invitación de un usuario ya activo

**⚠️ Atención:**
- ⚠️ Eliminar una invitación no se puede deshacer.

#### Actividad 7 — Consultar, buscar y filtrar entidades

**Objetivo de la actividad:** Que el Administrador pueda encontrar una entidad central o una subdirección y ver sus usuarios.

**Cuándo se hace y requisitos previos:** Secuencia E0.1. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Usuarios y entidades › pestaña **Entidades**.

**Qué ve:** "Entidades" con el contador, el botón **Agregar Entidad**, las vistas **Centrales** y **Subdirecciones**, "Buscar por nombre" y **Filtros** (Categoría: "Todas las categorías").

| Columna | Descripción |
|---|---|
| Entidades | Nombre de la entidad |
| Subdirecciones | Número de subdirecciones (en Centrales) |
| Usuarios | Número de usuarios; al pasar el cursor muestra "Usuarios asignados" |
| Categoría | Categoría de la entidad |
| Fecha de creación | Fecha de registro |

**Pasos:**

##### Paso 7.1 — Abrir Entidades
**Objetivo del paso:** Ver las entidades registradas.
**Qué hacer:** Haga clic en la pestaña **Entidades**.
**Resultado esperado:** Aparece la vista **Centrales**.

##### Paso 7.2 — Cambiar a Subdirecciones
**Objetivo del paso:** Ver las dependencias.
**Qué hacer:** Haga clic en **Subdirecciones**.
**Resultado esperado:** Aparece la tabla de subdirecciones.

##### Paso 7.3 — Buscar y filtrar
**Objetivo del paso:** Encontrar una entidad.
**Qué hacer:** Escriba en "Buscar por nombre" o use **Filtros** › Categoría › **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 7.4 — Ver los usuarios asignados
**Objetivo del paso:** Saber quién pertenece a la entidad.
**Qué hacer:** Pase el cursor sobre el número de la columna **Usuarios**.
**Resultado esperado:** Aparece "Usuarios asignados" con hasta 5 nombres, o "Sin usuarios asignados".

##### Paso 7.5 — Abrir el detalle
**Objetivo del paso:** Ver las subdirecciones de una entidad.
**Qué hacer:** Haga clic en el ícono **Detalle** de la fila.
**Resultado esperado:** Se abre la ventana con "Entidad central", "Sub direcciones — Subdirecciones asociadas a la entidad central.", el buscador "Buscar subdirección..." y **Mostrar 10 más**.

> 📷 **[CAPTURA MED-02-USU-19]** — Pestaña Entidades
> **Debe mostrar:** La vista Centrales con el tooltip Usuarios asignados abierto
> **Resaltar:** Vistas Centrales/Subdirecciones; columna Usuarios
> **Pantalla / ruta:** `dashboard/src/components/usuarios-entidades/EntidadesTab.tsx`
> **Tomarla con:** Administrador · **Datos:** Entidades Mock
> **Texto alternativo:** Listado de entidades centrales

**Resultado de la actividad:** Ubica la entidad, sus subdirecciones y sus usuarios.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El listado de usuarios o entidades no carga | "Error al cargar usuarios" / "Error al cargar entidades" | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

**⚠️ Atención:**
- Busque siempre antes de crear: la pantalla advierte "verifica primero que no exista ya en la base de datos para evitar duplicados".

#### Actividad 8 — Agregar una entidad con sus subdirecciones

**Objetivo de la actividad:** Que el Administrador pueda registrar una entidad central con su categoría y sus subdirecciones para poder asignarla a usuarios y recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E0.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El nombre de la entidad es único; la entidad central de una subdirección debe estar activa y no puede ser la misma entidad. | Revise el estado o el dato en la pantalla antes de actuar | Buscar la entidad antes de crearla (Super Administrador o Administrador) | RN-USU-09 |
| Para guardar una entidad se requieren nombre y categoría; si se habilitan subdirecciones, al menos una, y no se quita una subdirección en uso. | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario (Super Administrador o Administrador) | RN-USU-11 |

**Dónde:** Entidades › **Agregar Entidad** › ventana "Agregar entidad territorial".

**Qué ve:** La ventana "Agregar entidad territorial — Crea una entidad y verifica primero que no exista ya en la base de datos para evitar duplicados." con el formulario y el botón **Agregar entidad**.

**Campos a diligenciar — Agregar / Editar entidad territorial:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Entidad Central (`name`) | Sí | Texto | Nombre único | — | — | Gobernación de Prueba | "La entidad central es requerida" / "El nombre de la entidad ya existe" |
| 2 | Categoría (`categories`) | Sí | Lista con búsqueda | Una categoría del catálogo | 89 categorías (Alcaldía, Gobernación, Ministerio, Policía, Ejército, Defensoría…); ver 05_catalogos.md | — | Gobernación | "Debe seleccionar una categoría" |
| 3 | Sub Direcciones (interruptor) (`subdirectionsEnabled`) | No | Interruptor | Si está activo, al menos una subdirección | Activo / Inactivo | — | Activo | "Debe agregar al menos una subdirección o deshabilitar las subdirecciones" / "Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones." |
| 4 | Subdirección (cada fila) · **Agregar subdirección** (`subdirecciones[].name`) | Condicional: si el interruptor está activo | Texto repetible | Una fila por subdirección | — | Sub Direcciones | Secretaría de Gobierno de Prueba | "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas." |

- Campos que llena el sistema: Estado Activa y fecha de creación.
- Campos que se bloquean: No se puede quitar una subdirección con usuarios o alertas, ni desactivar las subdirecciones mientras existan.
- Archivos: No aplica.
- Guardar o enviar con: **Agregar entidad** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 8.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** Haga clic en **Agregar Entidad**.
**Resultado esperado:** Se abre "Agregar entidad territorial".

##### Paso 8.2 — Escribir el nombre
**Objetivo del paso:** Identificar la entidad.
**Qué hacer:** En **Entidad Central** escriba el nombre oficial completo (por ejemplo, "Policía Nacional").
**Resultado esperado:** El campo queda diligenciado.

##### Paso 8.3 — Elegir la categoría
**Objetivo del paso:** Clasificar la entidad.
**Qué hacer:** Despliegue **Categoría**, busque y elija una opción.
**Resultado esperado:** La categoría queda seleccionada.

##### Paso 8.4 — Agregar subdirecciones (si aplica)
**Objetivo del paso:** Registrar las dependencias que responderán recomendaciones.
**Qué hacer:** Active **Sub Direcciones** ("Aplica para las entidades segmentadas a nivel municipal.") y use **Agregar subdirección** para cada una; escriba su nombre.
**Resultado esperado:** Aparecen las filas de subdirección.

##### Paso 8.5 — Guardar
**Objetivo del paso:** Crear la entidad.
**Qué hacer:** Revise el nombre y haga clic en **Agregar entidad**.
**Resultado esperado:** Aparece "Entidad creada con éxito — La entidad fue registrada y está lista para su gestión."

> 🎞️ **[GIF MED-02-USU-20]** — Agregar entidad
> **Debe mostrar:** El registro de una entidad con dos subdirecciones
> **Resaltar:** Entidad Central; Categoría; Sub Direcciones; Agregar entidad
> **Pantalla / ruta:** `dashboard/src/components/ui/EntityModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Gobernación de Prueba (Mock)
> **Solo para GIF — Secuencia:** 1) Agregar Entidad 2) Nombre 3) Categoría 4) Subdirecciones 5) Agregar entidad · **Duración aproximada:** 25 segundos
> **Texto alternativo:** Animación del registro de una entidad

**Resultado de la actividad:** La entidad queda Activa y disponible para usuarios y recomendaciones.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Guardar una entidad sin datos | "La entidad central es requerida", "Debe seleccionar una categoría", "Debe agregar al menos una subdirección o deshabilitar las subdirecciones" | Faltan datos obligatorios de la entidad. | Escriba el nombre, elija la categoría y agregue subdirecciones o desactive la opción. | — |
| Crear o renombrar una entidad con un nombre existente | "El nombre de la entidad ya existe" | Los nombres de entidad son únicos. | Busque la entidad existente con "Buscar por nombre" y úsela. | Busque antes de crear (la pantalla lo recomienda: "verifica primero que no exista ya en la base de datos para evitar duplicados"). |
| Crear una subdirección de una entidad inactiva o hacerla su propia central | "La Entidad Central no esta Activa" / "Una entidad no puede ser su propia entidad central" | Regla de jerarquía de entidades. | Use una entidad central activa y distinta. | — |

> 📷 **[CAPTURA MED-02-USU-21]** — Mensaje ERR-USU-10
> **Debe mostrar:** La pantalla con el mensaje "La entidad central es requerida", "Debe seleccionar una categoría", "Debe agregar al menos una subdirección o deshabilitar las subdirecciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/EntityModal.tsx:196-208`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Guardar una entidad sin datos

> 📷 **[CAPTURA MED-02-USU-22]** — Mensaje ERR-USU-11
> **Debe mostrar:** La pantalla con el mensaje "El nombre de la entidad ya existe"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioEntidades.cs:64,153`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Crear o renombrar una entidad con un nombre existente

> 📷 **[CAPTURA MED-02-USU-23]** — Mensaje ERR-USU-12
> **Debe mostrar:** La pantalla con el mensaje "La Entidad Central no esta Activa" / "Una entidad no puede ser su propia entidad central"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioEntidades.cs:44-49,173-184`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Crear una subdirección de una entidad inactiva o hacerla su propia central

**⚠️ Atención:**
- Las entidades no se inactivan desde la pantalla: la plataforma no tiene esa opción.

#### Actividad 9 — Editar una entidad y sus subdirecciones

**Objetivo de la actividad:** Que el Administrador pueda corregir el nombre o la categoría de una entidad y agregar o quitar subdirecciones.

**Cuándo se hace y requisitos previos:** Secuencia E0.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El nombre de la entidad es único; la entidad central de una subdirección debe estar activa y no puede ser la misma entidad. | Revise el estado o el dato en la pantalla antes de actuar | Buscar la entidad antes de crearla (Super Administrador o Administrador) | RN-USU-09 |
| Para guardar una entidad se requieren nombre y categoría; si se habilitan subdirecciones, al menos una, y no se quita una subdirección en uso. | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario (Super Administrador o Administrador) | RN-USU-11 |

**Dónde:** Entidades › fila › ícono **Editar** (o **Detalle** › **Editar**) › ventana "Editar entidad territorial".

**Qué ve:** La ventana "Editar entidad territorial" con el aviso "Ten cuidado al cambiar los nombres. Esta modificación actualizará la información en la plataforma.", el contador "{N} Subdirecciones" y el botón **Guardar cambios**.

**Campos a diligenciar — Agregar / Editar entidad territorial:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Entidad Central (`name`) | Sí | Texto | Nombre único | — | — | Gobernación de Prueba | "La entidad central es requerida" / "El nombre de la entidad ya existe" |
| 2 | Categoría (`categories`) | Sí | Lista con búsqueda | Una categoría del catálogo | 89 categorías (Alcaldía, Gobernación, Ministerio, Policía, Ejército, Defensoría…); ver 05_catalogos.md | — | Gobernación | "Debe seleccionar una categoría" |
| 3 | Sub Direcciones (interruptor) (`subdirectionsEnabled`) | No | Interruptor | Si está activo, al menos una subdirección | Activo / Inactivo | — | Activo | "Debe agregar al menos una subdirección o deshabilitar las subdirecciones" / "Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones." |
| 4 | Subdirección (cada fila) · **Agregar subdirección** (`subdirecciones[].name`) | Condicional: si el interruptor está activo | Texto repetible | Una fila por subdirección | — | Sub Direcciones | Secretaría de Gobierno de Prueba | "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas." |

- Campos que llena el sistema: Estado Activa y fecha de creación.
- Campos que se bloquean: No se puede quitar una subdirección con usuarios o alertas, ni desactivar las subdirecciones mientras existan.
- Archivos: No aplica.
- Guardar o enviar con: **Agregar entidad** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 9.1 — Abrir la edición
**Objetivo del paso:** Cargar los datos de la entidad.
**Qué hacer:** Haga clic en el ícono **Editar** de la fila (o en **Detalle** › **Editar**).
**Resultado esperado:** Se abre "Editar entidad territorial".

##### Paso 9.2 — Cambiar nombre o categoría
**Objetivo del paso:** Corregir los datos.
**Qué hacer:** Modifique **Entidad Central** o **Categoría**.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 9.3 — Agregar o quitar subdirecciones
**Objetivo del paso:** Actualizar las dependencias.
**Qué hacer:** Use **Agregar subdirección** o quite una fila; use "Buscar" y **Mostrar 10 más** si son muchas.
**Resultado esperado:** Si la subdirección tiene usuarios o alertas: "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas."

##### Paso 9.4 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Entidad actualizada con éxito — Los cambios han sido guardados correctamente."

> 📷 **[CAPTURA MED-02-USU-24]** — Editar entidad
> **Debe mostrar:** La ventana con el aviso "Ten cuidado al cambiar los nombres"
> **Resaltar:** Aviso; Guardar cambios
> **Pantalla / ruta:** `dashboard/src/components/ui/EntityModal.tsx:378-381`
> **Tomarla con:** Administrador · **Datos:** Entidad Mock
> **Imagen existente:** Refenrence/resources/img_home.png: la ventana "Editar entidad territorial" con el aviso "Ten cuidado al cambiar los nombres" aparece superpuesta en la maqueta (tomada con Super Administrador; la ventana es la misma para el Administrador). Debe actualizarse: es parte de una maqueta de diseño
> **Texto alternativo:** Edición de una entidad

**Resultado de la actividad:** La entidad queda actualizada en toda la plataforma.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Crear o renombrar una entidad con un nombre existente | "El nombre de la entidad ya existe" | Los nombres de entidad son únicos. | Busque la entidad existente con "Buscar por nombre" y úsela. | Busque antes de crear (la pantalla lo recomienda: "verifica primero que no exista ya en la base de datos para evitar duplicados"). |
| Crear una subdirección de una entidad inactiva o hacerla su propia central | "La Entidad Central no esta Activa" / "Una entidad no puede ser su propia entidad central" | Regla de jerarquía de entidades. | Use una entidad central activa y distinta. | — |
| Quitar una subdirección con usuarios o alertas | "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas." | La subdirección está en uso. | Reasigne los usuarios antes de quitarla. | — |
| Desactivar las subdirecciones de una entidad que ya tiene | "Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones." | La entidad tiene subdirecciones creadas. | Elimine primero las subdirecciones (si no están en uso). | — |

> 📷 **[CAPTURA MED-02-USU-25]** — Mensaje ERR-USU-14
> **Debe mostrar:** La pantalla con el mensaje "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/EntityModal.tsx:389-392`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Quitar una subdirección con usuarios o alertas

> 📷 **[CAPTURA MED-02-USU-26]** — Mensaje ERR-USU-15
> **Debe mostrar:** La pantalla con el mensaje "Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/EntityModal.tsx:487`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Desactivar las subdirecciones de una entidad que ya tiene

**⚠️ Atención:**
- ⚠️ El cambio de nombre se refleja en todas las recomendaciones y usuarios de la entidad.

#### Actividad 10 — Eliminar una entidad

**Objetivo de la actividad:** Que el Administrador pueda eliminar una entidad creada por error que no tiene información relacionada.

**Cuándo se hace y requisitos previos:** Secuencia E0.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para eliminar una entidad, no debe tener usuarios, subdirecciones, alertas ni recomendaciones asociadas. | Las columnas Subdirecciones y Usuarios están en 0 | Retirar o reasignar primero lo relacionado (Super Administrador o Administrador) | RN-USU-10 |

**Dónde:** Entidades › vista Centrales › fila › ícono **Eliminar** › ventana "Eliminar entidad central".

**Qué ve:** La confirmación "Eliminar entidad central — ¿Estás seguro de que deseas eliminar la entidad "{nombre}"? Esta acción no se puede deshacer."

**Pasos:**

##### Paso 10.1 — Verificar que no esté en uso
**Objetivo del paso:** Evitar el error de eliminación.
**Qué hacer:** Revise que las columnas **Subdirecciones** y **Usuarios** estén en 0 y que la entidad no tenga recomendaciones.
**Resultado esperado:** Confirma que se puede eliminar.

##### Paso 10.2 — Eliminar
**Objetivo del paso:** Retirar la entidad.
**Qué hacer:** Haga clic en el ícono **Eliminar** de la fila y confirme.
**Resultado esperado:** Aparece "Entidad eliminada con éxito — La entidad ha sido eliminada correctamente."

> 📷 **[CAPTURA MED-02-USU-27]** — Error al eliminar entidad
> **Debe mostrar:** El mensaje "No es posible eliminar la entidad"
> **Resaltar:** Texto del mensaje
> **Pantalla / ruta:** `dashboard/src/pages/UsuariosYEntidades.tsx:677-695`
> **Tomarla con:** Administrador · **Datos:** Entidad Mock con usuarios
> **Texto alternativo:** Mensaje que impide eliminar una entidad en uso

**Resultado de la actividad:** La entidad deja de aparecer (borrado lógico).

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Eliminar una entidad con información relacionada | "No es posible eliminar la entidad — Tiene usuarios asociados o subdirecciones o está relacionada con alertas tempranas." / "La entidad tiene recomendaciones asociadas y no puede ser eliminada." | La entidad tiene usuarios, subdirecciones, alertas o recomendaciones. | Reasigne o retire primero lo relacionado; si la entidad sigue en uso, no la elimine. | Elimine solo entidades creadas por error y sin uso. |

> 📷 **[CAPTURA MED-02-USU-28]** — Mensaje ERR-USU-13
> **Debe mostrar:** La pantalla con el mensaje "No es posible eliminar la entidad — Tiene usuarios asociados o subdirecciones o está relacionada con alertas tempranas." / "La entidad tiene recomendaciones as
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioEntidades.cs:247-264`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Eliminar una entidad con información relacionada

**⚠️ Atención:**
- ⚠️ Irreversible.

### Módulo 04 — Alertas tempranas

**Prerrequisitos:** Módulos 01 y 02; para registrar alertas no se requiere ningún otro módulo, pero las recomendaciones exigen entidades creadas (Módulo 03).

**Definición del módulo:** Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. Permite listar, buscar, filtrar y descargar las alertas; ver su detalle, su PDF y su historial de actividades; reportar una alerta nueva en un formulario de 6 pasos; editarla, publicarla si está en borrador, subsumir otras alertas, eliminarla y cerrar alertas.

**Objetivo del módulo:** Que el Administrador pueda consultar, buscar y filtrar alertas tempranas; ver el detalle de una alerta y descargar su PDF; consultar el historial de actividades de una alerta; descargar el listado de alertas en CSV; revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA; ir a las recomendaciones de una alerta; reportar una alerta temprana; editar una alerta; publicar una alerta en Borrador; subsumir alertas.

**Contexto del módulo:** Inicia el ciclo (E1) y lo termina (E6.3 cierre). Recibe alertas por X-Road o del Agente IA, o las registra el Ministerio. Entrega la alerta a *Recomendaciones* (E2), cuya existencia habilita el plan de acción, y a *Inicio* para los indicadores. Todos los roles consultan las alertas de su alcance; el registro y la edición son del Super Administrador y el Administrador; la eliminación, el cierre y la carga de archivos, solo del Super Administrador. Para el Administrador: ve todas las alertas del país, sin filtro. En total, tiene 11 de las 16 funcionalidades del módulo; no tiene: adjuntar el PDF de la alerta y el Adjunto, cambiar el número de una alerta manual, eliminar una alerta, reemplazar o eliminar los archivos de la alerta, cerrar alertas.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar alertas (F-ALE-01) | Muestra las tarjetas Total de alertas, Alertas activas y Alertas cerradas y la tabla de alertas, con las pestañas Todas, Inminencia y Estructurales. | R | Módulo 04 — Actividad 1 |
| Buscar alertas (F-ALE-02) | Busca por número o texto de la alerta. | R | Módulo 04 — Actividad 1 |
| Filtrar alertas (F-ALE-03) | Filtra por Tipo, Estado, Etiqueta, Economías Ilegales, Grupos Armados, Conductas Vulneratorias y Población Afectada. | R | Módulo 04 — Actividad 1 |
| Ver el detalle de una alerta (F-ALE-04) | Abre la ficha de la alerta: Información general (con Ejecutado / Programado y Plan de acción), Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas. | R | Módulo 04 — Actividad 2 |
| Descargar el PDF de la alerta (F-ALE-05) | Descarga el "PDF de la alerta" desde el detalle. | Archivo | Módulo 04 — Actividad 2 |
| Consultar el historial de actividades de la alerta (F-ALE-06) | Muestra la línea de tiempo de acciones sobre la alerta: creación, edición, publicación, recomendaciones, actividades, aprobaciones, confirmación, informes, cierre. | R | Módulo 04 — Actividad 3 |
| Descargar el listado de alertas (CSV) (F-ALE-07) | Descarga en CSV las alertas visibles con los filtros aplicados. | Archivo | Módulo 04 — Actividad 4 |
| Reportar una alerta temprana (F-ALE-08) | Registra manualmente una alerta en 6 pasos (Información general, Lugar de advertencia, Conflicto, Conductas vulneratorias, Población afectada, Subsunción) y la deja Activa. | C | Módulo 04 — Actividad 7 |
| Editar una alerta (F-ALE-10) | Modifica los datos de la alerta en el mismo formulario de 6 pasos. | U | Módulo 04 — Actividad 8 |
| Publicar una alerta en borrador (F-ALE-12) | Al guardar la edición con "Publicar alerta al guardar" activo, la alerta pasa de Borrador a Activa. | Estado | Módulo 04 — Actividad 9 |
| Subsumir otras alertas (F-ALE-13) | Marca alertas existentes como subsumidas por la alerta que se registra o edita; las subsumidas pasan a Cerrada. | Estado | Módulo 04 — Actividad 7; Módulo 04 — Actividad 10 |
| Recibir alertas tempranas por X-Road (F-INT-01, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía la alerta con sus municipios y recomendaciones; el sistema crea la alerta y las recomendaciones automáticas y notifica a las entidades. | Automática | Módulo 04 — Actividad 1 |
| Listar las recomendaciones de una alerta (F-REC-01, módulo Recomendaciones) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 04 — Actividad 6 |

#### Actividad 1 — Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el Administrador pueda encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Qué ve:** "Alertas Tempranas — Gestiona y monitorea la comunicación de las alertas tempranas." con las tarjetas **Total de alertas**, **Alertas activas** y **Alertas cerradas**; la sección "Alertas" con el contador y los botones **Descargar**, **Cerrar alertas** y **Reportar alerta**; las pestañas **Todas**, **Inminencia** y **Estructurales**; el buscador "Buscar por nombre" y **Filtros**. Ve todas las alertas del país, sin filtro de entidad ni de departamento, incluidas las alertas en Borrador de ese alcance.

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
**Resultado esperado:** Aparecen Detalle, Editar, Recomendaciones, Historial de actividades y Eliminar (Eliminar deshabilitado: "No tienes permisos para eliminar alertas").

> 📷 **[CAPTURA MED-02-ALE-01]** — Listado de alertas
> **Debe mostrar:** La pantalla Alertas Tempranas de un usuario Administrador con las tarjetas, las pestañas y la tabla
> **Resaltar:** Pestañas Todas/Inminencia/Estructurales; Buscar por nombre; Filtros; menú ⋯
> **Pantalla / ruta:** `/alertas-tempranas` (`dashboard/src/components/alertas-tempranas/AlertasTab.tsx`)
> **Tomarla con:** Administrador · **Datos:** AT-013-2025 o alertas Mock
> **Texto alternativo:** Listado de alertas tempranas con filtros

**Resultado de la actividad:** Ubica la alerta y sus datos principales.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El listado de alertas no carga | "Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |
| Una alerta emitida por la Defensoría no aparece en SI-CIPRAT | No aparece mensaje en la plataforma. | La alerta aún no llega por X-Road o el mensaje fue rechazado por el servidor. | Informe a la Secretaría Técnica; el Super Administrador o el Administrador pueden registrarla con **Reportar alerta** si se confirma que no llegará. | — |

> 📷 **[CAPTURA MED-02-ALE-02]** — Mensaje ERR-ALE-19
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:212-215`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El listado de alertas no carga

**⚠️ Atención:**
- La lista también muestra alertas en estado Borrador (creadas por el Agente IA o por X-Road) de su alcance: todavía no son alertas activas.

**Ejemplo:** Busque "AT-013" y verá la alerta AT-013-2025 [DATO REAL AT-013-25], tipo Estructural, etiqueta Regional según la línea base (los scripts del repositorio la cargan como "Nacional": verifique cuál muestra su ambiente), notificada el 07/10/2025.

#### Actividad 2 — Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

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

> 📷 **[CAPTURA MED-02-ALE-03]** — Detalle de la alerta
> **Debe mostrar:** La ficha de una alerta en la pestaña Lugar de advertencia
> **Resaltar:** Pestañas; columnas CAT, PNIS, PDET y Zona Fut.; "PDF de la alerta"
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx`
> **Tomarla con:** Administrador · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Ficha de detalle de una alerta temprana

**Resultado de la actividad:** Conoce la alerta completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**⚠️ Atención:**
- El botón **Editar** del detalle abre la edición (ver la actividad "Editar una alerta").

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25], la pestaña Lugar de advertencia lista 1.122 municipios, por ejemplo GUAVIARE › Miraflores (95200).

#### Actividad 3 — Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el Administrador pueda saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

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

> 📷 **[CAPTURA MED-02-ALE-04]** — Historial de actividades
> **Debe mostrar:** La línea de tiempo con la confirmación del plan
> **Resaltar:** Evento de confirmación con usuario y fecha
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/ActivityHistoryModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock con varias acciones
> **Texto alternativo:** Historial de actividades de una alerta

**Resultado de la actividad:** Conoce la trazabilidad de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El servidor falla al procesar la solicitud | "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio — La plataforma presentó un inconveniente al procesar tu solicitud. Estamos trabajando para solucionarlo. Por favor, intenta nuevamente en unos minutos." | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | — |

> 📷 **[CAPTURA MED-02-ALE-05]** — Mensaje ERR-GEN-04
> **Debe mostrar:** La pantalla con el mensaje "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio — La plataforma presentó un inconveniente al procesar tu solicitud. Estamos 
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/services/apiClient.ts:77-78`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor falla al procesar la solicitud

**⚠️ Atención:**
- El historial guarda eventos, no versiones completas: no permite ver cómo estaba una actividad antes de editarla.

#### Actividad 4 — Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el Administrador pueda descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

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

> 📷 **[CAPTURA MED-02-ALE-06]** — Botón Descargar
> **Debe mostrar:** La cabecera de la tabla con el botón Descargar
> **Resaltar:** Botón Descargar
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:165-221`
> **Tomarla con:** Administrador · **Datos:** Alertas Mock
> **Texto alternativo:** Botón para descargar el listado de alertas

**Resultado de la actividad:** Tiene el listado en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

> 📷 **[CAPTURA MED-02-ALE-07]** — Mensaje ERR-GEN-10
> **Debe mostrar:** La pantalla con el mensaje "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:87-88`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: La descarga del CSV falla

**⚠️ Atención:**
- Los textos salen completos (el sistema no los corta a 4.000 caracteres).
- Las fechas salen en formato AAAA-MM-DD.

#### Actividad 5 — Revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA

**Objetivo de la actividad:** Que el Administrador pueda identificar las alertas automáticas en Borrador y revisarlas contra el documento antes de publicarlas.

**Cuándo se hace y requisitos previos:** Secuencia E1.1 / E1.2.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La alerta que crea el agente queda en Borrador: no cuenta en los indicadores ni se trabaja hasta que se revisa y se publica. | Revise el estado o el dato en la pantalla antes de actuar | Revisar el borrador y publicarlo con **Publicar alerta al guardar** (Super Administrador o Administrador) | RN-AGE-02 |

**Dónde:** Alertas tempranas › **Filtros** › Estado "Borrador" › fila › ⋯ › **Detalle**.

**Qué ve:** Las alertas con Estado "Borrador" y Creación "Automática". En el detalle aparece la etiqueta "Borrador".

**Pasos:**

##### Paso 5.1 — Filtrar los borradores
**Objetivo del paso:** Encontrar lo pendiente de revisión.
**Qué hacer:** Abra **Filtros**, marque Estado "Borrador" y haga clic en **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo los borradores.

##### Paso 5.2 — Comparar con el documento
**Objetivo del paso:** Detectar errores de lectura automática.
**Qué hacer:** Abra el **Detalle** y compare número, fechas, tipo, etiqueta, municipios, grupos armados, conductas y población con el documento de la Defensoría.
**Resultado esperado:** Identifica lo que debe corregir.

##### Paso 5.3 — Pasar a la edición
**Objetivo del paso:** Corregir y publicar.
**Qué hacer:** Use ⋯ › **Editar** (actividad "Editar una alerta" y "Publicar una alerta en Borrador").
**Resultado esperado:** Se abre el formulario con los datos del borrador.

> 📷 **[CAPTURA MED-02-ALE-08]** — Alertas en Borrador
> **Debe mostrar:** La tabla filtrada por Estado Borrador
> **Resaltar:** Columna Estado "Borrador" y Creación "Automática"
> **Pantalla / ruta:** `/alertas-tempranas`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock en Borrador
> **Texto alternativo:** Listado de alertas en borrador

**Resultado de la actividad:** El borrador queda revisado y listo para corregir y publicar.

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:603-614`. La alerta se emite en el sistema de la Defensoría (SISAT) y llega por X-Road; en SI-CIPRAT vuelve como alerta en *Alertas tempranas*.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Una alerta emitida por la Defensoría no aparece en SI-CIPRAT | No aparece mensaje en la plataforma. | La alerta aún no llega por X-Road o el mensaje fue rechazado por el servidor. | Informe a la Secretaría Técnica; el Super Administrador o el Administrador pueden registrarla con **Reportar alerta** si se confirma que no llegará. | — |

**⚠️ Atención:**
- En una alerta automática el número no se puede editar ("No es posible editar el número de una alerta automática").

#### Actividad 6 — Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el Administrador pueda pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Qué ve:** La pantalla de recomendaciones de la alerta con el enlace "Volver a Alertas Tempranas".

**Pasos:**

##### Paso 6.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 6.2 — Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

> 📷 **[CAPTURA MED-02-ALE-09]** — Menú ⋯ de la alerta
> **Debe mostrar:** El menú de acciones de una fila con la opción Recomendaciones
> **Resaltar:** Opción Recomendaciones
> **Pantalla / ruta:** `dashboard/src/components/alertas-tempranas/AlertasTab.tsx:469-507`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock
> **Texto alternativo:** Menú de acciones de una alerta

**Resultado de la actividad:** Llega a las recomendaciones de la alerta.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | — |

> 📷 **[CAPTURA MED-02-ALE-10]** — Mensaje ERR-REC-08
> **Debe mostrar:** La pantalla con el mensaje "La alerta solicitada no existe o ha sido eliminada."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:168`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir las recomendaciones de una alerta eliminada

#### Actividad 7 — Reportar una alerta temprana

**Objetivo de la actividad:** Que el Administrador pueda registrar manualmente una alerta temprana completa (6 pasos) para que quede Activa y se le puedan cargar las recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E1.3.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El número de alerta es obligatorio, debe tener el formato AT-XXX-XXXX (por ejemplo AT-013-2025) y no puede existir otra alerta con ese número. | Busque el número en Alertas tempranas | Escribir el año con 4 dígitos y buscar antes si la alerta ya existe (Super Administrador o Administrador) | RN-ALE-01 |
| Para reportar una alerta se requieren fecha de la alerta, fecha de notificación, tipo y etiqueta. | Revise el estado o el dato en la pantalla antes de actuar | Completar el Paso 1 (Super Administrador o Administrador) | RN-ALE-02 |
| La alerta debe tener al menos una ubicación (departamento y municipio con código DANE de 5 dígitos). | Revise el estado o el dato en la pantalla antes de actuar | Agregar los municipios del documento (Super Administrador o Administrador) | RN-ALE-03 |
| La alerta debe tener al menos un grupo armado ilegal, una conducta vulneratoria y una población afectada. | Revise el estado o el dato en la pantalla antes de actuar | Seleccionar al menos una opción en los Pasos 3, 4 y 5 (Super Administrador o Administrador) | RN-ALE-04 |
| Los archivos de la alerta deben ser PDF de hasta 20 MB y solo el Super Administrador puede subirlos o eliminarlos. | En el detalle aparece "PDF de la alerta" | Pedir al Super Administrador que adjunte el PDF (Super Administrador) | RN-ALE-05 |
| Solo se pueden subsumir alertas existentes, activas y que no hayan sido subsumidas antes; al guardar quedan Cerradas. | Revise el estado o el dato en la pantalla antes de actuar | Elegir solo alertas activas (Super Administrador o Administrador) | RN-ALE-09 |
| La fecha de notificación es el día 0 del ciclo de informes; el sistema no verifica que sea posterior a la fecha de la alerta. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la fecha contra el documento (Super Administrador o Administrador) | RN-ALE-13 |

**Dónde:** Alertas tempranas › **Reportar alerta** › ventana "Reportar alerta temprana — Informa una alerta temprana y asigna las entidades involucradas para su atención y seguimiento.".

**Qué ve:** Un asistente de 6 pasos con el indicador "Paso N de 6": 1 Información general, 2 Lugar de advertencia, 3 Conflicto, 4 Conductas vulneratorias e infracciones al D.I.H., 5 Población afectada, 6 Subsunción. Botones **Cancelar**, **Atrás**, **Siguiente** y, en el último paso, **Enviar Alerta**.

**Campos a diligenciar — Reportar alerta temprana / Editar alerta temprana (6 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Número y fecha de alerta (número) (`alert_number`) | Sí | Texto | Formato `AT-XXX-XXXX` (3 y 4 caracteres alfanuméricos), máx. 50, único. La pantalla solo valida que no esté vacío | — | — | AT-013-2025 [DATO REAL AT-013-25] | "El número de alerta es requerido" / "El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)" / "El número de alerta '…' ya existe" |
| 2 | Número y fecha de alerta (fecha) (`alert_date`) | Sí | Fecha (calendario) | Fecha válida | — | — | 07/10/2025 [DATO REAL AT-013-25] | "La fecha de alerta es requerida" |
| 3 | Fecha de notificación (`notification_date`) | Sí | Fecha (calendario) | Fecha válida; es el día 0 de los informes; no se compara con la fecha de la alerta | — | — | 07/10/2025 [DATO REAL AT-013-25] | "La fecha de notificación es requerida" |
| 4 | Tipo de alerta (`type`) | Sí | Lista de selección única | — | Inminencia, Estructural | — | Estructural [DATO REAL AT-013-25] | "El tipo de alerta es requerido" |
| 5 | Etiqueta (`label`) | Sí | Lista de selección única | — | Nacional, Regional, Internacional | — | Regional [DATO REAL AT-013-25] (línea base; en los scripts del repositorio figura "Nacional") | "La etiqueta es requerida" |
| 6 | PDF de la alerta (`pdf_alerta`) | No | Archivo | PDF ≤ 20 MB; solo lo sube el Super Administrador | — | — | PDF oficial de la AT-013-25 (no se usa en esta fase) | "Tipo de archivo no permitido. Solo se aceptan: .pdf" / "El PDF de la alerta no pudo ser subido." |
| 7 | Adjunto (`adjunto`) | No | Archivo | PDF ≤ 20 MB; solo lo sube el Super Administrador | — | — | oficio_remisorio_prueba.pdf | "El adjunto no pudo ser subido." |
| 8 | Tema Clave (`description`) | No | Área de texto | Sin límite de longitud | — | — | "Se prevé que los procesos electorales podrán desarrollarse con normalidad en la mayor parte del territorio nacional. Sin embargo…" [DATO REAL AT-013-25] | — |
| 9 | Departamento (`department_name / department_dane_code`) | Sí (al menos una ubicación) | Lista con búsqueda | Departamento del catálogo | Departamentos de Colombia | Habilita y filtra Municipio | GUAVIARE [DATO REAL AT-013-25] | "Debe agregar al menos una ubicación" |
| 10 | Municipio (`municipality_dane_code`) | Sí | Lista con búsqueda (dependiente) | Código DANE de 5 dígitos; se pueden agregar varios | Municipios del departamento elegido | Departamento | Miraflores (95200) [DATO REAL AT-013-25] | "El código DANE del municipio debe tener exactamente 5 dígitos" (servidor) |
| 11 | Economías ilegales (`illegal_economies`) | No | Lista de selección múltiple con búsqueda | — | 10 opciones (Narcotráfico, Siembra, Cultivo, Procesamiento, Comercialización, Minería ilegal, Contrabando, Préstamos de usura / gota a gota, Tala ilegal, Lavado de activos) | — | Contrabando [DATO REAL AT-013-25] | — |
| 12 | Grupos armados ilegales (`armed_groups`) | Sí (al menos uno) | Lista de selección múltiple con búsqueda | Al menos una opción | 179 opciones, incluida "Sin determinar" (ver 05_catalogos.md) | — | Ejército de Liberación Nacional (ELN) [DATO REAL AT-013-25] | "Debe seleccionar al menos un grupo armado ilegal" |
| 13 | Conducta Vulneratoria (`vulnerable_behaviors`) | Sí (al menos una) | Lista de selección múltiple con búsqueda | Al menos una opción | 54 opciones, incluida "Otra" (ver 05_catalogos.md) | — | Amenazas [DATO REAL AT-013-25] | "Debe seleccionar al menos una conducta vulneratoria" |
| 14 | Población afectada (`affected_population`) | Sí (al menos una) | Lista de selección múltiple con búsqueda | Al menos una opción | 88 opciones (ver 05_catalogos.md) | — | Jóvenes [DATO REAL AT-013-25] | "Debe seleccionar al menos una población afectada" |
| 15 | Esta alerta subsume otras alertas (`subsumption_enabled`) | No | Interruptor | — | Activo / Inactivo | Habilita Alertas subsumidas | Inactivo | "No hay alertas disponibles para subsunción" |
| 16 | Alertas subsumidas (`subsumed_alert_ids`) | Condicional: si el interruptor está activo | Lista de selección múltiple con búsqueda | Alertas activas no subsumidas | Alertas disponibles para subsunción | Esta alerta subsume otras alertas | AT-900-2025 (ficticia) | "La alerta AT-… ya ha sido subsumida por otra alerta" |

- Campos que llena el sistema: Estado (Activa al crear manualmente), modo de creación (manual), consecutivos y contadores, usuario y fecha de creación; historial "created".
- Campos que se bloquean: En edición, el número no se edita en alertas automáticas y solo el Super Administrador lo edita en alertas manuales. Con la alerta cerrada, subsumida o con el plan confirmado no se puede guardar ninguna edición.
- Archivos: "PDF de la alerta" y "Adjunto": solo PDF, hasta 20 MB cada uno; se suben después de crear la alerta y solo los acepta el servidor si el usuario es Super Administrador.
- Guardar o enviar con: **Enviar Alerta** (edición: **Guardar Cambios**); navegación con **Siguiente**, **Atrás** y **Cancelar**.

**Pasos:**

##### Paso 7.1 — Buscar si la alerta ya existe
**Objetivo del paso:** Evitar duplicados con X-Road o el Agente IA.
**Qué hacer:** Busque el número en "Buscar por nombre", incluidas las alertas en Borrador.
**Resultado esperado:** Si existe, edítela en lugar de crearla.

##### Paso 7.2 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** Haga clic en **Reportar alerta** (desde un computador; en celular aparece "Disponible en escritorio").
**Resultado esperado:** Se abre "Reportar alerta temprana" en el Paso 1 de 6.

##### Paso 7.3 — Paso 1: escribir el número de la alerta
**Objetivo del paso:** Identificar la alerta con el formato que acepta el servidor.
**Qué hacer:** En **Número y fecha de alerta** escriba el número con el formato `AT-` + 3 caracteres + `-` + 4 caracteres, por ejemplo `AT-013-2025`. No use el formato del ejemplo de la pantalla ("Ej: AT-001-25").
**Resultado esperado:** El campo queda diligenciado (la pantalla no valida el formato; el servidor lo hará al enviar).

##### Paso 7.4 — Paso 1: elegir la fecha de la alerta y la fecha de notificación
**Objetivo del paso:** Registrar el día 0 del ciclo.
**Qué hacer:** Elija la fecha de la alerta en el calendario junto al número; en **Fecha de notificación** elija la fecha en que se notificó al CIPRAT. Verifique que la de notificación no sea anterior a la de la alerta.
**Resultado esperado:** Las fechas quedan registradas; la de notificación será la base del próximo informe (+6 meses).

##### Paso 7.5 — Paso 1: elegir el tipo y la etiqueta
**Objetivo del paso:** Clasificar la alerta.
**Qué hacer:** Despliegue **Tipo de alerta** (Inminencia o Estructural) y **Etiqueta** (Nacional, Regional o Internacional) y elija.
**Resultado esperado:** Los dos valores quedan seleccionados.

##### Paso 7.6 — Paso 1: adjuntar el PDF y el adjunto
**Objetivo del paso:** Dejar el soporte oficial de la alerta.
**Qué hacer:** Los campos **PDF de la alerta** y **Adjunto** aparecen, pero su rol no puede subir archivos: déjelos vacíos y pida al Super Administrador que adjunte el PDF después de crear la alerta.
**Resultado esperado:** Si los adjunta, al final aparecerá "El PDF de la alerta no pudo ser subido.".

##### Paso 7.7 — Paso 1: escribir el Tema Clave
**Objetivo del paso:** Resumir el riesgo advertido.
**Qué hacer:** En **Tema Clave** escriba la descripción del documento (opcional, sin límite).
**Resultado esperado:** El texto queda registrado.

##### Paso 7.8 — Avanzar al Paso 2
**Objetivo del paso:** Validar el Paso 1.
**Qué hacer:** Haga clic en **Siguiente**.
**Resultado esperado:** Si falta un dato obligatorio aparece su mensaje ("El número de alerta es requerido", "La etiqueta es requerida"…); si no, pasa al Paso 2 de 6.

##### Paso 7.9 — Paso 2: agregar los municipios (Lugar de advertencia)
**Objetivo del paso:** Registrar dónde aplica la alerta.
**Qué hacer:** Elija el **Departamento** ("Selecciona un departamento"), luego el **Municipio**; repita por cada municipio del documento.
**Resultado esperado:** Cada municipio aparece en la tabla con Cod DANE, CAT, PNIS, PDET y Zona Fut.; sin municipios: "No hay ubicaciones agregadas. Agrega al menos una ubicación para continuar."

##### Paso 7.10 — Paso 3: Conflicto
**Objetivo del paso:** Registrar economías ilegales y grupos armados.
**Qué hacer:** En **Economías ilegales** marque las que apliquen (opcional). En **Grupos armados ilegales** marque al menos uno (use "Sin determinar" si el documento no lo precisa). Use los buscadores. Haga clic en **Siguiente**.
**Resultado esperado:** Sin grupo armado: "Debe seleccionar al menos un grupo armado ilegal".

##### Paso 7.11 — Paso 4: Conductas vulneratorias
**Objetivo del paso:** Registrar las conductas advertidas.
**Qué hacer:** En **Conducta Vulneratoria** marque al menos una (use "Otra" si no está). Haga clic en **Siguiente**.
**Resultado esperado:** Sin selección: "Debe seleccionar al menos una conducta vulneratoria".

##### Paso 7.12 — Paso 5: Población afectada
**Objetivo del paso:** Registrar la población en riesgo.
**Qué hacer:** En **Población afectada** marque al menos una. Haga clic en **Siguiente**.
**Resultado esperado:** Sin selección: "Debe seleccionar al menos una población afectada".

##### Paso 7.13 — Paso 6: Subsunción (si aplica)
**Objetivo del paso:** Indicar si esta alerta reemplaza a otras.
**Qué hacer:** Solo si el documento lo indica, active **Esta alerta subsume otras alertas** y elija las **Alertas subsumidas**.
**Resultado esperado:** Aparece "Al confirmar, las alertas seleccionadas se subsumirán en esta alerta y cambiarán su estado a 'Cerrada'."

##### Paso 7.14 — Revisar antes de enviar
**Objetivo del paso:** Evitar errores difíciles de corregir después.
**Qué hacer:** Use **Atrás** para revisar cada paso, en especial el número (año con 4 dígitos), las fechas y los municipios.
**Resultado esperado:** Los datos coinciden con el documento.

##### Paso 7.15 — Enviar la alerta
**Objetivo del paso:** Registrar la alerta.
**Qué hacer:** Haga clic en **Enviar Alerta**.
**Resultado esperado:** Aparece "Alerta {número} reportada con éxito" y "La alerta {número} se encuentra lista para su carga junto con las recomendaciones correspondientes."; la alerta queda Activa. Si el formato del número no es válido, aparece el error del servidor.

> 🎞️ **[GIF MED-02-ALE-11]** — Reportar alerta: pasos 1 y 2
> **Debe mostrar:** El diligenciamiento del Paso 1 (número, fechas, tipo, etiqueta) y la adición de dos municipios en el Paso 2
> **Resaltar:** Número con año de 4 dígitos; Fecha de notificación; tabla de municipios
> **Pantalla / ruta:** Alertas tempranas › Reportar alerta (`dashboard/src/components/report-alert/ReportAlertModal.tsx`)
> **Tomarla con:** Administrador · **Datos:** Mock AT-901-2026
> **Solo para GIF — Secuencia:** 1) Reportar alerta 2) Número y fechas 3) Tipo y etiqueta 4) Siguiente 5) Departamento y municipio · **Duración aproximada:** 40 segundos
> **Texto alternativo:** Animación del registro de una alerta, pasos 1 y 2

> 🎞️ **[GIF MED-02-ALE-12]** — Reportar alerta: pasos 3 a 6 y envío
> **Debe mostrar:** La selección de grupo armado, conducta y población, la subsunción desactivada y el envío
> **Resaltar:** Mensajes de obligatoriedad; botón Enviar Alerta; mensaje de éxito
> **Pantalla / ruta:** Alertas tempranas › Reportar alerta
> **Tomarla con:** Administrador · **Datos:** Mock AT-901-2026
> **Solo para GIF — Secuencia:** 1) Grupo armado 2) Conducta 3) Población 4) Subsunción 5) Enviar Alerta · **Duración aproximada:** 35 segundos
> **Texto alternativo:** Animación de los pasos finales del registro de una alerta

**Resultado de la actividad:** La alerta queda Activa, con modo de creación Manual y el evento "created" en su historial. El siguiente paso es cargar sus recomendaciones (módulo Recomendaciones).

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `dashboard/src/components/report-alert/AlertFormStep1.tsx:152-156`. La alerta se emite fuera de SI-CIPRAT (documento de la Defensoría); sus datos y su PDF vuelven a la plataforma en este formulario.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Hacer clic en **Siguiente** con el Paso 1 incompleto | "El número de alerta es requerido", "La fecha de alerta es requerida", "La fecha de notificación es requerida", "El tipo de alerta es requerido", "La etiqueta es requerida" | Faltan campos obligatorios del Paso 1. | Complete Número y fecha de alerta, Fecha de notificación, Tipo de alerta y Etiqueta. | Tenga el PDF de la alerta a la mano antes de empezar. |
| Escribir el número con el año de 2 dígitos (como sugiere el ejemplo "Ej: AT-001-25") | "El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)" | El servidor exige 4 caracteres al final; la pantalla no lo valida y su ejemplo usa 2 (diferencia D1). | Vuelva al Paso 1 con **Atrás** y escriba el número con el año completo, por ejemplo `AT-013-2025`; envíe de nuevo. | Escriba siempre `AT-` + 3 caracteres + `-` + año de 4 dígitos. |
| Registrar un número de alerta que ya existe | "El número de alerta 'AT-…' ya existe" | La alerta ya fue registrada (manualmente, por X-Road o por el Agente IA). | Busque el número en *Alertas tempranas* (incluidos los borradores) y edite la existente. | Busque antes de registrar. |
| Avanzar del Paso 2 sin municipios | "Debe agregar al menos una ubicación" | La alerta necesita al menos un departamento y municipio. | Seleccione el departamento, luego el municipio, y verifique que aparezca en la tabla. | — |
| Avanzar de los Pasos 3, 4 o 5 sin selección | "Debe seleccionar al menos un grupo armado ilegal" / "Debe seleccionar al menos una conducta vulneratoria" / "Debe seleccionar al menos una población afectada" | Cada uno de esos pasos exige al menos una opción. | Seleccione al menos una opción de la lista (use "Sin determinar" u "Otro" cuando el documento no lo precise, si la lista lo ofrece). | — |
| Subsumir una alerta ya subsumida o cerrada | "La alerta AT-… ya ha sido subsumida por otra alerta" / "La alerta AT-… ya está cerrada y no puede ser subsumida" | Solo se subsumen alertas activas y no subsumidas. | Quite esa alerta de la selección del Paso 6. | — |
| Adjuntar el PDF de la alerta como Administrador | "El PDF de la alerta no pudo ser subido." / "El adjunto no pudo ser subido." (la alerta sí queda creada) | Solo el Super Administrador tiene el permiso de subir archivos (riesgo R1). | Pida al Super Administrador que edite la alerta y adjunte el PDF; verifique después que aparezca "PDF de la alerta" en el detalle. | Coordine con el Super Administrador la carga del PDF. |
| Dos personas registran alertas al mismo tiempo | Aviso "El número de alerta fue ajustado a … debido a una creación concurrente." | El sistema ajustó el número para evitar duplicados. | Verifique que el número final coincida con el documento; si no, corríjalo (Super Administrador). | — |
| Registrar una fecha de notificación anterior a la fecha de la alerta | No aparece mensaje: el sistema la acepta. | NO ENCONTRADA la validación entre las dos fechas; la fecha de notificación es el día 0 de los informes. | Verifique las fechas contra el documento antes de enviar; si ya se guardó mal, edite la alerta. | Confirme la fecha de notificación: de ella dependen los plazos de informe. |
| Activar la subsunción y no ver alertas | "No hay alertas disponibles para subsunción" | No hay otras alertas activas no subsumidas. | Desactive "Esta alerta subsume otras alertas" y continúe. | — |
| Seleccionar un archivo que no es PDF | "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF") | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Prepare los soportes en PDF antes de abrir el formulario. |
| Seleccionar un PDF muy pesado | "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB") | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Escanee en resolución media y sin color cuando sea posible. |
| Abrir un formulario de registro desde un celular | "Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio." | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Planee el registro desde un computador. |

> 📷 **[CAPTURA MED-02-ALE-13]** — Mensaje ERR-ALE-01
> **Debe mostrar:** La pantalla con el mensaje "El número de alerta es requerido", "La fecha de alerta es requerida", "La fecha de notificación es requerida", "El tipo de alerta es requerido", "La etiqueta e
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/report-alert/ReportAlertModal.tsx:171-186`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Hacer clic en **Siguiente** con el Paso 1 incompleto

> 📷 **[CAPTURA MED-02-ALE-14]** — Mensaje ERR-ALE-02
> **Debe mostrar:** La pantalla con el mensaje "El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/DTOs/AlertaDto/SolicitudCrearAlertaInterop.cs:46`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Escribir el número con el año de 2 dígitos (como sugiere el ejemplo "Ej: AT-001-25")

> 📷 **[CAPTURA MED-02-ALE-15]** — Mensaje ERR-ALE-03
> **Debe mostrar:** La pantalla con el mensaje "El número de alerta 'AT-…' ya existe"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAlertas.cs:66-75`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Registrar un número de alerta que ya existe

> 📷 **[CAPTURA MED-02-ALE-16]** — Mensaje ERR-ALE-04
> **Debe mostrar:** La pantalla con el mensaje "Debe agregar al menos una ubicación"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/report-alert/ReportAlertModal.tsx:194-197`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Avanzar del Paso 2 sin municipios

> 📷 **[CAPTURA MED-02-ALE-17]** — Mensaje ERR-ALE-05
> **Debe mostrar:** La pantalla con el mensaje "Debe seleccionar al menos un grupo armado ilegal" / "Debe seleccionar al menos una conducta vulneratoria" / "Debe seleccionar al menos una población afectada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/report-alert/ReportAlertModal.tsx:205-229`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Avanzar de los Pasos 3, 4 o 5 sin selección

> 📷 **[CAPTURA MED-02-ALE-18]** — Mensaje ERR-ALE-06
> **Debe mostrar:** La pantalla con el mensaje "La alerta AT-… ya ha sido subsumida por otra alerta" / "La alerta AT-… ya está cerrada y no puede ser subsumida"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAlertas.cs:205-225`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Subsumir una alerta ya subsumida o cerrada

> 📷 **[CAPTURA MED-02-ALE-19]** — Mensaje ERR-ALE-07
> **Debe mostrar:** La pantalla con el mensaje "El PDF de la alerta no pudo ser subido." / "El adjunto no pudo ser subido." (la alerta sí queda creada)
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:333-360`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Adjuntar el PDF de la alerta como Administrador

> 📷 **[CAPTURA MED-02-ALE-20]** — Mensaje ERR-ALE-20
> **Debe mostrar:** La pantalla con el mensaje Aviso "El número de alerta fue ajustado a … debido a una creación concurrente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:367`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Dos personas registran alertas al mismo tiempo

> 📷 **[CAPTURA MED-02-ALE-21]** — Mensaje ERR-ALE-23
> **Debe mostrar:** La pantalla con el mensaje "No hay alertas disponibles para subsunción"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/report-alert/AlertFormStep6.tsx:125`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Activar la subsunción y no ver alertas

> 📷 **[CAPTURA MED-02-ALE-22]** — Mensaje ERR-GEN-08
> **Debe mostrar:** La pantalla con el mensaje "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/ui/FileUploadField.tsx:53-64`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Seleccionar un archivo que no es PDF

> 📷 **[CAPTURA MED-02-ALE-23]** — Mensaje ERR-GEN-09
> **Debe mostrar:** La pantalla con el mensaje "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioArchivos.cs:820-827`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Seleccionar un PDF muy pesado

**⚠️ Atención:**
- ⚠️ El ejemplo de la pantalla ("Ej: AT-001-25") no pasa la validación: escriba siempre el año con 4 dígitos.
- ⚠️ La fecha de notificación es el día 0 de los informes de ejecución y el sistema no la compara con la fecha de la alerta.
- ⚠️ Su rol no puede subir el PDF: coordine con el Super Administrador para que la alerta no quede sin soporte.

**Ejemplo:** AT-013-2025 [DATO REAL AT-013-25]: Número AT-013-2025, fecha de la alerta 07/10/2025, fecha de notificación 07/10/2025, tipo Estructural, etiqueta Regional (línea base; en los scripts del repositorio figura "Nacional"), 1.122 municipios en los scripts del repositorio (la línea base dice "Todos los municipios", opción que la pantalla no ofrece). Con esa notificación, el primer próximo informe será el 07/04/2026. Mock alternativo: AT-901-2026, 15/01/2026, 20/01/2026, Inminencia, Regional, CAUCA › Popayán.

#### Actividad 8 — Editar una alerta

**Objetivo de la actividad:** Que el Administrador pueda corregir los datos de una alerta mientras no esté cerrada, subsumida ni con el plan confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E1.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para editar una alerta, no debe estar cerrada ni subsumida y su plan de acción no debe estar confirmado. | Revise el estado de la alerta y el estado del plan en el detalle | Corregir la alerta antes de que se confirme el plan (Super Administrador o Administrador) | RN-ALE-06 |
| El número de una alerta automática no se puede cambiar; el de una alerta manual solo lo cambia el Super Administrador. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el cambio al Super Administrador (Super Administrador) | RN-ALE-07 |
| El número de alerta es obligatorio, debe tener el formato AT-XXX-XXXX (por ejemplo AT-013-2025) y no puede existir otra alerta con ese número. | Busque el número en Alertas tempranas | Escribir el año con 4 dígitos y buscar antes si la alerta ya existe (Super Administrador o Administrador) | RN-ALE-01 |
| Para reportar una alerta se requieren fecha de la alerta, fecha de notificación, tipo y etiqueta. | Revise el estado o el dato en la pantalla antes de actuar | Completar el Paso 1 (Super Administrador o Administrador) | RN-ALE-02 |
| La alerta debe tener al menos una ubicación (departamento y municipio con código DANE de 5 dígitos). | Revise el estado o el dato en la pantalla antes de actuar | Agregar los municipios del documento (Super Administrador o Administrador) | RN-ALE-03 |
| La alerta debe tener al menos un grupo armado ilegal, una conducta vulneratoria y una población afectada. | Revise el estado o el dato en la pantalla antes de actuar | Seleccionar al menos una opción en los Pasos 3, 4 y 5 (Super Administrador o Administrador) | RN-ALE-04 |

**Dónde:** Alertas tempranas › ⋯ › **Editar** (o **Detalle** › **Editar**) › "Editar alerta temprana — Actualiza la información de la alerta temprana.".

**Qué ve:** El mismo asistente de 6 pasos con los datos actuales y el botón final **Guardar Cambios**.

**Campos a diligenciar — Reportar alerta temprana / Editar alerta temprana (6 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Número y fecha de alerta (número) (`alert_number`) | Sí | Texto | Formato `AT-XXX-XXXX` (3 y 4 caracteres alfanuméricos), máx. 50, único. La pantalla solo valida que no esté vacío | — | — | AT-013-2025 [DATO REAL AT-013-25] | "El número de alerta es requerido" / "El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)" / "El número de alerta '…' ya existe" |
| 2 | Número y fecha de alerta (fecha) (`alert_date`) | Sí | Fecha (calendario) | Fecha válida | — | — | 07/10/2025 [DATO REAL AT-013-25] | "La fecha de alerta es requerida" |
| 3 | Fecha de notificación (`notification_date`) | Sí | Fecha (calendario) | Fecha válida; es el día 0 de los informes; no se compara con la fecha de la alerta | — | — | 07/10/2025 [DATO REAL AT-013-25] | "La fecha de notificación es requerida" |
| 4 | Tipo de alerta (`type`) | Sí | Lista de selección única | — | Inminencia, Estructural | — | Estructural [DATO REAL AT-013-25] | "El tipo de alerta es requerido" |
| 5 | Etiqueta (`label`) | Sí | Lista de selección única | — | Nacional, Regional, Internacional | — | Regional [DATO REAL AT-013-25] (línea base; en los scripts del repositorio figura "Nacional") | "La etiqueta es requerida" |
| 6 | PDF de la alerta (`pdf_alerta`) | No | Archivo | PDF ≤ 20 MB; solo lo sube el Super Administrador | — | — | PDF oficial de la AT-013-25 (no se usa en esta fase) | "Tipo de archivo no permitido. Solo se aceptan: .pdf" / "El PDF de la alerta no pudo ser subido." |
| 7 | Adjunto (`adjunto`) | No | Archivo | PDF ≤ 20 MB; solo lo sube el Super Administrador | — | — | oficio_remisorio_prueba.pdf | "El adjunto no pudo ser subido." |
| 8 | Tema Clave (`description`) | No | Área de texto | Sin límite de longitud | — | — | "Se prevé que los procesos electorales podrán desarrollarse con normalidad en la mayor parte del territorio nacional. Sin embargo…" [DATO REAL AT-013-25] | — |
| 9 | Departamento (`department_name / department_dane_code`) | Sí (al menos una ubicación) | Lista con búsqueda | Departamento del catálogo | Departamentos de Colombia | Habilita y filtra Municipio | GUAVIARE [DATO REAL AT-013-25] | "Debe agregar al menos una ubicación" |
| 10 | Municipio (`municipality_dane_code`) | Sí | Lista con búsqueda (dependiente) | Código DANE de 5 dígitos; se pueden agregar varios | Municipios del departamento elegido | Departamento | Miraflores (95200) [DATO REAL AT-013-25] | "El código DANE del municipio debe tener exactamente 5 dígitos" (servidor) |
| 11 | Economías ilegales (`illegal_economies`) | No | Lista de selección múltiple con búsqueda | — | 10 opciones (Narcotráfico, Siembra, Cultivo, Procesamiento, Comercialización, Minería ilegal, Contrabando, Préstamos de usura / gota a gota, Tala ilegal, Lavado de activos) | — | Contrabando [DATO REAL AT-013-25] | — |
| 12 | Grupos armados ilegales (`armed_groups`) | Sí (al menos uno) | Lista de selección múltiple con búsqueda | Al menos una opción | 179 opciones, incluida "Sin determinar" (ver 05_catalogos.md) | — | Ejército de Liberación Nacional (ELN) [DATO REAL AT-013-25] | "Debe seleccionar al menos un grupo armado ilegal" |
| 13 | Conducta Vulneratoria (`vulnerable_behaviors`) | Sí (al menos una) | Lista de selección múltiple con búsqueda | Al menos una opción | 54 opciones, incluida "Otra" (ver 05_catalogos.md) | — | Amenazas [DATO REAL AT-013-25] | "Debe seleccionar al menos una conducta vulneratoria" |
| 14 | Población afectada (`affected_population`) | Sí (al menos una) | Lista de selección múltiple con búsqueda | Al menos una opción | 88 opciones (ver 05_catalogos.md) | — | Jóvenes [DATO REAL AT-013-25] | "Debe seleccionar al menos una población afectada" |
| 15 | Esta alerta subsume otras alertas (`subsumption_enabled`) | No | Interruptor | — | Activo / Inactivo | Habilita Alertas subsumidas | Inactivo | "No hay alertas disponibles para subsunción" |
| 16 | Alertas subsumidas (`subsumed_alert_ids`) | Condicional: si el interruptor está activo | Lista de selección múltiple con búsqueda | Alertas activas no subsumidas | Alertas disponibles para subsunción | Esta alerta subsume otras alertas | AT-900-2025 (ficticia) | "La alerta AT-… ya ha sido subsumida por otra alerta" |
| 17 | Publicar alerta al guardar (`(publicar)`) | Condicional: solo aparece al editar una alerta en Borrador | Interruptor | — | Activo / Inactivo | Estado de la alerta = Borrador | Activo | "La alerta no pudo ser publicada." |

- Campos que llena el sistema: Estado (Activa al crear manualmente), modo de creación (manual), consecutivos y contadores, usuario y fecha de creación; historial "created".
- Campos que se bloquean: En edición, el número no se edita en alertas automáticas y solo el Super Administrador lo edita en alertas manuales. Con la alerta cerrada, subsumida o con el plan confirmado no se puede guardar ninguna edición.
- Archivos: "PDF de la alerta" y "Adjunto": solo PDF, hasta 20 MB cada uno; se suben después de crear la alerta y solo los acepta el servidor si el usuario es Super Administrador.
- Guardar o enviar con: **Enviar Alerta** (edición: **Guardar Cambios**); navegación con **Siguiente**, **Atrás** y **Cancelar**.

**Pasos:**

##### Paso 8.1 — Abrir la edición
**Objetivo del paso:** Cargar la alerta.
**Qué hacer:** Haga clic en ⋯ › **Editar**.
**Resultado esperado:** Se abre el asistente con los datos; si la alerta está cerrada aparece "Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada."

##### Paso 8.2 — Corregir el Paso 1
**Objetivo del paso:** Ajustar número, fechas, tipo, etiqueta, archivos o tema.
**Qué hacer:** Modifique los campos necesarios. El número aparece bloqueado ("No tienes permisos para editar el número de alerta").
**Resultado esperado:** Los campos muestran los nuevos valores.

##### Paso 8.3 — Corregir los Pasos 2 a 5
**Objetivo del paso:** Ajustar municipios, conflicto, conductas y población.
**Qué hacer:** Avance con **Siguiente** y agregue o quite municipios y opciones.
**Resultado esperado:** Se mantienen al menos una ubicación, un grupo armado, una conducta y una población.

##### Paso 8.4 — Revisar el Paso 6
**Objetivo del paso:** Confirmar subsunción y publicación.
**Qué hacer:** Revise **Esta alerta subsume otras alertas** y, si la alerta es un borrador, **Publicar alerta al guardar**.
**Resultado esperado:** Las opciones quedan como corresponde.

##### Paso 8.5 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Alerta actualizada con éxito — Los cambios han sido guardados correctamente."

> 📷 **[CAPTURA MED-02-ALE-24]** — Número bloqueado en la edición
> **Debe mostrar:** El Paso 1 de la edición con el número deshabilitado y su mensaje
> **Resaltar:** Tooltip del número
> **Pantalla / ruta:** `dashboard/src/components/report-alert/AlertFormStep1.tsx:104-121`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock automática
> **Texto alternativo:** Campo de número de alerta bloqueado en la edición

**Resultado de la actividad:** La alerta queda actualizada y el cambio aparece en su historial ("updated").

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Editar una alerta cerrada | "Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada." (servidor: "No se puede editar una alerta cerrada") | Las alertas cerradas no se modifican. | No requiere acción; si el cierre fue un error, escálelo. | — |
| Editar una alerta con el plan de acción confirmado | "No se puede editar la alerta porque su plan de acción ya fue confirmado" | Con el plan confirmado la alerta queda bloqueada. | Si el cambio es necesario, coordine con la Secretaría Técnica; la plataforma no ofrece reabrir el plan. | Revise los datos de la alerta antes de que se confirme el plan. |
| Editar una alerta subsumida | "No se puede editar la alerta AT-… porque ha sido subsumida por otra alerta" | La alerta fue reemplazada por otra. | Edite la alerta que la subsumió. | — |
| Intentar cambiar el número de la alerta en la edición | Campo deshabilitado con "No es posible editar el número de una alerta automática" o "No tienes permisos para editar el número de alerta" | El número de las alertas automáticas no se cambia; el de las manuales solo lo cambia el Super Administrador. | Si el número está mal en una alerta manual, pida el cambio al Super Administrador. | — |
| Hacer clic en **Siguiente** con el Paso 1 incompleto | "El número de alerta es requerido", "La fecha de alerta es requerida", "La fecha de notificación es requerida", "El tipo de alerta es requerido", "La etiqueta es requerida" | Faltan campos obligatorios del Paso 1. | Complete Número y fecha de alerta, Fecha de notificación, Tipo de alerta y Etiqueta. | Tenga el PDF de la alerta a la mano antes de empezar. |
| Escribir el número con el año de 2 dígitos (como sugiere el ejemplo "Ej: AT-001-25") | "El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)" | El servidor exige 4 caracteres al final; la pantalla no lo valida y su ejemplo usa 2 (diferencia D1). | Vuelva al Paso 1 con **Atrás** y escriba el número con el año completo, por ejemplo `AT-013-2025`; envíe de nuevo. | Escriba siempre `AT-` + 3 caracteres + `-` + año de 4 dígitos. |
| Registrar un número de alerta que ya existe | "El número de alerta 'AT-…' ya existe" | La alerta ya fue registrada (manualmente, por X-Road o por el Agente IA). | Busque el número en *Alertas tempranas* (incluidos los borradores) y edite la existente. | Busque antes de registrar. |
| Avanzar del Paso 2 sin municipios | "Debe agregar al menos una ubicación" | La alerta necesita al menos un departamento y municipio. | Seleccione el departamento, luego el municipio, y verifique que aparezca en la tabla. | — |
| Avanzar de los Pasos 3, 4 o 5 sin selección | "Debe seleccionar al menos un grupo armado ilegal" / "Debe seleccionar al menos una conducta vulneratoria" / "Debe seleccionar al menos una población afectada" | Cada uno de esos pasos exige al menos una opción. | Seleccione al menos una opción de la lista (use "Sin determinar" u "Otro" cuando el documento no lo precise, si la lista lo ofrece). | — |

> 📷 **[CAPTURA MED-02-ALE-25]** — Mensaje ERR-ALE-08
> **Debe mostrar:** La pantalla con el mensaje "Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada." (servidor: "No se puede editar una alerta cerrada")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/AlertasTempranas.tsx:556-557`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar una alerta cerrada

> 📷 **[CAPTURA MED-02-ALE-26]** — Mensaje ERR-ALE-09
> **Debe mostrar:** La pantalla con el mensaje "No se puede editar la alerta porque su plan de acción ya fue confirmado"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAlertas.cs:424-428`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar una alerta con el plan de acción confirmado

> 📷 **[CAPTURA MED-02-ALE-27]** — Mensaje ERR-ALE-10
> **Debe mostrar:** La pantalla con el mensaje "No se puede editar la alerta AT-… porque ha sido subsumida por otra alerta"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAlertas.cs:430-436`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Editar una alerta subsumida

> 📷 **[CAPTURA MED-02-ALE-28]** — Mensaje ERR-ALE-11
> **Debe mostrar:** La pantalla con el mensaje Campo deshabilitado con "No es posible editar el número de una alerta automática" o "No tienes permisos para editar el número de alerta"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/report-alert/ReportAlertModal.tsx:30-45`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar cambiar el número de la alerta en la edición

**⚠️ Atención:**
- ⚠️ Cuando el Monitor o el Líder confirman el plan de acción, la alerta ya no se puede editar.

#### Actividad 9 — Publicar una alerta en Borrador

**Objetivo de la actividad:** Que el Administrador pueda pasar a Activa una alerta en Borrador después de revisarla.

**Cuándo se hace y requisitos previos:** Secuencia E1.5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para publicar una alerta, debe estar en Borrador. | El estado de la fila dice "Borrador" | Verificar el estado (Super Administrador o Administrador) | RN-ALE-08 |
| La alerta que crea el agente queda en Borrador: no cuenta en los indicadores ni se trabaja hasta que se revisa y se publica. | Revise el estado o el dato en la pantalla antes de actuar | Revisar el borrador y publicarlo con **Publicar alerta al guardar** (Super Administrador o Administrador) | RN-AGE-02 |
| Para editar una alerta, no debe estar cerrada ni subsumida y su plan de acción no debe estar confirmado. | Revise el estado de la alerta y el estado del plan en el detalle | Corregir la alerta antes de que se confirme el plan (Super Administrador o Administrador) | RN-ALE-06 |

**Dónde:** Alertas tempranas › alerta en Borrador › ⋯ › **Editar** › Paso 6 › **Publicar alerta al guardar**.

**Qué ve:** En el Paso 6, el interruptor "Publicar alerta al guardar — Al habilitar esta opción, la alerta cambiará de estado Borrador a Activa." (solo en borradores).

**Campos a diligenciar — Reportar alerta temprana / Editar alerta temprana (6 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Publicar alerta al guardar (`(publicar)`) | Condicional: solo aparece al editar una alerta en Borrador | Interruptor | — | Activo / Inactivo | Estado de la alerta = Borrador | Activo | "La alerta no pudo ser publicada." |

- Campos que llena el sistema: Estado (Activa al crear manualmente), modo de creación (manual), consecutivos y contadores, usuario y fecha de creación; historial "created".
- Campos que se bloquean: En edición, el número no se edita en alertas automáticas y solo el Super Administrador lo edita en alertas manuales. Con la alerta cerrada, subsumida o con el plan confirmado no se puede guardar ninguna edición.
- Archivos: "PDF de la alerta" y "Adjunto": solo PDF, hasta 20 MB cada uno; se suben después de crear la alerta y solo los acepta el servidor si el usuario es Super Administrador.
- Guardar o enviar con: **Enviar Alerta** (edición: **Guardar Cambios**); navegación con **Siguiente**, **Atrás** y **Cancelar**.

**Pasos:**

##### Paso 9.1 — Revisar y corregir el borrador
**Objetivo del paso:** Publicar datos correctos.
**Qué hacer:** Abra **Editar** y corrija los Pasos 1 a 5.
**Resultado esperado:** El borrador queda correcto.

##### Paso 9.2 — Activar la publicación
**Objetivo del paso:** Indicar que debe pasar a Activa.
**Qué hacer:** En el Paso 6 active **Publicar alerta al guardar**.
**Resultado esperado:** El interruptor queda activo.

##### Paso 9.3 — Guardar
**Objetivo del paso:** Publicar.
**Qué hacer:** Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Alerta publicada con éxito — Los cambios han sido guardados y la alerta ha sido publicada."; el estado cambia a Activa.

> 📷 **[CAPTURA MED-02-ALE-29]** — Publicar alerta al guardar
> **Debe mostrar:** El Paso 6 de un borrador con el interruptor
> **Resaltar:** Interruptor Publicar alerta al guardar
> **Pantalla / ruta:** `dashboard/src/components/report-alert/AlertFormStep6.tsx:185-195`
> **Tomarla con:** Administrador · **Datos:** Borrador Mock
> **Texto alternativo:** Opción para publicar una alerta en borrador

**Resultado de la actividad:** La alerta queda Activa, cuenta en los indicadores y queda lista para sus recomendaciones; historial "published".

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Publicar una alerta que no está en Borrador | "La alerta no pudo ser publicada." (servidor: "Solo se pueden publicar alertas en estado Borrador. La alerta … está en estado …") | La alerta ya estaba Activa o Cerrada. | No requiere acción: la opción solo aplica a borradores. | — |

> 📷 **[CAPTURA MED-02-ALE-30]** — Mensaje ERR-ALE-12
> **Debe mostrar:** La pantalla con el mensaje "La alerta no pudo ser publicada." (servidor: "Solo se pueden publicar alertas en estado Borrador. La alerta … está en estado …")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:339-345`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Publicar una alerta que no está en Borrador

**⚠️ Atención:**
- ⚠️ Una alerta publicada no vuelve a Borrador.

#### Actividad 10 — Subsumir alertas

**Objetivo de la actividad:** Que el Administrador pueda registrar que una alerta nueva reemplaza a otras alertas activas, que quedan cerradas.

**Cuándo se hace y requisitos previos:** Secuencia E1.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Solo se pueden subsumir alertas existentes, activas y que no hayan sido subsumidas antes; al guardar quedan Cerradas. | Revise el estado o el dato en la pantalla antes de actuar | Elegir solo alertas activas (Super Administrador o Administrador) | RN-ALE-09 |
| Una alerta cerrada no se reabre ni se edita; al cerrarla, su plan y sus informes quedan en estado Cerrado. | Revise el estado o el dato en la pantalla antes de actuar | Verificar antes de cerrar (Super Administrador) | RN-ALE-12 |

**Dónde:** Reportar o Editar alerta › Paso 6 › **Esta alerta subsume otras alertas** › Alertas subsumidas.

**Qué ve:** El interruptor "Esta alerta subsume otras alertas" y, al activarlo, la lista **Alertas subsumidas** con las alertas disponibles; sin alertas: "No hay alertas disponibles para subsunción".

**Campos a diligenciar — Reportar alerta temprana / Editar alerta temprana (6 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Esta alerta subsume otras alertas (`subsumption_enabled`) | No | Interruptor | — | Activo / Inactivo | Habilita Alertas subsumidas | Inactivo | "No hay alertas disponibles para subsunción" |
| 2 | Alertas subsumidas (`subsumed_alert_ids`) | Condicional: si el interruptor está activo | Lista de selección múltiple con búsqueda | Alertas activas no subsumidas | Alertas disponibles para subsunción | Esta alerta subsume otras alertas | AT-900-2025 (ficticia) | "La alerta AT-… ya ha sido subsumida por otra alerta" |

- Campos que llena el sistema: Estado (Activa al crear manualmente), modo de creación (manual), consecutivos y contadores, usuario y fecha de creación; historial "created".
- Campos que se bloquean: En edición, el número no se edita en alertas automáticas y solo el Super Administrador lo edita en alertas manuales. Con la alerta cerrada, subsumida o con el plan confirmado no se puede guardar ninguna edición.
- Archivos: "PDF de la alerta" y "Adjunto": solo PDF, hasta 20 MB cada uno; se suben después de crear la alerta y solo los acepta el servidor si el usuario es Super Administrador.
- Guardar o enviar con: **Enviar Alerta** (edición: **Guardar Cambios**); navegación con **Siguiente**, **Atrás** y **Cancelar**.

**Pasos:**

##### Paso 10.1 — Activar la subsunción
**Objetivo del paso:** Habilitar la selección.
**Qué hacer:** En el Paso 6 active **Esta alerta subsume otras alertas**.
**Resultado esperado:** Aparece la lista Alertas subsumidas.

##### Paso 10.2 — Elegir las alertas
**Objetivo del paso:** Indicar cuáles se reemplazan.
**Qué hacer:** Busque y marque las alertas que el documento declara subsumidas.
**Resultado esperado:** Aparece "Al confirmar, las alertas seleccionadas se subsumirán en esta alerta y cambiarán su estado a 'Cerrada'."

##### Paso 10.3 — Guardar
**Objetivo del paso:** Aplicar la subsunción.
**Qué hacer:** Haga clic en **Enviar Alerta** o **Guardar Cambios**.
**Resultado esperado:** Las alertas subsumidas pasan a Cerrada y aparecen en la pestaña "Alertas subsumidas" del detalle.

> 📷 **[CAPTURA MED-02-ALE-31]** — Subsunción
> **Debe mostrar:** El Paso 6 con dos alertas seleccionadas para subsumir
> **Resaltar:** Mensaje de confirmación
> **Pantalla / ruta:** `dashboard/src/components/report-alert/AlertFormStep6.tsx:95-131`
> **Tomarla con:** Administrador · **Datos:** Alertas Mock
> **Texto alternativo:** Selección de alertas subsumidas

**Resultado de la actividad:** Las alertas subsumidas quedan Cerradas y vinculadas a la nueva.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Subsumir una alerta ya subsumida o cerrada | "La alerta AT-… ya ha sido subsumida por otra alerta" / "La alerta AT-… ya está cerrada y no puede ser subsumida" | Solo se subsumen alertas activas y no subsumidas. | Quite esa alerta de la selección del Paso 6. | — |
| Activar la subsunción y no ver alertas | "No hay alertas disponibles para subsunción" | No hay otras alertas activas no subsumidas. | Desactive "Esta alerta subsume otras alertas" y continúe. | — |

**⚠️ Atención:**
- ⚠️ Irreversible: una alerta subsumida queda cerrada y no se puede editar.

### Módulo 05 — Recomendaciones

**Prerrequisitos:** Módulo 04 (la alerta debe existir y estar Activa).

**Definición del módulo:** Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). Permite listarlas, buscarlas, filtrarlas, ver su detalle y descargarlas; al Super Administrador y al Administrador, crearlas en 2 pasos (eje temático y descripción; entidades principales y asociadas) y editarlas; al Super Administrador, eliminarlas. El sistema asigna el código RC y notifica por correo a las entidades.

**Objetivo del módulo:** Que el Administrador pueda consultar, buscar y filtrar las recomendaciones de una alerta; ver el detalle de una recomendación; descargar las recomendaciones de una alerta en CSV; agregar una recomendación; editar una recomendación.

**Contexto del módulo:** Corresponde a la fase E2. Requiere una alerta registrada (E1). Entrega las recomendaciones a *Planes de acción* (E3), donde la Entidad Territorial les agrega actividades, y dispara el correo "Nueva Recomendacion Asignada". Mientras el plan de acción no esté confirmado, las recomendaciones se pueden editar o eliminar. Para el Administrador: ve todas las recomendaciones de cada alerta que está en su alcance. En total, tiene 7 de las 8 funcionalidades del módulo; no tiene: eliminar una recomendación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar las recomendaciones de una alerta (F-REC-01) | Muestra la tabla de recomendaciones de la alerta: Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades (Aprobadas / Total) y Ejecución (Ejecutadas / Programadas). | R | Módulo 04 — Actividad 6; Módulo 05 — Actividad 1 |
| Buscar y filtrar recomendaciones (F-REC-02) | Busca por código o descripción y filtra por Entidad Principal, Eje Temático y Modo de Creación. | R | Módulo 05 — Actividad 1 |
| Ver el detalle de una recomendación (F-REC-03) | Muestra Información general (Eje temático, Entidad principal), Descripción, Entidades asociadas y Ejecución. | R | Módulo 05 — Actividad 2 |
| Descargar las recomendaciones (CSV) (F-REC-04) | Descarga las recomendaciones visibles: Código, Eje Temático, Entidad Principal, Descripción, Modo de Creación y Fecha de Creación. | Archivo | Módulo 05 — Actividad 3 |
| Agregar una recomendación (F-REC-05) | Registra en 2 pasos el eje temático, la descripción, una o varias entidades principales y sus entidades asociadas; se crea una recomendación por cada entidad principal. | C | Módulo 05 — Actividad 4 |
| Editar una recomendación (F-REC-06) | Modifica eje, descripción y entidades. | U | Módulo 05 — Actividad 5 |
| Asignar el código RC (F-REC-08) | El sistema asigna el código RC-{NNN}-{AAAA}-{NNN} con el consecutivo de la alerta. | Automática | Módulo 05 — Actividad 1; Módulo 05 — Actividad 4 |

#### Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el Administrador pueda ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Alertas tempranas › ⋯ › **Recomendaciones**.

**Qué ve:** El encabezado de la alerta, el botón **Agregar recomendación**, **Descargar**, "Buscar por nombre" y **Filtros** (Entidad Principal "Todas las entidades", Eje Temático, Modo de Creación Manual/Automática).

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

> 📷 **[CAPTURA MED-02-REC-01]** — Recomendaciones de una alerta
> **Debe mostrar:** La tabla de recomendaciones vista por un usuario Administrador
> **Resaltar:** Columnas Actividades y Ejecución; Filtros
> **Pantalla / ruta:** `/alertas-tempranas/:id/recomendaciones` (`dashboard/src/components/recomendaciones/RecomendacionesTab.tsx`)
> **Tomarla con:** Administrador · **Datos:** AT-013-2025 o alerta Mock
> **Texto alternativo:** Listado de recomendaciones de una alerta

**Resultado de la actividad:** Conoce las recomendaciones de la alerta y su avance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Las recomendaciones no cargan | "Error al cargar las recomendaciones. Por favor, intente nuevamente." | Falla del servicio. | Recargue la página. | — |
| Abrir las recomendaciones de una alerta eliminada | "La alerta solicitada no existe o ha sido eliminada." | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-REC-02]** — Mensaje ERR-REC-07
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar las recomendaciones. Por favor, intente nuevamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:238`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Las recomendaciones no cargan

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25] hay 41 recomendaciones, de RC-001-2025-013 a RC-041-2025-013; por ejemplo RC-001-2025-013, eje "Coordinación de Respuesta Rápida", Entidad Principal "MinInterior - CIPRAT".

#### Actividad 2 — Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el Administrador pueda leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

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

> 📷 **[CAPTURA MED-02-REC-03]** — Detalle de recomendación
> **Debe mostrar:** La ventana con Entidad principal y Entidades asociadas
> **Resaltar:** Entidades asociadas
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Recomendación Mock
> **Texto alternativo:** Detalle de una recomendación

**Resultado de la actividad:** Conoce la recomendación completa.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**Ejemplo:** RC-011-2025-013 [DATO REAL AT-013-25]: su descripción empieza "Recomendación No. 12 …", es decir, el código RC no coincide con el número de la recomendación en el documento (hallazgo H3).

#### Actividad 3 — Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el Administrador pueda descargar las recomendaciones visibles en un archivo CSV.

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

> 📷 **[CAPTURA MED-02-REC-04]** — CSV de recomendaciones
> **Debe mostrar:** El archivo CSV abierto en Excel
> **Resaltar:** Columnas
> **Pantalla / ruta:** Recomendaciones › Descargar (`main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566`)
> **Tomarla con:** Administrador · **Datos:** Alerta Mock
> **Texto alternativo:** Archivo CSV de recomendaciones

**Resultado de la actividad:** Tiene las recomendaciones en un archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

**⚠️ Atención:**
- El texto de la descripción sale completo (sin corte a 4.000 caracteres).

#### Actividad 4 — Agregar una recomendación

**Objetivo de la actividad:** Que el Administrador pueda registrar una recomendación de la alerta con su eje, su descripción, su Entidad Principal y sus entidades asociadas, para que la entidad formule su plan.

**Cuándo se hace y requisitos previos:** Secuencia E2.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para crear una recomendación, la alerta debe existir y no estar cerrada. | La alerta aparece Activa | Registrar la alerta primero (Super Administrador o Administrador) | RN-REC-01 |
| Para crear, editar o eliminar recomendaciones, el plan de acción de la alerta no debe estar confirmado. | El listado de Planes de acción muestra el plan sin confirmar | Cargar todas las recomendaciones antes de la confirmación (Super Administrador o Administrador) | RN-REC-02 |
| Eje temático, descripción y al menos una Entidad Principal son obligatorios. | Revise el estado o el dato en la pantalla antes de actuar | Completar los 2 pasos (Super Administrador o Administrador) | RN-REC-03 |
| La Entidad Principal debe existir y estar activa. | Revise el estado o el dato en la pantalla antes de actuar | Crear o activar la entidad en Usuarios y entidades (Super Administrador o Administrador) | RN-REC-04 |
| Por cada Entidad Principal agregada se crea una recomendación distinta, con su propio código RC y la misma descripción. | Revise el estado o el dato en la pantalla antes de actuar | Agregar una Entidad Principal por recomendación; las demás como asociadas (Super Administrador o Administrador) | RN-REC-05 |
| El eje temático solo se valida contra la lista en la pantalla, y el sistema no impide recomendaciones duplicadas. | Revise el estado o el dato en la pantalla antes de actuar | Buscar antes de crear (Super Administrador o Administrador) | RN-REC-06 |

**Dónde:** Recomendaciones › **Agregar recomendación** › ventana "Agregar recomendación — Registra una recomendación y asigna las entidades responsables para su notificación y seguimiento.".

**Qué ve:** Un asistente de 2 pasos: 1 Información general (Eje temático, Descripción) y 2 Entidades (Entidad Principal con "Encargada de reportar el informe de ejecución.", el aviso "Notificación a entidades principales — Las entidades principales serán notificadas a través de la aplicación." y **Asociar entidades**). Botones **Atrás**, **Siguiente** y **Crear recomendación**.

**Campos a diligenciar — Agregar recomendación / Editar recomendación (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Eje temático (`thematic_axis`) | Sí | Lista de selección única | El servidor no valida contra la lista | 14 ejes (Coordinación de Respuesta Rápida; Disuasión del Contexto de amenaza; Investigación y acceso a la Justicia; Medidas de prevención y protección; …) | — | Coordinación de Respuesta Rápida (RC-001-2025-013) [DATO REAL AT-013-25] | "El eje temático es requerido" |
| 2 | Descripción (`description`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo | — | — | "Recomendación No. 1 Categoría temática de la recomendación: Coordinación de la respuesta rápida…" [DATO REAL AT-013-25] | "La descripción es requerida" |
| 3 | Entidad Principal (`main_organization_id`) | Sí (al menos una) | Lista con búsqueda, repetible ("Seleccionar") | Entidad activa; por cada una se crea una recomendación | Entidades registradas | — | MinInterior - CIPRAT [DATO REAL AT-013-25] | "Debe agregar al menos una entidad" / "La organización no existe o fue eliminada" |
| 4 | Entidades asociadas (`associated_entities`) | No | Lista de selección múltiple (por Entidad Principal) | Entidades activas distintas de la principal | Entidades registradas | Entidad Principal | Alcaldía de Prueba | "No se encontraron entidades" |

- Campos que llena el sistema: Código RC-{NNN}-{AAAA}-{NNN}, Modo de Creación (Manual), estado "sin_actividad", fecha de creación; correo a las entidades.
- Campos que se bloquean: Con la alerta cerrada o el plan confirmado no se puede crear, editar ni eliminar.
- Archivos: No aplica.
- Guardar o enviar con: **Crear recomendación** (edición: **Guardar cambios**); **Siguiente** / **Atrás**.

**Pasos:**

##### Paso 4.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** Haga clic en **Agregar recomendación**.
**Resultado esperado:** Se abre el Paso 1.

##### Paso 4.2 — Elegir el eje temático
**Objetivo del paso:** Clasificar la recomendación.
**Qué hacer:** Despliegue **Eje temático** y elija el eje del documento (14 opciones).
**Resultado esperado:** El eje queda seleccionado.

##### Paso 4.3 — Escribir la descripción
**Objetivo del paso:** Registrar el texto de la recomendación.
**Qué hacer:** En **Descripción** pegue el texto de la recomendación. Buena práctica: empiece por "Recomendación No. X" del documento para conservar la referencia (hallazgo H3).
**Resultado esperado:** El texto queda registrado (sin límite de longitud).

##### Paso 4.4 — Agregar la Entidad Principal
**Objetivo del paso:** Definir quién responde.
**Qué hacer:** Haga clic en **Siguiente**; en **Entidad Principal** busque ("Buscar entidad...") y elija la entidad responsable.
**Resultado esperado:** La entidad aparece en la lista. Si agrega varias, se creará una recomendación por cada una.

##### Paso 4.5 — Asociar entidades
**Objetivo del paso:** Registrar quién apoya.
**Qué hacer:** Para la entidad principal, use **Asociar entidades** y marque las entidades de apoyo.
**Resultado esperado:** Las asociadas aparecen bajo la principal; recibirán correo pero no verán la recomendación.

##### Paso 4.6 — Revisar
**Objetivo del paso:** Evitar duplicados.
**Qué hacer:** Verifique que haya una sola Entidad Principal si la recomendación es una sola.
**Resultado esperado:** Los datos son correctos.

##### Paso 4.7 — Crear
**Objetivo del paso:** Registrar y notificar.
**Qué hacer:** Haga clic en **Crear recomendación**.
**Resultado esperado:** Aparece "Recomendación creada — La recomendación ha sido registrada correctamente." (o "Se han creado {N} recomendaciones correctamente."); se asigna el código RC y se envía el correo a las entidades.

> 🎞️ **[GIF MED-02-REC-05]** — Agregar recomendación
> **Debe mostrar:** Los dos pasos del registro con una Entidad Principal y una asociada
> **Resaltar:** Eje temático; Entidad Principal; Asociar entidades; Crear recomendación
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecommendationModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Mock
> **Solo para GIF — Secuencia:** 1) Agregar recomendación 2) Eje 3) Descripción 4) Siguiente 5) Entidad Principal 6) Asociar 7) Crear · **Duración aproximada:** 35 segundos
> **Texto alternativo:** Animación del registro de una recomendación

**Resultado de la actividad:** La recomendación queda en estado "sin actividad" con su código RC; la Entidad Territorial recibe "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" y el plan de la alerta pasa a "Sin plan".

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:560-635`. La entidad recibe el correo fuera de la plataforma; su respuesta vuelve como actividades en *Planes de acción*.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Avanzar o guardar sin datos | "El eje temático es requerido", "La descripción es requerida", "Debe agregar al menos una entidad" | Faltan datos obligatorios. | Elija el eje temático, escriba la descripción y agregue al menos una Entidad Principal. | — |
| Elegir una entidad inactiva o eliminada | "La organización no existe o fue eliminada" | La entidad no está activa. | Elija otra entidad o revise la entidad en *Usuarios y entidades*. | — |
| Agregar, editar o eliminar recomendaciones de una alerta cerrada | Botones deshabilitados: "No se pueden agregar recomendaciones a una alerta cerrada" (servidor: "No se puede crear una recomendación para una alerta cerrada") | La alerta está cerrada. | No requiere acción. | — |
| Agregar, editar o eliminar recomendaciones con el plan confirmado | "No se pueden crear recomendaciones porque el plan de acción ya fue confirmado" / "No se puede editar la recomendación porque el plan de acción ya fue confirmado" / "No se puede eliminar la recomendación porque el plan de acción ya fue confirmado" | Con el plan confirmado las recomendaciones quedan bloqueadas. | Las recomendaciones nuevas de la Defensoría se cargan con un informe de seguimiento. | Cargue todas las recomendaciones antes de la confirmación. |
| Agregar varias entidades principales en una sola recomendación | Aviso "Recomendaciones creadas — Se han creado {N} recomendaciones correctamente." | Por cada Entidad Principal se crea una recomendación distinta con la misma descripción (hallazgo H2). | Si debía ser una sola, el Super Administrador elimina las sobrantes y las demás entidades se registran como **Entidades asociadas**. | Agregue una Entidad Principal por recomendación y las demás como asociadas. |
| Registrar dos veces la misma recomendación | No aparece mensaje: el sistema la acepta. | NO ENCONTRADA una validación de unicidad de eje, entidad y descripción. | Busque por texto antes de crear; si quedó duplicada, pida al Super Administrador eliminarla. | Use "Buscar por nombre" antes de crear. |

> 📷 **[CAPTURA MED-02-REC-06]** — Mensaje ERR-REC-01
> **Debe mostrar:** La pantalla con el mensaje "El eje temático es requerido", "La descripción es requerida", "Debe agregar al menos una entidad"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecommendationModal.tsx:122-140`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Avanzar o guardar sin datos

> 📷 **[CAPTURA MED-02-REC-07]** — Mensaje ERR-REC-02
> **Debe mostrar:** La pantalla con el mensaje "La organización no existe o fue eliminada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:438`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Elegir una entidad inactiva o eliminada

> 📷 **[CAPTURA MED-02-REC-08]** — Mensaje ERR-REC-03
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados: "No se pueden agregar recomendaciones a una alerta cerrada" (servidor: "No se puede crear una recomendación para una alerta cerrada")
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecomendacionesTab.tsx:70-88`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar, editar o eliminar recomendaciones de una alerta cerrada

> 📷 **[CAPTURA MED-02-REC-09]** — Mensaje ERR-REC-04
> **Debe mostrar:** La pantalla con el mensaje "No se pueden crear recomendaciones porque el plan de acción ya fue confirmado" / "No se puede editar la recomendación porque el plan de acción ya fue confirmad
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:423-428,614-618,749-753`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar, editar o eliminar recomendaciones con el plan confirmado

> 📷 **[CAPTURA MED-02-REC-10]** — Mensaje ERR-REC-05
> **Debe mostrar:** La pantalla con el mensaje Aviso "Recomendaciones creadas — Se han creado {N} recomendaciones correctamente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Recomendaciones.tsx:272-313`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar varias entidades principales en una sola recomendación

**⚠️ Atención:**
- ⚠️ Cada Entidad Principal agregada crea una recomendación distinta con el mismo texto (hallazgo H2). Use una principal y las demás como asociadas.
- ⚠️ Cargue todas las recomendaciones antes de que se confirme el plan: después ya no se pueden crear aquí.
- Las entidades asociadas no ven la recomendación en su listado (riesgo R6).

**Ejemplo:** RC-001-2025-013 [DATO REAL AT-013-25]: Eje "Coordinación de Respuesta Rápida", Descripción "Recomendación No. 1 Categoría temática de la recomendación: Coordinación de la respuesta rápida…", Entidad Principal "MinInterior - CIPRAT". Mock: eje "Medidas de prevención y protección", Entidad Principal "Gobernación de Prueba", asociada "Alcaldía de Prueba".

#### Actividad 5 — Editar una recomendación

**Objetivo de la actividad:** Que el Administrador pueda corregir el eje, la descripción o las entidades de una recomendación antes de la confirmación del plan.

**Cuándo se hace y requisitos previos:** Secuencia E2.3.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para crear, editar o eliminar recomendaciones, el plan de acción de la alerta no debe estar confirmado. | El listado de Planes de acción muestra el plan sin confirmar | Cargar todas las recomendaciones antes de la confirmación (Super Administrador o Administrador) | RN-REC-02 |
| Eje temático, descripción y al menos una Entidad Principal son obligatorios. | Revise el estado o el dato en la pantalla antes de actuar | Completar los 2 pasos (Super Administrador o Administrador) | RN-REC-03 |
| La Entidad Principal debe existir y estar activa. | Revise el estado o el dato en la pantalla antes de actuar | Crear o activar la entidad en Usuarios y entidades (Super Administrador o Administrador) | RN-REC-04 |

**Dónde:** Recomendaciones › ⋯ › **Editar** › "Editar recomendación — Actualiza la información de la recomendación y las entidades responsables.".

**Qué ve:** El mismo asistente con los datos actuales y el botón **Guardar cambios**.

**Campos a diligenciar — Agregar recomendación / Editar recomendación (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Eje temático (`thematic_axis`) | Sí | Lista de selección única | El servidor no valida contra la lista | 14 ejes (Coordinación de Respuesta Rápida; Disuasión del Contexto de amenaza; Investigación y acceso a la Justicia; Medidas de prevención y protección; …) | — | Coordinación de Respuesta Rápida (RC-001-2025-013) [DATO REAL AT-013-25] | "El eje temático es requerido" |
| 2 | Descripción (`description`) | Sí | Área de texto | Mínimo 1 carácter; sin máximo | — | — | "Recomendación No. 1 Categoría temática de la recomendación: Coordinación de la respuesta rápida…" [DATO REAL AT-013-25] | "La descripción es requerida" |
| 3 | Entidad Principal (`main_organization_id`) | Sí (al menos una) | Lista con búsqueda, repetible ("Seleccionar") | Entidad activa; por cada una se crea una recomendación | Entidades registradas | — | MinInterior - CIPRAT [DATO REAL AT-013-25] | "Debe agregar al menos una entidad" / "La organización no existe o fue eliminada" |
| 4 | Entidades asociadas (`associated_entities`) | No | Lista de selección múltiple (por Entidad Principal) | Entidades activas distintas de la principal | Entidades registradas | Entidad Principal | Alcaldía de Prueba | "No se encontraron entidades" |

- Campos que llena el sistema: Código RC-{NNN}-{AAAA}-{NNN}, Modo de Creación (Manual), estado "sin_actividad", fecha de creación; correo a las entidades.
- Campos que se bloquean: Con la alerta cerrada o el plan confirmado no se puede crear, editar ni eliminar.
- Archivos: No aplica.
- Guardar o enviar con: **Crear recomendación** (edición: **Guardar cambios**); **Siguiente** / **Atrás**.

**Pasos:**

##### Paso 5.1 — Abrir la edición
**Objetivo del paso:** Cargar la recomendación.
**Qué hacer:** Haga clic en ⋯ › **Editar**.
**Resultado esperado:** Se abre el asistente con los datos.

##### Paso 5.2 — Corregir los datos
**Objetivo del paso:** Ajustar eje, descripción y entidades.
**Qué hacer:** Modifique **Eje temático**, **Descripción**, **Entidad Principal** o **Entidades asociadas**.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 5.3 — Guardar
**Objetivo del paso:** Aplicar y notificar.
**Qué hacer:** Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Recomendación actualizada — Los cambios han sido guardados correctamente." y se envía "SI-CIPRAT - Recomendacion Actualizada: {código}".

> 📷 **[CAPTURA MED-02-REC-11]** — Editar recomendación
> **Debe mostrar:** El Paso 2 de la edición
> **Resaltar:** Guardar cambios
> **Pantalla / ruta:** `dashboard/src/components/recomendaciones/RecommendationModal.tsx:185-186`
> **Tomarla con:** Administrador · **Datos:** Recomendación Mock
> **Texto alternativo:** Edición de una recomendación

**Resultado de la actividad:** La recomendación queda actualizada y notificada.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Avanzar o guardar sin datos | "El eje temático es requerido", "La descripción es requerida", "Debe agregar al menos una entidad" | Faltan datos obligatorios. | Elija el eje temático, escriba la descripción y agregue al menos una Entidad Principal. | — |
| Elegir una entidad inactiva o eliminada | "La organización no existe o fue eliminada" | La entidad no está activa. | Elija otra entidad o revise la entidad en *Usuarios y entidades*. | — |
| Agregar, editar o eliminar recomendaciones de una alerta cerrada | Botones deshabilitados: "No se pueden agregar recomendaciones a una alerta cerrada" (servidor: "No se puede crear una recomendación para una alerta cerrada") | La alerta está cerrada. | No requiere acción. | — |
| Agregar, editar o eliminar recomendaciones con el plan confirmado | "No se pueden crear recomendaciones porque el plan de acción ya fue confirmado" / "No se puede editar la recomendación porque el plan de acción ya fue confirmado" / "No se puede eliminar la recomendación porque el plan de acción ya fue confirmado" | Con el plan confirmado las recomendaciones quedan bloqueadas. | Las recomendaciones nuevas de la Defensoría se cargan con un informe de seguimiento. | Cargue todas las recomendaciones antes de la confirmación. |

**⚠️ Atención:**
- ⚠️ Con el plan confirmado o la alerta cerrada no se puede editar.

### Módulo 06 — Planes de acción

**Prerrequisitos:** Módulo 05; que la Secretaría Técnica haya registrado recomendaciones  (RN-REC-01).

**Definición del módulo:** Módulo donde se formula y se ejecuta el plan de acción. Tiene tres niveles: alertas con su plan (Ejecutado vs programado, estado del plan e informes), recomendaciones de la alerta y actividades de cada recomendación. Permite a las entidades agregar, editar y eliminar actividades, comentar y reportar o editar informes de ejecución con su PDF; a todos los roles con acceso, consultar, filtrar y descargar la información. Tiene además las pestañas globales Recomendaciones y Actividades y el acceso al Informe de recomendaciones.

**Objetivo del módulo:** Que el Administrador pueda consultar y filtrar los planes de acción por alerta; recorrer las recomendaciones del plan de una alerta; consultar las pestañas globales de Recomendaciones y Actividades; consultar las actividades de una recomendación y su detalle; consultar los informes de ejecución de una actividad y descargar su PDF.

**Contexto del módulo:** Corresponde a la formulación (E3) y al reporte de ejecución (E5.1-E5.2). Recibe las recomendaciones de E2 y entrega las actividades a *Seguimiento*, donde se revisan y aprueban (E4). Los informes solo se habilitan cuando el plan está confirmado (E4.3). Lo usan la Entidad Territorial (Central y Subdirección) y el Super Administrador para registrar, y el Administrador, Consulta Global y Consulta Entidad para consultar. Monitor, Líder de Macrozona y Consulta Departamentos trabajan esta información desde *Seguimiento*. Para el Administrador: ve los planes, recomendaciones y actividades de todas las alertas del país, sin filtro. En total, tiene 11 de las 20 funcionalidades del módulo; no tiene: agregar una actividad, agregar una actividad a un plan confirmado, editar una actividad, eliminar una actividad, ver y escribir comentarios de una actividad, eliminar un comentario propio, reportar un informe de ejecución, editar un informe de ejecución pendiente, eliminar un informe de ejecución.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar las alertas con plan de acción (F-PLA-01) | Pestaña **Alertas**: por alerta muestra Ejecutado vs programado, % de cumplimiento, estado del Plan de acción y estado del Informe. | R | Módulo 06 — Actividad 1 |
| Buscar y filtrar planes de acción (F-PLA-02) | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento (0-30, 31-50, 51-80, 81-100). | R | Módulo 06 — Actividad 1 |
| Ver el detalle y el historial del plan de una alerta (F-PLA-03) | Abre la ficha con "Información de alerta" e "Historial Plan de acción". | R | Módulo 06 — Actividad 1 |
| Descargar el listado de planes (CSV) (F-PLA-04) | Descarga Número de Alerta, Cumplimiento (%) y Plan de Acción de las alertas visibles. | Archivo | Módulo 06 — Actividad 1 |
| Ver las recomendaciones del plan de una alerta (F-PLA-05) | Desde **Ir al plan de acción**, lista las recomendaciones con Actividades (Aprobadas / Total) y Ejecución; **Ver Actividades** abre las actividades. | R | Módulo 06 — Actividad 2 |
| Consultar la pestaña global de Recomendaciones (F-PLA-06) | Pestaña **Recomendaciones** con todas las recomendaciones del alcance, filtros (alerta, eje, entidad) y descarga. | R | Módulo 06 — Actividad 3 |
| Consultar la pestaña global de Actividades (F-PLA-07) | Pestaña **Actividades** con todas las actividades del alcance: Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe, Próximo Informe; filtros y descarga. | R | Módulo 06 — Actividad 3 |
| Listar las actividades de una recomendación (F-PLA-08) | Muestra Actividad, Objetivo, Descripción, Número Actividades, Ejecución (Ejecutadas / Programadas), Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; busca por objetivo y filtra por Estado, Instrumento de Planeación y Recursos. | R | Módulo 06 — Actividad 4 |
| Ver el detalle de una actividad (F-PLA-09) | Abre "Detalle de Actividad": Recomendación, campos de la actividad, Estado Informe, Ejecución y Próximo Informe. | R | Módulo 06 — Actividad 4 |
| Descargar las actividades (CSV) (F-PLA-10) | Descarga Número de Alerta, Código de Recomendación, Objetivo, Descripción, Número de Actividades, Plazo, Instrumento, Recursos, Estado, Observaciones y fechas. | Archivo | Módulo 06 — Actividad 3; Módulo 06 — Actividad 4 |
| Consultar los informes de ejecución y descargar su PDF (F-PLA-19) | En el detalle de la recomendación (pestaña de actividades) muestra "Informes de ejecución" con todos sus campos y el archivo "Informe.pdf". | Archivo | Módulo 06 — Actividad 5 |
| Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01, módulo Tareas programadas) | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Módulo 06 — Actividad 4 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 06 — Actividad 4 |
| Calcular el próximo informe al aprobar un informe (F-TAR-04, módulo Tareas programadas) | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Módulo 06 — Actividad 4 |

#### Actividad 1 — Consultar y filtrar los planes de acción por alerta

**Objetivo de la actividad:** Que el Administrador pueda ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Planes de acción** (`/planes-de-accion`) › pestaña **Alertas**.

**Qué ve:** "Planes de Acción — Gestionar de manera organizada y eficiente todas las actividades asociadas a las recomendaciones", el botón **Informe** y las pestañas **Alertas**, **Recomendaciones** y **Actividades**. En **Alertas**: "Alertas tempranas" con **Descargar**, "Buscar por nombre" y **Filtros**.

| Columna | Descripción |
|---|---|
| Alerta | Número y fecha de la alerta |
| Cumplimiento | Ejecutado vs programado y % |
| Plan de acción | Estado del plan |
| Informe | Estado de los informes |
| Acciones | **Ir al plan de acción** y detalle |

Estados del **Plan de acción**: "Sin recomendaciones", "Sin plan" (recomendaciones sin actividades), "Pendiente" (hay actividades por aprobar), "Aprobado" (todas aprobadas; listo para confirmar), "Cerrado" (alerta cerrada). Estados del **Informe**: "Sin Informe", "Sin Completar", "Pendiente", "Aprobado", "Completado", "Cerrado".

Filtros: **Estado del Plan de Acción**, **Estado del Informe** y **Porcentaje de Cumplimiento** (0-30, 31-50, 51-80, 81-100). Ve los planes de nacional.

**Pasos:**

##### Paso 1.1 — Abrir Planes de acción
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** Haga clic en **Planes de acción**.
**Resultado esperado:** Aparece la pestaña **Alertas**.

##### Paso 1.2 — Leer el estado y el cumplimiento
**Objetivo del paso:** Saber qué plan está pendiente o aprobado.
**Qué hacer:** Lea las columnas Cumplimiento, Plan de acción e Informe.
**Resultado esperado:** Identifica, por ejemplo, los planes "Sin plan" que aún no tienen actividades.

##### Paso 1.3 — Filtrar
**Objetivo del paso:** Ver solo lo que le interesa.
**Qué hacer:** Haga clic en **Filtros**, elija Estado del Plan de Acción, Estado del Informe o Porcentaje de Cumplimiento y **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 1.4 — Ver el detalle del plan
**Objetivo del paso:** Revisar la información de la alerta y el historial del plan.
**Qué hacer:** Haga clic en el ícono de detalle de la fila.
**Resultado esperado:** Se abre la ficha con "Información de alerta" e "Historial Plan de acción".

##### Paso 1.5 — Descargar el listado
**Objetivo del paso:** Tener el estado en un archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga un CSV con Número de Alerta, Cumplimiento (%) y Plan de Acción.

> 📷 **[CAPTURA MED-02-PLA-01]** — Planes de acción por alerta
> **Debe mostrar:** La pestaña Alertas de Planes de acción vista por un usuario Administrador
> **Resaltar:** Columnas Cumplimiento, Plan de acción e Informe; Filtros
> **Pantalla / ruta:** `/planes-de-accion` (`dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx`)
> **Tomarla con:** Administrador · **Datos:** Planes Mock en distintos estados
> **Texto alternativo:** Listado de planes de acción por alerta

**Resultado de la actividad:** Conoce el estado de los planes de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |

#### Actividad 2 — Recorrer las recomendaciones del plan de una alerta

**Objetivo de la actividad:** Que el Administrador pueda entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Planes de acción › fila › **Ir al plan de acción** (`/planes-de-accion/:id/recomendaciones`).

**Qué ve:** La tabla de recomendaciones de la alerta (Recomendación, Eje tematico, Entidad Principal, Descripción, Actividades Aprobadas / Total, Ejecución Ejecutadas / Programadas) con **Ver Actividades** y el ícono de detalle. El detalle abre una ventana con las pestañas **Información**, **Actividades** e **Historial** ("No hay historial disponible." si no hay eventos). 

**Pasos:**

##### Paso 2.1 — Entrar al plan
**Objetivo del paso:** Ver las recomendaciones de la alerta.
**Qué hacer:** En la fila de la alerta haga clic en **Ir al plan de acción**.
**Resultado esperado:** Aparece la tabla de recomendaciones.

##### Paso 2.2 — Abrir el detalle de una recomendación
**Objetivo del paso:** Ver su información y su historial.
**Qué hacer:** Haga clic en el ícono de detalle y recorra **Información**, **Actividades** e **Historial**.
**Resultado esperado:** Ve la recomendación, sus actividades y los eventos del plan.

##### Paso 2.3 — Ir a las actividades
**Objetivo del paso:** Trabajar las actividades de la recomendación.
**Qué hacer:** Haga clic en **Ver Actividades**.
**Resultado esperado:** Se abre la lista de actividades de la recomendación.

> 📷 **[CAPTURA MED-02-PLA-02]** — Recomendaciones del plan
> **Debe mostrar:** La tabla de recomendaciones con el botón Ver Actividades
> **Resaltar:** Ver Actividades; Actividades Aprobadas / Total
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/PlanDeAccionRecomendacionesTab.tsx`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock con dos recomendaciones
> **Texto alternativo:** Recomendaciones del plan de acción de una alerta

**Resultado de la actividad:** Llega a las actividades de la recomendación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Las actividades no cargan o no se eliminan | "Error al cargar las actividades" / "Error al eliminar la actividad" | Falla del servicio. | Recargue la página e intente de nuevo. | — |

> 📷 **[CAPTURA MED-02-PLA-03]** — Mensaje ERR-PLA-15
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar las actividades" / "Error al eliminar la actividad"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/RecomendacionDetailModalWithTabs.tsx:95-158`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Las actividades no cargan o no se eliminan

**Ejemplo:** En la AT-013-2025 [DATO REAL AT-013-25], la recomendación RC-002-2025-013 tiene como Entidad Principal "MinInterior - Democracia y Participación".

#### Actividad 3 — Consultar las pestañas globales de Recomendaciones y Actividades

**Objetivo de la actividad:** Que el Administrador pueda ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La Entidad Territorial y Consulta Entidad solo ven, dentro de cada alerta, las recomendaciones cuya Entidad Principal es su entidad o subdirección. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la Entidad Principal de la recomendación (Super Administrador o Administrador) | RN-REC-08 |

**Dónde:** Planes de acción › pestañas **Recomendaciones** y **Actividades**.

**Qué ve:** En **Recomendaciones**: todas las recomendaciones (con la columna Alerta), filtros por alerta, eje, entidad y modo, y **Descargar**. En **Actividades**: todas las actividades con Actividad, Alerta, Objetivo, Plazo, Instrumento, Recursos, Estado, Estado Informe y Próximo Informe; filtros **Alerta**, **Recomendacion**, **Estado**, **Instrumento de Planeación**, **Recursos** y **Plazo de Implementación**; **Descargar**.

**Pasos:**

##### Paso 3.1 — Abrir Recomendaciones
**Objetivo del paso:** Ver todas las recomendaciones.
**Qué hacer:** Haga clic en la pestaña **Recomendaciones**.
**Resultado esperado:** Aparece la tabla global.

##### Paso 3.2 — Abrir Actividades
**Objetivo del paso:** Ver todas las actividades.
**Qué hacer:** Haga clic en la pestaña **Actividades**.
**Resultado esperado:** Aparece la tabla global de actividades.

##### Paso 3.3 — Filtrar y descargar
**Objetivo del paso:** Obtener un listado específico.
**Qué hacer:** Use **Filtros** (por ejemplo, Estado "Pendiente Aprobación") y luego **Descargar**.
**Resultado esperado:** Se descarga el CSV filtrado.

> 📷 **[CAPTURA MED-02-PLA-04]** — Pestaña global Actividades
> **Debe mostrar:** La tabla global de actividades con el filtro de Estado
> **Resaltar:** Pestañas; Filtros; columna Próximo Informe
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/GlobalActividadesTab.tsx`
> **Tomarla con:** Administrador · **Datos:** Actividades Mock
> **Texto alternativo:** Vista global de actividades

**Resultado de la actividad:** Tiene la vista global de su alcance.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| La descarga del CSV falla | "Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo." | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Filtre antes de descargar. |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

#### Actividad 4 — Consultar las actividades de una recomendación y su detalle

**Objetivo de la actividad:** Que el Administrador pueda leer cada actividad de una recomendación, su estado, su avance y su próximo informe.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| La fecha de notificación es el día 0 del ciclo de informes; el sistema no verifica que sea posterior a la fecha de la alerta. | Revise el estado o el dato en la pantalla antes de actuar | Verificar la fecha contra el documento (Super Administrador o Administrador) | RN-ALE-13 |
| Al aprobar un informe, el próximo informe es la fecha de notificación de la alerta + 6 meses (primer informe) o el anterior + 6 meses. | Revise el estado o el dato en la pantalla antes de actuar | — (Sistema) | RN-SEG-06 |
| Cada día a las 00:01, si el próximo informe de una actividad venció y la alerta no está cerrada, la actividad vuelve a "Sin Informe" y su Número de actividades se suma otra vez a lo programado. | Revise el estado o el dato en la pantalla antes de actuar | Reportar el informe del nuevo ciclo (Entidad Territorial) | RN-TAR-01 |

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** (`/planes-de-accion/:id/recomendaciones/:recomendacionId/actividades`); el detalle, en la tabla de recomendaciones › ícono de detalle › pestaña **Actividades**.

**Qué ve:** La tabla de actividades, "Buscar por objetivo", **Filtros** (Estado, Instrumento de Planeación, Recursos), **Descargar** y **Agregar actividad** (deshabilitado para su rol).

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

El ícono de detalle de la recomendación abre una ventana con las pestañas Información, Actividades e Historial; la pestaña **Actividades** muestra con "Seleccionar actividad", los campos de la actividad (Número de actividades, Plazo, Instrumento de planeación, Capacidades o recursos), el Estado Informe, la Ejecución, el Próximo Informe y la sección "Informes de ejecución". Cuando la alerta está cerrada, la columna de acciones no se muestra.

**Pasos:**

##### Paso 4.1 — Abrir las actividades
**Objetivo del paso:** Ver la lista.
**Qué hacer:** Haga clic en **Ver Actividades** de la recomendación.
**Resultado esperado:** Aparece "Cargando actividades..." y luego la tabla.

##### Paso 4.2 — Buscar y filtrar
**Objetivo del paso:** Encontrar una actividad.
**Qué hacer:** Escriba en "Buscar por objetivo" o use **Filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 4.3 — Ver el detalle
**Objetivo del paso:** Leer la actividad completa.
**Qué hacer:** Vuelva a la tabla de recomendaciones, haga clic en el ícono de detalle de la recomendación y abra la pestaña **Actividades**.
**Resultado esperado:** Ve el detalle de la actividad; con varias actividades puede cambiar con "Seleccionar actividad".

##### Paso 4.4 — Descargar
**Objetivo del paso:** Tener las actividades en un archivo.
**Qué hacer:** Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV de actividades.

> 📷 **[CAPTURA MED-02-PLA-05]** — Actividades de una recomendación
> **Debe mostrar:** La tabla de actividades vista por un usuario Administrador
> **Resaltar:** Columnas Estado, Estado Informe, Próximo Informe
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx`
> **Tomarla con:** Administrador · **Datos:** Actividades Mock
> **Texto alternativo:** Listado de actividades de una recomendación

**Resultado de la actividad:** Conoce el detalle y el avance de las actividades.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Las actividades no cargan o no se eliminan | "Error al cargar las actividades" / "Error al eliminar la actividad" | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |
| Buscar el botón **Agregar actividad** | Botón deshabilitado con "Solo las entidades territoriales pueden agregar actividades" o "No tienes permisos para agregar actividades" | Su rol no formula actividades en la pantalla. | Las actividades las registra la Entidad Territorial responsable de la recomendación. | — |

> 📷 **[CAPTURA MED-02-PLA-06]** — Mensaje ERR-PLA-06
> **Debe mostrar:** La pantalla con el mensaje Botón deshabilitado con "Solo las entidades territoriales pueden agregar actividades" o "No tienes permisos para agregar actividades"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:174-180`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar el botón **Agregar actividad**

**⚠️ Atención:**
- Su rol no ve la columna de acciones de esta tabla: el detalle se consulta desde la recomendación.

#### Actividad 5 — Consultar los informes de ejecución de una actividad y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda leer los informes reportados de una actividad, con todos sus campos y su archivo.

**Cuándo se hace y requisitos previos:** Secuencia E5. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Planes de acción › **Ir al plan de acción** › ícono de detalle de la recomendación › pestaña **Actividades** › sección **Informes de ejecución**.

**Qué ve:** Cada informe muestra su estado y: Actividades ejecutadas, Fecha de inicio, Fecha final, Total de días, Actividad implementada ("Acciones desarrolladas en cumplimiento de la recomendación."), Acciones complementarias, Acciones de coordinación, Buenas prácticas, Instrumento de planeación, Resultados, Dificultades y Adjuntos ("Informe.pdf"). Sin informes: "No hay informes de ejecución registrados para esta actividad."

**Pasos:**

##### Paso 5.1 — Abrir el detalle de la actividad
**Objetivo del paso:** Llegar a los informes.
**Qué hacer:** En la tabla de recomendaciones haga clic en el ícono de detalle y abra la pestaña **Actividades**.
**Resultado esperado:** Ve el detalle de la actividad.

##### Paso 5.2 — Leer los informes
**Objetivo del paso:** Conocer lo reportado.
**Qué hacer:** Baje a "Informes de ejecución" y lea cada informe.
**Resultado esperado:** Ve los datos y el estado de cada informe.

##### Paso 5.3 — Descargar el PDF
**Objetivo del paso:** Revisar el soporte.
**Qué hacer:** Haga clic en "Informe.pdf".
**Resultado esperado:** Se descarga el archivo; sin archivo: "No hay archivos adjuntos".

> 📷 **[CAPTURA MED-02-PLA-07]** — Informes de ejecución
> **Debe mostrar:** La sección Informes de ejecución del detalle de una actividad
> **Resaltar:** Total de días; Informe.pdf
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:523-795`
> **Tomarla con:** Administrador · **Datos:** Informe Mock
> **Texto alternativo:** Informes de ejecución de una actividad

**Resultado de la actividad:** Conoce los informes de la actividad y su soporte.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

### Módulo 07 — Seguimiento

**Prerrequisitos:** Módulo 04; que la Entidad Territorial haya registrado actividades (RN-PLA-01) para revisar, o informes (RN-PLA-07) para aprobar.

**Definición del módulo:** Módulo "Seguimiento de Planes": usa las mismas pantallas de Planes de acción en modo de seguimiento. Allí el Monitor, el Líder de Macrozona y el Super Administrador revisan las actividades (comentarios y "Marcar como Revisado"), las aprueban o descartan su aprobación, confirman el plan de acción de la alerta y aprueban los informes de ejecución. Los demás roles con acceso solo consultan.

**Objetivo del módulo:** Que el Administrador pueda consultar el listado de Seguimiento y encontrar lo pendiente; consultar recomendaciones, actividades e informes en Seguimiento.

**Contexto del módulo:** Corresponde a E4 (E4.1 revisión, E4.2 aprobación, E4.3 confirmación) y a E5.3 (aprobación de informes). Recibe las actividades formuladas en *Planes de acción* (E3.2) y los informes reportados (E5.1). Entrega el plan confirmado, que habilita los informes de ejecución y envía el correo de validación a las entidades, y los informes aprobados, que fijan la fecha del próximo informe. Las aprobaciones solo se pueden hacer desde este módulo. Para el Administrador: ve los planes de todas las alertas del país, sin filtro. En total, tiene 4 de las 10 funcionalidades del módulo; no tiene: marcar una actividad como revisada, aprobar una actividad, descartar la aprobación de una actividad, validar si el plan se puede confirmar, confirmar el plan de acción, aprobar un informe de ejecución.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los planes en Seguimiento (F-SEG-01) | Pantalla "Seguimiento de Planes": por alerta muestra Ejecutado vs programado, Plan de acción e Informe, y la acción para confirmar el plan. | R | Módulo 07 — Actividad 1 |
| Buscar y filtrar planes en Seguimiento (F-SEG-02) | Filtra por Estado del Plan de Acción, Estado del Informe y Porcentaje de Cumplimiento. | R | Módulo 07 — Actividad 1 |
| Descargar el listado de Seguimiento (CSV) (F-SEG-03) | Descarga el listado de planes visible. | Archivo | Módulo 07 — Actividad 1 |
| Consultar recomendaciones, actividades e informes en Seguimiento (F-SEG-04) | Recorre alerta › recomendaciones › actividades en modo seguimiento, con el panel "Información Actividades" y los "Informes de ejecución". | R | Módulo 07 — Actividad 2 |
| Abrir un nuevo ciclo de informe al vencer el próximo informe (F-TAR-01, módulo Tareas programadas) | Cada día a las 00:01 las actividades con "Próximo Informe" vencido vuelven a "Sin Informe" y su meta se suma de nuevo a lo programado. | Automática | Módulo 07 — Actividad 2 |
| Recalcular estados y porcentajes de cumplimiento (F-TAR-03, módulo Tareas programadas) | Después de cada cambio en actividades e informes, el sistema recalcula el estado de la recomendación y del plan y los contadores de programado, ejecutado y % de cumplimiento. | Automática | Módulo 07 — Actividad 2 |
| Calcular el próximo informe al aprobar un informe (F-TAR-04, módulo Tareas programadas) | Al aprobar un informe, el próximo informe es la fecha de notificación + 6 meses (primer informe) o el anterior + 6 meses. | Automática | Módulo 07 — Actividad 2 |

#### Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente

**Objetivo de la actividad:** Que el Administrador pueda ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Seguimiento** (`/seguimiento`) — pantalla "Seguimiento de Planes".

**Qué ve:** "Seguimiento de Planes — Monitorea de manera organizada y eficiente todas las actividades asociadas a las recomendaciones", el botón **Informe** y las pestañas **Alertas**, **Recomendaciones** y **Actividades**, con las mismas columnas y filtros de Planes de acción y, en cada alerta, la acción **Confirmar Plan de Acción** (deshabilitada para su rol: "No tienes permisos para confirmar planes de acción").

Estados del **Plan de acción**: "Sin recomendaciones", "Sin plan" (recomendaciones sin actividades), "Pendiente" (hay actividades por aprobar), "Aprobado" (todas aprobadas; listo para confirmar), "Cerrado" (alerta cerrada). Estados del **Informe**: "Sin Informe", "Sin Completar", "Pendiente", "Aprobado", "Completado", "Cerrado".

Ve los planes de nacional.

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

> 📷 **[CAPTURA MED-02-SEG-01]** — Seguimiento de Planes
> **Debe mostrar:** La pantalla Seguimiento de Planes de un usuario Administrador con el filtro de plan Pendiente
> **Resaltar:** Filtros; columna Plan de acción; acción Confirmar Plan de Acción
> **Pantalla / ruta:** `/seguimiento`
> **Tomarla con:** Administrador · **Datos:** Planes Mock
> **Texto alternativo:** Listado de seguimiento de planes de acción

**Resultado de la actividad:** Sabe qué planes, actividades e informes requieren atención.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de aprobar o confirmar | Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado** | Su rol solo consulta en Seguimiento. | La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-SEG-02]** — Mensaje ERR-SEG-07
> **Debe mostrar:** La pantalla con el mensaje Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado**
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:75-79,331`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de aprobar o confirmar

**⚠️ Atención:**
- Su rol solo consulta en Seguimiento.

#### Actividad 2 — Consultar recomendaciones, actividades e informes en Seguimiento

**Objetivo de la actividad:** Que el Administrador pueda leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución.

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

> 📷 **[CAPTURA MED-02-SEG-03]** — Detalle de Actividad en Seguimiento
> **Debe mostrar:** El detalle de una actividad visto por un usuario Administrador
> **Resaltar:** Ícono Ver detalle; Informes de ejecución
> **Pantalla / ruta:** `dashboard/src/components/planes-de-accion/ActividadDetailModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Actividad Mock
> **Texto alternativo:** Detalle de actividad en Seguimiento

**Resultado de la actividad:** Conoce el estado de las actividades y sus informes.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir un registro que ya no existe o fue eliminado | "El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose." | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | No use enlaces antiguos guardados en el navegador. |

**⚠️ Atención:**
- La pantalla no le muestra los comentarios de las actividades ni le permite comentar (el botón **Comentarios** solo aparece a quien formula o aprueba).

### Módulo 08 — Informe de recomendaciones

**Prerrequisitos:** Módulo 07.

**Definición del módulo:** Tablero "Informe de recomendaciones — Tablero de seguimiento a las recomendaciones", que se abre con el botón **Informe** de Planes de acción o de Seguimiento. Consolida la información de alertas (total, activas, cerradas), recomendaciones (total, % de cumplimiento, sin actividades, pendientes de aprobación), actividades (total, % de cumplimiento, sin informe) y el cumplimiento por Entidad Principal y por Eje Temático, con filtro por alerta.

**Objetivo del módulo:** Que el Administrador pueda consultar el Informe de recomendaciones.

**Contexto del módulo:** Se consulta durante la formulación, la aprobación y la ejecución (E3–E5). Recibe los datos de recomendaciones, actividades e informes. El servidor solo responde a Super Administrador, Administrador, Líder de Macrozona y Monitor; a los demás roles el botón se les muestra, pero el tablero responde con error de permisos. Para el Administrador: en total, tiene 2 de las 2 funcionalidades del módulo.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Consultar el Informe de recomendaciones (F-IRE-01) | Tablero con Información alertas, Información recomendaciones, Información actividades y Cumplimiento por Entidad Principal y por Eje Temático. | R | Módulo 08 — Actividad 1 |
| Filtrar el Informe de recomendaciones por alerta (F-IRE-02) | Cambia el consolidado de "Todas las alertas" a una alerta. | R | Módulo 08 — Actividad 1 |

#### Actividad 1 — Consultar el Informe de recomendaciones

**Objetivo de la actividad:** Que el Administrador pueda leer el avance consolidado de alertas, recomendaciones y actividades, y el cumplimiento por Entidad Principal y por Eje temático.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El Informe de recomendaciones y el módulo Reportes solo responden a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el consolidado a esos roles (Monitor, Líder de Macrozona o Administrador) | RN-IRE-01 |

**Dónde:** Planes de acción o Seguimiento › botón **Informe** (`/planes-de-accion/informe-recomendaciones` o `/seguimiento/informe-recomendaciones`).

**Qué ve:** "Informe de recomendaciones — Tablero de seguimiento a las recomendaciones" con tres bloques:

| Bloque | Indicadores |
|---|---|
| Información alertas | Total de alertas, Alertas activas, Alertas cerradas |
| Información recomendaciones | Total recomendaciones, Cumplimiento (%), Sin actividades, Pendiente de aprobación (filtro "Todas las alertas") |
| Información actividades | Total actividades, Cumplimiento (%), Sin informe |

Y la tabla **Cumplimiento** con las vistas **Entidad** y **Eje tematico** ("{N} Entidades" / "{N} Ejes temáticos"):

| Columna | Descripción |
|---|---|
| Entidad Principal / Eje Temático | Agrupación |
| Alertas | Alertas con recomendaciones de esa entidad o eje |
| Recomendaciones | Número de recomendaciones |
| Actividades | Número de actividades |
| Ejecutado vs programado | Actividades ejecutadas frente a programadas |
| % Avance | Ejecutado ÷ programado |

**Pasos:**

##### Paso 1.1 — Abrir el informe
**Objetivo del paso:** Ver el consolidado.
**Qué hacer:** En Planes de acción o en Seguimiento haga clic en **Informe**.
**Resultado esperado:** Aparece el tablero con los tres bloques.

##### Paso 1.2 — Filtrar por alerta
**Objetivo del paso:** Ver el consolidado de una alerta.
**Qué hacer:** En "Todas las alertas" elija una alerta.
**Resultado esperado:** Los bloques y la tabla se recalculan para esa alerta.

##### Paso 1.3 — Comparar por entidad y por eje
**Objetivo del paso:** Identificar rezagos.
**Qué hacer:** Cambie entre **Entidad** y **Eje tematico** y ordene mentalmente por % Avance.
**Resultado esperado:** Identifica las entidades o ejes con menor avance.

> 📷 **[CAPTURA MED-02-IRE-01]** — Informe de recomendaciones
> **Debe mostrar:** El tablero con los tres bloques y la tabla por Entidad
> **Resaltar:** Filtro Todas las alertas; vistas Entidad / Eje tematico; % Avance
> **Pantalla / ruta:** `dashboard/src/pages/InformeRecomendaciones.tsx`
> **Tomarla con:** Administrador · **Datos:** Datos Mock
> **Texto alternativo:** Tablero del informe de recomendaciones

**Resultado de la actividad:** Conoce el avance consolidado de las recomendaciones.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| El servidor falla al procesar la solicitud | "Error interno del servidor. Por favor, intenta más tarde." o "Error en el servicio — La plataforma presentó un inconveniente al procesar tu solicitud. Estamos trabajando para solucionarlo. Por favor, intenta nuevamente en unos minutos." | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | — |

**Ejemplo:** Si una entidad tiene 2 recomendaciones con 10 actividades programadas y 4 ejecutadas, su fila muestra "4 / 10" y % Avance 40 %.

### Módulo 09 — Reportes

**Prerrequisitos:** Módulo 07; para que el reporte tenga sentido, informes de ejecución aprobados.

**Definición del módulo:** Módulo "Reportes de ejecución": publica reportes de ejecución consolidados por alerta, entidad, departamento o municipio, con su PDF y un aprobador designado; permite listarlos por pestañas (Todos, Alerta, Entidad, Regional), filtrarlos, ver su detalle, descargarlos, editarlos, eliminarlos y aprobarlos. Incluye el **Panel de consultas**, que genera y descarga informes ejecutivos en Word por alerta, entidad, departamento, municipio o general.

**Objetivo del módulo:** Que el Administrador pueda consultar, buscar y filtrar los reportes de ejecución; ver el detalle de un reporte y descargarlo; cargar un reporte de ejecución; editar un reporte de ejecución; generar un informe ejecutivo en Word (Panel de consultas).

**Contexto del módulo:** Corresponde a E5.6-E5.8, después de que los informes de ejecución se aprueban. Recibe los datos de alertas, entidades, actividades e informes. Entrega un reporte que el aprobador designado (Líder de Macrozona o Super Administrador) aprueba, y documentos Word descargables. Lo usan Super Administrador, Administrador, Líder de Macrozona y Monitor; la Entidad Territorial y los roles de Consulta no tienen acceso. Para el Administrador: ve los reportes de ejecución de todo el país. En total, tiene 7 de las 9 funcionalidades del módulo; no tiene: eliminar un reporte de ejecución, aprobar un reporte de ejecución.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los reportes de ejecución (F-REP-01) | Pantalla "Reportes de ejecución" con las pestañas Todos, Alerta, Entidad y Regional y la tabla Informe, Tipo, Publicado, Estado y Aprobador. | R | Módulo 09 — Actividad 1 |
| Buscar y filtrar reportes (F-REP-02) | Busca por nombre y filtra por Tipo, Estado, Alerta asociada, Entidad, Departamento y Municipio. | R | Módulo 09 — Actividad 1 |
| Ver el detalle de un reporte (F-REP-03) | Muestra Nombre del reporte, Etiqueta (tipo), Fecha de publicacion, Estado, Descripcion, Adjunto y Aprobador. | R | Módulo 09 — Actividad 2 |
| Descargar un reporte (F-REP-04) | Descarga el PDF del reporte. | Archivo | Módulo 09 — Actividad 2 |
| Cargar un reporte de ejecución (F-REP-05) | Registra el tipo (Alerta, Entidad, Depto, Municipio), su alcance, la fecha, el aprobador, la descripción y el PDF. | C | Módulo 09 — Actividad 3 |
| Editar un reporte de ejecución (F-REP-06) | Modifica los datos o el PDF del reporte desde su detalle. | U | Módulo 09 — Actividad 4 |
| Generar un informe ejecutivo en Word (Panel de consultas) (F-REP-09) | Genera y descarga un documento Word por Alerta, Entidad, Depto, Municipio o General. | Archivo | Módulo 09 — Actividad 5 |

#### Actividad 1 — Consultar, buscar y filtrar los reportes de ejecución

**Objetivo de la actividad:** Que el Administrador pueda encontrar los reportes de ejecución publicados, su tipo, su estado y su aprobador.

**Cuándo se hace y requisitos previos:** Secuencia E5.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El Informe de recomendaciones y el módulo Reportes solo responden a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el consolidado a esos roles (Monitor, Líder de Macrozona o Administrador) | RN-IRE-01 |

**Dónde:** Menú lateral › **Reportes** (`/reportes`).

**Qué ve:** "Reportes de ejecución — Publica los Reportes de ejecución, para que otras entidades puedan acceder a consultar." con las pestañas **Todos**, **Alerta**, **Entidad** y **Regional** (Regional = departamental y municipal), los botones **Consultas** y **Cargar informe**, "Buscar por nombre" y **Filtros**.

| Columna | Descripción |
|---|---|
| Informe | Nombre del reporte (alerta, entidad, departamento o municipio) |
| Tipo | Alerta, Entidad, Depto, Municipio |
| Publicado | Fecha del reporte |
| Estado | Sin aprobación o Aprobado |
| Aprobador | Usuario designado |
| Acciones | Ver detalles, Descargar reporte, Eliminar reporte |

Filtros: **Tipo** ("Todos los tipos"), **Estado** ("Todos los estados"), **Alerta asociada**, **Entidad**, **Departamento** y **Municipio** ("Seleccione un departamento para filtrar por municipio").

**Pasos:**

##### Paso 1.1 — Abrir Reportes
**Objetivo del paso:** Ver los reportes.
**Qué hacer:** Haga clic en **Reportes**.
**Resultado esperado:** Aparece "Cargando reportes..." y luego la tabla.

##### Paso 1.2 — Cambiar de pestaña
**Objetivo del paso:** Ver un tipo de reporte.
**Qué hacer:** Haga clic en **Alerta**, **Entidad** o **Regional**.
**Resultado esperado:** La tabla muestra ese tipo.

##### Paso 1.3 — Filtrar
**Objetivo del paso:** Encontrar un reporte.
**Qué hacer:** Use "Buscar por nombre" o **Filtros** › **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra; sin datos: "No hay reportes de ejecucion".

> 📷 **[CAPTURA MED-02-REP-01]** — Reportes de ejecución
> **Debe mostrar:** La tabla de reportes con las pestañas
> **Resaltar:** Pestañas Todos/Alerta/Entidad/Regional; columnas Estado y Aprobador
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ReportesEjecucionTab.tsx`
> **Tomarla con:** Administrador · **Datos:** Reportes Mock
> **Texto alternativo:** Listado de reportes de ejecución

**Resultado de la actividad:** Ubica los reportes y su estado.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Los reportes no cargan | "Error al cargar reportes — No se pudieron cargar los reportes de ejecución. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-REP-02]** — Mensaje ERR-REP-10
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar reportes — No se pudieron cargar los reportes de ejecución. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/Reportes.tsx:107-109`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los reportes no cargan

#### Actividad 2 — Ver el detalle de un reporte y descargarlo

**Objetivo de la actividad:** Que el Administrador pueda leer un reporte de ejecución y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E5.6. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Reportes › fila › **Ver detalles** / **Descargar reporte**.

**Qué ve:** El detalle con "Fecha de publicacion", **Nombre del reporte**, **Etiqueta** (tipo), **Estado**, **Descripcion**, **Adjunto** ("No hay archivo adjunto" si falta) y **Aprobador** ("Sin aprobador"); botones **Cerrar**, **Editar** y, si corresponde, **Aprobar informe**.

**Pasos:**

##### Paso 2.1 — Abrir el detalle
**Objetivo del paso:** Leer el reporte.
**Qué hacer:** Haga clic en **Ver detalles**.
**Resultado esperado:** Se abre el detalle.

##### Paso 2.2 — Descargar
**Objetivo del paso:** Obtener el PDF.
**Qué hacer:** Haga clic en **Descargar reporte** en la fila (o en el adjunto del detalle).
**Resultado esperado:** Se descarga el PDF; sin archivo: "No hay archivo disponible".

> 📷 **[CAPTURA MED-02-REP-03]** — Detalle del reporte
> **Debe mostrar:** El detalle de un reporte de tipo Alerta
> **Resaltar:** Aprobador; Adjunto
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ReporteDetailModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Reporte Mock
> **Texto alternativo:** Detalle de un reporte de ejecución

**Resultado de la actividad:** Conoce el reporte y tiene su archivo.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Descargar un reporte sin archivo | "No hay archivo disponible" / "Sin archivo" / "Error al descargar el reporte. Por favor, intenta de nuevo." | El reporte no tiene PDF o la descarga falló. | Pida al autor que edite el reporte y adjunte el PDF. | — |
| Buscar la opción de eliminar un reporte | Botón deshabilitado con "No tienes permisos para eliminar reportes" | En la pantalla solo el Super Administrador elimina reportes. | Pida la eliminación al Super Administrador. | — |

> 📷 **[CAPTURA MED-02-REP-04]** — Mensaje ERR-REP-08
> **Debe mostrar:** La pantalla con el mensaje "No hay archivo disponible" / "Sin archivo" / "Error al descargar el reporte. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ReportesEjecucionTab.tsx:256,322`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Descargar un reporte sin archivo

> 📷 **[CAPTURA MED-02-REP-05]** — Mensaje ERR-REP-06
> **Debe mostrar:** La pantalla con el mensaje Botón deshabilitado con "No tienes permisos para eliminar reportes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ReportesEjecucionTab.tsx:52-53,329-340`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar la opción de eliminar un reporte

#### Actividad 3 — Cargar un reporte de ejecución

**Objetivo de la actividad:** Que el Administrador pueda publicar un reporte de ejecución consolidado con su PDF y designar a quien lo aprueba.

**Cuándo se hace y requisitos previos:** Secuencia E5.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El tipo es obligatorio y define el dato exigido: Alerta → alerta; Entidad → entidad; Depto → departamento; Municipio → departamento y municipio. También son obligatorios la fecha, el aprobador, la descripción (hasta 2.000 caracteres) y el PDF. | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario según el tipo (Monitor, Líder, Administrador o Super Administrador) | RN-REP-01 |
| El aprobador debe ser un usuario activo con permiso de aprobar reportes (Super Administrador o Líder de Macrozona). | Revise el estado o el dato en la pantalla antes de actuar | Elegir al Líder de Macrozona correspondiente (Quien carga el reporte) | RN-REP-02 |
| El Informe de recomendaciones y el módulo Reportes solo responden a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el consolidado a esos roles (Monitor, Líder de Macrozona o Administrador) | RN-IRE-01 |

**Dónde:** Reportes › **Cargar informe** › ventana "Cargar informe de seguimiento — Reportar Reportes de ejecución para dar visibilidad sobre la ejecución." (el título de la ventana dice "informe de seguimiento", aunque carga un reporte de ejecución).

**Qué ve:** El formulario "Información general" con Tipo, el campo de alcance según el tipo, Fecha de reporte, Aprobador, Descripción y Adjunto; botones **Cancelar** y **Cargar informe**.

**Campos a diligenciar — Cargar reporte de ejecución / Editar reporte:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Tipo (`tipo`) | Sí | Lista de selección única | — | Alerta, Entidad, Depto, Municipio | Define el campo de alcance que aparece | Alerta | "El tipo de reporte es requerido" |
| 2 | Alerta (`alerta_id`) | Condicional: Tipo = Alerta | Lista con búsqueda | Alerta existente | Alertas | Tipo | AT-013-2025 [DATO REAL AT-013-25] | "Debe seleccionar una alerta" |
| 3 | Entidad (`entidad_id`) | Condicional: Tipo = Entidad | Lista con búsqueda | Entidad existente | Entidades | Tipo | Gobernación de Prueba | "Debe seleccionar una entidad" |
| 4 | Departamento (`departamento`) | Condicional: Tipo = Depto o Municipio | Lista con búsqueda | — | Departamentos | Tipo; filtra Municipio | CAUCA | "Debe seleccionar un departamento" |
| 5 | Municipio (`municipio`) | Condicional: Tipo = Municipio | Lista con búsqueda (dependiente) | — | Municipios del departamento | Departamento | Popayán | "Debe seleccionar un municipio" |
| 6 | Fecha de reporte (`fecha_reporte`) | Sí | Fecha | Fecha válida | — | — | 15/07/2026 | "La fecha del reporte es requerida" / "La fecha del reporte no tiene un formato válido" |
| 7 | Aprobador (`aprobador_id`) | Sí | Lista con búsqueda de usuarios | Usuario activo Super Administrador o Líder de Macrozona | Aprobadores (`/reportes-ejecucion/aprobadores`) | — | Líder de Macrozona de prueba | "El aprobador es requerido" / "El aprobador especificado no existe" |
| 8 | Descripción (`descripcion`) | Sí | Área de texto | Máx. 2.000 caracteres | — | — | Consolidado del primer semestre (dato ficticio) | "La descripción es requerida" / "La descripción no puede exceder 2000 caracteres" |
| 9 | Adjunto (`archivo`) | Sí al crear | Archivo | PDF ≤ 20 MB | — | — | IES-AT-901-2026-20260715.pdf | "El archivo PDF es requerido" |

- Campos que llena el sistema: Estado "Sin aprobación", creador y fecha; correo al aprobador. El nombre del archivo se arma como IES-{alerta|entidad|DPTO|MPIO}-{fecha}.pdf.
- Campos que se bloquean: El servidor no impide editar un reporte aprobado.
- Archivos: "Adjunto": PDF obligatorio al crear (o si el reporte no tiene archivo), hasta 20 MB.
- Guardar o enviar con: **Cargar informe** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 3.1 — Abrir el formulario
**Objetivo del paso:** Iniciar la carga.
**Qué hacer:** Haga clic en **Cargar informe**.
**Resultado esperado:** Se abre la ventana.

##### Paso 3.2 — Elegir el tipo
**Objetivo del paso:** Definir qué consolida el reporte.
**Qué hacer:** Despliegue **Tipo** y elija Alerta, Entidad, Depto o Municipio.
**Resultado esperado:** Aparece el campo de alcance correspondiente.

##### Paso 3.3 — Elegir el alcance
**Objetivo del paso:** Indicar la alerta, entidad o territorio.
**Qué hacer:** Según el tipo: busque la **Alerta**; o la **Entidad**; o el **Departamento**; o el Departamento y el **Municipio**.
**Resultado esperado:** Si falta: "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento" o "Debe seleccionar un municipio".

##### Paso 3.4 — Elegir la fecha y el aprobador
**Objetivo del paso:** Fechar el reporte y designar quién aprueba.
**Qué hacer:** Elija la **Fecha de reporte** y en **Aprobador** busque ("Buscar por nombre o email...") al Líder de Macrozona (o al Super Administrador) que aprobará.
**Resultado esperado:** Solo aparecen usuarios activos que pueden aprobar.

##### Paso 3.5 — Escribir la descripción
**Objetivo del paso:** Resumir el reporte.
**Qué hacer:** Escriba la **Descripción** (máx. 2.000 caracteres).
**Resultado esperado:** Si excede: "La descripción no puede exceder 2000 caracteres".

##### Paso 3.6 — Adjuntar el PDF
**Objetivo del paso:** Publicar el documento.
**Qué hacer:** En **Adjunto** suba el PDF del reporte.
**Resultado esperado:** Sin archivo: "El archivo PDF es requerido".

##### Paso 3.7 — Cargar
**Objetivo del paso:** Publicar y notificar al aprobador.
**Qué hacer:** Haga clic en **Cargar informe**.
**Resultado esperado:** Aparece "Reporte creado — El reporte de ejecución se ha cargado exitosamente"; el reporte queda "Sin aprobación".

> 🎞️ **[GIF MED-02-REP-06]** — Cargar reporte de ejecución
> **Debe mostrar:** La carga de un reporte de tipo Alerta con aprobador
> **Resaltar:** Tipo; Aprobador; Cargar informe
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/CargarReporteModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Mock
> **Solo para GIF — Secuencia:** 1) Cargar informe 2) Tipo 3) Alerta 4) Fecha y aprobador 5) Descripción y PDF 6) Cargar informe · **Duración aproximada:** 30 segundos
> **Texto alternativo:** Animación de la carga de un reporte de ejecución

**Resultado de la actividad:** El reporte queda "Sin aprobación" y el aprobador recibe "Reporte de ejecución pendiente de su aprobación – SI-CIPRAT".

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Cargar el reporte sin datos | "El tipo de reporte es requerido", "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento", "Debe seleccionar un municipio", "La fecha del reporte es requerida", "La descripción es requerida", "La descripción no puede exceder 2000 caracteres", "El archivo PDF es requerido", "El aprobador es requerido" | Faltan datos según el tipo. | Complete los campos del tipo elegido, el aprobador, la descripción y el PDF. | Elija primero el **Tipo**. |
| El servidor rechaza el reporte | "Para reportes de tipo Alerta, debe especificar una alerta" (y equivalentes), "El aprobador especificado no existe", "La alerta especificada no existe", "La entidad especificada no existe" | Datos inconsistentes con el tipo. | Revise el tipo y el dato correspondiente. | — |
| El PDF del reporte no se sube | "El reporte se creó pero hubo un error al subir el archivo" / "El reporte se actualizó pero hubo un error al subir el archivo" | Falla al subir el archivo después de guardar. | Abra el reporte con **Editar** y vuelva a adjuntar el PDF. | — |
| Seleccionar un archivo que no es PDF | "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF") | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Prepare los soportes en PDF antes de abrir el formulario. |
| Seleccionar un PDF muy pesado | "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB") | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Escanee en resolución media y sin color cuando sea posible. |

> 📷 **[CAPTURA MED-02-REP-07]** — Mensaje ERR-REP-01
> **Debe mostrar:** La pantalla con el mensaje "El tipo de reporte es requerido", "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento", "Debe seleccionar un munic
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/CargarReporteModal.tsx:231-274`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Cargar el reporte sin datos

> 📷 **[CAPTURA MED-02-REP-08]** — Mensaje ERR-REP-02
> **Debe mostrar:** La pantalla con el mensaje "Para reportes de tipo Alerta, debe especificar una alerta" (y equivalentes), "El aprobador especificado no existe", "La alerta especificada no existe", "La ent
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioReportesEjecucion.cs:142-202`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El servidor rechaza el reporte

> 📷 **[CAPTURA MED-02-REP-09]** — Mensaje ERR-REP-07
> **Debe mostrar:** La pantalla con el mensaje "El reporte se creó pero hubo un error al subir el archivo" / "El reporte se actualizó pero hubo un error al subir el archivo"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/CargarReporteModal.tsx:317-321`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El PDF del reporte no se sube

**⚠️ Atención:**
- El tipo "General" solo existe en el Panel de consultas, no al cargar un reporte.

**Ejemplo:** Mock: Tipo Alerta, Alerta AT-901-2026, Fecha 15/07/2026, Aprobador "Líder de Macrozona de prueba", Descripción "Consolidado del primer semestre", Adjunto IES-AT-901-2026-20260715.pdf.

#### Actividad 4 — Editar un reporte de ejecución

**Objetivo de la actividad:** Que el Administrador pueda corregir los datos o el PDF de un reporte de ejecución.

**Cuándo se hace y requisitos previos:** Secuencia E5.6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El tipo es obligatorio y define el dato exigido: Alerta → alerta; Entidad → entidad; Depto → departamento; Municipio → departamento y municipio. También son obligatorios la fecha, el aprobador, la descripción (hasta 2.000 caracteres) y el PDF. | Revise el estado o el dato en la pantalla antes de actuar | Completar el formulario según el tipo (Monitor, Líder, Administrador o Super Administrador) | RN-REP-01 |

**Dónde:** Reportes › **Ver detalles** › **Editar** › ventana "Editar informe de seguimiento — Modifica los datos del reporte de ejecución.".

**Qué ve:** El mismo formulario con los datos del reporte y el botón **Guardar cambios**.

**Campos a diligenciar — Cargar reporte de ejecución / Editar reporte:**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Tipo (`tipo`) | Sí | Lista de selección única | — | Alerta, Entidad, Depto, Municipio | Define el campo de alcance que aparece | Alerta | "El tipo de reporte es requerido" |
| 2 | Alerta (`alerta_id`) | Condicional: Tipo = Alerta | Lista con búsqueda | Alerta existente | Alertas | Tipo | AT-013-2025 [DATO REAL AT-013-25] | "Debe seleccionar una alerta" |
| 3 | Entidad (`entidad_id`) | Condicional: Tipo = Entidad | Lista con búsqueda | Entidad existente | Entidades | Tipo | Gobernación de Prueba | "Debe seleccionar una entidad" |
| 4 | Departamento (`departamento`) | Condicional: Tipo = Depto o Municipio | Lista con búsqueda | — | Departamentos | Tipo; filtra Municipio | CAUCA | "Debe seleccionar un departamento" |
| 5 | Municipio (`municipio`) | Condicional: Tipo = Municipio | Lista con búsqueda (dependiente) | — | Municipios del departamento | Departamento | Popayán | "Debe seleccionar un municipio" |
| 6 | Fecha de reporte (`fecha_reporte`) | Sí | Fecha | Fecha válida | — | — | 15/07/2026 | "La fecha del reporte es requerida" / "La fecha del reporte no tiene un formato válido" |
| 7 | Aprobador (`aprobador_id`) | Sí | Lista con búsqueda de usuarios | Usuario activo Super Administrador o Líder de Macrozona | Aprobadores (`/reportes-ejecucion/aprobadores`) | — | Líder de Macrozona de prueba | "El aprobador es requerido" / "El aprobador especificado no existe" |
| 8 | Descripción (`descripcion`) | Sí | Área de texto | Máx. 2.000 caracteres | — | — | Consolidado del primer semestre (dato ficticio) | "La descripción es requerida" / "La descripción no puede exceder 2000 caracteres" |
| 9 | Adjunto (`archivo`) | Sí al crear | Archivo | PDF ≤ 20 MB | — | — | IES-AT-901-2026-20260715.pdf | "El archivo PDF es requerido" |

- Campos que llena el sistema: Estado "Sin aprobación", creador y fecha; correo al aprobador. El nombre del archivo se arma como IES-{alerta|entidad|DPTO|MPIO}-{fecha}.pdf.
- Campos que se bloquean: El servidor no impide editar un reporte aprobado.
- Archivos: "Adjunto": PDF obligatorio al crear (o si el reporte no tiene archivo), hasta 20 MB.
- Guardar o enviar con: **Cargar informe** (edición: **Guardar cambios**).

**Pasos:**

##### Paso 4.1 — Abrir la edición
**Objetivo del paso:** Cargar el reporte.
**Qué hacer:** Abra **Ver detalles** y haga clic en **Editar**.
**Resultado esperado:** Se abre el formulario con los datos.

##### Paso 4.2 — Corregir
**Objetivo del paso:** Ajustar el reporte.
**Qué hacer:** Modifique Tipo, Alerta, Entidad, Departamento, Municipio, Fecha de reporte, Aprobador, Descripción o Adjunto.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 4.3 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Reporte actualizado — El reporte de ejecución se ha actualizado exitosamente".

> 📷 **[CAPTURA MED-02-REP-10]** — Editar reporte
> **Debe mostrar:** El formulario de edición de un reporte
> **Resaltar:** Guardar cambios
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/CargarReporteModal.tsx:413-418`
> **Tomarla con:** Administrador · **Datos:** Reporte Mock
> **Texto alternativo:** Edición de un reporte de ejecución

**Resultado de la actividad:** El reporte queda actualizado.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Cargar el reporte sin datos | "El tipo de reporte es requerido", "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento", "Debe seleccionar un municipio", "La fecha del reporte es requerida", "La descripción es requerida", "La descripción no puede exceder 2000 caracteres", "El archivo PDF es requerido", "El aprobador es requerido" | Faltan datos según el tipo. | Complete los campos del tipo elegido, el aprobador, la descripción y el PDF. | Elija primero el **Tipo**. |
| El servidor rechaza el reporte | "Para reportes de tipo Alerta, debe especificar una alerta" (y equivalentes), "El aprobador especificado no existe", "La alerta especificada no existe", "La entidad especificada no existe" | Datos inconsistentes con el tipo. | Revise el tipo y el dato correspondiente. | — |
| El PDF del reporte no se sube | "El reporte se creó pero hubo un error al subir el archivo" / "El reporte se actualizó pero hubo un error al subir el archivo" | Falla al subir el archivo después de guardar. | Abra el reporte con **Editar** y vuelva a adjuntar el PDF. | — |

**⚠️ Atención:**
- ⚠️ El sistema permite editar incluso un reporte ya aprobado: si lo hace, informe al aprobador.

#### Actividad 5 — Generar un informe ejecutivo en Word (Panel de consultas)

**Objetivo de la actividad:** Que el Administrador pueda descargar un informe ejecutivo en Word por alerta, entidad, departamento, municipio o general.

**Cuándo se hace y requisitos previos:** Secuencia E5.8.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Para generar una consulta, el tipo es obligatorio y debe elegirse su alerta, entidad, departamento o municipio. | Revise el estado o el dato en la pantalla antes de actuar | Completar el Panel de consultas (Quien consulta) | RN-REP-05 |
| El Informe de recomendaciones y el módulo Reportes solo responden a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Revise el estado o el dato en la pantalla antes de actuar | Pedir el consolidado a esos roles (Monitor, Líder de Macrozona o Administrador) | RN-IRE-01 |

**Dónde:** Reportes › **Consultas** › "Panel de consultas — Descarga informes sobre el seguimiento y ejecucion".

**Qué ve:** El formulario "Informacion general" con el texto "La consulta generara un PDF con los datos obtenidos", el Tipo de consulta y su campo de alcance, y el botón **Generar consulta** ("Generando...").

**Campos a diligenciar — Panel de consultas (informe ejecutivo):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Tipo de consulta (`tipo`) | Sí | Lista de selección única | — | Alerta, Entidad, Depto, Municipio, General | Define el campo de alcance | Alerta | "El tipo de consulta es requerido" |
| 2 | Alerta (`alerta_id`) | Condicional: Tipo = Alerta | Lista con búsqueda | — | Alertas | Tipo | AT-013-2025 [DATO REAL AT-013-25] | "Debe seleccionar una alerta" |
| 3 | Entidad (`entidad_id`) | Condicional: Tipo = Entidad | Lista con búsqueda | — | Entidades | Tipo | Gobernación de Prueba | "Debe seleccionar una entidad" |
| 4 | Departamento (`departamento`) | Condicional: Tipo = Depto o Municipio | Lista con búsqueda | — | Departamentos | Tipo | CAUCA | "Debe seleccionar un departamento" |
| 5 | Municipio (`municipio`) | Condicional: Tipo = Municipio | Lista con búsqueda (dependiente) | — | Municipios | Departamento | Popayán | "Debe seleccionar un municipio" |

- Campos que llena el sistema: El documento Word se descarga ("Informe generado — El documento Word se ha descargado exitosamente").
- Campos que se bloquean: —
- Archivos: Genera un .docx (la ayuda de la ventana dice "La consulta generara un PDF").
- Guardar o enviar con: **Generar consulta**.

**Pasos:**

##### Paso 5.1 — Abrir el Panel de consultas
**Objetivo del paso:** Iniciar la consulta.
**Qué hacer:** Haga clic en **Consultas**.
**Resultado esperado:** Se abre "Panel de consultas".

##### Paso 5.2 — Elegir el tipo y el alcance
**Objetivo del paso:** Definir el informe.
**Qué hacer:** Elija **Tipo de consulta** (Alerta, Entidad, Depto, Municipio o General) y su **Alerta**, **Entidad**, **Departamento** o **Municipio**.
**Resultado esperado:** Si falta: "El tipo de consulta es requerido" o el mensaje del campo.

##### Paso 5.3 — Generar
**Objetivo del paso:** Descargar el documento.
**Qué hacer:** Haga clic en **Generar consulta**.
**Resultado esperado:** Aparece "Informe generado — El documento Word se ha descargado exitosamente".

> 📷 **[CAPTURA MED-02-REP-11]** — Panel de consultas
> **Debe mostrar:** El panel con Tipo de consulta "Alerta" y una alerta elegida
> **Resaltar:** Generar consulta
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ConsultasModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Alerta Mock
> **Texto alternativo:** Panel de consultas para informes ejecutivos

**Resultado de la actividad:** Tiene el informe ejecutivo en Word con los datos de la alerta, el avance por entidad y las dificultades.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Generar una consulta sin datos | "El tipo de consulta es requerido", "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento", "Debe seleccionar un municipio" / "Error al generar informe" | Faltan datos o falla la generación. | Complete el tipo y su dato y haga clic en **Generar consulta**. | — |

> 📷 **[CAPTURA MED-02-REP-12]** — Mensaje ERR-REP-09
> **Debe mostrar:** La pantalla con el mensaje "El tipo de consulta es requerido", "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento", "Debe seleccionar un muni
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/reportes-ejecucion/ConsultasModal.tsx:154-221`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Generar una consulta sin datos

**⚠️ Atención:**
- El texto de la ventana dice "PDF", pero el archivo que se descarga es un documento Word.
- NO ENCONTRADO un filtro por departamentos del usuario en la generación: el informe se genera para el alcance elegido.

**Ejemplo:** Tipo Alerta, alerta AT-013-2025 [DATO REAL AT-013-25] (Mock: AT-901-2026) → documento Word del informe de la alerta.

### Módulo 10 — Informes de seguimiento

**Prerrequisitos:** Módulo 04 (la alerta debe existir).

**Definición del módulo:** Módulo donde se registran los informes de seguimiento que emite la Defensoría sobre una alerta. Permite listarlos, filtrarlos por alerta, ver su detalle y descargar su PDF; al Super Administrador y al Administrador, cargarlos en 2 pasos (datos del informe; modificaciones a la alerta: cerrar municipios, agregar municipios y recomendaciones) y editarlos; al Super Administrador, eliminarlos y cerrar la alerta con el informe.

**Objetivo del módulo:** Que el Administrador pueda consultar los informes de seguimiento y descargar su PDF; cargar un informe de seguimiento y aplicar sus cambios a la alerta; editar un informe de seguimiento.

**Contexto del módulo:** Ocurre después del registro de la alerta, normalmente hacia el cierre del ciclo (E6.1). Recibe la alerta y sus municipios; puede devolver el ciclo a E2 (nuevas recomendaciones, con correo a las entidades) o cerrar la alerta (E6.3). También llegan informes por X-Road. La Entidad Territorial no tiene este módulo en el menú. Para el Administrador: ve todos los registrados (`main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:266-279`). En total, tiene 7 de las 9 funcionalidades del módulo; no tiene: cerrar la alerta con el informe de seguimiento, eliminar un informe de seguimiento.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los informes de seguimiento (F-ISE-01) | Tabla con Informe, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Módulo 10 — Actividad 1 |
| Buscar y filtrar informes por alerta (F-ISE-02) | Busca por número y filtra por Alerta asociada. | R | Módulo 10 — Actividad 1 |
| Ver el detalle de un informe de seguimiento (F-ISE-03) | Muestra Informacion basica, Detalles del seguimiento y Archivo adjunto. | R | Módulo 10 — Actividad 1 |
| Descargar el PDF del informe de seguimiento (F-ISE-04) | Descarga el archivo del informe. | Archivo | Módulo 10 — Actividad 1 |
| Cargar un informe de seguimiento (F-ISE-05) | Registra en 2 pasos el número, la alerta, las fechas, el radicado y el PDF, y las modificaciones a la alerta. | C | Módulo 10 — Actividad 2 |
| Modificar municipios y agregar recomendaciones desde el informe (F-ISE-06) | En el paso 2 marca municipios como cerrados, agrega municipios y agrega recomendaciones nuevas. | U | Módulo 10 — Actividad 2 |
| Editar un informe de seguimiento (F-ISE-08) | Modifica los datos del informe (la alerta asociada no se cambia). | U | Módulo 10 — Actividad 3 |
| Recibir informes de seguimiento por X-Road (F-INT-02, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía informes de seguimiento, que pueden cerrar la alerta o modificarla. | Automática | Módulo 10 — Actividad 1 |

#### Actividad 1 — Consultar los informes de seguimiento y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1. No hay reglas de negocio que deban cumplirse antes, aparte de tener la sesión abierta.

**Dónde:** Menú lateral › **Informes de seguimiento** ("Encuentra los informes de seguimiento publicados por la defensoría").

**Qué ve:** La sección "Informes" con el botón **Cargar informe**, "Buscar por nombre" y **Filtros** (Alerta asociada: "Todas las alertas").

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

> 📷 **[CAPTURA MED-02-ISE-01]** — Informes de seguimiento
> **Debe mostrar:** La tabla de informes y el panel de detalle abierto
> **Resaltar:** Detalles del seguimiento; Descargar
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformeSeguimientoDetailPanel.tsx`
> **Tomarla con:** Administrador · **Datos:** Informe Mock
> **Texto alternativo:** Informes de seguimiento y su detalle

**Resultado de la actividad:** Conoce los informes de seguimiento.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de cargar, editar o eliminar informes | Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes" | Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. | Pida la carga a la Secretaría Técnica. | — |
| Los informes no cargan | "Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo." | Falla del servicio. | Recargue la página. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-ISE-02]** — Mensaje ERR-ISE-07
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:49-52,121,261,288`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de cargar, editar o eliminar informes

> 📷 **[CAPTURA MED-02-ISE-03]** — Mensaje ERR-ISE-09
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/InformesDeSeguimiento.tsx:76-77`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los informes no cargan

**⚠️ Atención:**
- Ve todos los informes registrados.
- El filtro "Alerta asociada" solo ofrece alertas cerradas.

#### Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta

**Objetivo de la actividad:** Que el Administrador pueda registrar un informe de seguimiento de la Defensoría con su PDF y aplicar sus efectos: cerrar o agregar municipios, agregar recomendaciones o cerrar la alerta.

**Cuándo se hace y requisitos previos:** Secuencia E6.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El número de informe es obligatorio (hasta 500 caracteres) y único; la alerta y la fecha de notificación son obligatorias y el PDF es obligatorio en pantalla. | Revise el estado o el dato en la pantalla antes de actuar | Tomar los datos del documento de la Defensoría (Super Administrador o Administrador) | RN-ISE-01 |
| No se agregan ni modifican municipios ni recomendaciones en una alerta cerrada. | Revise el estado o el dato en la pantalla antes de actuar | Registrar solo los datos del informe (Super Administrador o Administrador) | RN-ISE-02 |
| Cerrar la alerta con un informe exige el permiso de cerrar alertas (solo Super Administrador). | Revise el estado o el dato en la pantalla antes de actuar | Pedir el cierre al Super Administrador (Super Administrador) | RN-ISE-03 |
| La Entidad Principal debe existir y estar activa. | Revise el estado o el dato en la pantalla antes de actuar | Crear o activar la entidad en Usuarios y entidades (Super Administrador o Administrador) | RN-REC-04 |

**Dónde:** Informes de seguimiento › **Cargar informe** › ventana "Cargar informe de seguimiento — Registra un nuevo informe de seguimiento para una alerta.".

**Qué ve:** Un asistente de 2 pasos: 1 Información del informe y 2 Modificaciones a la alerta (Municipios actuales de la alerta, Agregar nuevos municipios, Recomendaciones, Cerrar la alerta con este informe). Botones **Atrás**, **Siguiente** y **Cargar informe**.

**Campos a diligenciar — Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Número de informe (`numero_informe`) | Sí | Texto | Máx. 500; único | — | — | IS-901-26 | "El número de informe es requerido" / "El número de informe no puede exceder 500 caracteres" / "Ya existe un informe con el número '…'" |
| 2 | Alerta asociada (`alerta_id`) | Sí | Lista con búsqueda | Alerta existente | Alertas | Carga los municipios del Paso 2 | AT-013-2025 [DATO REAL AT-013-25] | "Debe seleccionar una alerta" / "La alerta asociada no puede ser modificada" |
| 3 | Fecha de notificación (`fecha_notificacion`) | Sí | Fecha | — | — | — | 30/06/2026 | "La fecha de notificación es requerida" |
| 4 | Fecha de emisión (`fecha_emision`) | No | Fecha | — | — | — | 25/06/2026 | — |
| 5 | Número de radicado (`numero_radicado`) | No | Texto | Máx. 500 | — | — | RAD-2026-00901 | — |
| 6 | PDF del informe (`pdf`) | Sí (si no hay archivo existente) | Archivo | PDF ≤ 20 MB | — | — | IS-901-26_prueba.pdf | "El archivo PDF es requerido" |
| 7 | Municipios actuales de la alerta (Marcar como cerrado) (`ubicaciones_cerradas`) | No | Casilla por municipio | Alerta no cerrada | Municipios de la alerta | Alerta asociada | Popayán (marcar cerrado) | "Esta alerta ya se encuentra cerrada…" |
| 8 | Agregar nuevos municipios (Departamento y Municipio) (`nuevas_ubicaciones`) | No | Listas con búsqueda | Alerta no cerrada | Departamentos y municipios | Alerta asociada | CAUCA › Timbío | "No hay nuevos municipios para agregar." |
| 9 | Recomendaciones (Eje tematico, Descripción, Entidad principal) · **Agregar** (`recomendaciones_nuevas`) | No | Sub-formulario repetible | Eje y entidad activa; alerta no cerrada | Ejes temáticos; entidades | Alerta asociada | Medidas de prevención y protección · Alcaldía de Prueba | "El valor de 'eje_tematico' es requerido" / "La entidad principal con ID … no existe o no está activa" |
| 10 | Cerrar la alerta con este informe (`cierra_alerta`) | No | Casilla | Solo el Super Administrador puede cerrar | Marcada / No marcada | — | No marcada | "No tienes permisos para realizar esta acción." (Administrador) |

- Campos que llena el sistema: Fecha de creación; correo "Notificación informe de seguimiento" a las entidades; el archivo se nombra IS-{número}-{alerta}-{fecha}.pdf.
- Campos que se bloquean: La alerta asociada no se cambia en la edición; con la alerta cerrada no se modifican municipios ni recomendaciones.
- Archivos: "PDF del informe": obligatorio si no hay uno existente, PDF ≤ 20 MB.
- Guardar o enviar con: **Cargar informe** (edición: **Guardar cambios**); **Siguiente** / **Atrás**.

**Pasos:**

##### Paso 2.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** Haga clic en **Cargar informe**.
**Resultado esperado:** Se abre el Paso 1.

##### Paso 2.2 — Escribir el número y elegir la alerta
**Objetivo del paso:** Identificar el informe.
**Qué hacer:** Escriba el **Número de informe** (por ejemplo "IS-001-25") y busque la **Alerta asociada**.
**Resultado esperado:** Si el número ya existe, al guardar: "Ya existe un informe con el número…".

##### Paso 2.3 — Elegir las fechas y el radicado
**Objetivo del paso:** Registrar los datos del documento.
**Qué hacer:** Elija la **Fecha de notificación** (obligatoria) y la **Fecha de emisión**; escriba el **Número de radicado** (por ejemplo "RAD-2025-00456").
**Resultado esperado:** Los campos quedan diligenciados.

##### Paso 2.4 — Adjuntar el PDF
**Objetivo del paso:** Dejar el soporte.
**Qué hacer:** Suba el **PDF del informe**.
**Resultado esperado:** Sin archivo: "El archivo PDF es requerido".

##### Paso 2.5 — Paso 2: marcar municipios cerrados
**Objetivo del paso:** Reflejar los municipios donde ya no aplica la alerta.
**Qué hacer:** Haga clic en **Siguiente**; en "Municipios actuales de la alerta" use **Marcar como cerrado** en los que indique el informe.
**Resultado esperado:** Los municipios quedan marcados para cerrar.

##### Paso 2.6 — Paso 2: agregar municipios
**Objetivo del paso:** Ampliar la alerta si el informe lo indica.
**Qué hacer:** En "Agregar nuevos municipios" elija departamento y municipio.
**Resultado esperado:** Aparecen en "Municipios a agregar".

##### Paso 2.7 — Paso 2: agregar recomendaciones
**Objetivo del paso:** Registrar recomendaciones nuevas del informe.
**Qué hacer:** En **Recomendaciones** use **Agregar** y diligencie Eje tematico, Descripción y Entidad principal; puede editarlas o eliminarlas antes de guardar.
**Resultado esperado:** Aparecen en la lista ("Se crearan al guardar el informe.").

##### Paso 2.8 — Paso 2: decidir el cierre
**Objetivo del paso:** Cerrar la alerta si el informe lo dispone.
**Qué hacer:** No marque **Cerrar la alerta con este informe**: su rol no puede cerrar alertas y el sistema rechazará el informe. Pida el cierre al Super Administrador.
**Resultado esperado:** Aparece "Si marca esta opcion, la alerta pasara a estado cerrada al guardar el informe."

##### Paso 2.9 — Cargar
**Objetivo del paso:** Registrar el informe y aplicar los cambios.
**Qué hacer:** Haga clic en **Cargar informe**.
**Resultado esperado:** Aparece "Informe de seguimiento creado — El informe ha sido registrado exitosamente"; se aplican los cambios y se envía el correo a las entidades.

> 🎞️ **[GIF MED-02-ISE-04]** — Cargar informe de seguimiento
> **Debe mostrar:** Los dos pasos con un municipio cerrado y una recomendación nueva
> **Resaltar:** Marcar como cerrado; Agregar recomendación; Cerrar la alerta con este informe
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/CargarInformeSeguimientoModal.tsx`
> **Tomarla con:** Administrador · **Datos:** Mock
> **Solo para GIF — Secuencia:** 1) Cargar informe 2) Paso 1 3) Siguiente 4) Municipios 5) Recomendación 6) Cargar informe · **Duración aproximada:** 40 segundos
> **Texto alternativo:** Animación de la carga de un informe de seguimiento

**Resultado de la actividad:** El informe queda registrado; los municipios y las recomendaciones nuevas se aplican (las recomendaciones generan el correo de recomendación asignada) y, si se marcó, la alerta queda Cerrada. Las entidades reciben "Notificación informe de seguimiento – Alerta Temprana N° {número}".

> ⤴ **El flujo continúa por fuera de la plataforma.** Evidencia: `dashboard/src/pages/InformesDeSeguimiento.tsx:228-230`. El informe lo emite la Defensoría fuera de SI-CIPRAT; vuelve con sus datos y su PDF en este formulario (o automáticamente por X-Road).

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Cargar el informe sin datos | "El número de informe es requerido", "El número de informe no puede exceder 500 caracteres", "Debe seleccionar una alerta", "La fecha de notificación es requerida", "El archivo PDF es requerido" | Faltan datos obligatorios. | Complete Número de informe, Alerta asociada, Fecha de notificación y PDF del informe. | — |
| Usar un número de informe ya registrado | "Ya existe un informe con el número '…'. Por favor use un número diferente." | El número de informe es único. | Verifique el número en el documento de la Defensoría. | Busque el número antes de cargar. |
| Modificar municipios o recomendaciones de una alerta cerrada | "Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso anterior." (servidor: "No se pueden agregar o modificar municipios en una alerta que ya se encuentra cerrada.") | La alerta está cerrada. | Registre solo los datos del informe. | — |
| Marcar "Cerrar la alerta con este informe" como Administrador | "No tienes permisos para realizar esta acción." (el servidor exige el permiso de cerrar alertas) | Solo el Super Administrador cierra alertas. | Cargue el informe sin marcar el cierre y pida al Super Administrador que cierre la alerta. | — |
| El PDF del informe no se adjunta | "El informe se registró sin el documento PDF — No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo." | Falla al subir el archivo. | Abra **Editar informe** y adjunte el PDF. | — |
| Agregar una recomendación con una entidad inactiva | "La entidad principal con ID … no existe o no está activa" / "La entidad asociada con ID … no existe o no está activa" | La entidad no está activa. | Elija otra entidad activa. | — |
| Seleccionar un archivo que no es PDF | "Tipo de archivo no permitido. Solo se aceptan: .pdf" (en el servidor: "Solo se permiten archivos PDF") | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Prepare los soportes en PDF antes de abrir el formulario. |
| Seleccionar un PDF muy pesado | "El archivo excede el tamaño máximo de {N} MB" (en el servidor: "El archivo excede el tamaño máximo permitido de 20MB") | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Escanee en resolución media y sin color cuando sea posible. |

> 📷 **[CAPTURA MED-02-ISE-05]** — Mensaje ERR-ISE-01
> **Debe mostrar:** La pantalla con el mensaje "El número de informe es requerido", "El número de informe no puede exceder 500 caracteres", "Debe seleccionar una alerta", "La fecha de notificación es requeri
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/CargarInformeSeguimientoModal.tsx:238-256`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Cargar el informe sin datos

> 📷 **[CAPTURA MED-02-ISE-06]** — Mensaje ERR-ISE-02
> **Debe mostrar:** La pantalla con el mensaje "Ya existe un informe con el número '…'. Por favor use un número diferente."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:413-416`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Usar un número de informe ya registrado

> 📷 **[CAPTURA MED-02-ISE-07]** — Mensaje ERR-ISE-03
> **Debe mostrar:** La pantalla con el mensaje "Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformeSeguimientoStep2Modificaciones.tsx:176-177`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Modificar municipios o recomendaciones de una alerta cerrada

> 📷 **[CAPTURA MED-02-ISE-08]** — Mensaje ERR-ISE-04
> **Debe mostrar:** La pantalla con el mensaje "No tienes permisos para realizar esta acción." (el servidor exige el permiso de cerrar alertas)
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Controladores/AccionAlertasControlador.cs:205`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Marcar "Cerrar la alerta con este informe" como Administrador

> 📷 **[CAPTURA MED-02-ISE-09]** — Mensaje ERR-ISE-05
> **Debe mostrar:** La pantalla con el mensaje "El informe se registró sin el documento PDF — No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/CargarInformeSeguimientoModal.tsx:377-380`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: El PDF del informe no se adjunta

> 📷 **[CAPTURA MED-02-ISE-10]** — Mensaje ERR-ISE-10
> **Debe mostrar:** La pantalla con el mensaje "La entidad principal con ID … no existe o no está activa" / "La entidad asociada con ID … no existe o no está activa"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** Pantalla de la actividad (mensaje del servidor: `main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:1150-1170`)
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Agregar una recomendación con una entidad inactiva

**⚠️ Atención:**
- ⚠️ Las recomendaciones nuevas del informe empiezan sin actividades: si el plan de la alerta ya estaba confirmado, revise con el Monitor cómo quedan en el plan.
- ⚠️ La casilla de cierre se le muestra, pero solo el Super Administrador puede usarla.

**Ejemplo:** Mock: Número IS-901-26, alerta AT-901-2026, notificación 30/06/2026, radicado RAD-2026-00901, cerrar el municipio Popayán y agregar Timbío.

#### Actividad 3 — Editar un informe de seguimiento

**Objetivo de la actividad:** Que el Administrador pueda corregir los datos o el PDF de un informe de seguimiento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| El número de informe es obligatorio (hasta 500 caracteres) y único; la alerta y la fecha de notificación son obligatorias y el PDF es obligatorio en pantalla. | Revise el estado o el dato en la pantalla antes de actuar | Tomar los datos del documento de la Defensoría (Super Administrador o Administrador) | RN-ISE-01 |
| Al editar un informe de seguimiento no se cambia su alerta asociada. | Revise el estado o el dato en la pantalla antes de actuar | Eliminar y cargar de nuevo si la alerta está mal (Super Administrador) (Super Administrador) | RN-ISE-05 |
| No se agregan ni modifican municipios ni recomendaciones en una alerta cerrada. | Revise el estado o el dato en la pantalla antes de actuar | Registrar solo los datos del informe (Super Administrador o Administrador) | RN-ISE-02 |

**Dónde:** Informes de seguimiento › **Editar informe** › "Editar informe de seguimiento — Modifica los datos del informe de seguimiento.".

**Qué ve:** El asistente con los datos del informe; la Alerta asociada aparece bloqueada ("La alerta asociada no puede ser modificada"). Botón **Guardar cambios**.

**Campos a diligenciar — Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos):**

| # | Campo | Obligatorio | Tipo de campo | Requisitos | Opciones disponibles | Depende de | Ejemplo (AT-013-25 o Mock) | Mensaje si no se cumple |
|---|---|---|---|---|---|---|---|---|
| 1 | Número de informe (`numero_informe`) | Sí | Texto | Máx. 500; único | — | — | IS-901-26 | "El número de informe es requerido" / "El número de informe no puede exceder 500 caracteres" / "Ya existe un informe con el número '…'" |
| 2 | Alerta asociada (`alerta_id`) | Sí | Lista con búsqueda | Alerta existente | Alertas | Carga los municipios del Paso 2 | AT-013-2025 [DATO REAL AT-013-25] | "Debe seleccionar una alerta" / "La alerta asociada no puede ser modificada" |
| 3 | Fecha de notificación (`fecha_notificacion`) | Sí | Fecha | — | — | — | 30/06/2026 | "La fecha de notificación es requerida" |
| 4 | Fecha de emisión (`fecha_emision`) | No | Fecha | — | — | — | 25/06/2026 | — |
| 5 | Número de radicado (`numero_radicado`) | No | Texto | Máx. 500 | — | — | RAD-2026-00901 | — |
| 6 | PDF del informe (`pdf`) | Sí (si no hay archivo existente) | Archivo | PDF ≤ 20 MB | — | — | IS-901-26_prueba.pdf | "El archivo PDF es requerido" |
| 7 | Municipios actuales de la alerta (Marcar como cerrado) (`ubicaciones_cerradas`) | No | Casilla por municipio | Alerta no cerrada | Municipios de la alerta | Alerta asociada | Popayán (marcar cerrado) | "Esta alerta ya se encuentra cerrada…" |
| 8 | Agregar nuevos municipios (Departamento y Municipio) (`nuevas_ubicaciones`) | No | Listas con búsqueda | Alerta no cerrada | Departamentos y municipios | Alerta asociada | CAUCA › Timbío | "No hay nuevos municipios para agregar." |
| 9 | Recomendaciones (Eje tematico, Descripción, Entidad principal) · **Agregar** (`recomendaciones_nuevas`) | No | Sub-formulario repetible | Eje y entidad activa; alerta no cerrada | Ejes temáticos; entidades | Alerta asociada | Medidas de prevención y protección · Alcaldía de Prueba | "El valor de 'eje_tematico' es requerido" / "La entidad principal con ID … no existe o no está activa" |
| 10 | Cerrar la alerta con este informe (`cierra_alerta`) | No | Casilla | Solo el Super Administrador puede cerrar | Marcada / No marcada | — | No marcada | "No tienes permisos para realizar esta acción." (Administrador) |

- Campos que llena el sistema: Fecha de creación; correo "Notificación informe de seguimiento" a las entidades; el archivo se nombra IS-{número}-{alerta}-{fecha}.pdf.
- Campos que se bloquean: La alerta asociada no se cambia en la edición; con la alerta cerrada no se modifican municipios ni recomendaciones.
- Archivos: "PDF del informe": obligatorio si no hay uno existente, PDF ≤ 20 MB.
- Guardar o enviar con: **Cargar informe** (edición: **Guardar cambios**); **Siguiente** / **Atrás**.

**Pasos:**

##### Paso 3.1 — Abrir la edición
**Objetivo del paso:** Cargar el informe.
**Qué hacer:** Haga clic en **Editar informe**.
**Resultado esperado:** Se abre el asistente.

##### Paso 3.2 — Corregir el Paso 1
**Objetivo del paso:** Ajustar los datos del documento.
**Qué hacer:** Modifique Número de informe, Fecha de notificación, Fecha de emisión, Número de radicado o el PDF del informe.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 3.3 — Revisar el Paso 2
**Objetivo del paso:** Ajustar las modificaciones si la alerta sigue abierta.
**Qué hacer:** Revise municipios, recomendaciones y la casilla de cierre.
**Resultado esperado:** Si la alerta está cerrada: "Esta alerta ya se encuentra cerrada…".

##### Paso 3.4 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Informe de seguimiento actualizado — El informe ha sido actualizado exitosamente".

> 📷 **[CAPTURA MED-02-ISE-11]** — Alerta bloqueada en la edición
> **Debe mostrar:** El Paso 1 de la edición con la alerta bloqueada
> **Resaltar:** Mensaje "La alerta asociada no puede ser modificada"
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformeSeguimientoStep1.tsx:123`
> **Tomarla con:** Administrador · **Datos:** Informe Mock
> **Texto alternativo:** Edición de un informe de seguimiento

**Resultado de la actividad:** El informe queda corregido.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Usar un número de informe ya registrado | "Ya existe un informe con el número '…'. Por favor use un número diferente." | El número de informe es único. | Verifique el número en el documento de la Defensoría. | Busque el número antes de cargar. |
| Modificar municipios o recomendaciones de una alerta cerrada | "Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso anterior." (servidor: "No se pueden agregar o modificar municipios en una alerta que ya se encuentra cerrada.") | La alerta está cerrada. | Registre solo los datos del informe. | — |
| El PDF del informe no se adjunta | "El informe se registró sin el documento PDF — No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo." | Falla al subir el archivo. | Abra **Editar informe** y adjunte el PDF. | — |
| Intentar cambiar la alerta al editar el informe | Campo bloqueado con "La alerta asociada no puede ser modificada" | La alerta del informe no se cambia. | Si la alerta está mal, elimine el informe (Super Administrador) y cárguelo de nuevo. | — |

> 📷 **[CAPTURA MED-02-ISE-12]** — Mensaje ERR-ISE-08
> **Debe mostrar:** La pantalla con el mensaje Campo bloqueado con "La alerta asociada no puede ser modificada"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/informes-seguimiento/InformeSeguimientoStep1.tsx:123`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Intentar cambiar la alerta al editar el informe

### Módulo 11 — Oficios de consumación

**Prerrequisitos:** Módulo 04 (las alertas deben existir).

**Definición del módulo:** Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. Todos los roles los listan, filtran por alerta, consultan y descargan; solo el Super Administrador los carga en 2 pasos (información del oficio y alertas; modificaciones por alerta), los edita y los elimina.

**Objetivo del módulo:** Que el Administrador pueda consultar los oficios de consumación y descargar su PDF.

**Contexto del módulo:** Corresponde al cierre del ciclo (E6.2). Recibe las alertas asociadas y sus municipios; envía el correo "Notificación Oficio de Consumación" a las entidades. También llegan oficios por X-Road. Es visible para todos los roles. Para el Administrador: ve todos los registrados (`main-api/CipratApi/Servicios/ServicioOficiosConsumacion.cs:59-72`). En total, tiene 4 de las 8 funcionalidades del módulo; no tiene: cargar un oficio de consumación, modificar municipios y agregar recomendaciones desde el oficio, editar un oficio de consumación, eliminar un oficio de consumación.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Listar los oficios de consumación (F-OFI-01) | Tabla con Oficio, Fecha de creación, Fecha de finalización y Alertas asociadas. | R | Módulo 11 — Actividad 1 |
| Buscar y filtrar oficios por alerta (F-OFI-02) | Busca por radicado y filtra por Alerta asociada. | R | Módulo 11 — Actividad 1 |
| Ver el detalle de un oficio (F-OFI-03) | Muestra Numero de radicado, Fecha del oficio, Fecha de notificacion, Fecha de consumacion, Alertas asociadas y Archivo adjunto. | R | Módulo 11 — Actividad 1 |
| Descargar el PDF del oficio (F-OFI-04) | Descarga el archivo del oficio. | Archivo | Módulo 11 — Actividad 1 |
| Recibir oficios de consumación por X-Road (F-INT-03, módulo Interoperabilidad X-Road (SISAT)) | SISAT envía oficios de consumación. | Automática | Módulo 11 — Actividad 1 |

#### Actividad 1 — Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

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

> 📷 **[CAPTURA MED-02-OFI-01]** — Oficios de consumación
> **Debe mostrar:** La tabla de oficios con el detalle abierto
> **Resaltar:** Alertas asociadas; Archivo PDF
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx`
> **Tomarla con:** Administrador · **Datos:** Oficio Mock
> **Texto alternativo:** Oficios de consumación y su detalle

**Resultado de la actividad:** Conoce los oficios de consumación.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Buscar los botones de cargar, editar o eliminar oficios | Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios" | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | — |
| Los oficios no cargan o no se descargan | "Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio." | Falla del servicio. | Recargue la página e intente de nuevo. | — |
| Buscar o filtrar sin coincidencias | "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo." | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Busque por número de alerta o código. |

> 📷 **[CAPTURA MED-02-OFI-02]** — Mensaje ERR-OFI-02
> **Debe mostrar:** La pantalla con el mensaje Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48,107,241,263`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Buscar los botones de cargar, editar o eliminar oficios

> 📷 **[CAPTURA MED-02-OFI-03]** — Mensaje ERR-OFI-05
> **Debe mostrar:** La pantalla con el mensaje "Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo." / "Error al descargar el oficio."
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/pages/OficiosDeConsumacion.tsx:81-82,194`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Los oficios no cargan o no se descargan

**⚠️ Atención:**
- Ve todos los oficios registrados.

### Módulo 12 — Notificaciones

**Prerrequisitos:** Módulo 01.

**Definición del módulo:** Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).

**Objetivo del módulo:** Que el Administrador pueda consultar el panel de Notificaciones; reconocer los correos que envía el sistema y qué hacer con cada uno.

**Contexto del módulo:** Acompaña todo el ciclo. Recibe eventos de todos los módulos: cada acción registrada en el historial aparece en el panel, y ciertos eventos generan correo. Los correos de negocio solo llegan a usuarios activos de Entidad Territorial (Central o Subdirección) cuya entidad es principal o asociada; el aprobador designado de un reporte de ejecución recibe su propio correo. No hay mensajes de texto (SMS). Para el Administrador: ve el historial de actividad de todas las alertas del país, sin filtro (`main-api/CipratApi/Controladores/AlertasControlador.cs:736-800`). En total, tiene 6 de las 13 funcionalidades del módulo; no tiene: recibir el correo de recomendación asignada, recibir el correo de recomendación actualizada, recibir el correo de validación del plan de acción, recibir el recordatorio de informe de ejecución, recibir el correo de informe de seguimiento, recibir el correo de oficio de consumación, recibir el correo de reporte de ejecución pendiente.

**Funcionalidades disponibles:**

| Funcionalidad | Definición | Tipo | Actividad de la ruta donde se explica |
|---|---|---|---|
| Abrir el panel de Notificaciones (F-NOT-01) | Muestra el historial de actividad de las alertas del alcance del usuario: quién hizo qué, cuándo y sobre qué alerta. | R | Módulo 12 — Actividad 1 |
| Buscar en el panel de Notificaciones (F-NOT-02) | Filtra el historial por texto. | R | Módulo 12 — Actividad 1 |
| Cargar más notificaciones (F-NOT-03) | Trae 10 registros más del historial. | R | Módulo 12 — Actividad 1 |
| Recibir el correo de invitación (F-NOT-04) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" con el enlace de activación (7 días). | Automática | Módulo 01 — Actividad 1; Módulo 12 — Actividad 2 |
| Recibir el correo con el código de verificación (F-NOT-05) | Correo "SI-CIPRAT - Código de Verificación" con el código de 4 dígitos (1 hora). | Automática | Módulo 01 — Actividad 2; Módulo 12 — Actividad 2 |
| Recibir el correo de restablecimiento de contraseña (F-NOT-06) | Correo "SI-CIPRAT - Restablecer Contraseña" con el enlace (1 hora). | Automática | Módulo 01 — Actividad 3; Módulo 12 — Actividad 2 |

#### Actividad 1 — Consultar el panel de Notificaciones

**Objetivo de la actividad:** Que el Administrador pueda revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6.

| Requisito | Cómo verificar que se cumple | Qué hacer si no se cumple (quién lo hace) | RN |
|---|---|---|---|
| Cada usuario solo ve las alertas de su alcance: Monitor, Líder de Macrozona y Consulta Departamentos por sus departamentos; Entidad Territorial y Consulta Entidad por su entidad o subdirección; los demás, todo el país. | Revise su alcance en Ver Perfil | Pedir el ajuste del usuario (departamentos o entidad) (Super Administrador o Administrador) | RN-SCO-01 |

**Dónde:** Menú lateral › **Notificaciones** (panel lateral).

**Qué ve:** El panel "Notificaciones" con el buscador "Buscar por nombre" y la lista del historial de actividad de nacional: usuario que actuó, acción, alerta y fecha; algunos eventos muestran "Consecutivo:", "Fecha notificacion:" y el enlace "Descargar archivo". Al final, **Mostrar 10 mas**.

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

> 📷 **[CAPTURA MED-02-NOT-01]** — Panel Notificaciones
> **Debe mostrar:** El panel abierto con varios eventos de una alerta
> **Resaltar:** Buscador; un evento con usuario, acción y fecha; Mostrar 10 mas
> **Pantalla / ruta:** Panel lateral (`dashboard/src/components/notifications/NotificationsPanel.tsx`)
> **Tomarla con:** Administrador · **Datos:** Alerta Mock con historial
> **Texto alternativo:** Panel de notificaciones con el historial de actividad

**Resultado de la actividad:** Conoce lo que pasó en las alertas de su alcance; es su fuente de avisos, porque su rol no recibe los correos de negocio.

**Escenarios de error y solución:**

| Qué pasa | Qué ve el usuario (mensaje exacto) | Por qué ocurre | Cómo solucionarlo | Cómo prevenirlo |
|---|---|---|---|---|
| Abrir el panel sin actividad en su alcance | "No hay notificaciones" | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | — |

> 📷 **[CAPTURA MED-02-NOT-02]** — Mensaje ERR-NOT-01
> **Debe mostrar:** La pantalla con el mensaje "No hay notificaciones"
> **Resaltar:** El mensaje y el campo o botón que lo produce
> **Pantalla / ruta:** `dashboard/src/components/notifications/NotificationsPanel.tsx:143`
> **Tomarla con:** Administrador · **Datos:** Datos Mock que provoquen el error
> **Texto alternativo:** Mensaje de error: Abrir el panel sin actividad en su alcance

**⚠️ Atención:**
- El panel no tiene marcas de leído o no leído: muestra el historial de actividad.

#### Actividad 2 — Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el Administrador pueda identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

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

> 📷 **[CAPTURA MED-02-NOT-03]** — Correo del sistema
> **Debe mostrar:** Un correo "SI-CIPRAT - Código de Verificación" de prueba
> **Resaltar:** Asunto y enlace
> **Pantalla / ruta:** Bandeja de correo (plantillas en `main-api/CipratApi/Servicios/EmailService.cs`)
> **Tomarla con:** Administrador · **Datos:** Correo de prueba con datos Mock
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

### Módulo 13 — Práctica con el caso AT-013-25

**Prerrequisitos:** Haber completado los Módulos 01 a 12 de esta ruta; tener un usuario de prueba con el rol Administrador en el ambiente de pruebas y los valores de la línea base de la AT-013-25 o los datos Mock indicados.

**Definición del módulo:** Módulo de práctica guiada que repite, en orden cronológico, cada actividad operativa de la ruta con datos de la alerta AT-013-25 o con datos ficticios (Mock) cuando el dato real no está disponible o no está autorizado.

**Objetivo del módulo:** Que el Administrador pueda ejecutar en un ambiente de pruebas todas las actividades de su ruta con datos de la AT-013-25 o datos Mock.

**Contexto del módulo:** Los valores de la práctica salen de la línea base de la AT-013-25 (Riesgo Electoral Nacional 2025-2026) [DATO REAL AT-013-25]: alerta notificada el 07/10/2025, tipo Estructural, etiqueta Regional, 41 recomendaciones (RC-001-2025-013 a RC-041-2025-013) y un plan de mitigación **parcial**: 20 actividades de 5 recomendaciones (RC-003, RC-004, RC-021, RC-022 y RC-023). En el sistema la alerta se escribe AT-013-2025, porque el número exige año de 4 dígitos. Lo que la línea base no trae (las actividades de las otras recomendaciones y los informes de ejecución) se practica con datos Mock (pendiente: plan de mitigación no disponible). Antes de usar datos reales en una sesión, el Ministerio debe autorizarlos (ver `usos_datos_reales.csv`).

**Funcionalidades disponibles:** las mismas de los módulos anteriores de esta ruta, en el ambiente de pruebas.

#### Actividad 1 — Práctica: Cerrar sesión y entender el cierre automático

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, cerrar su sesión de forma segura y reconocer cuándo el sistema la cierra solo.

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

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, conocer las condiciones de uso de la plataforma y escribir al soporte cuando no pueda resolver un problema.

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

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, moverse entre los módulos de su menú y ajustar el contraste y el tamaño de letra.

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

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo).

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 12 — Actividad 1.

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
- [ ] Provocó a propósito al menos un escenario de error de Módulo 12 — Actividad 1 y lo resolvió.

#### Actividad 5 — Práctica: Reconocer los correos que envía el sistema y qué hacer con cada uno

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno.

**Cuándo se hace y requisitos previos:** Secuencia E0–E6; los mismos requisitos de Módulo 12 — Actividad 2.

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
- [ ] Provocó a propósito al menos un escenario de error de Módulo 12 — Actividad 2 y lo resolvió.

#### Actividad 6 — Práctica: Consultar, buscar y filtrar entidades

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar una entidad central o una subdirección y ver sus usuarios.

**Cuándo se hace y requisitos previos:** Secuencia E0.1; los mismos requisitos de Módulo 03 — Actividad 7.

**Dónde:** Usuarios y entidades › pestaña **Entidades**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 6.1 — Abrir Entidades
**Objetivo del paso:** Ver las entidades registradas.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la pestaña **Entidades**.
**Resultado esperado:** Aparece la vista **Centrales**.

##### Paso 6.2 — Cambiar a Subdirecciones
**Objetivo del paso:** Ver las dependencias.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Subdirecciones**.
**Resultado esperado:** Aparece la tabla de subdirecciones.

##### Paso 6.3 — Buscar y filtrar
**Objetivo del paso:** Encontrar una entidad.
**Qué hacer:** En el ambiente de pruebas: Escriba en "Buscar por nombre" o use **Filtros** › Categoría › **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 6.4 — Ver los usuarios asignados
**Objetivo del paso:** Saber quién pertenece a la entidad.
**Qué hacer:** En el ambiente de pruebas: Pase el cursor sobre el número de la columna **Usuarios**.
**Resultado esperado:** Aparece "Usuarios asignados" con hasta 5 nombres, o "Sin usuarios asignados".

##### Paso 6.5 — Abrir el detalle
**Objetivo del paso:** Ver las subdirecciones de una entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono **Detalle** de la fila.
**Resultado esperado:** Se abre la ventana con "Entidad central", "Sub direcciones — Subdirecciones asociadas a la entidad central.", el buscador "Buscar subdirección..." y **Mostrar 10 más**.

**Resultado esperado de la práctica:** Ubica la entidad, sus subdirecciones y sus usuarios.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica la entidad, sus subdirecciones y sus usuarios.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 7 y lo resolvió.

#### Actividad 7 — Práctica: Agregar una entidad con sus subdirecciones

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, registrar una entidad central con su categoría y sus subdirecciones para poder asignarla a usuarios y recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E0.1; los mismos requisitos de Módulo 03 — Actividad 8.

**Dónde:** Entidades › **Agregar Entidad** › ventana "Agregar entidad territorial".

**Datos de la práctica:** Entidad Mock "Gobernación de Prueba", categoría Gobernación, subdirección "Secretaría de Gobierno de Prueba".

**Pasos:**

##### Paso 7.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Agregar Entidad**.
**Resultado esperado:** Se abre "Agregar entidad territorial".

##### Paso 7.2 — Escribir el nombre
**Objetivo del paso:** Identificar la entidad.
**Qué hacer:** En el ambiente de pruebas: En **Entidad Central** escriba el nombre oficial completo (por ejemplo, "Policía Nacional").
**Resultado esperado:** El campo queda diligenciado.

##### Paso 7.3 — Elegir la categoría
**Objetivo del paso:** Clasificar la entidad.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Categoría**, busque y elija una opción.
**Resultado esperado:** La categoría queda seleccionada.

##### Paso 7.4 — Agregar subdirecciones (si aplica)
**Objetivo del paso:** Registrar las dependencias que responderán recomendaciones.
**Qué hacer:** En el ambiente de pruebas: Active **Sub Direcciones** ("Aplica para las entidades segmentadas a nivel municipal.") y use **Agregar subdirección** para cada una; escriba su nombre.
**Resultado esperado:** Aparecen las filas de subdirección.

##### Paso 7.5 — Guardar
**Objetivo del paso:** Crear la entidad.
**Qué hacer:** En el ambiente de pruebas: Revise el nombre y haga clic en **Agregar entidad**.
**Resultado esperado:** Aparece "Entidad creada con éxito — La entidad fue registrada y está lista para su gestión."

**Resultado esperado de la práctica:** La entidad queda Activa y disponible para usuarios y recomendaciones.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La entidad queda Activa y disponible para usuarios y recomendaciones.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 8 y lo resolvió.

#### Actividad 8 — Práctica: Editar una entidad y sus subdirecciones

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir el nombre o la categoría de una entidad y agregar o quitar subdirecciones.

**Cuándo se hace y requisitos previos:** Secuencia E0.1; los mismos requisitos de Módulo 03 — Actividad 9.

**Dónde:** Entidades › fila › ícono **Editar** (o **Detalle** › **Editar**) › ventana "Editar entidad territorial".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 8.1 — Abrir la edición
**Objetivo del paso:** Cargar los datos de la entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono **Editar** de la fila (o en **Detalle** › **Editar**).
**Resultado esperado:** Se abre "Editar entidad territorial".

##### Paso 8.2 — Cambiar nombre o categoría
**Objetivo del paso:** Corregir los datos.
**Qué hacer:** En el ambiente de pruebas: Modifique **Entidad Central** o **Categoría**.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 8.3 — Agregar o quitar subdirecciones
**Objetivo del paso:** Actualizar las dependencias.
**Qué hacer:** En el ambiente de pruebas: Use **Agregar subdirección** o quite una fila; use "Buscar" y **Mostrar 10 más** si son muchas.
**Resultado esperado:** Si la subdirección tiene usuarios o alertas: "No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas."

##### Paso 8.4 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Entidad actualizada con éxito — Los cambios han sido guardados correctamente."

**Resultado esperado de la práctica:** La entidad queda actualizada en toda la plataforma.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La entidad queda actualizada en toda la plataforma.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 9 y lo resolvió.

#### Actividad 9 — Práctica: Eliminar una entidad

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, eliminar una entidad creada por error que no tiene información relacionada.

**Cuándo se hace y requisitos previos:** Secuencia E0.1; los mismos requisitos de Módulo 03 — Actividad 10.

**Dónde:** Entidades › vista Centrales › fila › ícono **Eliminar** › ventana "Eliminar entidad central".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 9.1 — Verificar que no esté en uso
**Objetivo del paso:** Evitar el error de eliminación.
**Qué hacer:** En el ambiente de pruebas: Revise que las columnas **Subdirecciones** y **Usuarios** estén en 0 y que la entidad no tenga recomendaciones.
**Resultado esperado:** Confirma que se puede eliminar.

##### Paso 9.2 — Eliminar
**Objetivo del paso:** Retirar la entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono **Eliminar** de la fila y confirme.
**Resultado esperado:** Aparece "Entidad eliminada con éxito — La entidad ha sido eliminada correctamente."

**Resultado esperado de la práctica:** La entidad deja de aparecer (borrado lógico).

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La entidad deja de aparecer (borrado lógico).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 10 y lo resolvió.

#### Actividad 10 — Práctica: Invitar un usuario

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, crear un usuario con el rol y el alcance correctos y enviarle la invitación por correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.2; los mismos requisitos de Módulo 03 — Actividad 3.

**Dónde:** Usuarios y entidades › **Usuarios** › **Enviar invitación** › ventana "Enviar invitación".

**Datos de la práctica:** Monitor Mock: CAUCA y NARIÑO, "Ana Prueba", cargo "Profesional especializado", ana.prueba@ejemplo.gov.co.

**Pasos:**

##### Paso 10.1 — Abrir el formulario
**Objetivo del paso:** Iniciar la invitación.
**Qué hacer:** En el ambiente de pruebas: En la pestaña **Usuarios** haga clic en **Enviar invitación**.
**Resultado esperado:** Se abre la ventana "Enviar invitación".

##### Paso 10.2 — Elegir el Rol
**Objetivo del paso:** Definir los permisos y qué campos se piden.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Rol** y elija el rol (pase el cursor por el ícono de ayuda para leer "Tipos de roles"). La opción "Super Administrador" no aparece para su rol.
**Resultado esperado:** Según el rol aparecen o desaparecen Nivel de acceso, Entidad Central, Subdirección y Departamentos, y el Cargo se vuelve obligatorio u opcional.

##### Paso 10.3 — Definir el Nivel de acceso (solo Entidad Territorial)
**Objetivo del paso:** Distinguir entre usuario de la entidad central y de una subdirección.
**Qué hacer:** En el ambiente de pruebas: Si el rol es "Entidad Territorial", elija **Nivel de acceso**: Central o Subdirección.
**Resultado esperado:** Se limpian Entidad Central y Subdirección para elegirlas de nuevo.

##### Paso 10.4 — Elegir la Entidad Central y la Subdirección
**Objetivo del paso:** Fijar el alcance por entidad.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Entidad Central**, escriba en "Buscar entidad..." y elíjala (obligatoria para Entidad Territorial y Consulta Entidad; opcional para Administrador, Líder de Macrozona y Monitor). Si el nivel es Subdirección, elija también **Subdirección**.
**Resultado esperado:** Aparece "El usuario solo tendrá acceso a las alertas de esta subdirección." cuando aplica.

##### Paso 10.5 — Escribir el Área (opcional)
**Objetivo del paso:** Registrar la dependencia interna del usuario.
**Qué hacer:** En el ambiente de pruebas: Si aplica, escriba el **Área**.
**Resultado esperado:** El campo queda diligenciado.

##### Paso 10.6 — Elegir los Departamentos (Monitor, Líder de Macrozona, Consulta Departamentos)
**Objetivo del paso:** Fijar el alcance territorial.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Departamentos**, busque y marque uno o varios.
**Resultado esperado:** Aparece "El usuario solo tendrá acceso a las alertas de estos departamentos."

##### Paso 10.7 — Escribir nombres, apellidos y cargo
**Objetivo del paso:** Identificar al usuario.
**Qué hacer:** En el ambiente de pruebas: Escriba **Nombres** y **Apellidos**; escriba el **Cargo** (obligatorio para Entidad Territorial, Líder de Macrozona y Monitor).
**Resultado esperado:** Los campos quedan diligenciados.

##### Paso 10.8 — Escribir el correo
**Objetivo del paso:** Indicar a dónde llega la invitación.
**Qué hacer:** En el ambiente de pruebas: Escriba el **Correo electrónico** institucional, sin espacios.
**Resultado esperado:** Si el formato no es válido: "El correo electrónico no es válido".

##### Paso 10.9 — Revisar antes de enviar
**Objetivo del paso:** Evitar errores de permisos.
**Qué hacer:** En el ambiente de pruebas: Verifique el rol, la entidad, la subdirección, los departamentos y el correo: el aviso indica que los permisos no deberían cambiarse después.
**Resultado esperado:** Los datos están completos.

##### Paso 10.10 — Enviar la invitación
**Objetivo del paso:** Crear el usuario y enviar el correo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Enviar Invitación**.
**Resultado esperado:** Aparece "Invitación enviada con éxito — Se ha enviado una invitación a {nombre} ({correo})." y el usuario aparece en **Invitaciones** con estado Pendiente.

**Resultado esperado de la práctica:** El usuario queda en "Invitación pendiente" con 7 días para activar su cuenta y recibe el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas".

**Lista de verificación:**
- [ ] Completó los 10 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El usuario queda en "Invitación pendiente" con 7 días para activar su cuenta y recibe el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas".
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 3 y lo resolvió.

#### Actividad 11 — Práctica: Activar la cuenta desde la invitación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, activar su cuenta de SI-CIPRAT creando su contraseña desde el correo de invitación, dentro de los 7 días de vigencia del enlace.

**Cuándo se hace y requisitos previos:** Secuencia E0.3; los mismos requisitos de Módulo 01 — Actividad 1.

**Dónde:** Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" › enlace › pantalla "Configura tu contraseña" (`/setup/:token`).

**Datos de la práctica:** Invitación de prueba enviada al correo del participante (Mock).

**Pasos:**

##### Paso 11.1 — Abrir el enlace de la invitación
**Objetivo del paso:** Llegar a la pantalla de activación con un enlace válido.
**Qué hacer:** En el ambiente de pruebas: Abra el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" y haga clic en el enlace. Hágalo antes de 7 días desde el envío.
**Resultado esperado:** Se abre "Configura tu contraseña". Si el enlace venció, aparece "El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador."

##### Paso 11.2 — Escribir la nueva contraseña
**Objetivo del paso:** Crear una contraseña que cumpla las reglas de seguridad.
**Qué hacer:** En el ambiente de pruebas: En **Nueva Contraseña** escriba al menos 8 caracteres e incluya un carácter especial (por ejemplo, # o !). Use el ícono del ojo para verificar lo escrito.
**Resultado esperado:** Los indicadores "Debe tener al menos 8 caracteres" y "Debe contener al menos un carácter especial" se marcan como cumplidos.

##### Paso 11.3 — Confirmar la contraseña
**Objetivo del paso:** Evitar errores de digitación.
**Qué hacer:** En el ambiente de pruebas: En **Confirmar Contraseña** escriba exactamente la misma contraseña.
**Resultado esperado:** Si no coinciden, al enviar aparece "Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente."

##### Paso 11.4 — Activar la cuenta
**Objetivo del paso:** Dejar la cuenta en estado Activo.
**Qué hacer:** En el ambiente de pruebas: Revise que los dos campos coincidan y haga clic en **Activar cuenta**.
**Resultado esperado:** El botón muestra "Activando cuenta..." y luego la pantalla confirma; la cuenta queda Activa y puede iniciar sesión.

**Resultado esperado de la práctica:** La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La cuenta queda en estado Activo y la invitación queda utilizada. El siguiente paso es iniciar sesión (Actividad 2 de este módulo).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 1 y lo resolvió.

#### Actividad 12 — Práctica: Iniciar sesión con el código de verificación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ingresar a SI-CIPRAT con su correo, su contraseña y el código de 4 dígitos que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01 — Actividad 2.

**Dónde:** Dirección de la plataforma › **Iniciar sesión** (`/signin`) › "Inicia sesión en tu cuenta".

**Datos de la práctica:** Usuario de prueba de la ruta (administrador.prueba@ejemplo.gov.co).

**Pasos:**

##### Paso 12.1 — Abrir la pantalla de ingreso
**Objetivo del paso:** Llegar al formulario de inicio de sesión.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de SI-CIPRAT en Chrome, Firefox o Edge actualizados y haga clic en **Iniciar sesión** (o abra directamente `/signin`).
**Resultado esperado:** Aparece "Inicia sesión en tu cuenta".

##### Paso 12.2 — Escribir correo y contraseña
**Objetivo del paso:** Identificarse ante el sistema.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional (el mismo de la invitación). En **Contraseña** escriba su contraseña.
**Resultado esperado:** Los campos quedan diligenciados. Si están vacíos, la pantalla muestra "Email is required" o "Password is required".

##### Paso 12.3 — Solicitar el código
**Objetivo del paso:** Validar credenciales y recibir el código de verificación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Iniciar Sesión**.
**Resultado esperado:** El botón muestra "Iniciando sesión..." y aparece "Revisa tu correo electrónico". Llega el correo "SI-CIPRAT - Código de Verificación". Si las credenciales no son correctas: "Credenciales inválidas".

##### Paso 12.4 — Escribir el código de 4 dígitos
**Objetivo del paso:** Comprobar que quien ingresa tiene acceso al correo.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y escriba los 4 dígitos, uno en cada casilla (solo acepta números; puede pegarlos). Si no llegó, espere un minuto, revise el correo no deseado y haga clic en **Haz clic para reenviar**.
**Resultado esperado:** Las 4 casillas quedan llenas.

##### Paso 12.5 — Validar el código
**Objetivo del paso:** Abrir la sesión.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Validar código**.
**Resultado esperado:** Entra a **Inicio** con el menú lateral de su rol. Si el código no coincide: "Código de autenticación inválido"; si pasó más de 1 hora: "Código expirado".

**Resultado esperado de la práctica:** Sesión abierta con el rol el Administrador y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sesión abierta con el rol el Administrador y el alcance de datos de su usuario. La sesión dura máximo 720 minutos y se cierra tras 60 minutos sin actividad.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 2 y lo resolvió.

#### Actividad 13 — Práctica: Consultar Mi perfil y verificar el alcance asignado

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, verificar en Mi perfil su rol, entidad, subdirección y departamentos, porque de ellos depende la información que ve.

**Cuándo se hace y requisitos previos:** Secuencia E0.4; los mismos requisitos de Módulo 01 — Actividad 6.

**Dónde:** Menú lateral › nombre del usuario › **Ver Perfil** (`/mi-perfil`).

**Datos de la práctica:** Usuario de prueba configurado con el alcance de la ruta.

**Pasos:**

##### Paso 13.1 — Abrir Mi perfil
**Objetivo del paso:** Llegar a la pantalla de datos de la cuenta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en su nombre al pie del menú lateral y luego en **Ver Perfil**.
**Resultado esperado:** Se abre Mi perfil con "Cargando perfil..." y luego sus datos.

##### Paso 13.2 — Revisar Información General
**Objetivo del paso:** Confirmar los datos personales registrados.
**Qué hacer:** En el ambiente de pruebas: Lea Nombres, Apellidos, Cargo, Área y Correo electrónico.
**Resultado esperado:** Los datos coinciden con los suyos; los campos no se pueden editar.

##### Paso 13.3 — Revisar Entidad y Acceso y Asignaciones
**Objetivo del paso:** Confirmar el alcance de datos.
**Qué hacer:** En el ambiente de pruebas: Verifique que el Rol diga "Administrador". Su alcance es nacional; la Entidad Central, si aparece, es informativa.
**Resultado esperado:** Confirma que verá todas las alertas del país, sin filtro de entidad ni de departamento.

**Resultado esperado de la práctica:** Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe con qué datos fue configurado; si algo no corresponde, pide la corrección a quien administra los usuarios.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 6 y lo resolvió.

#### Actividad 14 — Práctica: Consultar, buscar y filtrar usuarios e invitaciones

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar a cualquier usuario o invitación y saber en qué estado está.

**Cuándo se hace y requisitos previos:** Secuencia E0.5; los mismos requisitos de Módulo 03 — Actividad 1.

**Dónde:** Menú lateral › **Usuarios y entidades** › pestaña **Usuarios**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 14.1 — Abrir la pestaña Usuarios
**Objetivo del paso:** Ver los usuarios de la plataforma.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Usuarios y entidades** y luego en la pestaña **Usuarios**.
**Resultado esperado:** Aparece la tabla con "Cargando usuarios..." y luego los registros.

##### Paso 14.2 — Cambiar de vista
**Objetivo del paso:** Ver un grupo de usuarios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Todos**, **Entidades Territoriales**, **Administradores**, **Monitores** o **Invitaciones**.
**Resultado esperado:** La tabla muestra solo ese grupo; **Invitaciones** muestra Pendiente y Expirada.

##### Paso 14.3 — Buscar por nombre
**Objetivo del paso:** Encontrar un usuario puntual.
**Qué hacer:** En el ambiente de pruebas: Escriba el nombre o el correo en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; si no hay coincidencias: "No se encontraron resultados".

##### Paso 14.4 — Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Rol, Nivel, Estado o Categoría y haga clic en **Aplicar filtros**; para quitar, **Limpiar filtros**.
**Resultado esperado:** La tabla muestra los usuarios que cumplen todos los filtros.

**Resultado esperado de la práctica:** Ubica el usuario o la invitación y su estado.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica el usuario o la invitación y su estado.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 1 y lo resolvió.

#### Actividad 15 — Práctica: Ver el detalle de un usuario

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, revisar todos los datos de acceso de un usuario antes de editarlo o de responder una consulta.

**Cuándo se hace y requisitos previos:** Secuencia E0.5; los mismos requisitos de Módulo 03 — Actividad 2.

**Dónde:** Usuarios › fila › ícono **Detalle** (en la vista Invitaciones: **Ver detalle**) › ventana "Información de Usuario — Datos asignados para el acceso a la plataforma".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 15.1 — Abrir el detalle
**Objetivo del paso:** Ver los datos completos.
**Qué hacer:** En el ambiente de pruebas: En la fila del usuario haga clic en el ícono **Detalle** (en Invitaciones, **Ver detalle**).
**Resultado esperado:** Se abre "Información de Usuario".

##### Paso 15.2 — Revisar rol y alcance
**Objetivo del paso:** Confirmar qué verá el usuario.
**Qué hacer:** En el ambiente de pruebas: Lea Rol, Nivel de acceso, Entidad Central, Subdirección y Departamentos.
**Resultado esperado:** Identifica el alcance del usuario.

##### Paso 15.3 — Cerrar o pasar a editar
**Objetivo del paso:** Terminar la consulta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar** o en **Editar** para modificar.
**Resultado esperado:** Se cierra la ventana o se abre "Editar usuario".

**Resultado esperado de la práctica:** Conoce los datos y el alcance del usuario.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los datos y el alcance del usuario.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 2 y lo resolvió.

#### Actividad 16 — Práctica: Editar un usuario

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir los datos de un usuario (nombres, cargo, correo, entidad, departamentos o rol).

**Cuándo se hace y requisitos previos:** Secuencia E0.5; los mismos requisitos de Módulo 03 — Actividad 4.

**Dónde:** Usuarios › fila › ícono **Editar** (o **Detalle** › **Editar**) › ventana "Editar usuario".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 16.1 — Abrir la edición
**Objetivo del paso:** Cargar los datos actuales.
**Qué hacer:** En el ambiente de pruebas: En la fila del usuario haga clic en el ícono **Editar** (o abra **Detalle** y haga clic en **Editar**).
**Resultado esperado:** Se abre "Editar usuario" con los datos actuales.

##### Paso 16.2 — Cambiar los datos
**Objetivo del paso:** Corregir lo necesario.
**Qué hacer:** En el ambiente de pruebas: Modifique los campos que correspondan, con las mismas reglas de la invitación (Rol, Nivel de acceso, Entidad Central, Subdirección, Área, Departamentos, Nombres, Apellidos, Cargo, Correo electrónico).
**Resultado esperado:** Los campos quedan con los datos nuevos.

##### Paso 16.3 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Usuario actualizado con éxito — Se han guardado los cambios de {nombre}."

**Resultado esperado de la práctica:** El usuario queda con los datos nuevos; el cambio de alcance aplica en su siguiente ingreso.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El usuario queda con los datos nuevos; el cambio de alcance aplica en su siguiente ingreso.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 4 y lo resolvió.

#### Actividad 17 — Práctica: Activar o inactivar un usuario

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, impedir o restablecer el ingreso de un usuario cambiando su estado.

**Cuándo se hace y requisitos previos:** Secuencia E0.5; los mismos requisitos de Módulo 03 — Actividad 5.

**Dónde:** Usuarios › columna **Estado** › interruptor **Activo**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 17.1 — Ubicar al usuario
**Objetivo del paso:** Encontrar la fila correcta.
**Qué hacer:** En el ambiente de pruebas: Busque al usuario en la vista **Todos**.
**Resultado esperado:** Ve su fila con el interruptor.

##### Paso 17.2 — Cambiar el estado
**Objetivo del paso:** Activar o inactivar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el interruptor **Activo**.
**Resultado esperado:** Aparece "Estado actualizado — El usuario {nombre} ha sido {activado/desactivado} correctamente."

**Resultado esperado de la práctica:** Un usuario inactivo no puede iniciar sesión ("Cuenta no activa").

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Un usuario inactivo no puede iniciar sesión ("Cuenta no activa").
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 5 y lo resolvió.

#### Actividad 18 — Práctica: Reenviar o eliminar una invitación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, volver a enviar una invitación vencida o eliminar una invitación que no debe usarse.

**Cuándo se hace y requisitos previos:** Secuencia E0.5; los mismos requisitos de Módulo 03 — Actividad 6.

**Dónde:** Usuarios › vista **Invitaciones** › **Reenviar** / **Eliminar invitación**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 18.1 — Abrir Invitaciones
**Objetivo del paso:** Ver las invitaciones sin aceptar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la vista **Invitaciones**.
**Resultado esperado:** Aparecen las invitaciones Pendiente y Expirada.

##### Paso 18.2 — Reenviar
**Objetivo del paso:** Dar 7 días más al usuario.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Reenviar** (muestra "Reenviando...").
**Resultado esperado:** Aparece "Invitación reenviada — Se ha reenviado la invitación a {nombre} ({correo})." y la nueva fecha de expiración.

##### Paso 18.3 — Eliminar
**Objetivo del paso:** Retirar una invitación equivocada.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Eliminar invitación** y confirme en "Eliminar invitación — ¿Estás seguro de que deseas eliminar la invitación? Esta acción no se puede deshacer.".
**Resultado esperado:** Aparece "Invitación eliminada con éxito".

**Resultado esperado de la práctica:** La invitación queda vigente de nuevo o eliminada.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La invitación queda vigente de nuevo o eliminada.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 03 — Actividad 6 y lo resolvió.

#### Actividad 19 — Práctica: Recuperar la contraseña

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, crear una contraseña nueva cuando la olvidó, usando el enlace que llega a su correo.

**Cuándo se hace y requisitos previos:** Secuencia E0.6; los mismos requisitos de Módulo 01 — Actividad 3.

**Dónde:** Pantalla de ingreso › **¿Has olvidado tu contraseña?** (`/forgot-password`) › correo "SI-CIPRAT - Restablecer Contraseña" › "Configurar nueva contraseña" (`/reset-password/:token`).

**Datos de la práctica:** Usuario de prueba administrador.prueba@ejemplo.gov.co; contraseña nueva "Nueva#2026" (Mock).

**Pasos:**

##### Paso 19.1 — Abrir la recuperación
**Objetivo del paso:** Iniciar el proceso de cambio de contraseña.
**Qué hacer:** En el ambiente de pruebas: En la pantalla de ingreso haga clic en **¿Has olvidado tu contraseña?**.
**Resultado esperado:** Aparece "¿Olvidaste tu contraseña?".

##### Paso 19.2 — Escribir el correo
**Objetivo del paso:** Indicar a qué cuenta se enviará el enlace.
**Qué hacer:** En el ambiente de pruebas: En **Correo electrónico** escriba su correo institucional y haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Revisa tu correo electrónico" y llega el correo "SI-CIPRAT - Restablecer Contraseña".

##### Paso 19.3 — Abrir el enlace del correo
**Objetivo del paso:** Llegar a la pantalla de nueva contraseña antes de que venza.
**Qué hacer:** En el ambiente de pruebas: Abra el correo y haga clic en el enlace dentro de la hora siguiente.
**Resultado esperado:** Aparece "Configurar nueva contraseña". Si pasó más de 1 hora, al guardar aparece "Token inválido o expirado".

##### Paso 19.4 — Escribir y confirmar la nueva contraseña
**Objetivo del paso:** Definir una contraseña válida y distinta de las anteriores.
**Qué hacer:** En el ambiente de pruebas: Escriba en **Nueva Contraseña** al menos 8 caracteres con un carácter especial, distinta de sus últimas 5 contraseñas, y repítala en **Confirmar Contraseña**.
**Resultado esperado:** Los indicadores se marcan como cumplidos.

##### Paso 19.5 — Guardar la contraseña
**Objetivo del paso:** Dejar activa la nueva contraseña.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Restablecer contraseña**.
**Resultado esperado:** Aparece "Contraseña restablecida — Tu contraseña se ha restablecido correctamente. Haz clic abajo para iniciar sesión." con el botón **Iniciar Sesión**.

**Resultado esperado de la práctica:** La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La contraseña queda cambiada y registrada en el historial de contraseñas; el usuario inicia sesión con la nueva.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 01 — Actividad 3 y lo resolvió.

#### Actividad 20 — Práctica: Leer los indicadores del Inicio

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, interpretar los indicadores del Inicio (totales, tendencia y porcentaje de avance global) sobre las alertas de su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 1.

**Dónde:** Menú lateral › **Inicio** (`/inicio`).

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25] y alertas Mock.

**Pasos:**

##### Paso 20.1 — Abrir Inicio
**Objetivo del paso:** Ver el tablero de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inicio** en el menú lateral.
**Resultado esperado:** Aparecen las tarjetas, el avance global, el ranking y el mapa.

##### Paso 20.2 — Leer las tarjetas y su tendencia
**Objetivo del paso:** Saber cuántas alertas hay y cómo cambió el último mes.
**Qué hacer:** En el ambiente de pruebas: Lea el valor grande de cada tarjeta y el número "vs ultimo mes".
**Resultado esperado:** Identifica, por ejemplo, que hay 2 alertas activas más que el mes anterior.

##### Paso 20.3 — Interpretar el Porcentaje de Avance Global
**Objetivo del paso:** Entender el avance de los planes de acción.
**Qué hacer:** En el ambiente de pruebas: Lea el porcentaje y la línea "X de Y actividades ejecutadas". Recuerde que es un promedio por alerta y no la división del total.
**Resultado esperado:** Puede explicar por qué el porcentaje puede ser distinto de X/Y.

**Resultado esperado de la práctica:** Interpreta el estado general de las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Interpreta el estado general de las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 1 y lo resolvió.

#### Actividad 21 — Práctica: Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ubicar en el Inicio la última alerta emitida, los departamentos con más alertas, las alertas recientes y los municipios afectados en el mapa.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 2.

**Dónde:** Menú lateral › **Inicio**.

**Datos de la práctica:** Ambiente de pruebas con la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 21.1 — Abrir la última alerta
**Objetivo del paso:** Conocer la alerta activa más reciente.
**Qué hacer:** En el ambiente de pruebas: Lea el banner superior y haga clic en **Ver Alerta**.
**Resultado esperado:** Se abre la alerta en *Alertas tempranas*.

##### Paso 21.2 — Revisar el ranking de departamentos
**Objetivo del paso:** Saber dónde se concentran las alertas.
**Qué hacer:** En el ambiente de pruebas: Lea "Alertas por departamento" (Top 10).
**Resultado esperado:** Identifica los departamentos con más alertas y su porcentaje.

##### Paso 21.3 — Revisar las alertas recientes
**Objetivo del paso:** Ver lo último registrado.
**Qué hacer:** En el ambiente de pruebas: Recorra "Alertas recientes".
**Resultado esperado:** Ve las últimas alertas por fecha de la alerta.

##### Paso 21.4 — Usar el mapa
**Objetivo del paso:** Ubicar los municipios con alertas.
**Qué hacer:** En el ambiente de pruebas: Pase el cursor sobre un municipio coloreado; use la tabla accesible si prefiere leer los datos.
**Resultado esperado:** Aparece el nombre del municipio, el departamento y el número de alertas.

**Resultado esperado de la práctica:** Ubica geográficamente las alertas de su alcance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica geográficamente las alertas de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 2 y lo resolvió.

#### Actividad 22 — Práctica: Consultar el tablero público sin iniciar sesión

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, reconocer la vista pública de consulta ciudadana y diferenciarla de la vista con sesión.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 02 — Actividad 4.

**Dónde:** Dirección principal de SI-CIPRAT (`/`), sin iniciar sesión.

**Datos de la práctica:** Ventana privada del navegador.

**Pasos:**

##### Paso 22.1 — Abrir la vista pública
**Objetivo del paso:** Ver lo que ve la ciudadanía.
**Qué hacer:** En el ambiente de pruebas: Abra la dirección de la plataforma sin iniciar sesión (o en una ventana privada).
**Resultado esperado:** Aparece el tablero público con el botón **Iniciar sesión**.

##### Paso 22.2 — Comparar con su vista
**Objetivo del paso:** Entender la diferencia de alcance.
**Qué hacer:** En el ambiente de pruebas: Compare los totales con los de su Inicio con sesión, que se calculan sobre nacional.
**Resultado esperado:** Los totales coinciden: su alcance también es nacional.

**Resultado esperado de la práctica:** Sabe qué información es pública y cuál depende de su sesión.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué información es pública y cuál depende de su sesión.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 02 — Actividad 4 y lo resolvió.

#### Actividad 23 — Práctica: Consultar, buscar y filtrar alertas tempranas

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 04 — Actividad 1.

**Dónde:** Menú lateral › **Alertas tempranas** (`/alertas-tempranas`).

**Datos de la práctica:** Buscar "AT-013" [DATO REAL AT-013-25].

**Pasos:**

##### Paso 23.1 — Abrir Alertas tempranas
**Objetivo del paso:** Ver las alertas de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Alertas tempranas** en el menú lateral.
**Resultado esperado:** Aparecen "Cargando alertas..." y luego las tarjetas y la tabla.

##### Paso 23.2 — Leer las tarjetas
**Objetivo del paso:** Conocer los totales.
**Qué hacer:** En el ambiente de pruebas: Lea Total de alertas, Alertas activas y Alertas cerradas.
**Resultado esperado:** Conoce cuántas alertas hay en cada estado.

##### Paso 23.3 — Cambiar de pestaña
**Objetivo del paso:** Separar por tipo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Inminencia** o **Estructurales**; **Todas** quita el filtro.
**Resultado esperado:** La tabla muestra solo ese tipo.

##### Paso 23.4 — Buscar una alerta
**Objetivo del paso:** Ir directo a una alerta.
**Qué hacer:** En el ambiente de pruebas: Escriba el número (por ejemplo "AT-013") o una palabra del tema en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra; sin coincidencias: "No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo."

##### Paso 23.5 — Aplicar filtros
**Objetivo del paso:** Combinar criterios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Tipo, Estado, Etiqueta y las listas del conflicto, y haga clic en **Aplicar filtros**. Para quitar, **Limpiar filtros**.
**Resultado esperado:** El botón Filtros muestra cuántos filtros están activos y la tabla se actualiza.

##### Paso 23.6 — Abrir el menú de acciones
**Objetivo del paso:** Saber qué puede hacer con cada alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ al final de la fila.
**Resultado esperado:** Aparecen Detalle, Editar, Recomendaciones, Historial de actividades y Eliminar (Eliminar deshabilitado: "No tienes permisos para eliminar alertas").

**Resultado esperado de la práctica:** Ubica la alerta y sus datos principales.

**Lista de verificación:**
- [ ] Completó los 6 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica la alerta y sus datos principales.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 1 y lo resolvió.

#### Actividad 24 — Práctica: Ver el detalle de una alerta y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 04 — Actividad 2.

**Dónde:** Alertas tempranas › fila › ⋯ › **Detalle**.

**Datos de la práctica:** Abrir la AT-013-2025 y revisar GUAVIARE › Miraflores (95200) [DATO REAL AT-013-25].

**Pasos:**

##### Paso 24.1 — Abrir el detalle
**Objetivo del paso:** Ver la ficha completa.
**Qué hacer:** En el ambiente de pruebas: En la fila, haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ficha en la pestaña Información general.

##### Paso 24.2 — Revisar Información general
**Objetivo del paso:** Conocer el avance y el tema.
**Qué hacer:** En el ambiente de pruebas: Lea Ejecutado / Programado, el estado del Plan de acción y la Descripción.
**Resultado esperado:** Conoce el avance y el estado del plan.

##### Paso 24.3 — Descargar el PDF
**Objetivo del paso:** Consultar el documento oficial.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el archivo de "PDF de la alerta".
**Resultado esperado:** Se descarga el PDF. Si no hay archivo, la alerta no tiene PDF cargado.

##### Paso 24.4 — Recorrer las demás pestañas
**Objetivo del paso:** Conocer el territorio, el conflicto y la población.
**Qué hacer:** En el ambiente de pruebas: Abra Lugar de advertencia, Conflicto, Conductas vulneratorias e infracciones al D.I.H., Población afectada y Alertas subsumidas.
**Resultado esperado:** Ve los municipios (con CAT, PNIS, PDET y Zona Fut.), los grupos armados, las conductas, las poblaciones y las subsunciones.

##### Paso 24.5 — Cerrar la ficha
**Objetivo del paso:** Volver al listado.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cerrar**.
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Conoce la alerta completa.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la alerta completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 2 y lo resolvió.

#### Actividad 25 — Práctica: Consultar el historial de actividades de una alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre).

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 04 — Actividad 3.

**Dónde:** Alertas tempranas › fila › ⋯ › **Historial de actividades**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 25.1 — Abrir el historial
**Objetivo del paso:** Ver la trazabilidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Historial de actividades**.
**Resultado esperado:** Se abre la línea de tiempo de la alerta.

##### Paso 25.2 — Leer los eventos
**Objetivo del paso:** Reconstruir lo ocurrido.
**Qué hacer:** En el ambiente de pruebas: Recorra los eventos y use **Mostrar 10 mas** para ver los anteriores.
**Resultado esperado:** Identifica, por ejemplo, cuándo se confirmó el plan y quién lo hizo.

##### Paso 25.3 — Descargar un archivo del evento
**Objetivo del paso:** Ver el soporte de un cierre o informe.
**Qué hacer:** En el ambiente de pruebas: Si el evento tiene "Descargar archivo", haga clic.
**Resultado esperado:** Se descarga el archivo asociado.

**Resultado esperado de la práctica:** Conoce la trazabilidad de la alerta.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la trazabilidad de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 3 y lo resolvió.

#### Actividad 26 — Práctica: Descargar el listado de alertas en CSV

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados.

**Cuándo se hace y requisitos previos:** Secuencia E1–E6; los mismos requisitos de Módulo 04 — Actividad 4.

**Dónde:** Alertas tempranas › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 26.1 — Aplicar los filtros que necesita
**Objetivo del paso:** Descargar solo lo útil.
**Qué hacer:** En el ambiente de pruebas: Use la pestaña, el buscador y **Filtros**.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 26.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; ábralo en Excel.

**Resultado esperado de la práctica:** Tiene el listado en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene el listado en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 4 y lo resolvió.

#### Actividad 27 — Práctica: Revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, identificar las alertas automáticas en Borrador y revisarlas contra el documento antes de publicarlas.

**Cuándo se hace y requisitos previos:** Secuencia E1.1 / E1.2; los mismos requisitos de Módulo 04 — Actividad 5.

**Dónde:** Alertas tempranas › **Filtros** › Estado "Borrador" › fila › ⋯ › **Detalle**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 27.1 — Filtrar los borradores
**Objetivo del paso:** Encontrar lo pendiente de revisión.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros**, marque Estado "Borrador" y haga clic en **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo los borradores.

##### Paso 27.2 — Comparar con el documento
**Objetivo del paso:** Detectar errores de lectura automática.
**Qué hacer:** En el ambiente de pruebas: Abra el **Detalle** y compare número, fechas, tipo, etiqueta, municipios, grupos armados, conductas y población con el documento de la Defensoría.
**Resultado esperado:** Identifica lo que debe corregir.

##### Paso 27.3 — Pasar a la edición
**Objetivo del paso:** Corregir y publicar.
**Qué hacer:** En el ambiente de pruebas: Use ⋯ › **Editar** (actividad "Editar una alerta" y "Publicar una alerta en Borrador").
**Resultado esperado:** Se abre el formulario con los datos del borrador.

**Resultado esperado de la práctica:** El borrador queda revisado y listo para corregir y publicar.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El borrador queda revisado y listo para corregir y publicar.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 5 y lo resolvió.

#### Actividad 28 — Práctica: Reportar una alerta temprana

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, registrar manualmente una alerta temprana completa (6 pasos) para que quede Activa y se le puedan cargar las recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E1.3; los mismos requisitos de Módulo 04 — Actividad 7.

**Dónde:** Alertas tempranas › **Reportar alerta** › ventana "Reportar alerta temprana — Informa una alerta temprana y asigna las entidades involucradas para su atención y seguimiento.".

**Datos de la práctica:** Valores de la línea base [DATO REAL AT-013-25], con el número Mock AT-901-2026 porque la AT-013-2025 ya existe en el ambiente: fecha de la alerta 07/10/2025; fecha de notificación 07/10/2025; tipo Estructural; etiqueta Regional (en los scripts del repositorio figura "Nacional"); Tema Clave "Se prevé que los procesos electorales podrán desarrollarse con normalidad en la mayor parte del territorio nacional. Sin embargo, resulta factible…"; Lugar de advertencia: la línea base dice "Todos los municipios", que la pantalla no ofrece (cada municipio se agrega con **Agregar**): agregue CAUCA › Popayán y NARIÑO › Tumaco; Economías ilegales "Contrabando"; Grupos armados "Ejército de Liberación Nacional (ELN)" y "Tren de Aragua"; Conducta Vulneratoria "Amenazas" y "Extorsión"; Población afectada "Jóvenes" y "Candidatos/as a cargos de elección popular"; Alertas que subsume: ninguna. Varios valores de la línea base no existen tal cual en las listas (ver `analisis/05c_linea_base_vs_catalogos.md`).

**Pasos:**

##### Paso 28.1 — Buscar si la alerta ya existe
**Objetivo del paso:** Evitar duplicados con X-Road o el Agente IA.
**Qué hacer:** En el ambiente de pruebas: Busque el número en "Buscar por nombre", incluidas las alertas en Borrador.
**Resultado esperado:** Si existe, edítela en lugar de crearla.

##### Paso 28.2 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Reportar alerta** (desde un computador; en celular aparece "Disponible en escritorio").
**Resultado esperado:** Se abre "Reportar alerta temprana" en el Paso 1 de 6.

##### Paso 28.3 — Paso 1: escribir el número de la alerta
**Objetivo del paso:** Identificar la alerta con el formato que acepta el servidor.
**Qué hacer:** En el ambiente de pruebas: En **Número y fecha de alerta** escriba el número con el formato `AT-` + 3 caracteres + `-` + 4 caracteres, por ejemplo `AT-013-2025`. No use el formato del ejemplo de la pantalla ("Ej: AT-001-25").
**Resultado esperado:** El campo queda diligenciado (la pantalla no valida el formato; el servidor lo hará al enviar).

##### Paso 28.4 — Paso 1: elegir la fecha de la alerta y la fecha de notificación
**Objetivo del paso:** Registrar el día 0 del ciclo.
**Qué hacer:** En el ambiente de pruebas: Elija la fecha de la alerta en el calendario junto al número; en **Fecha de notificación** elija la fecha en que se notificó al CIPRAT. Verifique que la de notificación no sea anterior a la de la alerta.
**Resultado esperado:** Las fechas quedan registradas; la de notificación será la base del próximo informe (+6 meses).

##### Paso 28.5 — Paso 1: elegir el tipo y la etiqueta
**Objetivo del paso:** Clasificar la alerta.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Tipo de alerta** (Inminencia o Estructural) y **Etiqueta** (Nacional, Regional o Internacional) y elija.
**Resultado esperado:** Los dos valores quedan seleccionados.

##### Paso 28.6 — Paso 1: adjuntar el PDF y el adjunto
**Objetivo del paso:** Dejar el soporte oficial de la alerta.
**Qué hacer:** En el ambiente de pruebas: Los campos **PDF de la alerta** y **Adjunto** aparecen, pero su rol no puede subir archivos: déjelos vacíos y pida al Super Administrador que adjunte el PDF después de crear la alerta.
**Resultado esperado:** Si los adjunta, al final aparecerá "El PDF de la alerta no pudo ser subido.".

##### Paso 28.7 — Paso 1: escribir el Tema Clave
**Objetivo del paso:** Resumir el riesgo advertido.
**Qué hacer:** En el ambiente de pruebas: En **Tema Clave** escriba la descripción del documento (opcional, sin límite).
**Resultado esperado:** El texto queda registrado.

##### Paso 28.8 — Avanzar al Paso 2
**Objetivo del paso:** Validar el Paso 1.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Siguiente**.
**Resultado esperado:** Si falta un dato obligatorio aparece su mensaje ("El número de alerta es requerido", "La etiqueta es requerida"…); si no, pasa al Paso 2 de 6.

##### Paso 28.9 — Paso 2: agregar los municipios (Lugar de advertencia)
**Objetivo del paso:** Registrar dónde aplica la alerta.
**Qué hacer:** En el ambiente de pruebas: Elija el **Departamento** ("Selecciona un departamento"), luego el **Municipio**; repita por cada municipio del documento.
**Resultado esperado:** Cada municipio aparece en la tabla con Cod DANE, CAT, PNIS, PDET y Zona Fut.; sin municipios: "No hay ubicaciones agregadas. Agrega al menos una ubicación para continuar."

##### Paso 28.10 — Paso 3: Conflicto
**Objetivo del paso:** Registrar economías ilegales y grupos armados.
**Qué hacer:** En el ambiente de pruebas: En **Economías ilegales** marque las que apliquen (opcional). En **Grupos armados ilegales** marque al menos uno (use "Sin determinar" si el documento no lo precisa). Use los buscadores. Haga clic en **Siguiente**.
**Resultado esperado:** Sin grupo armado: "Debe seleccionar al menos un grupo armado ilegal".

##### Paso 28.11 — Paso 4: Conductas vulneratorias
**Objetivo del paso:** Registrar las conductas advertidas.
**Qué hacer:** En el ambiente de pruebas: En **Conducta Vulneratoria** marque al menos una (use "Otra" si no está). Haga clic en **Siguiente**.
**Resultado esperado:** Sin selección: "Debe seleccionar al menos una conducta vulneratoria".

##### Paso 28.12 — Paso 5: Población afectada
**Objetivo del paso:** Registrar la población en riesgo.
**Qué hacer:** En el ambiente de pruebas: En **Población afectada** marque al menos una. Haga clic en **Siguiente**.
**Resultado esperado:** Sin selección: "Debe seleccionar al menos una población afectada".

##### Paso 28.13 — Paso 6: Subsunción (si aplica)
**Objetivo del paso:** Indicar si esta alerta reemplaza a otras.
**Qué hacer:** En el ambiente de pruebas: Solo si el documento lo indica, active **Esta alerta subsume otras alertas** y elija las **Alertas subsumidas**.
**Resultado esperado:** Aparece "Al confirmar, las alertas seleccionadas se subsumirán en esta alerta y cambiarán su estado a 'Cerrada'."

##### Paso 28.14 — Revisar antes de enviar
**Objetivo del paso:** Evitar errores difíciles de corregir después.
**Qué hacer:** En el ambiente de pruebas: Use **Atrás** para revisar cada paso, en especial el número (año con 4 dígitos), las fechas y los municipios.
**Resultado esperado:** Los datos coinciden con el documento.

##### Paso 28.15 — Enviar la alerta
**Objetivo del paso:** Registrar la alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Enviar Alerta**.
**Resultado esperado:** Aparece "Alerta {número} reportada con éxito" y "La alerta {número} se encuentra lista para su carga junto con las recomendaciones correspondientes."; la alerta queda Activa. Si el formato del número no es válido, aparece el error del servidor.

**Resultado esperado de la práctica:** La alerta queda Activa, con modo de creación Manual y el evento "created" en su historial. El siguiente paso es cargar sus recomendaciones (módulo Recomendaciones).

**Lista de verificación:**
- [ ] Completó los 15 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La alerta queda Activa, con modo de creación Manual y el evento "created" en su historial. El siguiente paso es cargar sus recomendaciones (módulo Recomendaciones).
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 7 y lo resolvió.

#### Actividad 29 — Práctica: Editar una alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir los datos de una alerta mientras no esté cerrada, subsumida ni con el plan confirmado.

**Cuándo se hace y requisitos previos:** Secuencia E1.5; los mismos requisitos de Módulo 04 — Actividad 8.

**Dónde:** Alertas tempranas › ⋯ › **Editar** (o **Detalle** › **Editar**) › "Editar alerta temprana — Actualiza la información de la alerta temprana.".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 29.1 — Abrir la edición
**Objetivo del paso:** Cargar la alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Editar**.
**Resultado esperado:** Se abre el asistente con los datos; si la alerta está cerrada aparece "Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada."

##### Paso 29.2 — Corregir el Paso 1
**Objetivo del paso:** Ajustar número, fechas, tipo, etiqueta, archivos o tema.
**Qué hacer:** En el ambiente de pruebas: Modifique los campos necesarios. El número aparece bloqueado ("No tienes permisos para editar el número de alerta").
**Resultado esperado:** Los campos muestran los nuevos valores.

##### Paso 29.3 — Corregir los Pasos 2 a 5
**Objetivo del paso:** Ajustar municipios, conflicto, conductas y población.
**Qué hacer:** En el ambiente de pruebas: Avance con **Siguiente** y agregue o quite municipios y opciones.
**Resultado esperado:** Se mantienen al menos una ubicación, un grupo armado, una conducta y una población.

##### Paso 29.4 — Revisar el Paso 6
**Objetivo del paso:** Confirmar subsunción y publicación.
**Qué hacer:** En el ambiente de pruebas: Revise **Esta alerta subsume otras alertas** y, si la alerta es un borrador, **Publicar alerta al guardar**.
**Resultado esperado:** Las opciones quedan como corresponde.

##### Paso 29.5 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Alerta actualizada con éxito — Los cambios han sido guardados correctamente."

**Resultado esperado de la práctica:** La alerta queda actualizada y el cambio aparece en su historial ("updated").

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La alerta queda actualizada y el cambio aparece en su historial ("updated").
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 8 y lo resolvió.

#### Actividad 30 — Práctica: Publicar una alerta en Borrador

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, pasar a Activa una alerta en Borrador después de revisarla.

**Cuándo se hace y requisitos previos:** Secuencia E1.5; los mismos requisitos de Módulo 04 — Actividad 9.

**Dónde:** Alertas tempranas › alerta en Borrador › ⋯ › **Editar** › Paso 6 › **Publicar alerta al guardar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 30.1 — Revisar y corregir el borrador
**Objetivo del paso:** Publicar datos correctos.
**Qué hacer:** En el ambiente de pruebas: Abra **Editar** y corrija los Pasos 1 a 5.
**Resultado esperado:** El borrador queda correcto.

##### Paso 30.2 — Activar la publicación
**Objetivo del paso:** Indicar que debe pasar a Activa.
**Qué hacer:** En el ambiente de pruebas: En el Paso 6 active **Publicar alerta al guardar**.
**Resultado esperado:** El interruptor queda activo.

##### Paso 30.3 — Guardar
**Objetivo del paso:** Publicar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar Cambios**.
**Resultado esperado:** Aparece "Alerta publicada con éxito — Los cambios han sido guardados y la alerta ha sido publicada."; el estado cambia a Activa.

**Resultado esperado de la práctica:** La alerta queda Activa, cuenta en los indicadores y queda lista para sus recomendaciones; historial "published".

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La alerta queda Activa, cuenta en los indicadores y queda lista para sus recomendaciones; historial "published".
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 9 y lo resolvió.

#### Actividad 31 — Práctica: Subsumir alertas

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, registrar que una alerta nueva reemplaza a otras alertas activas, que quedan cerradas.

**Cuándo se hace y requisitos previos:** Secuencia E1.6; los mismos requisitos de Módulo 04 — Actividad 10.

**Dónde:** Reportar o Editar alerta › Paso 6 › **Esta alerta subsume otras alertas** › Alertas subsumidas.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 31.1 — Activar la subsunción
**Objetivo del paso:** Habilitar la selección.
**Qué hacer:** En el ambiente de pruebas: En el Paso 6 active **Esta alerta subsume otras alertas**.
**Resultado esperado:** Aparece la lista Alertas subsumidas.

##### Paso 31.2 — Elegir las alertas
**Objetivo del paso:** Indicar cuáles se reemplazan.
**Qué hacer:** En el ambiente de pruebas: Busque y marque las alertas que el documento declara subsumidas.
**Resultado esperado:** Aparece "Al confirmar, las alertas seleccionadas se subsumirán en esta alerta y cambiarán su estado a 'Cerrada'."

##### Paso 31.3 — Guardar
**Objetivo del paso:** Aplicar la subsunción.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Enviar Alerta** o **Guardar Cambios**.
**Resultado esperado:** Las alertas subsumidas pasan a Cerrada y aparecen en la pestaña "Alertas subsumidas" del detalle.

**Resultado esperado de la práctica:** Las alertas subsumidas quedan Cerradas y vinculadas a la nueva.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Las alertas subsumidas quedan Cerradas y vinculadas a la nueva.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 10 y lo resolvió.

#### Actividad 32 — Práctica: Ir a las recomendaciones de una alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, pasar de una alerta a su lista de recomendaciones.

**Cuándo se hace y requisitos previos:** Secuencia E2; los mismos requisitos de Módulo 04 — Actividad 6.

**Dónde:** Alertas tempranas › fila › ⋯ › **Recomendaciones** (`/alertas-tempranas/:id/recomendaciones`).

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 32.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver qué se le recomienda a cada entidad.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Recomendaciones**.
**Resultado esperado:** Se abre la lista de recomendaciones (módulo Recomendaciones).

##### Paso 32.2 — Volver
**Objetivo del paso:** Regresar al listado de alertas.
**Qué hacer:** En el ambiente de pruebas: Haga clic en "Volver a Alertas Tempranas".
**Resultado esperado:** Vuelve a la tabla de alertas.

**Resultado esperado de la práctica:** Llega a las recomendaciones de la alerta.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Llega a las recomendaciones de la alerta.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 04 — Actividad 6 y lo resolvió.

#### Actividad 33 — Práctica: Consultar, buscar y filtrar las recomendaciones de una alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ver las recomendaciones de una alerta con su entidad, sus actividades y su avance.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 05 — Actividad 1.

**Dónde:** Alertas tempranas › ⋯ › **Recomendaciones**.

**Datos de la práctica:** Recomendaciones de la AT-013-2025: RC-001-2025-013 a RC-041-2025-013 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 33.1 — Abrir las recomendaciones
**Objetivo del paso:** Ver la lista.
**Qué hacer:** En el ambiente de pruebas: Desde la alerta, ⋯ › **Recomendaciones**.
**Resultado esperado:** Aparece "Cargando recomendaciones..." y luego la tabla.

##### Paso 33.2 — Buscar
**Objetivo del paso:** Encontrar una recomendación.
**Qué hacer:** En el ambiente de pruebas: Escriba el código (por ejemplo "RC-001") o una palabra en "Buscar por nombre".
**Resultado esperado:** La tabla se filtra.

##### Paso 33.3 — Filtrar
**Objetivo del paso:** Ver por entidad, eje o modo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Entidad Principal, Eje Temático o Modo de Creación y **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo lo filtrado.

##### Paso 33.4 — Leer el avance
**Objetivo del paso:** Saber cómo va cada recomendación.
**Qué hacer:** En el ambiente de pruebas: Lea Actividades (Aprobadas / Total) y Ejecución.
**Resultado esperado:** Identifica las recomendaciones sin actividades o con bajo cumplimiento.

**Resultado esperado de la práctica:** Conoce las recomendaciones de la alerta y su avance.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce las recomendaciones de la alerta y su avance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 1 y lo resolvió.

#### Actividad 34 — Práctica: Ver el detalle de una recomendación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 05 — Actividad 2.

**Dónde:** Recomendaciones › fila › ⋯ › **Detalle**.

**Datos de la práctica:** RC-011-2025-013 ("Recomendación No. 12…") [DATO REAL AT-013-25].

**Pasos:**

##### Paso 34.1 — Abrir el detalle
**Objetivo del paso:** Ver la recomendación completa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Detalle**.
**Resultado esperado:** Se abre la ventana.

##### Paso 34.2 — Leer las entidades
**Objetivo del paso:** Saber quién responde y quién apoya.
**Qué hacer:** En el ambiente de pruebas: Lea la Entidad principal y las Entidades asociadas.
**Resultado esperado:** Identifica a la entidad responsable del plan y a las que apoyan.

**Resultado esperado de la práctica:** Conoce la recomendación completa.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce la recomendación completa.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 2 y lo resolvió.

#### Actividad 35 — Práctica: Descargar las recomendaciones de una alerta en CSV

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, descargar las recomendaciones visibles en un archivo CSV.

**Cuándo se hace y requisitos previos:** Secuencia E2–E6; los mismos requisitos de Módulo 05 — Actividad 3.

**Dónde:** Recomendaciones › **Descargar**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 35.1 — Filtrar
**Objetivo del paso:** Descargar lo necesario.
**Qué hacer:** En el ambiente de pruebas: Aplique búsqueda y filtros.
**Resultado esperado:** La tabla muestra lo que se descargará.

##### Paso 35.2 — Descargar
**Objetivo del paso:** Obtener el archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV; si falla: "Error al descargar el archivo CSV. Por favor, intente nuevamente."

**Resultado esperado de la práctica:** Tiene las recomendaciones en un archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene las recomendaciones en un archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 3 y lo resolvió.

#### Actividad 36 — Práctica: Agregar una recomendación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, registrar una recomendación de la alerta con su eje, su descripción, su Entidad Principal y sus entidades asociadas, para que la entidad formule su plan.

**Cuándo se hace y requisitos previos:** Secuencia E2.1; los mismos requisitos de Módulo 05 — Actividad 4.

**Dónde:** Recomendaciones › **Agregar recomendación** › ventana "Agregar recomendación — Registra una recomendación y asigna las entidades responsables para su notificación y seguimiento.".

**Datos de la práctica:** En la alerta Mock AT-901-2026, con los valores de RC-003-2025-013 [DATO REAL AT-013-25]: Eje temático "Coordinación de Respuesta Rápida"; Entidad Principal "MinInterior - Democracia y Participación"; Descripción "Recomendación No. 4 Categoría temática de la recomendación: Coordinación de la respuesta rápida Entidad Principal Concernida: Ministerio del Interior -,…".

**Pasos:**

##### Paso 36.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Agregar recomendación**.
**Resultado esperado:** Se abre el Paso 1.

##### Paso 36.2 — Elegir el eje temático
**Objetivo del paso:** Clasificar la recomendación.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Eje temático** y elija el eje del documento (14 opciones).
**Resultado esperado:** El eje queda seleccionado.

##### Paso 36.3 — Escribir la descripción
**Objetivo del paso:** Registrar el texto de la recomendación.
**Qué hacer:** En el ambiente de pruebas: En **Descripción** pegue el texto de la recomendación. Buena práctica: empiece por "Recomendación No. X" del documento para conservar la referencia (hallazgo H3).
**Resultado esperado:** El texto queda registrado (sin límite de longitud).

##### Paso 36.4 — Agregar la Entidad Principal
**Objetivo del paso:** Definir quién responde.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Siguiente**; en **Entidad Principal** busque ("Buscar entidad...") y elija la entidad responsable.
**Resultado esperado:** La entidad aparece en la lista. Si agrega varias, se creará una recomendación por cada una.

##### Paso 36.5 — Asociar entidades
**Objetivo del paso:** Registrar quién apoya.
**Qué hacer:** En el ambiente de pruebas: Para la entidad principal, use **Asociar entidades** y marque las entidades de apoyo.
**Resultado esperado:** Las asociadas aparecen bajo la principal; recibirán correo pero no verán la recomendación.

##### Paso 36.6 — Revisar
**Objetivo del paso:** Evitar duplicados.
**Qué hacer:** En el ambiente de pruebas: Verifique que haya una sola Entidad Principal si la recomendación es una sola.
**Resultado esperado:** Los datos son correctos.

##### Paso 36.7 — Crear
**Objetivo del paso:** Registrar y notificar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Crear recomendación**.
**Resultado esperado:** Aparece "Recomendación creada — La recomendación ha sido registrada correctamente." (o "Se han creado {N} recomendaciones correctamente."); se asigna el código RC y se envía el correo a las entidades.

**Resultado esperado de la práctica:** La recomendación queda en estado "sin actividad" con su código RC; la Entidad Territorial recibe "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" y el plan de la alerta pasa a "Sin plan".

**Lista de verificación:**
- [ ] Completó los 7 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La recomendación queda en estado "sin actividad" con su código RC; la Entidad Territorial recibe "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" y el plan de la alerta pasa a "Sin plan".
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 4 y lo resolvió.

#### Actividad 37 — Práctica: Editar una recomendación

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir el eje, la descripción o las entidades de una recomendación antes de la confirmación del plan.

**Cuándo se hace y requisitos previos:** Secuencia E2.3; los mismos requisitos de Módulo 05 — Actividad 5.

**Dónde:** Recomendaciones › ⋯ › **Editar** › "Editar recomendación — Actualiza la información de la recomendación y las entidades responsables.".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 37.1 — Abrir la edición
**Objetivo del paso:** Cargar la recomendación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en ⋯ › **Editar**.
**Resultado esperado:** Se abre el asistente con los datos.

##### Paso 37.2 — Corregir los datos
**Objetivo del paso:** Ajustar eje, descripción y entidades.
**Qué hacer:** En el ambiente de pruebas: Modifique **Eje temático**, **Descripción**, **Entidad Principal** o **Entidades asociadas**.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 37.3 — Guardar
**Objetivo del paso:** Aplicar y notificar.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Recomendación actualizada — Los cambios han sido guardados correctamente." y se envía "SI-CIPRAT - Recomendacion Actualizada: {código}".

**Resultado esperado de la práctica:** La recomendación queda actualizada y notificada.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: La recomendación queda actualizada y notificada.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 05 — Actividad 5 y lo resolvió.

#### Actividad 38 — Práctica: Consultar y filtrar los planes de acción por alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 06 — Actividad 1.

**Dónde:** Menú lateral › **Planes de acción** (`/planes-de-accion`) › pestaña **Alertas**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 38.1 — Abrir Planes de acción
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Planes de acción**.
**Resultado esperado:** Aparece la pestaña **Alertas**.

##### Paso 38.2 — Leer el estado y el cumplimiento
**Objetivo del paso:** Saber qué plan está pendiente o aprobado.
**Qué hacer:** En el ambiente de pruebas: Lea las columnas Cumplimiento, Plan de acción e Informe.
**Resultado esperado:** Identifica, por ejemplo, los planes "Sin plan" que aún no tienen actividades.

##### Paso 38.3 — Filtrar
**Objetivo del paso:** Ver solo lo que le interesa.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Filtros**, elija Estado del Plan de Acción, Estado del Informe o Porcentaje de Cumplimiento y **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 38.4 — Ver el detalle del plan
**Objetivo del paso:** Revisar la información de la alerta y el historial del plan.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono de detalle de la fila.
**Resultado esperado:** Se abre la ficha con "Información de alerta" e "Historial Plan de acción".

##### Paso 38.5 — Descargar el listado
**Objetivo del paso:** Tener el estado en un archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga un CSV con Número de Alerta, Cumplimiento (%) y Plan de Acción.

**Resultado esperado de la práctica:** Conoce el estado de los planes de su alcance.

**Lista de verificación:**
- [ ] Completó los 5 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el estado de los planes de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 1 y lo resolvió.

#### Actividad 39 — Práctica: Recorrer las recomendaciones del plan de una alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 06 — Actividad 2.

**Dónde:** Planes de acción › fila › **Ir al plan de acción** (`/planes-de-accion/:id/recomendaciones`).

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 39.1 — Entrar al plan
**Objetivo del paso:** Ver las recomendaciones de la alerta.
**Qué hacer:** En el ambiente de pruebas: En la fila de la alerta haga clic en **Ir al plan de acción**.
**Resultado esperado:** Aparece la tabla de recomendaciones.

##### Paso 39.2 — Abrir el detalle de una recomendación
**Objetivo del paso:** Ver su información y su historial.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono de detalle y recorra **Información**, **Actividades** e **Historial**.
**Resultado esperado:** Ve la recomendación, sus actividades y los eventos del plan.

##### Paso 39.3 — Ir a las actividades
**Objetivo del paso:** Trabajar las actividades de la recomendación.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver Actividades**.
**Resultado esperado:** Se abre la lista de actividades de la recomendación.

**Resultado esperado de la práctica:** Llega a las actividades de la recomendación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Llega a las actividades de la recomendación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 2 y lo resolvió.

#### Actividad 40 — Práctica: Consultar las pestañas globales de Recomendaciones y Actividades

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 06 — Actividad 3.

**Dónde:** Planes de acción › pestañas **Recomendaciones** y **Actividades**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 40.1 — Abrir Recomendaciones
**Objetivo del paso:** Ver todas las recomendaciones.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la pestaña **Recomendaciones**.
**Resultado esperado:** Aparece la tabla global.

##### Paso 40.2 — Abrir Actividades
**Objetivo del paso:** Ver todas las actividades.
**Qué hacer:** En el ambiente de pruebas: Haga clic en la pestaña **Actividades**.
**Resultado esperado:** Aparece la tabla global de actividades.

##### Paso 40.3 — Filtrar y descargar
**Objetivo del paso:** Obtener un listado específico.
**Qué hacer:** En el ambiente de pruebas: Use **Filtros** (por ejemplo, Estado "Pendiente Aprobación") y luego **Descargar**.
**Resultado esperado:** Se descarga el CSV filtrado.

**Resultado esperado de la práctica:** Tiene la vista global de su alcance.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene la vista global de su alcance.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 3 y lo resolvió.

#### Actividad 41 — Práctica: Consultar las actividades de una recomendación y su detalle

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer cada actividad de una recomendación, su estado, su avance y su próximo informe.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 06 — Actividad 4.

**Dónde:** Planes de acción › **Ir al plan de acción** › **Ver Actividades** (`/planes-de-accion/:id/recomendaciones/:recomendacionId/actividades`); el detalle, en la tabla de recomendaciones › ícono de detalle › pestaña **Actividades**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 41.1 — Abrir las actividades
**Objetivo del paso:** Ver la lista.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver Actividades** de la recomendación.
**Resultado esperado:** Aparece "Cargando actividades..." y luego la tabla.

##### Paso 41.2 — Buscar y filtrar
**Objetivo del paso:** Encontrar una actividad.
**Qué hacer:** En el ambiente de pruebas: Escriba en "Buscar por objetivo" o use **Filtros**.
**Resultado esperado:** La tabla se filtra.

##### Paso 41.3 — Ver el detalle
**Objetivo del paso:** Leer la actividad completa.
**Qué hacer:** En el ambiente de pruebas: Vuelva a la tabla de recomendaciones, haga clic en el ícono de detalle de la recomendación y abra la pestaña **Actividades**.
**Resultado esperado:** Ve el detalle de la actividad; con varias actividades puede cambiar con "Seleccionar actividad".

##### Paso 41.4 — Descargar
**Objetivo del paso:** Tener las actividades en un archivo.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV de actividades.

**Resultado esperado de la práctica:** Conoce el detalle y el avance de las actividades.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el detalle y el avance de las actividades.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 4 y lo resolvió.

#### Actividad 42 — Práctica: Consultar el Informe de recomendaciones

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer el avance consolidado de alertas, recomendaciones y actividades, y el cumplimiento por Entidad Principal y por Eje temático.

**Cuándo se hace y requisitos previos:** Secuencia E3–E5; los mismos requisitos de Módulo 08 — Actividad 1.

**Dónde:** Planes de acción o Seguimiento › botón **Informe** (`/planes-de-accion/informe-recomendaciones` o `/seguimiento/informe-recomendaciones`).

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 42.1 — Abrir el informe
**Objetivo del paso:** Ver el consolidado.
**Qué hacer:** En el ambiente de pruebas: En Planes de acción o en Seguimiento haga clic en **Informe**.
**Resultado esperado:** Aparece el tablero con los tres bloques.

##### Paso 42.2 — Filtrar por alerta
**Objetivo del paso:** Ver el consolidado de una alerta.
**Qué hacer:** En el ambiente de pruebas: En "Todas las alertas" elija una alerta.
**Resultado esperado:** Los bloques y la tabla se recalculan para esa alerta.

##### Paso 42.3 — Comparar por entidad y por eje
**Objetivo del paso:** Identificar rezagos.
**Qué hacer:** En el ambiente de pruebas: Cambie entre **Entidad** y **Eje tematico** y ordene mentalmente por % Avance.
**Resultado esperado:** Identifica las entidades o ejes con menor avance.

**Resultado esperado de la práctica:** Conoce el avance consolidado de las recomendaciones.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el avance consolidado de las recomendaciones.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 08 — Actividad 1 y lo resolvió.

#### Actividad 43 — Práctica: Consultar el listado de Seguimiento y encontrar lo pendiente

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5; los mismos requisitos de Módulo 07 — Actividad 1.

**Dónde:** Menú lateral › **Seguimiento** (`/seguimiento`) — pantalla "Seguimiento de Planes".

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 43.1 — Abrir Seguimiento
**Objetivo del paso:** Ver los planes de su alcance.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Seguimiento**.
**Resultado esperado:** Aparece "Seguimiento de Planes".

##### Paso 43.2 — Filtrar lo pendiente
**Objetivo del paso:** Encontrar el trabajo.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros**: Estado del Plan de Acción "Pendiente" (actividades por aprobar) o "Aprobado" (listo para confirmar); Estado del Informe "Pendiente" (informes por aprobar). **Aplicar filtros**.
**Resultado esperado:** La tabla muestra solo esos planes.

##### Paso 43.3 — Descargar el listado
**Objetivo del paso:** Llevar el control fuera de línea.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar**.
**Resultado esperado:** Se descarga el CSV.

##### Paso 43.4 — Entrar al plan
**Objetivo del paso:** Llegar a las actividades.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ir al plan de acción** y luego **Ver Actividades** en la recomendación.
**Resultado esperado:** Ve las actividades en modo de seguimiento.

**Resultado esperado de la práctica:** Sabe qué planes, actividades e informes requieren atención.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Sabe qué planes, actividades e informes requieren atención.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 07 — Actividad 1 y lo resolvió.

#### Actividad 44 — Práctica: Consultar recomendaciones, actividades e informes en Seguimiento

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución.

**Cuándo se hace y requisitos previos:** Secuencia E4–E5; los mismos requisitos de Módulo 07 — Actividad 2.

**Dónde:** Seguimiento › **Ir al plan de acción** › **Ver Actividades** › ícono **Ver detalle** de la fila.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 44.1 — Abrir las actividades
**Objetivo del paso:** Llegar a la información.
**Qué hacer:** En el ambiente de pruebas: En Seguimiento haga clic en **Ir al plan de acción** › **Ver Actividades**.
**Resultado esperado:** Aparece la tabla de actividades.

##### Paso 44.2 — Abrir el detalle
**Objetivo del paso:** Leer la actividad y sus informes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en el ícono **Ver detalle** de la fila.
**Resultado esperado:** Se abre "Detalle de Actividad" con los informes de ejecución y su PDF.

##### Paso 44.3 — Leer los informes de ejecución
**Objetivo del paso:** Conocer lo reportado por la entidad.
**Qué hacer:** En el ambiente de pruebas: Baje a "Informes de ejecución" y descargue "Informe.pdf" si lo necesita.
**Resultado esperado:** Conoce lo ejecutado en cada ciclo.

**Resultado esperado de la práctica:** Conoce el estado de las actividades y sus informes.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el estado de las actividades y sus informes.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 07 — Actividad 2 y lo resolvió.

#### Actividad 45 — Práctica: Consultar los informes de ejecución de una actividad y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer los informes reportados de una actividad, con todos sus campos y su archivo.

**Cuándo se hace y requisitos previos:** Secuencia E5; los mismos requisitos de Módulo 06 — Actividad 5.

**Dónde:** Planes de acción › **Ir al plan de acción** › ícono de detalle de la recomendación › pestaña **Actividades** › sección **Informes de ejecución**.

**Datos de la práctica:** Plan de la AT-013-2025 con las 20 actividades de la línea base cargadas en el ambiente de pruebas: RC-003-2025-013 (1), RC-004-2025-013 (11), RC-021-2025-013 (4), RC-022-2025-013 (3) y RC-023-2025-013 (1) [DATO REAL AT-013-25]. Las otras 36 recomendaciones quedan "Sin plan" (pendiente: plan de mitigación no disponible). Los informes de ejecución son Mock (pendiente: plan de mitigación no disponible).

**Pasos:**

##### Paso 45.1 — Abrir el detalle de la actividad
**Objetivo del paso:** Llegar a los informes.
**Qué hacer:** En el ambiente de pruebas: En la tabla de recomendaciones haga clic en el ícono de detalle y abra la pestaña **Actividades**.
**Resultado esperado:** Ve el detalle de la actividad.

##### Paso 45.2 — Leer los informes
**Objetivo del paso:** Conocer lo reportado.
**Qué hacer:** En el ambiente de pruebas: Baje a "Informes de ejecución" y lea cada informe.
**Resultado esperado:** Ve los datos y el estado de cada informe.

##### Paso 45.3 — Descargar el PDF
**Objetivo del paso:** Revisar el soporte.
**Qué hacer:** En el ambiente de pruebas: Haga clic en "Informe.pdf".
**Resultado esperado:** Se descarga el archivo; sin archivo: "No hay archivos adjuntos".

**Resultado esperado de la práctica:** Conoce los informes de la actividad y su soporte.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los informes de la actividad y su soporte.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 06 — Actividad 5 y lo resolvió.

#### Actividad 46 — Práctica: Consultar, buscar y filtrar los reportes de ejecución

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar los reportes de ejecución publicados, su tipo, su estado y su aprobador.

**Cuándo se hace y requisitos previos:** Secuencia E5.6; los mismos requisitos de Módulo 09 — Actividad 1.

**Dónde:** Menú lateral › **Reportes** (`/reportes`).

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 46.1 — Abrir Reportes
**Objetivo del paso:** Ver los reportes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Reportes**.
**Resultado esperado:** Aparece "Cargando reportes..." y luego la tabla.

##### Paso 46.2 — Cambiar de pestaña
**Objetivo del paso:** Ver un tipo de reporte.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Alerta**, **Entidad** o **Regional**.
**Resultado esperado:** La tabla muestra ese tipo.

##### Paso 46.3 — Filtrar
**Objetivo del paso:** Encontrar un reporte.
**Qué hacer:** En el ambiente de pruebas: Use "Buscar por nombre" o **Filtros** › **Aplicar filtros**.
**Resultado esperado:** La tabla se filtra; sin datos: "No hay reportes de ejecucion".

**Resultado esperado de la práctica:** Ubica los reportes y su estado.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Ubica los reportes y su estado.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 09 — Actividad 1 y lo resolvió.

#### Actividad 47 — Práctica: Ver el detalle de un reporte y descargarlo

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, leer un reporte de ejecución y descargar su PDF.

**Cuándo se hace y requisitos previos:** Secuencia E5.6; los mismos requisitos de Módulo 09 — Actividad 2.

**Dónde:** Reportes › fila › **Ver detalles** / **Descargar reporte**.

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 47.1 — Abrir el detalle
**Objetivo del paso:** Leer el reporte.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalles**.
**Resultado esperado:** Se abre el detalle.

##### Paso 47.2 — Descargar
**Objetivo del paso:** Obtener el PDF.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Descargar reporte** en la fila (o en el adjunto del detalle).
**Resultado esperado:** Se descarga el PDF; sin archivo: "No hay archivo disponible".

**Resultado esperado de la práctica:** Conoce el reporte y tiene su archivo.

**Lista de verificación:**
- [ ] Completó los 2 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce el reporte y tiene su archivo.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 09 — Actividad 2 y lo resolvió.

#### Actividad 48 — Práctica: Cargar un reporte de ejecución

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, publicar un reporte de ejecución consolidado con su PDF y designar a quien lo aprueba.

**Cuándo se hace y requisitos previos:** Secuencia E5.6; los mismos requisitos de Módulo 09 — Actividad 3.

**Dónde:** Reportes › **Cargar informe** › ventana "Cargar informe de seguimiento — Reportar Reportes de ejecución para dar visibilidad sobre la ejecución." (el título de la ventana dice "informe de seguimiento", aunque carga un reporte de ejecución).

**Datos de la práctica:** Reporte Mock tipo Alerta AT-901-2026, aprobador "Líder de Macrozona de prueba".

**Pasos:**

##### Paso 48.1 — Abrir el formulario
**Objetivo del paso:** Iniciar la carga.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cargar informe**.
**Resultado esperado:** Se abre la ventana.

##### Paso 48.2 — Elegir el tipo
**Objetivo del paso:** Definir qué consolida el reporte.
**Qué hacer:** En el ambiente de pruebas: Despliegue **Tipo** y elija Alerta, Entidad, Depto o Municipio.
**Resultado esperado:** Aparece el campo de alcance correspondiente.

##### Paso 48.3 — Elegir el alcance
**Objetivo del paso:** Indicar la alerta, entidad o territorio.
**Qué hacer:** En el ambiente de pruebas: Según el tipo: busque la **Alerta**; o la **Entidad**; o el **Departamento**; o el Departamento y el **Municipio**.
**Resultado esperado:** Si falta: "Debe seleccionar una alerta", "Debe seleccionar una entidad", "Debe seleccionar un departamento" o "Debe seleccionar un municipio".

##### Paso 48.4 — Elegir la fecha y el aprobador
**Objetivo del paso:** Fechar el reporte y designar quién aprueba.
**Qué hacer:** En el ambiente de pruebas: Elija la **Fecha de reporte** y en **Aprobador** busque ("Buscar por nombre o email...") al Líder de Macrozona (o al Super Administrador) que aprobará.
**Resultado esperado:** Solo aparecen usuarios activos que pueden aprobar.

##### Paso 48.5 — Escribir la descripción
**Objetivo del paso:** Resumir el reporte.
**Qué hacer:** En el ambiente de pruebas: Escriba la **Descripción** (máx. 2.000 caracteres).
**Resultado esperado:** Si excede: "La descripción no puede exceder 2000 caracteres".

##### Paso 48.6 — Adjuntar el PDF
**Objetivo del paso:** Publicar el documento.
**Qué hacer:** En el ambiente de pruebas: En **Adjunto** suba el PDF del reporte.
**Resultado esperado:** Sin archivo: "El archivo PDF es requerido".

##### Paso 48.7 — Cargar
**Objetivo del paso:** Publicar y notificar al aprobador.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cargar informe**.
**Resultado esperado:** Aparece "Reporte creado — El reporte de ejecución se ha cargado exitosamente"; el reporte queda "Sin aprobación".

**Resultado esperado de la práctica:** El reporte queda "Sin aprobación" y el aprobador recibe "Reporte de ejecución pendiente de su aprobación – SI-CIPRAT".

**Lista de verificación:**
- [ ] Completó los 7 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El reporte queda "Sin aprobación" y el aprobador recibe "Reporte de ejecución pendiente de su aprobación – SI-CIPRAT".
- [ ] Provocó a propósito al menos un escenario de error de Módulo 09 — Actividad 3 y lo resolvió.

#### Actividad 49 — Práctica: Editar un reporte de ejecución

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir los datos o el PDF de un reporte de ejecución.

**Cuándo se hace y requisitos previos:** Secuencia E5.6; los mismos requisitos de Módulo 09 — Actividad 4.

**Dónde:** Reportes › **Ver detalles** › **Editar** › ventana "Editar informe de seguimiento — Modifica los datos del reporte de ejecución.".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 49.1 — Abrir la edición
**Objetivo del paso:** Cargar el reporte.
**Qué hacer:** En el ambiente de pruebas: Abra **Ver detalles** y haga clic en **Editar**.
**Resultado esperado:** Se abre el formulario con los datos.

##### Paso 49.2 — Corregir
**Objetivo del paso:** Ajustar el reporte.
**Qué hacer:** En el ambiente de pruebas: Modifique Tipo, Alerta, Entidad, Departamento, Municipio, Fecha de reporte, Aprobador, Descripción o Adjunto.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 49.3 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Reporte actualizado — El reporte de ejecución se ha actualizado exitosamente".

**Resultado esperado de la práctica:** El reporte queda actualizado.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El reporte queda actualizado.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 09 — Actividad 4 y lo resolvió.

#### Actividad 50 — Práctica: Generar un informe ejecutivo en Word (Panel de consultas)

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, descargar un informe ejecutivo en Word por alerta, entidad, departamento, municipio o general.

**Cuándo se hace y requisitos previos:** Secuencia E5.8; los mismos requisitos de Módulo 09 — Actividad 5.

**Dónde:** Reportes › **Consultas** › "Panel de consultas — Descarga informes sobre el seguimiento y ejecucion".

**Datos de la práctica:** Consulta tipo Alerta con la AT-013-2025 [DATO REAL AT-013-25] o la AT-901-2026 (Mock).

**Pasos:**

##### Paso 50.1 — Abrir el Panel de consultas
**Objetivo del paso:** Iniciar la consulta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Consultas**.
**Resultado esperado:** Se abre "Panel de consultas".

##### Paso 50.2 — Elegir el tipo y el alcance
**Objetivo del paso:** Definir el informe.
**Qué hacer:** En el ambiente de pruebas: Elija **Tipo de consulta** (Alerta, Entidad, Depto, Municipio o General) y su **Alerta**, **Entidad**, **Departamento** o **Municipio**.
**Resultado esperado:** Si falta: "El tipo de consulta es requerido" o el mensaje del campo.

##### Paso 50.3 — Generar
**Objetivo del paso:** Descargar el documento.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Generar consulta**.
**Resultado esperado:** Aparece "Informe generado — El documento Word se ha descargado exitosamente".

**Resultado esperado de la práctica:** Tiene el informe ejecutivo en Word con los datos de la alerta, el avance por entidad y las dificultades.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Tiene el informe ejecutivo en Word con los datos de la alerta, el avance por entidad y las dificultades.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 09 — Actividad 5 y lo resolvió.

#### Actividad 51 — Práctica: Consultar los informes de seguimiento y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1; los mismos requisitos de Módulo 10 — Actividad 1.

**Dónde:** Menú lateral › **Informes de seguimiento** ("Encuentra los informes de seguimiento publicados por la defensoría").

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 51.1 — Abrir el módulo
**Objetivo del paso:** Ver los informes.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Informes de seguimiento**.
**Resultado esperado:** Aparece "Cargando informes..." y luego la tabla; sin datos: "No hay informes de seguimiento — Los informes de seguimiento publicados por la defensoría aparecerán aquí."

##### Paso 51.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros** y elija la Alerta asociada (la lista muestra alertas cerradas: "No se encontraron alertas cerradas").
**Resultado esperado:** La tabla se filtra.

##### Paso 51.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el informe.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalle** y luego en **Descargar**.
**Resultado esperado:** Se abre el detalle y se descarga el PDF.

**Resultado esperado de la práctica:** Conoce los informes de seguimiento.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los informes de seguimiento.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 10 — Actividad 1 y lo resolvió.

#### Actividad 52 — Práctica: Cargar un informe de seguimiento y aplicar sus cambios a la alerta

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, registrar un informe de seguimiento de la Defensoría con su PDF y aplicar sus efectos: cerrar o agregar municipios, agregar recomendaciones o cerrar la alerta.

**Cuándo se hace y requisitos previos:** Secuencia E6.1; los mismos requisitos de Módulo 10 — Actividad 2.

**Dónde:** Informes de seguimiento › **Cargar informe** › ventana "Cargar informe de seguimiento — Registra un nuevo informe de seguimiento para una alerta.".

**Datos de la práctica:** Informe Mock IS-901-26 sobre la AT-901-2026: cerrar Popayán, agregar Timbío.

**Pasos:**

##### Paso 52.1 — Abrir el formulario
**Objetivo del paso:** Iniciar el registro.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cargar informe**.
**Resultado esperado:** Se abre el Paso 1.

##### Paso 52.2 — Escribir el número y elegir la alerta
**Objetivo del paso:** Identificar el informe.
**Qué hacer:** En el ambiente de pruebas: Escriba el **Número de informe** (por ejemplo "IS-001-25") y busque la **Alerta asociada**.
**Resultado esperado:** Si el número ya existe, al guardar: "Ya existe un informe con el número…".

##### Paso 52.3 — Elegir las fechas y el radicado
**Objetivo del paso:** Registrar los datos del documento.
**Qué hacer:** En el ambiente de pruebas: Elija la **Fecha de notificación** (obligatoria) y la **Fecha de emisión**; escriba el **Número de radicado** (por ejemplo "RAD-2025-00456").
**Resultado esperado:** Los campos quedan diligenciados.

##### Paso 52.4 — Adjuntar el PDF
**Objetivo del paso:** Dejar el soporte.
**Qué hacer:** En el ambiente de pruebas: Suba el **PDF del informe**.
**Resultado esperado:** Sin archivo: "El archivo PDF es requerido".

##### Paso 52.5 — Paso 2: marcar municipios cerrados
**Objetivo del paso:** Reflejar los municipios donde ya no aplica la alerta.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Siguiente**; en "Municipios actuales de la alerta" use **Marcar como cerrado** en los que indique el informe.
**Resultado esperado:** Los municipios quedan marcados para cerrar.

##### Paso 52.6 — Paso 2: agregar municipios
**Objetivo del paso:** Ampliar la alerta si el informe lo indica.
**Qué hacer:** En el ambiente de pruebas: En "Agregar nuevos municipios" elija departamento y municipio.
**Resultado esperado:** Aparecen en "Municipios a agregar".

##### Paso 52.7 — Paso 2: agregar recomendaciones
**Objetivo del paso:** Registrar recomendaciones nuevas del informe.
**Qué hacer:** En el ambiente de pruebas: En **Recomendaciones** use **Agregar** y diligencie Eje tematico, Descripción y Entidad principal; puede editarlas o eliminarlas antes de guardar.
**Resultado esperado:** Aparecen en la lista ("Se crearan al guardar el informe.").

##### Paso 52.8 — Paso 2: decidir el cierre
**Objetivo del paso:** Cerrar la alerta si el informe lo dispone.
**Qué hacer:** En el ambiente de pruebas: No marque **Cerrar la alerta con este informe**: su rol no puede cerrar alertas y el sistema rechazará el informe. Pida el cierre al Super Administrador.
**Resultado esperado:** Aparece "Si marca esta opcion, la alerta pasara a estado cerrada al guardar el informe."

##### Paso 52.9 — Cargar
**Objetivo del paso:** Registrar el informe y aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Cargar informe**.
**Resultado esperado:** Aparece "Informe de seguimiento creado — El informe ha sido registrado exitosamente"; se aplican los cambios y se envía el correo a las entidades.

**Resultado esperado de la práctica:** El informe queda registrado; los municipios y las recomendaciones nuevas se aplican (las recomendaciones generan el correo de recomendación asignada) y, si se marcó, la alerta queda Cerrada. Las entidades reciben "Notificación informe de seguimiento – Alerta Temprana N° {número}".

**Lista de verificación:**
- [ ] Completó los 9 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El informe queda registrado; los municipios y las recomendaciones nuevas se aplican (las recomendaciones generan el correo de recomendación asignada) y, si se marcó, la alerta queda Cerrada. Las entidades reciben "Notificación informe de seguimiento – Alerta Temprana N° {número}".
- [ ] Provocó a propósito al menos un escenario de error de Módulo 10 — Actividad 2 y lo resolvió.

#### Actividad 53 — Práctica: Editar un informe de seguimiento

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, corregir los datos o el PDF de un informe de seguimiento.

**Cuándo se hace y requisitos previos:** Secuencia E6.1; los mismos requisitos de Módulo 10 — Actividad 3.

**Dónde:** Informes de seguimiento › **Editar informe** › "Editar informe de seguimiento — Modifica los datos del informe de seguimiento.".

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 53.1 — Abrir la edición
**Objetivo del paso:** Cargar el informe.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Editar informe**.
**Resultado esperado:** Se abre el asistente.

##### Paso 53.2 — Corregir el Paso 1
**Objetivo del paso:** Ajustar los datos del documento.
**Qué hacer:** En el ambiente de pruebas: Modifique Número de informe, Fecha de notificación, Fecha de emisión, Número de radicado o el PDF del informe.
**Resultado esperado:** Los campos muestran el cambio.

##### Paso 53.3 — Revisar el Paso 2
**Objetivo del paso:** Ajustar las modificaciones si la alerta sigue abierta.
**Qué hacer:** En el ambiente de pruebas: Revise municipios, recomendaciones y la casilla de cierre.
**Resultado esperado:** Si la alerta está cerrada: "Esta alerta ya se encuentra cerrada…".

##### Paso 53.4 — Guardar
**Objetivo del paso:** Aplicar los cambios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Guardar cambios**.
**Resultado esperado:** Aparece "Informe de seguimiento actualizado — El informe ha sido actualizado exitosamente".

**Resultado esperado de la práctica:** El informe queda corregido.

**Lista de verificación:**
- [ ] Completó los 4 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: El informe queda corregido.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 10 — Actividad 3 y lo resolvió.

#### Actividad 54 — Práctica: Consultar los oficios de consumación y descargar su PDF

**Objetivo de la actividad:** Que el Administrador pueda practicar, en el ambiente de pruebas, encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento.

**Cuándo se hace y requisitos previos:** Secuencia E6.2; los mismos requisitos de Módulo 11 — Actividad 1.

**Dónde:** Menú lateral › **Oficios de consumación** ("Encuentra los oficios de consumación emitidos por la defensoría").

**Datos de la práctica:** Datos Mock del ambiente de pruebas (alerta AT-901-2026 y entidades "de Prueba"); para consultas puede usar la AT-013-2025 [DATO REAL AT-013-25].

**Pasos:**

##### Paso 54.1 — Abrir el módulo
**Objetivo del paso:** Ver los oficios.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Oficios de consumación**.
**Resultado esperado:** Aparece la tabla; sin datos: "No hay oficios de consumación — Los oficios de consumación emitidos por la defensoría aparecerán aquí."

##### Paso 54.2 — Filtrar por alerta
**Objetivo del paso:** Ver los de una alerta.
**Qué hacer:** En el ambiente de pruebas: Abra **Filtros** y elija la Alerta asociada.
**Resultado esperado:** La tabla se filtra.

##### Paso 54.3 — Ver el detalle y descargar
**Objetivo del paso:** Leer el oficio.
**Qué hacer:** En el ambiente de pruebas: Haga clic en **Ver detalle** y en **Descargar**.
**Resultado esperado:** Se descarga el PDF.

**Resultado esperado de la práctica:** Conoce los oficios de consumación.

**Lista de verificación:**
- [ ] Completó los 3 pasos sin mensajes de error no previstos.
- [ ] El resultado coincide con: Conoce los oficios de consumación.
- [ ] Provocó a propósito al menos un escenario de error de Módulo 11 — Actividad 1 y lo resolvió.

## Alcance y límites

- Alcance de datos: todas las alertas del país, sin filtro de entidad ni de departamento.
- Acciones que comparte con otros roles (cada uno con su alcance): iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad; invitar un usuario; editar un usuario; activar o inactivar un usuario; reenviar una invitación.
- ⚠️ Acciones irreversibles que puede hacer: activar la cuenta desde la invitación; eliminar una invitación; eliminar una entidad; publicar una alerta en borrador; subsumir otras alertas.
- Módulos a los que no tiene acceso: Agentes IA.
- No puede: cambiar la contraseña con la contraseña actual; editar los datos del propio perfil; consultar el historial de cambios de contraseña; invitar un super administrador; crear una alerta desde pdf con el agente ia; consultar el historial de procesamiento; adjuntar el pdf de la alerta y el adjunto; cambiar el número de una alerta manual; eliminar una alerta; reemplazar o eliminar los archivos de la alerta; cerrar alertas; eliminar una recomendación; agregar una actividad; agregar una actividad a un plan confirmado; editar una actividad; y las demás de la tabla "Qué NO puede hacer".
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
- [ ] Puede revisar en el panel Notificaciones lo que ha pasado en las alertas de su alcance (quién hizo qué y cuándo) (Módulo 12 — Actividad 1).
- [ ] Puede identificar qué correos le llegan por su rol y qué acción debe tomar con cada uno (Módulo 12 — Actividad 2).
- [ ] Puede encontrar a cualquier usuario o invitación y saber en qué estado está (Módulo 03 — Actividad 1).
- [ ] Puede revisar todos los datos de acceso de un usuario antes de editarlo o de responder una consulta (Módulo 03 — Actividad 2).
- [ ] Puede crear un usuario con el rol y el alcance correctos y enviarle la invitación por correo (Módulo 03 — Actividad 3).
- [ ] Puede corregir los datos de un usuario (nombres, cargo, correo, entidad, departamentos o rol) (Módulo 03 — Actividad 4).
- [ ] Puede impedir o restablecer el ingreso de un usuario cambiando su estado (Módulo 03 — Actividad 5).
- [ ] Puede volver a enviar una invitación vencida o eliminar una invitación que no debe usarse (Módulo 03 — Actividad 6).
- [ ] Puede encontrar una entidad central o una subdirección y ver sus usuarios (Módulo 03 — Actividad 7).
- [ ] Puede registrar una entidad central con su categoría y sus subdirecciones para poder asignarla a usuarios y recomendaciones (Módulo 03 — Actividad 8).
- [ ] Puede corregir el nombre o la categoría de una entidad y agregar o quitar subdirecciones (Módulo 03 — Actividad 9).
- [ ] Puede eliminar una entidad creada por error que no tiene información relacionada (Módulo 03 — Actividad 10).
- [ ] Puede encontrar cualquier alerta de su alcance, conocer su estado y su avance, y usar los filtros (Módulo 04 — Actividad 1).
- [ ] Puede leer toda la información de una alerta (lugares, conflicto, conductas, población, subsunciones y avance) y descargar su PDF (Módulo 04 — Actividad 2).
- [ ] Puede saber quién hizo qué y cuándo sobre una alerta (registro, recomendaciones, actividades, aprobaciones, confirmación, informes y cierre) (Módulo 04 — Actividad 3).
- [ ] Puede descargar en un archivo CSV las alertas que está viendo, con los filtros aplicados (Módulo 04 — Actividad 4).
- [ ] Puede identificar las alertas automáticas en Borrador y revisarlas contra el documento antes de publicarlas (Módulo 04 — Actividad 5).
- [ ] Puede pasar de una alerta a su lista de recomendaciones (Módulo 04 — Actividad 6).
- [ ] Puede registrar manualmente una alerta temprana completa (6 pasos) para que quede Activa y se le puedan cargar las recomendaciones (Módulo 04 — Actividad 7).
- [ ] Puede corregir los datos de una alerta mientras no esté cerrada, subsumida ni con el plan confirmado (Módulo 04 — Actividad 8).
- [ ] Puede pasar a Activa una alerta en Borrador después de revisarla (Módulo 04 — Actividad 9).
- [ ] Puede registrar que una alerta nueva reemplaza a otras alertas activas, que quedan cerradas (Módulo 04 — Actividad 10).
- [ ] Puede ver las recomendaciones de una alerta con su entidad, sus actividades y su avance (Módulo 05 — Actividad 1).
- [ ] Puede leer la recomendación completa con su eje, su entidad principal y sus entidades asociadas (Módulo 05 — Actividad 2).
- [ ] Puede descargar las recomendaciones visibles en un archivo CSV (Módulo 05 — Actividad 3).
- [ ] Puede registrar una recomendación de la alerta con su eje, su descripción, su Entidad Principal y sus entidades asociadas, para que la entidad formule su plan (Módulo 05 — Actividad 4).
- [ ] Puede corregir el eje, la descripción o las entidades de una recomendación antes de la confirmación del plan (Módulo 05 — Actividad 5).
- [ ] Puede ver en qué estado está el plan de acción de cada alerta de su alcance y cuánto se ha ejecutado (Módulo 06 — Actividad 1).
- [ ] Puede entrar al plan de una alerta, ver sus recomendaciones con el avance y abrir el detalle con sus pestañas Información, Actividades e Historial (Módulo 06 — Actividad 2).
- [ ] Puede ver de una vez todas las recomendaciones o todas las actividades de su alcance, filtrarlas y descargarlas (Módulo 06 — Actividad 3).
- [ ] Puede leer cada actividad de una recomendación, su estado, su avance y su próximo informe (Módulo 06 — Actividad 4).
- [ ] Puede leer los informes reportados de una actividad, con todos sus campos y su archivo (Módulo 06 — Actividad 5).
- [ ] Puede ubicar en Seguimiento los planes con actividades o informes por revisar en su alcance (Módulo 07 — Actividad 1).
- [ ] Puede leer, en modo de seguimiento, las recomendaciones, las actividades con su detalle y sus informes de ejecución (Módulo 07 — Actividad 2).
- [ ] Puede leer el avance consolidado de alertas, recomendaciones y actividades, y el cumplimiento por Entidad Principal y por Eje temático (Módulo 08 — Actividad 1).
- [ ] Puede encontrar los reportes de ejecución publicados, su tipo, su estado y su aprobador (Módulo 09 — Actividad 1).
- [ ] Puede leer un reporte de ejecución y descargar su PDF (Módulo 09 — Actividad 2).
- [ ] Puede publicar un reporte de ejecución consolidado con su PDF y designar a quien lo aprueba (Módulo 09 — Actividad 3).
- [ ] Puede corregir los datos o el PDF de un reporte de ejecución (Módulo 09 — Actividad 4).
- [ ] Puede descargar un informe ejecutivo en Word por alerta, entidad, departamento, municipio o general (Módulo 09 — Actividad 5).
- [ ] Puede encontrar los informes de seguimiento de la Defensoría, leer su contenido y descargar el documento (Módulo 10 — Actividad 1).
- [ ] Puede registrar un informe de seguimiento de la Defensoría con su PDF y aplicar sus efectos: cerrar o agregar municipios, agregar recomendaciones o cerrar la alerta (Módulo 10 — Actividad 2).
- [ ] Puede corregir los datos o el PDF de un informe de seguimiento (Módulo 10 — Actividad 3).
- [ ] Puede encontrar los oficios de consumación del riesgo, leer sus datos y descargar el documento (Módulo 11 — Actividad 1).

## Preguntas frecuentes de uso

### Mi rol y lo que veo

**¿Qué puedo hacer con mi rol?**
Rol de gestión operativa nacional. Registra y edita alertas, crea y edita recomendaciones, carga y edita informes de seguimiento, carga reportes de ejecución y administra usuarios y entidades. No elimina alertas ni recomendaciones, no cierra alertas, no aprueba actividades, informes ni reportes y no sube archivos de la alerta. En la plataforma puede, entre otras: iniciar sesión con correo y contraseña; validar el código de verificación; reenviar el código de verificación; activar la cuenta desde la invitación; solicitar el restablecimiento de la contraseña; restablecer la contraseña con el enlace; cerrar sesión; usar el panel de accesibilidad. *Se explica en: Módulo 00 — Actividad 3.*

**¿Qué información veo y por qué?**
Ve todas las alertas del país, sin filtro de entidad ni de departamento. El sistema aplica ese filtro en el servidor según los datos de su usuario. *Se explica en: Módulo 01 — Actividad 6.*

**¿Cómo verifico con qué datos fui configurado?**
En **Ver Perfil** (Mi perfil) revise Rol, Nivel de Acceso, Entidad Central, Subdirección y Departamentos. Si algo no corresponde, pida la corrección a quien administra los usuarios. *Se explica en: Módulo 01 — Actividad 6.*

### Módulos y funcionalidades

**¿Para qué sirve el módulo Acceso a la plataforma?**
Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. *Se explica en: Módulo 01 — Actividad 1.*

**¿Para qué sirve el módulo Inicio?**
Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. Tablero de entrada de la plataforma. *Se explica en: Módulo 02 — Actividad 1.*

**¿Para qué sirve el módulo Usuarios y entidades?**
Preparar la plataforma con las entidades responsables y los usuarios correctos, cada uno con el rol y el alcance que le corresponde. Módulo de administración de las cuentas y de las organizaciones. *Se explica en: Módulo 03 — Actividad 1.*

**¿Para qué sirve el módulo Alertas tempranas?**
Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. *Se explica en: Módulo 04 — Actividad 1.*

**¿Para qué sirve el módulo Recomendaciones?**
Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). *Se explica en: Módulo 05 — Actividad 1.*

**¿Para qué sirve el módulo Planes de acción?**
Que cada entidad responsable formule las actividades con las que atenderá sus recomendaciones y reporte periódicamente lo ejecutado. Módulo donde se formula y se ejecuta el plan de acción. *Se explica en: Módulo 06 — Actividad 1.*

**¿Para qué sirve el módulo Seguimiento?**
Revisar y aprobar el plan de acción y su ejecución, actividad por actividad, hasta confirmar el plan y aprobar cada informe. Módulo "Seguimiento de Planes": usa las mismas pantallas de Planes de acción en modo de seguimiento. *Se explica en: Módulo 07 — Actividad 1.*

**¿Para qué sirve el módulo Informe de recomendaciones?**
Ver en un solo tablero el avance consolidado de las recomendaciones por entidad y por eje temático. Tablero "Informe de recomendaciones — Tablero de seguimiento a las recomendaciones", que se abre con el botón **Informe** de Planes de acción o de Seguimiento. *Se explica en: Módulo 08 — Actividad 1.*

**¿Para qué sirve el módulo Reportes?**
Consolidar y aprobar la información de ejecución para darle visibilidad institucional y producir informes ejecutivos. Módulo "Reportes de ejecución": publica reportes de ejecución consolidados por alerta, entidad, departamento o municipio, con su PDF y un aprobador designado; permite listarlos por pestañas (Todos, Alerta, Entidad, Regional), filtrarlos, ver su detalle, descargarlos, editarlos, eliminarlos y aprobarlos. *Se explica en: Módulo 09 — Actividad 1.*

**¿Para qué sirve el módulo Informes de seguimiento?**
Dejar en el sistema cada informe de seguimiento de la Defensoría y aplicar sus efectos sobre la alerta (municipios, recomendaciones nuevas o cierre). Módulo donde se registran los informes de seguimiento que emite la Defensoría sobre una alerta. *Se explica en: Módulo 10 — Actividad 1.*

**¿Para qué sirve el módulo Oficios de consumación?**
Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. *Se explica en: Módulo 11 — Actividad 1.*

**¿Para qué sirve el módulo Notificaciones?**
Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación).. *Se explica en: Módulo 12 — Actividad 1.*

**¿Cuándo debo consultar, buscar y filtrar usuarios e invitaciones?**
En la secuencia E0.5 del ciclo. Ubica el usuario o la invitación y su estado.. *Se explica en: Módulo 03 — Actividad 1.*

**¿Cuándo debo ver el detalle de un usuario?**
En la secuencia E0.5 del ciclo. Conoce los datos y el alcance del usuario.. *Se explica en: Módulo 03 — Actividad 2.*

**¿Cuándo debo invitar un usuario?**
En la secuencia E0.2 del ciclo. El usuario queda en "Invitación pendiente" con 7 días para activar su cuenta y recibe el correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas".. *Se explica en: Módulo 03 — Actividad 3.*

**¿Cuándo debo editar un usuario?**
En la secuencia E0.5 del ciclo. El usuario queda con los datos nuevos; el cambio de alcance aplica en su siguiente ingreso.. *Se explica en: Módulo 03 — Actividad 4.*

**¿Cuándo debo activar o inactivar un usuario?**
En la secuencia E0.5 del ciclo. Un usuario inactivo no puede iniciar sesión ("Cuenta no activa").. *Se explica en: Módulo 03 — Actividad 5.*

**¿Cuándo debo reenviar o eliminar una invitación?**
En la secuencia E0.5 del ciclo. La invitación queda vigente de nuevo o eliminada.. *Se explica en: Módulo 03 — Actividad 6.*

**¿Cuándo debo consultar, buscar y filtrar entidades?**
En la secuencia E0.1 del ciclo. Ubica la entidad, sus subdirecciones y sus usuarios.. *Se explica en: Módulo 03 — Actividad 7.*

**¿Cuándo debo agregar una entidad con sus subdirecciones?**
En la secuencia E0.1 del ciclo. La entidad queda Activa y disponible para usuarios y recomendaciones.. *Se explica en: Módulo 03 — Actividad 8.*

**¿Cuándo debo editar una entidad y sus subdirecciones?**
En la secuencia E0.1 del ciclo. La entidad queda actualizada en toda la plataforma.. *Se explica en: Módulo 03 — Actividad 9.*

**¿Cuándo debo eliminar una entidad?**
En la secuencia E0.1 del ciclo. La entidad deja de aparecer (borrado lógico).. *Se explica en: Módulo 03 — Actividad 10.*

**¿Cuándo debo consultar, buscar y filtrar alertas tempranas?**
En la secuencia E1–E6 del ciclo. Ubica la alerta y sus datos principales.. *Se explica en: Módulo 04 — Actividad 1.*

**¿Cuándo debo ver el detalle de una alerta y descargar su PDF?**
En la secuencia E1–E6 del ciclo. Conoce la alerta completa.. *Se explica en: Módulo 04 — Actividad 2.*

**¿Cuándo debo consultar el historial de actividades de una alerta?**
En la secuencia E1–E6 del ciclo. Conoce la trazabilidad de la alerta.. *Se explica en: Módulo 04 — Actividad 3.*

**¿Cuándo debo descargar el listado de alertas en CSV?**
En la secuencia E1–E6 del ciclo. Tiene el listado en un archivo.. *Se explica en: Módulo 04 — Actividad 4.*

**¿Cuándo debo revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA?**
En la secuencia E1.1 / E1.2 del ciclo. El borrador queda revisado y listo para corregir y publicar.. *Se explica en: Módulo 04 — Actividad 5.*

**¿Cuándo debo ir a las recomendaciones de una alerta?**
En la secuencia E2 del ciclo. Llega a las recomendaciones de la alerta.. *Se explica en: Módulo 04 — Actividad 6.*

**¿Cuándo debo reportar una alerta temprana?**
En la secuencia E1.3 del ciclo. La alerta queda Activa, con modo de creación Manual y el evento "created" en su historial. *Se explica en: Módulo 04 — Actividad 7.*

**¿Cuándo debo editar una alerta?**
En la secuencia E1.5 del ciclo. La alerta queda actualizada y el cambio aparece en su historial ("updated").. *Se explica en: Módulo 04 — Actividad 8.*

**¿Cuándo debo publicar una alerta en Borrador?**
En la secuencia E1.5 del ciclo. La alerta queda Activa, cuenta en los indicadores y queda lista para sus recomendaciones; historial "published".. *Se explica en: Módulo 04 — Actividad 9.*

**¿Cuándo debo subsumir alertas?**
En la secuencia E1.6 del ciclo. Las alertas subsumidas quedan Cerradas y vinculadas a la nueva.. *Se explica en: Módulo 04 — Actividad 10.*

**¿Cuándo debo consultar, buscar y filtrar las recomendaciones de una alerta?**
En la secuencia E2–E6 del ciclo. Conoce las recomendaciones de la alerta y su avance.. *Se explica en: Módulo 05 — Actividad 1.*

**¿Cuándo debo ver el detalle de una recomendación?**
En la secuencia E2–E6 del ciclo. Conoce la recomendación completa.. *Se explica en: Módulo 05 — Actividad 2.*

**¿Cuándo debo descargar las recomendaciones de una alerta en CSV?**
En la secuencia E2–E6 del ciclo. Tiene las recomendaciones en un archivo.. *Se explica en: Módulo 05 — Actividad 3.*

**¿Cuándo debo agregar una recomendación?**
En la secuencia E2.1 del ciclo. La recomendación queda en estado "sin actividad" con su código RC; la Entidad Territorial recibe "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" y el plan de la alerta pasa a "Sin plan".. *Se explica en: Módulo 05 — Actividad 4.*

**¿Cuándo debo editar una recomendación?**
En la secuencia E2.3 del ciclo. La recomendación queda actualizada y notificada.. *Se explica en: Módulo 05 — Actividad 5.*

**¿Cuándo debo consultar y filtrar los planes de acción por alerta?**
En la secuencia E3–E5 del ciclo. Conoce el estado de los planes de su alcance.. *Se explica en: Módulo 06 — Actividad 1.*

**¿Cuándo debo recorrer las recomendaciones del plan de una alerta?**
En la secuencia E3–E5 del ciclo. Llega a las actividades de la recomendación.. *Se explica en: Módulo 06 — Actividad 2.*

**¿Cuándo debo consultar las pestañas globales de Recomendaciones y Actividades?**
En la secuencia E3–E5 del ciclo. Tiene la vista global de su alcance.. *Se explica en: Módulo 06 — Actividad 3.*

**¿Cuándo debo consultar las actividades de una recomendación y su detalle?**
En la secuencia E3–E5 del ciclo. Conoce el detalle y el avance de las actividades.. *Se explica en: Módulo 06 — Actividad 4.*

**¿Cuándo debo consultar los informes de ejecución de una actividad y descargar su PDF?**
En la secuencia E5 del ciclo. Conoce los informes de la actividad y su soporte.. *Se explica en: Módulo 06 — Actividad 5.*

**¿Cuándo debo consultar el listado de Seguimiento y encontrar lo pendiente?**
En la secuencia E4–E5 del ciclo. Sabe qué planes, actividades e informes requieren atención.. *Se explica en: Módulo 07 — Actividad 1.*

**¿Cuándo debo consultar recomendaciones, actividades e informes en Seguimiento?**
En la secuencia E4–E5 del ciclo. Conoce el estado de las actividades y sus informes.. *Se explica en: Módulo 07 — Actividad 2.*

**¿Cuándo debo consultar el Informe de recomendaciones?**
En la secuencia E3–E5 del ciclo. Conoce el avance consolidado de las recomendaciones.. *Se explica en: Módulo 08 — Actividad 1.*

**¿Cuándo debo consultar, buscar y filtrar los reportes de ejecución?**
En la secuencia E5.6 del ciclo. Ubica los reportes y su estado.. *Se explica en: Módulo 09 — Actividad 1.*

**¿Cuándo debo ver el detalle de un reporte y descargarlo?**
En la secuencia E5.6 del ciclo. Conoce el reporte y tiene su archivo.. *Se explica en: Módulo 09 — Actividad 2.*

**¿Cuándo debo cargar un reporte de ejecución?**
En la secuencia E5.6 del ciclo. El reporte queda "Sin aprobación" y el aprobador recibe "Reporte de ejecución pendiente de su aprobación – SI-CIPRAT".. *Se explica en: Módulo 09 — Actividad 3.*

**¿Cuándo debo editar un reporte de ejecución?**
En la secuencia E5.6 del ciclo. El reporte queda actualizado.. *Se explica en: Módulo 09 — Actividad 4.*

**¿Cuándo debo generar un informe ejecutivo en Word (Panel de consultas)?**
En la secuencia E5.8 del ciclo. Tiene el informe ejecutivo en Word con los datos de la alerta, el avance por entidad y las dificultades.. *Se explica en: Módulo 09 — Actividad 5.*

**¿Cuándo debo consultar los informes de seguimiento y descargar su PDF?**
En la secuencia E6.1 del ciclo. Conoce los informes de seguimiento.. *Se explica en: Módulo 10 — Actividad 1.*

**¿Cuándo debo cargar un informe de seguimiento y aplicar sus cambios a la alerta?**
En la secuencia E6.1 del ciclo. El informe queda registrado; los municipios y las recomendaciones nuevas se aplican (las recomendaciones generan el correo de recomendación asignada) y, si se marcó, la alerta queda Cerrada. *Se explica en: Módulo 10 — Actividad 2.*

**¿Cuándo debo editar un informe de seguimiento?**
En la secuencia E6.1 del ciclo. El informe queda corregido.. *Se explica en: Módulo 10 — Actividad 3.*

**¿Cuándo debo consultar los oficios de consumación y descargar su PDF?**
En la secuencia E6.2 del ciclo. Conoce los oficios de consumación.. *Se explica en: Módulo 11 — Actividad 1.*

### Ciclo de la alerta y estados

**¿Qué significa el estado "Borrador"?**
Alerta creada por el Agente IA o por X-Road que aún no se publica; no cuenta en los indicadores. *Se explica en: Módulo 04 — Actividad 1.*

**¿Qué significa el estado "Activa"?**
Alerta vigente sobre la que se trabajan recomendaciones, plan e informes. *Se explica en: Módulo 04 — Actividad 1.*

**¿Qué significa el estado "Cerrada"?**
Alerta terminada; no se edita ni se reabre. *Se explica en: Módulo 04 — Actividad 1.*

**¿Qué significa el estado "Sin plan"?**
Ninguna recomendación de la alerta tiene actividades. *Se explica en: Módulo 06 — Actividad 1.*

**¿Qué significa el estado "Pendiente"?**
Hay actividades (o informes) por aprobar. *Se explica en: Módulo 07 — Actividad 1.*

**¿Qué significa el estado "Aprobado"?**
Todas las actividades están aprobadas; el plan se puede confirmar. *Se explica en: Módulo 07 — Actividad 1.*

**¿Qué significa el estado "Sin Informe"?**
La actividad debe reportar el informe del ciclo. *Se explica en: Módulo 06 — Actividad 1.*

**¿Qué significa el estado "Sin aprobación"?**
Reporte de ejecución que espera a su aprobador. *Se explica en: Módulo 09 — Actividad 1.*

**¿Qué pasa después de que se confirma el plan de acción?**
Las actividades quedan "Sin Informe", la Entidad Territorial recibe el correo de validación y puede reportar informes de ejecución; la alerta, sus recomendaciones y actividades ya no se editan. *Se explica en: Módulo 00 — Actividad 2.*

**¿Qué pasa si una entidad agrega una actividad a un plan confirmado?**
El plan se desconfirma: vuelve a "Pendiente", la nueva actividad debe aprobarse y el plan debe confirmarse otra vez. Lo existente no cambia. *Se explica en: Módulo 00 — Actividad 2.*

### Lo que puedo y no puedo hacer

**¿Puedo reportar una alerta temprana?**
Sí. *Se explica en: Módulo 04 — Actividad 7.*

**¿Puedo eliminar una alerta?**
No. UI y API: opción deshabilitada ("No tienes permisos para eliminar alertas") y permiso `EliminarAlerta` solo del Super Administrador. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cerrar alertas?**
No. UI y API: botón deshabilitado ("No tienes permisos para cerrar alertas") y permiso `CerrarAlerta` solo del Super Administrador. Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo agregar una recomendación?**
Sí. *Se explica en: Módulo 05 — Actividad 4.*

**¿Puedo agregar una actividad?**
No. UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría. Lo hace: La Entidad Territorial responsable de la recomendación. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo reportar un informe de ejecución?**
No. UI y API: sin botón y sin permiso `CrearInformeEjecucion`. Lo hace: La Entidad Territorial responsable. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar una actividad?**
No. UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades"). Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo confirmar el plan de acción?**
No. UI y API: botón deshabilitado ("No tienes permisos para confirmar planes de acción") y el servidor responde "No tiene permiso para confirmar planes de acción". Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo aprobar un informe de ejecución?**
No. UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades"). Lo hace: Monitor o Líder de Macrozona del departamento. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un reporte de ejecución?**
Sí. *Se explica en: Módulo 09 — Actividad 3.*

**¿Puedo aprobar un reporte de ejecución?**
No. UI y API: no ve el botón y no tiene el permiso `AprobarReporteEjecucion`. Lo hace: El aprobador designado (Líder de Macrozona o Super Administrador). *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo cargar un informe de seguimiento?**
Sí. *Se explica en: Módulo 10 — Actividad 2.*

**¿Puedo cargar un oficio de consumación?**
No. UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación". Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

**¿Puedo invitar un usuario?**
Sí. *Se explica en: Módulo 03 — Actividad 3.*

**¿Puedo adjuntar el PDF de la alerta y el Adjunto?**
No. API: el servidor exige el permiso `SubirArchivo`, que solo tiene el Super Administrador; la pantalla le muestra los campos y al final avisa "El PDF de la alerta no pudo ser subido.". Lo hace: Super Administrador. *Se explica en: Matriz de capacidades de esta ruta.*

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
No. Es informativo (1 a 3, 3 a 6, 6 a 9 meses o Permanente); los vencimientos solo los genera el Próximo Informe. *Se explica en: Módulo 06 — Actividad 4.*

### Notificaciones

**¿Qué avisos voy a recibir y qué debo hacer con cada uno?**
Solo los correos de acceso (invitación, código y restablecimiento). Lo demás lo ve en el panel Notificaciones. *Se explica en: Módulo 12 — Actividad 2.*

**¿Qué muestra el panel Notificaciones?**
El historial de actividad de las alertas de su alcance: quién hizo qué, cuándo y sobre qué alerta. No tiene marcas de leído. *Se explica en: Módulo 12 — Actividad 1.*

### Indicadores

**¿Cómo se calcula el % de cumplimiento?**
Actividades ejecutadas ÷ programadas × 100. Ejemplo: 3 ejecutadas de 4 programadas = 75 %. Cada 6 meses la meta se suma otra vez a lo programado: con 4 actividades por ciclo, en el segundo ciclo son 8 programadas. *Se explica en: Módulo 06 — Actividad 4.*

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

**¿Qué campos son obligatorios en "Enviar invitación / Editar usuario"?**
Rol; Nombres y Apellidos (Nombres); Nombres y Apellidos (Apellidos); Correo electrónico. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 03 — Actividad 3.*

**¿Qué campos son obligatorios en "Agregar / Editar entidad territorial"?**
Entidad Central; Categoría. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 03 — Actividad 8.*

**¿Qué campos son obligatorios en "Reportar alerta temprana / Editar alerta temprana (6 pasos)"?**
Número y fecha de alerta (número); Número y fecha de alerta (fecha); Fecha de notificación; Tipo de alerta; Etiqueta; Departamento; Municipio; Grupos armados ilegales; Conducta Vulneratoria; Población afectada. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 04 — Actividad 7.*

**¿Qué campos son obligatorios en "Agregar recomendación / Editar recomendación (2 pasos)"?**
Eje temático; Descripción; Entidad Principal. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 05 — Actividad 4.*

**¿Qué campos son obligatorios en "Cargar reporte de ejecución / Editar reporte"?**
Tipo; Fecha de reporte; Aprobador; Descripción; Adjunto. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 09 — Actividad 3.*

**¿Qué campos son obligatorios en "Panel de consultas (informe ejecutivo)"?**
Tipo de consulta. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 09 — Actividad 5.*

**¿Qué campos son obligatorios en "Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos)"?**
Número de informe; Alerta asociada; Fecha de notificación; PDF del informe. Los demás son opcionales o dependen de otro campo (vea la tabla "Campos a diligenciar"). *Se explica en: Módulo 10 — Actividad 2.*

**¿Qué archivos puedo adjuntar?**
Solo PDF, de hasta 20 MB por archivo. *Se explica en: Módulo 04 — Actividad 7.*

**¿De dónde salen las opciones de las listas?**
De archivos de catálogo del sistema (ejes temáticos, opciones de la alerta, departamentos y municipios, categorías de entidad) y de la tabla de entidades. Solo las entidades se administran desde la plataforma (Usuarios y entidades). *Se explica en: Módulo 03 — Actividad 3.*

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

**Me aparece «Tu organización está suspendida. Por favor contacta al administrador.»**
**Causa:** La entidad guardada en su usuario no está en estado Activa. **Solución:** Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 01 — Actividad 2 (ERR-ACC-05).*

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

**Me aparece «El rol es requerido»**
**Causa:** Faltan datos obligatorios según el rol. **Solución:** Complete los campos marcados con * según el rol elegido y vuelva a hacer clic en **Enviar Invitación**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Elija primero el **Rol**: de él dependen los demás campos. *Relacionado con: Módulo 03 — Actividad 3 (ERR-USU-01).*

**Me aparece «El correo electrónico ya existe»**
**Causa:** El correo debe ser único. **Solución:** Busque el usuario existente en la pestaña **Usuarios** o **Invitaciones**; si su invitación venció, use **Reenviar**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque por correo antes de invitar. *Relacionado con: Módulo 03 — Actividad 3 (ERR-USU-02).*

**Me aparece «El cargo es obligatorio para este rol»**
**Causa:** Falta un dato que el servidor exige para el rol. **Solución:** Complete el cargo, los departamentos, la entidad o la subdirección según el rol. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 3 (ERR-USU-04).*

**Me aparece «La entidad central es requerida»**
**Causa:** Faltan datos obligatorios de la entidad. **Solución:** Escriba el nombre, elija la categoría y agregue subdirecciones o desactive la opción. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 8 (ERR-USU-10).*

**Me aparece «El nombre de la entidad ya existe»**
**Causa:** Los nombres de entidad son únicos. **Solución:** Busque la entidad existente con "Buscar por nombre" y úsela. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque antes de crear (la pantalla lo recomienda: "verifica primero que no exista ya en la base de datos para evitar duplicados"). *Relacionado con: Módulo 03 — Actividad 8 (ERR-USU-11).*

**Me aparece «El número de alerta es requerido»**
**Causa:** Faltan campos obligatorios del Paso 1. **Solución:** Complete Número y fecha de alerta, Fecha de notificación, Tipo de alerta y Etiqueta. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Tenga el PDF de la alerta a la mano antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-01).*

**Me aparece «El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024)»**
**Causa:** El servidor exige 4 caracteres al final; la pantalla no lo valida y su ejemplo usa 2 (diferencia D1). **Solución:** Vuelva al Paso 1 con **Atrás** y escriba el número con el año completo, por ejemplo `AT-013-2025`; envíe de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Escriba siempre `AT-` + 3 caracteres + `-` + año de 4 dígitos. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-02).*

**Me aparece «El número de alerta 'AT-…' ya existe»**
**Causa:** La alerta ya fue registrada (manualmente, por X-Road o por el Agente IA). **Solución:** Busque el número en *Alertas tempranas* (incluidos los borradores) y edite la existente. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque antes de registrar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-03).*

**Me aparece «Debe agregar al menos una ubicación»**
**Causa:** La alerta necesita al menos un departamento y municipio. **Solución:** Seleccione el departamento, luego el municipio, y verifique que aparezca en la tabla. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-04).*

**Me aparece «Debe seleccionar al menos un grupo armado ilegal»**
**Causa:** Cada uno de esos pasos exige al menos una opción. **Solución:** Seleccione al menos una opción de la lista (use "Sin determinar" u "Otro" cuando el documento no lo precise, si la lista lo ofrece). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-05).*

**Registrar una fecha de notificación anterior a la fecha de la alerta y no aparece ningún mensaje**
**Causa:** NO ENCONTRADA la validación entre las dos fechas; la fecha de notificación es el día 0 de los informes. **Solución:** Verifique las fechas contra el documento antes de enviar; si ya se guardó mal, edite la alerta. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Confirme la fecha de notificación: de ella dependen los plazos de informe. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-22).*

**Me aparece «El eje temático es requerido»**
**Causa:** Faltan datos obligatorios. **Solución:** Elija el eje temático, escriba la descripción y agregue al menos una Entidad Principal. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-01).*

**Me aparece Aviso "Recomendaciones creadas — Se han creado {N} recomendaciones correctamente."**
**Causa:** Por cada Entidad Principal se crea una recomendación distinta con la misma descripción (hallazgo H2). **Solución:** Si debía ser una sola, el Super Administrador elimina las sobrantes y las demás entidades se registran como **Entidades asociadas**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Agregue una Entidad Principal por recomendación y las demás como asociadas. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-05).*

**Registrar dos veces la misma recomendación y no aparece ningún mensaje**
**Causa:** NO ENCONTRADA una validación de unicidad de eje, entidad y descripción. **Solución:** Busque por texto antes de crear; si quedó duplicada, pida al Super Administrador eliminarla. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use "Buscar por nombre" antes de crear. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-10).*

**Me aparece «El tipo de reporte es requerido»**
**Causa:** Faltan datos según el tipo. **Solución:** Complete los campos del tipo elegido, el aprobador, la descripción y el PDF. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Elija primero el **Tipo**. *Relacionado con: Módulo 09 — Actividad 3 (ERR-REP-01).*

**Me aparece «Para reportes de tipo Alerta, debe especificar una alerta»**
**Causa:** Datos inconsistentes con el tipo. **Solución:** Revise el tipo y el dato correspondiente. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 3 (ERR-REP-02).*

**Me aparece «El tipo de consulta es requerido»**
**Causa:** Faltan datos o falla la generación. **Solución:** Complete el tipo y su dato y haga clic en **Generar consulta**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 5 (ERR-REP-09).*

**Me aparece «El número de informe es requerido»**
**Causa:** Faltan datos obligatorios. **Solución:** Complete Número de informe, Alerta asociada, Fecha de notificación y PDF del informe. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-01).*

**Me aparece «Ya existe un informe con el número '…'. Por favor use un número diferente.»**
**Causa:** El número de informe es único. **Solución:** Verifique el número en el documento de la Defensoría. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque el número antes de cargar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-02).*

**Me aparece Campo bloqueado con "La alerta asociada no puede ser modificada"**
**Causa:** La alerta del informe no se cambia. **Solución:** Si la alerta está mal, elimine el informe (Super Administrador) y cárguelo de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 3 (ERR-ISE-08).*

### Permisos y alcance

**Encontrar en Mi perfil un rol, entidad, subdirección o departamentos que no corresponden y no aparece ningún mensaje**
**Causa:** El usuario fue configurado con otros datos; Mi perfil no permite editarlos. **Solución:** Pida la corrección a quien administra los usuarios, indicando el dato correcto. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise Mi perfil después del primer ingreso. *Relacionado con: Módulo 01 — Actividad 6 (ERR-ACC-15).*

**Me aparece «No tienes permisos para realizar esta acción.»**
**Causa:** El servidor rechaza la operación para el rol (403). **Solución:** Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co) con la pantalla, la hora y una captura **Cómo prevenirlo:** Use solo los botones habilitados para su rol. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-01).*

**Me aparece «Solo un Super Administrador puede crear otros Super Administradores»**
**Causa:** Restricción del rol Administrador. **Solución:** Pida la operación a un Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 3 (ERR-USU-03).*

**Me aparece Interruptor deshabilitado con el mensaje "No puedes desactivar tu propia cuenta" (servidor: "No puedes cambiar tu propio estado. Por favor contacta a otro administrador.")**
**Causa:** Nadie puede cambiar su propio estado. **Solución:** Pida el cambio a otro administrador. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 5 (ERR-USU-06).*

**Me aparece «No se puede cambiar el estado de un usuario con rol SUPER_ADMINISTRADOR»**
**Causa:** El estado de un Super Administrador no se cambia desde la plataforma. **Solución:** Escale al equipo técnico si se requiere. **Si no se resuelve:** Equipo técnico de SI-CIPRAT **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 5 (ERR-USU-07).*

**Me aparece Campo deshabilitado con "No es posible editar el número de una alerta automática" o "No tienes permisos para editar el número de alerta"**
**Causa:** El número de las alertas automáticas no se cambia; el de las manuales solo lo cambia el Super Administrador. **Solución:** Si el número está mal en una alerta manual, pida el cambio al Super Administrador. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 8 (ERR-ALE-11).*

**Me aparece Botón deshabilitado con "Solo las entidades territoriales pueden agregar actividades" o "No tienes permisos para agregar actividades"**
**Causa:** Su rol no formula actividades en la pantalla. **Solución:** Las actividades las registra la Entidad Territorial responsable de la recomendación. **Si no se resuelve:** Entidad Territorial responsable **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06 — Actividad 4 (ERR-PLA-06).*

**Me aparece Botón **Confirmar Plan de Acción** deshabilitado con "No tienes permisos para confirmar planes de acción"; sin botones **Aprobar** ni **Marcar como Revisado****
**Causa:** Su rol solo consulta en Seguimiento. **Solución:** La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 07 — Actividad 1 (ERR-SEG-07).*

**Me aparece Botón deshabilitado con "No tienes permisos para eliminar reportes"**
**Causa:** En la pantalla solo el Super Administrador elimina reportes. **Solución:** Pida la eliminación al Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 2 (ERR-REP-06).*

**Me aparece Botones deshabilitados con "No tienes permisos para cargar informes", "No tienes permisos para editar informes" o "No tienes permisos para eliminar informes"**
**Causa:** Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. **Solución:** Pida la carga a la Secretaría Técnica. **Si no se resuelve:** Administrador o Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 1 (ERR-ISE-07).*

**Me aparece «No tienes permisos para realizar esta acción.»**
**Causa:** Solo el Super Administrador cierra alertas. **Solución:** Cargue el informe sin marcar el cierre y pida al Super Administrador que cierre la alerta. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-04).*

**Me aparece Botones deshabilitados con "No tienes permisos para cargar oficios", "No tienes permisos para editar oficios" o "No tienes permisos para eliminar oficios"**
**Causa:** Solo el Super Administrador gestiona oficios. **Solución:** Pida la carga al Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 11 — Actividad 1 (ERR-OFI-02).*

**No veo, o aparece deshabilitada, la opción para cambiar la contraseña con la contraseña actual**
**Causa:** Su rol no tiene esta funcionalidad: UI: no existe una pantalla que use este servicio (`main-api/CipratApi/Controladores/AutenticacionControlador.cs:147`; solo `dashboard/src/contexts/AuthContext.tsx` lo referencia). **Solución:** No es un error de la plataforma. La realiza: Use **¿Has olvidado tu contraseña?** para cambiarla. **Si no se resuelve:** Use **¿Has olvidado tu contraseña?** para cambiarla **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-11).*

**No veo, o aparece deshabilitada, la opción para editar los datos del propio perfil**
**Causa:** Su rol no tiene esta funcionalidad: UI: los campos de Mi perfil están deshabilitados (`dashboard/src/pages/MyProfile.tsx:124-183`). **Solución:** No es un error de la plataforma. La realiza: Pida el cambio a quien administra los usuarios (Super Administrador o Administrador). **Si no se resuelve:** Pida el cambio a quien administra los usuarios (Super Administrador o Administrador) **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-13).*

**No veo, o aparece deshabilitada, la opción para consultar el historial de cambios de contraseña**
**Causa:** Su rol no tiene esta funcionalidad: UI: el hook `usePasswordHistory` existe, pero Mi perfil no lo muestra (`dashboard/src/hooks/usePasswordHistory.ts:20`, `dashboard/src/pages/MyProfile.tsx`). **Solución:** No es un error de la plataforma. La realiza: No disponible en la interfaz. **Si no se resuelve:** No disponible en la interfaz **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 01 — Actividad 1 (F-ACC-14).*

**No veo, o aparece deshabilitada, la opción para invitar un Super Administrador**
**Causa:** Su rol no tiene esta funcionalidad: API y UI: la opción no aparece para el Administrador y el servidor responde "Solo un Super Administrador puede crear otros Super Administradores" (`main-api/CipratApi/Servicios/InvitacionUsuarioServicio.cs:55`, `dashboard/src/components/ui/UserFormModal.tsx:332-336`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 03 — Actividad 1 (F-USU-05).*

**No veo, o aparece deshabilitada, la opción para adjuntar el PDF de la alerta y el Adjunto**
**Causa:** Su rol no tiene esta funcionalidad: API: el servidor exige el permiso `SubirArchivo`, que solo tiene el Super Administrador; la pantalla le muestra los campos y al final avisa "El PDF de la alerta no pudo ser subido." (`main-api/CipratApi/Servicios/ServicioPermisos.cs:254-258`, `dashboard/src/pages/AlertasTempranas.tsx:341-358`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-ALE-09).*

**No veo, o aparece deshabilitada, la opción para cambiar el número de una alerta manual**
**Causa:** Su rol no tiene esta funcionalidad: UI: el campo está deshabilitado con el mensaje "No tienes permisos para editar el número de alerta" (`dashboard/src/components/report-alert/ReportAlertModal.tsx:30-45`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-ALE-11).*

**No veo, o aparece deshabilitada, la opción para eliminar una alerta**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: opción deshabilitada ("No tienes permisos para eliminar alertas") y permiso `EliminarAlerta` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:40-44`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-ALE-14).*

**No veo, o aparece deshabilitada, la opción para reemplazar o eliminar los archivos de la alerta**
**Causa:** Su rol no tiene esta funcionalidad: API: permiso `EliminarArchivo` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:259-262`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-ALE-15).*

**No veo, o aparece deshabilitada, la opción para cerrar alertas**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cerrar alertas") y permiso `CerrarAlerta` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:45-49`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 04 — Actividad 1 (F-ALE-16).*

**No veo, o aparece deshabilitada, la opción para eliminar una recomendación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: opción deshabilitada ("No tienes permisos para eliminar recomendaciones") y permiso `EliminarRecomendacion` solo del Super Administrador (`main-api/CipratApi/Servicios/ServicioPermisos.cs:93-97`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 05 — Actividad 1 (F-REC-07).*

**No veo, o aparece deshabilitada, la opción para agregar una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable de la recomendación. **Si no se resuelve:** La Entidad Territorial responsable de la recomendación **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-11).*

**No veo, o aparece deshabilitada, la opción para agregar una actividad a un plan confirmado**
**Causa:** Su rol no tiene esta funcionalidad: UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable. **Si no se resuelve:** La Entidad Territorial responsable **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-12).*

**No veo, o aparece deshabilitada, la opción para editar una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI: los botones no se muestran ("Solo las entidades territoriales pueden agregar actividades"); el servidor sí lo permitiría (`dashboard/src/components/planes-de-accion/ActividadesTab.tsx:168-179`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-130`; riesgo R11). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable. **Si no se resuelve:** La Entidad Territorial responsable **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-13).*

**No veo, o aparece deshabilitada, la opción para eliminar una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `EliminarActividad` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:131-139`). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable. **Si no se resuelve:** La Entidad Territorial responsable **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-14).*

**No veo, o aparece deshabilitada, la opción para ver y escribir comentarios de una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI: el botón **Comentarios** solo aparece a quien formula actividades en Planes de acción o aprueba en Seguimiento (`dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:395-510`, `dashboard/src/components/planes-de-accion/ActividadesTab.tsx:569-711`); la API sí lo permitiría (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:77-83`). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial, el Monitor o el Líder de Macrozona. **Si no se resuelve:** La Entidad Territorial, el Monitor o el Líder de Macrozona **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-15).*

**No veo, o aparece deshabilitada, la opción para eliminar un comentario propio**
**Causa:** Su rol no tiene esta funcionalidad: UI: la ventana "Comentarios" no ofrece eliminar (`dashboard/src/components/planes-de-accion/ComentariosActividadModal.tsx`); la API lo permite al autor (`main-api/CipratApi/Controladores/ComentariosActividadControlador.cs:140`). **Solución:** No es un error de la plataforma. La realiza: No disponible en la interfaz. **Si no se resuelve:** No disponible en la interfaz **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-16).*

**No veo, o aparece deshabilitada, la opción para reportar un informe de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botón y sin permiso `CrearInformeEjecucion` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:168-176`). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable. **Si no se resuelve:** La Entidad Territorial responsable **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-17).*

**No veo, o aparece deshabilitada, la opción para editar un informe de ejecución pendiente**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botón y sin permiso `CrearInformeEjecucion` (`main-api/CipratApi/Servicios/ServicioPermisos.cs:168-176`). **Solución:** No es un error de la plataforma. La realiza: La Entidad Territorial responsable. **Si no se resuelve:** La Entidad Territorial responsable **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-18).*

**No veo, o aparece deshabilitada, la opción para eliminar un informe de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: NO ENCONTRADO: no hay endpoint DELETE en `main-api/CipratApi/Controladores/InformesEjecucionControlador.cs` aunque `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191` define `EliminarInformeEjecucion`. **Solución:** No es un error de la plataforma. La realiza: Corrija el informe con **Editar Informe** mientras esté pendiente. **Si no se resuelve:** Corrija el informe con **Editar Informe** mientras esté pendiente **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 06 — Actividad 1 (F-PLA-20).*

**No veo, o aparece deshabilitada, la opción para marcar una actividad como revisada**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-05).*

**No veo, o aparece deshabilitada, la opción para aprobar una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-06).*

**No veo, o aparece deshabilitada, la opción para descartar la aprobación de una actividad**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-07).*

**No veo, o aparece deshabilitada, la opción para validar si el plan se puede confirmar**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-08).*

**No veo, o aparece deshabilitada, la opción para confirmar el plan de acción**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para confirmar planes de acción") y el servidor responde "No tiene permiso para confirmar planes de acción" (`dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:75-79,331`, `main-api/CipratApi/Controladores/AlertasControlador.cs:880-893`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-09).*

**No veo, o aparece deshabilitada, la opción para aprobar un informe de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: sin botones y sin permiso `AprobarActividad` ("No tiene permiso para aprobar actividades") (`main-api/CipratApi/Servicios/ServicioPermisos.cs:140-146`). **Solución:** No es un error de la plataforma. La realiza: Monitor o Líder de Macrozona del departamento. **Si no se resuelve:** Monitor o Líder de Macrozona del departamento **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 07 — Actividad 1 (F-SEG-10).*

**No veo, o aparece deshabilitada, la opción para eliminar un reporte de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: UI: el botón solo se habilita al Super Administrador ("No tienes permisos para eliminar reportes"); la API sí lo permitiría (`dashboard/src/components/reportes-ejecucion/ReportesEjecucionTab.tsx:52-53`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:227-232`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 09 — Actividad 1 (F-REP-07).*

**No veo, o aparece deshabilitada, la opción para aprobar un reporte de ejecución**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: no ve el botón y no tiene el permiso `AprobarReporteEjecucion` (`dashboard/src/components/reportes-ejecucion/ReporteDetailModal.tsx:35-39`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:234-239`). **Solución:** No es un error de la plataforma. La realiza: El aprobador designado (Líder de Macrozona o Super Administrador). **Si no se resuelve:** El aprobador designado (Líder de Macrozona o Super Administrador) **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 09 — Actividad 1 (F-REP-08).*

**No veo, o aparece deshabilitada, la opción para cerrar la alerta con el informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: API: el servidor exige el permiso `CerrarAlerta` y responde 403 al Administrador, aunque la casilla se le muestra (`main-api/CipratApi/Controladores/AccionAlertasControlador.cs:205`, `dashboard/src/components/informes-seguimiento/InformeSeguimientoStep2Modificaciones.tsx:360`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 10 — Actividad 1 (F-ISE-07).*

**No veo, o aparece deshabilitada, la opción para eliminar un informe de seguimiento**
**Causa:** Su rol no tiene esta funcionalidad: UI: el botón solo se habilita al Super Administrador ("No tienes permisos para eliminar informes"); la API sí lo permitiría (`dashboard/src/components/informes-seguimiento/InformesDeSeguimientoTab.tsx:52`, `main-api/CipratApi/Servicios/ServicioPermisos.cs:64-68`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 10 — Actividad 1 (F-ISE-09).*

**No veo, o aparece deshabilitada, la opción para cargar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 11 — Actividad 1 (F-OFI-05).*

**No veo, o aparece deshabilitada, la opción para modificar municipios y agregar recomendaciones desde el oficio**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para cargar oficios") y el servidor responde "No tiene permiso para crear oficios de consumación" (`dashboard/src/components/oficios-consumacion/OficiosDeConsumacionTab.tsx:48`, `main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:195-198`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 11 — Actividad 1 (F-OFI-06).*

**No veo, o aparece deshabilitada, la opción para editar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para editar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:296-300`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 11 — Actividad 1 (F-OFI-07).*

**No veo, o aparece deshabilitada, la opción para eliminar un oficio de consumación**
**Causa:** Su rol no tiene esta funcionalidad: UI y API: botón deshabilitado ("No tienes permisos para eliminar oficios") y el servidor exige Super Administrador (`main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:353-357`). **Solución:** No es un error de la plataforma. La realiza: Super Administrador. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Consulte la tabla "Qué NO puede hacer" de esta ruta. *Relacionado con: Módulo 11 — Actividad 1 (F-OFI-08).*

### Estados

**Me aparece «Conflicto con el estado actual del recurso.»**
**Causa:** Otro usuario o una acción anterior cambió el estado del registro (409). **Solución:** Actualice la página, revise el estado actual y repita la acción si todavía aplica. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Evite el doble clic y trabaje sobre la información recién cargada. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-03).*

**Me aparece «La organización no existe o no está activa»**
**Causa:** La entidad elegida no está activa. **Solución:** Elija otra entidad activa o revise la entidad en la pestaña **Entidades**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 3 (ERR-USU-05).*

**Me aparece «No se puede cambiar el estado de un usuario con estado {estado}. El usuario debe aceptar su invitación primero.»**
**Causa:** El usuario está en Invitación pendiente o expirada. **Solución:** Use **Reenviar** para que active su cuenta, o **Eliminar invitación**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 5 (ERR-USU-08).*

**Me aparece «Solo se pueden reenviar invitaciones a usuarios con estado Pendiente o Expirada»**
**Causa:** El usuario ya activó su cuenta. **Solución:** Si no puede ingresar, que use **¿Has olvidado tu contraseña?**; para retirarlo, inactívelo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 6 (ERR-USU-09).*

**Me aparece «La Entidad Central no esta Activa»**
**Causa:** Regla de jerarquía de entidades. **Solución:** Use una entidad central activa y distinta. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 8 (ERR-USU-12).*

**Me aparece «No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas.»**
**Causa:** La subdirección está en uso. **Solución:** Reasigne los usuarios antes de quitarla. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 9 (ERR-USU-14).*

**Me aparece «Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones.»**
**Causa:** La entidad tiene subdirecciones creadas. **Solución:** Elimine primero las subdirecciones (si no están en uso). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 9 (ERR-USU-15).*

**Me aparece «No es posible eliminar la entidad — Tiene usuarios asociados o subdirecciones o está relacionada con alertas tempranas.»**
**Causa:** La entidad tiene usuarios, subdirecciones, alertas o recomendaciones. **Solución:** Reasigne o retire primero lo relacionado; si la entidad sigue en uso, no la elimine. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Elimine solo entidades creadas por error y sin uso. *Relacionado con: Módulo 03 — Actividad 10 (ERR-USU-13).*

**Me aparece «La alerta AT-… ya ha sido subsumida por otra alerta»**
**Causa:** Solo se subsumen alertas activas y no subsumidas. **Solución:** Quite esa alerta de la selección del Paso 6. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-06).*

**Me aparece Aviso "El número de alerta fue ajustado a … debido a una creación concurrente."**
**Causa:** El sistema ajustó el número para evitar duplicados. **Solución:** Verifique que el número final coincida con el documento; si no, corríjalo (Super Administrador). **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-20).*

**Me aparece «Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada.»**
**Causa:** Las alertas cerradas no se modifican. **Solución:** No requiere acción; si el cierre fue un error, escálelo. **Si no se resuelve:** Super Administrador / equipo técnico **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 8 (ERR-ALE-08).*

**Me aparece «No se puede editar la alerta porque su plan de acción ya fue confirmado»**
**Causa:** Con el plan confirmado la alerta queda bloqueada. **Solución:** Si el cambio es necesario, coordine con la Secretaría Técnica; la plataforma no ofrece reabrir el plan. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los datos de la alerta antes de que se confirme el plan. *Relacionado con: Módulo 04 — Actividad 8 (ERR-ALE-09).*

**Me aparece «No se puede editar la alerta AT-… porque ha sido subsumida por otra alerta»**
**Causa:** La alerta fue reemplazada por otra. **Solución:** Edite la alerta que la subsumió. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 8 (ERR-ALE-10).*

**Me aparece «La alerta no pudo ser publicada.»**
**Causa:** La alerta ya estaba Activa o Cerrada. **Solución:** No requiere acción: la opción solo aplica a borradores. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 9 (ERR-ALE-12).*

**Me aparece «La organización no existe o fue eliminada»**
**Causa:** La entidad no está activa. **Solución:** Elija otra entidad o revise la entidad en *Usuarios y entidades*. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-02).*

**Me aparece Botones deshabilitados: "No se pueden agregar recomendaciones a una alerta cerrada" (servidor: "No se puede crear una recomendación para una alerta cerrada")**
**Causa:** La alerta está cerrada. **Solución:** No requiere acción. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-03).*

**Me aparece «No se pueden crear recomendaciones porque el plan de acción ya fue confirmado»**
**Causa:** Con el plan confirmado las recomendaciones quedan bloqueadas. **Solución:** Las recomendaciones nuevas de la Defensoría se cargan con un informe de seguimiento. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Cargue todas las recomendaciones antes de la confirmación. *Relacionado con: Módulo 05 — Actividad 4 (ERR-REC-04).*

**Me aparece «Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso anterior.»**
**Causa:** La alerta está cerrada. **Solución:** Registre solo los datos del informe. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-03).*

**Me aparece «La entidad principal con ID … no existe o no está activa»**
**Causa:** La entidad no está activa. **Solución:** Elija otra entidad activa. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-10).*

### Archivos

**Me aparece «El PDF de la alerta no pudo ser subido.»**
**Causa:** Solo el Super Administrador tiene el permiso de subir archivos (riesgo R1). **Solución:** Pida al Super Administrador que edite la alerta y adjunte el PDF; verifique después que aparezca "PDF de la alerta" en el detalle. **Si no se resuelve:** Super Administrador **Cómo prevenirlo:** Coordine con el Super Administrador la carga del PDF. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-07).*

**Me aparece «Tipo de archivo no permitido. Solo se aceptan: .pdf»**
**Causa:** Los campos de archivo solo aceptan PDF. **Solución:** Convierta el documento a PDF y vuelva a seleccionarlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Prepare los soportes en PDF antes de abrir el formulario. *Relacionado con: Módulo 04 — Actividad 7 (ERR-GEN-08).*

**Me aparece «El archivo excede el tamaño máximo de {N} MB»**
**Causa:** El servidor acepta hasta 20 MB por archivo. **Solución:** Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Escanee en resolución media y sin color cuando sea posible. *Relacionado con: Módulo 04 — Actividad 7 (ERR-GEN-09).*

**Me aparece «No hay archivo disponible»**
**Causa:** El reporte no tiene PDF o la descarga falló. **Solución:** Pida al autor que edite el reporte y adjunte el PDF. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 2 (ERR-REP-08).*

**Me aparece «El reporte se creó pero hubo un error al subir el archivo»**
**Causa:** Falla al subir el archivo después de guardar. **Solución:** Abra el reporte con **Editar** y vuelva a adjuntar el PDF. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 3 (ERR-REP-07).*

**Me aparece «El informe se registró sin el documento PDF — No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo.»**
**Causa:** Falla al subir el archivo. **Solución:** Abra **Editar informe** y adjunte el PDF. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 2 (ERR-ISE-05).*

### Integraciones

**Esperar un correo de negocio (recomendación, plan, recordatorio) y no aparece ningún mensaje**
**Causa:** Los correos de negocio solo se envían a usuarios de Entidad Territorial. **Solución:** Consulte los cambios en el panel **Notificaciones** y en los módulos. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise el panel Notificaciones al iniciar el día. *Relacionado con: Módulo 12 — Actividad 2 (ERR-NOT-02).*

**Una alerta emitida por la Defensoría no aparece en SI-CIPRAT y no aparece ningún mensaje**
**Causa:** La alerta aún no llega por X-Road o el mensaje fue rechazado por el servidor. **Solución:** Informe a la Secretaría Técnica; el Super Administrador o el Administrador pueden registrarla con **Reportar alerta** si se confirma que no llegará. **Si no se resuelve:** Super Administrador / equipo técnico de interoperabilidad **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 1 (ERR-INT-01).*

### Sistema y conexión

**Me aparece «No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo.»**
**Causa:** Sin conexión o red bloqueada. **Solución:** Revise la conexión, recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Trabaje con conexión estable; los Términos de uso la exigen. *Relacionado con: Módulo 01 — Actividad 2 (ERR-GEN-06).*

**Me aparece «Error al cargar datos»**
**Causa:** Falla del servicio del tablero. **Solución:** Recargue la página; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 1 (ERR-INI-01).*

**Me aparece «Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio.»**
**Causa:** Los formularios de registro se bloquean en pantallas pequeñas. **Solución:** Use un computador de escritorio o portátil. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Planee el registro desde un computador. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-11).*

**Me aparece «El servidor no está disponible. Por favor, intenta más tarde.»**
**Causa:** Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). **Solución:** Espere unos minutos e intente de nuevo. **Si no se resuelve:** Soporte técnico si dura más de 30 minutos **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-05).*

**Me aparece «Error al cargar usuarios»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 03 — Actividad 1 (ERR-USU-17).*

**Me aparece «El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose.»**
**Causa:** El registro fue eliminado o el servidor no responde (404). **Solución:** Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. **Si no se resuelve:** Soporte técnico, con el número de la alerta y la hora **Cómo prevenirlo:** No use enlaces antiguos guardados en el navegador. *Relacionado con: Módulo 03 — Actividad 2 (ERR-GEN-02).*

**Me aparece «Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 1 (ERR-ALE-19).*

**Me aparece «Error interno del servidor. Por favor, intenta más tarde.»**
**Causa:** Error 500 del servidor. **Solución:** Espere unos minutos e intente de nuevo; si persiste, repórtelo. **Si no se resuelve:** Soporte técnico, con la pantalla, la acción, la hora y una captura **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 3 (ERR-GEN-04).*

**Me aparece «Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo.»**
**Causa:** Falla al generar el archivo o al conectarse. **Solución:** Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Filtre antes de descargar. *Relacionado con: Módulo 04 — Actividad 4 (ERR-GEN-10).*

**Me aparece «Error al cargar las recomendaciones. Por favor, intente nuevamente.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 05 — Actividad 1 (ERR-REC-07).*

**Me aparece «Error al cargar las actividades»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 06 — Actividad 2 (ERR-PLA-15).*

**Me aparece «Error al cargar reportes — No se pudieron cargar los reportes de ejecución. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 09 — Actividad 1 (ERR-REP-10).*

**Me aparece «Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 10 — Actividad 1 (ERR-ISE-09).*

**Me aparece «Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo.»**
**Causa:** Falla del servicio. **Solución:** Recargue la página e intente de nuevo. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 11 — Actividad 1 (ERR-OFI-05).*

### Sin resultados

**Me aparece «No hay datos de departamentos»**
**Causa:** No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. **Solución:** Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. **Si no se resuelve:** Super Administrador o Administrador **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 02 — Actividad 1 (ERR-INI-02).*

**Me aparece «Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida.»**
**Causa:** La ruta no existe. **Solución:** Haga clic en **Volver al inicio** y navegue desde el menú. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Use el menú lateral. *Relacionado con: Módulo 02 — Actividad 3 (ERR-GEN-12).*

**Me aparece «No hay notificaciones»**
**Causa:** No hay acciones registradas en las alertas de su alcance. **Solución:** No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 12 — Actividad 1 (ERR-NOT-01).*

**Me aparece «No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo.»**
**Causa:** No hay registros que cumplan la búsqueda dentro de su alcance. **Solución:** Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Busque por número de alerta o código. *Relacionado con: Módulo 03 — Actividad 1 (ERR-GEN-07).*

**Me aparece «La alerta solicitada no existe o ha sido eliminada.»**
**Causa:** La alerta ya no existe. **Solución:** Vuelva con **Volver a Alertas Tempranas**. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 6 (ERR-REC-08).*

**Me aparece «No hay alertas disponibles para subsunción»**
**Causa:** No hay otras alertas activas no subsumidas. **Solución:** Desactive "Esta alerta subsume otras alertas" y continúe. **Si no se resuelve:** Soporte técnico (siciprat@mininterior.gov.co), con la pantalla, la hora y una captura del mensaje. **Cómo prevenirlo:** Revise los requisitos previos de la actividad antes de empezar. *Relacionado con: Módulo 04 — Actividad 7 (ERR-ALE-23).*

## Glosario de la ruta

### Botón

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| ¿Has olvidado tu contraseña? | botón | Inicia la recuperación de la contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Activar cuenta | botón | Crea la contraseña y activa la cuenta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Agregar actividad | botón | Abre el registro de una actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Agregar entidad | botón | Guarda la entidad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Agregar Entidad | botón | Abre el registro de una entidad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Agregar recomendación | botón | Abre el registro de una recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Agregar subdirección | botón | Agrega una fila de subdirección. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Aplicar filtros | botón | Aplica los filtros elegidos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Aprobar | botón | Aprueba la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Aprobar informe | botón | Aprueba el reporte de ejecución (aprobador designado). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Aprobar Informe | botón | Aprueba el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Asociar entidades | botón | Agrega entidades asociadas a la Entidad Principal. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Atrás | botón | Regresa al paso anterior. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Cancelar | botón | Cierra sin guardar. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Cargar informe | botón | Abre la carga (reporte de ejecución o informe de seguimiento). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Cargar oficio | botón | Abre o guarda la carga de un oficio. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 11 — Actividad 1 |
| Cerrar alertas | botón | Abre el cierre de alertas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Comentarios | botón | Abre la conversación de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Confirmar | botón | Confirma la acción de la ventana. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Confirmar Plan de Acción | botón | Abre la confirmación del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Consultas | botón | Abre el Panel de consultas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Continuar | botón | Acepta agregar una actividad a un plan confirmado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Crear nuevo registro | botón | Registra otra revisión de la misma actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Crear recomendación | botón | Guarda la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 05 — Actividad 1 |
| Descargar | botón | Descarga el listado en CSV o el archivo. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Descargar reporte | botón | Descarga el PDF del reporte. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Descartar aprobación | botón | Devuelve la actividad aprobada a pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Editar Actividad | botón | Abre la edición de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Editar informe | botón | Edita el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 10 — Actividad 1 |
| Editar Informe | botón | Abre la edición del informe pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Eliminar Actividad | botón | Elimina la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Eliminar informe | botón | Elimina el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 10 — Actividad 1 |
| Eliminar invitación | botón | Elimina una invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Eliminar reporte | botón | Elimina un reporte no aprobado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Enviar Alerta | botón | Guarda la alerta nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Enviar invitación | botón | Abre el formulario de invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Enviar Invitación | botón | Envía la invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Filtros | botón | Abre los filtros del listado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Generar consulta | botón | Genera el informe ejecutivo en Word. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 09 — Actividad 1 |
| Guardar Cambios | botón | Guarda la edición (alerta o usuario). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Haz clic para reenviar | botón | Envía un nuevo código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Informe | botón | Abre el Informe de recomendaciones. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Iniciar Sesión | botón | Valida correo y contraseña y envía el código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Ir al plan de acción | botón | Abre las recomendaciones del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Limpiar filtros | botón | Quita todos los filtros. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Marcar como Revisado | botón | Deja constancia de la revisión (no cambia el estado). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 07 — Actividad 1 |
| Mostrar 10 mas | botón | Carga 10 registros más. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 12 — Actividad 1 |
| Reenviar | botón | Reenvía una invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 03 — Actividad 1 |
| Reportar actividad | botón | Guarda la actividad nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Reportar alerta | botón | Abre el registro manual de una alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Reportar Informe | botón | Abre el informe de ejecución de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Reportar informe de ejecución | botón | Guarda el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Restablecer contraseña | botón | Envía el enlace o guarda la nueva contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Siguiente | botón | Avanza al siguiente paso del asistente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 04 — Actividad 1 |
| Validar código | botón | Valida el código de 4 dígitos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 01 — Actividad 1 |
| Ver Actividades | botón | Abre las actividades de la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |
| Ver Alerta | botón | Abre la última alerta del banner. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 02 — Actividad 1 |
| Ver detalle | botón | Abre el detalle del registro. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Módulo 06 — Actividad 1 |

### Campo

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| % cumplimiento | campo | Ejecutadas ÷ programadas × 100. | Indicador de avance de actividad, recomendación y alerta. | Módulo 06 — Actividad 1 |
| Adjunto | campo | Archivo. PDF ≤ 20 MB; solo lo sube el Super Administrador | Obligatorio: No. | Módulo 04 — Actividad 7 |
| Agregar nuevos municipios (Departamento y Municipio) | campo | Listas con búsqueda. Alerta no cerrada | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Alerta | campo | Lista con búsqueda. Alerta existente | Obligatorio: Condicional: Tipo = Alerta. | Módulo 09 — Actividad 3 |
| Alerta asociada | campo | Lista con búsqueda. Alerta existente | Obligatorio: Sí. | Módulo 10 — Actividad 2 |
| Alertas subsumidas | campo | Lista de selección múltiple con búsqueda. Alertas activas no subsumidas | Obligatorio: Condicional: si el interruptor está activo. | Módulo 04 — Actividad 7 |
| Aprobador | campo | Usuario designado para aprobar un reporte de ejecución. | Solo él puede aprobar. | Módulo 09 — Actividad 1 |
| Área | campo | Texto. — | Obligatorio: No. | Módulo 03 — Actividad 3 |
| Cargo | campo | Texto. No vacío cuando es obligatorio | Obligatorio: Condicional: obligatorio para Entidad Territorial, Líder de Macrozona y Monitor. | Módulo 03 — Actividad 3 |
| Categoría | campo | Lista con búsqueda. Una categoría del catálogo | Obligatorio: Sí. | Módulo 03 — Actividad 8 |
| Cerrar la alerta con este informe | campo | Casilla. Solo el Super Administrador puede cerrar | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Código de verificación (4 casillas) | campo | Número (4 dígitos, uno por casilla). Solo dígitos 0-9; vigente 1 hora | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Código RC | campo | Código de la recomendación RC-{NNN}-{AAAA}-{NNN}. | Lo asigna el sistema; no corresponde al número de la recomendación en el documento. | Módulo 05 — Actividad 1 |
| Conducta Vulneratoria | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos una). | Módulo 04 — Actividad 7 |
| Confirmar Contraseña | campo | Texto oculto. Igual a Nueva Contraseña | Obligatorio: Sí. | Módulo 01 — Actividad 1 |
| Contraseña | campo | Texto oculto. La contraseña vigente | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Correo electrónico | campo | Texto (correo). Formato de correo | Obligatorio: Sí. | Módulo 01 — Actividad 2 |
| Creación: Manual / Automática | campo | Cómo se creó la alerta o la recomendación. | Las automáticas vienen de X-Road o del Agente IA. | Módulo 04 — Actividad 1 |
| Departamento | campo | Lista con búsqueda. Departamento del catálogo | Obligatorio: Sí (al menos una ubicación). | Módulo 04 — Actividad 7 |
| Departamentos | campo | Lista de selección múltiple con búsqueda. Al menos uno | Obligatorio: Condicional: obligatorio para Monitor, Líder de Macrozona y Consulta Departamentos. | Módulo 03 — Actividad 3 |
| Descripción | campo | Área de texto. Mínimo 1 carácter; sin máximo | Obligatorio: Sí. | Módulo 05 — Actividad 4 |
| Economías ilegales | campo | Lista de selección múltiple con búsqueda. — | Obligatorio: No. | Módulo 04 — Actividad 7 |
| Ejecutadas / Programadas | campo | Actividades ejecutadas frente a las programadas acumuladas. | Programadas suma el Número de actividades en cada ciclo. | Módulo 06 — Actividad 1 |
| Entidad | campo | Lista con búsqueda. Entidad existente | Obligatorio: Condicional: Tipo = Entidad. | Módulo 09 — Actividad 3 |
| Entidad Central | campo | Lista con búsqueda. Entidad central activa | Obligatorio: Condicional: obligatoria para Entidad Territorial y Consulta Entidad; "(opcional)" para Administrador, Líder de Macrozona y Monitor; no aparece para los demás. | Módulo 03 — Actividad 3 |
| Entidad Principal | campo | Entidad responsable de la recomendación y de reportar el informe de ejecución. | Sus usuarios de Entidad Territorial ven la recomendación y reciben los correos. | Módulo 05 — Actividad 1 |
| Entidades asociadas | campo | Entidades que apoyan una recomendación. | Reciben correo, pero no ven la recomendación. | Módulo 05 — Actividad 1 |
| Esta alerta subsume otras alertas | campo | Interruptor. — | Obligatorio: No. | Módulo 04 — Actividad 7 |
| Etiqueta | campo | Lista de selección única. — | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| Fecha de emisión | campo | Fecha. — | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Fecha de notificación | campo | Fecha (calendario). Fecha válida; es el día 0 de los informes; no se compara con la fecha de la alerta | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| Fecha de reporte | campo | Fecha. Fecha válida | Obligatorio: Sí. | Módulo 09 — Actividad 3 |
| Grupos armados ilegales | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos uno). | Módulo 04 — Actividad 7 |
| Historial Plan de acción | campo | Eventos del plan de una alerta. | Permite ver confirmaciones y desconfirmaciones. | Módulo 06 — Actividad 1 |
| Municipio | campo | Lista con búsqueda (dependiente). Código DANE de 5 dígitos; se pueden agregar varios | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| Municipios actuales de la alerta (Marcar como cerrado) | campo | Casilla por municipio. Alerta no cerrada | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Nivel de acceso | campo | Lista de selección única. — | Obligatorio: Condicional: solo si Rol = Entidad Territorial. | Módulo 03 — Actividad 3 |
| Nivel de acceso: Central / Subdirección | campo | Subdivisión del rol Entidad Territorial. | Central: entidad central; Subdirección: solo la subdirección elegida. | Módulo 03 — Actividad 1 |
| Nombres y Apellidos (Apellidos) | campo | Texto. No vacío | Obligatorio: Sí. | Módulo 03 — Actividad 3 |
| Nombres y Apellidos (Nombres) | campo | Texto. No vacío | Obligatorio: Sí. | Módulo 03 — Actividad 3 |
| Nueva Contraseña | campo | Texto oculto. Mínimo 8 caracteres y al menos un carácter especial | Obligatorio: Sí. | Módulo 01 — Actividad 1 |
| Número de actividades | campo | Meta de la actividad por cada ciclo de 6 meses. | Se suma a lo programado en cada ciclo. | Módulo 06 — Actividad 1 |
| Número de informe | campo | Texto. Máx. 500; único | Obligatorio: Sí. | Módulo 10 — Actividad 2 |
| Número de radicado | campo | Texto. Máx. 500 | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Número y fecha de alerta (fecha) | campo | Fecha (calendario). Fecha válida | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| Número y fecha de alerta (número) | campo | Texto. Formato `AT-XXX-XXXX` (3 y 4 caracteres alfanuméricos), máx. 50, único. La pantalla solo valida que no esté vacío | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| PDF de la alerta | campo | Archivo. PDF ≤ 20 MB; solo lo sube el Super Administrador | Obligatorio: No. | Módulo 04 — Actividad 7 |
| PDF del informe | campo | Archivo. PDF ≤ 20 MB | Obligatorio: Sí (si no hay archivo existente). | Módulo 10 — Actividad 2 |
| Población afectada | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos una). | Módulo 04 — Actividad 7 |
| Porcentaje de Avance Global | campo | Promedio del % de cumplimiento de las alertas no borrador del alcance. | Las alertas sin actividades cuentan como 0 %. | Módulo 02 — Actividad 1 |
| Próximo Informe | campo | Fecha límite del siguiente informe de la actividad. | Se fija al aprobar un informe: notificación + 6 meses y luego +6; al vencer se abre un nuevo ciclo. | Módulo 06 — Actividad 1 |
| Publicar alerta al guardar | campo | Interruptor. — | Obligatorio: Condicional: solo aparece al editar una alerta en Borrador. | Módulo 04 — Actividad 7 |
| Recomendaciones (Eje tematico, Descripción, Entidad principal) · **Agregar** | campo | Sub-formulario repetible. Eje y entidad activa; alerta no cerrada | Obligatorio: No. | Módulo 10 — Actividad 2 |
| Rol | campo | Lista de selección única. — | Obligatorio: Sí. | Módulo 03 — Actividad 3 |
| Sub Direcciones (interruptor) | campo | Interruptor. Si está activo, al menos una subdirección | Obligatorio: No. | Módulo 03 — Actividad 8 |
| Subdirección | campo | Lista con búsqueda. Subdirección activa de la Entidad Central | Obligatorio: Condicional: obligatoria si Nivel de acceso = Subdirección. | Módulo 03 — Actividad 3 |
| Subdirección (cada fila) · **Agregar subdirección** | campo | Texto repetible. Una fila por subdirección | Obligatorio: Condicional: si el interruptor está activo. | Módulo 03 — Actividad 8 |
| Tema Clave | campo | Descripción de la alerta. | Aparece en la columna Tema. | Módulo 04 — Actividad 1 |
| Tipo | campo | Lista de selección única. — | Obligatorio: Sí. | Módulo 09 — Actividad 3 |
| Tipo de alerta | campo | Lista de selección única. — | Obligatorio: Sí. | Módulo 04 — Actividad 7 |
| Tipo de consulta | campo | Lista de selección única. — | Obligatorio: Sí. | Módulo 09 — Actividad 5 |

### Catálogo

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Categoría (de entidad) | catálogo | 89 categorías de entidad (Alcaldía, Gobernación, Ministerio…). | Se usa para filtrar entidades y usuarios. | Módulo 03 — Actividad 1 |
| Eje temático | catálogo | Lista de 14 ejes de las recomendaciones. | El servidor no valida contra la lista. | Módulo 05 — Actividad 1 |
| Etiqueta: Nacional / Regional / Internacional | catálogo | Alcance territorial de la alerta. | Las etiquetas Focalizado y Binacional solo llegan por X-Road. | Módulo 04 — Actividad 1 |
| Plazo de implementación | catálogo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente. | Solo informativo. | Módulo 06 — Actividad 1 |
| Tipo de alerta: Inminencia / Estructural | catálogo | Clasificación de la alerta por su urgencia. | Inminencia se pinta en rojo y Estructural en azul en el mapa. | Módulo 04 — Actividad 1 |
| Tipo de reporte: Alerta / Entidad / Depto / Municipio / General | catálogo | Alcance de un reporte o consulta. | General solo en el Panel de consultas. | Módulo 09 — Actividad 1 |

### Concepto

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Actividad | concepto | Acción que la entidad se compromete a ejecutar para una recomendación, con meta por semestre. | Se aprueba una por una y se reporta con informes de ejecución. | Módulo 06 — Actividad 1 |
| Alerta temprana | concepto | Documento de la Defensoría del Pueblo que advierte un riesgo; en SI-CIPRAT es el registro central del ciclo. | Todo el trabajo (recomendaciones, plan, informes) cuelga de una alerta. | Módulo 04 — Actividad 1 |
| Informe de ejecución | concepto | Reporte semestral de lo ejecutado en una actividad, con su PDF. | Lo aprueban el Monitor o el Líder; al aprobarlo se fija el próximo informe. | Módulo 06 — Actividad 1 |
| Informe de seguimiento | concepto | Documento de la Defensoría que hace seguimiento a una alerta. | Puede agregar municipios y recomendaciones o cerrar la alerta. | Módulo 10 — Actividad 1 |
| Oficio de consumación | concepto | Documento de la Defensoría que informa que el riesgo se consumó. | Se asocia a alertas y puede modificar sus municipios. | Módulo 11 — Actividad 1 |
| Plan de acción | concepto | Conjunto de actividades de todas las recomendaciones de una alerta. | Se confirma completo por alerta. | Módulo 06 — Actividad 1 |
| Recomendación | concepto | Acción que la alerta pide a una Entidad Principal; tiene código RC. | La Entidad Principal le formula actividades. | Módulo 05 — Actividad 1 |
| Reporte de ejecución | concepto | Reporte consolidado publicado en Reportes, con aprobador designado. | Lo aprueba solo su aprobador. | Módulo 09 — Actividad 1 |
| Subsunción | concepto | Una alerta nueva reemplaza a otras, que quedan cerradas. | Irreversible. | Módulo 04 — Actividad 1 |

### Estado

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Activa | estado | Alerta vigente sobre la que se trabajan recomendaciones, planes e informes. | Se le cargan recomendaciones y actividades; puede editarse mientras el plan no esté confirmado. | Módulo 04 — Actividad 1 |
| Activo | estado | Usuario que puede iniciar sesión. | Puede inactivarse con el interruptor. | Módulo 03 — Actividad 1 |
| Aprobado | estado | Actividad aprobada; o plan con todas sus actividades aprobadas; o informe o reporte aprobado. | Una actividad aprobada no se edita; un plan Aprobado se puede confirmar; un informe aprobado no se edita. | Módulo 06 — Actividad 1 |
| Aprobado - Sin Informe | estado | Opción del filtro de actividades: actividad aprobada sin informe del ciclo. | La entidad debe reportar el informe. | Módulo 06 — Actividad 1 |
| Borrador | estado | Alerta creada por el Agente IA o por X-Road que aún no se publica. | Puede revisarla, corregirla y publicarla. | Módulo 04 — Actividad 1 |
| Cerrada | estado | Alerta terminada (por cierre, informe de seguimiento, subsunción o X-Road). | No se edita ni se reabre; su plan y sus informes quedan en "Cerrado". | Módulo 04 — Actividad 1 |
| Completado | estado | Informe que quedó cerrado al aprobar la actividad con un informe pendiente. | No se calcula el próximo informe en ese caso. | Módulo 06 — Actividad 1 |
| Inactivo | estado | Usuario que no puede iniciar sesión ("Cuenta no activa"). | Puede reactivarse con el interruptor. | Módulo 03 — Actividad 1 |
| Invitación Expirada | estado | Invitación no aceptada en 7 días. | Se debe reenviar. | Módulo 03 — Actividad 1 |
| Invitación Pendiente | estado | Usuario invitado que aún no activa su cuenta (7 días). | Se puede reenviar o eliminar la invitación. | Módulo 03 — Actividad 1 |
| Pendiente | estado | En el plan: hay actividades por aprobar. En el informe: hay informes por aprobar. | El Monitor o el Líder de Macrozona deben revisar y aprobar. | Módulo 06 — Actividad 1 |
| Pendiente Aprobación | estado | Estado de una actividad recién formulada o devuelta. | La entidad puede editarla o eliminarla; el Monitor o el Líder pueden aprobarla. | Módulo 06 — Actividad 1 |
| Plan de acción confirmado | estado | Plan cuya aprobación cerró el Monitor, el Líder o el Super Administrador con "Confirmar". | Habilita los informes de ejecución y bloquea la edición de la alerta, las recomendaciones y las actividades. | Módulo 06 — Actividad 1 |
| Sin aprobación | estado | Reporte de ejecución que espera al aprobador designado. | Se puede editar o eliminar (Super Administrador). | Módulo 09 — Actividad 1 |
| Sin Completar | estado | Estado de informes de la alerta cuando hay actividades sin informe del ciclo. | Faltan informes por reportar. | Módulo 06 — Actividad 1 |
| Sin Informe | estado | Actividad aprobada que aún no reporta el informe del ciclo. | La entidad puede usar "Reportar Informe". | Módulo 06 — Actividad 1 |
| Sin plan | estado | Estado del plan cuando ninguna recomendación tiene actividades. | La Entidad Territorial debe formular actividades. | Módulo 06 — Actividad 1 |
| Sin recomendaciones | estado | Estado del plan de una alerta que aún no tiene recomendaciones. | Se deben cargar recomendaciones (Super Administrador o Administrador). | Módulo 06 — Actividad 1 |

### Mensaje

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Alerta cerrada — No es posible editar una alerta que ya ha sido cerrada. | mensaje | Las alertas cerradas no se modifican. | No requiere acción; si el cierre fue un error, escálelo. | Módulo 04 — Actividad 8 |
| Código de autenticación inválido | mensaje | El código no coincide con el último enviado. | Revise el último correo "SI-CIPRAT - Código de Verificación" y escriba los 4 dígitos; si dudó, use **Haz clic para reenviar**. | Módulo 01 — Actividad 2 |
| Código expirado | mensaje | El código vence 1 hora después de enviado. | Haga clic en **Haz clic para reenviar** y use el código nuevo. | Módulo 01 — Actividad 2 |
| Conflicto con el estado actual del recurso. | mensaje | Otro usuario o una acción anterior cambió el estado del registro (409). | Actualice la página, revise el estado actual y repita la acción si todavía aplica. | Módulo 02 — Actividad 3 |
| Credenciales inválidas | mensaje | El correo no existe o la contraseña no corresponde. | Revise el correo (sin espacios) y la contraseña; si no la recuerda, use **¿Has olvidado tu contraseña?**. | Módulo 01 — Actividad 2 |
| Cuenta no activa | mensaje | El administrador cambió el estado del usuario a Inactivo. | Solicite la reactivación a quien administra los usuarios (Super Administrador o Administrador). | Módulo 01 — Actividad 2 |
| Debe agregar al menos una ubicación | mensaje | La alerta necesita al menos un departamento y municipio. | Seleccione el departamento, luego el municipio, y verifique que aparezca en la tabla. | Módulo 04 — Actividad 7 |
| Debe seleccionar al menos un grupo armado ilegal | mensaje | Cada uno de esos pasos exige al menos una opción. | Seleccione al menos una opción de la lista (use "Sin determinar" u "Otro" cuando el documento no lo precise, si la lista lo ofrece). | Módulo 04 — Actividad 7 |
| Debe tener al menos 8 caracteres | mensaje | La contraseña no cumple las reglas. | Escriba al menos 8 caracteres e incluya un símbolo (por ejemplo, ! # $ %). | Módulo 01 — Actividad 1 |
| Disponible en escritorio — Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio. | mensaje | Los formularios de registro se bloquean en pantallas pequeñas. | Use un computador de escritorio o portátil. | Módulo 02 — Actividad 3 |
| El archivo excede el tamaño máximo de {N} MB | mensaje | El servidor acepta hasta 20 MB por archivo. | Comprima el PDF por debajo de 20 MB y vuelva a cargarlo. | Módulo 04 — Actividad 7 |
| El cargo es obligatorio para este rol | mensaje | Falta un dato que el servidor exige para el rol. | Complete el cargo, los departamentos, la entidad o la subdirección según el rol. | Módulo 03 — Actividad 3 |
| El correo electrónico ya existe | mensaje | El correo debe ser único. | Busque el usuario existente en la pestaña **Usuarios** o **Invitaciones**; si su invitación venció, use **Reenviar**. | Módulo 03 — Actividad 3 |
| El eje temático es requerido | mensaje | Faltan datos obligatorios. | Elija el eje temático, escriba la descripción y agregue al menos una Entidad Principal. | Módulo 05 — Actividad 4 |
| El enlace de invitación es inválido. Verifica que el enlace esté completo. | mensaje | El enlace se cortó al copiarlo o la cuenta ya se activó. | Abra el enlace directamente desde el correo; si ya activó la cuenta, ingrese por **Iniciar Sesión**. | Módulo 01 — Actividad 1 |
| El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador. | mensaje | La invitación vence a los 7 días. | Pida que le reenvíen la invitación (opción **Reenviar** en Usuarios y entidades). | Módulo 01 — Actividad 1 |
| El informe se registró sin el documento PDF — No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo. | mensaje | Falla al subir el archivo. | Abra **Editar informe** y adjunte el PDF. | Módulo 10 — Actividad 2 |
| El nombre de la entidad ya existe | mensaje | Los nombres de entidad son únicos. | Busque la entidad existente con "Buscar por nombre" y úsela. | Módulo 03 — Actividad 8 |
| El número de alerta 'AT-…' ya existe | mensaje | La alerta ya fue registrada (manualmente, por X-Road o por el Agente IA). | Busque el número en *Alertas tempranas* (incluidos los borradores) y edite la existente. | Módulo 04 — Actividad 7 |
| El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024) | mensaje | El servidor exige 4 caracteres al final; la pantalla no lo valida y su ejemplo usa 2 (diferencia D1). | Vuelva al Paso 1 con **Atrás** y escriba el número con el año completo, por ejemplo `AT-013-2025`; envíe de nuevo. | Módulo 04 — Actividad 7 |
| El número de alerta es requerido | mensaje | Faltan campos obligatorios del Paso 1. | Complete Número y fecha de alerta, Fecha de notificación, Tipo de alerta y Etiqueta. | Módulo 04 — Actividad 7 |
| El número de alerta fue ajustado a … debido a una creación concurrente. | mensaje | El sistema ajustó el número para evitar duplicados. | Verifique que el número final coincida con el documento; si no, corríjalo (Super Administrador). | Módulo 04 — Actividad 7 |
| El número de informe es requerido | mensaje | Faltan datos obligatorios. | Complete Número de informe, Alerta asociada, Fecha de notificación y PDF del informe. | Módulo 10 — Actividad 2 |
| El PDF de la alerta no pudo ser subido. | mensaje | Solo el Super Administrador tiene el permiso de subir archivos (riesgo R1). | Pida al Super Administrador que edite la alerta y adjunte el PDF; verifique después que aparezca "PDF de la alerta" en el detalle. | Módulo 04 — Actividad 7 |
| El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose. | mensaje | El registro fue eliminado o el servidor no responde (404). | Vuelva al listado con **Volver** o el menú, actualice la página y busque de nuevo el registro. | Módulo 03 — Actividad 2 |
| El reporte se creó pero hubo un error al subir el archivo | mensaje | Falla al subir el archivo después de guardar. | Abra el reporte con **Editar** y vuelva a adjuntar el PDF. | Módulo 09 — Actividad 3 |
| El rol es requerido | mensaje | Faltan datos obligatorios según el rol. | Complete los campos marcados con * según el rol elegido y vuelva a hacer clic en **Enviar Invitación**. | Módulo 03 — Actividad 3 |
| El servidor no está disponible. Por favor, intenta más tarde. | mensaje | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Espere unos minutos e intente de nuevo. | Módulo 02 — Actividad 3 |
| El tipo de consulta es requerido | mensaje | Faltan datos o falla la generación. | Complete el tipo y su dato y haga clic en **Generar consulta**. | Módulo 09 — Actividad 5 |
| El tipo de reporte es requerido | mensaje | Faltan datos según el tipo. | Complete los campos del tipo elegido, el aprobador, la descripción y el PDF. | Módulo 09 — Actividad 3 |
| Error al cargar alertas — No se pudieron cargar las alertas. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 04 — Actividad 1 |
| Error al cargar datos | mensaje | Falla del servicio del tablero. | Recargue la página; si persiste, repórtelo. | Módulo 02 — Actividad 1 |
| Error al cargar informes — No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página. | Módulo 10 — Actividad 1 |
| Error al cargar las actividades | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 06 — Actividad 2 |
| Error al cargar las recomendaciones. Por favor, intente nuevamente. | mensaje | Falla del servicio. | Recargue la página. | Módulo 05 — Actividad 1 |
| Error al cargar oficios — No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 11 — Actividad 1 |
| Error al cargar reportes — No se pudieron cargar los reportes de ejecución. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Recargue la página. | Módulo 09 — Actividad 1 |
| Error al cargar usuarios | mensaje | Falla del servicio. | Recargue la página e intente de nuevo. | Módulo 03 — Actividad 1 |
| Error al descargar — No se pudo generar el archivo CSV. Intente de nuevo. | mensaje | Falla al generar el archivo o al conectarse. | Intente de nuevo; si el listado es muy grande, aplique filtros para reducirlo. | Módulo 04 — Actividad 4 |
| Error interno del servidor. Por favor, intenta más tarde. | mensaje | Error 500 del servidor. | Espere unos minutos e intente de nuevo; si persiste, repórtelo. | Módulo 04 — Actividad 3 |
| Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso anterior. | mensaje | La alerta está cerrada. | Registre solo los datos del informe. | Módulo 10 — Actividad 2 |
| La alerta asociada no puede ser modificada | mensaje | La alerta del informe no se cambia. | Si la alerta está mal, elimine el informe (Super Administrador) y cárguelo de nuevo. | Módulo 10 — Actividad 3 |
| La alerta AT-… ya ha sido subsumida por otra alerta | mensaje | Solo se subsumen alertas activas y no subsumidas. | Quite esa alerta de la selección del Paso 6. | Módulo 04 — Actividad 7 |
| La alerta no pudo ser publicada. | mensaje | La alerta ya estaba Activa o Cerrada. | No requiere acción: la opción solo aplica a borradores. | Módulo 04 — Actividad 9 |
| La alerta solicitada no existe o ha sido eliminada. | mensaje | La alerta ya no existe. | Vuelva con **Volver a Alertas Tempranas**. | Módulo 04 — Actividad 6 |
| La entidad central es requerida | mensaje | Faltan datos obligatorios de la entidad. | Escriba el nombre, elija la categoría y agregue subdirecciones o desactive la opción. | Módulo 03 — Actividad 8 |
| La Entidad Central no esta Activa | mensaje | Regla de jerarquía de entidades. | Use una entidad central activa y distinta. | Módulo 03 — Actividad 8 |
| La entidad principal con ID … no existe o no está activa | mensaje | La entidad no está activa. | Elija otra entidad activa. | Módulo 10 — Actividad 2 |
| La organización no existe o fue eliminada | mensaje | La entidad no está activa. | Elija otra entidad o revise la entidad en *Usuarios y entidades*. | Módulo 05 — Actividad 4 |
| La organización no existe o no está activa | mensaje | La entidad elegida no está activa. | Elija otra entidad activa o revise la entidad en la pestaña **Entidades**. | Módulo 03 — Actividad 3 |
| La solicitud no es válida. Verifica los datos e intenta de nuevo. | mensaje | Errores 400 o 422 de validación. | Revise los campos marcados en rojo y los formatos indicados; corrija y envíe de nuevo. | Módulo 02 — Actividad 3 |
| Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente. | mensaje | Los dos campos no coinciden. | Escriba la misma contraseña en **Nueva Contraseña** y **Confirmar Contraseña**. | Módulo 01 — Actividad 1 |
| No es posible editar el número de una alerta automática | mensaje | El número de las alertas automáticas no se cambia; el de las manuales solo lo cambia el Super Administrador. | Si el número está mal en una alerta manual, pida el cambio al Super Administrador. | Módulo 04 — Actividad 8 |
| No es posible eliminar la entidad — Tiene usuarios asociados o subdirecciones o está relacionada con alertas tempranas. | mensaje | La entidad tiene usuarios, subdirecciones, alertas o recomendaciones. | Reasigne o retire primero lo relacionado; si la entidad sigue en uso, no la elimine. | Módulo 03 — Actividad 10 |
| No hay alertas disponibles para subsunción | mensaje | No hay otras alertas activas no subsumidas. | Desactive "Esta alerta subsume otras alertas" y continúe. | Módulo 04 — Actividad 7 |
| No hay archivo disponible | mensaje | El reporte no tiene PDF o la descarga falló. | Pida al autor que edite el reporte y adjunte el PDF. | Módulo 09 — Actividad 2 |
| No hay datos de departamentos | mensaje | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Revise su alcance en **Ver Perfil**; si falta la asignación, pídala al administrador. | Módulo 02 — Actividad 1 |
| No hay notificaciones | mensaje | No hay acciones registradas en las alertas de su alcance. | No requiere acción; verifique su alcance en **Ver Perfil** si esperaba ver eventos. | Módulo 12 — Actividad 1 |
| No puedes desactivar tu propia cuenta | mensaje | Nadie puede cambiar su propio estado. | Pida el cambio a otro administrador. | Módulo 03 — Actividad 5 |
| No puedes reutilizar ninguna de tus últimas 5 contraseñas | mensaje | El sistema guarda el historial de contraseñas. | Elija una contraseña distinta de las 5 anteriores. | Módulo 01 — Actividad 3 |
| No se encontraron resultados — Tu búsqueda no coincide con ningún registro. Intenta de nuevo. | mensaje | No hay registros que cumplan la búsqueda dentro de su alcance. | Borre la búsqueda, use **Limpiar filtros** y busque con menos palabras o por número. | Módulo 03 — Actividad 1 |
| No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo. | mensaje | Sin conexión o red bloqueada. | Revise la conexión, recargue la página e intente de nuevo. | Módulo 01 — Actividad 2 |
| No se puede cambiar el estado de un usuario con estado {estado}. El usuario debe aceptar su invitación primero. | mensaje | El usuario está en Invitación pendiente o expirada. | Use **Reenviar** para que active su cuenta, o **Eliminar invitación**. | Módulo 03 — Actividad 5 |
| No se puede cambiar el estado de un usuario con rol SUPER_ADMINISTRADOR | mensaje | El estado de un Super Administrador no se cambia desde la plataforma. | Escale al equipo técnico si se requiere. | Módulo 03 — Actividad 5 |
| No se puede editar la alerta AT-… porque ha sido subsumida por otra alerta | mensaje | La alerta fue reemplazada por otra. | Edite la alerta que la subsumió. | Módulo 04 — Actividad 8 |
| No se puede editar la alerta porque su plan de acción ya fue confirmado | mensaje | Con el plan confirmado la alerta queda bloqueada. | Si el cambio es necesario, coordine con la Secretaría Técnica; la plataforma no ofrece reabrir el plan. | Módulo 04 — Actividad 8 |
| No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas. | mensaje | La subdirección está en uso. | Reasigne los usuarios antes de quitarla. | Módulo 03 — Actividad 9 |
| No se pueden agregar recomendaciones a una alerta cerrada | mensaje | La alerta está cerrada. | No requiere acción. | Módulo 05 — Actividad 4 |
| No se pueden crear recomendaciones porque el plan de acción ya fue confirmado | mensaje | Con el plan confirmado las recomendaciones quedan bloqueadas. | Las recomendaciones nuevas de la Defensoría se cargan con un informe de seguimiento. | Módulo 05 — Actividad 4 |
| No tienes permisos para cargar informes | mensaje | Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. | Pida la carga a la Secretaría Técnica. | Módulo 10 — Actividad 1 |
| No tienes permisos para cargar oficios | mensaje | Solo el Super Administrador gestiona oficios. | Pida la carga al Super Administrador. | Módulo 11 — Actividad 1 |
| No tienes permisos para confirmar planes de acción | mensaje | Su rol solo consulta en Seguimiento. | La aprobación la hacen el Monitor y el Líder de Macrozona del departamento. | Módulo 07 — Actividad 1 |
| No tienes permisos para eliminar reportes | mensaje | En la pantalla solo el Super Administrador elimina reportes. | Pida la eliminación al Super Administrador. | Módulo 09 — Actividad 2 |
| No tienes permisos para realizar esta acción. | mensaje | El servidor rechaza la operación para el rol (403). | Verifique en su ruta qué puede hacer su rol; pida la operación al rol que la realiza. | Módulo 02 — Actividad 3 |
| Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones. | mensaje | La entidad tiene subdirecciones creadas. | Elimine primero las subdirecciones (si no están en uso). | Módulo 03 — Actividad 9 |
| Página no encontrada — Lo sentimos, la página que buscas no existe o ha sido movida. | mensaje | La ruta no existe. | Haga clic en **Volver al inicio** y navegue desde el menú. | Módulo 02 — Actividad 3 |
| Para reportes de tipo Alerta, debe especificar una alerta | mensaje | Datos inconsistentes con el tipo. | Revise el tipo y el dato correspondiente. | Módulo 09 — Actividad 3 |
| Recomendaciones creadas — Se han creado {N} recomendaciones correctamente. | mensaje | Por cada Entidad Principal se crea una recomendación distinta con la misma descripción (hallazgo H2). | Si debía ser una sola, el Super Administrador elimina las sobrantes y las demás entidades se registran como **Entidades asociadas**. | Módulo 05 — Actividad 4 |
| Sesión cerrada por inactividad — Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente. | mensaje | Cierre automático por inactividad de 60 minutos. | Inicie sesión de nuevo (correo, contraseña y código). | Módulo 01 — Actividad 4 |
| Sesión expirada — Tu sesión ha expirado. Por favor, inicia sesión nuevamente. | mensaje | El token de la sesión venció (720 minutos) o no es válido. | Inicie sesión de nuevo. | Módulo 01 — Actividad 4 |
| Solo las entidades territoriales pueden agregar actividades | mensaje | Su rol no formula actividades en la pantalla. | Las actividades las registra la Entidad Territorial responsable de la recomendación. | Módulo 06 — Actividad 4 |
| Solo se pueden reenviar invitaciones a usuarios con estado Pendiente o Expirada | mensaje | El usuario ya activó su cuenta. | Si no puede ingresar, que use **¿Has olvidado tu contraseña?**; para retirarlo, inactívelo. | Módulo 03 — Actividad 6 |
| Solo un Super Administrador puede crear otros Super Administradores | mensaje | Restricción del rol Administrador. | Pida la operación a un Super Administrador. | Módulo 03 — Actividad 3 |
| Tipo de archivo no permitido. Solo se aceptan: .pdf | mensaje | Los campos de archivo solo aceptan PDF. | Convierta el documento a PDF y vuelva a seleccionarlo. | Módulo 04 — Actividad 7 |
| Token inválido o expirado | mensaje | El enlace de restablecimiento vence en 1 hora. | Vuelva a **¿Has olvidado tu contraseña?** y solicite un enlace nuevo. | Módulo 01 — Actividad 3 |
| Tu organización está suspendida. Por favor contacta al administrador. | mensaje | La entidad guardada en su usuario no está en estado Activa. | Comuníquese con el Super Administrador o el Administrador para revisar el estado de su entidad. | Módulo 01 — Actividad 2 |
| Ya existe un informe con el número '…'. Por favor use un número diferente. | mensaje | El número de informe es único. | Verifique el número en el documento de la Defensoría. | Módulo 10 — Actividad 2 |

### Menú o pestaña

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Alertas / Recomendaciones / Actividades | menú o pestaña | Pestañas de Planes de acción y Seguimiento. | Abre la vista correspondiente. | Módulo 06 — Actividad 1 |
| Alertas tempranas | menú o pestaña | Registro y consulta de las alertas. | Abre la vista correspondiente. | Módulo 04 — Actividad 1 |
| Centrales / Subdirecciones | menú o pestaña | Vistas de la pestaña Entidades. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Cerrar sesión | menú o pestaña | Termina la sesión. | Abre la vista correspondiente. | Módulo 01 — Actividad 1 |
| Entidad / Eje tematico | menú o pestaña | Vistas de la tabla Cumplimiento del Informe de recomendaciones. | Abre la vista correspondiente. | Módulo 08 — Actividad 1 |
| Historial de actividades | menú o pestaña | Línea de tiempo de acciones sobre una alerta. | Abre la vista correspondiente. | Módulo 04 — Actividad 1 |
| Información / Actividades / Historial | menú o pestaña | Pestañas del detalle de una recomendación en el plan. | Abre la vista correspondiente. | Módulo 06 — Actividad 1 |
| Informes de seguimiento | menú o pestaña | Informes de seguimiento de la Defensoría. | Abre la vista correspondiente. | Módulo 10 — Actividad 1 |
| Inicio | menú o pestaña | Tablero de indicadores, mapa y alertas recientes. | Abre la vista correspondiente. | Módulo 02 — Actividad 1 |
| Notificaciones | menú o pestaña | Panel con el historial de actividad de su alcance. | Abre la vista correspondiente. | Módulo 12 — Actividad 1 |
| Oficios de consumación | menú o pestaña | Oficios de consumación del riesgo. | Abre la vista correspondiente. | Módulo 11 — Actividad 1 |
| Panel de consultas | menú o pestaña | Ventana para generar informes ejecutivos en Word. | Abre la vista correspondiente. | Módulo 09 — Actividad 1 |
| Planes de acción | menú o pestaña | Formulación de actividades e informes de ejecución. | Abre la vista correspondiente. | Módulo 06 — Actividad 1 |
| Reportes | menú o pestaña | Reportes de ejecución y Panel de consultas. | Abre la vista correspondiente. | Módulo 09 — Actividad 1 |
| Seguimiento | menú o pestaña | Revisión y aprobación de actividades, confirmación de planes y aprobación de informes ("Seguimiento de Planes"). | Abre la vista correspondiente. | Módulo 07 — Actividad 1 |
| Todas / Inminencia / Estructurales | menú o pestaña | Pestañas del listado de alertas por tipo. | Abre la vista correspondiente. | Módulo 04 — Actividad 1 |
| Todos / Alerta / Entidad / Regional | menú o pestaña | Pestañas de Reportes (Regional = departamental y municipal). | Abre la vista correspondiente. | Módulo 09 — Actividad 1 |
| Todos / Entidades Territoriales / Administradores / Monitores / Invitaciones | menú o pestaña | Vistas de la pestaña Usuarios. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Usuarios y entidades | menú o pestaña | Administración de usuarios, invitaciones, entidades y subdirecciones. | Abre la vista correspondiente. | Módulo 03 — Actividad 1 |
| Ver Perfil | menú o pestaña | Acceso a Mi perfil. | Abre la vista correspondiente. | Módulo 01 — Actividad 1 |

### Rol

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| Administrador | rol | Acceso nacional para visualizar alertas y gestionar planes de acción. No puede eliminar alertas ni aprobar actividades. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Consulta Departamentos | rol | Solo lectura filtrado por departamentos asignados. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Consulta Entidad | rol | Solo lectura filtrado por su entidad asignada. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Consulta Global | rol | Solo lectura a nivel nacional (sin modificar datos). (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Entidad Territorial | rol | Gestiona actividades e informes de ejecución de su entidad/subdirección. No puede aprobar. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Líder de Macrozona | rol | Supervisa alertas en departamentos asignados. Acceso total a reportes de ejecución. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Monitor | rol | Acceso departamental. Puede aprobar actividades e informes en Seguimiento. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |
| Super Administrador | rol | Acceso total a la plataforma sin restricciones. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Módulo 03 — Actividad 1 |

### Sigla

| Término | Tipo | Significado | Qué implica para el Administrador | Dónde lo verá |
|---|---|---|---|---|
| AT | sigla | Prefijo del número de alerta temprana (AT-XXX-XXXX). | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| CAT | sigla | Categoría municipal según la Contaduría General de la Nación (ESP, 1 a 6, N/A). | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| CIPRAT | sigla | Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas. | Aparece en pantallas y documentos de la ruta. | Módulo 01 — Actividad 1 |
| CSV | sigla | Archivo de texto separado por comas que se abre en Excel. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| D.I.H. | sigla | Derecho Internacional Humanitario (paso 4 de la alerta). | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| DANE / Cod DANE | sigla | Código del municipio (5 dígitos) del DANE. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| PDET | sigla | Programa de Desarrollo con Enfoque Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| PDF | sigla | Único formato de archivo aceptado para los soportes. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| PNIS | sigla | Programa Nacional Integral de Sustitución de Cultivos de Uso Ilícito. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| RC | sigla | Prefijo del código de la recomendación. | Aparece en pantallas y documentos de la ruta. | Módulo 05 — Actividad 1 |
| SI-CIPRAT | sigla | Sistema de Información de la Secretaría Técnica CIPRAT. | Aparece en pantallas y documentos de la ruta. | Módulo 01 — Actividad 1 |
| SISAT | sigla | Sistema de Alertas Tempranas de la Defensoría del Pueblo; envía información por X-Road. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| X-Road | sigla | Plataforma de interoperabilidad por la que llegan alertas, informes y oficios. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |
| Zona Fut. | sigla | Zona del Formulario Único Territorial. | Aparece en pantallas y documentos de la ruta. | Módulo 04 — Actividad 1 |

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
| 12 Notificaciones | 1. Consultar el panel de Notificaciones | 3 | F-NOT-01, F-NOT-02, F-NOT-03 | dashboard/src/components/notifications/NotificationsPanel.tsx:30-113; dashboard/src/components/notifications/NotificationsPanel.tsx:128; dashboard/src/components/ui/ActivityList.tsx:77 |
| 12 Notificaciones | 2. Reconocer los correos que envía el sistema y qué hacer con cada uno | 2 | F-NOT-04, F-NOT-05, F-NOT-06 | main-api/CipratApi/Servicios/EmailService.cs:62; main-api/CipratApi/Servicios/EmailService.cs:38; main-api/CipratApi/Servicios/EmailService.cs:92 |
| 03 Usuarios y entidades | 1. Consultar, buscar y filtrar usuarios e invitaciones | 4 | F-USU-01, F-USU-02 | dashboard/src/components/usuarios-entidades/UsuariosTab.tsx:192-439; dashboard/src/components/ui/UserFiltersModal.tsx:121-441 |
| 03 Usuarios y entidades | 2. Ver el detalle de un usuario | 3 | F-USU-03 | dashboard/src/components/ui/UserDetailModal.tsx:269-360 |
| 03 Usuarios y entidades | 3. Invitar un usuario | 10 | F-USU-04 | main-api/CipratApi/Controladores/UsuariosControlador.cs:63-69 |
| 03 Usuarios y entidades | 4. Editar un usuario | 3 | F-USU-06 | main-api/CipratApi/Controladores/UsuariosControlador.cs:125-132 |
| 03 Usuarios y entidades | 5. Activar o inactivar un usuario | 2 | F-USU-07 | main-api/CipratApi/Controladores/UsuariosControlador.cs:353-360 |
| 03 Usuarios y entidades | 6. Reenviar o eliminar una invitación | 3 | F-USU-08, F-USU-09 | main-api/CipratApi/Controladores/UsuariosControlador.cs:199-206; main-api/CipratApi/Controladores/UsuariosControlador.cs:422-429 |
| 03 Usuarios y entidades | 7. Consultar, buscar y filtrar entidades | 5 | F-USU-10, F-USU-11, F-USU-12, F-USU-13 | dashboard/src/components/usuarios-entidades/EntidadesTab.tsx:90-310; dashboard/src/components/ui/EntityFiltersModal.tsx:134-211; dashboard/src/components/ui/EntityDetailModal.tsx:175-313 |
| 03 Usuarios y entidades | 8. Agregar una entidad con sus subdirecciones | 5 | F-USU-14 | main-api/CipratApi/Controladores/EntidadesControlador.cs:41-47 |
| 03 Usuarios y entidades | 9. Editar una entidad y sus subdirecciones | 4 | F-USU-15 | main-api/CipratApi/Controladores/EntidadesControlador.cs:89-95 |
| 03 Usuarios y entidades | 10. Eliminar una entidad | 2 | F-USU-16 | main-api/CipratApi/Controladores/EntidadesControlador.cs:281-282 |
| 04 Alertas tempranas | 1. Consultar, buscar y filtrar alertas tempranas | 6 | F-ALE-01, F-ALE-02, F-ALE-03, F-INT-01 | main-api/CipratApi/Controladores/AlertasControlador.cs:87; dashboard/src/components/alertas-tempranas/AlertasTab.tsx:294; dashboard/src/components/alertas-tempranas/AlertFiltersModal.tsx:216-420 |
| 04 Alertas tempranas | 2. Ver el detalle de una alerta y descargar su PDF | 5 | F-ALE-04, F-ALE-05 | dashboard/src/components/alertas-tempranas/AlertInfoContent.tsx:13-340; main-api/CipratApi/Controladores/ArchivosControlador.cs:135-170 |
| 04 Alertas tempranas | 3. Consultar el historial de actividades de una alerta | 3 | F-ALE-06 | main-api/CipratApi/Controladores/AlertasControlador.cs:627-700 |
| 04 Alertas tempranas | 4. Descargar el listado de alertas en CSV | 2 | F-ALE-07 | main-api/CipratApi/Controladores/AlertasControlador.cs:1004-1087 |
| 04 Alertas tempranas | 5. Revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA | 3 | F-INT-01 | main-api/CipratApi/Controladores/InteroperabilidadControlador.cs:603-614 |
| 04 Alertas tempranas | 6. Ir a las recomendaciones de una alerta | 2 | F-REC-01 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41 |
| 04 Alertas tempranas | 7. Reportar una alerta temprana | 15 | F-ALE-08, F-ALE-13 | main-api/CipratApi/Controladores/AlertasControlador.cs:336-387; main-api/CipratApi/Servicios/ServicioAlertas.cs:195-259 |
| 04 Alertas tempranas | 8. Editar una alerta | 5 | F-ALE-10 | main-api/CipratApi/Servicios/ServicioAlertas.cs:416-454 |
| 04 Alertas tempranas | 9. Publicar una alerta en Borrador | 3 | F-ALE-12 | main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:339-359 |
| 04 Alertas tempranas | 10. Subsumir alertas | 3 | F-ALE-13 | main-api/CipratApi/Servicios/ServicioAlertas.cs:195-259 |
| 05 Recomendaciones | 1. Consultar, buscar y filtrar las recomendaciones de una alerta | 4 | F-REC-01, F-REC-02, F-REC-08 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:41; dashboard/src/components/recomendaciones/RecomendacionFiltersModal.tsx:198-344; main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:516-540 |
| 05 Recomendaciones | 2. Ver el detalle de una recomendación | 2 | F-REC-03 | dashboard/src/components/recomendaciones/RecomendacionDetailModal.tsx:84-207 |
| 05 Recomendaciones | 3. Descargar las recomendaciones de una alerta en CSV | 2 | F-REC-04 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:436-566 |
| 05 Recomendaciones | 4. Agregar una recomendación | 7 | F-REC-05, F-REC-08 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:133-140; main-api/CipratApi/Servicios/ServicioRecomendaciones.cs:516-540 |
| 05 Recomendaciones | 5. Editar una recomendación | 3 | F-REC-06 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:218-225 |
| 06 Planes de acción | 1. Consultar y filtrar los planes de acción por alerta | 5 | F-PLA-01, F-PLA-02, F-PLA-03, F-PLA-04 | dashboard/src/components/planes-de-accion/PlanesDeAccionTab.tsx:139-334; dashboard/src/components/planes-de-accion/ActionPlanFiltersModal.tsx:119-243; dashboard/src/components/planes-de-accion/ActionPlanDetailModal.tsx:96-106 |
| 06 Planes de acción | 2. Recorrer las recomendaciones del plan de una alerta | 3 | F-PLA-05 | dashboard/src/components/planes-de-accion/PlanDeAccionRecomendacionesTab.tsx:137-245 |
| 06 Planes de acción | 3. Consultar las pestañas globales de Recomendaciones y Actividades | 3 | F-PLA-06, F-PLA-07, F-PLA-10 | main-api/CipratApi/Controladores/RecomendacionesControlador.cs:343; main-api/CipratApi/Servicios/ServicioActividades.cs:476-497; main-api/CipratApi/Controladores/ActividadesControlador.cs:496-560 |
| 06 Planes de acción | 4. Consultar las actividades de una recomendación y su detalle | 4 | F-PLA-08, F-PLA-09, F-PLA-10, F-TAR-01, F-TAR-03, F-TAR-04 | dashboard/src/pages/ActividadesRecomendacion.tsx:96-110; dashboard/src/components/planes-de-accion/ActividadDetailModal.tsx:73-163; main-api/CipratApi/Controladores/ActividadesControlador.cs:496-560 |
| 06 Planes de acción | 5. Consultar los informes de ejecución de una actividad y descargar su PDF | 3 | F-PLA-19 | dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:523-795 |
| 07 Seguimiento | 1. Consultar el listado de Seguimiento y encontrar lo pendiente | 4 | F-SEG-01, F-SEG-02, F-SEG-03 | dashboard/src/contexts/ActionPlanModeContext.tsx:35-37; dashboard/src/components/planes-de-accion/ActionPlanFiltersModal.tsx:119-243; dashboard/src/pages/PlanesDeAccion.tsx:232-267 |
| 07 Seguimiento | 2. Consultar recomendaciones, actividades e informes en Seguimiento | 3 | F-SEG-04, F-TAR-01, F-TAR-03, F-TAR-04 | dashboard/src/components/planes-de-accion/ActividadesTabContent.tsx:254-795; main-api/CipratApi/Servicios/ServicioTareasWorker.cs:27-140; main-api/CipratApi/Servicios/ServicioActividades.cs:928-966 |
| 08 Informe de recomendaciones | 1. Consultar el Informe de recomendaciones | 3 | F-IRE-01, F-IRE-02 | dashboard/src/pages/InformeRecomendaciones.tsx:134-298; dashboard/src/pages/InformeRecomendaciones.tsx:186-187 |
| 09 Reportes | 1. Consultar, buscar y filtrar los reportes de ejecución | 3 | F-REP-01, F-REP-02 | main-api/CipratApi/Controladores/ReportesEjecucionControlador.cs:84-130; dashboard/src/components/reportes-ejecucion/ReportesFiltersModal.tsx:176-409 |
| 09 Reportes | 2. Ver el detalle de un reporte y descargarlo | 2 | F-REP-03, F-REP-04 | dashboard/src/components/reportes-ejecucion/ReporteDetailModal.tsx:121-253; main-api/CipratApi/Controladores/ArchivosControlador.cs:698-733 |
| 09 Reportes | 3. Cargar un reporte de ejecución | 7 | F-REP-05 | main-api/CipratApi/Controladores/ReportesEjecucionControlador.cs:196-250 |
| 09 Reportes | 4. Editar un reporte de ejecución | 3 | F-REP-06 | main-api/CipratApi/Controladores/ReportesEjecucionControlador.cs:293-345 |
| 09 Reportes | 5. Generar un informe ejecutivo en Word (Panel de consultas) | 3 | F-REP-09 | main-api/CipratApi/Controladores/ReportesEjecucionControlador.cs:451-758 |
| 10 Informes de seguimiento | 1. Consultar los informes de seguimiento y descargar su PDF | 3 | F-ISE-01, F-ISE-02, F-ISE-03, F-ISE-04, F-INT-02 | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:127-180; dashboard/src/components/informes-seguimiento/InformesFiltersModal.tsx:97-134; dashboard/src/components/informes-seguimiento/InformeSeguimientoDetailPanel.tsx:104-276 |
| 10 Informes de seguimiento | 2. Cargar un informe de seguimiento y aplicar sus cambios a la alerta | 9 | F-ISE-05, F-ISE-06 | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:185-265; main-api/CipratApi/Servicios/ServicioAccionAlertas.cs:425-432,840-850 |
| 10 Informes de seguimiento | 3. Editar un informe de seguimiento | 4 | F-ISE-08 | main-api/CipratApi/Controladores/AccionAlertasControlador.cs:359-435 |
| 11 Oficios de consumación | 1. Consultar los oficios de consumación y descargar su PDF | 3 | F-OFI-01, F-OFI-02, F-OFI-03, F-OFI-04, F-INT-03 | main-api/CipratApi/Controladores/OficiosConsumacionControlador.cs:47-95; dashboard/src/components/oficios-consumacion/OficiosFiltersModal.tsx:97-134; dashboard/src/components/oficios-consumacion/OficioConsumacionDetailPanel.tsx:102-196 |

### Diferencias con la versión anterior de la Academia

Se comparó con `Refenrence/plan_capacitacion/02_rol_administrador.md` de la Academia (9 módulos, 0 actividades) y con ROLES & PERMISOS-2-3.xlsx (detalle en `analisis/02c_comparacion_academia_xlsx.md`). Diferencias principales, contrastadas con el código:

- Los roles y subroles de esta versión salen del código; la Academia los toma como lista de 8 roles. Esta ruta corresponde a: `02_rol_administrador.md` de la Academia.
- Código de verificación: 4 dígitos (`main-api/CipratApi/Servicios/ServicioAutenticacion.cs:41`), con vigencia de 1 hora; sesión de 720 minutos y cierre por inactividad a los 60 minutos.
- La Academia cita el mensaje "Tiene usuarios asociados o subdirecciones" al eliminar una entidad (`01_rol_super_administrador.md:302`); la pantalla muestra "No es posible eliminar la entidad" (`dashboard/src/pages/UsuariosYEntidades.tsx:677-695`).
- El aviso de los 5 meses que menciona la Academia corresponde en el código a un recordatorio cuando faltan 30 días o menos para el próximo informe, y solo llega a la Entidad Territorial (`main-api/CipratApi/Servicios/ServicioTareasWorker.cs:145-220`).

### Vacíos (NO ENCONTRADO EN CÓDIGO)

- Validación de que la fecha de notificación sea posterior a la fecha de la alerta (NO ENCONTRADO en `main-api/CipratApi/Servicios/ServicioAlertas.cs` ni en `dashboard/src/components/report-alert/ReportAlertModal.tsx`).
- Mínimo de 40 caracteres para "Actividad" y máximo de 4.000 para descripciones (NO ENCONTRADO en DTOs ni en formularios).
- Fecha límite para el primer informe de ejecución: el próximo informe solo se fija al aprobar el primer informe (`main-api/CipratApi/Servicios/ServicioInformesEjecucion.cs:337-346`).
- Servicio para eliminar informes de ejecución (permiso definido sin endpoint; `main-api/CipratApi/Servicios/ServicioPermisos.cs:185-191`).
- Pantallas para cambiar la contraseña con la actual, editar el propio perfil y borrar comentarios (los servicios existen en la API; ninguna pantalla los usa).

### Apoyos visuales de la ruta

| ID | Tipo | Dónde va | Título |
|---|---|---|---|
| MED-02-ACC-01 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación | Pantalla "Configura tu contraseña" |
| MED-02-ACC-02 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-06 | Mensaje ERR-ACC-06 |
| MED-02-ACC-03 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-07 | Mensaje ERR-ACC-07 |
| MED-02-ACC-04 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-08 | Mensaje ERR-ACC-08 |
| MED-02-ACC-05 | Captura | 01 Acceso a la plataforma · Actividad 1 — Activar la cuenta desde la invitación · Escenario ERR-ACC-09 | Mensaje ERR-ACC-09 |
| MED-02-ACC-06 | GIF | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación | Ingreso con código de verificación |
| MED-02-ACC-07 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-01 | Mensaje ERR-ACC-01 |
| MED-02-ACC-08 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-02 | Mensaje ERR-ACC-02 |
| MED-02-ACC-09 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-03 | Mensaje ERR-ACC-03 |
| MED-02-ACC-10 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-04 | Mensaje ERR-ACC-04 |
| MED-02-ACC-11 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-ACC-05 | Mensaje ERR-ACC-05 |
| MED-02-ACC-12 | Captura | 01 Acceso a la plataforma · Actividad 2 — Iniciar sesión con el código de verificación · Escenario ERR-GEN-06 | Mensaje ERR-GEN-06 |
| MED-02-ACC-13 | GIF | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña | Recuperación de la contraseña |
| MED-02-ACC-14 | Captura | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña · Escenario ERR-ACC-10 | Mensaje ERR-ACC-10 |
| MED-02-ACC-15 | Captura | 01 Acceso a la plataforma · Actividad 3 — Recuperar la contraseña · Escenario ERR-ACC-11 | Mensaje ERR-ACC-11 |
| MED-02-ACC-16 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático | Menú del usuario |
| MED-02-ACC-17 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-12 | Mensaje ERR-ACC-12 |
| MED-02-ACC-18 | Captura | 01 Acceso a la plataforma · Actividad 4 — Cerrar sesión y entender el cierre automático · Escenario ERR-ACC-13 | Mensaje ERR-ACC-13 |
| MED-02-ACC-19 | Captura | 01 Acceso a la plataforma · Actividad 5 — Consultar los Términos de uso y contactar al soporte técnico | Términos de uso |
| MED-02-ACC-20 | Captura | 01 Acceso a la plataforma · Actividad 6 — Consultar Mi perfil y verificar el alcance asignado | Mi perfil |
| MED-02-INI-01 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio | Indicadores del Inicio |
| MED-02-INI-02 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio · Escenario ERR-INI-01 | Mensaje ERR-INI-01 |
| MED-02-INI-03 | Captura | 02 Inicio · Actividad 1 — Leer los indicadores del Inicio · Escenario ERR-INI-02 | Mensaje ERR-INI-02 |
| MED-02-INI-04 | Captura | 02 Inicio · Actividad 2 — Consultar la última alerta, el ranking por departamento, las alertas recientes y el mapa | Mapa y ranking del Inicio |
| MED-02-INI-05 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad | Menú lateral del rol |
| MED-02-INI-06 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-12 | Mensaje ERR-GEN-12 |
| MED-02-INI-07 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-11 | Mensaje ERR-GEN-11 |
| MED-02-INI-08 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-01 | Mensaje ERR-GEN-01 |
| MED-02-INI-09 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-03 | Mensaje ERR-GEN-03 |
| MED-02-INI-10 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-05 | Mensaje ERR-GEN-05 |
| MED-02-INI-11 | Captura | 02 Inicio · Actividad 3 — Navegar con el menú lateral y usar el panel de accesibilidad · Escenario ERR-GEN-13 | Mensaje ERR-GEN-13 |
| MED-02-INI-12 | Captura | 02 Inicio · Actividad 4 — Consultar el tablero público sin iniciar sesión | Tablero público |
| MED-02-USU-01 | Captura | 03 Usuarios y entidades · Actividad 1 — Consultar, buscar y filtrar usuarios e invitaciones | Pestaña Usuarios |
| MED-02-USU-02 | Captura | 03 Usuarios y entidades · Actividad 1 — Consultar, buscar y filtrar usuarios e invitaciones · Escenario ERR-USU-17 | Mensaje ERR-USU-17 |
| MED-02-USU-03 | Captura | 03 Usuarios y entidades · Actividad 1 — Consultar, buscar y filtrar usuarios e invitaciones · Escenario ERR-GEN-07 | Mensaje ERR-GEN-07 |
| MED-02-USU-04 | Captura | 03 Usuarios y entidades · Actividad 2 — Ver el detalle de un usuario | Información de Usuario |
| MED-02-USU-05 | Captura | 03 Usuarios y entidades · Actividad 2 — Ver el detalle de un usuario · Escenario ERR-GEN-02 | Mensaje ERR-GEN-02 |
| MED-02-USU-06 | GIF | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario | Invitar un usuario |
| MED-02-USU-07 | Captura | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario · Escenario ERR-USU-01 | Mensaje ERR-USU-01 |
| MED-02-USU-08 | Captura | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario · Escenario ERR-USU-02 | Mensaje ERR-USU-02 |
| MED-02-USU-09 | Captura | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario · Escenario ERR-USU-03 | Mensaje ERR-USU-03 |
| MED-02-USU-10 | Captura | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario · Escenario ERR-USU-04 | Mensaje ERR-USU-04 |
| MED-02-USU-11 | Captura | 03 Usuarios y entidades · Actividad 3 — Invitar un usuario · Escenario ERR-USU-05 | Mensaje ERR-USU-05 |
| MED-02-USU-12 | Captura | 03 Usuarios y entidades · Actividad 4 — Editar un usuario | Editar usuario |
| MED-02-USU-13 | Captura | 03 Usuarios y entidades · Actividad 5 — Activar o inactivar un usuario | Interruptor de estado |
| MED-02-USU-14 | Captura | 03 Usuarios y entidades · Actividad 5 — Activar o inactivar un usuario · Escenario ERR-USU-06 | Mensaje ERR-USU-06 |
| MED-02-USU-15 | Captura | 03 Usuarios y entidades · Actividad 5 — Activar o inactivar un usuario · Escenario ERR-USU-07 | Mensaje ERR-USU-07 |
| MED-02-USU-16 | Captura | 03 Usuarios y entidades · Actividad 5 — Activar o inactivar un usuario · Escenario ERR-USU-08 | Mensaje ERR-USU-08 |
| MED-02-USU-17 | Captura | 03 Usuarios y entidades · Actividad 6 — Reenviar o eliminar una invitación | Vista Invitaciones |
| MED-02-USU-18 | Captura | 03 Usuarios y entidades · Actividad 6 — Reenviar o eliminar una invitación · Escenario ERR-USU-09 | Mensaje ERR-USU-09 |
| MED-02-USU-19 | Captura | 03 Usuarios y entidades · Actividad 7 — Consultar, buscar y filtrar entidades | Pestaña Entidades |
| MED-02-USU-20 | GIF | 03 Usuarios y entidades · Actividad 8 — Agregar una entidad con sus subdirecciones | Agregar entidad |
| MED-02-USU-21 | Captura | 03 Usuarios y entidades · Actividad 8 — Agregar una entidad con sus subdirecciones · Escenario ERR-USU-10 | Mensaje ERR-USU-10 |
| MED-02-USU-22 | Captura | 03 Usuarios y entidades · Actividad 8 — Agregar una entidad con sus subdirecciones · Escenario ERR-USU-11 | Mensaje ERR-USU-11 |
| MED-02-USU-23 | Captura | 03 Usuarios y entidades · Actividad 8 — Agregar una entidad con sus subdirecciones · Escenario ERR-USU-12 | Mensaje ERR-USU-12 |
| MED-02-USU-24 | Captura | 03 Usuarios y entidades · Actividad 9 — Editar una entidad y sus subdirecciones | Editar entidad |
| MED-02-USU-25 | Captura | 03 Usuarios y entidades · Actividad 9 — Editar una entidad y sus subdirecciones · Escenario ERR-USU-14 | Mensaje ERR-USU-14 |
| MED-02-USU-26 | Captura | 03 Usuarios y entidades · Actividad 9 — Editar una entidad y sus subdirecciones · Escenario ERR-USU-15 | Mensaje ERR-USU-15 |
| MED-02-USU-27 | Captura | 03 Usuarios y entidades · Actividad 10 — Eliminar una entidad | Error al eliminar entidad |
| MED-02-USU-28 | Captura | 03 Usuarios y entidades · Actividad 10 — Eliminar una entidad · Escenario ERR-USU-13 | Mensaje ERR-USU-13 |
| MED-02-ALE-01 | Captura | 04 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas | Listado de alertas |
| MED-02-ALE-02 | Captura | 04 Alertas tempranas · Actividad 1 — Consultar, buscar y filtrar alertas tempranas · Escenario ERR-ALE-19 | Mensaje ERR-ALE-19 |
| MED-02-ALE-03 | Captura | 04 Alertas tempranas · Actividad 2 — Ver el detalle de una alerta y descargar su PDF | Detalle de la alerta |
| MED-02-ALE-04 | Captura | 04 Alertas tempranas · Actividad 3 — Consultar el historial de actividades de una alerta | Historial de actividades |
| MED-02-ALE-05 | Captura | 04 Alertas tempranas · Actividad 3 — Consultar el historial de actividades de una alerta · Escenario ERR-GEN-04 | Mensaje ERR-GEN-04 |
| MED-02-ALE-06 | Captura | 04 Alertas tempranas · Actividad 4 — Descargar el listado de alertas en CSV | Botón Descargar |
| MED-02-ALE-07 | Captura | 04 Alertas tempranas · Actividad 4 — Descargar el listado de alertas en CSV · Escenario ERR-GEN-10 | Mensaje ERR-GEN-10 |
| MED-02-ALE-08 | Captura | 04 Alertas tempranas · Actividad 5 — Revisar una alerta en Borrador recibida por X-Road o creada por el Agente IA | Alertas en Borrador |
| MED-02-ALE-09 | Captura | 04 Alertas tempranas · Actividad 6 — Ir a las recomendaciones de una alerta | Menú ⋯ de la alerta |
| MED-02-ALE-10 | Captura | 04 Alertas tempranas · Actividad 6 — Ir a las recomendaciones de una alerta · Escenario ERR-REC-08 | Mensaje ERR-REC-08 |
| MED-02-ALE-11 | GIF | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana | Reportar alerta: pasos 1 y 2 |
| MED-02-ALE-12 | GIF | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana | Reportar alerta: pasos 3 a 6 y envío |
| MED-02-ALE-13 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-01 | Mensaje ERR-ALE-01 |
| MED-02-ALE-14 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-02 | Mensaje ERR-ALE-02 |
| MED-02-ALE-15 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-03 | Mensaje ERR-ALE-03 |
| MED-02-ALE-16 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-04 | Mensaje ERR-ALE-04 |
| MED-02-ALE-17 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-05 | Mensaje ERR-ALE-05 |
| MED-02-ALE-18 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-06 | Mensaje ERR-ALE-06 |
| MED-02-ALE-19 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-07 | Mensaje ERR-ALE-07 |
| MED-02-ALE-20 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-20 | Mensaje ERR-ALE-20 |
| MED-02-ALE-21 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-ALE-23 | Mensaje ERR-ALE-23 |
| MED-02-ALE-22 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-GEN-08 | Mensaje ERR-GEN-08 |
| MED-02-ALE-23 | Captura | 04 Alertas tempranas · Actividad 7 — Reportar una alerta temprana · Escenario ERR-GEN-09 | Mensaje ERR-GEN-09 |
| MED-02-ALE-24 | Captura | 04 Alertas tempranas · Actividad 8 — Editar una alerta | Número bloqueado en la edición |
| MED-02-ALE-25 | Captura | 04 Alertas tempranas · Actividad 8 — Editar una alerta · Escenario ERR-ALE-08 | Mensaje ERR-ALE-08 |
| MED-02-ALE-26 | Captura | 04 Alertas tempranas · Actividad 8 — Editar una alerta · Escenario ERR-ALE-09 | Mensaje ERR-ALE-09 |
| MED-02-ALE-27 | Captura | 04 Alertas tempranas · Actividad 8 — Editar una alerta · Escenario ERR-ALE-10 | Mensaje ERR-ALE-10 |
| MED-02-ALE-28 | Captura | 04 Alertas tempranas · Actividad 8 — Editar una alerta · Escenario ERR-ALE-11 | Mensaje ERR-ALE-11 |
| MED-02-ALE-29 | Captura | 04 Alertas tempranas · Actividad 9 — Publicar una alerta en Borrador | Publicar alerta al guardar |
| MED-02-ALE-30 | Captura | 04 Alertas tempranas · Actividad 9 — Publicar una alerta en Borrador · Escenario ERR-ALE-12 | Mensaje ERR-ALE-12 |
| MED-02-ALE-31 | Captura | 04 Alertas tempranas · Actividad 10 — Subsumir alertas | Subsunción |
| MED-02-REC-01 | Captura | 05 Recomendaciones · Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta | Recomendaciones de una alerta |
| MED-02-REC-02 | Captura | 05 Recomendaciones · Actividad 1 — Consultar, buscar y filtrar las recomendaciones de una alerta · Escenario ERR-REC-07 | Mensaje ERR-REC-07 |
| MED-02-REC-03 | Captura | 05 Recomendaciones · Actividad 2 — Ver el detalle de una recomendación | Detalle de recomendación |
| MED-02-REC-04 | Captura | 05 Recomendaciones · Actividad 3 — Descargar las recomendaciones de una alerta en CSV | CSV de recomendaciones |
| MED-02-REC-05 | GIF | 05 Recomendaciones · Actividad 4 — Agregar una recomendación | Agregar recomendación |
| MED-02-REC-06 | Captura | 05 Recomendaciones · Actividad 4 — Agregar una recomendación · Escenario ERR-REC-01 | Mensaje ERR-REC-01 |
| MED-02-REC-07 | Captura | 05 Recomendaciones · Actividad 4 — Agregar una recomendación · Escenario ERR-REC-02 | Mensaje ERR-REC-02 |
| MED-02-REC-08 | Captura | 05 Recomendaciones · Actividad 4 — Agregar una recomendación · Escenario ERR-REC-03 | Mensaje ERR-REC-03 |
| MED-02-REC-09 | Captura | 05 Recomendaciones · Actividad 4 — Agregar una recomendación · Escenario ERR-REC-04 | Mensaje ERR-REC-04 |
| MED-02-REC-10 | Captura | 05 Recomendaciones · Actividad 4 — Agregar una recomendación · Escenario ERR-REC-05 | Mensaje ERR-REC-05 |
| MED-02-REC-11 | Captura | 05 Recomendaciones · Actividad 5 — Editar una recomendación | Editar recomendación |
| MED-02-PLA-01 | Captura | 06 Planes de acción · Actividad 1 — Consultar y filtrar los planes de acción por alerta | Planes de acción por alerta |
| MED-02-PLA-02 | Captura | 06 Planes de acción · Actividad 2 — Recorrer las recomendaciones del plan de una alerta | Recomendaciones del plan |
| MED-02-PLA-03 | Captura | 06 Planes de acción · Actividad 2 — Recorrer las recomendaciones del plan de una alerta · Escenario ERR-PLA-15 | Mensaje ERR-PLA-15 |
| MED-02-PLA-04 | Captura | 06 Planes de acción · Actividad 3 — Consultar las pestañas globales de Recomendaciones y Actividades | Pestaña global Actividades |
| MED-02-PLA-05 | Captura | 06 Planes de acción · Actividad 4 — Consultar las actividades de una recomendación y su detalle | Actividades de una recomendación |
| MED-02-PLA-06 | Captura | 06 Planes de acción · Actividad 4 — Consultar las actividades de una recomendación y su detalle · Escenario ERR-PLA-06 | Mensaje ERR-PLA-06 |
| MED-02-PLA-07 | Captura | 06 Planes de acción · Actividad 5 — Consultar los informes de ejecución de una actividad y descargar su PDF | Informes de ejecución |
| MED-02-SEG-01 | Captura | 07 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente | Seguimiento de Planes |
| MED-02-SEG-02 | Captura | 07 Seguimiento · Actividad 1 — Consultar el listado de Seguimiento y encontrar lo pendiente · Escenario ERR-SEG-07 | Mensaje ERR-SEG-07 |
| MED-02-SEG-03 | Captura | 07 Seguimiento · Actividad 2 — Consultar recomendaciones, actividades e informes en Seguimiento | Detalle de Actividad en Seguimiento |
| MED-02-IRE-01 | Captura | 08 Informe de recomendaciones · Actividad 1 — Consultar el Informe de recomendaciones | Informe de recomendaciones |
| MED-02-REP-01 | Captura | 09 Reportes · Actividad 1 — Consultar, buscar y filtrar los reportes de ejecución | Reportes de ejecución |
| MED-02-REP-02 | Captura | 09 Reportes · Actividad 1 — Consultar, buscar y filtrar los reportes de ejecución · Escenario ERR-REP-10 | Mensaje ERR-REP-10 |
| MED-02-REP-03 | Captura | 09 Reportes · Actividad 2 — Ver el detalle de un reporte y descargarlo | Detalle del reporte |
| MED-02-REP-04 | Captura | 09 Reportes · Actividad 2 — Ver el detalle de un reporte y descargarlo · Escenario ERR-REP-08 | Mensaje ERR-REP-08 |
| MED-02-REP-05 | Captura | 09 Reportes · Actividad 2 — Ver el detalle de un reporte y descargarlo · Escenario ERR-REP-06 | Mensaje ERR-REP-06 |
| MED-02-REP-06 | GIF | 09 Reportes · Actividad 3 — Cargar un reporte de ejecución | Cargar reporte de ejecución |
| MED-02-REP-07 | Captura | 09 Reportes · Actividad 3 — Cargar un reporte de ejecución · Escenario ERR-REP-01 | Mensaje ERR-REP-01 |
| MED-02-REP-08 | Captura | 09 Reportes · Actividad 3 — Cargar un reporte de ejecución · Escenario ERR-REP-02 | Mensaje ERR-REP-02 |
| MED-02-REP-09 | Captura | 09 Reportes · Actividad 3 — Cargar un reporte de ejecución · Escenario ERR-REP-07 | Mensaje ERR-REP-07 |
| MED-02-REP-10 | Captura | 09 Reportes · Actividad 4 — Editar un reporte de ejecución | Editar reporte |
| MED-02-REP-11 | Captura | 09 Reportes · Actividad 5 — Generar un informe ejecutivo en Word (Panel de consultas) | Panel de consultas |
| MED-02-REP-12 | Captura | 09 Reportes · Actividad 5 — Generar un informe ejecutivo en Word (Panel de consultas) · Escenario ERR-REP-09 | Mensaje ERR-REP-09 |
| MED-02-ISE-01 | Captura | 10 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF | Informes de seguimiento |
| MED-02-ISE-02 | Captura | 10 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF · Escenario ERR-ISE-07 | Mensaje ERR-ISE-07 |
| MED-02-ISE-03 | Captura | 10 Informes de seguimiento · Actividad 1 — Consultar los informes de seguimiento y descargar su PDF · Escenario ERR-ISE-09 | Mensaje ERR-ISE-09 |
| MED-02-ISE-04 | GIF | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta | Cargar informe de seguimiento |
| MED-02-ISE-05 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-01 | Mensaje ERR-ISE-01 |
| MED-02-ISE-06 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-02 | Mensaje ERR-ISE-02 |
| MED-02-ISE-07 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-03 | Mensaje ERR-ISE-03 |
| MED-02-ISE-08 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-04 | Mensaje ERR-ISE-04 |
| MED-02-ISE-09 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-05 | Mensaje ERR-ISE-05 |
| MED-02-ISE-10 | Captura | 10 Informes de seguimiento · Actividad 2 — Cargar un informe de seguimiento y aplicar sus cambios a la alerta · Escenario ERR-ISE-10 | Mensaje ERR-ISE-10 |
| MED-02-ISE-11 | Captura | 10 Informes de seguimiento · Actividad 3 — Editar un informe de seguimiento | Alerta bloqueada en la edición |
| MED-02-ISE-12 | Captura | 10 Informes de seguimiento · Actividad 3 — Editar un informe de seguimiento · Escenario ERR-ISE-08 | Mensaje ERR-ISE-08 |
| MED-02-OFI-01 | Captura | 11 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF | Oficios de consumación |
| MED-02-OFI-02 | Captura | 11 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-02 | Mensaje ERR-OFI-02 |
| MED-02-OFI-03 | Captura | 11 Oficios de consumación · Actividad 1 — Consultar los oficios de consumación y descargar su PDF · Escenario ERR-OFI-05 | Mensaje ERR-OFI-05 |
| MED-02-NOT-01 | Captura | 12 Notificaciones · Actividad 1 — Consultar el panel de Notificaciones | Panel Notificaciones |
| MED-02-NOT-02 | Captura | 12 Notificaciones · Actividad 1 — Consultar el panel de Notificaciones · Escenario ERR-NOT-01 | Mensaje ERR-NOT-01 |
| MED-02-NOT-03 | Captura | 12 Notificaciones · Actividad 2 — Reconocer los correos que envía el sistema y qué hacer con cada uno | Correo del sistema |
