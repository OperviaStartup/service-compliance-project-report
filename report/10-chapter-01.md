<a id="capitulo-i-presentacion"></a>

# Capítulo I: Presentación

<a id="11-startup-profile"></a>

## 1.1. Startup Profile

<a id="111-descripcion-de-la-startup"></a>

### 1.1.1. Descripción de la Startup

**Opervia** es una startup académica orientada al diseño de soluciones digitales para la gestión y trazabilidad del cumplimiento de servicios tercerizados. El proyecto toma como dominio inicial los **servicios de limpieza tercerizada B2B en el Perú**, donde una empresa prestadora ejecuta actividades en instalaciones de una organización cliente y debe coordinar personas, condiciones del servicio, planificación operativa, supervisión y resultados.

El Instituto Nacional de Estadística e Informática (INEI) clasifica la **limpieza general de edificios** en la clase CIIU 8121, que comprende la limpieza general no especializada de oficinas, fábricas, comercios, instituciones y otros establecimientos. En enero de 2026, el INEI reportó además que este rubro creció por la ampliación de contratos de limpieza integral en centros comerciales, hospitales, plantas industriales y almacenes, lo que evidencia la presencia de este tipo de servicio en distintos entornos organizacionales (INEI, 2026a; INEI, s. f.).

A partir de este dominio, Opervia propone **Service Compliance**, un producto cuyo propósito es mantener una relación trazable entre aquello que una organización se compromete a prestar y aquello que realmente ocurre durante la operación. El modelo conceptual inicial del producto se resume en la siguiente cadena:

> **Service Contract → Service Conditions → Service Plan → Service Obligation → Execution → Evidence → Compliance Evaluation → Compliance Result → Corrective Action (when applicable) → Compliance Report**

En este modelo, el **Service Contract** establece el marco del servicio; las **Service Conditions** representan las condiciones relevantes para la operación; y el **Service Plan** constituye la interpretación operativa mediante la cual esas condiciones se organizan en obligaciones ejecutables. Esta separación evita asumir que el software interpretará automáticamente un contrato o que toda cláusula contractual puede convertirse de forma directa en una obligación.

El **Compliance Result** representa el resultado de evaluar lo esperado frente a lo ocurrido. Dicho resultado puede reflejar cumplimiento, una excepción aceptada, una desviación o un incumplimiento, dependiendo de las reglas aplicables. Una **Corrective Action** solo se genera cuando corresponde y no elimina ni reemplaza el historial de la ejecución o de la evaluación original.

Service Compliance no se plantea como un gestor genérico de tareas. Su propuesta consiste en que una actividad operativa conserve el contexto del servicio que la origina, la obligación que debía atender, el resultado de su ejecución, la evidencia requerida y la evaluación posterior que permite explicar su estado de cumplimiento.

En la primera iteración del modelo de negocio, la **empresa prestadora del servicio de limpieza** se considera el cliente organizacional y comprador potencial de la solución. Los supervisores/coordinadores y operarios de dicha empresa constituyen los segmentos de usuario priorizados. La **organización cliente que recibe el servicio** se mantiene como stakeholder relevante, ya que puede formular observaciones, solicitar explicaciones o recibir reportes de cumplimiento, pero no se considera un tercer segmento objetivo en esta etapa.

**Misión.** Facilitar que las empresas prestadoras de servicios tercerizados relacionen de forma clara sus compromisos operativos, la ejecución en campo y la evidencia necesaria para comprender, supervisar y explicar el estado de cumplimiento del servicio.

**Visión.** Convertir a Opervia en una alternativa digital especializada para la gestión del cumplimiento de servicios tercerizados, iniciando en limpieza y extendiendo el modelo únicamente cuando las necesidades, reglas del dominio y viabilidad comercial hayan sido validadas.

**Propuesta de valor inicial.** Permitir que supervisores y operarios de una empresa prestadora trabajen sobre una misma referencia operativa, registren lo ocurrido en campo y conserven una trazabilidad desde el servicio planificado hasta su evaluación de cumplimiento, facilitando la supervisión, la atención de desviaciones y la explicación del servicio frente a responsables internos o clientes.

<a id="112-perfiles-de-integrantes-del-equipo"></a>

### 1.1.2. Perfiles de integrantes del equipo

El equipo de Opervia reúne conocimientos de análisis de requisitos, desarrollo de software, modelado de dominio, arquitectura e integración de aplicaciones. La composición del equipo se presenta a continuación.

