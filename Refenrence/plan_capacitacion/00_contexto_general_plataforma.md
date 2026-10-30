Generado desde: monorepo SI-CIPRAT rama develop commit 56d3f33 (2026-07-17 10:20:06 -0500) · 2026-10-28

# Contexto general de la plataforma SI-CIPRAT

> Documento de consulta general. Las rutas por rol no remiten a él: cada una trae su propio contexto completo en su Módulo 00.

## 1. Qué es SI-CIPRAT

SI-CIPRAT es el Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT), del Ministerio del Interior. Registra las alertas tempranas emitidas por la Defensoría del Pueblo, sus recomendaciones, los planes de acción de las entidades responsables, los informes de ejecución, los informes de seguimiento, los oficios de consumación y el cierre de cada alerta. La Defensoría no es usuaria del sistema: su información llega de forma automática o la registra el Ministerio.

## 2. Módulos

| Código | Módulo | Definición | Objetivo | Fases |
|---|---|---|---|---|
| ACC | Acceso a la plataforma | Conjunto de pantallas y procesos que controlan quién entra a SI-CIPRAT y con qué datos: activación de la cuenta desde la invitación, inicio de sesión con correo, contraseña y código de verificación de 4 dígitos enviado al correo, recuperación de la contraseña, cierre de sesión, cierre automático por inactividad y la pantalla **Mi perfil**, que muestra (sin permitir editarlos) el rol, la entidad, la subdirección y los departamentos del usuario. También muestra los Términos de uso y el correo de soporte técnico. | Permitir que cada usuario ingrese a la plataforma de forma segura con su propia cuenta, la recupere si la pierde y verifique con qué rol y alcance fue configurado. | E0 (y cada vez que se ingresa) |
| INI | Inicio | Tablero de entrada de la plataforma. Muestra la última alerta activa, cinco indicadores (Total de alertas, Alertas activas, Alertas de inminencia, Alertas estructurales, Alertas cerradas) con su tendencia de los últimos meses, el "Porcentaje de Avance Global", el ranking "Alertas por departamento" (Top 10), las "Alertas recientes" y el mapa de municipios con alertas. La misma página, sin sesión, es la vista pública de consulta ciudadana. Incluye el panel de accesibilidad (alto contraste y tamaño de letra). | Dar una vista rápida y georreferenciada del estado de las alertas tempranas y del avance de los planes dentro del alcance del usuario. | E1–E6 (consulta) |
| NOT | Notificaciones | Mecanismos por los que el sistema avisa lo que ocurre: el panel **Notificaciones** del menú lateral, que muestra el historial de actividad de las alertas del alcance del usuario (quién hizo qué y cuándo), y los correos electrónicos automáticos (invitación, código de verificación, restablecimiento de contraseña, recomendaciones asignadas o actualizadas, validación del plan de acción, recordatorio de informe, informe de seguimiento, oficio de consumación y reporte pendiente de aprobación). | Mantener al usuario informado de los eventos que le exigen actuar o que cambian el estado de sus alertas. | E0–E6 |
| USU | Usuarios y entidades | Módulo de administración de las cuentas y de las organizaciones. En la pestaña **Usuarios** se invitan usuarios, se ven sus datos, se editan, se activan o inactivan y se reenvían o eliminan invitaciones. En la pestaña **Entidades** se crean, consultan, editan y eliminan las entidades centrales y sus subdirecciones, con su categoría. | Preparar la plataforma con las entidades responsables y los usuarios correctos, cada uno con el rol y el alcance que le corresponde. | E0 |
| AGE | Agentes IA | Pantalla en la que se carga el PDF de una alerta temprana para que el agente de inteligencia artificial extraiga sus datos y cree la alerta en estado **Borrador**. Muestra el resultado del envío y el "Historial de Procesamiento" (fecha, evento, mensaje, archivo y alerta). | Agilizar el registro de alertas a partir del PDF oficial, dejando un borrador que una persona revisa y publica. | E1 |
| ALE | Alertas tempranas | Módulo central de registro y consulta de las alertas tempranas emitidas por la Defensoría del Pueblo. Permite listar, buscar, filtrar y descargar las alertas; ver su detalle, su PDF y su historial de actividades; reportar una alerta nueva en un formulario de 6 pasos; editarla, publicarla si está en borrador, subsumir otras alertas, eliminarla y cerrar alertas. | Mantener en SI-CIPRAT el registro completo y verificable de cada alerta temprana, desde su llegada hasta su cierre. | E1 (registro) y E6 (cierre); consulta en todas |
| REC | Recomendaciones | Pantalla de las recomendaciones de una alerta (se abre desde la alerta con la acción **Recomendaciones**). Permite listarlas, buscarlas, filtrarlas, ver su detalle y descargarlas; al Super Administrador y al Administrador, crearlas en 2 pasos (eje temático y descripción; entidades principales y asociadas) y editarlas; al Super Administrador, eliminarlas. El sistema asigna el código RC y notifica por correo a las entidades. | Registrar cada recomendación de la alerta con la entidad que debe responder por ella, para que esa entidad formule su plan de acción. | E2 |
| PLA | Planes de acción | Módulo donde se formula y se ejecuta el plan de acción. Tiene tres niveles: alertas con su plan (Ejecutado vs programado, estado del plan e informes), recomendaciones de la alerta y actividades de cada recomendación. Permite a las entidades agregar, editar y eliminar actividades, comentar y reportar o editar informes de ejecución con su PDF; a todos los roles con acceso, consultar, filtrar y descargar la información. Tiene además las pestañas globales Recomendaciones y Actividades y el acceso al Informe de recomendaciones. | Que cada entidad responsable formule las actividades con las que atenderá sus recomendaciones y reporte periódicamente lo ejecutado. | E3 (formulación) y E5 (informes de ejecución) |
| SEG | Seguimiento | Módulo "Seguimiento de Planes": usa las mismas pantallas de Planes de acción en modo de seguimiento. Allí el Monitor, el Líder de Macrozona y el Super Administrador revisan las actividades (comentarios y "Marcar como Revisado"), las aprueban o descartan su aprobación, confirman el plan de acción de la alerta y aprueban los informes de ejecución. Los demás roles con acceso solo consultan. | Revisar y aprobar el plan de acción y su ejecución, actividad por actividad, hasta confirmar el plan y aprobar cada informe. | E4 (revisión, aprobación y confirmación) y E5 (aprobación de informes) |
| IRE | Informe de recomendaciones | Tablero "Informe de recomendaciones: Tablero de seguimiento a las recomendaciones", que se abre con el botón **Informe** de Planes de acción o de Seguimiento. Consolida la información de alertas (total, activas, cerradas), recomendaciones (total, % de cumplimiento, sin actividades, pendientes de aprobación), actividades (total, % de cumplimiento, sin informe) y el cumplimiento por Entidad Principal y por Eje Temático, con filtro por alerta. | Ver en un solo tablero el avance consolidado de las recomendaciones por entidad y por eje temático. | E3–E5 (consulta) |
| REP | Reportes | Módulo "Reportes de ejecución": publica reportes de ejecución consolidados por alerta, entidad, departamento o municipio, con su PDF y un aprobador designado; permite listarlos por pestañas (Todos, Alerta, Entidad, Regional), filtrarlos, ver su detalle, descargarlos, editarlos, eliminarlos y aprobarlos. Incluye el **Panel de consultas**, que genera y descarga informes ejecutivos en Word por alerta, entidad, departamento, municipio o general. | Consolidar y aprobar la información de ejecución para darle visibilidad institucional y producir informes ejecutivos. | E5 |
| ISE | Informes de seguimiento | Módulo donde se registran los informes de seguimiento que emite la Defensoría sobre una alerta. Permite listarlos, filtrarlos por alerta, ver su detalle y descargar su PDF; al Super Administrador y al Administrador, cargarlos en 2 pasos (datos del informe; modificaciones a la alerta: cerrar municipios, agregar municipios y recomendaciones) y editarlos; al Super Administrador, eliminarlos y cerrar la alerta con el informe. | Dejar en el sistema cada informe de seguimiento de la Defensoría y aplicar sus efectos sobre la alerta (municipios, recomendaciones nuevas o cierre). | E6 (y en cualquier momento después de E1) |
| OFI | Oficios de consumación | Módulo donde se registran los oficios de consumación del riesgo que emite la Defensoría. Todos los roles los listan, filtran por alerta, consultan y descargan; solo el Super Administrador los carga en 2 pasos (información del oficio y alertas; modificaciones por alerta), los edita y los elimina. | Registrar la consumación del riesgo advertido y sus efectos en los municipios y recomendaciones de las alertas. | E6 |
| TAR | Tareas programadas | Procesos automáticos que corren todos los días a las 00:01: cierran el ciclo de informe de las actividades cuyo "Próximo Informe" ya venció (las vuelven a "Sin Informe" y suman otra vez su meta a lo programado) y envían el recordatorio de informe cuando faltan 30 días o menos. | Mantener el ciclo semestral de informes de ejecución sin intervención manual. | E5 (automático) |

## 3. Roles y subroles

### Super Administrador

Rol con acceso total a la plataforma. Configura usuarios y entidades, registra alertas y recomendaciones, puede actuar como respaldo en la aprobación de actividades, informes y planes, y es el único que elimina alertas y recomendaciones, cierra alertas, carga oficios de consumación, sube los PDF de las alertas y usa el Agente IA. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:18-303`, `dashboard/src/components/ui/UserFormModal.tsx:422`.


### Administrador

Rol de gestión operativa nacional. Registra y edita alertas, crea y edita recomendaciones, carga y edita informes de seguimiento, carga reportes de ejecución y administra usuarios y entidades. No elimina alertas ni recomendaciones, no cierra alertas, no aprueba actividades, informes ni reportes y no sube archivos de la alerta. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:30-68,83-97,140-153,193-199,254-262`.


### Líder de Macrozona

Rol territorial de supervisión. Tiene en sus departamentos los mismos permisos de revisión y aprobación del Monitor en el módulo Seguimiento (aprobar actividades e informes, confirmar planes) y, además, aprueba los reportes de ejecución en los que fue designado aprobador. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:96-99,140-153,193-199,234-239`.


### Monitor

Rol territorial de revisión y aprobación. En el módulo Seguimiento revisa y comenta las actividades formuladas por las entidades, las aprueba o descarta su aprobación, confirma el plan de acción de la alerta, aprueba los informes de ejecución y carga reportes de ejecución. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:140-153,193-199,213-233`.


### Entidad Territorial

