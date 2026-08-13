# Rol: Monitor — Plan de Capacitación

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
| **Rol** | Monitor |
| **Alcance** | Departamental — uno o más departamentos asignados |
| **Objetivo principal** | Hacer seguimiento a las alertas tempranas de su(s) departamento(s), aprobar planes de acción e informes de entidades territoriales |
| **Quién ocupa este rol** | Profesional del Ministerio del Interior o enlace territorial con responsabilidad de monitoreo departamental |

---

## Objetivo de Capacitación

Al finalizar la formación, el Monitor podrá navegar las alertas de sus departamentos asignados, consultar recomendaciones, aprobar planes de acción e informes de entidades territoriales, registrar observaciones, ejecutar reportes y gestionar el seguimiento integral de su territorio.

---

## Alcance en la Plataforma

### Módulos disponibles

| Módulo | Acciones disponibles |
|--------|----------------------|
| Inicio de Plataforma | Vista segmentada por departamento(s) asignado(s) |
| Alertas Tempranas | Visualización según filtro departamental; ver historial de actividades |
| Recomendaciones | Visualización de recomendaciones según filtro departamental |
| Planes de Acción | Visualización filtrada; aprobar plan de acción; registrar observaciones sobre actividades |
| Seguimiento y Monitoreo | Aprobar actividades e informes de seguimiento |
| Informes de Seguimiento | Visualizar informes |
| Reportes | Consultar, cargar y aprobar informes |
| Visualización Geográfica | Mapa interactivo y mapas estáticos (filtrado por departamentos asignados) |
| Notificaciones | Todas las notificaciones del sistema |

### Restricciones del rol

- **No gestiona** usuarios ni entidades
- **No puede** crear, editar ni eliminar alertas
- **No puede** crear ni editar recomendaciones
- **No puede** agregar actividades a planes (esa acción es de Entidad Territorial)
- Su visualización está restringida a los departamentos asignados en su perfil

---

## Segmentación de Visualización

- **Dashboard de inicio**: Vista segmentada al nivel del (los) departamento(s) asignado(s).
- **Alertas**: Solo alertas de sus departamentos asignados.
- **Planes de acción**: Planes filtrados por alertas de sus departamentos; puede aprobarlos.
- **Seguimiento**: Puede aprobar actividades e informes enviados por entidades territoriales.
- **Reportes**: Consulta y carga según su cobertura departamental.

---

## Ruta de Aprendizaje

### Módulo 0 — Contexto de la Plataforma SI-CIPRAT

**Objetivo:** Que el usuario entienda el marco institucional en el que opera y el funcionamiento de SI-CIPRAT antes de comenzar a usar la plataforma.

SI-CIPRAT es el **Sistema de Información de la Secretaría Técnica de la Comisión Intersectorial para la Respuesta Rápida a las Alertas Tempranas (CIPRAT)**, una plataforma desarrollada por el **Ministerio del Interior de Colombia** para centralizar y articular la gestión de las alertas tempranas emitidas por la Defensoría del Pueblo.

La **Comisión Intersectorial CIPRAT** reúne a entidades del nivel central y territorial con el mandato de responder de forma coordinada y oportuna ante los escenarios de riesgo identificados en el territorio nacional. Antes de SI-CIPRAT, esta coordinación dependía de procesos manuales, comunicaciones fragmentadas y ausencia de una fuente de información unificada, lo que generaba reprocesos, demoras y dificultades para tomar decisiones basadas en datos confiables y en tiempo real.

SI-CIPRAT resuelve estos retos al ofrecer un espacio digital común donde la Defensoría del Pueblo emite alertas tempranas, el Ministerio del Interior las gestiona y emite recomendaciones, y las entidades territoriales responden con planes de acción concretos que son monitoreados, aprobados y seguidos a lo largo de todo su ciclo de vida. Cada actor del ecosistema —Defensoría, Ministerio, entidades centrales, subdirecciones y monitores— tiene un rol definido dentro de la plataforma, con acceso segmentado según sus responsabilidades.

