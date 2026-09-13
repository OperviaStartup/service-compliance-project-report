<a id="capitulo-i-presentacion"></a>

# Capítulo I: Presentación

<a id="11-startup-profile"></a>

## 1.1. Startup Profile

<a id="111-descripcion-de-la-startup"></a>

### 1.1.1. Descripción de la Startup

**Opervia** es una startup de software orientada al desarrollo de soluciones digitales para la gestión operativa, verificación y evidencia del cumplimiento de servicios tercerizados ejecutados en instalaciones físicas de empresas clientes.

Su producto principal, **Service Compliance**, está diseñado para el dominio de los servicios de limpieza tercerizada en Perú. La solución relaciona las condiciones establecidas en un contrato de servicio con obligaciones operativas concretas, ejecuciones realizadas en campo, evidencias y resultados de cumplimiento.

El producto se desarrolla sobre la base directa del repositorio existente `attendance-system`, cuya estructura y componentes serán adaptados al dominio de cumplimiento de servicios tercerizados. La evolución del producto incorporará la gestión de obligaciones contractuales, el registro de ejecuciones, la captura de evidencias, la supervisión de incidencias y la consulta de información de cumplimiento.

Service Compliance no es un gestor genérico de tareas. Cada obligación operativa tiene como origen una condición del servicio contratado y se relaciona con una frecuencia, una ventana horaria, una ubicación, un responsable, un estándar de ejecución y, cuando corresponda, un nivel de evidencia.

La cadena principal de la solución es:

> **Service Contract → Service Obligation → Execution → Evidence → SLA Evaluation → Non-compliance → Corrective Action → Compliance Report**

El alcance funcional de Service Compliance comprende:

- gestión de obligaciones de servicios de limpieza tercerizada;
- consulta de obligaciones asignadas;
- registro móvil de ejecuciones;
- captura de evidencias;
- registro y seguimiento de incidencias;
- supervisión de obligaciones pendientes o vencidas;
- gestión de acciones correctivas;
- consulta de indicadores y reportes de cumplimiento;
- almacenamiento local y sincronización con servicios RESTful.

La solución será implementada como una experiencia integrada compuesta por una aplicación móvil, servicios RESTful y un Landing Page. Su diseño seguirá un enfoque de Domain-Driven Design y cumplirá con los requerimientos tecnológicos establecidos para el curso 1ACC0238.

<a id="112-perfiles-de-integrantes-del-equipo"></a>

### 1.1.2. Perfiles de integrantes del equipo

La startup Opervia estará conformada por los integrantes responsables del análisis, diseño, desarrollo, validación y documentación de Service Compliance. La información se organizará con el formato requerido para el informe:

| N.° | Apellidos y nombres | Código | Carrera | Rol en Opervia | Conocimientos y aporte al proyecto |
|---:|---|---|---|---|---|
| 1 | Por completar | Por completar | Por completar | Por completar | Por completar |
| 2 | Por completar | Por completar | Por completar | Por completar | Por completar |
| 3 | Por completar | Por completar | Por completar | Por completar | Por completar |
| 4 | Por completar | Por completar | Por completar | Por completar | Por completar |

Los perfiles deberán complementarse con la fotografía de cada participante, sus nombres y apellidos, código de estudiante, carrera profesional y un resumen de sus conocimientos técnicos y habilidades aplicables al proyecto.

<a id="12-solution-profile"></a>

## 1.2. Solution Profile

<a id="121-antecedentes-y-problematica"></a>

### 1.2.1. Antecedentes y problemática

Las empresas proveedoras de servicios tercerizados deben ejecutar actividades físicas conforme a condiciones establecidas en contratos comerciales. En el caso de la limpieza tercerizada, estas condiciones pueden incluir frecuencias de atención, horarios, ubicaciones, estándares de calidad, inspecciones y tiempos máximos para resolver incidencias.

La operación requiere coordinación entre los operarios que ejecutan el servicio y los supervisores que controlan su cumplimiento. El operario debe conocer las obligaciones que debe ejecutar y registrar la información correspondiente. El supervisor debe revisar el avance, identificar desviaciones y gestionar las acciones correctivas necesarias.