Rol de las entidades responsables de las recomendaciones. Formula las actividades del plan de acción, atiende los comentarios de la revisión y reporta los informes de ejecución con su soporte en PDF. No aprueba. Recibe los correos de negocio del sistema. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:113-139,168-192`, `main-api/CipratApi/Servicios/ServicioNotificacionesRecomendacion.cs:85-89`. Tiene dos subroles que el sistema distingue por el **Nivel de acceso** elegido al invitar: Central y Subdirección.

- **Central:** Usuario de una entidad central (por ejemplo, un ministerio, una gobernación o una alcaldía) que responde por las recomendaciones en las que su entidad es la **Entidad Principal**. El sistema lo identifica con el valor `ENTIDAD_TERRITORIAL_CENTRAL` y con la entidad guardada en su usuario (`EntidadId`). Ve las alertas que tienen al menos una recomendación cuya Entidad Principal es exactamente su entidad central (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:65-66,83-92`); no ve, por ese filtro, las recomendaciones asignadas a las subdirecciones de su entidad, aunque el texto de ayuda del formulario de usuarios diga que el nivel Central "Permite visualizar la información general de la entidad y de todas las subdirecciones asociadas a ella" (`dashboard/src/components/ui/UserFormModal.tsx:509`). Puede agregar, editar y eliminar actividades, comentar y reportar informes de ejecución.
- **Subdirección:** Usuario de una subdirección (dirección, dependencia o secretaría) de una entidad central, que responde por las recomendaciones asignadas directamente a esa subdirección como **Entidad Principal**. El sistema lo identifica con el valor `ENTIDAD_TERRITORIAL_SUBDIRECCION` y con la subdirección guardada en su usuario (`SubEntidadId`). Ve las alertas con al menos una recomendación cuya Entidad Principal es su subdirección (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:59-63`). Tiene las mismas acciones de la entidad central sobre esas recomendaciones: agregar, editar y eliminar actividades, comentar y reportar informes de ejecución. Riesgo conocido R5: el listado global de actividades se filtra con la entidad central del usuario (`EntidadId`) y no con la subdirección (`main-api/CipratApi/Servicios/ServicioActividades.cs:490-495`).

### Consulta

Rol de solo lectura. Consulta alertas, recomendaciones, planes de acción, seguimiento, informes de seguimiento y oficios de consumación, y descarga archivos y listados, sin crear, editar ni aprobar registros de negocio. Evidencia: `main-api/CipratApi/Servicios/ServicioPermisos.cs:18-29,71-82,101-112,156-167`, `dashboard/src/components/ui/UserFormModal.tsx:434-440`. Tiene tres subroles que se distinguen por el alcance de los datos: Global, Entidad y Departamentos.

- **Global:** Usuario de consulta con alcance nacional. El sistema lo identifica con el valor `CONSULTA_GLOBAL`, que no aplica ningún filtro de datos. Ve todas las alertas, recomendaciones, actividades, informes de seguimiento y oficios de consumación. Es el único subrol de Consulta al que el menú le muestra *Usuarios y entidades*, pero la ruta de esa pantalla lo rechaza (`dashboard/src/components/layout/Sidebar.tsx:38-42`, `dashboard/src/components/auth/AdminRoute.tsx:36-40`; riesgo R12).
- **Entidad:** Usuario de consulta limitado a una entidad central. El sistema lo identifica con el valor `CONSULTA_ENTIDAD` y la entidad guardada en su usuario (`EntidadId`). Ve las alertas que tienen al menos una recomendación cuya Entidad Principal es su entidad (`main-api/CipratApi/Servicios/ServicioFiltradoEntidades.cs:65-66,83-92`). Si el usuario no tiene entidad asignada, el servidor no aplica filtro y vería todas las alertas (riesgo R4).
- **Departamentos:** Usuario de consulta limitado a uno o varios departamentos. El sistema lo identifica con el valor `CONSULTA_DEPARTAMENTOS` y la lista de departamentos de su usuario. Ve las alertas que tienen al menos un municipio en esos departamentos (`main-api/CipratApi/Servicios/ServicioFiltradoDepartamentos.cs:16-21,79-88`). No ve el menú *Planes de acción*, pero la ruta de esa pantalla no lo bloquea (`dashboard/src/components/layout/Sidebar.tsx:50-55`, `dashboard/src/App.tsx:56`; riesgo R11).

## 4. Segmentación por ruta

| Ruta | Alcance de datos | Menú |
|---|---|---|
| 01 Super Administrador | todas las alertas del país, sin filtro de entidad ni de departamento | Inicio, Alertas tempranas, Planes de acción, Seguimiento, Reportes, Agentes, Oficios de consumación, Informes de seguimiento, Notificaciones, Usuarios y entidades, Ver Perfil |
| 02 Administrador | todas las alertas del país, sin filtro de entidad ni de departamento | Inicio, Alertas tempranas, Planes de acción, Seguimiento, Reportes, Oficios de consumación, Informes de seguimiento, Notificaciones, Usuarios y entidades, Ver Perfil |
| 03 Líder de Macrozona | las alertas que tienen al menos un municipio en los departamentos asignados a su usuario | Inicio, Alertas tempranas, Seguimiento, Reportes, Oficios de consumación, Informes de seguimiento, Notificaciones, Ver Perfil |
| 04 Monitor | las alertas que tienen al menos un municipio en los departamentos asignados a su usuario | Inicio, Alertas tempranas, Seguimiento, Reportes, Oficios de consumación, Informes de seguimiento, Notificaciones, Ver Perfil |
| 05 Entidad Territorial (Central) | las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su entidad central | Inicio, Alertas tempranas, Planes de acción, Oficios de consumación, Notificaciones, Ver Perfil |
| 06 Entidad Territorial (Subdirección) | las alertas que tienen al menos una recomendación cuya **Entidad Principal** es su subdirección | Inicio, Alertas tempranas, Planes de acción, Oficios de consumación, Notificaciones, Ver Perfil |
| 07 Consulta (Global) | todas las alertas del país, en modo de consulta | Inicio, Alertas tempranas, Planes de acción, Seguimiento, Oficios de consumación, Informes de seguimiento, Notificaciones, Usuarios y entidades, Ver Perfil |
| 08 Consulta (Entidad) | las alertas que tienen al menos una recomendación cuya **Entidad Principal** es la entidad central asignada a su usuario | Inicio, Alertas tempranas, Planes de acción, Seguimiento, Oficios de consumación, Informes de seguimiento, Notificaciones, Ver Perfil |
| 09 Consulta (Departamentos) | las alertas que tienen al menos un municipio en los departamentos asignados a su usuario | Inicio, Alertas tempranas, Seguimiento, Oficios de consumación, Informes de seguimiento, Notificaciones, Ver Perfil |

## 5. Flujo general y cronología E0–E6

| Secuencia | Fase | Actores | Acción | Disparador | Plazo | Estado resultante | ⤴ |
|---|---|---|---|---|---|---|---|
| E0.1 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador | Agregar Entidad (entidad central y subdirecciones) | Ninguno | Antes de la primera alerta | Entidad Activa | |
| E0.2 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador | Enviar invitación (rol, nivel de acceso, entidad, subdirección, departamentos, cargo) | E0.1 (la entidad existe) | La invitación vence a los 7 días | Invitación pendiente | |
| E0.3 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos) | Activar cuenta (crear contraseña) | Correo "SI-CIPRAT - Invitación al Sistema de Alertas Tempranas" | ≤ 7 días desde E0.2 | Usuario Activo | |
| E0.4 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos) | Iniciar Sesión y Validar código | E0.3 | Código válido 1 hora; sesión de 720 minutos; cierre a los 60 minutos de inactividad | Sesión abierta | |
| E0.5 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador | Editar usuario, activar o inactivar, Reenviar o Eliminar invitación | E0.2 | Cuando se requiera | Activo / Inactivo / invitación vigente | |
| E0.6 | Preparación del sistema (usuarios y entidades) | Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos) | ¿Has olvidado tu contraseña? › Restablecer contraseña | El usuario olvidó la contraseña | Enlace válido 1 hora | Contraseña nueva | |
| E1.1 | Registro de la alerta | Defensoría, Sistema | Envío de la alerta de forma automática (con sus recomendaciones) | La Defensoría emite la alerta en su sistema | Día 0 = fecha de notificación | Alerta automática (Borrador o Activa según el mensaje) y recomendaciones automáticas | ⤴ La alerta se emite en el sistema de la Defensoría y llega a SI-CIPRAT |
| E1.2 | Registro de la alerta | Super Administrador | Crear Alerta desde PDF (Agente IA) | Se recibió el PDF de la alerta | | Alerta en Borrador | ⤴ El PDF llega por fuera de la plataforma |
| E1.3 | Registro de la alerta | Super Administrador, Administrador | Reportar alerta › Enviar Alerta (6 pasos) | Se recibió el documento de la alerta | | Alerta Activa (manual) | ⤴ El documento de la alerta llega por fuera de la plataforma |
| E1.4 | Registro de la alerta | Super Administrador | Adjuntar "PDF de la alerta" y "Adjunto" | E1.3 | Antes de confirmar el plan (después la alerta no se edita) | Alerta con PDF | |
| E1.5 | Registro de la alerta | Super Administrador, Administrador | Editar alerta y Publicar alerta al guardar | E1.1 o E1.2 (borrador) o datos por corregir | Antes de confirmar el plan | Borrador → Activa | |
| E1.6 | Registro de la alerta | Super Administrador, Administrador | Esta alerta subsume otras alertas | El documento declara alertas subsumidas | | Alertas subsumidas → Cerrada | |
| E1.7 | Registro de la alerta | Super Administrador | Eliminar alerta | Alerta registrada por error | | Alerta eliminada (borrado lógico) | |
| E2.1 | Recomendaciones | Super Administrador, Administrador | Agregar recomendación › Crear recomendación | Alerta Activa | Antes de confirmar el plan | Recomendación "sin actividad" con código RC; plan "Sin plan" | |
| E2.2 | Recomendaciones | Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección) | Correo "SI-CIPRAT - Nueva Recomendacion Asignada: {código}" | E2.1 o E1.1 | Inmediato | | ⤴ El correo se recibe fuera de la plataforma; la respuesta vuelve como actividades |
| E2.3 | Recomendaciones | Super Administrador, Administrador | Editar recomendación | E2.1 | Antes de confirmar el plan | Correo "Recomendacion Actualizada" | |
| E2.4 | Recomendaciones | Super Administrador | Eliminar recomendación | E2.1 | Antes de confirmar el plan | Recomendación eliminada | |
| E3.1 | Plan de acción (formulación) | Entidad Territorial (Central), Entidad Territorial (Subdirección) | Consultar las recomendaciones asignadas (Ir al plan de acción) | E2.2 | El sistema no fija plazo | |, |
| E3.2 | Plan de acción (formulación) | Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador | Agregar actividad › Reportar actividad | E3.1 | El sistema no fija plazo | Actividad "Pendiente Aprobación"; plan "Pendiente" | |
| E3.3 | Plan de acción (formulación) | Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador | Editar Actividad / Eliminar Actividad | E3.2; actividad pendiente; plan sin confirmar | Antes de la aprobación | Igual estado | |
| E3.4 | Plan de acción (formulación) | Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos) | Comentarios de la actividad | Actividad registrada | |, | |
| E4.1 | Aprobación y confirmación del plan | Monitor, Líder de Macrozona, Super Administrador | Revisar: Comentarios y Marcar como Revisado | E3.2 | El sistema no fija plazo | Revisión registrada (el estado no cambia) | ⤴ Las mesas técnicas de revisión, si existen, ocurren por fuera; vuelven como comentarios y aprobaciones |
| E4.2 | Aprobación y confirmación del plan | Monitor, Líder de Macrozona, Super Administrador | Aprobar / Descartar aprobación | E4.1 | | Actividad "Aprobado" (o vuelve a pendiente) | |
| E4.3 | Aprobación y confirmación del plan | Monitor, Líder de Macrozona, Super Administrador | Confirmar Plan de Acción | Plan "Aprobado" | | Plan confirmado; actividades "Sin Informe" | |
| E4.4 | Aprobación y confirmación del plan | Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección) | Correo "Notificación validación Plan de Acción – Alerta Temprana N° {número}" | E4.3 | Inmediato | |, |
| E4.5 | Aprobación y confirmación del plan | Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador | Agregar actividad a plan confirmado › Continuar | E4.3 | | Plan desconfirmado; nueva actividad pendiente | |
| E5.1 | Informes de ejecución | Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador | Reportar Informe › Reportar informe de ejecución (con PDF) | E4.3 (plan confirmado) | Sin fecha antes del primer informe; luego hasta el Próximo Informe | Informe "Pendiente" | ⤴ El soporte de la ejecución se produce por fuera; vuelve como PDF |
| E5.2 | Informes de ejecución | Entidad Territorial (Central), Entidad Territorial (Subdirección), Super Administrador | Editar Informe | E5.1; informe no aprobado | Hasta su aprobación | Informe "Pendiente" | |
| E5.3 | Informes de ejecución | Monitor, Líder de Macrozona, Super Administrador | Aprobar Informe | E5.1 | | Informe "Aprobado"; Próximo Informe = notificación + 6 meses (luego +6) | |
| E5.4 | Informes de ejecución | Sistema, Entidad Territorial (Central), Entidad Territorial (Subdirección) | Correo "Recordatorio vencimiento plazo presentación de informe de ejecución" | E5.3 (hay Próximo Informe) | Cuando faltan 30 días o menos; una vez por ciclo | |, |
| E5.5 | Informes de ejecución | Sistema | Tarea diaria 00:01: vencimiento del ciclo | Próximo Informe vencido | Diario | Actividad "Sin Informe"; programadas += Número de actividades | |
| E5.6 | Informes de ejecución | Monitor, Líder de Macrozona, Administrador, Super Administrador | Cargar informe (reporte de ejecución) con aprobador | Información de ejecución consolidable | El sistema no fija plazo | Reporte "Sin aprobación"; correo al aprobador | |
| E5.7 | Informes de ejecución | Líder de Macrozona, Super Administrador | Aprobar informe (reporte de ejecución), solo el aprobador designado | E5.6 | | Reporte "Aprobado" | |
| E5.8 | Informes de ejecución | Monitor, Líder de Macrozona, Administrador, Super Administrador | Consultas › Generar consulta (informe ejecutivo Word) | Cuando se requiera | | Documento Word descargado | |
| E5.9 | Informes de ejecución | Monitor, Líder de Macrozona, Administrador, Super Administrador | Informe (Informe de recomendaciones) | Cuando se requiera | |, | |
| E6.1 | Seguimiento y cierre | Super Administrador, Administrador, Defensoría | Cargar informe de seguimiento (con municipios, recomendaciones y cierre opcional) | La Defensoría emitió un informe de seguimiento | | Informe registrado; cambios aplicados; correo a las entidades | ⤴ El informe lo emite la Defensoría por fuera (o llega de forma automática) |
| E6.2 | Seguimiento y cierre | Super Administrador, Defensoría | Cargar oficio de consumación | La Defensoría emitió un oficio de consumación | | Oficio registrado; correo a las entidades | ⤴ El oficio lo emite la Defensoría por fuera (o llega de forma automática) |
| E6.3 | Seguimiento y cierre | Super Administrador | Cerrar alertas | Decisión de cierre de la Defensoría | | Alerta Cerrada; plan e informes "Cerrado" | ⤴ La decisión de cierre se toma por fuera; vuelve con el consecutivo y el PDF |
| E1–E6 | Registro de la alerta | Super Administrador, Administrador, Líder de Macrozona, Monitor, Entidad Territorial (Central), Entidad Territorial (Subdirección), Consulta (Global), Consulta (Entidad), Consulta (Departamentos) | Consultar alertas, recomendaciones, planes, seguimiento, informes y oficios; descargar CSV y PDF | Desde E1 | Permanente | |, |

## 6. Estados

| Objeto | Estados (texto en pantalla) |
|---|---|
| Alerta | Borrador, Activa, Cerrada |
| Plan de acción | Sin recomendaciones, Sin plan, Pendiente, Aprobado, Cerrado; confirmado sí/no |
| Actividad | Pendiente Aprobación, Aprobado |
| Informe de ejecución | Pendiente, Aprobado, Completado |
| Estado de informes de la actividad | Sin Informe, Sin Completar, Pendiente, Aprobado |
| Reporte de ejecución | Sin aprobación, Aprobado |
| Usuario | Invitación pendiente, Invitación expirada, Activo, Inactivo |

## 7. Autenticación

Invitación por correo (7 días) → **Activar cuenta** (contraseña de al menos 8 caracteres con un carácter especial, distinta de las 5 anteriores) → **Iniciar Sesión** con correo y contraseña → código de 4 dígitos por correo (1 hora) → **Validar código**. Sesión de 720 minutos; cierre por inactividad a los 60 minutos; recuperación con **¿Has olvidado tu contraseña?** (enlace de 1 hora).

## 8. Notificaciones

Panel **Notificaciones** (historial de actividad del alcance) para todos; correos de negocio solo para la Entidad Territorial; correo de reporte pendiente para el aprobador designado. Ver `analisis/07_notificaciones_reportes.md`.

## 9. Glosario completo de la plataforma

| Término | Tipo | Significado | Qué implica | Dónde aparece |
|---|---|---|---|---|
| ¿Has olvidado tu contraseña? | botón | Inicia la recuperación de la contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Activar cuenta | botón | Crea la contraseña y activa la cuenta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Actualizar | botón | Recarga el Historial de Procesamiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Agentes IA |
| Agregar actividad | botón | Abre el registro de una actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Agregar entidad | botón | Guarda la entidad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Agregar Entidad | botón | Abre el registro de una entidad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Agregar recomendación | botón | Abre el registro de una recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Recomendaciones |
| Agregar subdirección | botón | Agrega una fila de subdirección. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Aplicar filtros | botón | Aplica los filtros elegidos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento, Usuarios y entidades, Reportes, Informes de seguimiento, Oficios de consumación |
| Aprobar | botón | Aprueba la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Aprobar informe | botón | Aprueba el reporte de ejecución (aprobador designado). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes |
| Aprobar Informe | botón | Aprueba el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Asociar entidades | botón | Agrega entidades asociadas a la Entidad Principal. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Recomendaciones |
| Atrás | botón | Regresa al paso anterior. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Informes de seguimiento, Oficios de consumación |
| Cancelar | botón | Cierra sin guardar. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento, Usuarios y entidades, Reportes, Informes de seguimiento, Oficios de consumación |
| Cargar informe | botón | Abre la carga (reporte de ejecución o informe de seguimiento). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes, Informes de seguimiento |
| Cargar oficio | botón | Abre o guarda la carga de un oficio. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Oficios de consumación |
| Cerrar alertas | botón | Abre el cierre de alertas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas |
| Comentarios | botón | Abre la conversación de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción, Seguimiento |
| Confirmar | botón | Confirma la acción de la ventana. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Confirmar Plan de Acción | botón | Abre la confirmación del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Consultas | botón | Abre el Panel de consultas. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes |
| Continuar | botón | Acepta agregar una actividad a un plan confirmado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Crear Alerta desde PDF | botón | Envía el PDF al Agente IA. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Agentes IA |
| Crear nuevo registro | botón | Registra otra revisión de la misma actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Crear recomendación | botón | Guarda la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Recomendaciones |
| Descargar | botón | Descarga el listado en CSV o el archivo. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento, Informes de seguimiento, Oficios de consumación |
| Descargar reporte | botón | Descarga el PDF del reporte. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes |
| Descartar aprobación | botón | Devuelve la actividad aprobada a pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Editar Actividad | botón | Abre la edición de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Editar informe | botón | Edita el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Informes de seguimiento |
| Editar Informe | botón | Abre la edición del informe pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Eliminar Actividad | botón | Elimina la actividad pendiente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Eliminar informe | botón | Elimina el informe de seguimiento. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Informes de seguimiento |
| Eliminar invitación | botón | Elimina una invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Eliminar reporte | botón | Elimina un reporte no aprobado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes |
| Enviar Alerta | botón | Guarda la alerta nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas |
| Enviar invitación | botón | Abre el formulario de invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Enviar Invitación | botón | Envía la invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Filtros | botón | Abre los filtros del listado. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento, Usuarios y entidades, Reportes, Informes de seguimiento, Oficios de consumación |
| Generar consulta | botón | Genera el informe ejecutivo en Word. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Reportes |
| Guardar Cambios | botón | Guarda la edición (alerta o usuario). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Usuarios y entidades |
| Haz clic para reenviar | botón | Envía un nuevo código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Informe | botón | Abre el Informe de recomendaciones. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción, Seguimiento, Informe de recomendaciones |
| Iniciar Sesión | botón | Valida correo y contraseña y envía el código. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Ir al plan de acción | botón | Abre las recomendaciones del plan de la alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción, Seguimiento |
| Limpiar filtros | botón | Quita todos los filtros. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento, Usuarios y entidades, Reportes, Informes de seguimiento, Oficios de consumación |
| Marcar como Revisado | botón | Deja constancia de la revisión (no cambia el estado). | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Seguimiento |
| Mostrar 10 mas | botón | Carga 10 registros más. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Notificaciones, Alertas tempranas |
| Reenviar | botón | Reenvía una invitación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Usuarios y entidades |
| Reportar actividad | botón | Guarda la actividad nueva. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Reportar alerta | botón | Abre el registro manual de una alerta. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas |
| Reportar Informe | botón | Abre el informe de ejecución de la actividad. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Reportar informe de ejecución | botón | Guarda el informe de ejecución. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción |
| Restablecer contraseña | botón | Envía el enlace o guarda la nueva contraseña. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Siguiente | botón | Avanza al siguiente paso del asistente. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Alertas tempranas, Recomendaciones, Planes de acción, Informes de seguimiento, Oficios de consumación |
| Validar código | botón | Valida el código de 4 dígitos. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Acceso a la plataforma |
| Ver Actividades | botón | Abre las actividades de la recomendación. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción, Seguimiento |
| Ver Alerta | botón | Abre la última alerta del banner. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Inicio |
| Ver detalle | botón | Abre el detalle del registro. | Ejecuta la acción si su rol la tiene; si no, aparece deshabilitado con un mensaje. | Planes de acción, Seguimiento, Usuarios y entidades, Informes de seguimiento, Oficios de consumación |
| % cumplimiento | campo | Ejecutadas ÷ programadas × 100. | Indicador de avance de actividad, recomendación y alerta. | Planes de acción, Seguimiento, Alertas tempranas |
| Acciones complementarias | campo | Área de texto., | Obligatorio: No | Cargar informe de ejecución / Editar informe de ejecución |
| Acciones de coordinación | campo | Área de texto., | Obligatorio: No | Cargar informe de ejecución / Editar informe de ejecución |
| Acciones implementadas | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Actividades ejecutadas | campo | Lista de selección (número). Entero de 0 al Número de actividades | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Adjunto | campo | Archivo. PDF ≤ 20 MB; solo lo sube el Super Administrador | Obligatorio: No | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Agregar nuevos municipios | campo | Listas con búsqueda., | Obligatorio: No | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Agregar nuevos municipios (Departamento y Municipio) | campo | Listas con búsqueda. Alerta no cerrada | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Alerta | campo | Lista con búsqueda. Alerta existente | Obligatorio: Condicional: Tipo = Alerta | Cargar reporte de ejecución / Editar reporte |
| Alerta asociada | campo | Lista con búsqueda. Alerta existente | Obligatorio: Sí | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Alertas | campo | Lista de selección múltiple. Solo alertas activas | Obligatorio: Sí (al menos una) | Cerrar alertas (2 pasos) |
| Alertas asociadas | campo | Lista de selección múltiple con búsqueda. Alertas existentes | Obligatorio: Sí (al menos una) | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Alertas subsumidas | campo | Lista de selección múltiple con búsqueda. Alertas activas no subsumidas | Obligatorio: Condicional: si el interruptor está activo | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Aprobador | campo | Usuario designado para aprobar un reporte de ejecución. | Solo él puede aprobar. | Reportes |
| Archivo adjunto (PDF del informe) | campo | Archivo. PDF ≤ 20 MB | Obligatorio: Sí (en pantalla) | Cargar informe de ejecución / Editar informe de ejecución |
| Archivo PDF de la alerta | campo | Archivo. PDF; ≤ 20 MB en el servidor | Obligatorio: Sí | Crear Alerta Temprana usando PDF |
| Área | campo | Texto., | Obligatorio: No | Enviar invitación / Editar usuario |
| Buenas prácticas | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Cargo | campo | Texto. No vacío cuando es obligatorio | Obligatorio: Condicional: obligatorio para Entidad Territorial, Líder de Macrozona y Monitor | Enviar invitación / Editar usuario |
| Categoría | campo | Lista con búsqueda. Una categoría del catálogo | Obligatorio: Sí | Agregar / Editar entidad territorial |
| Cerrar la alerta con este informe | campo | Casilla. Solo el Super Administrador puede cerrar | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Código de verificación (4 casillas) | campo | Número (4 dígitos, uno por casilla). Solo dígitos 0-9; vigente 1 hora | Obligatorio: Sí | Iniciar sesión |
| Código RC | campo | Código de la recomendación RC-{NNN}-{AAAA}-{NNN}. | Lo asigna el sistema; no corresponde al número de la recomendación en el documento. | Recomendaciones, Planes de acción, Seguimiento |
| Conducta Vulneratoria | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos una) | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Confirmar Contraseña | campo | Texto oculto. Igual a Nueva Contraseña | Obligatorio: Sí | Activar la cuenta (Configura tu contraseña) |
| Consecutivo | campo | Texto (solo números). Solo dígitos; máx. 500; no usado antes | Obligatorio: Sí | Cerrar alertas (2 pasos) |
| Contraseña | campo | Texto oculto. La contraseña vigente | Obligatorio: Sí | Iniciar sesión |
| Correo electrónico | campo | Texto (correo). Formato de correo | Obligatorio: Sí | Iniciar sesión |
| Creación: Manual / Automática | campo | Cómo se creó la alerta o la recomendación. | Las automáticas llegan desde otros sistemas o las crea el Agente IA. | Alertas tempranas, Recomendaciones |
| Departamento | campo | Lista con búsqueda. Departamento del catálogo | Obligatorio: Sí (al menos una ubicación) | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Departamentos | campo | Lista de selección múltiple con búsqueda. Al menos uno | Obligatorio: Condicional: obligatorio para Monitor, Líder de Macrozona y Consulta Departamentos | Enviar invitación / Editar usuario |
| Descripción | campo | Área de texto. Mínimo 1 carácter; sin máximo | Obligatorio: Sí | Agregar recomendación / Editar recomendación (2 pasos) |
| Dificultades | campo | Área de texto., | Obligatorio: No | Cargar informe de ejecución / Editar informe de ejecución |
| Economías ilegales | campo | Lista de selección múltiple con búsqueda., | Obligatorio: No | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Ejecutadas / Programadas | campo | Actividades ejecutadas frente a las programadas acumuladas. | Programadas suma el Número de actividades en cada ciclo. | Planes de acción, Seguimiento, Alertas tempranas, Inicio |
| Entidad | campo | Lista con búsqueda. Entidad existente | Obligatorio: Condicional: Tipo = Entidad | Cargar reporte de ejecución / Editar reporte |
| Entidad Central | campo | Lista con búsqueda. Entidad central activa | Obligatorio: Condicional: obligatoria para Entidad Territorial y Consulta Entidad; "(opcional)" para Administrador, Líder de Macrozona y Monitor; no aparece para los demás | Enviar invitación / Editar usuario |
| Entidad Principal | campo | Entidad responsable de la recomendación y de reportar el informe de ejecución. | Sus usuarios de Entidad Territorial ven la recomendación y reciben los correos. | Recomendaciones, Planes de acción, Seguimiento, Informe de recomendaciones |
| Entidades asociadas | campo | Entidades que apoyan una recomendación. | Reciben correo, pero no ven la recomendación. | Recomendaciones |
| Esta alerta subsume otras alertas | campo | Interruptor., | Obligatorio: No | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Etiqueta | campo | Lista de selección única., | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Fecha de consumación | campo | Fecha., | Obligatorio: Sí | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Fecha de emisión | campo | Fecha., | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Fecha de inicio y fin (Fin de ejecución) | campo | Fecha. ≥ fecha de inicio | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Fecha de inicio y fin (Inicio ejecución) | campo | Fecha., | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Fecha de notificación | campo | Fecha (calendario). Fecha válida; es el día 0 de los informes; no se compara con la fecha de la alerta | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Fecha de reporte | campo | Fecha. Fecha válida | Obligatorio: Sí | Cargar reporte de ejecución / Editar reporte |
| Fecha del oficio | campo | Fecha., | Obligatorio: Sí | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Grupos armados ilegales | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos uno) | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Historial Plan de acción | campo | Eventos del plan de una alerta. | Permite ver confirmaciones y desconfirmaciones. | Planes de acción, Seguimiento |
| Instrumento de planeación | campo | Selección única (Sí / No)., | Obligatorio: Sí | Agregar actividad / Editar actividad (2 pasos) |
| Municipio | campo | Lista con búsqueda (dependiente). Código DANE de 5 dígitos; se pueden agregar varios | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Municipios actuales de la alerta (Marcar como cerrado) | campo | Casilla por municipio. Alerta no cerrada | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Nivel de acceso | campo | Lista de selección única., | Obligatorio: Condicional: solo si Rol = Entidad Territorial | Enviar invitación / Editar usuario |
| Nivel de acceso: Central / Subdirección | campo | Subdivisión del rol Entidad Territorial. | Central: entidad central; Subdirección: solo la subdirección elegida. | Usuarios y entidades, Acceso a la plataforma |
| Nombres y Apellidos (Apellidos) | campo | Texto. No vacío | Obligatorio: Sí | Enviar invitación / Editar usuario |
| Nombres y Apellidos (Nombres) | campo | Texto. No vacío | Obligatorio: Sí | Enviar invitación / Editar usuario |
| Nueva Contraseña | campo | Texto oculto. Mínimo 8 caracteres y al menos un carácter especial | Obligatorio: Sí | Activar la cuenta (Configura tu contraseña) |
| Número de actividades | campo | Meta de la actividad por cada ciclo de 6 meses. | Se suma a lo programado en cada ciclo. | Planes de acción, Seguimiento |
| Número de informe | campo | Texto. Máx. 500; único | Obligatorio: Sí | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Número de radicado | campo | Texto. Máx. 500 | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Número y fecha de alerta (fecha) | campo | Fecha (calendario). Fecha válida | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Número y fecha de alerta (número) | campo | Texto. Formato `AT-XXX-XXXX` (3 y 4 caracteres alfanuméricos), máx. 50, único. La pantalla solo valida que no esté vacío | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Objetivo | campo | Área de texto. Mínimo 1 carácter; sin máximo | Obligatorio: Sí | Agregar actividad / Editar actividad (2 pasos) |
| Observaciones | campo | Área de texto. Sin límite | Obligatorio: No | Agregar actividad / Editar actividad (2 pasos) |
| PDF de la alerta | campo | Archivo. PDF ≤ 20 MB; solo lo sube el Super Administrador | Obligatorio: No | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| PDF del informe | campo | Archivo. PDF ≤ 20 MB | Obligatorio: Sí (si no hay archivo existente) | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| PDF del informe de seguimiento | campo | Archivo. PDF ≤ 20 MB | Obligatorio: No | Cerrar alertas (2 pasos) |
| PDF del Oficio | campo | Archivo. PDF ≤ 20 MB | Obligatorio: Sí (si no hay archivo existente) | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Población afectada | campo | Lista de selección múltiple con búsqueda. Al menos una opción | Obligatorio: Sí (al menos una) | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Porcentaje de Avance Global | campo | Promedio del % de cumplimiento de las alertas no borrador del alcance. | Las alertas sin actividades cuentan como 0 %. | Inicio |
| Próximo Informe | campo | Fecha límite del siguiente informe de la actividad. | Se fija al aprobar un informe: notificación + 6 meses y luego +6; al vencer se abre un nuevo ciclo. | Planes de acción, Seguimiento |
| Publicar alerta al guardar | campo | Interruptor., | Obligatorio: Condicional: solo aparece al editar una alerta en Borrador | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Recomendaciones (Eje temático, Descripción, Entidad principal) | campo | Sub-formulario repetible. Eje y entidad activa | Obligatorio: No | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Recomendaciones (Eje tematico, Descripción, Entidad principal) · **Agregar** | campo | Sub-formulario repetible. Eje y entidad activa; alerta no cerrada | Obligatorio: No | Cargar informe de seguimiento / Editar informe de seguimiento (2 pasos) |
| Recursos | campo | Selección única (Sí / No)., | Obligatorio: Sí | Agregar actividad / Editar actividad (2 pasos) |
| Resultados | campo | Área de texto. Mínimo 1 carácter | Obligatorio: Sí | Cargar informe de ejecución / Editar informe de ejecución |
| Rol | campo | Lista de selección única., | Obligatorio: Sí | Enviar invitación / Editar usuario |
| Sub Direcciones (interruptor) | campo | Interruptor. Si está activo, al menos una subdirección | Obligatorio: No | Agregar / Editar entidad territorial |
| Subdirección | campo | Lista con búsqueda. Subdirección activa de la Entidad Central | Obligatorio: Condicional: obligatoria si Nivel de acceso = Subdirección | Enviar invitación / Editar usuario |
| Subdirección (cada fila) · **Agregar subdirección** | campo | Texto repetible. Una fila por subdirección | Obligatorio: Condicional: si el interruptor está activo | Agregar / Editar entidad territorial |
| Tema clave | campo | Texto. Máx. 500 | Obligatorio: No | Cargar oficio de consumación / Editar oficio (2 pasos) |
| Tema Clave | campo | Descripción de la alerta. | Aparece en la columna Tema. | Alertas tempranas |
| Tipo | campo | Lista de selección única., | Obligatorio: Sí | Cargar reporte de ejecución / Editar reporte |
| Tipo de alerta | campo | Lista de selección única., | Obligatorio: Sí | Reportar alerta temprana / Editar alerta temprana (6 pasos) |
| Tipo de consulta | campo | Lista de selección única., | Obligatorio: Sí | Panel de consultas (informe ejecutivo) |
| Categoría (de entidad) | catálogo | 89 categorías de entidad (Alcaldía, Gobernación, Ministerio…). | Se usa para filtrar entidades y usuarios. | Usuarios y entidades |
| Eje temático | catálogo | Lista de 14 ejes de las recomendaciones. | El servidor no valida contra la lista. | Recomendaciones, Planes de acción, Seguimiento, Informe de recomendaciones, Informes de seguimiento, Oficios de consumación |
| Etiqueta: Nacional / Regional / Internacional | catálogo | Alcance territorial de la alerta. | Las etiquetas Focalizado y Binacional solo llegan de forma automática. | Alertas tempranas |
| Plazo de implementación | catálogo | 1 a 3 meses, 3 a 6 meses, 6 a 9 meses, Permanente. | Solo informativo. | Planes de acción, Seguimiento |
| Tipo de alerta: Inminencia / Estructural | catálogo | Clasificación de la alerta por su urgencia. | Inminencia se pinta en rojo y Estructural en azul en el mapa. | Alertas tempranas, Inicio |
| Tipo de reporte: Alerta / Entidad / Depto / Municipio / General | catálogo | Alcance de un reporte o consulta. | General solo en el Panel de consultas. | Reportes |
| Actividad | concepto | Acción que la entidad se compromete a ejecutar para una recomendación, con meta por semestre. | Se aprueba una por una y se reporta con informes de ejecución. | Planes de acción, Seguimiento |
| Alerta temprana | concepto | Documento de la Defensoría del Pueblo que advierte un riesgo; en SI-CIPRAT es el registro central del ciclo. | Todo el trabajo (recomendaciones, plan, informes) cuelga de una alerta. | Alertas tempranas, Inicio |
| Informe de ejecución | concepto | Reporte semestral de lo ejecutado en una actividad, con su PDF. | Lo aprueban el Monitor o el Líder; al aprobarlo se fija el próximo informe. | Planes de acción, Seguimiento |
| Informe de seguimiento | concepto | Documento de la Defensoría que hace seguimiento a una alerta. | Puede agregar municipios y recomendaciones o cerrar la alerta. | Informes de seguimiento |
| Oficio de consumación | concepto | Documento de la Defensoría que informa que el riesgo se consumó. | Se asocia a alertas y puede modificar sus municipios. | Oficios de consumación |
| Plan de acción | concepto | Conjunto de actividades de todas las recomendaciones de una alerta. | Se confirma completo por alerta. | Planes de acción, Seguimiento, Alertas tempranas |
| Recomendación | concepto | Acción que la alerta pide a una Entidad Principal; tiene código RC. | La Entidad Principal le formula actividades. | Recomendaciones, Planes de acción, Seguimiento |
| Reporte de ejecución | concepto | Reporte consolidado publicado en Reportes, con aprobador designado. | Lo aprueba solo su aprobador. | Reportes |
| Subsunción | concepto | Una alerta nueva reemplaza a otras, que quedan cerradas. | Irreversible. | Alertas tempranas |
| Activa | estado | Alerta vigente sobre la que se trabajan recomendaciones, planes e informes. | Se le cargan recomendaciones y actividades; puede editarse mientras el plan no esté confirmado. | Alertas tempranas, Inicio |
| Activo | estado | Usuario que puede iniciar sesión. | Puede inactivarse con el interruptor. | Usuarios y entidades |
| Aprobado | estado | Actividad aprobada; o plan con todas sus actividades aprobadas; o informe o reporte aprobado. | Una actividad aprobada no se edita; un plan Aprobado se puede confirmar; un informe aprobado no se edita. | Planes de acción, Seguimiento, Reportes |
| Aprobado - Sin Informe | estado | Opción del filtro de actividades: actividad aprobada sin informe del ciclo. | La entidad debe reportar el informe. | Planes de acción, Seguimiento |
| Borrador | estado | Alerta creada por el Agente IA o recibida de forma automática que aún no se publica. | No cuenta en los indicadores; se revisa y se publica con "Publicar alerta al guardar". | Alertas tempranas, Agentes IA, Inicio |
| Cerrada | estado | Alerta terminada (por cierre, informe de seguimiento, subsunción o actualización automática). | No se edita ni se reabre; su plan y sus informes quedan en "Cerrado". | Alertas tempranas, Inicio, Planes de acción, Seguimiento |
| Completado | estado | Informe que quedó cerrado al aprobar la actividad con un informe pendiente. | No se calcula el próximo informe en ese caso. | Planes de acción, Seguimiento |
| Inactivo | estado | Usuario que no puede iniciar sesión ("Cuenta no activa"). | Puede reactivarse con el interruptor. | Usuarios y entidades, Acceso a la plataforma |
| Invitación Expirada | estado | Invitación no aceptada en 7 días. | Se debe reenviar. | Usuarios y entidades |
| Invitación Pendiente | estado | Usuario invitado que aún no activa su cuenta (7 días). | Se puede reenviar o eliminar la invitación. | Usuarios y entidades |
| Pendiente | estado | En el plan: hay actividades por aprobar. En el informe: hay informes por aprobar. | El Monitor o el Líder de Macrozona deben revisar y aprobar. | Planes de acción, Seguimiento |
| Pendiente Aprobación | estado | Estado de una actividad recién formulada o devuelta. | La entidad puede editarla o eliminarla; el Monitor o el Líder pueden aprobarla. | Planes de acción, Seguimiento |
| Plan de acción confirmado | estado | Plan cuya aprobación cerró el Monitor, el Líder o el Super Administrador con "Confirmar". | Habilita los informes de ejecución y bloquea la edición de la alerta, las recomendaciones y las actividades. | Planes de acción, Seguimiento |
| Sin aprobación | estado | Reporte de ejecución que espera al aprobador designado. | Se puede editar o eliminar (Super Administrador). | Reportes |
| Sin Completar | estado | Estado de informes de la alerta cuando hay actividades sin informe del ciclo. | Faltan informes por reportar. | Planes de acción, Seguimiento |
| Sin Informe | estado | Actividad aprobada que aún no reporta el informe del ciclo. | La entidad puede usar "Reportar Informe". | Planes de acción, Seguimiento |
| Sin plan | estado | Estado del plan cuando ninguna recomendación tiene actividades. | La Entidad Territorial debe formular actividades. | Planes de acción, Seguimiento |
| Sin recomendaciones | estado | Estado del plan de una alerta que aún no tiene recomendaciones. | Se deben cargar recomendaciones (Super Administrador o Administrador). | Planes de acción, Seguimiento |
| Agregar actividad a plan confirmado: Al agregar una nueva actividad a la alerta … el plan de acción será desconfirmado automáticamente. … El estado del plan volverá a  | mensaje | Regla de desconfirmación automática. | Aparece cuando: Agregar una actividad cuando el plan ya está confirmado | Planes de acción |
| Alerta cerrada: No es posible editar una alerta que ya ha sido cerrada. | mensaje | Las alertas cerradas no se modifican. | Aparece cuando: Editar una alerta cerrada | Alertas tempranas |
| Código de autenticación inválido | mensaje | El código no coincide con el último enviado. | Aparece cuando: Escribir mal el código de 4 dígitos | Acceso a la plataforma |
| Código expirado | mensaje | El código vence 1 hora después de enviado. | Aparece cuando: Usar un código después de 1 hora | Acceso a la plataforma |
| Conflicto con el estado actual del recurso. | mensaje | Otro usuario o una acción anterior cambió el estado del registro (409). | Aparece cuando: Repetir una acción o actuar sobre un registro que cambió de estado | General |
| Credenciales inválidas | mensaje | El correo no existe o la contraseña no corresponde. | Aparece cuando: Escribir mal el correo o la contraseña | Acceso a la plataforma |
| Cuenta no activa | mensaje | El administrador cambió el estado del usuario a Inactivo. | Aparece cuando: Ingresar con una cuenta inactivada | Acceso a la plataforma |
| Debe agregar al menos una ubicación | mensaje | La alerta necesita al menos un departamento y municipio. | Aparece cuando: Avanzar del Paso 2 sin municipios | Alertas tempranas |
| Debe seleccionar al menos un grupo armado ilegal | mensaje | Cada uno de esos pasos exige al menos una opción. | Aparece cuando: Avanzar de los Pasos 3, 4 o 5 sin selección | Alertas tempranas |
| Debe tener al menos 8 caracteres | mensaje | La contraseña no cumple las reglas. | Aparece cuando: Crear una contraseña corta o sin símbolos | Acceso a la plataforma |
| Disponible en escritorio: Para una mejor experiencia, esta funcionalidad está optimizada para usarse desde un computador de escritorio. | mensaje | Los formularios de registro se bloquean en pantallas pequeñas. | Aparece cuando: Abrir un formulario de registro desde un celular | General |
| El archivo excede el tamaño máximo de {N} MB | mensaje | El servidor acepta hasta 20 MB por archivo. | Aparece cuando: Seleccionar un PDF muy pesado | General |
| El archivo excede el tamaño máximo de 50 MB | mensaje | La pantalla admite hasta 50 MB, pero el servidor limita los archivos a 20 MB. | Aparece cuando: Seleccionar un PDF de más de 50 MB (o de más de 20 MB en el servidor) | Agentes IA |
| El cargo es obligatorio para este rol | mensaje | Falta un dato que el servidor exige para el rol. | Aparece cuando: El servidor rechaza la invitación por datos del rol | Usuarios y entidades |
| El consecutivo '…' ya existe. Por favor use un número diferente. | mensaje | Cada consecutivo se usa una sola vez. | Aparece cuando: Usar un consecutivo de cierre ya registrado | Alertas tempranas |
| El consecutivo es requerido | mensaje | Faltan datos del cierre. | Aparece cuando: Cerrar alertas con datos incompletos | Alertas tempranas |
| El contenido no puede exceder 2000 caracteres | mensaje | Límite de 2.000 caracteres o falla de conexión. | Aparece cuando: Enviar un comentario muy largo o con falla | Planes de acción |
| El correo electrónico ya existe | mensaje | El correo debe ser único. | Aparece cuando: Invitar o editar con un correo ya registrado | Usuarios y entidades |
| El eje temático es requerido | mensaje | Faltan datos obligatorios. | Aparece cuando: Avanzar o guardar sin datos | Recomendaciones |
| El enlace de invitación es inválido. Verifica que el enlace esté completo. | mensaje | El enlace se cortó al copiarlo o la cuenta ya se activó. | Aparece cuando: Abrir un enlace de invitación incompleto o ya usado | Acceso a la plataforma |
| El enlace de invitación ha expirado. Solicita un nuevo enlace al administrador. | mensaje | La invitación vence a los 7 días. | Aparece cuando: Abrir el enlace de invitación después de 7 días | Acceso a la plataforma |
| El informe se registró sin el documento PDF: No se pudo adjuntar el documento PDF obligatorio. Edite el informe para adjuntarlo. | mensaje | Falla al subir el archivo. | Aparece cuando: El PDF del informe no se adjunta | Informes de seguimiento |
| El informe ya está aprobado | mensaje | El informe ya fue aprobado o completado. | Aparece cuando: Aprobar un informe que no está pendiente | Seguimiento |
| El nombre de la entidad ya existe | mensaje | Los nombres de entidad son únicos. | Aparece cuando: Crear o renombrar una entidad con un nombre existente | Usuarios y entidades |
| El número de alerta 'AT-…' ya existe | mensaje | La alerta ya fue registrada (manualmente, de forma automática o por el Agente IA). | Aparece cuando: Registrar un número de alerta que ya existe | Alertas tempranas |
| El número de alerta debe cumplir el formato AT-XXX-XXXX (ej: AT-001-2024) | mensaje | El servidor exige 4 caracteres al final; la pantalla no lo valida y su ejemplo usa 2 (diferencia D1). | Aparece cuando: Escribir el número con el año de 2 dígitos (como sugiere el ejemplo "Ej: AT-001-25") | Alertas tempranas |
| El número de alerta es requerido | mensaje | Faltan campos obligatorios del Paso 1. | Aparece cuando: Hacer clic en **Siguiente** con el Paso 1 incompleto | Alertas tempranas |
| El número de alerta fue ajustado a … debido a una creación concurrente. | mensaje | El sistema ajustó el número para evitar duplicados. | Aparece cuando: Dos personas registran alertas al mismo tiempo | Alertas tempranas |
| El número de informe es requerido | mensaje | Faltan datos obligatorios. | Aparece cuando: Cargar el informe sin datos | Informes de seguimiento |
| El número de radicado es requerido | mensaje | Faltan datos obligatorios. | Aparece cuando: Cargar el oficio sin datos | Oficios de consumación |
| El objetivo es requerido | mensaje | Faltan campos obligatorios. | Aparece cuando: Avanzar o guardar la actividad sin datos | Planes de acción |
| El oficio se creó pero hubo un error al subir el archivo PDF | mensaje | Falla al subir el archivo. | Aparece cuando: El PDF del oficio no se sube | Oficios de consumación |
| El PDF de la alerta no pudo ser subido. | mensaje | Solo el Super Administrador tiene el permiso de subir archivos (riesgo R1). | Aparece cuando: Adjuntar el PDF de la alerta como Administrador | Alertas tempranas |
| El plan de acción debe estar confirmado para reportar informes | mensaje | Los informes solo se habilitan con el plan confirmado. | Aparece cuando: Reportar un informe antes de que el plan esté confirmado | Planes de acción |
| El recurso solicitado no fue encontrado. El servidor puede estar reiniciándose. | mensaje | El registro fue eliminado o el servidor no responde (404). | Aparece cuando: Abrir un registro que ya no existe o fue eliminado | General |
| El reporte se creó pero hubo un error al subir el archivo | mensaje | Falla al subir el archivo después de guardar. | Aparece cuando: El PDF del reporte no se sube | Reportes |
| El reporte ya está aprobado | mensaje | Ya fue aprobado. | Aparece cuando: Aprobar un reporte ya aprobado | Reportes |
| El rol es requerido | mensaje | Faltan datos obligatorios según el rol. | Aparece cuando: Enviar la invitación con campos vacíos | Usuarios y entidades |
| El rol MONITOR no tiene permiso para aprobar en el módulo Planes de Acción | mensaje | Las aprobaciones solo se aceptan desde Seguimiento. | Aparece cuando: Intentar aprobar desde *Planes de acción* (por enlace) | Seguimiento |
| El servidor no está disponible. Por favor, intenta más tarde. | mensaje | Errores 502, 503 o 504 (servidor reiniciándose o en mantenimiento). | Aparece cuando: El servidor no está disponible | General |
| El tipo de consulta es requerido | mensaje | Faltan datos o falla la generación. | Aparece cuando: Generar una consulta sin datos | Reportes |
| El tipo de reporte es requerido | mensaje | Faltan datos según el tipo. | Aparece cuando: Cargar el reporte sin datos | Reportes |
| El último informe debe estar en estado 'pendiente_aprobacion' para aprobar la actividad | mensaje | Al aprobar una actividad con informes, el último debe estar pendiente y tener PDF. | Aparece cuando: Aprobar una actividad cuyo informe pendiente no tiene PDF | Seguimiento |
| Error al aprobar: Error al aprobar el reporte. Por favor, intenta de nuevo. | mensaje | La pantalla muestra **Aprobar informe** a todo Super Administrador y Líder de Macrozona, pero solo aprueba el aprobador designado. | Aparece cuando: Aprobar un reporte en el que no fue designado aprobador | Reportes |
| Error al cargar alertas: No se pudieron cargar las alertas. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Aparece cuando: El listado de alertas no carga | Alertas tempranas |
| Error al cargar datos | mensaje | Falla del servicio del tablero. | Aparece cuando: El tablero no carga | Inicio |
| Error al cargar el informe de recomendaciones | mensaje | El servidor solo entrega el tablero a Super Administrador, Administrador, Líder de Macrozona y Monitor. | Aparece cuando: Hacer clic en **Informe** (Informe de recomendaciones) desde Seguimiento | Seguimiento |
| Error al cargar informes: No se pudieron cargar los informes de seguimiento. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Aparece cuando: Los informes no cargan | Informes de seguimiento |
| Error al cargar las actividades | mensaje | Falla del servicio. | Aparece cuando: Las actividades no cargan o no se eliminan | Planes de acción |
| Error al cargar las recomendaciones. Por favor, intente nuevamente. | mensaje | Falla del servicio. | Aparece cuando: Las recomendaciones no cargan | Recomendaciones |
| Error al cargar oficios: No se pudieron cargar los oficios de consumación. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Aparece cuando: Los oficios no cargan o no se descargan | Oficios de consumación |
| Error al cargar reportes: No se pudieron cargar los reportes de ejecución. Por favor, intenta de nuevo. | mensaje | Falla del servicio. | Aparece cuando: Los reportes no cargan | Reportes |
| Error al cargar usuarios | mensaje | Falla del servicio. | Aparece cuando: El listado de usuarios o entidades no carga | Usuarios y entidades |
| Error al descargar: No se pudo generar el archivo CSV. Intente de nuevo. | mensaje | Falla al generar el archivo o al conectarse. | Aparece cuando: La descarga del CSV falla | General |
| Error al guardar el informe. Por favor, intente nuevamente. | mensaje | Falla del servicio o validación del servidor. | Aparece cuando: El informe no se guarda | Planes de acción |
| Error al Procesar PDF | mensaje | Falla del servicio del agente o PDF ilegible. | Aparece cuando: El agente no logra procesar el PDF | Agentes IA |
| Error al validar el plan de acción | mensaje | Falla del servicio. | Aparece cuando: La validación o la confirmación fallan | Seguimiento |
| Error interno del servidor. Por favor, intenta más tarde. | mensaje | Error 500 del servidor. | Aparece cuando: El servidor falla al procesar la solicitud | General |
| Esta alerta ya se encuentra cerrada. No es posible agregar municipios ni recomendaciones desde este informe. Solo puede editar los datos del informe en el paso anterior. | mensaje | La alerta está cerrada. | Aparece cuando: Modificar municipios o recomendaciones de una alerta cerrada | Informes de seguimiento |
| La actividad ya está aprobada | mensaje | La actividad no está pendiente. | Aparece cuando: Aprobar una actividad que ya está aprobada | Seguimiento |
| La alerta … ya está cerrada | mensaje | Solo se cierran alertas activas. | Aparece cuando: Cerrar una alerta que ya está cerrada | Alertas tempranas |
| La alerta asociada no puede ser modificada | mensaje | La alerta del informe no se cambia. | Aparece cuando: Intentar cambiar la alerta al editar el informe | Informes de seguimiento |
| La alerta AT-… ya ha sido subsumida por otra alerta | mensaje | Solo se subsumen alertas activas y no subsumidas. | Aparece cuando: Subsumir una alerta ya subsumida o cerrada | Alertas tempranas |
| La alerta no pudo ser publicada. | mensaje | La alerta ya estaba Activa o Cerrada. | Aparece cuando: Publicar una alerta que no está en Borrador | Alertas tempranas |
| La alerta solicitada no existe o ha sido eliminada. | mensaje | La alerta ya no existe. | Aparece cuando: Abrir las recomendaciones de una alerta eliminada | Recomendaciones |
| La entidad central es requerida | mensaje | Faltan datos obligatorios de la entidad. | Aparece cuando: Guardar una entidad sin datos | Usuarios y entidades |
| La Entidad Central no esta Activa | mensaje | Regla de jerarquía de entidades. | Aparece cuando: Crear una subdirección de una entidad inactiva o hacerla su propia central | Usuarios y entidades |
| La entidad principal con ID … no existe o no está activa | mensaje | La entidad no está activa. | Aparece cuando: Agregar una recomendación con una entidad inactiva | Informes de seguimiento |
| La fecha de fin debe ser posterior a la fecha de inicio | mensaje | Rango de fechas inválido. | Aparece cuando: Poner la fecha de fin antes de la de inicio | Planes de acción |
| La organización no existe o fue eliminada | mensaje | La entidad no está activa. | Aparece cuando: Elegir una entidad inactiva o eliminada | Recomendaciones |
| La organización no existe o no está activa | mensaje | La entidad elegida no está activa. | Aparece cuando: Asignar una entidad o subdirección inactiva | Usuarios y entidades |
| La solicitud no es válida. Verifica los datos e intenta de nuevo. | mensaje | Errores 400 o 422 de validación. | Aparece cuando: Enviar datos con un formato que el servidor no acepta | General |
| Las actividades ejecutadas son requeridas | mensaje | Faltan datos obligatorios del informe. | Aparece cuando: Guardar el informe sin datos obligatorios | Planes de acción |
| Las contraseñas ingresadas no son iguales. Por favor, verifica e ingrésalas nuevamente. | mensaje | Los dos campos no coinciden. | Aparece cuando: Escribir diferente la confirmación de la contraseña | Acceso a la plataforma |
| Las siguientes alertas no existen: … | mensaje | Inconsistencia entre las alertas seleccionadas y sus modificaciones. | Aparece cuando: Asociar alertas inexistentes o modificar alertas no asociadas | Oficios de consumación |
| No es posible editar el número de una alerta automática | mensaje | El número de las alertas automáticas no se cambia; el de las manuales solo lo cambia el Super Administrador. | Aparece cuando: Intentar cambiar el número de la alerta en la edición | Alertas tempranas |
| No es posible eliminar la entidad: Tiene usuarios asociados o subdirecciones o está relacionada con alertas tempranas. | mensaje | La entidad tiene usuarios, subdirecciones, alertas o recomendaciones. | Aparece cuando: Eliminar una entidad con información relacionada | Usuarios y entidades |
| No hay alertas con planes de acción | mensaje | No hay alertas con municipios en sus departamentos, o su usuario no tiene departamentos. | Aparece cuando: Seguimiento aparece vacío | Seguimiento |
| No hay alertas disponibles para subsunción | mensaje | No hay otras alertas activas no subsumidas. | Aparece cuando: Activar la subsunción y no ver alertas | Alertas tempranas |
| No hay archivo disponible | mensaje | El reporte no tiene PDF o la descarga falló. | Aparece cuando: Descargar un reporte sin archivo | Reportes |
| No hay datos de departamentos | mensaje | No hay alertas (no borradores) dentro de su alcance, o su usuario no tiene la entidad o los departamentos asignados. | Aparece cuando: El tablero aparece vacío o en cero | Inicio |
| No hay notificaciones | mensaje | No hay acciones registradas en las alertas de su alcance. | Aparece cuando: Abrir el panel sin actividad en su alcance | Notificaciones |
| No puede ser mayor que {N} | mensaje | Lo ejecutado no puede superar el "Número de actividades" del ciclo. | Aparece cuando: Reportar más actividades ejecutadas que las programadas | Planes de acción |
| No puedes desactivar tu propia cuenta | mensaje | Nadie puede cambiar su propio estado. | Aparece cuando: Intentar inactivar su propia cuenta | Usuarios y entidades |
| No puedes reutilizar ninguna de tus últimas 5 contraseñas | mensaje | El sistema guarda el historial de contraseñas. | Aparece cuando: Usar una contraseña anterior al restablecerla | Acceso a la plataforma |
| No se encontraron resultados: Tu búsqueda no coincide con ningún registro. Intenta de nuevo. | mensaje | No hay registros que cumplan la búsqueda dentro de su alcance. | Aparece cuando: Buscar o filtrar sin coincidencias | General |
| No se pudo conectar con el servidor. Por favor, verifica tu conexión e intenta de nuevo. | mensaje | Sin conexión o red bloqueada. | Aparece cuando: Se pierde la conexión a internet | General |
| No se puede cambiar el estado de un usuario con estado {estado}. El usuario debe aceptar su invitación primero. | mensaje | El usuario está en Invitación pendiente o expirada. | Aparece cuando: Intentar activar o inactivar a quien no ha aceptado la invitación | Usuarios y entidades |
| No se puede cambiar el estado de un usuario con rol SUPER_ADMINISTRADOR | mensaje | El estado de un Super Administrador no se cambia desde la plataforma. | Aparece cuando: Intentar inactivar a un Super Administrador | Usuarios y entidades |
| No se puede confirmar el plan de acción | mensaje | Hay actividades sin aprobar o recomendaciones sin actividades. | Aparece cuando: Intentar confirmar un plan incompleto | Seguimiento |
| No se puede desaprobar una actividad cuando el plan de acción ya fue confirmado | mensaje | Con el plan confirmado la aprobación no se puede descartar. | Aparece cuando: Descartar la aprobación con el plan confirmado | Seguimiento |
| No se puede editar la actividad porque el plan de acción ya fue confirmado | mensaje | Con el plan confirmado no se modifican actividades. | Aparece cuando: Editar o eliminar una actividad con el plan confirmado | Planes de acción |
| No se puede editar la alerta AT-… porque ha sido subsumida por otra alerta | mensaje | La alerta fue reemplazada por otra. | Aparece cuando: Editar una alerta subsumida | Alertas tempranas |
| No se puede editar la alerta porque su plan de acción ya fue confirmado | mensaje | Con el plan confirmado la alerta queda bloqueada. | Aparece cuando: Editar una alerta con el plan de acción confirmado | Alertas tempranas |
| No se puede editar porque el informe ya está aprobado. Podrá reportar un nuevo informe cuando pase la fecha del próximo informe. | mensaje | La aprobación del informe es irreversible. | Aparece cuando: Editar un informe ya aprobado | Planes de acción |
| No se puede editar porque la actividad ya está aprobada | mensaje | Las actividades aprobadas quedan bloqueadas. | Aparece cuando: Editar o eliminar una actividad aprobada | Planes de acción |
| No se puede eliminar: No se puede eliminar un reporte que ya ha sido aprobado | mensaje | Los reportes aprobados no se eliminan. | Aparece cuando: Eliminar un reporte aprobado | Reportes |
| No se puede eliminar la subdirección. Tiene usuarios asignados y/o está asociada a alertas temporanas. | mensaje | La subdirección está en uso. | Aparece cuando: Quitar una subdirección con usuarios o alertas | Usuarios y entidades |
| No se puede eliminar un informe asociado a una alerta cerrada | mensaje | El informe es soporte del cierre. | Aparece cuando: Eliminar un informe de una alerta cerrada | Informes de seguimiento |
| No se pueden agregar actividades a una alerta cerrada | mensaje | La alerta está cerrada. | Aparece cuando: Agregar actividades a una alerta cerrada | Planes de acción |
| No se pueden agregar recomendaciones a una alerta cerrada | mensaje | La alerta está cerrada. | Aparece cuando: Agregar, editar o eliminar recomendaciones de una alerta cerrada | Recomendaciones |
| No se pueden crear recomendaciones porque el plan de acción ya fue confirmado | mensaje | Con el plan confirmado las recomendaciones quedan bloqueadas. | Aparece cuando: Agregar, editar o eliminar recomendaciones con el plan confirmado | Recomendaciones |
| No tienes permisos para agregar recomendaciones | mensaje | Solo el Super Administrador y el Administrador las registran. | Aparece cuando: Buscar los botones de agregar, editar o eliminar recomendaciones | Recomendaciones |
| No tienes permisos para cargar informes | mensaje | Solo el Super Administrador y el Administrador cargan y editan; solo el Super Administrador elimina en pantalla. | Aparece cuando: Buscar los botones de cargar, editar o eliminar informes | Informes de seguimiento |
| No tienes permisos para cargar oficios | mensaje | Solo el Super Administrador gestiona oficios. | Aparece cuando: Buscar los botones de cargar, editar o eliminar oficios | Oficios de consumación |
| No tienes permisos para confirmar planes de acción | mensaje | Su rol solo consulta en Seguimiento. | Aparece cuando: Buscar los botones de aprobar o confirmar | Seguimiento |
| No tienes permisos para eliminar reportes | mensaje | En la pantalla solo el Super Administrador elimina reportes. | Aparece cuando: Buscar la opción de eliminar un reporte | Reportes |
| No tienes permisos para realizar esta acción. | mensaje | El servidor rechaza la operación para el rol (403). | Aparece cuando: Intentar una acción que el rol no tiene (por ejemplo, desde un enlace o un botón visible por error) | General |
| No tienes permisos para reportar alertas | mensaje | Su rol solo consulta alertas. | Aparece cuando: Buscar los botones de registrar, editar, eliminar o cerrar alertas | Alertas tempranas |
| Nota: El archivo PDF no pudo ser subido, pero el cierre se completó exitosamente. | mensaje | Falló la carga del archivo después de cerrar. | Aparece cuando: El PDF del cierre no se sube | Alertas tempranas |
| Opción no disponible. Para deshabilitar las subdirecciones, primero debes eliminar todas sus subdirecciones. | mensaje | La entidad tiene subdirecciones creadas. | Aparece cuando: Desactivar las subdirecciones de una entidad que ya tiene | Usuarios y entidades |
| Página no encontrada: Lo sentimos, la página que buscas no existe o ha sido movida. | mensaje | La ruta no existe. | Aparece cuando: Escribir una dirección que no existe | General |
| Para reportes de tipo Alerta, debe especificar una alerta | mensaje | Datos inconsistentes con el tipo. | Aparece cuando: El servidor rechaza el reporte | Reportes |
| Plan de acción ya confirmado | mensaje | El plan ya fue confirmado. | Aparece cuando: Confirmar un plan ya confirmado | Seguimiento |
| Plazo de implementación inválido: … | mensaje | Solo se aceptan 1 a 3 meses, 3 a 6 meses, 6 a 9 meses o Permanente. | Aparece cuando: El servidor recibe un plazo fuera de la lista | Planes de acción |
| Recomendaciones creadas: Se han creado {N} recomendaciones correctamente. | mensaje | Por cada Entidad Principal se crea una recomendación distinta con la misma descripción (hallazgo H2). | Aparece cuando: Agregar varias entidades principales en una sola recomendación | Recomendaciones |
| Revisión existente: Ya registraste una revisión para esta actividad el {fecha}. ¿Estás seguro de que deseas crear otro registro? | mensaje | Ya existe una revisión suya. | Aparece cuando: Marcar como revisada una actividad que ya revisó | Seguimiento |
| Sesión cerrada por inactividad: Tu sesión fue cerrada automáticamente por inactividad. Por favor, inicia sesión nuevamente. | mensaje | Cierre automático por inactividad de 60 minutos. | Aparece cuando: Dejar la plataforma abierta sin usarla 60 minutos | Acceso a la plataforma |
| Sesión expirada: Tu sesión ha expirado. Por favor, inicia sesión nuevamente. | mensaje | El token de la sesión venció (720 minutos) o no es válido. | Aparece cuando: Trabajar con una sesión vencida | Acceso a la plataforma |
| Solo las entidades territoriales pueden agregar actividades | mensaje | Su rol no formula actividades en la pantalla. | Aparece cuando: Buscar el botón **Agregar actividad** | Planes de acción |
| Solo se permiten archivos PDF | mensaje | El agente solo procesa PDF. | Aparece cuando: Seleccionar un archivo que no es PDF | Agentes IA |
| Solo se pueden reenviar invitaciones a usuarios con estado Pendiente o Expirada | mensaje | El usuario ya activó su cuenta. | Aparece cuando: Reenviar o eliminar la invitación de un usuario ya activo | Usuarios y entidades |
| Solo un Super Administrador puede crear otros Super Administradores | mensaje | Restricción del rol Administrador. | Aparece cuando: Intentar crear o editar un Super Administrador | Usuarios y entidades |
| Tipo de archivo no permitido. Solo se aceptan: .pdf | mensaje | Los campos de archivo solo aceptan PDF. | Aparece cuando: Seleccionar un archivo que no es PDF | General |
| Token inválido o expirado | mensaje | El enlace de restablecimiento vence en 1 hora. | Aparece cuando: Abrir el enlace de restablecimiento después de 1 hora | Acceso a la plataforma |
| Tu organización está suspendida. Por favor contacta al administrador. | mensaje | La entidad guardada en su usuario no está en estado Activa. | Aparece cuando: Ingresar cuando la entidad asignada no está activa | Acceso a la plataforma |
| Uno de los archivos marcados para eliminar no pudo ser eliminado. | mensaje | Falla al eliminar o subir el archivo. | Aparece cuando: Reemplazar los archivos de la alerta en la edición | Alertas tempranas |
| Ya existe un informe con el número '…'. Por favor use un número diferente. | mensaje | El número de informe es único. | Aparece cuando: Usar un número de informe ya registrado | Informes de seguimiento |
| Agentes | menú o pestaña | Agente IA para crear alertas desde PDF ("Agentes IA"). | Abre la vista correspondiente. | Agentes IA |
| Alertas / Recomendaciones / Actividades | menú o pestaña | Pestañas de Planes de acción y Seguimiento. | Abre la vista correspondiente. | Planes de acción, Seguimiento |
| Alertas tempranas | menú o pestaña | Registro y consulta de las alertas. | Abre la vista correspondiente. | Alertas tempranas |
| Centrales / Subdirecciones | menú o pestaña | Vistas de la pestaña Entidades. | Abre la vista correspondiente. | Usuarios y entidades |
| Cerrar sesión | menú o pestaña | Termina la sesión. | Abre la vista correspondiente. | Acceso a la plataforma |
| Entidad / Eje tematico | menú o pestaña | Vistas de la tabla Cumplimiento del Informe de recomendaciones. | Abre la vista correspondiente. | Informe de recomendaciones |
| Historial de actividades | menú o pestaña | Línea de tiempo de acciones sobre una alerta. | Abre la vista correspondiente. | Alertas tempranas |
| Información / Actividades / Historial | menú o pestaña | Pestañas del detalle de una recomendación en el plan. | Abre la vista correspondiente. | Planes de acción, Seguimiento |
| Informes de seguimiento | menú o pestaña | Informes de seguimiento de la Defensoría. | Abre la vista correspondiente. | Informes de seguimiento |
| Inicio | menú o pestaña | Tablero de indicadores, mapa y alertas recientes. | Abre la vista correspondiente. | Inicio |
| Notificaciones | menú o pestaña | Panel con el historial de actividad de su alcance. | Abre la vista correspondiente. | Notificaciones |
| Oficios de consumación | menú o pestaña | Oficios de consumación del riesgo. | Abre la vista correspondiente. | Oficios de consumación |
| Panel de consultas | menú o pestaña | Ventana para generar informes ejecutivos en Word. | Abre la vista correspondiente. | Reportes |
| Planes de acción | menú o pestaña | Formulación de actividades e informes de ejecución. | Abre la vista correspondiente. | Planes de acción |
| Reportes | menú o pestaña | Reportes de ejecución y Panel de consultas. | Abre la vista correspondiente. | Reportes |
| Seguimiento | menú o pestaña | Revisión y aprobación de actividades, confirmación de planes y aprobación de informes ("Seguimiento de Planes"). | Abre la vista correspondiente. | Seguimiento |
| Todas / Inminencia / Estructurales | menú o pestaña | Pestañas del listado de alertas por tipo. | Abre la vista correspondiente. | Alertas tempranas |
| Todos / Alerta / Entidad / Regional | menú o pestaña | Pestañas de Reportes (Regional = departamental y municipal). | Abre la vista correspondiente. | Reportes |
| Todos / Entidades Territoriales / Administradores / Monitores / Invitaciones | menú o pestaña | Vistas de la pestaña Usuarios. | Abre la vista correspondiente. | Usuarios y entidades |
| Usuarios y entidades | menú o pestaña | Administración de usuarios, invitaciones, entidades y subdirecciones. | Abre la vista correspondiente. | Usuarios y entidades |
| Ver Perfil | menú o pestaña | Acceso a Mi perfil. | Abre la vista correspondiente. | Acceso a la plataforma |
| Administrador | rol | Acceso nacional para visualizar alertas y gestionar planes de acción. No puede eliminar alertas ni aprobar actividades. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Consulta Departamentos | rol | Solo lectura filtrado por departamentos asignados. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Consulta Entidad | rol | Solo lectura filtrado por su entidad asignada. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Consulta Global | rol | Solo lectura a nivel nacional (sin modificar datos). (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Entidad Territorial | rol | Gestiona actividades e informes de ejecución de su entidad/subdirección. No puede aprobar. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Líder de Macrozona | rol | Supervisa alertas en departamentos asignados. Acceso total a reportes de ejecución. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Monitor | rol | Acceso departamental. Puede aprobar actividades e informes en Seguimiento. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| Super Administrador | rol | Acceso total a la plataforma sin restricciones. (texto de ayuda de la plataforma) | Define los menús, los botones y el alcance de datos del usuario. | Usuarios y entidades, Acceso a la plataforma |
| AT | sigla | Prefijo del número de alerta temprana (AT-XXX-XXXX). | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |
| CAT | sigla | Categoría municipal según la Contaduría General de la Nación (ESP, 1 a 6, N/A). | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |
| CIPRAT | sigla | Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas. | Aparece en pantallas y documentos de la ruta. | Acceso a la plataforma, Inicio |
| CSV | sigla | Archivo de texto separado por comas que se abre en Excel. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas, Recomendaciones, Planes de acción, Seguimiento |
| D.I.H. | sigla | Derecho Internacional Humanitario (paso 4 de la alerta). | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |
| DANE / Cod DANE | sigla | Código del municipio (5 dígitos) del DANE. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas, Informes de seguimiento, Oficios de consumación |
| PDET | sigla | Programa de Desarrollo con Enfoque Territorial. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |
| PDF | sigla | Único formato de archivo aceptado para los soportes. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas, Planes de acción, Reportes, Informes de seguimiento, Oficios de consumación, Agentes IA |
| PNIS | sigla | Programa Nacional Integral de Sustitución de Cultivos de Uso Ilícito. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |
| RC | sigla | Prefijo del código de la recomendación. | Aparece en pantallas y documentos de la ruta. | Recomendaciones, Planes de acción, Seguimiento |
| SI-CIPRAT | sigla | Sistema de Información de la Secretaría Técnica CIPRAT. | Aparece en pantallas y documentos de la ruta. | Acceso a la plataforma, Inicio |
| Zona Fut. | sigla | Zona del Formulario Único Territorial. | Aparece en pantallas y documentos de la ruta. | Alertas tempranas |

## 10. Caso práctico AT-013-25 [DATO REAL AT-013-25]

Valores de la línea base (`data/`): alerta **AT-013-25** (en el sistema AT-013-2025, porque el número exige año de 4 dígitos), fecha de la alerta y de notificación 07/10/2025, tipo Estructural, etiqueta Regional (los scripts del repositorio la cargan como Nacional), lugar de advertencia "Todos los municipios" (1.122 municipios en los scripts), 41 recomendaciones (RC-001-2025-013 a RC-041-2025-013) y un plan de mitigación **parcial**: 20 actividades de RC-003, RC-004, RC-021, RC-022 y RC-023. Lo demás del plan y los informes de ejecución quedan como Mock (pendiente: plan de mitigación no disponible). Su uso en sesiones requiere autorización del Ministerio; la alternativa Mock es la alerta ficticia AT-901-2026.
