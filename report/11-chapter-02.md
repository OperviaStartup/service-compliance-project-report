# Capítulo II: Requirements Development and Software Solution Design

## Nota metodológica

Este capítulo sigue la secuencia problema → investigación → hallazgos →
needfinding → requirements → Strategic DDD → arquitectura. A la fecha de esta
versión, no existen entrevistas reales incorporadas al repositorio. Por ello,
los artefactos posteriores a la investigación se identifican como
**Candidate**, **Preliminary**, **Provisional** o **Pending validation** y no
constituyen evidencia oficial.

## 2.1. Competidores

### 2.1.1. Análisis competitivo

El análisis competitivo permite ubicar la hipótesis de Service Compliance
frente a productos que digitalizan operaciones, inventario o control de
servicios. No demuestra que tales productos resuelvan —ni que no resuelvan— el
problema específico de una empresa de limpieza tercerizada en Perú.

| Producto / alternativa | Oferta declarada por su fuente oficial | Relevancia para la investigación | Pregunta abierta |
|---|---|---|---|
| Apicbase | Plataforma de operación de foodservice con recetas, compras, inventario y dashboards para operaciones multisede. | Muestra un enfoque de estandarización y fuente central de información. | ¿Una operación de limpieza requiere una centralización semejante o un flujo más simple? |
| MarketMan | Gestión de inventario, facturación, compras, costos y pedidos para restaurantes. | Expone cómo una herramienta relaciona operación y compras. | ¿La trazabilidad contractual es una necesidad distinta de la gestión de insumos? |
| WISK | Gestión de inventario, facturas, compras, costos de recetas y reportes para bares y restaurantes. | Aporta referencias sobre captura operativa móvil y control por ubicación. | ¿Qué tipo de captura operativa es proporcional y aceptable en limpieza tercerizada? |
| Restaurant365 | Suite para restaurantes que integra contabilidad, inventario, operaciones, personal y reportes. | Ilustra la amplitud y complejidad de una plataforma empresarial integrada. | ¿Qué mínimo de capacidades evita que Service Compliance se convierta en un ERP genérico? |
| Proceso actual sin producto especializado | Contratos, formatos, mensajes, llamadas, hojas de cálculo y supervisión presencial. | Debe analizarse como alternativa real, no como una carencia automática. | ¿Qué resuelve adecuadamente y qué falla en situaciones concretas? |

<sub>*Tabla 1. Panorama competitivo preliminar. Las fuentes describen sus
propias ofertas y no validan necesidades de Opervia.*</sub>

**Lectura comparativa provisional.** Las alternativas revisadas se concentran
en foodservice, inventario, compras, costos o administración empresarial. La
diferenciación posible de Service Compliance no se formulará como una ventaja
confirmada; la investigación debe comprobar si existe una necesidad de enlazar
condiciones contractuales, obligación, ejecución, evidencia, evaluación y
respuesta a no conformidades.

### 2.1.2. Estrategias y tácticas frente a competidores

| Estrategia candidata | Fundamento por comprobar | Estado |
|---|---|---|
| Enfocar la conversación en trazabilidad de compromisos de servicio, no en gestión genérica de tareas. | Que el contrato y su interpretación sean fuente real de fricción. | **Hypothesis — Pending validation** |
| Priorizar el flujo que los participantes ya realizan antes de incorporar tecnología de captura. | Que la mayor fricción esté en un proceso existente y no en ausencia de QR, GPS o fotos. | **Hypothesis — Pending validation** |
| Diseñar para que comprador, cliente y usuario puedan tener intereses distintos. | Que el modelo de compra no recaiga necesariamente en la persona que opera en campo. | **Hypothesis — Pending validation** |
| Definir evidencia configurable solo si los contratos y usuarios lo requieren. | Que no exista una evidencia universalmente aceptable. | **Hypothesis — Pending validation** |

