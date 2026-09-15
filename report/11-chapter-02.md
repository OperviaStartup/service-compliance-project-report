Capítulo II: Requirements Development and Software Solution Design

<a id="21-competidores"></a>

2.1. Competidores

<a id="211-analisis-competitivo"></a>

2.1.1. Análisis competitivo

<a id="212-estrategias-y-tacticas-frente-a-competidores"></a>

2.1.2. Estrategias y tácticas frente a competidores

<a id="22-entrevistas"></a>

2.2. Entrevistas

<a id="221-diseno-de-entrevistas"></a>

2.2.1. Diseño de entrevistas

<a id="222-registro-de-entrevistas"></a>

2.2.2. Registro de entrevistas

<a id="223-analisis-de-entrevistas"></a>

2.2.3. Análisis de entrevistas

<a id="23-needfinding"></a>

2.3. Needfinding

<a id="231-user-personas"></a>

2.3.1. User Personas

<a id="232-user-task-matrix"></a>

2.3.2. User Task Matrix

<a id="233-user-journey-mapping"></a>

2.3.3. User Journey Mapping

<a id="234-empathy-mapping"></a>

2.3.4. Empathy Mapping

<a id="235-big-picture-eventstorming"></a>

2.3.5. Big Picture EventStorming

<a id="236-ubiquitous-language"></a>

2.3.6. Ubiquitous Language

<a id="24-requirements-specification"></a>

2.4. Requirements specification

<a id="241-user-stories"></a>

2.4.1. User Stories

<a id="242-impact-mapping"></a>

2.4.2. Impact Mapping

<a id="243-product-backlog"></a>

2.4.3. Product Backlog

<a id="25-strategic-level-domain-driven-design"></a>

2.5. Strategic-Level Domain-Driven Design

<a id="251-eventstorming"></a>

2.5.1. EventStorming

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


2.5.1.1. Candidate Context Discovery

<a id="2512-domain-message-flows-modeling"></a>
A partir del EventStorming general, se realizó una segunda sesión enfocada en identificar los Candidate Bounded Contexts, aplicando las técnicas de start-with-value y look-for-pivotal-events sobre los eventos, actores y agregados identificados previamente.

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

Gestiona la consolidación de información proveniente de los demás contextos para la generación de reportes de cumplimiento e indicadores, así como el envío de notificaciones automáticas de vencimiento.

<img src="resources/10-chapter-01/CompilanceReporting.png">

2.5.1.2. Domain Message Flows Modeling

<a id="2513-bounded-context-canvases"></a>
Con el fin de visualizar cómo colaboran los Bounded Contexts identificados para resolver los casos de uso principales del negocio, se aplicó la técnica de Domain Storytelling. A continuación, se presentan los flujos modelados:

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

Representa la interacción y el flujo de información entre los diferentes Bounded Contexts del sistema, evidenciando cómo Authentication habilita el acceso, Contract & Obligation Management origina las obligaciones, Field Execution & Evidence las ejecuta y captura evidencia, Incident & Corrective Action gestiona las excepciones, y Compliance Reporting consolida la información de los demás contextos para la generación de reportes.

<img src="resources/10-chapter-01/FlujoGeneral.png">


2.5.1.3. Bounded Context Canvases

<a id="252-context-mapping"></a>
Para cada uno de los Bounded Contexts candidatos identificados, se elaboró un Bounded Context Canvas siguiendo un proceso iterativo de Context Overview Definition, Business Rules Distillation & Ubiquitous Language Capture, Capability Analysis, Dependencies Capture y Design Critique. Los contextos se abordaron en orden de importancia, priorizando el core domain de la solución.

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

2.5.2. Context Mapping

<a id="253-software-architecture"></a>
A partir de los Bounded Context Canvases elaborados, el equipo desarrolló un Context Map para visualizar las relaciones estructurales entre los contextos identificados, aplicando los patrones de relación establecidos en Domain-Driven Design.

Durante el proceso se discutieron alternativas de diseño, entre ellas: mover la evaluación de SLA desde Field Execution & Evidence hacia Incident & Corrective Action (descartado por generar dependencia circular, dado que el SLA se evalúa sobre datos que ya posee Field Execution), la creación de un shared service entre Field Execution e Incident para reducir duplicación (descartado por el momento, dado el alcance del proyecto), y el consumo directo de Compliance Reporting hacia cada context individual sin un Open Host Service intermedio (descartado por generar alto acoplamiento ante cambios internos de cada context).