La problemática abordada por Service Compliance es la falta de trazabilidad integrada entre las condiciones contractuales, las obligaciones operativas, la ejecución realizada en campo y la evidencia del cumplimiento. Cuando esta información se gestiona mediante registros manuales o canales separados, se dificulta conocer oportunamente el estado real del servicio, consolidar evidencias y responder ante incumplimientos o reclamos.

Los principales problemas que resuelve la propuesta son:

1. dificultad para relacionar una actividad de campo con la obligación contractual que la origina;
2. limitada visibilidad sobre obligaciones pendientes, vencidas o incumplidas;
3. dispersión de evidencias en distintos medios de comunicación;
4. retraso en la identificación y atención de incidencias;
5. esfuerzo elevado para consolidar reportes de cumplimiento;
6. dificultad para demostrar objetivamente la ejecución del servicio;
7. ausencia de un historial integrado de ejecuciones, evidencias e incidencias.

En respuesta a esta problemática, Service Compliance centraliza el ciclo operativo de cumplimiento mediante una solución móvil conectada con servicios RESTful. El sistema permite registrar la ejecución de obligaciones, asociar evidencias, identificar incumplimientos y realizar seguimiento a las acciones correctivas.

#### Análisis 5W+2H

| Elemento | Aplicación al proyecto |
|---|---|
| **Who** | Operarios y supervisores que participan en la ejecución y control de servicios de limpieza tercerizada. |
| **What** | Gestión, ejecución, verificación y seguimiento de obligaciones contractuales de limpieza. |
| **Where** | Instalaciones físicas de las empresas clientes donde se ejecuta el servicio. |
| **When** | Durante las frecuencias, turnos y ventanas horarias definidas para cada obligación. |
| **Why** | Para mejorar la trazabilidad del servicio, detectar incumplimientos y facilitar la gestión de evidencias y acciones correctivas. |
| **How** | Mediante una aplicación móvil integrada con servicios RESTful, almacenamiento local, mecanismos de evidencia y módulos de supervisión. |
| **How much** | Mediante indicadores de cumplimiento, tiempo de supervisión, incidencias y consolidación de evidencias definidos durante el proceso de investigación y validación. |

#### Objetivo de la solución

Desarrollar una solución móvil para gestionar y evidenciar el cumplimiento de obligaciones de servicios de limpieza tercerizada, permitiendo a los operarios registrar sus ejecuciones y a los supervisores controlar incidencias, obligaciones vencidas, acciones correctivas y reportes de cumplimiento.

#### Delimitación del alcance

| Criterio | Alcance definido |
|---|---|
| Dominio | Servicios de limpieza tercerizada. |
| Mercado inicial | Empresas y operaciones ubicadas en Perú. |
| Segmentos objetivo | Operarios de campo y supervisores. |
| Producto base | Repositorio `attendance-system`. |
| Aplicación principal | Aplicación móvil para operación y supervisión. |
| Componentes complementarios | Servicios RESTful y Landing Page. |
| Proceso central | Obligación contractual, ejecución, evidencia y cumplimiento. |
| Desarrollo | Ciclo académico del curso 1ACC0238. |
| Exclusiones iniciales | Control de plagas, seguridad, jardinería, mantenimiento y otros verticales de facility management. |

<a id="122-lean-ux-process"></a>

### 1.2.2. Lean UX Process

El proceso Lean UX organiza las decisiones iniciales de Opervia en Problem Statement, Assumptions, Hypothesis Statements y Lean UX Canvas. Estos artefactos permiten relacionar el dominio, los segmentos objetivo, la problemática, la estrategia del producto y los resultados esperados.

La investigación UX se aplicará para sustentar la priorización de funcionalidades y ajustar la experiencia de uso de Service Compliance dentro del alcance definido para limpieza tercerizada.

<a id="1221-lean-ux-problem-statements"></a>

#### 1.2.2.1. Lean UX Problem Statements

##### Problem Statement