No se definirán precios, campañas, integraciones ni tecnologías a partir de
este análisis. Esas decisiones dependen de evidencia de usuarios, viabilidad
académica y alcance aprobado.

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

**Objetivo.** Descubrir cómo se realiza hoy el ciclo de servicio, desde la
interpretación de un acuerdo hasta la elaboración de un reporte o la respuesta
a un reclamo. La entrevista no busca vender, probar aceptación de una
funcionalidad ni inducir respuestas sobre QR, NFC, GPS, fotografías o una app.

**Participantes candidatos.** Personas que administran contratos o la
operación; supervisan servicios; ejecutan trabajo en campo; representan a la
organización cliente; o toman/autorizarían una decisión de compra. La selección
final, consentimiento y resguardo de datos son **Pending validation**.

**Guía semiestructurada.**

1. Cuénteme sobre el último servicio que necesitó coordinar, supervisar o
   ejecutar de principio a fin.
2. ¿Cómo se acuerda qué debe realizarse y dónde queda registrado?
3. Cuando una condición del acuerdo es ambigua o cambia, ¿quién la interpreta y
   cómo se comunica el cambio?
4. ¿Cómo sabe una persona que ejecuta el servicio qué debe hacer, en qué lugar,
   con qué frecuencia y bajo qué estándar?
5. ¿Cómo se supervisa el trabajo actualmente? Describa el último caso.
6. ¿Qué se considera evidencia aceptable de que una actividad ocurrió o se
   realizó correctamente? ¿Quién lo decide?
7. ¿Qué ocurre cuando falta evidencia, llega tarde o no convence al cliente?
8. ¿Cómo detectan que una obligación está pendiente, vencida o incompleta?
9. Describa el último reclamo, desvío o incumplimiento: ¿cómo se registró,
   evaluó, comunicó y cerró?
10. ¿Cómo se documentan y verifican las acciones correctivas?
11. ¿Cómo se prepara hoy un reporte para el cliente y qué información resulta
    difícil de reunir?
12. ¿Qué herramientas, formatos y canales utiliza en cada paso? ¿Qué
    información se duplica o se pierde?
13. ¿Qué sucede si no hay conectividad, no se puede usar un teléfono o no es
    posible capturar una evidencia?
14. ¿Quién decidiría pagar por cambiar este proceso? ¿Quién lo usaría y quién
    debería aprobarlo?
15. Si pudiera cambiar una sola parte del proceso actual, ¿cuál sería y por
    qué?

**Repreguntas neutrales.** “¿Puede mostrar un ejemplo anonimizado?”, “¿qué
ocurrió después?”, “¿quién participó?”, “¿cómo lo sabe?” y “¿qué alternativa
usaron?”.

**No preguntar como validación de solución.** No se emplearán preguntas tales
como “¿Usaría QR?”, “¿Le gustaría GPS?” o “¿Querría una app?”, pues presuponen
una solución antes de descubrir la necesidad.

### 2.2.2. Registro de entrevistas

No hay entrevistas reales registradas en este repositorio. Esta sección se
mantiene deliberadamente sin participantes, capturas, videos, enlaces,
timestamps, nombres, edades, citas ni porcentajes.

Cuando exista investigación real, cada registro deberá contener, según
autorización: identificador anonimizado, rol y tipo de organización, fecha,
consentimiento, guía utilizada, notas/transcripción autorizada y referencia a
evidencia permitida. El equipo no debe publicar datos personales o materiales
sin autorización.

### 2.2.3. Análisis de entrevistas

**Pending validation.** El análisis se realizará solo después de registrar
entrevistas reales. Debe separar observaciones, citas verificables autorizadas,
interpretaciones, contradicciones y decisiones pendientes. Ningún resultado de
`docs/PROVISIONAL_RESEARCH.md` debe migrarse a esta sección como hallazgo.

## 2.3. Needfinding

Los siguientes artefactos se derivan de escenarios provisionales, no de
entrevistas. Su finalidad es preparar la investigación y hacer visibles las
decisiones que todavía no deben fijarse.

