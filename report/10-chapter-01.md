<a id="capitulo-i-presentacion"></a>

# Capítulo I: Presentación

<a id="11-startup-profile"></a>

## 1.1. Startup Profile

<a id="111-descripcion-de-la-startup"></a>

### 1.1.1. Descripción de la Startup

**Opervia** es una startup académica orientada al diseño de soluciones digitales para la gestión y trazabilidad del cumplimiento de servicios tercerizados. El proyecto toma como dominio inicial los **servicios de limpieza tercerizada B2B en el Perú**, donde una empresa prestadora ejecuta actividades en instalaciones de una organización cliente y debe coordinar personas, condiciones de servicio, supervisión y resultados.

El Instituto Nacional de Estadística e Informática (INEI) clasifica la **limpieza general de edificios** en la clase CIIU 8121, que comprende la limpieza general no especializada de oficinas, fábricas, comercios, instituciones y otros establecimientos. En enero de 2026, el INEI reportó además que este rubro creció por la ampliación de contratos de limpieza integral en centros comerciales, hospitales, plantas industriales y almacenes, lo que evidencia la presencia de este tipo de servicio en distintos entornos organizacionales (INEI, 2026a; INEI, s. f.).

A partir de este dominio, Opervia propone **Service Compliance**, un producto cuyo propósito es mantener una relación trazable entre aquello que debe cumplirse dentro de un servicio y aquello que realmente ocurre durante su ejecución. Su modelo conceptual inicial se resume en la siguiente cadena:

> **Service Contract → Service Obligation → Execution → Evidence → Compliance Evaluation → Non-compliance → Corrective Action → Compliance Report**

La cadena representa el modelo de solución que el equipo busca validar y desarrollar. No presupone que todo contrato pueda transformarse automáticamente en obligaciones operativas ni que todas las actividades requieran el mismo mecanismo de evidencia. Estas reglas dependen del servicio, del acuerdo entre las organizaciones y del resultado de la investigación con los segmentos objetivo.

Service Compliance no se plantea como un gestor genérico de tareas. Su propuesta consiste en que una actividad operativa conserve el contexto del compromiso de servicio que la origina, el resultado de su ejecución y los elementos necesarios para explicar posteriormente su estado de cumplimiento.

**Misión.** Facilitar que los equipos responsables de servicios tercerizados relacionen de forma clara los compromisos operativos, su ejecución y la evidencia necesaria para comprender el estado de cumplimiento del servicio.

**Visión.** Convertir a Opervia en una alternativa digital especializada para la gestión del cumplimiento de servicios tercerizados, iniciando en limpieza y extendiendo el modelo únicamente cuando las necesidades y reglas del dominio hayan sido validadas.

**Propuesta de valor inicial.** Permitir a supervisores y operarios de servicios de limpieza trabajar sobre una misma referencia operativa, registrar lo ocurrido en campo y conservar una trazabilidad que facilite la supervisión, la atención de desviaciones y la explicación del cumplimiento.

<a id="112-perfiles-de-integrantes-del-equipo"></a>

### 1.1.2. Perfiles de integrantes del equipo

El equipo de Opervia reúne conocimientos de análisis de requisitos, desarrollo de software, modelado de dominio, arquitectura e integración de aplicaciones. La composición del equipo se presenta a continuación.