> The current state of the outsourced cleaning services domain has focused mainly on executing and supervising physical service activities according to contractual conditions such as frequency, schedule, location and service standards.
>
> What existing operational practices fail to address is the integrated traceability between contractual obligations, field execution, evidence collection, compliance evaluation and corrective actions.
>
> Our product, Service Compliance, will address this gap by transforming service contract conditions into operational obligations and providing a mobile-first workflow for execution registration, evidence capture, incident management and compliance supervision. Our initial focus will be outsourced cleaning services in Peru, with field operators and supervisors as the target user segments.
>
> We’ll know we are successful when operators can register their assigned obligations efficiently, supervisors can identify pending or overdue obligations, and the organization can consult reliable execution evidence and compliance information.

##### Componentes del Problem Statement

| Componente | Definición para Service Compliance |
|---|---|
| Domain | Servicios de limpieza tercerizada ejecutados en instalaciones físicas. |
| Customer segments | Operarios de campo y supervisores. |
| Pain points | Falta de trazabilidad, evidencias dispersas, detección tardía de incumplimientos y consolidación manual de información. |
| Market gap | Ausencia de un flujo integrado entre contrato, obligación, ejecución, evidencia y cumplimiento. |
| Product strategy | Solución móvil conectada a servicios RESTful para registrar, verificar y supervisar obligaciones de servicio. |
| Initial segment | Operarios y supervisores de empresas que ejecutan servicios de limpieza tercerizada en Perú. |
| Success behaviors | Registro oportuno de ejecuciones, consulta de obligaciones, detección de vencimientos y uso de evidencias para supervisión. |

<a id="1222-lean-ux-assumptions"></a>

#### 1.2.2.2. Lean UX Assumptions

##### Business Assumptions

| ID | Assumption |
|---|---|
| BA-01 | Las empresas que prestan servicios de limpieza tercerizada necesitan controlar y demostrar el cumplimiento de sus servicios. |
| BA-02 | La reducción de incumplimientos, reclamos, penalidades y tiempo de supervisión representa valor económico para la organización. |
| BA-03 | Service Compliance se orienta a un modelo B2B con pago recurrente por parte de una empresa proveedora o cliente. |
| BA-04 | La propuesta de valor se concentra en la trazabilidad del servicio y no en la simple creación de tareas. |

##### Business Outcome Assumptions

| ID | Assumption |
|---|---|
| BOA-01 | La solución reduce el tiempo dedicado por los supervisores a consolidar información operativa. |
| BOA-02 | La solución permite detectar obligaciones vencidas antes de que generen reclamos. |
| BOA-03 | La solución mejora la disponibilidad de evidencia para resolver disputas sobre la ejecución. |
| BOA-04 | La solución incrementa la trazabilidad histórica de los servicios ejecutados. |
| BOA-05 | La solución facilita la identificación de sedes, turnos u obligaciones con incumplimientos recurrentes. |

##### User Assumptions

| ID | Assumption |
|---|---|
| UA-01 | El operario de campo ejecuta actividades físicas de limpieza en las instalaciones del cliente. |
| UA-02 | El supervisor coordina, monitorea o revisa la ejecución del servicio. |
| UA-03 | El operario necesita conocer la obligación, ubicación y ventana horaria de cada ejecución. |
| UA-04 | El supervisor necesita identificar desviaciones y gestionar acciones correctivas. |
| UA-05 | Los usuarios utilizan dispositivos móviles como parte de sus actividades operativas o de supervisión. |

##### User Outcome and Benefit Assumptions

| ID | Assumption |
|---|---|
| UBA-01 | El operario busca completar el registro de una ejecución con poca fricción. |
| UBA-02 | El operario necesita registrar únicamente la información necesaria para demostrar el servicio. |
| UBA-03 | El supervisor busca detectar tempranamente obligaciones vencidas o incumplidas. |
| UBA-04 | El supervisor necesita consultar información consolidada sobre el estado de las obligaciones. |
| UBA-05 | Los usuarios valoran reducir la duplicidad de registros y la comunicación dispersa. |

##### Feature Assumptions