### 2.3.1. User personas

| Persona candidata | Objetivo posible | Incertidumbres críticas | Estado |
|---|---|---|---|
| Operario de campo | Completar una actividad de servicio e informar resultados o impedimentos. | Instrucciones recibidas, autonomía, acceso a dispositivo y conectividad. | **Candidate — Preliminary — Pending validation** |
| Supervisor de servicio | Coordinar, revisar y responder ante desvíos. | Alcance de supervisión, criterios de aceptación y carga de consolidación. | **Candidate — Preliminary — Pending validation** |
| Responsable contractual o de operaciones | Interpretar condiciones, acordar cambios y explicar el estado del servicio. | Si este rol existe, quién lo asume y si decide la compra. | **Candidate — Preliminary — Pending validation** |
| Representante de la organización cliente | Recibir el servicio, revisar resultados o plantear reclamos. | Participación real en aceptación, evidencia y reportes. | **Candidate — Preliminary — Pending validation** |

Estas no son personas reales ni incluyen datos demográficos. Se revisarán o
descartarán luego de entrevistas.

### 2.3.2. User Task Matrix

Las tareas describen actividades que pueden existir sin Service Compliance. No
son historias de usuario ni funcionalidades propuestas.

| Actor candidato | Tarea actual candidata | Resultado buscado | Estado |
|---|---|---|---|
| Responsable contractual | Interpretar una condición de servicio y comunicar lo esperado. | Que el servicio pueda ejecutarse conforme a lo acordado. | **Preliminary — Pending validation** |
| Supervisor | Distribuir o coordinar trabajo para una ubicación y periodo. | Que una persona sepa qué atender. | **Preliminary — Pending validation** |
| Operario | Ejecutar una actividad de limpieza según una instrucción recibida. | Completar el servicio o comunicar un impedimento. | **Preliminary — Pending validation** |
| Operario o supervisor | Registrar, conservar o comunicar un resultado de ejecución. | Poder informar lo ocurrido. | **Preliminary — Pending validation** |
| Supervisor | Comparar lo esperado con lo reportado y resolver una excepción. | Determinar si requiere atención adicional. | **Preliminary — Pending validation** |
| Organización cliente o prestadora | Plantear, atender o cerrar un reclamo. | Recuperar el nivel de servicio acordado o explicar una decisión. | **Preliminary — Pending validation** |
| Responsable de operaciones | Consolidar información de servicio para una revisión o reporte. | Comunicar estado y pendientes a la parte interesada. | **Preliminary — Pending validation** |

### 2.3.3. User Journey Mapping

| Etapa candidata | Acciones posibles | Riesgos o preguntas por validar |
|---|---|---|
| Acordar servicio | Se negocian condiciones, ubicaciones, frecuencias y estándares. | ¿Las condiciones están suficientemente estructuradas para orientar el trabajo? |
| Traducir a operación | Alguien interpreta el acuerdo y comunica una actividad o turno. | ¿Se pierden detalles o se generan instrucciones informales? |
| Ejecutar | El operario realiza el servicio o enfrenta una excepción. | ¿Qué impide completar el trabajo y cómo se comunica? |
| Evidenciar o informar | Se usa un formato, mensaje, firma, foto u otro medio. | ¿Qué es aceptado, suficiente y proporcional? |
| Supervisar y evaluar | Se revisa lo reportado, se inspecciona o se responde a un reclamo. | ¿Qué criterio define conformidad o no conformidad? |
| Corregir y reportar | Se coordina una respuesta y se consolida información. | ¿Cómo se registra una corrección y quién recibe el reporte? |

<sub>*Tabla 2. Journey As-Is preliminar; no representa una observación de
campo.*</sub>

### 2.3.4. Empathy Mapping