| N.° | Integrante                             | Código     | Carrera                | Fotografía                                             | Principales conocimientos y aportes                                                                                                                                                                                                                                                                                                                                                                    |
| --: | -------------------------------------- | ---------- | ---------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|   1 | Arias Tasayco, Jean Pool Alexander     | U202414054 | Ingeniería de Software | ![Participante Jean](resources/10-chapter-01/jean.jpg) | Cuenta con conocimientos en desarrollo de software, programación, bases de datos, diseño de APIs REST y control de versiones con Git/GitHub. Aporta al proyecto en el análisis de requisitos, definición de la arquitectura de la solución, modelado del dominio, desarrollo del backend y aplicaciones móviles, así como en la integración y validación de las funcionalidades de Service Compliance. |
|   2 | Ayasta Martel, Zayd Jaffar             | U202410837 | Ingeniería de Software |                                                        | Cuenta con conocimientos en especificación de requisitos, gestión de producto y desarrollo de software. Aporta en la elaboración de las User Stories, el Impact Mapping y el Product Backlog, así como en la revisión de la coherencia del modelo de solución de Service Compliance.                                                                                                                     |
|   3 | Blancas Chávez, Carlos Franco          | U20241A322 | Ingeniería de Software |                                                        | Posee conocimientos en arquitectura de software, modelado de dominio y metodologías ágiles. Aporta en el diseño a nivel estratégico del Domain-Driven Design (EventStorming, Context Mapping y arquitectura C4) y en la coordinación del modelado táctico de los Bounded Contexts de la solución.                                                                                                          |
|   4 | Flores Eusebio, Angel Thyago           | U20231B781 | Ingeniería de Software |                                                        | Cuenta con conocimientos en análisis competitivo, investigación de mercado y estrategia de producto. Aporta en la identificación y análisis de los competidores de Service Compliance y en la definición de estrategias y tácticas frente a los mismos.                                                                                                                                                    |
|   5 | Montes Maza, Augusto Sebastian         | U202218645 | Ingeniería de Software |                                                        | Posee conocimientos en investigación de usuarios y diseño de experiencia (UX). Aporta en la elaboración de los artefactos de Needfinding: User Personas, User Task Matrix, User Journey Mapping, Empathy Mapping, Big Picture EventStorming y Ubiquitous Language.                                                                      |
|   6 | Sánchez Espinoza, Mathias Enrique      | U20231C524 | Ingeniería de Software |                                                        | Cuenta con conocimientos en UX Research y diseño de investigaciones con usuarios. Aporta en el diseño y la conducción de las entrevistas dirigidas a los segmentos objetivo de Operarios de Campo y Supervisores, base de la investigación para Service Compliance.                                                                         |


<a id="12-solution-profile"></a>

## 1.2. Solution Profile

<a id="121-antecedentes-y-problematica"></a>

### 1.2.1. Antecedentes y problemática

La prestación de servicios de limpieza en edificios forma parte de las actividades de servicios administrativos y de apoyo. El INEI define la clase CIIU 8121 como la limpieza general de oficinas, fábricas, comercios, instituciones y otros establecimientos. Esta actividad puede desarrollarse dentro de múltiples tipos de instalaciones y bajo contratos de servicio entre organizaciones (INEI, s. f.).

El contexto laboral también evidencia la relevancia de las ocupaciones vinculadas al dominio. La Encuesta de Demanda Ocupacional del Ministerio de Trabajo y Promoción del Empleo (MTPE) ubicó a los **limpiadores y asistentes de oficinas, hoteles y otros establecimientos** entre las ocupaciones con mayor demanda de puestos permanentes para 2023. Para el conjunto de nuevos puestos permanentes analizados por la encuesta, 72,5 % requería experiencia laboral, 99,1 % al menos una habilidad digital y 45,5 % como mínimo secundaria completa (MTPE, 2023a). Estas cifras describen el contexto de contratación formal estudiado por la EDO y no deben interpretarse como características exclusivas de todos los trabajadores de limpieza.

En Lima Metropolitana, la misma Encuesta de Demanda Ocupacional proyectó para 2023 una demanda de **2 530 trabajadores** para la ocupación de limpiadores y asistentes de oficinas, hoteles y otros establecimientos dentro de los puestos cuyo nivel educativo mínimo requerido era secundaria completa (MTPE, 2023b). Asimismo, el Informe Trimestral del Mercado Laboral del MTPE reportó para el primer trimestre de 2024 un promedio de **49 653 trabajadores formales privados** en esta ocupación; entre los registros con característica identificada, 55 % correspondía a mujeres y 37 % a hombres, 64 % a adultos de 30 a 59 años y 20 % a jóvenes de 15 a 29 años. El mismo informe clasificó al 98 % como trabajadores no calificados según su metodología ocupacional (MTPE, 2024).

El problema abordado por Opervia no es la actividad de limpieza en sí misma, sino la **trazabilidad del cumplimiento de un servicio tercerizado**. En una relación B2B, una organización cliente espera que determinadas condiciones de servicio se cumplan, mientras que la organización prestadora debe convertir esas condiciones en trabajo operativo, coordinar personas, supervisar resultados y atender desviaciones. El proyecto parte de la hipótesis de que, cuando la información relacionada con el servicio queda distribuida entre contratos, cronogramas, instrucciones, mensajes, registros de campo y reportes, puede resultar costoso reconstruir qué debía ocurrir, qué ocurrió realmente y qué evidencia existe para sustentar una evaluación de cumplimiento.

La problemática se analiza mediante la técnica **5W+2H** para delimitar el dominio sin convertir assumptions en resultados empíricos.