| N.° | Integrante                             | Código     | Carrera                | Fotografía                                             | Principales conocimientos y aportes                                                                                                                                                                                                                                                                                                                                                                    |
| --: | -------------------------------------- | ---------- | ---------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|   1 | Arias Tasayco, Jean Pool Alexander     | U202414054 | Ingeniería de Software | ![Participante Jean](resources/10-chapter-01/jean.jpg) | Cuenta con conocimientos en desarrollo de software, programación, bases de datos, diseño de APIs REST y control de versiones con Git/GitHub. Aporta al proyecto en el análisis de requisitos, definición de la arquitectura de la solución, modelado del dominio, desarrollo del backend y aplicaciones móviles, así como en la integración y validación de las funcionalidades de Service Compliance. |
|   2 | Ayasta Martel, Zayd Jaffar             | U202410837 | Ingeniería de Software | ![Participante Zayd](resources/10-chapter-01/foto_zayd.png)                                                       | Cuenta con conocimientos en especificación de requisitos, gestión de producto y desarrollo de software. Aporta en la elaboración de las User Stories, el Impact Mapping y el Product Backlog, así como en la revisión de la coherencia del modelo de solución de Service Compliance.                                                                                                                     |
|   3 | Blancas Chávez, Carlos Franco          | U20241A322 | Ingeniería de Software | ![Participante Carlos](resources/10-chapter-01/foto_carlos.png)                                                       | Posee conocimientos en arquitectura de software, modelado de dominio y metodologías ágiles. Aporta en el diseño a nivel estratégico del Domain-Driven Design (EventStorming, Context Mapping y arquitectura C4) y en la coordinación del modelado táctico de los Bounded Contexts de la solución.                                                                                                          |
|   4 | Flores Eusebio, Angel Thyago           | U20231B781 | Ingeniería de Software | ![Participante Angel](resources/10-chapter-01/foto-reporte-angel.jpeg) | Cuenta con conocimientos en análisis competitivo, investigación de mercado y estrategia de producto. Aporta en la identificación y análisis de los competidores de Service Compliance y en la definición de estrategias y tácticas frente a los mismos.                                                                                                                                                    |
|   5 | Montes Maza, Augusto Sebastian         | U202218645 | Ingeniería de Software |  ![Participante Angel](resources/10-chapter-01/foto-Sebastian.png) | Posee conocimientos en investigación de usuarios y diseño de experiencia (UX). Aporta en la elaboración de los artefactos de Needfinding: User Personas, User Task Matrix, User Journey Mapping, Empathy Mapping, Big Picture EventStorming y Ubiquitous Language.                                                                      |
|   6 | Sánchez Espinoza, Mathias Enrique      | U20231C524 | Ingeniería de Software | ![Participante Mathias](resources/10-chapter-01/mathias.jpg) | Cuenta con conocimientos en UX Research y diseño de investigaciones con usuarios. Aporta en el diseño y la conducción de las entrevistas dirigidas a los segmentos objetivo de Operarios de Campo y Supervisores, base de la investigación para Service Compliance.                                                                         |


<a id="12-solution-profile"></a>

## 1.2. Solution Profile

<a id="121-antecedentes-y-problematica"></a>

### 1.2.1. Antecedentes y problemática

La prestación de servicios de limpieza en edificios forma parte de las actividades de servicios administrativos y de apoyo. El INEI define la clase CIIU 8121 como la limpieza general de oficinas, fábricas, comercios, instituciones y otros establecimientos. Esta actividad puede desarrollarse dentro de múltiples tipos de instalaciones y bajo contratos de servicio entre organizaciones (INEI, s. f.).

El contexto laboral también evidencia la relevancia de las ocupaciones vinculadas al dominio. La Encuesta de Demanda Ocupacional del Ministerio de Trabajo y Promoción del Empleo (MTPE) ubicó a los **limpiadores y asistentes de oficinas, hoteles y otros establecimientos** entre las ocupaciones con mayor demanda de puestos permanentes para 2023. Para el conjunto de nuevos puestos permanentes analizados por la encuesta, 72,5 % requería experiencia laboral, 99,1 % al menos una habilidad digital y 45,5 % como mínimo secundaria completa (MTPE, 2023a). Estas cifras describen el contexto de contratación formal estudiado por la EDO y no deben interpretarse como características exclusivas de todos los trabajadores de limpieza.

En Lima Metropolitana, la misma Encuesta de Demanda Ocupacional proyectó para 2023 una demanda de **2 530 trabajadores** para la ocupación de limpiadores y asistentes de oficinas, hoteles y otros establecimientos dentro de los puestos cuyo nivel educativo mínimo requerido era secundaria completa (MTPE, 2023b). Asimismo, el Informe Trimestral del Mercado Laboral del MTPE reportó para el primer trimestre de 2024 un promedio de **49 653 trabajadores formales privados** en esta ocupación; entre los registros con característica identificada, 55 % correspondía a mujeres y 37 % a hombres, 64 % a adultos de 30 a 59 años y 20 % a jóvenes de 15 a 29 años. El mismo informe clasificó al 98 % como trabajadores no calificados según su metodología ocupacional (MTPE, 2024).

El problema abordado por Opervia no es la actividad de limpieza en sí misma, sino la **trazabilidad del cumplimiento de un servicio tercerizado**. En una relación B2B, una organización cliente espera que determinadas condiciones de servicio se cumplan, mientras que la empresa prestadora debe interpretar esas condiciones, convertirlas en un plan operativo, coordinar personas, ejecutar actividades, supervisar resultados y atender desviaciones.

El proyecto parte de la hipótesis de que, cuando la información relacionada con el servicio queda distribuida entre contratos, planes o cronogramas, instrucciones operativas, mensajes, registros de campo y reportes, puede resultar costoso reconstruir qué debía ocurrir, qué ocurrió realmente, qué evidencia se requería y cómo se determinó el estado de cumplimiento. La investigación del Capítulo II deberá confirmar, modificar o rechazar esta hipótesis y determinar qué partes del proceso representan los problemas de mayor prioridad para los segmentos objetivo.

