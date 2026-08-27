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
| **Alcance** | Nacional — acceso total al sistema sin restricción geográfica |
| **Objetivo principal** | Administrar técnica y operativamente la totalidad de la plataforma SI-CIPRAT |
| **Quién ocupa este rol** | Personal TI o enlace técnico del Ministerio del Interior |

---

## Objetivo de Capacitación

Al finalizar la formación, el Super Administrador podrá gestionar de forma autónoma todos los módulos de la plataforma: configurar usuarios y entidades, administrar alertas tempranas y recomendaciones, gestionar planes de acción en todas sus fases, aprobar informes, ejecutar reportes, subir oficios de consumación y supervisar la interoperabilidad con SISAT vía X-Road.

---

## Alcance en la Plataforma

### Módulos con acceso completo (visualización + gestión)

| Módulo | Acciones disponibles |
|--------|----------------------|
| Usuarios y Organizaciones | Invitar, editar, activar/desactivar usuarios; crear, editar y eliminar entidades centrales y subdirecciones |
| Gestión de Alertas Tempranas | Crear, editar, cerrar, eliminar alertas; gestionar recomendaciones (crear, editar, eliminar); descargar listado; ver historial |
| Planes de Acción | Agregar, editar y eliminar actividades; subir informes; aprobar planes; registrar observaciones |
| Seguimiento y Monitoreo | Aprobar actividades e informes de seguimiento |
| Informes de Seguimiento | Visualizar y subir informes de seguimiento |
| Reportes | Realizar consultas, cargar y aprobar informes |
| Visualización Geográfica | Mapa interactivo y mapas estáticos (cobertura nacional) |
| Notificaciones | Todas las notificaciones del sistema |
| Interoperabilidad X-ROAD | Supervisión de endpoints y datos recibidos desde SISAT |
| Oficios de Consumación | Visualizar y subir oficios de consumación |
| Inicio de Plataforma | Vista global nacional |

### Capacidades exclusivas del Super Administrador

- Eliminar alertas y recomendaciones
- Cerrar alertas y generar oficios de consumación
- Editar o escalar usuarios al rol Super Administrador
- Gestionar otros Super Administradores
- Agregar, editar y eliminar actividades en planes de acción (capacidad compartida solo con Entidad Territorial)
- Aprobar informes de reportes (capacidad compartida solo con Líder de Macrozona)

---

## Segmentación de Visualización

- **Dashboard de inicio**: Vista global nacional — todas las alertas, todos los departamentos, sin filtro de restricción.
- **Alertas**: Sin filtro — ve todas las alertas del sistema independientemente del departamento o entidad.
- **Planes de acción**: Visualización filtrada por alerta/entidad, sin restricción geográfica.
- **Reportes**: Acceso total sin segmentación territorial.

---

## Ruta de Aprendizaje

### Módulo 0 — Contexto de la Plataforma SI-CIPRAT

**Objetivo:** Que el Super Administrador entienda el marco institucional en el que opera y el rol que cumple SI-CIPRAT antes de comenzar a gestionar la plataforma.

SI-CIPRAT es el **Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT)**, una plataforma desarrollada por el **Ministerio del Interior de Colombia** para centralizar y articular la gestión de las alertas tempranas emitidas por la Defensoría del Pueblo.

La **Comisión Intersectorial CIPRAT** reúne a entidades del nivel central y territorial con el mandato de responder de forma coordinada y oportuna ante los escenarios de riesgo identificados en el territorio nacional. Antes de SI-CIPRAT, esta coordinación dependía de procesos manuales, comunicaciones fragmentadas y ausencia de una fuente de información unificada, lo que generaba reprocesos, demoras y dificultades para tomar decisiones basadas en datos confiables y en tiempo real.

SI-CIPRAT resuelve estos retos al ofrecer un espacio digital común donde la Defensoría del Pueblo emite alertas tempranas, el Ministerio del Interior las gestiona y emite recomendaciones, y las entidades territoriales responden con planes de acción concretos que son monitoreados, aprobados y seguidos a lo largo de todo su ciclo de vida. Cada actor del ecosistema —Defensoría, Ministerio, entidades centrales, subdirecciones y monitores— tiene un rol definido dentro de la plataforma, con acceso segmentado según sus responsabilidades.