#### Análisis 5W+2H

| Dimensión | Análisis para Service Compliance |
|---|---|
| **What — ¿Qué ocurre?** | Puede existir una pérdida de trazabilidad entre las condiciones acordadas para un servicio, las obligaciones operativas derivadas de ellas, la ejecución en campo, la evidencia disponible y la evaluación posterior de cumplimiento. |
| **Who — ¿Quiénes intervienen?** | Intervienen principalmente la organización prestadora, sus supervisores/coordinadores y operarios; también participan responsables de la organización cliente, responsables contractuales y decisores del servicio según el tipo de contrato. |
| **Where — ¿Dónde ocurre?** | En instalaciones donde una organización presta servicios de limpieza a otra: oficinas, comercios, instituciones, centros de salud, plantas, almacenes u otros establecimientos. El estudio inicial del equipo se concentra en Lima Metropolitana. |
| **When — ¿Cuándo se vuelve crítico?** | Al convertir condiciones del servicio en instrucciones operativas, durante la ejecución, al verificar resultados, cuando aparece una desviación u observación, al responder un reclamo y al consolidar información de cumplimiento. |
| **Why — ¿Por qué importa?** | Una trazabilidad insuficiente puede aumentar el esfuerzo de supervisión, dificultar la explicación del servicio y generar discrepancias acerca de qué se esperaba, qué se realizó y cómo se determinó el cumplimiento. |
| **How — ¿Cómo puede manifestarse?** | Mediante información distribuida en diferentes canales, instrucciones ambiguas, ausencia de una referencia común, evidencia insuficiente, seguimiento tardío de excepciones o consolidación manual de reportes. |
| **How Much — ¿Cuánto impacta?** | Aún no se dispone de una línea base propia que cuantifique el tiempo, costo o frecuencia del problema en las organizaciones objetivo. El impacto se medirá durante la investigación mediante variables como tiempo de consolidación, número de fuentes consultadas para reconstruir un caso, frecuencia de desviaciones y tiempo de respuesta ante consultas. |

**Objetivo de la solución.** Diseñar una experiencia digital que permita relacionar las condiciones relevantes de un servicio con obligaciones operativas, registrar su ejecución y evidencia, evaluar su estado de cumplimiento y conservar el seguimiento de desviaciones sin perder el historial original.

**Alcance inicial.** El proyecto se concentra en servicios de limpieza tercerizada B2B en Perú, con investigación y validación inicial en Lima Metropolitana. El core del producto comprende la trazabilidad desde la obligación hasta el resultado de cumplimiento.

**Restricciones y delimitación.** No forman parte del alcance inicial la nómina, control general de recursos humanos, contabilidad, planificación financiera ni la administración genérica de proyectos. Tecnologías como QR, NFC, GPS, fotografías o notificaciones se consideran mecanismos candidatos de implementación y solo deben incorporarse cuando exista una necesidad funcional, una regla del servicio o un requisito académico que las justifique. La solución sí deberá cumplir las restricciones tecnológicas establecidas por el curso para las experiencias móviles.

<a id="122-lean-ux-process"></a>

### 1.2.2. Lean UX Process

El equipo emplea Lean UX para convertir la problemática inicial en supuestos explícitos, resultados de negocio esperados y soluciones candidatas que posteriormente serán contrastadas mediante UX Research. El propósito no es presentar los assumptions como hechos, sino hacer visible aquello que el equipo considera necesario aprender y medir.

#### 1.2.2.1. Lean UX Problem Statements

##### Problem Statement

> **The current state of the domain we are working in** —los servicios de limpieza tercerizada B2B— requiere coordinar compromisos de servicio con actividades ejecutadas físicamente en instalaciones de clientes, involucrando principalmente a supervisores/coordinadores y operarios de la empresa prestadora.
>
> **What existing products/services and current practices may fail to address is** una trazabilidad simple y consultable que conecte la condición acordada, la obligación operativa, la ejecución realizada, la evidencia disponible y la respuesta frente a una desviación, evitando que el estado del servicio tenga que reconstruirse desde múltiples fuentes.
>
> **Our product/service will address this gap by** relacionar cada obligación relevante con su ejecución, evidencia, evaluación de cumplimiento y seguimiento de excepciones, manteniendo un historial consultable para la supervisión.
>
> **Our initial focus will be** supervisores/coordinadores de servicios de limpieza tercerizada y operarios de campo de empresas prestadoras que atienden instalaciones de clientes.
>
> **We’ll know we are successful when we see** una reducción del tiempo necesario para determinar y explicar el estado de una obligación, una mayor proporción de ejecuciones con el registro requerido completo, menor detección tardía de desviaciones y una experiencia de registro que los operarios puedan completar sin interferir significativamente con su trabajo principal.