La problemática se analiza mediante la técnica **5W+2H** para delimitar el dominio sin convertir assumptions en resultados empíricos.

#### Análisis 5W+2H

| Dimensión | Análisis para Service Compliance |
|---|---|
| **What — ¿Qué ocurre?** | Puede existir una pérdida de trazabilidad entre las condiciones acordadas para un servicio, su interpretación en un plan operativo, las obligaciones resultantes, la ejecución en campo, la evidencia disponible y la evaluación posterior de cumplimiento. |
| **Who — ¿Quiénes intervienen?** | Intervienen principalmente la empresa prestadora, sus supervisores/coordinadores y operarios; también participan responsables de operaciones, responsables contractuales y representantes de la organización cliente según el tipo de servicio y contrato. |
| **Where — ¿Dónde ocurre?** | En instalaciones donde una organización presta servicios de limpieza a otra: oficinas, comercios, instituciones, centros de salud, plantas, almacenes u otros establecimientos. El estudio inicial del equipo se concentra en Lima Metropolitana. |
| **When — ¿Cuándo se vuelve crítico?** | Al interpretar condiciones del servicio, planificar actividades, comunicar obligaciones, ejecutar y verificar el trabajo, atender impedimentos o desviaciones, responder observaciones del cliente y consolidar información de cumplimiento. |
| **Why — ¿Por qué importa?** | Una trazabilidad insuficiente puede aumentar el esfuerzo de supervisión, dificultar la explicación del servicio y generar discrepancias acerca de qué se esperaba, qué se realizó, qué evidencia era necesaria y cómo se determinó el cumplimiento. |
| **How — ¿Cómo puede manifestarse?** | Mediante información distribuida en diferentes canales, cambios operativos difíciles de rastrear, instrucciones ambiguas, ausencia de una referencia común, evidencia insuficiente o descontextualizada, seguimiento tardío de excepciones o consolidación manual de reportes. |
| **How Much — ¿Cuánto impacta?** | La magnitud del impacto debe medirse sobre el proceso actual. Se consideran variables como tiempo de consolidación, cantidad de fuentes consultadas para reconstruir un caso, frecuencia de desviaciones, tiempo de reacción ante observaciones y proporción de ejecuciones cuya evidencia puede relacionarse con una obligación concreta. |

**Objetivo de la solución.** Diseñar una experiencia digital que permita representar el plan operativo de un servicio y sus obligaciones, registrar su ejecución y la evidencia requerida, evaluar su estado de cumplimiento y conservar el seguimiento de excepciones, desviaciones y acciones correctivas sin perder el historial original.

**Alcance inicial.** El proyecto se concentra en servicios de limpieza tercerizada B2B en Perú, con investigación y validación inicial en Lima Metropolitana. El core conceptual del producto comprende la trazabilidad **Service Plan → Service Obligation → Execution → Evidence → Compliance Evaluation → Compliance Result**, incluyendo seguimiento correctivo cuando corresponda.

**Cliente organizacional inicial.** La hipótesis comercial prioriza a empresas prestadoras de servicios de limpieza tercerizada que necesitan coordinar y demostrar el cumplimiento de los servicios prestados. El responsable de operaciones, administración o dirección de la empresa prestadora se considera comprador o decisor potencial. Esta hipótesis de compra deberá contrastarse de manera separada de la investigación de experiencia de los dos segmentos de usuario.

**Restricciones y delimitación.** No forman parte del alcance inicial la nómina, el control general de recursos humanos, la contabilidad, la planificación financiera ni la administración genérica de proyectos. El producto tampoco pretende interpretar jurídicamente contratos ni derivar automáticamente todas sus cláusulas. Tecnologías como QR, NFC, GPS, fotografías o notificaciones se consideran mecanismos candidatos de implementación y solo deben incorporarse cuando exista una necesidad funcional, una regla del servicio o un requisito académico que las justifique. La solución deberá cumplir las restricciones tecnológicas establecidas por el curso para las experiencias móviles, incluyendo almacenamiento local, acceso a recursos del dispositivo, integración con el servicio RESTful propio y uso de un servicio externo de terceros.

<a id="122-lean-ux-process"></a>

### 1.2.2. Lean UX Process

El equipo emplea Lean UX para convertir la problemática inicial en supuestos explícitos, resultados de negocio esperados y soluciones candidatas que posteriormente serán contrastadas mediante UX Research. El propósito no es presentar los assumptions como hechos, sino hacer visible aquello que el equipo considera necesario aprender, medir y validar antes de consolidar el alcance del producto.

#### 1.2.2.1. Lean UX Problem Statements

##### Problem Statement