| Área | Hallazgo provisional | Estado |
|---|---|---|
| Lo que una persona operaria puede ver o hacer | Puede alternar ejecución física, instrucciones cambiantes y comunicación de excepciones. | **Hypothesis — Pending validation** |
| Lo que una persona supervisora puede necesitar | Puede requerir contexto suficiente para priorizar revisiones o explicar una decisión. | **Hypothesis — Pending validation** |
| Lo que una organización cliente puede esperar | Puede solicitar claridad ante un reclamo, pero el formato y nivel de detalle son desconocidos. | **Hypothesis — Pending validation** |
| Lo que puede generar fricción | Registrar información, interpretar condiciones, obtener aceptación o conciliar versiones podría resultar más costoso que el problema que resuelve. | **Hypothesis — Pending validation** |

### 2.3.5. Big Picture EventStorming

No se afirma que se haya realizado una sesión de EventStorming. La siguiente
lista es un inventario de **eventos candidatos** para revisar con participantes
del dominio. Los eventos se expresan en pasado y excluyen decisiones técnicas.

| Secuencia candidata | Evento de dominio candidato | Pregunta / hotspot |
|---:|---|---|
| 1 | Condición de servicio acordada | ¿Qué parte del acuerdo es operable y cuál requiere interpretación? |
| 2 | Obligación de servicio definida | ¿La obligación se deriva, se planifica manualmente o ambas? |
| 3 | Obligación comunicada | ¿Quién recibe instrucciones y cómo confirma comprensión? |
| 4 | Ejecución iniciada | ¿Qué significa iniciar en cada contrato? |
| 5 | Resultado de ejecución informado | ¿Qué resultado se comunica y en qué momento? |
| 6 | Evidencia presentada | ¿Qué evidencia es aceptable para cada tipo de obligación? |
| 7 | Cumplimiento evaluado | ¿Quién aplica qué criterio y con qué información? |
| 8 | No conformidad identificada | ¿Es un incumplimiento, excepción autorizada o reclamo? |
| 9 | Acción correctiva acordada | ¿Quién es responsable y cómo se verifica el cierre? |
| 10 | Reporte de cumplimiento emitido | ¿Qué destinatario, periodo y nivel de detalle corresponden? |

QR, NFC, GPS, foto, sincronización, API, base de datos y notificaciones no son
eventos de dominio en este inventario. Podrán evaluarse posteriormente como
posibles mecanismos o restricciones técnicas.

### 2.3.6. Ubiquitous Language

| Término candidato | Definición de trabajo | Estado |
|---|---|---|
| Service Contract | Acuerdo que establece condiciones del servicio entre organizaciones. | **Candidate — Pending validation** |
| Service Obligation | Unidad de compromiso operativo definida a partir de una condición o planificación de servicio. | **Candidate — Pending validation** |
| Execution | Lo que se realizó —o se intentó realizar— para atender una obligación. | **Candidate — Pending validation** |
| Evidence | Información que respalda una afirmación sobre la ejecución; su aceptabilidad depende del acuerdo y contexto. | **Candidate — Pending validation** |
| Compliance Evaluation | Comparación entre expectativa acordada y resultado disponible. | **Candidate — Pending validation** |
| Non-compliance | Resultado de evaluación que indica que una obligación no alcanzó un criterio aplicable. | **Candidate — Pending validation** |
| Corrective Action | Acción acordada para responder a una no conformidad o reclamo. | **Candidate — Pending validation** |
| Compliance Report | Comunicación consolidada sobre el estado de cumplimiento para un destinatario y periodo. | **Candidate — Pending validation** |

## 2.4. Requirements specification

Los siguientes requisitos son candidatos de aprendizaje derivados de la
hipótesis y el needfinding preliminar. No conforman un backlog comprometido y
no autorizan decidir una interfaz, tecnología o mecanismo de evidencia.