La oportunidad que Opervia busca explorar consiste en especializar el producto en **cumplimiento verificable de servicios**, diferenciándolo de herramientas cuya unidad principal es una tarea aislada. La magnitud de esta oportunidad y la disposición a pagar deberán contrastarse mediante investigación competitiva y entrevistas.

#### 1.2.2.2. Lean UX Assumptions

Los assumptions se organizan en los cinco tipos requeridos para el proyecto: **Business Assumptions, Business Outcome Assumptions, User Assumptions, User Outcome and Benefit Assumptions y Feature Assumptions**.

##### Business Assumptions

| ID | Business Assumption |
|---|---|
| BA-01 | Creemos que empresas proveedoras de servicios de limpieza tercerizada pueden percibir valor económico en mejorar la trazabilidad del cumplimiento frente a sus clientes. |
| BA-02 | Creemos que el comprador o decisor de Service Compliance puede ser un responsable de operaciones, administración o dirección de la empresa prestadora, distinto del usuario que ejecuta o supervisa el servicio. |
| BA-03 | Creemos que existe una oportunidad de diferenciación si Service Compliance relaciona explícitamente obligaciones de servicio, ejecución, evidencia, desviaciones y estado de cumplimiento, en lugar de gestionar tareas aisladas. |
| BA-04 | Creemos que comenzar con el vertical de limpieza permitirá modelar reglas, lenguaje y flujos suficientemente concretos antes de evaluar otros servicios tercerizados. |

##### Business Outcome Assumptions

| ID | Business Outcome Assumption | Indicador propuesto |
|---|---|---|
| BO-01 | Creemos que Service Compliance puede reducir el esfuerzo necesario para reconstruir y explicar el estado de cumplimiento de un servicio. | Tiempo medio para reconstruir un caso o responder una consulta. |
| BO-02 | Creemos que Service Compliance puede aumentar la proporción de obligaciones cuya ejecución y evidencia requerida son trazables. | Porcentaje de obligaciones cerradas con registro y evidencia exigida completos. |
| BO-03 | Creemos que Service Compliance puede ayudar a identificar desviaciones antes de que sean descubiertas únicamente por el cliente o al cierre del periodo. | Porcentaje de desviaciones detectadas antes de reclamo o cierre. |
| BO-04 | Creemos que Service Compliance puede reducir el trabajo manual de consolidación para supervisión y reporting. | Cantidad de fuentes consultadas y tiempo utilizado para consolidar información. |

Los valores objetivo de estos indicadores se establecerán después de obtener una línea base mediante investigación. Se evita fijar porcentajes arbitrarios antes de medir el proceso actual.

##### User Assumptions

| ID | User Assumption |
|---|---|
| UA-01 | Creemos que los supervisores/coordinadores necesitan conocer qué obligaciones están pendientes, realizadas, observadas, exceptuadas o vencidas dentro del servicio que supervisan. |
| UA-02 | Creemos que los operarios necesitan instrucciones comprensibles sobre qué actividad realizar, dónde, en qué momento y qué registro se espera como resultado. |
| UA-03 | Creemos que los supervisores combinan observación directa, comunicación con el personal y registros operativos para controlar el servicio. |
| UA-04 | Creemos que los operarios presentan distintos niveles de familiaridad digital y que un flujo de registro complejo puede generar fricción o registros incompletos. |

##### User Outcome and Benefit Assumptions

| ID | User Outcome and Benefit Assumption |
|---|---|
| UO-01 | Los supervisores quieren identificar rápidamente qué requiere su atención sin reconstruir el estado desde varias fuentes. |
| UO-02 | Los supervisores quieren consultar el historial de una obligación cuando existe una observación, desviación o reclamo. |
| UO-03 | Los operarios quieren comprender con claridad qué deben ejecutar y registrar el resultado con la menor carga adicional posible. |
| UO-04 | Los operarios quieren comunicar impedimentos y excepciones para que una ejecución incompleta no sea interpretada sin contexto. |
| UO-05 | Los responsables de la empresa prestadora quieren disponer de información consistente para explicar al cliente qué ocurrió y qué acciones se tomaron. |