> **The current state of the domain we are working in** —los servicios de limpieza tercerizada B2B— **has focused mainly on** coordinar personas, zonas, horarios, condiciones del servicio y verificación del trabajo mediante supervisión operativa y registros que pueden encontrarse distribuidos entre diferentes medios, involucrando principalmente a supervisores/coordinadores y operarios de la empresa prestadora.
>
> **What existing products/services fail to address is** una trazabilidad suficientemente simple y centrada en cumplimiento que conecte la condición relevante del servicio, su planificación operativa, la obligación concreta, la ejecución realizada, la evidencia requerida y la decisión posterior de cumplimiento, sin tratar cada actividad como una tarea aislada.
>
> **Our product/service will address this gap by** mantener una cadena trazable entre Service Plan, Service Obligation, Execution, Evidence y Compliance Result, preservando además el contexto de excepciones, desviaciones y acciones correctivas cuando correspondan.
>
> **Our initial focus will be** supervisores/coordinadores de servicios de limpieza tercerizada y operarios de campo de empresas prestadoras que atienden instalaciones de clientes.
>
> **We’ll know we are successful when we see** menor tiempo y menor cantidad de fuentes necesarias para determinar el estado de una obligación, mayor proporción de ejecuciones cuyo registro puede relacionarse con la obligación y evidencia requerida, detección más temprana de desviaciones relevantes y una experiencia de registro que los operarios puedan completar sin interferir significativamente con su trabajo principal.

La oportunidad que Opervia busca explorar consiste en especializar el producto en **cumplimiento verificable de servicios**, diferenciándolo de soluciones cuyo centro de gravedad se encuentra en la gestión genérica de tareas, órdenes de trabajo o inspecciones aisladas. La magnitud de esta oportunidad, la prioridad real del problema y la disposición a pagar deberán contrastarse mediante investigación competitiva, entrevistas y validaciones posteriores.

#### 1.2.2.2. Lean UX Assumptions

Los assumptions se organizan en los cinco tipos requeridos para el proyecto: **Business Assumptions, Business Outcome Assumptions, User Assumptions, User Outcome and Benefit Assumptions y Feature Assumptions**. Cada assumption representa una creencia del equipo que podrá mantenerse, modificarse o descartarse a partir de la evidencia obtenida.

##### Business Assumptions

| ID | Business Assumption |
|---|---|
| BA-01 | Creemos que empresas proveedoras de servicios de limpieza tercerizada pueden percibir valor económico en mejorar la trazabilidad del cumplimiento frente a sus clientes. |
| BA-02 | Creemos que el comprador o decisor de Service Compliance puede ser un responsable de operaciones, administración o dirección de la empresa prestadora, distinto del usuario que ejecuta o supervisa el servicio. |
| BA-03 | Creemos que existe una oportunidad de diferenciación si Service Compliance relaciona explícitamente condiciones de servicio, planificación, obligaciones, ejecución, evidencia y resultados de cumplimiento, en lugar de gestionar tareas aisladas. |
| BA-04 | Creemos que comenzar con el vertical de limpieza permitirá modelar reglas, lenguaje y flujos suficientemente concretos antes de evaluar otros servicios tercerizados. |
| BA-05 | Creemos que un modelo de suscripción B2B pagado por la empresa prestadora puede ser viable si el producto demuestra reducción de esfuerzo operativo y una mejor capacidad para explicar el cumplimiento frente a sus clientes. |
| BA-06 | Creemos que Opervia puede iniciar mediante pilotos acotados por servicio o sede antes de intentar un despliegue organizacional amplio, reduciendo el riesgo de adopción para la empresa prestadora. |

##### Business Outcome Assumptions

| ID | Business Outcome Assumption | Indicador propuesto | Criterio de éxito preliminar |
|---|---|---|---|
| BO-01 | Creemos que Service Compliance puede reducir el esfuerzo necesario para reconstruir y explicar el estado de cumplimiento de un servicio. | Tiempo medio y cantidad de fuentes necesarias para reconstruir un caso o responder una consulta. | El proceso apoyado por la solución requiere menos tiempo o menos fuentes que el proceso de referencia medido durante la investigación. |
| BO-02 | Creemos que Service Compliance puede aumentar la proporción de obligaciones cuya ejecución y evidencia requerida son trazables. | Porcentaje de obligaciones cerradas con registro y evidencia exigida completos y vinculados. | La proporción de obligaciones trazables durante el piloto supera la línea base del proceso actual. |
| BO-03 | Creemos que Service Compliance puede ayudar a identificar desviaciones antes de que sean descubiertas únicamente por el cliente o al cierre del periodo. | Porcentaje de desviaciones detectadas antes de reclamo del cliente o cierre del periodo. | La proporción de detecciones tempranas durante el piloto supera la línea base observada. |
| BO-04 | Creemos que Service Compliance puede reducir el trabajo manual de consolidación para supervisión y reporting. | Tiempo de consolidación y cantidad de fuentes o registros que deben revisarse manualmente. | La consolidación apoyada por la solución requiere menos pasos, tiempo o fuentes que el proceso actual medido. |

Los valores numéricos objetivo se establecerán después de obtener una línea base. De esta manera se mantiene una **Definition of Done orientada a mejora comprobable** sin fijar porcentajes arbitrarios antes de medir el proceso real.

##### User Assumptions