| ID | Necesidad candidata | Capacidad candidata | Trazabilidad | Estado |
|---|---|---|---|---|
| R-01 | Relacionar lo acordado con el trabajo operativo. | Representar condiciones y obligaciones de servicio. | Eventos 1–3; H-01 y H-04. | **Candidate — Pending validation** |
| R-02 | Comunicar y registrar el resultado de una ejecución. | Registrar una ejecución, impedimento o resultado informado. | Eventos 4–5; tarea de ejecución. | **Candidate — Pending validation** |
| R-03 | Sustentar una afirmación sobre ejecución cuando corresponda. | Asociar evidencia definida por el acuerdo o proceso. | Evento 6; evidencia aceptable por investigar. | **Candidate — Pending validation** |
| R-04 | Determinar y explicar cumplimiento. | Evaluar una ejecución frente a un criterio aplicable. | Evento 7; H-01. | **Candidate — Pending validation** |
| R-05 | Gestionar una desviación o reclamo. | Registrar una no conformidad y dar seguimiento a una respuesta. | Eventos 8–9; journey preliminar. | **Candidate — Pending validation** |
| R-06 | Comunicar estado a una parte interesada. | Consolidar un reporte para destinatario y periodo definidos. | Evento 10; tarea de consolidación. | **Candidate — Pending validation** |

Las decisiones sobre fotografía, ubicación, código, sensor, uso sin conexión,
alerta o integración externa se registrarán como requisitos solo si la
investigación, una regla contractual o una restricción académica las sustenta.

### 2.4.1. User Stories

### 2.4.2. Impact Mapping

### 2.4.3. Product Backlog

## 2.5. Strategic-Level Domain-Driven Design

<a id="251-eventstorming"></a>

### 2.5.1. EventStorming

<a id="2511-candidate-context-discovery"></a>
Con el objetivo de comprender a profundidad el dominio de la aplicación Service Compliance, se llevó a cabo una sesión de EventStorming de aproximadamente 2 horas. Esta sesión permitió identificar los eventos clave dentro del sistema, así como actores, comandos, agregados y posibles hotspots (dudas o riesgos del dominio). El enfoque se centró en capturar la mayor cantidad de conocimiento del dominio desde una perspectiva colaborativa, permitiendo así una primera aproximación al modelo general del negocio.

La herramienta utilizada para la sesión fue Miro, que facilitó la colaboración en tiempo real y la organización visual de los eventos. La sesión se dividió en las siguientes etapas:

- **Unstructured Exploration** (exploración sin estructura)
- **Timelines** (flujo del negocio)
- **Pain Points** (puntos de fricción)

Se identificaron eventos relacionados con el ciclo de vida completo de una obligación de servicio, desde el registro del contrato hasta la generación del reporte de cumplimiento, incluyendo actividades complementarias como la captura de evidencia en campo, la detección de incumplimientos y la gestión de incidencias.

#### Step 1: Unstructured Exploration

Lluvia de ideas con eventos importantes dentro del dominio de Service Compliance, organizados por área funcional para facilitar su posterior análisis: Cuenta/Sesión, Contrato/Obligación, Ejecución/Evidencia, Cumplimiento/SLA, Incidencia/Acción Correctiva, y Reportes/Notificaciones.

<img src="resources/10-chapter-01/step1.png">

#### Step 2: Timelines

Organización de los eventos identificados en el Step 1 en flujos funcionales secuenciales, incluyendo escenarios alternativos como el registro de evidencia sin conexión y la bifurcación entre obligaciones cumplidas a tiempo y obligaciones vencidas que derivan en incidencias.

<img src="resources/10-chapter-01/step2.png">

#### Step 3: Pain Points

Identificación de puntos conflictivos o dolorosos en la experiencia de los usuarios (operarios y supervisores), incluyendo problemas de conectividad al capturar evidencia, ambigüedad en la interpretación del plazo del SLA, y riesgos de duplicidad de registros al sincronizar ejecuciones offline.

<img src="resources/10-chapter-01/step3.png">

#### 2.5.1.1. Candidate Context Discovery