##### Feature Assumptions

| ID | Feature Assumption |
|---|---|
| FA-01 | Creemos que representar obligaciones de servicio asociadas a una ubicación, frecuencia o ventana y criterio de aceptación ayudará a supervisores y operarios a compartir una referencia operativa común. |
| FA-02 | Creemos que registrar la ejecución desde una experiencia móvil y vincularla directamente con su obligación y evidencia reducirá la pérdida de contexto entre campo y supervisión. |
| FA-03 | Creemos que registrar desviaciones, excepciones y acciones correctivas sin reemplazar el historial original permitirá explicar posteriormente qué ocurrió y cómo se respondió. |
| FA-04 | Creemos que una vista de estado de cumplimiento y reportes trazables por servicio, ubicación y periodo reducirá el trabajo manual de consolidación de los supervisores. |
| FA-05 | Creemos que permitir almacenamiento local temporal y sincronización posterior reducirá la pérdida de registros en entornos donde la conectividad resulte insuficiente, si esta condición se confirma durante la investigación. |

#### 1.2.2.3. Lean UX Hypothesis Statements

Se formula un Hypothesis Statement por cada **Feature Assumption**, aplicando el siguiente formato:

> **We believe we will achieve [business outcome] if [these personas] attain [this benefit/user outcome] with [this feature or solution].**

##### HS-01 — Obligaciones de servicio

> **We believe we will achieve** una reducción del esfuerzo necesario para coordinar y explicar el estado del servicio (**BO-01**)  
> **if** supervisores/coordinadores y operarios (**UA-01, UA-02**)  
> **attain** una referencia compartida sobre qué debe realizarse, dónde, cuándo y bajo qué criterio (**UO-01, UO-03**)  
> **with** obligaciones de servicio estructuradas y vinculadas al servicio contratado (**FA-01**).

##### HS-02 — Ejecución y evidencia

> **We believe we will achieve** una mayor proporción de obligaciones con ejecución y evidencia trazables (**BO-02**)  
> **if** operarios y supervisores (**UA-02, UA-04**)  
> **attain** una forma rápida y comprensible de registrar el resultado sin reconstruir posteriormente su contexto (**UO-03**)  
> **with** un registro móvil de ejecución directamente vinculado a la obligación y a la evidencia requerida (**FA-02**).

##### HS-03 — Desviaciones y acciones correctivas

> **We believe we will achieve** una detección y respuesta más temprana ante desviaciones relevantes (**BO-03**)  
> **if** supervisores y operarios (**UA-01, UA-02**)  
> **attain** la capacidad de comunicar una excepción, conocer su estado y conservar qué acción se realizó (**UO-01, UO-04**)  
> **with** un flujo de desviaciones, excepciones y acciones correctivas que conserve el historial original (**FA-03**).

##### HS-04 — Estado de cumplimiento y reporting

> **We believe we will achieve** una reducción del trabajo manual de consolidación y explicación del cumplimiento (**BO-01, BO-04**)  
> **if** supervisores/coordinadores (**UA-01, UA-03**)  
> **attain** acceso directo al estado e historial de las obligaciones relevantes (**UO-01, UO-02, UO-05**)  
> **with** una vista de cumplimiento y reportes trazables por servicio, ubicación y periodo (**FA-04**).

##### HS-05 — Continuidad ante conectividad limitada

> **We believe we will achieve** una mayor proporción de registros de ejecución completos (**BO-02**)  
> **if** los operarios de campo (**UA-02, UA-04**)  
> **attain** la capacidad de registrar una ejecución aun cuando la conectividad inmediata sea insuficiente (**UO-03**)  
> **with** almacenamiento local temporal y sincronización posterior controlada (**FA-05**).

#### 1.2.2.4. Lean UX Canvas

El Lean UX Canvas sintetiza los elementos definidos previamente y establece qué debe aprender primero el equipo antes de consolidar las decisiones del producto.