| ID | User Assumption |
|---|---|
| UA-01 | Creemos que los supervisores/coordinadores necesitan conocer qué obligaciones están pendientes, realizadas, observadas, exceptuadas o vencidas dentro del servicio que supervisan. |
| UA-02 | Creemos que los operarios necesitan instrucciones comprensibles sobre qué actividad realizar, dónde, en qué momento y qué registro se espera como resultado. |
| UA-03 | Creemos que los supervisores combinan observación directa, comunicación con el personal y registros operativos para controlar el servicio y responder frente a observaciones. |
| UA-04 | Creemos que los operarios presentan distintos niveles de familiaridad digital y que un flujo de registro complejo puede generar fricción o registros incompletos. |
| UA-05 | Creemos que supervisor y operario necesitan compartir una referencia operativa común, aun cuando la interpretación contractual, las decisiones comerciales o la aprobación de presupuesto correspondan a otros roles. |

##### User Outcome and Benefit Assumptions

| ID | User Outcome and Benefit Assumption |
|---|---|
| UO-01 | Los supervisores quieren identificar rápidamente qué requiere su atención sin reconstruir el estado desde varias fuentes. |
| UO-02 | Los supervisores quieren consultar el historial de una obligación cuando existe una observación, desviación o reclamo. |
| UO-03 | Los operarios quieren comprender con claridad qué deben ejecutar y registrar el resultado con la menor carga adicional posible. |
| UO-04 | Los operarios quieren comunicar impedimentos y excepciones para que una ejecución incompleta no sea interpretada sin contexto. |
| UO-05 | Los supervisores/coordinadores quieren disponer de información consistente para explicar a responsables internos o al cliente qué ocurrió, cómo se evaluó y qué acciones se tomaron. |

##### Feature Assumptions

| ID | Feature Assumption |
|---|---|
| FA-01 | Creemos que representar un **Service Plan** con obligaciones asociadas a condiciones relevantes, ubicación, frecuencia o ventana y criterios de aceptación ayudará a supervisores y operarios a compartir una referencia operativa común. |
| FA-02 | Creemos que registrar la ejecución desde una experiencia móvil y vincularla directamente con su obligación y la evidencia requerida reducirá la pérdida de contexto entre campo y supervisión. |
| FA-03 | Creemos que registrar excepciones y desviaciones, diferenciarlas de un incumplimiento cuando corresponda y conservar las acciones correctivas sin reemplazar el historial original permitirá explicar posteriormente qué ocurrió y cómo se respondió. |
| FA-04 | Creemos que una vista de estado de cumplimiento y reportes trazables por servicio, ubicación y periodo reducirá el trabajo manual de consolidación de los supervisores. |
| FA-05 | Creemos que permitir almacenamiento local temporal y sincronización posterior reducirá la pérdida de registros en entornos donde la conectividad resulte insuficiente, si esta condición se confirma durante la investigación. |

QR, NFC, geolocalización, fotografías, firmas, checklists u otros mecanismos de evidencia no constituyen assumptions independientes en esta etapa. Se consideran alternativas de implementación que deberán seleccionarse según las reglas de cada obligación, los hallazgos de investigación y las restricciones académicas del curso.

#### 1.2.2.3. Lean UX Hypothesis Statements

Se formula un Hypothesis Statement por cada **Feature Assumption**:

##### HS-01 — Plan de servicio y obligaciones

> **We believe we will achieve** una reducción del esfuerzo necesario para coordinar y explicar el estado del servicio (**BO-01**)  
> **If** supervisores/coordinadores y operarios (**UA-01, UA-02, UA-05**)  
> **Attain** una referencia compartida sobre qué debe realizarse, dónde, cuándo y bajo qué criterio (**UO-01, UO-03**)  
> **With** un Service Plan con obligaciones estructuradas y relacionadas con las condiciones relevantes del servicio (**FA-01**).

##### HS-02 — Ejecución y evidencia

> **We believe we will achieve** una mayor proporción de obligaciones con ejecución y evidencia trazables (**BO-02**)  
> **If** operarios y supervisores (**UA-02, UA-04**)  
> **Attain** una forma rápida y comprensible de registrar el resultado sin reconstruir posteriormente su contexto (**UO-03**)  
> **With** un registro móvil de ejecución directamente vinculado a la obligación y a la evidencia requerida (**FA-02**).

##### HS-03 — Excepciones, desviaciones y acciones correctivas

> **We believe we will achieve** una detección y respuesta más temprana ante desviaciones relevantes (**BO-03**)  
> **If** supervisores y operarios (**UA-01, UA-02**)  
> **Attain** la capacidad de comunicar una excepción, conocer su evaluación y conservar qué respuesta o acción se realizó (**UO-01, UO-04, UO-05**)  
> **With** un flujo que registre excepciones y desviaciones, permita determinar el resultado de cumplimiento y conserve las acciones correctivas sin reemplazar el historial original (**FA-03**).

##### HS-04 — Estado de cumplimiento y reporting

> **We believe we will achieve** una reducción del trabajo manual de consolidación y explicación del cumplimiento (**BO-01, BO-04**)  
> **If** supervisores/coordinadores (**UA-01, UA-03**)  
> **Attain** acceso directo al estado e historial de las obligaciones relevantes y pueden explicar posteriormente qué ocurrió (**UO-01, UO-02, UO-05**)  
> **With** una vista de cumplimiento y reportes trazables por servicio, ubicación y periodo (**FA-04**).

##### HS-05 — Continuidad ante conectividad limitada