Con el objetivo de comprender a profundidad el dominio de la aplicación Service Compliance, se llevó a cabo una sesión de EventStorming de aproximadamente 2 horas. Esta sesión permitió identificar los eventos clave, procesos y pain points del dominio.

La herramienta utilizada para la sesión fue Miro, que facilitó la colaboración en tiempo real y la organización visual de los eventos. La sesión se dividió en las siguientes etapas:

- **Unstructured Exploration** (exploración sin estructura)
- **Timelines** (flujo del negocio)
- **Pain Points** (puntos de fricción)

Se identificaron eventos relacionados con el ciclo de vida completo de una obligación de servicio, desde el registro del contrato hasta la generación del reporte de cumplimiento, incluyendo actividades de ejecución y verificación.

##### Step 1: Unstructured Exploration

Lluvia de ideas con eventos importantes dentro del dominio de Service Compliance, organizados por área funcional para facilitar su posterior análisis: Cuenta/Sesión, Contrato/Obligación, Ejecución, Evidencia, Incumplimiento e Incidencia.

<img src="resources/10-chapter-01/step1.png">

##### Step 2: Timelines

Organización de los eventos identificados en el Step 1 en flujos funcionales secuenciales, incluyendo escenarios alternativos como el registro de evidencia sin conexión y la bifurcación entre obligaciones regulares y obligaciones de emergencia.

<img src="resources/10-chapter-01/step2.png">

##### Step 3: Pain Points

Identificación de puntos conflictivos o dolorosos en la experiencia de los usuarios (operarios y supervisores), incluyendo problemas de conectividad al capturar evidencia, ambigüedad en la interpretación de obligaciones y retraso en la consolidación de reportes.

<img src="resources/10-chapter-01/step3.png">

<a id="2512-domain-message-flows-modeling"></a>

#### 2.5.1.2. Domain Message Flows Modeling

A partir del EventStorming general, se realizó una segunda sesión enfocada en identificar los Candidate Bounded Contexts, aplicando las técnicas de start-with-value y look-for-pivotal-events sobre los eventos identificados. Se definieron cinco Candidate Bounded Contexts:

**Authentication:**

Gestiona la información y operaciones relacionadas con el registro, inicio de sesión y perfil de los usuarios del sistema (operarios y supervisores).

<img src="resources/10-chapter-01/Authentication.png">

**Contract & Obligation Management:**

Gestiona la información y operaciones relacionadas con los contratos de servicio y las obligaciones operativas derivadas de ellos, incluyendo su registro y asignación a los operarios de campo.

<img src="resources/10-chapter-01/contract.png">

**Field Execution & Evidence:**

Gestiona la ejecución de obligaciones en campo y la captura de evidencia asociada (foto, código QR, ubicación), incluyendo el soporte de registro sin conexión y su posterior sincronización. Constituye el core domain de la solución.

<img src="resources/10-chapter-01/fieldExecution.png">

**Incident & Corrective Action:**

Gestiona la evaluación del cumplimiento de SLA, la detección de incumplimientos, y el ciclo de vida de las incidencias generadas junto con sus acciones correctivas asignadas por el supervisor.

<img src="resources/10-chapter-01/incidentCorrective.png">

**Compliance Reporting:**

Gestiona la consolidación de información proveniente de los demás contextos para la generación de reportes de cumplimiento e indicadores, así como el envío de notificaciones automáticas de vencimientos y cambios de estado.

<img src="resources/10-chapter-01/CompilanceReporting.png">

Con el fin de visualizar cómo colaboran los Bounded Contexts identificados para resolver los casos de uso principales del negocio, se aplicó la técnica de Domain Storytelling. A continuación, se presentan los flujos de interacción:

**Authentication:**

Representa el flujo de registro e inicio de sesión del usuario en el sistema.

<img src="resources/10-chapter-01/FlujoAutenticacion.png">

**Field Execution & Evidence:**

Representa el flujo mediante el cual un operario consulta su obligación asignada, ejecuta el servicio y registra la evidencia correspondiente, incluyendo el escenario de registro sin conexión.