El objetivo central del sistema es garantizar la articulación entre todos estos niveles mediante una fuente de información unificada, que permita una coordinación eficiente, el intercambio oportuno de información y la toma de decisiones basadas en datos confiables para la prevención y atención integral de los riesgos identificados en el territorio.

---

### Módulo 1 — Acceso a la Plataforma

**Objetivo:** Que el Monitor pueda ingresar de forma autónoma a la plataforma, conocer el flujo completo de autenticación y saber cómo actuar ante cualquier problema de acceso.

#### Flujo de acceso (happy path)

**Paso 1 — Recibir invitación y asignar contraseña**

El Administrador registra al Monitor en el sistema. La plataforma envía automáticamente un **correo de invitación** a la dirección registrada con un enlace de activación. Al hacer clic en el enlace, el usuario asigna su contraseña con los siguientes requisitos:

- Mínimo 8 caracteres
- Al menos un carácter especial (ej. `!`, `@`, `#`, `$`, `%`)

**Paso 2 — Ingresar a la plataforma**

Ir a la URL de acceso e ingresar el correo electrónico y la contraseña asignada:

> [https://polite-wave-005a5910f.3.azurestaticapps.net/signin](https://polite-wave-005a5910f.3.azurestaticapps.net/signin)

**Paso 3 — Verificar identidad con código de 4 dígitos**

Tras ingresar las credenciales, la plataforma envía automáticamente un **código de verificación de 4 dígitos** al correo registrado. Ingresar el código en la pantalla de verificación y hacer clic en **Confirmar**.

> **Sin este código no es posible acceder a la plataforma.** Es una medida de seguridad obligatoria del sistema.

El código tiene una vigencia de **1 hora**. Una vez confirmado, la sesión queda activa.

> **Importante:** Al ingresar, la plataforma mostrará únicamente las alertas asociadas a los departamentos asignados en su rol.

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
- Revisar su perfil: rol, departamentos asignados, cargo y área
- Entender el alcance de su rol vs. Líder de Macrozona y Administrador

### Módulo 2 — Inicio de la Plataforma

**Objetivo:** Que el Monitor pueda interpretar el panel de inicio como una vista ejecutiva del estado de las alertas en sus departamentos asignados, identificando de forma rápida la situación general antes de profundizar en módulos específicos.

Al ingresar al sistema, el Monitor llega a la pantalla de **Inicio**, que presenta un resumen ejecutivo de la situación de alertas tempranas en los departamentos asignados a su rol.

> **Toda la información del Inicio corresponde exclusivamente a los departamentos asignados.** Para verificar cuáles son, consultar la sección **Perfil** del usuario.

#### Indicadores de alertas por departamento

El Inicio permite identificar, para el conjunto de departamentos asignados:

- **Total de alertas** registradas en el sistema
- **Alertas activas** — en seguimiento o con planes de acción en curso
- **Alertas cerradas** — con proceso finalizado
- **Alertas estructurales** — asociadas a condiciones de riesgo de mediano y largo plazo
- **Alertas de inminencia** — asociadas a situaciones de riesgo inmediato que requieren respuesta urgente

#### Porcentaje de avance en ejecución

El Inicio también muestra el **porcentaje de avance en la ejecución** de las alertas. Este indicador refleja el progreso de los planes de acción asociados a cada alerta.

> El cálculo de este porcentaje sigue la metodología definida en el **capítulo de cálculo de avance** del sistema. Consultar dicho capítulo para entender cómo se pondera el avance según actividades completadas, informes aprobados y estado del plan.

#### Vista de mapa

El Inicio incluye una **vista de mapa** que permite visualizar geográficamente la distribución de alertas por departamento asignado. Desde el mapa es posible identificar de forma rápida en qué territorios hay mayor concentración de alertas activas.

#### Últimas alertas emitidas

El Inicio presenta también un listado de las **últimas alertas emitidas** en los departamentos asignados, permitiendo al Monitor estar al tanto de las novedades más recientes sin necesidad de navegar al módulo de alertas.

### Módulo 3 — Alertas Tempranas

**Objetivo:** Que el Monitor pueda consultar, filtrar y analizar el detalle de las alertas tempranas de sus departamentos asignados, accediendo a información específica de cada alerta y a las recomendaciones vinculadas.

Este módulo es **exclusivamente de consulta** para el rol Monitor. No permite crear, editar ni eliminar alertas. Su propósito es que el Monitor tenga visibilidad completa del detalle de las alertas en sus departamentos asignados.

#### Indicadores generales del módulo

Al ingresar al módulo, se presentan indicadores agregados de las alertas asignadas:

- **Total de alertas** de los departamentos asignados
- **Alertas de inminencia** — riesgo inmediato
- **Alertas estructurales** — riesgo de mediano y largo plazo

#### Vista de lista — detalle de alertas

El módulo presenta una tabla con el detalle de cada alerta, con las siguientes columnas:

| Columna | Descripción |
|---------|-------------|
| **Alerta** | Identificador o nombre de la alerta |
| **Tipo** | Inminencia o Estructural |
| **Tema** | Temática principal de la alerta |
| **Estado** | Estado actual (activa, cerrada, etc.) |
| **Porcentaje de ejecución** | Avance del plan de acción asociado |
| **Cantidad de Recomendaciones** | Número de recomendaciones emitidas sobre la alerta |
| **Creación** | Fecha de registro de la alerta en el sistema |

#### Búsqueda y filtros

El Monitor puede localizar una alerta específica mediante:

- **Búsqueda por nombre** — campo de texto libre para buscar por nombre o identificador de la alerta
- **Filtros disponibles:**
  - **Tipo** — Inminencia / Estructural
  - **Estado** — Activa / Cerrada / otros estados disponibles
  - **Etiqueta** — clasificación temática asignada a la alerta
  - **Economías Ilegales** — filtro por tipo de economía ilegal asociada
  - **Grupos Armados** — filtro por grupo armado relacionado con la alerta

Los filtros pueden combinarse para acotar los resultados y encontrar alertas específicas con mayor precisión.

> **¿No ve una alerta de su departamento o ve alertas que no le corresponden?** Esto puede indicar un error en la configuración de su rol. Comuníquese con el equipo de soporte: [siciprat@mininterior.gov.co](mailto:siciprat@mininterior.gov.co)

#### Descarga de la lista de alertas

Desde este módulo el Monitor puede **descargar la lista de alertas** de sus departamentos asignados. Esta descarga es útil para realizar análisis estadísticos externos o consolidar información de seguimiento fuera de la plataforma.

---

#### Detalle de una alerta

En la lista de alertas, cada fila tiene un menú de tres puntos ( **⋯** ) o un ícono de **lupa** que al hacer clic despliega las opciones de consulta. Desde allí el Monitor accede al **detalle completo** de esa alerta. Este detalle está organizado en las siguientes secciones:

- **Información general** — datos principales de la alerta: identificador, tipo, estado, fechas, temática
- **Lugar de advertencia** — ubicación geográfica (departamento, municipio) donde se emite la alerta
- **Conflicto** — descripción del contexto de conflicto asociado a la alerta
- **Conductas vulneratorias e infracciones al D.I.H.** — registro de conductas identificadas que vulneran derechos o infringen el Derecho Internacional Humanitario
- **Población afectada** — caracterización de la población en riesgo
- **Alertas subsumidas** — alertas anteriores que quedan integradas dentro de esta alerta

Adicionalmente, desde el detalle el Monitor puede acceder al **PDF oficial emitido por la Defensoría del Pueblo**, que contiene el pronunciamiento formal que dio origen a la alerta.

---

#### Recomendaciones de la alerta

Desde el detalle de la alerta, el Monitor puede consultar las **recomendaciones emitidas** para esa alerta. Esta vista le permite identificar:

- Las recomendaciones específicas que aplican a la alerta
- Las **entidades principales responsables** de dar respuesta a cada recomendación
- El estado de cada recomendación en términos de carga de actividades del plan de acción

> Esta información es clave para el Monitor, ya que le permite hacer seguimiento a qué entidades tienen compromisos pendientes y verificar que estén avanzando en la carga de sus actividades.

### Módulo 4 — Planes de Acción

> ⚠️ **Pendiente de verificación.** Se está confirmando si el Monitor accede a este módulo de forma independiente o si su interacción con los planes de acción ocurre íntegramente desde el módulo de Seguimiento. Este módulo se completará una vez verificado.

### Módulo 5 — Seguimiento de Planes de Acción

**Objetivo:** Que el Monitor pueda identificar el estado de los planes de acción asociados a las alertas de sus departamentos, aprobar las actividades cargadas por las entidades territoriales y hacer seguimiento al avance de ejecución, garantizando que los compromisos acordados se cumplan de forma oportuna.

#### Niveles de visualización

Este módulo ofrece tres niveles de profundidad para analizar el estado de los planes de acción:

**Nivel 1 — Vista de alertas**

Lista todas las alertas asignadas al Monitor con información consolidada del plan de acción de cada una. Es el punto de entrada para identificar en cuál alerta hay acciones pendientes de gestión.

Las columnas disponibles en esta vista son:

| Columna | Descripción |
|---------|-------------|
| **Alerta** | Nombre o identificador de la alerta |
| **Programado** | Total de actividades programadas en el plan de acción |
| **Ejecutado** | Total de actividades ejecutadas y reportadas |
| **% Cumplimiento** | Porcentaje de lo programado que ya fue ejecutado |
| **Estado del plan** | Estado actual del plan de acción (ver estados más abajo) |

**Nivel 2 — Vista de recomendaciones**

Despliega todas las recomendaciones de todas las alertas asignadas. Permite al Monitor identificar, por recomendación, qué entidades tienen compromisos y cuál es el avance de cada una.

**Nivel 3 — Vista de actividades**

Nivel más granular: lista todas las actividades de todos los planes de acción. Permite al Monitor revisar actividad por actividad el estado de ejecución y gestionar aprobaciones individuales.

---

#### Estados del plan de acción

Un plan de acción asociado a una alerta puede encontrarse en uno de los siguientes estados:

**Sin plan de acción**
Las entidades territoriales aún no han cargado actividades en respuesta a las recomendaciones de la alerta. No hay plan que aprobar. El Monitor debe hacer seguimiento para que las entidades responsables inicien la carga.

**Pendiente**
Las entidades territoriales ya cargaron actividades, pero estas están pendientes de aprobación por parte del Monitor. Es en este estado donde el Monitor debe revisar que cada actividad tenga coherencia con el objetivo de la recomendación y proceder a aprobarla o registrar observaciones.

**Aprobado**
Todas las actividades del plan han sido revisadas y aprobadas por el Monitor.

**Confirmado**
El plan ha sido confirmado en firme. Esto habilita a las entidades territoriales para comenzar a reportar el avance de ejecución sobre cada actividad. **Una vez confirmado el plan, no es posible agregar nuevas actividades.** Es el estado que da inicio formal a la fase de ejecución.

---

#### Actividad 1 — Buscar alertas tempranas

El Monitor puede buscar alertas dentro del módulo por nombre para ubicar rápidamente los planes que requieren su atención. La vista de alertas muestra, para cada una, las columnas de programado, ejecutado, porcentaje de cumplimiento y estado del plan, lo que permite priorizar cuáles alertas requieren acción inmediata.

---

#### Actividad 2 — Identificar el plan de acción de la alerta temprana

Una vez identificada la alerta, el Monitor ingresa al detalle del plan de acción haciendo clic en el botón **Plan de Acción** de esa alerta. Desde allí puede navegar los dos niveles de profundidad del plan:

**Recomendaciones del plan**
El Monitor visualiza las recomendaciones asignadas a la alerta. Cada recomendación está vinculada a una **entidad principal responsable**, que es quien define y carga las actividades que ejecutará para mitigar el escenario de riesgo.

**Actividades por recomendación**
Al ingresar a una recomendación, el Monitor puede ver todas las **actividades cargadas por la entidad principal** en respuesta a esa recomendación. Este es el nivel donde se concentra la revisión y el trabajo de aprobación.

---

#### Actividad 3 — Aprobación de actividades del plan de acción

Para cada actividad cargada por la entidad, el Monitor debe verificar los siguientes criterios antes de aprobar:

- Que la actividad sea **coherente con el objetivo de la recomendación**
- Que el **número de actividades** propuesto sea razonable y suficiente
- Que el **plazo de ejecución** definido por la entidad sea viable
- Que la entidad cuente con **instrumento de planeación** para ejecutar la actividad
- Que la entidad tenga **capacidad y recursos** para llevarla a cabo

Una vez validados estos criterios, el Monitor **aprueba la actividad**. Esta aprobación queda registrada en el sistema con trazabilidad de qué monitor revisó y aprobó cada actividad específica.

> Si después de aprobar una actividad el Monitor identifica que no cumple con los criterios, puede **descartar la aprobación**, lo que devuelve la actividad a estado pendiente para su ajuste por parte de la entidad.

Cada actividad cuenta además con una **sección de comentarios** donde el Monitor puede dejar observaciones para que la entidad principal lea, ajuste y vuelva a someter la actividad a revisión. Esta sección es la herramienta de trazabilidad para los ciclos de revisión y ajuste.

El objetivo de esta actividad es **aprobar la totalidad de las actividades de todas las recomendaciones de la alerta**. Solo cuando esto se cumpla será posible avanzar a la confirmación del plan.

> Si existe al menos una actividad sin aprobar, el plan **no puede ser confirmado**.

---

#### Actividad 4 — Confirmación del plan de acción

Una vez que todas las actividades de todas las recomendaciones están aprobadas, el Monitor procede con la **confirmación del plan de acción**, que lo pone en firme y tiene dos efectos inmediatos:

**Bloqueo de cargue de actividades**
Las entidades territoriales ya no podrán agregar nuevas actividades al plan. La estructura de compromisos queda cerrada tal como fue aprobada.

**Habilitación del reporte de ejecución**
Se habilita para las entidades territoriales el **cargue de informes de ejecución**, a través de los cuales reportarán el avance real sobre las actividades programadas. Estos informes alimentan directamente el **porcentaje de ejecución** visible en el módulo de inicio y en la vista de alertas del seguimiento.

> La confirmación del plan marca el inicio formal de la fase de ejecución. A partir de aquí, el rol del Monitor transita de la aprobación de compromisos al control del avance de ejecución reportado por las entidades.

---

#### Actividad 5 — Revisión y aprobación de informes de ejecución

Una vez confirmado el plan, las entidades territoriales quedan habilitadas para cargar informes de ejecución por cada actividad. El Monitor accede a estos informes directamente desde el detalle de cada actividad.

**Periodicidad de los informes**

Los informes tienen una periodicidad de **seis meses a partir de la fecha de confirmación del plan de acción**. Al vencer cada período se habilita automáticamente el siguiente ciclo de seis meses.

> **Ejemplo:** Si el plan se confirma el 30 de enero, la entidad debe cargar su primer informe dentro del período que va hasta el 30 de julio. Vencida esa fecha, se abre el segundo período por otros seis meses.

**Contenido de cada informe**

Cada informe de ejecución cargado por la entidad territorial contiene:

- **Descripción de lo ejecutado** — qué se realizó, cuándo y bajo qué condiciones
- **Recursos utilizados** — disponibilidad de recursos para la ejecución
- **Actividades ejecutadas vs. programadas** — número concreto de lo realizado frente a lo comprometido en el plan

> **Ejemplo:** Si la entidad programó 10 mesas técnicas, el informe puede reportar que realizó 4, con la descripción y evidencia correspondiente.

- **Documento PDF de soporte** — evidencia adjunta que respalda la ejecución declarada (actas, registros, certificaciones, etc.)

**Validación por parte del Monitor**

Antes de aprobar, el Monitor debe verificar:

- Que la descripción sea coherente con la actividad comprometida en el plan
- Que el número de actividades ejecutadas sea consistente con la evidencia adjunta
- Que el PDF de soporte respalde efectivamente lo declarado

**Aprobación del informe**

Una vez validada la información, el Monitor aprueba el informe. Esta aprobación afecta directamente el **porcentaje de ejecución** del plan, visible en el módulo de inicio y en la vista de seguimiento.

> ⚠️ **La aprobación de un informe de ejecución es irreversible.** Una vez aprobado no puede deshacerse, ya que impacta directamente los indicadores de ejecución de todo el sistema. El Monitor debe asegurarse de haber validado completamente la evidencia antes de aprobar.

### Módulo 6 — Reportes

**Objetivo:** Que el Monitor pueda generar consultas de seguimiento sobre la ejecución de las actividades de las alertas de sus departamentos asignados, y cargar informes oficiales con corte a la fecha que queden documentados y aprobados por el Líder de Macrozona.

Este módulo permite **oficializar** el reporte del seguimiento a la ejecución de actividades sobre las alertas tempranas.

---

#### Actividad 1 — Generar una consulta de seguimiento

El Monitor puede realizar consultas puntuales desde las siguientes perspectivas:

- **Por alerta** — consulta el estado de una alerta específica
- **Por entidad territorial** — consulta el avance de una entidad en particular
- **Por departamento** — visión consolidada de todas las alertas de un departamento
- **Por municipio** — granularidad a nivel municipal
- **Visión general del período actual** — resumen consolidado de todos los departamentos asignados

**Contenido de una consulta a nivel departamental**

Al consultar por departamento, el Monitor obtiene:

- Departamento consultado
- Total de alertas del departamento
- Alertas activas y cerradas
- Alertas de inminencia y estructurales
- Estado de cada alerta
- Resumen de los escenarios de riesgo de cada alerta
- Estado de avance por alerta:
  - Total de actividades programadas
  - Total de actividades ejecutadas
  - Porcentaje de ejecución sobre lo programado

Este nivel de consulta permite consolidar un detalle específico del estado del seguimiento antes de emitir el informe formal.

---

#### Actividad 2 — Cargar el informe de seguimiento

Con base en la consulta generada, el Monitor puede cargar un **informe oficial de seguimiento**. Los tipos de informe disponibles son:

- **Por alerta**
- **Por entidad territorial**
- **Departamental** *(nivel recomendado para una visión integral)*

Para cargar el informe, el Monitor debe:

1. Seleccionar el tipo de informe
2. Seleccionar el **aprobador** — debe ser el **Líder de Macrozona** correspondiente
3. Agregar una descripción del informe
4. Subir el documento del informe

Una vez cargado, el sistema envía automáticamente una **notificación al aprobador** (Líder de Macrozona) para que proceda con la revisión y aprobación.

> El propósito de este módulo es dejar una documentación formal y trazable de los informes emitidos por el Monitor, con corte a la fecha, sobre el seguimiento a la ejecución de las entidades principales en las alertas asignadas a su territorio.

### Módulo 7 — Notificaciones
- Identificar notificaciones críticas: vencimiento de informes (5 meses), nuevas alertas, observaciones
- Usar el panel lateral para hacer seguimiento de actividades recientes

---

## Indicadores de Logro

- [ ] Puede identificar todas las alertas activas en sus departamentos asignados
- [ ] Puede consultar el detalle de un plan de acción con sus actividades
- [ ] Puede aprobar un plan de acción enviado por una Entidad Territorial
- [ ] Puede aprobar informes de avance de planes en ejecución
- [ ] Puede registrar observaciones sobre actividades de un plan
- [ ] Puede consultar y cargar reportes de su cobertura territorial
- [ ] Entiende los límites de su rol y cuándo escalar al Administrador o Super Admin