> **We believe we will achieve** una mayor proporción de registros de ejecución completos (**BO-02**)  
> **If** los operarios de campo (**UA-02, UA-04**)  
> **Attain** la capacidad de registrar una ejecución aun cuando la conectividad inmediata sea insuficiente (**UO-03**)  
> **With** almacenamiento local temporal y sincronización posterior controlada (**FA-05**).

#### 1.2.2.4. Lean UX Canvas

El Lean UX Canvas sintetiza la visión del modelo de negocio, los segmentos, los resultados esperados y las principales hipótesis que deberán contrastarse durante la investigación y validación del producto.

| **1. Business Problem** | **2. Business Outcomes** |
|---|---|
| Las empresas prestadoras de limpieza tercerizada deben transformar condiciones de servicio en planificación operativa, obligaciones y trabajo ejecutado en instalaciones del cliente. Cuando contrato, planificación, instrucciones, ejecución, evidencia y seguimiento quedan separados, explicar el estado de cumplimiento puede exigir reconstruir información desde múltiples fuentes. | Reducir esfuerzo de reconstrucción y consolidación; aumentar obligaciones con ejecución y evidencia trazables; detectar desviaciones antes de reclamos tardíos; reducir trabajo manual de reporting. |
| **3. Users / Customer Segments** | **4. User Outcomes & Benefits** |
| **Cliente organizacional / comprador potencial:** empresa prestadora de limpieza tercerizada, mediante responsables de operaciones, administración o dirección.<br><br>**Segmento objetivo 1:** supervisores y coordinadores de servicios de limpieza tercerizada.<br>**Segmento objetivo 2:** operarios de limpieza tercerizada.<br><br>**Stakeholders relacionados:** responsables contractuales y responsables de facilities/servicios generales de la organización cliente. | **Supervisores:** detectar qué requiere atención, consultar historial, explicar observaciones y reducir consolidación manual.<br>**Operarios:** entender qué hacer, registrar resultados con baja fricción y comunicar excepciones.<br>**Empresa prestadora:** disponer de información consistente para supervisar y explicar el servicio frente a sus clientes. |
| **5. Solutions** | **6. Hypotheses** |
| Service Plan y obligaciones; registro móvil de ejecución; evidencia configurable según obligación; registro de excepciones y desviaciones; evaluación de cumplimiento; acciones correctivas cuando correspondan; reporting trazable; almacenamiento local y sincronización cuando la conectividad lo requiera. QR, NFC, GPS, fotografías y otros mecanismos son alternativas de implementación, no requisitos universales. | HS-01: plan y obligaciones compartidas.<br>HS-02: ejecución y evidencia.<br>HS-03: excepciones, desviaciones y acciones correctivas.<br>HS-04: cumplimiento y reporting.<br>HS-05: continuidad ante conectividad limitada. |
| **7. Most important thing to learn first** | **8. Least amount of work to learn it** |
| Determinar si la falta de trazabilidad entre lo planificado y lo ejecutado constituye un problema prioritario para supervisores y operarios; qué información se considera suficiente para evaluar cumplimiento; qué diferencias existen entre excepción, desviación e incumplimiento; y si la empresa prestadora es efectivamente quien decide o paga por la solución. | Entrevistar entre 3 y 5 representantes por cada segmento objetivo; analizar competidores; revisar, cuando sea posible, ejemplos anonimizados de planes, registros o reportes; contrastar un prototipo de baja fidelidad del flujo Service Plan → Obligation → Execution → Evidence → Compliance; y realizar conversaciones exploratorias con potenciales decisores de compra. |

<sub>*Figura 1. Lean UX Canvas de Service Compliance.*</sub>

<a id="13-segmentos-objetivo"></a>

## 1.3. Segmentos objetivo

El proyecto prioriza **dos segmentos objetivo humanos** porque ambos participan directamente en la experiencia operativa y presentan necesidades suficientemente diferentes para requerir investigación y diseño propios. Esta decisión separa deliberadamente el concepto de **usuario** del concepto de **comprador**: una empresa puede pagar por Service Compliance sin que el decisor de compra sea quien utiliza la aplicación durante la ejecución cotidiana del servicio.

La hipótesis comercial inicial considera a la **empresa prestadora de limpieza tercerizada** como cliente organizacional y a un responsable de operaciones, administración o dirección como comprador o decisor potencial. La **organización cliente que recibe el servicio** se mantiene como stakeholder del dominio. Ninguno de estos actores constituye un segmento objetivo adicional en esta primera iteración.

| Actor relacionado | Participación esperada | Clasificación inicial |
|---|---|---|
| Jefe de operaciones / administrador de la empresa prestadora | Puede aprobar presupuesto, políticas y despliegue del producto. | Comprador o decisor potencial. |
| Responsable de facilities / servicios generales de la organización cliente | Recibe el servicio y puede formular observaciones, solicitar explicaciones o revisar cumplimiento. | Stakeholder/beneficiario. |
| Responsable contractual | Interpreta condiciones del acuerdo y sus modificaciones y puede participar en la definición del Service Plan. | Actor de dominio. |
| Supervisor / coordinador | Coordina, verifica y da seguimiento al servicio. | **Segmento objetivo 1.** |
| Operario de limpieza | Ejecuta las actividades del servicio en campo. | **Segmento objetivo 2.** |