<img src="resources/10-chapter-01/FlujoEjecucionObligacion.png">

**Incident & Corrective Action:**

Representa el flujo mediante el cual el sistema evalúa automáticamente el cumplimiento del SLA, genera una incidencia ante un incumplimiento, y el supervisor revisa y asigna una acción correctiva.

<img src="resources/10-chapter-01/DeteccionIncumplimiento.png">

**Compliance Reporting:**

Representa el flujo mediante el cual el supervisor solicita un reporte de cumplimiento, el cual es generado consolidando información proveniente de los contextos de Field Execution & Evidence e Incident & Corrective Action.

<img src="resources/10-chapter-01/GeneracionReporte.png">

**Flujo General:**

Representa la interacción y el flujo de información entre los diferentes Bounded Contexts del sistema, evidenciando cómo Authentication habilita el acceso, Contract & Obligation Management origina las obligaciones, Field Execution & Evidence registra la ejecución, Incident & Corrective Action gestiona las desviaciones e Incident & Corrective Action consolida la información.

<img src="resources/10-chapter-01/FlujoGeneral.png">

<a id="2513-bounded-context-canvases"></a>

#### 2.5.1.3. Bounded Context Canvases

Para cada uno de los Bounded Contexts candidatos identificados, se elaboró un Bounded Context Canvas siguiendo un proceso iterativo de Context Overview Definition, Business Rules Distillation & Ubiquitous Language Definition, según las prácticas de Domain-Driven Design. A continuación, se presentan los canvases elaborados:

**Authentication:**

Gestiona la identificación, verificación y autorización de operarios y supervisores dentro del sistema.

<img src="resources/10-chapter-01/bc1.png">

**Contract & Obligation Management:**

Gestiona el registro de contratos de servicio y la traducción de sus condiciones en obligaciones operativas.

<img src="resources/10-chapter-01/bc2.png">

**Field Execution & Evidence:**

Core domain de la solución. Gestiona la ejecución de obligaciones en campo y la captura de evidencia, incluyendo soporte offline.

<img src="resources/10-chapter-01/bc3.png">

**Incident & Corrective Action:**

Gestiona la evaluación de SLA, detección de incumplimientos y el ciclo de vida de incidencias y acciones correctivas.

<img src="resources/10-chapter-01/bc4.png">

**Compliance Reporting:**

Consolida información de los demás contextos para la generación de reportes de cumplimiento y notificaciones.

<img src="resources/10-chapter-01/bc5.png">

<a id="252-context-mapping"></a>

### 2.5.2. Context Mapping

<a id="2521-context-mapping-process"></a>

#### 2.5.2.1. Context Mapping Process

A partir de los Bounded Context Canvases elaborados, el equipo desarrolló un Context Map para visualizar las relaciones estructurales entre los contextos identificados, aplicando los patrones de relación descritos por Newman (2015): Customer/Supplier, Partnership, Shared Kernel, Conformist, Anti-Corruption Layer y Open Host Service.

Durante el proceso se discutieron alternativas de diseño, entre ellas: mover la evaluación de SLA desde Field Execution & Evidence hacia Incident & Corrective Action (descartado por generar dependencias circulares), consolidar Authentication y Contract & Obligation Management (descartado para mantener separación de intereses) e implementar una anti-corruption layer entre los contextos (descartado en favor de una arquitectura más simple en la fase inicial).

Como resultado de esta discusión, se estableció el siguiente Context Map:

- **Authentication → Contract & Obligation Management** (Customer/Supplier): Contract & Obligation depende de la identidad y rol validados por Authentication.
- **Authentication → Field Execution & Evidence** (Customer/Supplier): el operario debe estar autenticado antes de ejecutar una obligación.
- **Contract & Obligation Management → Field Execution & Evidence** (Customer/Supplier): la obligación debe existir antes de poder ser ejecutada.
- **Field Execution & Evidence ↔ Incident & Corrective Action** (Partnership): ambos contextos evolucionan de forma coordinada, dado que un cambio en el registro de evidencia impacta directamente en la evaluación de cumplimiento.
- **Field Execution & Evidence e Incident & Corrective Action → Open Host Service → Compliance Reporting**: Compliance Reporting consume información consolidada de ambos contextos mediante un lenguaje de integración neutral.