| ID | Assumption |
|---|---|
| FA-01 | La aplicación muestra al operario sus obligaciones pendientes, ubicación y ventana horaria. |
| FA-02 | La aplicación permite registrar una ejecución desde el lugar donde se realiza el servicio. |
| FA-03 | La aplicación permite capturar evidencia mediante timestamp, ubicación, QR, NFC o fotografía, según el nivel requerido. |
| FA-04 | El sistema muestra alertas e indicadores para que el supervisor identifique obligaciones pendientes o vencidas. |
| FA-05 | El sistema permite registrar incidencias y acciones correctivas conservando el historial original. |
| FA-06 | El sistema ofrece reportes de cumplimiento agrupados por contrato, sede, turno, ubicación u obligación. |
| FA-07 | La aplicación utiliza almacenamiento local y sincronización posterior para operar con conectividad limitada. |

<a id="1223-lean-ux-hypothesis-statements"></a>

#### 1.2.2.3. Lean UX Hypothesis Statements

La rúbrica solicita un Hypothesis Statement por cada Feature Assumption. Se utiliza el formato: **We believe we will achieve [business outcome] if [personas] attain [benefit] with [feature].**

| ID | Hypothesis Statement |
|---|---|
| HS-01 | We believe we will achieve better visibility of service execution if field operators attain a clear view of their assigned obligations, locations and time windows with a mobile list of contract-originated service obligations. |
| HS-02 | We believe we will achieve more complete execution traceability if field operators attain the ability to register an execution immediately after completing the obligation with a mobile execution flow that requires only the necessary information. |
| HS-03 | We believe we will achieve stronger evidence of service execution if operators and supervisors attain evidence associated with a specific obligation and location with configurable timestamps, location, QR, NFC or photographs. |
| HS-04 | We believe we will achieve earlier detection of operational deviations if supervisors attain visibility of pending, overdue or potentially non-compliant obligations with alerts and compliance indicators. |
| HS-05 | We believe we will achieve more controlled resolution of service deviations if supervisors attain the ability to register incidents, assign responsibility and track corrective actions with an incident workflow that preserves the original execution history. |
| HS-06 | We believe we will achieve better decision-making based on service history if supervisors attain summarized compliance information with reports grouped by contract, site, shift, location or obligation type. |
| HS-07 | We believe we will achieve more reliable field registration if operators working with limited connectivity attain the ability to record executions without an active connection with local storage and later synchronization. |

<a id="1224-lean-ux-canvas"></a>

#### 1.2.2.4. Lean UX Canvas

| Lean UX Canvas | Definition for Service Compliance |
|---|---|
| **Business problem** | Las obligaciones de limpieza tercerizada requieren ejecución y supervisión conforme a condiciones contractuales, pero la información de cumplimiento puede gestionarse de forma dispersa. |
| **Business outcome** | Mejorar la trazabilidad del servicio, reducir retrasos en la detección de incumplimientos y disminuir el esfuerzo de consolidación de evidencias. |
| **Users and customers** | Usuarios: operarios de campo y supervisores. Clientes organizacionales: empresas proveedoras y empresas cliente. |
| **User benefits** | El operario consulta y registra sus obligaciones. El supervisor controla desviaciones, evidencias y acciones correctivas. |
| **Solution ideas** | Aplicación móvil de operación, registro de evidencia, alertas, incidencias, sincronización y reportes de cumplimiento. |
| **Feature assumptions** | Lista de obligaciones, registro móvil, evidencias, alertas, acciones correctivas, reportes y operación con conectividad limitada. |
| **Business assumptions** | Existe una necesidad empresarial de controlar y demostrar el cumplimiento de servicios tercerizados. |
| **Risks** | Variación de condiciones contractuales, resistencia al registro móvil, conectividad limitada y diferencias en los niveles de evidencia requeridos. |
| **What must be true** | Las obligaciones deben poder expresarse como condiciones medibles y los usuarios deben completar el flujo de registro dentro del proceso operativo. |
| **Research questions** | ¿Cómo se traducen los contratos en actividades? ¿Cómo se demuestra la ejecución? ¿Qué evidencia se acepta? ¿Cómo se gestionan los incumplimientos? |
| **Initial experiments** | Entrevistas semiestructuradas, observación del proceso actual, prototipo de registro de obligaciones y prueba de alternativas de evidencia. |
| **Success indicators** | Registro oportuno, reducción del tiempo de supervisión, consulta de obligaciones vencidas, disponibilidad de evidencias y seguimiento de acciones correctivas. |