Como resultado de esta discusión, se estableció el siguiente Context Map:

- **Authentication → Contract & Obligation Management** (Customer/Supplier): Contract & Obligation depende de la identidad y rol validados por Authentication.
- **Authentication → Field Execution & Evidence** (Customer/Supplier): el operario debe estar autenticado antes de ejecutar una obligación.
- **Contract & Obligation Management → Field Execution & Evidence** (Customer/Supplier): la obligación debe existir antes de poder ser ejecutada.
- **Field Execution & Evidence ↔ Incident & Corrective Action** (Partnership): ambos contextos evolucionan de forma coordinada, dado que un cambio en el registro de evidencia impacta directamente en la detección de incumplimientos.
- **Field Execution & Evidence e Incident & Corrective Action → Open Host Service → Compliance Reporting**: Compliance Reporting consume información consolidada de ambos contextos mediante un lenguaje publicado y estable, evitando el acoplamiento directo.

<img src="resources/10-chapter-01/ContextMapping.png">
2.5.3. Software Architecture

<a id="2531-software-architecture-context-level-diagrams"></a>
Aplicando el C4 Model, el equipo elaboró la representación de la arquitectura de software de la solución, utilizando Structurizr como herramienta de Diagram-as-Code (Structurizr DSL).

#### 2.5.3.1. Software Architecture Context Level Diagrams

El Context Diagram muestra el sistema Service Compliance como una caja central, rodeado de sus usuarios (Operario de campo y Supervisor) y los sistemas externos con los que interactúa (Servicio de Notificaciones y Servicio de Almacenamiento).

El Operario de campo utiliza el sistema para consultar sus obligaciones asignadas, ejecutar el servicio y registrar evidencia. El Supervisor lo utiliza para supervisar el cumplimiento, gestionar incidencias y consultar reportes. El sistema se apoya en un servicio externo de notificaciones push para alertar sobre obligaciones próximas a vencer, y en un servicio externo de almacenamiento en la nube para conservar las evidencias fotográficas capturadas en campo.

<img src="resources/10-chapter-01/ContextDiagram1.png">

2.5.3.2. Software Architecture Container Level Diagrams

<a id="2533-software-architecture-deployment-diagrams"></a>
El Container Diagram muestra los elementos de alto nivel de la arquitectura de software de Service Compliance y cómo se distribuyen las responsabilidades entre ellos. La solución está compuesta por un Landing Page (sitio web estático que presenta el modelo de negocio), una Mobile App (utilizada por operarios y supervisores para interactuar con el sistema), una API REST (que centraliza la lógica de negocio de los cinco Bounded Contexts identificados: Authentication, Contract & Obligation Management, Field Execution & Evidence, Incident & Corrective Action y Compliance Reporting), y una Base de Datos que almacena la información del dominio.

La Mobile App se comunica con la API REST mediante peticiones HTTPS/JSON, mientras que la API REST se comunica con dos servicios externos: un servicio de notificaciones para alertar sobre obligaciones próximas a vencer, y un servicio de almacenamiento en la nube para conservar las evidencias fotográficas capturadas por los operarios.

<img src="resources/10-chapter-01/ContextDiagram2.png">

2.5.3.3. Software Architecture Deployment Diagrams

<a id="26-tactical-level-domain-driven-design"></a>
#### 2.5.3.3. Software Architecture Deployment Diagrams

El Deployment Diagram muestra la distribución física de los componentes del sistema Service Compliance sobre la infraestructura de hardware. La Mobile App se ejecuta en el dispositivo móvil del operario o supervisor. El Landing Page se despliega como sitio estático en un servicio de hosting (GitHub Pages / Vercel). La API REST y la Base de Datos se despliegan en un proveedor de servicios en la nube (Railway), permitiendo su acceso público según lo requerido por el enunciado del curso. Adicionalmente, el sistema se apoya en Firebase para los servicios externos de notificaciones y almacenamiento de evidencias.

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