<img src="resources/10-chapter-01/ContextMapping.png">

<a id="253-software-architecture"></a>

### 2.5.3. Software Architecture

<a id="2531-software-architecture-context-level-diagrams"></a>

#### 2.5.3.1. Software Architecture Context Level Diagrams

Aplicando el C4 Model, el equipo elaboró la representación de la arquitectura de software de la solución, utilizando Structurizr como herramienta de Diagram-as-Code (Structurizr DSL).

##### Context Diagram

El Context Diagram muestra el sistema Service Compliance como una caja central, rodeado de sus usuarios (Operario de campo y Supervisor) y los sistemas externos con los que interactúa (Servicio de Notificaciones).

El Operario de campo utiliza el sistema para consultar sus obligaciones asignadas, ejecutar el servicio y registrar evidencia. El Supervisor lo utiliza para supervisar el cumplimiento, gestionar incidencias y consultar reportes de cumplimiento.

<img src="resources/10-chapter-01/ContextDiagram1.png">

<a id="2532-software-architecture-container-level-diagrams"></a>

#### 2.5.3.2. Software Architecture Container Level Diagrams

##### Container Diagram

El Container Diagram muestra los elementos de alto nivel de la arquitectura de software de Service Compliance y cómo se distribuyen las responsabilidades entre ellos. La solución está compuesta por una Mobile App (frontend), una API REST (backend), una base de datos relacional y servicios externos de notificación.

La Mobile App se comunica con la API REST mediante peticiones HTTPS/JSON, mientras que la API REST se comunica con dos servicios externos: un servicio de notificaciones para alertar sobre obligaciones vencidas y un servicio de ubicación para validar geolocalización en tiempo real.

<img src="resources/10-chapter-01/ContextDiagram2.png">

<a id="2533-software-architecture-deployment-diagrams"></a>

#### 2.5.3.3. Software Architecture Deployment Diagrams

##### Deployment Diagram

El Deployment Diagram muestra la distribución física de los componentes del sistema Service Compliance sobre la infraestructura de hardware. La Mobile App se ejecuta en el dispositivo móvil del operario y del supervisor, la API REST se ejecuta en un servidor en la nube, y la base de datos se ejecuta en una instancia administrada en la nube.

<img src="resources/10-chapter-01/ContextDiagram3.png">

<img src="resources/10-chapter-01/ContextDiagram3.png">
2.6. Tactical-Level Domain-Driven Design

<a id="26x-bounded-context"></a>

2.6.x. Bounded Context: <Bounded Context Name>

<a id="26x1-domain-layer"></a>

2.6.x.1. Domain Layer

<a id="26x2-interface-layer"></a>

2.6.x.2. Interface Layer

<a id="26x3-application-layer"></a>

2.6.x.3. Application Layer

<a id="26x4-infrastructure-layer"></a>

2.6.x.4. Infrastructure Layer

<a id="26x5-bounded-context-software-architecture-component-level-diagrams"></a>

2.6.x.5. Bounded Context Software Architecture Component Level Diagrams

<a id="26x6-bounded-context-software-architecture-code-level-diagrams"></a>

2.6.x.6. Bounded Context Software Architecture Code Level Diagrams

<a id="26x61-bounded-context-domain-layer-class-diagrams"></a>

2.6.x.6.1. Bounded Context Domain Layer Class Diagrams

<a id="26x62-bounded-context-database-design-diagram"></a>

2.6.x.6.2. Bounded Context Database Design Diagram

<div style="page-break-before: always;"></div>

<a id="capitulo-iii-solution-uiux-design"></a>