| **1. Business Problem** | **2. Business Outcomes** |
|---|---|
| Las empresas proveedoras de limpieza tercerizada deben transformar compromisos de servicio en trabajo ejecutado en instalaciones del cliente. Cuando contrato, instrucciones, ejecución, evidencia y seguimiento quedan separados, explicar el estado de cumplimiento puede exigir reconstruir información desde múltiples fuentes. | Reducir esfuerzo de reconstrucción y consolidación; aumentar obligaciones con ejecución y evidencia trazables; detectar desviaciones antes de reclamos tardíos; reducir trabajo manual de reporting. |
| **3. Users / Customer Segments** | **4. User Outcomes & Benefits** |
| **Segmento 1:** supervisores y coordinadores de servicios de limpieza tercerizada.<br>**Segmento 2:** operarios de limpieza tercerizada.<br><br>Stakeholders relacionados: responsables de operaciones de la prestadora, responsables contractuales y responsables de facilities/servicios generales del cliente. | Supervisores: detectar qué requiere atención, consultar historial y responder observaciones.<br>Operarios: entender qué hacer, registrar resultados con baja fricción y comunicar excepciones.<br>Prestadora: disponer de información consistente para explicar el servicio. |
| **5. Solutions** | **6. Hypotheses** |
| Obligaciones de servicio; registro móvil de ejecución; evidencia configurable; gestión de desviaciones y acciones correctivas; estado de cumplimiento; reporting trazable; almacenamiento local y sincronización cuando corresponda. QR, NFC, GPS y fotografías son mecanismos candidatos, no requisitos universales. | HS-01: obligaciones compartidas.<br>HS-02: ejecución y evidencia.<br>HS-03: desviaciones y acciones correctivas.<br>HS-04: cumplimiento y reporting.<br>HS-05: continuidad ante conectividad limitada. |
| **7. Most important thing to learn first** | **8. Least amount of work to learn it** |
| Determinar si la falta de trazabilidad entre lo acordado y lo ejecutado constituye un problema prioritario para supervisores y operarios, qué información se considera suficiente para evaluar cumplimiento y qué actor decide o paga por una solución. | Entrevistar entre 3 y 5 representantes por segmento, analizar competidores, revisar ejemplos anonimizados de contratos/registros cuando sea posible y contrastar un prototipo de baja fidelidad del flujo obligación → ejecución → evidencia → desviación. |

<sub>*Figura 1. Lean UX Canvas de Service Compliance.*</sub>

<a id="13-segmentos-objetivo"></a>

## 1.3. Segmentos objetivo

El proyecto prioriza **dos segmentos objetivo humanos** porque ambos participan directamente en la experiencia operativa y presentan necesidades suficientemente diferentes para requerir investigación y diseño propios. Se evita convertir cada stakeholder del negocio en un segmento adicional, ya que posteriormente el proyecto debe realizar entre 3 y 5 entrevistas por segmento.

La empresa prestadora, la organización cliente, el comprador, el responsable contractual y el responsable de facilities continúan siendo actores relevantes del dominio, pero no constituyen segmentos objetivo independientes en esta primera iteración.

| Actor relacionado | Participación esperada | Clasificación inicial |
|---|---|---|
| Jefe de operaciones / administrador de la empresa prestadora | Puede aprobar presupuesto, políticas y despliegue del producto. | Comprador o decisor potencial. |
| Responsable de facilities / servicios generales de la organización cliente | Recibe el servicio y puede formular observaciones o revisar cumplimiento. | Stakeholder/beneficiario. |
| Responsable contractual | Interpreta condiciones del acuerdo y sus modificaciones. | Actor de dominio. |
| Supervisor / coordinador | Coordina, verifica y da seguimiento al servicio. | **Segmento objetivo 1.** |
| Operario de limpieza | Ejecuta las actividades del servicio en campo. | **Segmento objetivo 2.** |

### 1.3.1. Supervisores y coordinadores de servicios de limpieza tercerizada

#### Descripción del segmento

Este segmento está compuesto por personas que organizan, coordinan y supervisan la ejecución de actividades de limpieza dentro de oficinas, hoteles y otros establecimientos. El **Clasificador Nacional de Ocupaciones 2015** reconoce específicamente la ocupación **3131 — Supervisores de mantenimiento y limpieza en oficinas, hoteles y otros establecimientos**, y señala entre sus tareas supervisar a limpiadores y demás personal de limpieza, controlar suministros y velar por el correcto desempeño de las funciones asignadas (INEI, 2015).

Dentro de Service Compliance, este segmento representa al usuario que necesita comprender el estado operativo del servicio, detectar excepciones, revisar evidencia y responder ante observaciones. El supervisor no se asume automáticamente como comprador ni como administrador contractual; esas responsabilidades pueden recaer en otros cargos de la organización.

#### Características demográficas, laborales y tecnológicas