El Super Administrador es el actor con mayor nivel de acceso en el sistema. Su responsabilidad no es solo operar la plataforma: es garantizar que la estructura de usuarios, entidades y alertas esté correctamente configurada para que todos los demás roles puedan cumplir su función.

---

### Módulo 1 — Acceso a la Plataforma

**Objetivo:** Que el Super Administrador pueda ingresar de forma autónoma a la plataforma, conocer el flujo completo de autenticación y saber cómo actuar ante cualquier problema de acceso.

#### Flujo de acceso (happy path)

**Paso 1 — Recibir invitación y asignar contraseña**

El acceso del Super Administrador es gestionado directamente por otro Super Administrador existente en el sistema. La plataforma envía automáticamente un **correo de invitación** a la dirección registrada con un enlace de activación. Al hacer clic en el enlace, el usuario asigna su contraseña con los siguientes requisitos:

- Mínimo 8 caracteres
- Al menos un carácter especial (ej. `!`, `@`, `#`, `$`, `%`)

> **Nota:** A diferencia de todos los demás roles, el rol Super Administrador **no puede ser asignado a través del formulario de invitación estándar**. Solo un Super Administrador puede elevar a otro usuario a este rol mediante la edición directa del perfil del usuario en el módulo de gestión de usuarios.

**Paso 2 — Ingresar a la plataforma**

Ir a la URL de acceso e ingresar el correo electrónico y la contraseña asignada:

> [https://polite-wave-005a5910f.3.azurestaticapps.net/signin](https://polite-wave-005a5910f.3.azurestaticapps.net/signin)

**Paso 3 — Verificar identidad con código de 4 dígitos**

Tras ingresar las credenciales, la plataforma envía automáticamente un **código de verificación de 4 dígitos** al correo registrado. Ingresar el código en la pantalla de verificación y hacer clic en **Confirmar**.

> **Sin este código no es posible acceder a la plataforma.** Es una medida de seguridad obligatoria del sistema.

El código tiene una vigencia de **1 hora**. Una vez confirmado, la sesión queda activa con un token JWT de **24 horas de vigencia**.

---

#### Variaciones del flujo

**Si no llegó el correo de invitación (Paso 1)**

Revisar la carpeta de spam. Si tampoco está allí, ingresar a la URL de la plataforma, hacer clic en **"¿Olvidaste tu contraseña?"**, ingresar el correo registrado y seguir el enlace de restablecimiento que llegará al correo. La nueva contraseña debe cumplir los mismos requisitos.

**Si no llega el código de verificación (Paso 3)**

Revisar la carpeta de spam. Si no aparece, hacer clic en **"Reenviar"** dentro de la pantalla de verificación para generar un nuevo código. El nuevo código también tiene vigencia de 1 hora.

**Si no logra acceder por ninguna vía**

Contactar al equipo de soporte indicando nombre completo, correo registrado y descripción del problema:

> **Soporte SI-CIPRAT:** [siciprat@mininterior.gov.co](mailto:siciprat@mininterior.gov.co)

---

#### Cierre automático de sesión

La sesión se cierra automáticamente tras **1 hora de inactividad**. Al reanudar será necesario repetir el flujo completo de acceso (correo + contraseña + código de verificación).

> Guarde su trabajo con frecuencia si trabaja con formularios o documentos dentro de la plataforma.

---

#### Perfil y configuración inicial

Al ingresar por primera vez, el Super Administrador debe revisar su perfil desde el menú de usuario. El perfil muestra:

- Nombre completo y correo electrónico
- Rol asignado (Super Administrador)

> A diferencia de otros roles, el Super Administrador no tiene departamentos asignados ni entidad central asociada, ya que su acceso es de cobertura nacional.

---

### Módulo 2 — Inicio de la Plataforma

**Objetivo:** Que el Super Administrador pueda interpretar el panel de inicio como una vista ejecutiva del estado nacional de las alertas tempranas, identificando de forma rápida la situación global antes de profundizar en módulos específicos.

Al ingresar al sistema, el Super Administrador llega a la pantalla de **Inicio**, que presenta un resumen ejecutivo de la situación de alertas tempranas a nivel nacional.

> **Toda la información del Inicio corresponde a la totalidad del territorio nacional.** El Super Administrador ve todas las alertas del sistema sin ningún filtro geográfico.

#### Indicadores de alertas nacionales

El Inicio permite identificar, para el conjunto nacional de alertas:

- **Total de alertas** registradas en el sistema
- **Alertas activas** — en seguimiento o con planes de acción en curso
- **Alertas cerradas** — con proceso finalizado
- **Alertas estructurales** — asociadas a condiciones de riesgo de mediano y largo plazo
- **Alertas de inminencia** — asociadas a situaciones de riesgo inmediato que requieren respuesta urgente

#### Porcentaje de avance en ejecución

El Inicio también muestra el **porcentaje de avance en la ejecución** de las alertas a nivel nacional. Este indicador refleja el progreso agregado de los planes de acción asociados a cada alerta en todo el territorio.

#### Vista de mapa

El Inicio incluye una **vista de mapa** que permite visualizar geográficamente la distribución de alertas por departamento en todo el país. Desde el mapa es posible identificar de forma rápida en qué territorios hay mayor concentración de alertas activas.

#### Últimas alertas emitidas

El Inicio presenta también un listado de las **últimas alertas emitidas** a nivel nacional, permitiendo al Super Administrador estar al tanto de las novedades más recientes sin necesidad de navegar al módulo de alertas.

---

### Módulo 3 — Gestión de Usuarios y Entidades

**Objetivo:** Que el Super Administrador pueda gestionar de forma autónoma la estructura de acceso de la plataforma: invitar usuarios de cualquier rol, editar sus datos y permisos, controlar su estado, y crear y mantener la jerarquía de entidades territoriales centrales y subdirecciones.

Este módulo es el más estratégico para el Super Administrador, ya que una configuración incorrecta de usuarios o entidades afecta directamente la capacidad de todos los demás roles para operar la plataforma.

---

#### Actividad 1 — Gestión de usuarios

El módulo de usuarios presenta dos pestañas: **Usuarios** e **Invitaciones**.

**Vista de la pestaña Usuarios**

La tabla de usuarios muestra las siguientes columnas:

| Columna | Descripción |
|---------|-------------|
| **Usuario** | Avatar con iniciales, nombre completo y entidad |
| **Rol** | Badge con color según rol asignado |
| **Nivel de acceso** | Central o Subdirección |
| **Categoría de organización** | Clasificación de la entidad |
| **Fecha de activación** | Fecha en que el usuario activó su cuenta |
| **Estado** | Toggle activo (verde) / inactivo (gris) |
| **Acciones** | Ver detalle, editar |

El Super Administrador puede **buscar usuarios por nombre o correo electrónico** y **filtrar por rol** (Todos, Super Administrador, Administrador, Líder de Macrozona, Monitor, Consulta Global, Consulta Entidad, Entidad Territorial Central, Entidad Territorial Subdirección).

**Invitar un nuevo usuario**

Para agregar un usuario a la plataforma, el Super Administrador hace clic en **"Enviar invitación"**. El formulario solicita:

- **Rol** — selector con todos los roles disponibles (excepto Super Administrador; este rol solo se asigna mediante edición del perfil)
- **Entidad Central** — requerido para roles de Entidad Territorial
- **Subdirección** — requerido para rol Entidad Territorial Subdirección
- **Área** — campo de texto opcional
- **Nombres y Apellidos** — requeridos
- **Cargo** — requerido para roles Entidad Territorial y Monitor
- **Correo electrónico** — requerido, validación de formato y unicidad
- **Departamentos** — selector múltiple, solo para rol Monitor

Al enviar, el sistema crea al usuario con estado `INVITATION_PENDING` y genera un token de invitación con vigencia de **7 días**. El usuario recibirá un correo con el enlace para activar su cuenta y establecer su contraseña.

> ⚠️ **No es posible invitar usuarios con rol Super Administrador desde el formulario de invitación.** Para asignar este rol, primero invite al usuario con cualquier otro rol y luego edite su perfil para escalarlo a Super Administrador.

**Editar un usuario existente**

Desde el ícono de edición en cada fila o desde el modal de detalle del usuario, el Super Administrador puede modificar:

- Nombres y apellidos
- Correo electrónico
- Rol (incluida la escalación a Super Administrador)
- Entidad central y subdirección
- Cargo y área
- Departamentos (para rol Monitor)

> **Restricción exclusiva del Super Administrador:** Solo el Super Administrador puede editar usuarios con rol Super Administrador o escalar a este rol a otros usuarios. El Administrador no tiene esta capacidad.

**Activar o desactivar un usuario**

El toggle de estado en cada fila permite activar o desactivar el acceso de un usuario a la plataforma de forma inmediata. Un usuario desactivado no puede iniciar sesión.

Restricciones del sistema:
- No es posible desactivar la propia cuenta
- No es posible cambiar el estado de un Super Administrador desde un rol inferior
- No es posible cambiar el estado de usuarios con invitación pendiente o expirada

**Reenviar una invitación**

Si el token de una invitación venció (7 días) o el usuario no recibió el correo, el Super Administrador puede reenviar la invitación desde la pestaña **Invitaciones**. El sistema genera un nuevo token con vigencia de 7 días y notifica al usuario.

**Eliminar una invitación pendiente**

Desde la pestaña **Invitaciones**, el Super Administrador puede eliminar invitaciones que no fueron aceptadas y que ya no son válidas. Esta acción cambia el estado del usuario a `INACTIVE` y lo remueve de la lista de invitaciones.

---

#### Actividad 2 — Gestión de entidades

La pestaña **Entidades** del módulo de usuarios y organizaciones presenta dos vistas: **Centrales** y **Subdirecciones**.

**Vista de Entidades Centrales**

| Columna | Descripción |
|---------|-------------|
| **Entidades** | Nombre de la entidad central |
| **Subdirecciones** | Cantidad de subdirecciones asociadas |
| **Usuarios** | Total de usuarios incluyendo subdirecciones |
| **Categoría** | Badges con las categorías asignadas |
| **Fecha de creación** | Fecha de registro en el sistema |
| **Acciones** | Ver detalle, editar, eliminar |

**Crear una nueva entidad central**

Al hacer clic en **"Agregar Entidad"**, el formulario solicita:

- **Nombre de la Entidad Central** — requerido, debe ser único en el sistema
- **Categoría** — selector múltiple de categorías (requerido al menos una)
- **Subdirecciones** — toggle para habilitar; si está activo, permite agregar múltiples subdirecciones con su nombre

> ⚠️ **La eliminación de una entidad central solo es posible si no tiene usuarios asociados ni subdirecciones.** Si tiene alguno de estos, el sistema mostrará el mensaje "Tiene usuarios asociados o subdirecciones" y bloqueará la eliminación.

**Ver detalle de una entidad**

El modal de detalle muestra el nombre, categorías, cantidad de subdirecciones y la lista completa de subdirecciones con sus usuarios asociados. Desde este modal también se puede acceder a la edición.

**Editar una entidad existente**

Permite modificar el nombre, las categorías y las subdirecciones (agregar nuevas o editar nombres de las existentes). El sistema valida que el nombre no esté duplicado en otra entidad.

**Buscar y filtrar entidades**

El campo de búsqueda filtra entidades y subdirecciones por nombre en tiempo real. La búsqueda aplica simultáneamente a las vistas de Centrales y Subdirecciones.

---

### Módulo 4 — Gestión de Alertas Tempranas

**Objetivo:** Que el Super Administrador pueda registrar, editar, consultar y gestionar el ciclo de vida completo de las alertas tempranas en el sistema, incluyendo la creación de recomendaciones, el cierre de alertas y la generación de oficios de consumación.

El Super Administrador tiene **acceso completo de gestión** sobre todas las alertas del sistema. A diferencia del Monitor, que solo puede consultar, el Super Administrador puede crear, editar, cerrar y eliminar alertas, así como gestionar las recomendaciones asociadas.

---

#### Indicadores generales del módulo

Al ingresar al módulo, se presentan indicadores agregados del total nacional:

- **Total de alertas** del sistema
- **Alertas de inminencia** — riesgo inmediato
- **Alertas estructurales** — riesgo de mediano y largo plazo

#### Vista de lista — detalle de alertas

| Columna | Descripción |
|---------|-------------|
| **Alerta** | Identificador o nombre de la alerta |
| **Tipo** | Inminencia o Estructural |
| **Tema** | Temática principal de la alerta |
| **Estado** | Estado actual (activa, cerrada, etc.) |
| **Porcentaje de ejecución** | Avance del plan de acción asociado |
| **Cantidad de Recomendaciones** | Número de recomendaciones emitidas |
| **Creación** | Fecha de registro de la alerta en el sistema |

#### Búsqueda y filtros

El Super Administrador puede localizar una alerta mediante búsqueda por nombre y los siguientes filtros combinables:

- **Tipo** — Inminencia / Estructural
- **Estado** — Activa / Cerrada / otros estados disponibles
- **Etiqueta** — clasificación temática
- **Economías Ilegales** — filtro por tipo de economía ilegal asociada
- **Grupos Armados** — filtro por grupo armado relacionado

---

#### Actividad 1 — Registrar una nueva alerta temprana

Para crear una nueva alerta, el Super Administrador hace clic en **"Reportar entidad"** o en el botón de creación del módulo. El formulario incluye los campos requeridos para registrar la alerta: tipo, tema, ubicación geográfica, descripción del conflicto, conductas vulneratorias e infracciones al D.I.H., población afectada y alertas subsumidas si aplica.

Una vez registrada, la alerta queda disponible en el sistema para que los demás roles puedan consultarla y asociarle planes de acción.

---

#### Actividad 2 — Consultar el detalle de una alerta

Desde el menú de tres puntos ( **⋯** ) o el ícono de lupa en cada fila de la lista, el Super Administrador accede al **detalle completo** de la alerta, organizado en las siguientes secciones:

- **Información general** — tipo, estado, fechas, temática
- **Lugar de advertencia** — ubicación geográfica (departamento, municipio)
- **Conflicto** — descripción del contexto de conflicto asociado
- **Conductas vulneratorias e infracciones al D.I.H.**
- **Población afectada**
- **Alertas subsumidas** — alertas anteriores integradas en esta alerta
- **PDF oficial** — pronunciamiento formal de la Defensoría del Pueblo

---

#### Actividad 3 — Gestión de recomendaciones

Desde el detalle de una alerta, el Super Administrador puede gestionar las **recomendaciones** emitidas hacia las entidades responsables.

**Crear una recomendación**

Cada recomendación incluye la descripción de la acción esperada y la **entidad principal responsable** de ejecutarla. Las recomendaciones son el vínculo entre la alerta y los planes de acción que las entidades territoriales deberán cargar.

**Editar una recomendación existente**

Permite actualizar el texto de la recomendación o cambiar la entidad principal responsable.

**Eliminar una recomendación**

> ⚠️ **Esta acción es exclusiva del Super Administrador.** La eliminación de una recomendación es irreversible y afecta directamente la estructura del plan de acción asociado. Solo debe ejecutarse si la recomendación fue registrada por error o ya no es pertinente.

---

#### Actividad 4 — Editar y eliminar alertas

**Editar una alerta:** El Super Administrador puede modificar los datos de una alerta existente para corregir información o actualizar el estado del escenario de riesgo.

**Eliminar una alerta:**

> ⚠️ **La eliminación de alertas es una acción exclusiva e irreversible del Super Administrador.** Solo debe ejecutarse cuando la alerta fue registrada por error. Una alerta con planes de acción o informes asociados no debe eliminarse; en ese caso corresponde cerrarla mediante el flujo de consumación.

---

#### Actividad 5 — Cerrar una alerta y generar oficio de consumación

Cuando una alerta ha concluido su ciclo de vida, el Super Administrador procede con su **cierre formal**. Este proceso implica:

1. Seleccionar la opción **Cerrar alerta** desde el detalle de la alerta
2. El sistema genera o permite subir el **oficio de consumación** — documento oficial que formaliza el cierre y queda registrado en el módulo de Oficios de Consumación
3. La alerta queda en estado **Cerrada** y deja de ser visible como activa en los dashboards de los demás roles

> El oficio de consumación es el documento que certifica que la alerta fue atendida y que el proceso de seguimiento ha concluido. Su registro en el sistema es obligatorio para el cierre formal.

---

#### Descarga del listado de alertas

Desde este módulo el Super Administrador puede **descargar el listado completo de alertas** del sistema en formato Excel o PDF, útil para consolidar información de seguimiento o generar reportes externos.

---

#### Historial de actividades

Cada alerta cuenta con un **historial de actividades** que registra todas las acciones realizadas sobre ella: creaciones, ediciones, cambios de estado, recomendaciones gestionadas y aprobaciones. El Super Administrador puede consultar este historial para trazabilidad y auditoría.

---

### Módulo 5 — Planes de Acción

**Objetivo:** Que el Super Administrador comprenda el flujo completo de los planes de acción, pueda gestionarlos en todas sus fases —desde la carga de actividades hasta la aprobación, confirmación y seguimiento de informes de ejecución— y sepa cuándo intervenir directamente en el plan.

El Super Administrador tiene acceso completo al módulo de planes de acción, incluyendo capacidades que solo comparte parcialmente con Monitores y Entidades Territoriales.

---

#### Niveles de visualización

Al igual que el Monitor, el Super Administrador accede a tres niveles de profundidad en el módulo:

**Nivel 1 — Vista de alertas**

Lista todas las alertas del sistema con información consolidada del plan de acción de cada una.

| Columna | Descripción |
|---------|-------------|
| **Alerta** | Nombre o identificador de la alerta |
| **Programado** | Total de actividades programadas |
| **Ejecutado** | Total de actividades ejecutadas y reportadas |
| **% Cumplimiento** | Porcentaje de lo programado que fue ejecutado |
| **Estado del plan** | Estado actual del plan de acción |

**Nivel 2 — Vista de recomendaciones**

Despliega todas las recomendaciones de todas las alertas. Permite identificar, por recomendación, qué entidades tienen compromisos y cuál es el avance de cada una.

**Nivel 3 — Vista de actividades**

Nivel más granular: lista todas las actividades de todos los planes. Permite revisar actividad por actividad el estado de ejecución y gestionar aprobaciones o ediciones.

---

#### Estados del plan de acción

| Estado | Descripción |
|--------|-------------|
| **Sin plan de acción** | Las entidades territoriales aún no han cargado actividades. No hay plan que aprobar. |
| **Pendiente** | Las entidades cargaron actividades pendientes de aprobación por el Monitor. |
| **Aprobado** | Todas las actividades fueron aprobadas. |
| **Confirmado** | El plan está en firme. Las entidades pueden reportar avance. No se pueden agregar nuevas actividades. |

---

#### Actividad 1 — Agregar, editar y eliminar actividades en un plan

El Super Administrador puede intervenir directamente en la estructura de un plan de acción, una capacidad que comparte solo con la Entidad Territorial Central.

**Agregar una actividad:** Desde el detalle de una recomendación dentro del plan, el Super Administrador puede registrar nuevas actividades que la entidad debería ejecutar en respuesta a la recomendación.

**Editar una actividad:** Permite corregir la descripción, el plazo o los parámetros de una actividad existente.

**Eliminar una actividad:** Remueve una actividad del plan. Solo debe usarse cuando la actividad fue registrada por error.

> ⚠️ **Una vez que el plan está en estado Confirmado, no es posible agregar, editar ni eliminar actividades.** Cualquier ajuste debe hacerse antes de la confirmación.

---

#### Actividad 2 — Aprobar actividades del plan de acción

El Super Administrador puede aprobar actividades del plan, al igual que el Monitor. Para aprobar una actividad debe verificar:

- Que la actividad sea coherente con el objetivo de la recomendación
- Que el número de actividades propuesto sea razonable
- Que el plazo de ejecución definido sea viable
- Que la entidad cuente con instrumento de planeación para ejecutarla
- Que la entidad tenga capacidad y recursos para llevarla a cabo

Cada actividad cuenta con una **sección de comentarios** donde el Super Administrador puede registrar observaciones para que la entidad ajuste y vuelva a someter la actividad a revisión.

> Si después de aprobar una actividad el Super Administrador identifica que no cumple los criterios, puede **descartar la aprobación**, lo que devuelve la actividad a estado pendiente.

---

#### Actividad 3 — Subir informes de ejecución

El Super Administrador también puede subir informes de ejecución sobre las actividades de un plan, una acción que normalmente corresponde a las Entidades Territoriales. Esta capacidad es útil cuando se requiere registrar avances de forma centralizada o corregir información.

---

#### Actividad 4 — Revisión y aprobación de informes de ejecución

Una vez confirmado el plan, las entidades territoriales cargan informes de ejecución periódicos. El Super Administrador puede revisar y aprobar estos informes verificando:

- Que la descripción sea coherente con la actividad comprometida
- Que el número de actividades ejecutadas sea consistente con la evidencia adjunta
- Que el PDF de soporte respalde efectivamente lo declarado

> ⚠️ **La aprobación de un informe de ejecución es irreversible.** Una vez aprobado impacta directamente los indicadores de ejecución de todo el sistema. Asegúrese de haber validado completamente la evidencia antes de aprobar.

**Periodicidad de los informes:** Los informes tienen una periodicidad de **seis meses** a partir de la fecha de confirmación del plan de acción.

---

### Módulo 6 — Seguimiento y Monitoreo

**Objetivo:** Que el Super Administrador pueda identificar el estado de ejecución de los planes de acción a nivel nacional y aprobar actividades e informes de seguimiento cuando sea necesario.

Este módulo ofrece una vista consolidada del avance de ejecución de todos los planes activos en el sistema. A diferencia del Monitor, cuya vista está filtrada por sus departamentos asignados, el Super Administrador ve el estado de seguimiento de **todas las alertas del sistema sin excepción**.

#### Acciones disponibles en este módulo

- **Visualizar** el estado de todos los planes activos por alerta a nivel nacional
- **Aprobar actividades** de planes en curso
- **Aprobar informes** de avance presentados por las entidades territoriales

> El Super Administrador debe usar este módulo para supervisión global. Las aprobaciones de actividades e informes son responsabilidad primaria del Monitor asignado a cada departamento; el Super Administrador interviene cuando hay bloqueos, vacíos en la asignación de monitores o necesidad de trazabilidad centralizada.

---

### Módulo 7 — Informes de Seguimiento

**Objetivo:** Que el Super Administrador pueda visualizar todos los informes de seguimiento del sistema y subir informes en nombre del Ministerio del Interior cuando corresponda.

Este módulo concentra los **informes oficiales de seguimiento** cargados por Monitores, Administradores y el Super Administrador. Sirve como repositorio centralizado de la documentación formal de seguimiento.

#### Acciones disponibles

**Visualizar informes:** El Super Administrador accede a todos los informes de seguimiento del sistema, filtrados por alerta, entidad o período.

**Subir un informe de seguimiento:** El Super Administrador puede cargar informes de seguimiento oficiales en representación del Ministerio del Interior. Para ello debe:

1. Seleccionar el tipo de informe (por alerta, por entidad territorial o departamental)
2. Seleccionar el aprobador correspondiente
3. Agregar una descripción del informe
4. Subir el documento

---

### Módulo 8 — Reportes

**Objetivo:** Que el Super Administrador pueda generar consultas de seguimiento sobre la ejecución de actividades a nivel nacional, cargar informes oficiales y aprobar los reportes cargados por Monitores.

El módulo de Reportes permite **oficializar** el seguimiento a la ejecución de actividades sobre las alertas tempranas. El Super Administrador tiene la capacidad adicional de **aprobar informes** cargados por Monitores, una función que comparte solo con el Líder de Macrozona.

---

#### Actividad 1 — Generar una consulta de seguimiento

El Super Administrador puede realizar consultas desde las siguientes perspectivas:

- **Por alerta** — estado de una alerta específica
- **Por entidad territorial** — avance de una entidad en particular
- **Por departamento** — visión consolidada de todas las alertas de un departamento
- **Por municipio** — granularidad a nivel municipal
- **Visión general del período actual** — resumen consolidado de todo el sistema

**Contenido de una consulta a nivel departamental:**

Al consultar por departamento, el Super Administrador obtiene:

- Departamento consultado y total de alertas
- Alertas activas, cerradas, de inminencia y estructurales
- Estado de cada alerta y resumen de escenarios de riesgo
- Total de actividades programadas, ejecutadas y porcentaje de ejecución

---

#### Actividad 2 — Cargar un informe de seguimiento

Con base en la consulta generada, el Super Administrador puede cargar un **informe oficial de seguimiento**. Los tipos de informe disponibles son:

- **Por alerta**
- **Por entidad territorial**
- **Departamental** *(nivel recomendado para una visión integral)*

Para cargar el informe:

1. Seleccionar el tipo de informe
2. Seleccionar el aprobador correspondiente
3. Agregar una descripción
4. Subir el documento

---

#### Actividad 3 — Aprobar informes de seguimiento

El Super Administrador puede **aprobar los informes de seguimiento** cargados por Monitores. Esta aprobación formaliza el reporte como documento oficial validado por el nivel central.

> La aprobación de informes de reportes es una capacidad que el Super Administrador comparte **solo con el Líder de Macrozona**. Ningún otro rol puede aprobar estos informes.

---

### Módulo 9 — Notificaciones

**Objetivo:** Que el Super Administrador identifique las notificaciones críticas del sistema y las use como señal para gestionar acciones pendientes de forma oportuna.

El Super Administrador recibe **todas las notificaciones del sistema**, incluyendo:

| Tipo de notificación | Descripción |
|----------------------|-------------|
| **Nueva alerta** | Se emitió una nueva alerta temprana en el sistema |
| **Alerta cerrada** | Una alerta fue cerrada formalmente |
| **Vencimiento de informe (5 meses)** | Una entidad territorial está próxima al vencimiento de su informe de plan de acción |
| **Informe de seguimiento por alerta (Monitor, 5 meses)** | Un Monitor está próximo al vencimiento de su informe de seguimiento |
| **Observación** | Un Monitor registró una observación sobre una actividad de un plan de acción |

El panel lateral de notificaciones también muestra el **historial de actividades recientes** del sistema, lo que permite al Super Administrador tener trazabilidad en tiempo real de las acciones ejecutadas por todos los actores.

> Las notificaciones de vencimiento (5 meses) son señales de alerta temprana para que el Super Administrador haga seguimiento proactivo a las entidades o monitores que aún no han cumplido con sus informes antes del vencimiento real (6 meses).

---

### Módulo 10 — Interoperabilidad y Oficios de Consumación

**Objetivo:** Que el Super Administrador comprenda el flujo de datos proveniente de SISAT a través de X-Road, sepa consultar la información recibida y gestione los oficios de consumación generados en el cierre de alertas.

---

#### Sección A — Interoperabilidad X-ROAD/SISAT

SI-CIPRAT recibe datos del **Sistema de Información de Seguimiento a las Alertas Tempranas (SISAT)** a través del protocolo de interoperabilidad **X-Road**, que permite el intercambio seguro y trazable de información entre sistemas gubernamentales.

El Super Administrador tiene acceso a la visualización de los datos recibidos a través de este canal. Su rol en este módulo es de **supervisión**: verificar que la sincronización esté operando correctamente y que los datos recibidos sean coherentes con la información esperada.

> Si detecta inconsistencias en los datos de interoperabilidad o errores en los endpoints, debe reportarlo al equipo técnico de desarrollo: [siciprat@mininterior.gov.co](mailto:siciprat@mininterior.gov.co)

---

#### Sección B — Oficios de Consumación

Los **oficios de consumación** son los documentos oficiales que formalizan el cierre de una alerta temprana. En SI-CIPRAT, estos oficios pueden provenir de dos fuentes:

**Recibidos vía interoperabilidad (X-Road):** El sistema recibe automáticamente oficios de consumación desde SISAT. Estos quedan disponibles en el módulo de Oficios de Consumación para consulta de todos los roles con acceso de visualización.

**Subidos manualmente por el Super Administrador:** Cuando el oficio de consumación no llega por interoperabilidad, el Super Administrador puede **cargarlo manualmente** en el sistema. Esta es una capacidad exclusiva del Super Administrador; ningún otro rol puede subir oficios de consumación.

> ⚠️ **Solo el Super Administrador puede subir oficios de consumación.** Antes de cargar un oficio de forma manual, verifique que no haya sido recibido ya por la vía de interoperabilidad para evitar duplicados en el sistema.

**Vista del módulo:**

La tabla de oficios de consumación permite consultar los documentos registrados. Los demás roles (Administrador, Líder de Macrozona, Monitor) tienen acceso de visualización a este módulo pero no pueden subir documentos.

---

## Indicadores de Logro

- [ ] Puede ingresar a la plataforma con autenticación de dos factores
- [ ] Puede invitar usuarios de todos los roles (excepto Super Administrador vía invitación estándar)
- [ ] Puede escalar un usuario al rol Super Administrador mediante edición de perfil
- [ ] Puede crear, editar y estructurar entidades con subdirecciones
- [ ] Puede registrar, editar, cerrar y eliminar una alerta completa
- [ ] Puede crear, editar y eliminar recomendaciones de una alerta
- [ ] Puede agregar, editar y eliminar actividades en un plan de acción
- [ ] Puede aprobar actividades e informes de ejecución de planes
- [ ] Puede cargar y aprobar informes en el módulo de Reportes
- [ ] Puede subir oficios de consumación manualmente
- [ ] Puede consultar datos de interoperabilidad X-Road/SISAT
- [ ] Conoce todas las capacidades exclusivas de su rol y cuándo utilizarlas