### 1.3.1. Supervisores y coordinadores de servicios de limpieza tercerizada

#### Descripción del segmento

Este segmento está compuesto por personas que organizan, coordinan y supervisan la ejecución de actividades de limpieza dentro de oficinas, hoteles y otros establecimientos. El **Clasificador Nacional de Ocupaciones 2015** reconoce específicamente la ocupación **3131 — Supervisores de mantenimiento y limpieza en oficinas, hoteles y otros establecimientos**, y señala entre sus tareas supervisar a limpiadores y demás personal de limpieza, controlar suministros y velar por el correcto desempeño de las funciones asignadas (INEI, 2015).

Dentro de Service Compliance, este segmento representa al usuario que necesita comprender el estado operativo del servicio, detectar excepciones, revisar registros y evidencia, dar seguimiento a desviaciones y responder ante observaciones. El supervisor no se asume automáticamente como comprador, administrador contractual ni responsable de interpretar jurídicamente el contrato; esas responsabilidades pueden recaer en otros cargos de la organización.

#### Características demográficas, laborales y tecnológicas

| Variable | Caracterización del segmento |
|---|---|
| **Edad** | Personas adultas en edad laboral. No se fija un rango específico porque las fuentes oficiales revisadas no ofrecen una distribución reciente y desagregada para la ocupación CNO 3131. La edad se registra como variable objetiva durante las entrevistas. |
| **Género** | Participación abierta a hombres y mujeres. No se atribuye una proporción específica al segmento sin estadística ocupacional directa. |
| **Ubicación inicial** | Lima Metropolitana, como alcance inicial de investigación y validación del equipo. |
| **Rol laboral** | Supervisión, coordinación y control del trabajo de limpieza y del personal asignado; el CNO 2015 reconoce formalmente esta ocupación como 3131. |
| **Experiencia** | Se priorizan personas con experiencia reciente supervisando limpieza tercerizada. Como contexto del mercado formal, la EDO 2023 indicó que 72,5 % de los nuevos puestos permanentes estudiados requería experiencia, sin atribuir ese porcentaje exclusivamente a supervisores de limpieza (MTPE, 2023a). |
| **Formación** | Puede variar según la empresa y complejidad del servicio. El proyecto no presupone un nivel educativo único para la ocupación. |
| **Entorno tecnológico** | Se espera contacto habitual con teléfono móvil y herramientas de comunicación o registro. La EDO 2023 encontró que 99,1 % de la demanda de nuevos puestos permanentes estudiada solicitaba al menos una habilidad digital; el dato sirve como contexto general y debe contrastarse específicamente para este segmento (MTPE, 2023a). |
| **Contexto de trabajo** | Trabajo presencial o distribuido entre instalaciones, coordinación con operarios y comunicación con responsables internos o del cliente. |

#### Necesidades y comportamientos considerados para validación

- Identificar qué obligaciones requieren atención durante el turno o periodo.
- Conocer qué actividades fueron realizadas, observadas, exceptuadas o quedaron pendientes.
- Revisar el contexto y la evidencia de una ejecución sin recorrer múltiples fuentes.
- Distinguir entre impedimento, excepción, desviación e incumplimiento según las reglas aplicables.
- Registrar y dar seguimiento a desviaciones y acciones correctivas cuando correspondan.
- Responder observaciones del cliente con información trazable.
- Reducir trabajo manual de consolidación y reporting.

#### Fricciones y riesgos del segmento

- La herramienta puede añadir más trabajo del que elimina si exige registro duplicado.
- El supervisor puede no ser quien interpreta formalmente el contrato ni quien define todas las reglas del Service Plan.
- La organización puede mantener hojas de cálculo o mensajería como herramientas suficientes para determinados contratos.
- La evidencia exigida por la prestadora puede diferir de la que acepta el cliente.
- Los mecanismos de GPS, fotografías, QR o NFC pueden estar restringidos por políticas del lugar de servicio.
- La prioridad real del supervisor puede concentrarse en asignación, ausentismo o coordinación operativa y no únicamente en cumplimiento; esta relación deberá mantenerse visible durante la investigación.

### 1.3.2. Operarios de limpieza tercerizada

#### Descripción del segmento

Este segmento comprende a las personas que ejecutan directamente las actividades de limpieza en las instalaciones donde se presta el servicio. El **Clasificador Nacional de Ocupaciones 2015** identifica la ocupación **9112 — Limpiadores y asistentes de oficinas, hoteles y otros establecimientos**, cuyas tareas comprenden barrer o aspirar, lavar y lustrar pisos y muebles, limpiar servicios higiénicos y mantener ordenados diferentes tipos de establecimientos (INEI, 2015).

El operario constituye el principal actor de campo. Para Service Compliance, su experiencia es crítica porque cualquier registro digital debe adaptarse al ritmo del trabajo físico y no convertirse en una carga administrativa que dificulte la ejecución del servicio. El producto debe permitirle comprender la obligación concreta y comunicar el resultado o una excepción sin trasladarle responsabilidades contractuales o administrativas que no le corresponden.

#### Características demográficas, laborales y tecnológicas