| Variable | Caracterización del segmento |
|---|---|
| **Edad** | Personas adultas en edad laboral. No se fija un rango específico porque las fuentes oficiales revisadas no ofrecen una distribución reciente y desagregada para la ocupación CNO 3131. La edad se registrará como variable objetiva durante entrevistas. |
| **Género** | Participación abierta a hombres y mujeres. No se atribuye una proporción específica al segmento sin estadística ocupacional directa. |
| **Ubicación inicial** | Lima Metropolitana, como alcance de investigación del equipo. |
| **Rol laboral** | Supervisión, coordinación y control del trabajo de limpieza y del personal asignado; el CNO 2015 reconoce formalmente esta ocupación como 3131. |
| **Experiencia** | Se priorizarán personas con experiencia reciente supervisando limpieza tercerizada. Como contexto del mercado formal, la EDO 2023 indicó que 72,5 % de los nuevos puestos permanentes estudiados requería experiencia, sin atribuir ese porcentaje exclusivamente a supervisores de limpieza (MTPE, 2023a). |
| **Formación** | Puede variar según la empresa y complejidad del servicio. El proyecto no presupone un nivel educativo único para la ocupación. |
| **Entorno tecnológico** | Se espera contacto habitual con teléfono móvil y herramientas de comunicación/registro. La EDO 2023 encontró que 99,1 % de la demanda de nuevos puestos permanentes estudiada solicitaba al menos una habilidad digital; el dato sirve como contexto general y será contrastado para este segmento (MTPE, 2023a). |
| **Contexto de trabajo** | Trabajo presencial o distribuido entre instalaciones, coordinación con operarios y comunicación con responsables internos o del cliente. |

#### Necesidades y comportamientos a validar

- Identificar qué obligaciones requieren atención durante el turno o periodo.
- Conocer qué actividades fueron realizadas, observadas, exceptuadas o quedaron pendientes.
- Revisar el contexto y evidencia de una ejecución sin recorrer múltiples canales.
- Registrar y dar seguimiento a desviaciones o excepciones.
- Responder observaciones del cliente con información trazable.
- Reducir trabajo manual de consolidación y reporting.

#### Fricciones y riesgos del segmento

- La herramienta puede añadir más trabajo del que elimina si exige registro duplicado.
- El supervisor puede no ser quien interpreta formalmente el contrato.
- La organización puede mantener hojas de cálculo o mensajería como herramientas suficientes para determinados contratos.
- La evidencia exigida por la prestadora puede diferir de la que acepta el cliente.
- Los mecanismos de GPS, fotografías, QR o NFC pueden estar restringidos por políticas del lugar de servicio.

### 1.3.2. Operarios de limpieza tercerizada

#### Descripción del segmento

Este segmento comprende a las personas que ejecutan directamente las actividades de limpieza en las instalaciones donde se presta el servicio. El **Clasificador Nacional de Ocupaciones 2015** identifica la ocupación **9112 — Limpiadores y asistentes de oficinas, hoteles y otros establecimientos**, cuyas tareas comprenden barrer o aspirar, lavar y lustrar pisos y muebles, limpiar servicios higiénicos y mantener ordenados diferentes tipos de establecimientos (INEI, 2015).

El operario constituye el principal actor de campo. Para Service Compliance, su experiencia es crítica porque cualquier registro digital debe adaptarse al ritmo del trabajo físico y no convertirse en una carga administrativa que dificulte la ejecución del servicio.

#### Características demográficas, laborales y tecnológicas

El MTPE aporta información estadística específica para esta ocupación. En el primer trimestre de 2024, el empleo formal privado registró un promedio de **49 653 trabajadores** en la categoría de limpiadores y asistentes de oficinas, hoteles y otros establecimientos. El informe reportó 55 % de mujeres y 37 % de hombres; 64 % correspondía a adultos de 30 a 59 años y 20 % a jóvenes de 15 a 29 años. La suma no alcanza 100 % en algunas variables porque el propio informe excluye registros sin característica determinada. Además, 98 % fue clasificado como no calificado según la metodología ocupacional utilizada (MTPE, 2024).