<a id="13-segmentos-objetivo"></a>

## 1.3. Segmentos objetivo

Service Compliance se dirige inicialmente a dos segmentos objetivo directamente involucrados en la ejecución y control de servicios de limpieza tercerizada: **operarios de campo** y **supervisores**.

<a id="131-operarios-de-campo"></a>

### 1.3.1. Operarios de campo

Los operarios de campo ejecutan físicamente las actividades de limpieza en las instalaciones de la empresa cliente. Constituyen el usuario móvil principal de Service Compliance.

| Aspecto | Descripción del segmento |
|---|---|
| Actividad principal | Ejecutar obligaciones de limpieza en ubicaciones y horarios definidos. |
| Objetivo | Cumplir las obligaciones asignadas y registrar la evidencia correspondiente. |
| Tareas principales | Consultar obligaciones, desplazarse, ejecutar el servicio, registrar la ejecución, adjuntar evidencia y reportar incidencias. |
| Necesidad de información | Obligación, ubicación, frecuencia, ventana horaria, estándar y evidencia requerida. |
| Dispositivo principal | Teléfono móvil utilizado durante la operación de campo. |
| Beneficio esperado | Registrar el servicio de forma rápida, clara y trazable. |
| Problemas que aborda la solución | Registros dispersos, falta de claridad, duplicidad de comunicación y pérdida de evidencia. |

<a id="132-supervisores"></a>

### 1.3.2. Supervisores

Los supervisores coordinan, controlan y verifican la ejecución de los servicios de limpieza tercerizada. Constituyen el segmento encargado del monitoreo operativo.

| Aspecto | Descripción del segmento |
|---|---|
| Actividad principal | Coordinar y verificar el cumplimiento de las obligaciones de servicio. |
| Objetivo | Detectar desviaciones y gestionar acciones correctivas oportunamente. |
| Tareas principales | Revisar obligaciones, identificar vencimientos, verificar evidencias, gestionar incidencias y consultar reportes. |
| Necesidad de información | Estado de ejecución, evidencias, incidencias, responsables, fechas y acciones correctivas. |
| Dispositivo principal | Aplicación móvil y servicios digitales de supervisión. |
| Beneficio esperado | Obtener visibilidad centralizada y actuar antes de un reclamo. |
| Problemas que aborda la solución | Consolidación manual, detección tardía, información fragmentada y falta de historial. |

<a id="133-organizaciones-relacionadas"></a>

### 1.3.3. Organizaciones relacionadas

Los segmentos objetivo forman parte de dos organizaciones principales:

| Organización | Relación con Service Compliance |
|---|---|
| **Empresa proveedora** | Ejecuta y supervisa el servicio tercerizado. Puede adquirir la solución para controlar operaciones, evidencias e indicadores. |
| **Empresa cliente** | Contrata o recibe el servicio y establece las condiciones que deben cumplirse. Puede utilizar reportes y evidencias para verificar el servicio. |

La aplicación se concentra inicialmente en los usuarios operativos, porque son quienes ejecutan, registran y controlan directamente el servicio. La información producida por estos usuarios se utilizará para generar reportes destinados a responsables de operaciones y representantes de las organizaciones relacionadas.

<a id="134-plan-de-investigacion-ux"></a>

### 1.3.4. Plan de investigación UX

De acuerdo con el enunciado del curso, se realizarán entre tres y cinco entrevistas por segmento objetivo:

| Segmento | Cantidad requerida | Propósito |
|---|---:|---|
| Operarios de campo | 3 a 5 entrevistas | Identificar tareas, herramientas, dificultades, evidencia utilizada y condiciones de operación. |
| Supervisores | 3 a 5 entrevistas | Identificar actividades de coordinación, monitoreo, gestión de incidencias y elaboración de reportes. |

Las entrevistas permitirán sustentar la elaboración posterior de User Personas, User Task Matrix, User Journey Maps, Empathy Maps, Needfinding y requisitos. Los resultados se incorporarán en las secciones correspondientes del informe y se relacionarán con las decisiones de diseño y priorización del Product Backlog.

<div style="page-break-before: always;"></div>

<a id="capitulo-ii-requirements-development-and-software-solution-design"></a>