El MTPE aporta información estadística específica para esta ocupación. En el primer trimestre de 2024, el empleo formal privado registró un promedio de **49 653 trabajadores** en la categoría de limpiadores y asistentes de oficinas, hoteles y otros establecimientos. El informe reportó 55 % de mujeres y 37 % de hombres; 64 % correspondía a adultos de 30 a 59 años y 20 % a jóvenes de 15 a 29 años. La suma no alcanza 100 % en algunas variables porque el propio informe excluye registros sin característica determinada. Además, 98 % fue clasificado como no calificado según la metodología ocupacional utilizada (MTPE, 2024).

| Variable | Caracterización del segmento |
|---|---|
| **Edad** | Predominio de adultos de 30 a 59 años (64 % en el empleo formal privado reportado para 2024 T1); 20 % correspondía a jóvenes de 15 a 29 años (MTPE, 2024). |
| **Género** | En el registro formal privado analizado por el MTPE, 55 % correspondía a mujeres y 37 % a hombres; existe un porcentaje no determinado en la fuente (MTPE, 2024). |
| **Ubicación inicial** | Lima Metropolitana. Para 2023, la EDO proyectó 2 530 nuevos puestos de esta ocupación que requerían como mínimo secundaria completa en Lima Metropolitana (MTPE, 2023b). |
| **Nivel educativo / calificación** | El informe laboral de 2024 clasificó a 98 % de los trabajadores de esta ocupación como no calificados bajo su metodología. La EDO 2023 muestra además demanda relevante para personas con secundaria completa. |
| **Experiencia laboral** | Variable según empresa e instalación. El reclutamiento de entrevistas prioriza personas con experiencia reciente en limpieza institucional, comercial, industrial u oficinas. |
| **Capacidad digital** | No se presupone homogénea. El producto deberá minimizar escritura, pasos y navegación innecesaria y validar el nivel real de familiaridad con aplicaciones móviles. |
| **Entorno de trabajo** | Trabajo físico y presencial, desplazamiento entre zonas, turnos y posible uso de guantes u otros implementos. El registro digital debe integrarse al flujo de trabajo en lugar de interrumpirlo. |

#### Necesidades y comportamientos considerados para validación

- Recibir instrucciones claras acerca de qué actividad realizar, dónde y cuándo.
- Comprender qué evidencia o confirmación se solicita para una obligación concreta.
- Registrar el resultado con pocos pasos y sin duplicar información.
- Comunicar impedimentos, incidencias o excepciones con contexto suficiente.
- Conocer si el registro de una actividad quedó correctamente guardado o sincronizado.
- Poder continuar el registro ante conectividad insuficiente cuando esa condición se presente.

#### Fricciones y riesgos del segmento

- Registrar cada actividad puede generar una carga desproporcionada frente al valor aportado.
- El trabajador puede no disponer siempre de datos móviles o de un dispositivo asignado por la empresa.
- El uso de fotografía o geolocalización puede ser sensible o estar prohibido en algunas instalaciones.
- QR o NFC pueden fallar si el punto físico se deteriora, se retira o no corresponde a la actividad que se pretende verificar.
- La definición de “evidencia suficiente” puede depender más del Service Plan y del acuerdo entre las organizaciones que de la preferencia del operario.
- El producto debe evitar convertir al operario en responsable de interpretar criterios contractuales; su responsabilidad principal es ejecutar y comunicar el resultado de la obligación asignada.


## Referencias

Instituto Nacional de Estadística e Informática. (2015). *Clasificador Nacional de Ocupaciones 2015*. https://cdn.www.gob.pe/uploads/document/file/4123438/Clasificador%20Nacional%20de%20Ocupaciones%202015.pdf

Instituto Nacional de Estadística e Informática. (2026a, 20 de marzo). *Sector Servicios Prestados a Empresas aumentó 3,68 % en enero 2026*. Plataforma del Estado Peruano. https://www.gob.pe/es/institucion/inei/noticias/1368667-sector-servicios-prestados-a-empresas-aumento-3-68-en-enero-2026

Instituto Nacional de Estadística e Informática. (s. f.). *Clasificación Industrial Internacional Uniforme, Revisión 4: Clase 8121, Limpieza general de edificios*. https://proyectos.inei.gob.pe/CIIU/frm_lista_notas.asp?wc_cod=8121

Ministerio de Trabajo y Promoción del Empleo. (2023a, 17 de febrero). *Empresas privadas requerirán más de 348 mil puestos laborales el 2023*. Plataforma del Estado Peruano. https://www.gob.pe/institucion/mtpe/noticias/701438-empresas-privadas-requeriran-mas-de-348-mil-puestos-laborales-el-2023

Ministerio de Trabajo y Promoción del Empleo. (2023b). *Demanda de ocupaciones en Lima Metropolitana 2023: Encuesta de Demanda Ocupacional*. https://cdn.www.gob.pe/uploads/document/file/4921861/Informe%20EDO%20al%202023%20_%20Lima%20Metro.pdf

Ministerio de Trabajo y Promoción del Empleo. (2024). *Informe trimestral del mercado laboral: primer trimestre de 2024*. https://cdn.www.gob.pe/uploads/document/file/6653196/5783668-ite-2024-t1.pdf