| Variable | Caracterización del segmento |
|---|---|
| **Edad** | Predominio de adultos de 30 a 59 años (64 % en el empleo formal privado reportado para 2024 T1); 20 % correspondía a jóvenes de 15 a 29 años (MTPE, 2024). |
| **Género** | En el registro formal privado analizado por el MTPE, 55 % correspondía a mujeres y 37 % a hombres; existe un porcentaje no determinado en la fuente (MTPE, 2024). |
| **Ubicación inicial** | Lima Metropolitana. Para 2023, la EDO proyectó 2 530 nuevos puestos de esta ocupación que requerían como mínimo secundaria completa en Lima Metropolitana (MTPE, 2023b). |
| **Nivel educativo / calificación** | El informe laboral de 2024 clasificó a 98 % de los trabajadores de esta ocupación como no calificados bajo su metodología. La EDO 2023 muestra además demanda relevante para personas con secundaria completa. |
| **Experiencia laboral** | Variable según empresa e instalación. El reclutamiento de entrevistas priorizará personas con experiencia reciente en limpieza institucional, comercial, industrial u oficinas. |
| **Capacidad digital** | No se presupone homogénea. El producto deberá minimizar escritura, pasos y navegación innecesaria y validar el nivel real de familiaridad con aplicaciones móviles. |
| **Entorno de trabajo** | Trabajo físico y presencial, desplazamiento entre zonas, turnos y posible uso de guantes u otros implementos. El registro digital debe integrarse al flujo de trabajo en lugar de interrumpirlo. |

#### Necesidades y comportamientos a validar

- Recibir instrucciones claras acerca de qué actividad realizar, dónde y cuándo.
- Comprender qué evidencia o confirmación se solicita para una obligación concreta.
- Registrar el resultado con pocos pasos y sin duplicar información.
- Comunicar impedimentos, incidencias o excepciones con contexto suficiente.
- Conocer si el registro de una actividad quedó correctamente guardado o sincronizado.
- Poder continuar el registro ante conectividad insuficiente si esa situación se confirma como frecuente.

#### Fricciones y riesgos del segmento

- Registrar cada actividad puede generar una carga desproporcionada frente al valor aportado.
- El trabajador puede no disponer siempre de datos móviles o de un dispositivo asignado por la empresa.
- El uso de fotografía o geolocalización puede ser sensible o estar prohibido en algunas instalaciones.
- QR o NFC pueden fallar si el punto físico se deteriora, se retira o no corresponde a la actividad que se pretende verificar.
- La definición de “evidencia suficiente” puede depender más del acuerdo de servicio que de la preferencia del operario.

La investigación del Capítulo II deberá incluir **entre 3 y 5 participantes por cada segmento**, manteniendo separadas las características observadas en entrevistas de las assumptions definidas en este capítulo. Los resultados obtenidos servirán para construir User Personas, User Task Matrix, User Journey Mapping y Empathy Mapping y para confirmar, modificar o rechazar las hipótesis de Lean UX.

## Referencias

Instituto Nacional de Estadística e Informática. (2015). *Clasificador Nacional de Ocupaciones 2015*. https://cdn.www.gob.pe/uploads/document/file/4123438/Clasificador%20Nacional%20de%20Ocupaciones%202015.pdf

Instituto Nacional de Estadística e Informática. (2026a, 20 de marzo). *Sector Servicios Prestados a Empresas aumentó 3,68 % en enero 2026*. Plataforma del Estado Peruano. https://www.gob.pe/es/institucion/inei/noticias/1368667-sector-servicios-prestados-a-empresas-aumento-3-68-en-enero-2026

Instituto Nacional de Estadística e Informática. (s. f.). *Clasificación Industrial Internacional Uniforme, Revisión 4: Clase 8121, Limpieza general de edificios*. https://proyectos.inei.gob.pe/CIIU/frm_lista_notas.asp?wc_cod=8121

Ministerio de Trabajo y Promoción del Empleo. (2023a, 17 de febrero). *Empresas privadas requerirán más de 348 mil puestos laborales el 2023*. Plataforma del Estado Peruano. https://www.gob.pe/institucion/mtpe/noticias/701438-empresas-privadas-requeriran-mas-de-348-mil-puestos-laborales-el-2023

Ministerio de Trabajo y Promoción del Empleo. (2023b). *Demanda de ocupaciones en Lima Metropolitana 2023: Encuesta de Demanda Ocupacional*. https://cdn.www.gob.pe/uploads/document/file/4921861/Informe%20EDO%20al%202023%20_%20Lima%20Metro.pdf

Ministerio de Trabajo y Promoción del Empleo. (2024). *Informe trimestral del mercado laboral: primer trimestre de 2024*. https://cdn.www.gob.pe/uploads/document/file/6653196/5783668-ite-2024-t1.pdf
