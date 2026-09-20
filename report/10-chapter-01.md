<a id="capitulo-i-presentacion"></a>

# Capítulo I: Presentación

<a id="11-startup-profile"></a>

## 1.1. Startup Profile

<a id="111-descripcion-de-la-startup"></a>

### 1.1.1. Descripción de la Startup.

Opervia es una startup tecnológica orientada a mejorar la gestión del cumplimiento de servicios tercerizados. Su primer producto, Service Compliance, se enfoca en empresas prestadoras de servicios de limpieza B2B que operan dentro de instalaciones de organizaciones cliente y necesitan coordinar la planificación del servicio, la ejecución en campo, la supervisión y la evidencia asociada al trabajo realizado.

Service Compliance busca mantener una relación trazable entre el plan de servicio, las obligaciones que deben cumplirse, la ejecución realizada, la evidencia requerida y el resultado de cumplimiento. De esta manera, supervisores y operarios trabajan sobre una referencia común y la empresa prestadora puede reconstruir qué debía realizarse, qué ocurrió durante la operación y cómo se atendieron las desviaciones detectadas.

**Misión.** Facilitar que las empresas prestadoras de servicios tercerizados gestionen y expliquen el cumplimiento de sus operaciones mediante información trazable, clara y accesible para supervisores y operarios.

**Visión.** Convertir a Opervia en una solución digital especializada en la gestión del cumplimiento de servicios tercerizados, iniciando en el sector de limpieza y consolidando un modelo aplicable a operaciones donde la trazabilidad del servicio sea crítica.

**Propuesta de valor inicial.** Service Compliance permite relacionar lo planificado con lo ejecutado y su evidencia, facilitando la supervisión, la detección de desviaciones, el seguimiento de acciones correctivas y la elaboración de información de cumplimiento para la empresa prestadora y sus clientes.

<a id="112-perfiles-de-integrantes-del-equipo"></a>

### 1.1.2. Perfiles de integrantes del equipo.

El equipo de Opervia reúne conocimientos de análisis de requisitos, desarrollo de software, modelado de dominio, arquitectura, experiencia de usuario e integración de aplicaciones.

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

### 1.2.1. Antecedentes y problemática.

La limpieza general de edificios forma parte de las actividades de servicios administrativos y de apoyo. El Instituto Nacional de Estadística e Informática (INEI) la clasifica en la clase CIIU 8121, que comprende la limpieza general no especializada de oficinas, fábricas, comercios, instituciones y otros establecimientos. En enero de 2026, el INEI reportó crecimiento en esta actividad asociado, entre otros factores, a la ampliación de contratos de limpieza integral en centros comerciales, hospitales, plantas industriales y almacenes (INEI, 2026a; INEI, s. f.).

En este tipo de relación B2B, una empresa prestadora debe convertir las condiciones acordadas con su cliente en un plan de servicio, coordinar personal, ejecutar actividades, verificar resultados y responder ante observaciones o desviaciones. Cuando la información del servicio queda distribuida entre instrucciones, registros, mensajes, fotografías, hojas de cálculo u otros medios, reconstruir el estado de una obligación puede requerir revisar varias fuentes y dificultar la explicación de lo ocurrido.

Opervia aborda específicamente este problema de trazabilidad del cumplimiento. Service Compliance busca conectar la planificación del servicio con las obligaciones operativas, su ejecución, la evidencia requerida y el resultado de cumplimiento, conservando además el historial de excepciones, desviaciones y acciones correctivas.

#### Análisis 5W+2H

| Dimensión | Análisis para Service Compliance |
|---|---|
| **¿Qué ocurre? (WHAT)** | La información necesaria para determinar el cumplimiento de un servicio puede quedar separada entre planificación, instrucciones operativas, registros de ejecución, evidencia y seguimiento de observaciones, dificultando relacionar lo que debía realizarse con lo que efectivamente ocurrió. |
| **¿Quiénes intervienen? (WHO)** | Principalmente la empresa prestadora, sus supervisores/coordinadores y operarios. También participan responsables de operaciones, responsables contractuales y representantes de la organización cliente según el servicio. |
| **¿Dónde ocurre? (WHERE)** | En instalaciones donde una empresa presta servicios de limpieza a otra organización, como oficinas, comercios, instituciones, centros de salud, plantas o almacenes. El alcance inicial del proyecto se concentra en Lima Metropolitana. |
| **¿Cuándo ocurre? (WHEN)** | Durante la planificación, asignación, ejecución y verificación del servicio, así como al atender impedimentos, desviaciones, observaciones del cliente y periodos de consolidación de resultados. |
| **¿Por qué importa? (WHY)** | Una trazabilidad insuficiente aumenta el esfuerzo necesario para supervisar el servicio y dificulta responder con claridad qué se esperaba, qué se realizó, qué evidencia existe y cómo se atendió una desviación. |
| **¿Cómo se manifiesta? (HOW)** | En registros distribuidos, duplicidad de información, cambios difíciles de rastrear, evidencia sin contexto, seguimiento tardío de desviaciones y consolidación manual para explicar o reportar el estado del servicio. |
| **¿Cuánto impacta? (HOW MUCH)** | El impacto se expresa en tiempo dedicado a recopilar y consolidar registros, cantidad de fuentes consultadas para reconstruir un caso, demora en detectar desviaciones y proporción de ejecuciones cuya evidencia puede relacionarse con una obligación concreta. |

##### Puntos principales que debe resolver la solución
Service Compliance debe permitir mantener una referencia común sobre las obligaciones del servicio, registrar lo ocurrido durante su ejecución, conservar la evidencia asociada, identificar desviaciones sin perder el historial original y consolidar información suficiente para supervisar y explicar el cumplimiento.

##### Objetivo de la solución
Diseñar Service Compliance como un producto digital con experiencias móviles que facilite la trazabilidad del cumplimiento de servicios de limpieza tercerizada, relacionando el plan de servicio con las obligaciones operativas, la ejecución realizada, la evidencia requerida y el seguimiento de desviaciones y acciones correctivas.

##### Alcance y restricciones
El alcance inicial se limita a servicios de limpieza tercerizada B2B en Lima Metropolitana y a dos segmentos de usuario: supervisores/coordinadores y operarios de campo. Service Compliance no reemplaza sistemas de nómina, recursos humanos, contabilidad o facturación; tampoco interpreta automáticamente cláusulas legales ni convierte contratos completos en obligaciones sin intervención humana. Los mecanismos de evidencia —como fotografías, ubicación, QR, NFC, checklist o firma— se aplican según las condiciones definidas para cada obligación y no como requisitos universales del producto.

<a id="122-lean-ux-process"></a>

#### 1.2.2. Lean UX Process

A partir de la problemática identificada se aplicó Lean UX para formular el Problem Statement, los assumptions del modelo de negocio, los Hypothesis Statements y el Lean UX Canvas de Service Compliance.

#### 1.2.2.1. Lean UX Problem Statements

**The current state of the domain we are working in has focused mainly on:** la coordinación de servicios de limpieza tercerizada mediante supervisión operativa, comunicación directa y registros distribuidos entre diferentes medios. Los principales usuarios involucrados son supervisores/coordinadores y operarios de la empresa prestadora, quienes necesitan ejecutar y verificar actividades dentro de instalaciones de clientes.

**What existing products/services fail to address is:** una trazabilidad integrada y centrada en cumplimiento que relacione el plan de servicio, la obligación concreta, la ejecución realizada, la evidencia requerida y el resultado de cumplimiento, conservando además el contexto de desviaciones y acciones correctivas.

**Our product/service will address this gap by:** ofrecer Service Compliance como un producto digital orientado a experiencias móviles que conecta planificación, obligaciones, ejecución, evidencia, evaluación del cumplimiento y seguimiento correctivo dentro de una misma cadena de información.

**Our initial focus will be:** supervisores/coordinadores de servicios de limpieza tercerizada y operarios de campo de empresas prestadoras ubicadas inicialmente en Lima Metropolitana.

**We’ll know we are successful when we see:** menor tiempo y menor cantidad de fuentes necesarias para determinar el estado de una obligación; mayor proporción de ejecuciones relacionadas con su obligación y evidencia requerida; detección más temprana de desviaciones relevantes; y registros de campo completados sin interferir de forma significativa con la actividad principal del operario.


#### 1.2.2.2. Lean UX Assumptions

##### Business Assumptions

| ID | Business Assumption |
|---|---|
| BA-01 | Creemos que las empresas prestadoras de limpieza tercerizada perciben valor económico en mejorar la trazabilidad del cumplimiento frente a sus clientes. |
| BA-02 | Creemos que el comprador de Service Compliance puede ser un responsable de operaciones, administración o dirección de la empresa prestadora, distinto de los usuarios que ejecutan y supervisan el servicio. |
| BA-03 | Creemos que Service Compliance puede diferenciarse al relacionar explícitamente planificación, obligaciones, ejecución, evidencia y resultado de cumplimiento, en lugar de gestionar actividades como tareas aisladas. |
| BA-04 | Creemos que comenzar por el vertical de limpieza permite construir una propuesta suficientemente especializada antes de extender el producto a otros servicios tercerizados. |
| BA-05 | Creemos que un plan base cercano a S/300 mensuales puede ser viable para una empresa prestadora cuando el valor recuperado por reducción de tiempo operativo y administrativo sea claramente superior al precio del servicio. |

##### Business Outcome Assumptions

| ID | Business Outcome Assumption | Indicador propuesto | Criterio de éxito preliminar |
|---|---|---|---|
| BO-01 | Creemos que Service Compliance reducirá el esfuerzo necesario para reconstruir y explicar el estado de cumplimiento de una obligación. | Tiempo medio y cantidad de fuentes utilizadas para reconstruir un caso. | El proceso con Service Compliance requiere menos tiempo o menos fuentes que el proceso actual. |
| BO-02 | Creemos que Service Compliance aumentará la trazabilidad entre obligación, ejecución y evidencia requerida. | Porcentaje de obligaciones cerradas con registro y evidencia vinculados. | La proporción de obligaciones trazables con la solución supera la línea base del proceso actual. |
| BO-03 | Creemos que Service Compliance permitirá detectar desviaciones relevantes con mayor anticipación. | Porcentaje de desviaciones identificadas antes de una observación del cliente o del cierre del periodo. | La proporción de detecciones tempranas aumenta respecto del proceso actual. |
| BO-04 | Creemos que Service Compliance reducirá el trabajo manual de consolidación para supervisión y elaboración de reportes. | Tiempo y cantidad de pasos necesarios para consolidar información. | La consolidación con la solución requiere menos tiempo o menos pasos que el proceso actual. |

##### User Assumptions
UA-01. Creemos que los supervisores/coordinadores necesitan conocer qué obligaciones están pendientes, realizadas, observadas, exceptuadas o vencidas dentro del servicio que supervisan.

UA-02. Creemos que los operarios necesitan instrucciones comprensibles sobre qué actividad realizar, dónde, cuándo y qué evidencia debe acompañar el resultado.

UA-03. Creemos que los supervisores combinan observación directa, comunicación con el personal y registros operativos para controlar el servicio y responder ante observaciones.

UA-04. Creemos que los operarios presentan distintos niveles de familiaridad digital y que un flujo de registro complejo puede generar fricción o registros incompletos.

UA-05. Creemos que supervisores y operarios necesitan compartir una referencia operativa común aunque las decisiones contractuales y comerciales correspondan a otros roles.

##### User Outcome and Benefit Assumptions
UO-01. Creemos que los supervisores quieren identificar rápidamente qué obligaciones requieren su atención sin reconstruir el estado desde varias fuentes.

UO-02. Creemos que los supervisores quieren consultar el historial de una obligación cuando existe una observación, desviación o reclamo.

UO-03. Creemos que los operarios quieren comprender con claridad qué deben ejecutar y registrar el resultado con la menor carga adicional posible.

UO-04. Creemos que los operarios quieren comunicar impedimentos o excepciones para que una ejecución incompleta conserve su contexto.

UO-05. Creemos que los supervisores/coordinadores quieren disponer de información consistente para explicar qué ocurrió, cómo se evaluó y qué acciones se realizaron.

##### Feature Assumptions
FA-01. Creemos que representar un plan de servicio con obligaciones asociadas a ubicación, frecuencia, ventana de ejecución y criterios de aceptación ayudará a supervisores y operarios a compartir una referencia operativa común.

FA-02. Creemos que registrar la ejecución desde una experiencia móvil y vincularla directamente con su obligación y evidencia requerida reducirá la pérdida de contexto entre campo y supervisión.

FA-03. Creemos que registrar excepciones y desviaciones, diferenciarlas del incumplimiento cuando corresponda y conservar las acciones correctivas sin reemplazar el historial original permitirá explicar posteriormente qué ocurrió y cómo se respondió.

FA-04. Creemos que una vista de cumplimiento y reportes trazables por servicio, ubicación y periodo reducirá el trabajo manual de consolidación de los supervisores.

FA-05. Creemos que el almacenamiento local temporal y la sincronización posterior reducirán la pérdida de registros en zonas con conectividad limitada.

Los mecanismos de evidencia pueden variar según la obligación e incluir fotografías, ubicación, QR, NFC, checklist, firma u otras formas de verificación.

#### 1.2.2.3. Lean UX Hypothesis Statements

Se formula un Hypothesis Statement por cada Feature Assumption.

**- HS-01. Plan de servicio y obligaciones**

**We believe we will achieve:** una reducción del esfuerzo necesario para coordinar y explicar el estado del servicio (BO-01).
**If:** supervisores/coordinadores y operarios (UA-01, UA-02, UA-05).
**Attain:** una referencia compartida sobre qué debe realizarse, dónde, cuándo y bajo qué criterio (UO-01, UO-03).
**With:** un plan de servicio con obligaciones estructuradas y relacionadas con las condiciones operativas relevantes (FA-01).

**- HS-02. Ejecución y evidencia**

**We believe we will achieve:** una mayor proporción de obligaciones con ejecución y evidencia trazables (BO-02).
**If:** operarios y supervisores (UA-02, UA-04).
**Attain:** una forma rápida y comprensible de registrar el resultado sin reconstruir posteriormente su contexto (UO-03).
**With:** un registro móvil de ejecución vinculado directamente con la obligación y la evidencia requerida (FA-02).

**- HS-03. Excepciones, desviaciones y acciones correctivas**

**We believe we will achieve:** una detección y respuesta más temprana ante desviaciones relevantes (BO-03).
**If:** supervisores y operarios (UA-01, UA-02).
**Attain:** la capacidad de comunicar una excepción, conocer su evaluación y conservar la respuesta realizada (UO-01, UO-04, UO-05).
**With:** un flujo que registre excepciones y desviaciones, permita determinar el resultado de cumplimiento y conserve las acciones correctivas sin reemplazar el historial original (FA-03).

**- HS-04. Estado de cumplimiento y reportes**

**We believe we will achieve:** una reducción del trabajo manual de consolidación y explicación del cumplimiento (BO-01, BO-04).
**If:** supervisores/coordinadores (UA-01, UA-03).
**Attain:** acceso directo al estado e historial de las obligaciones relevantes y capacidad de explicar qué ocurrió (UO-01, UO-02, UO-05).
**With:** una vista de cumplimiento y reportes trazables por servicio, ubicación y periodo (FA-04).

**- HS-05. Continuidad ante conectividad limitada**

**We believe we will achieve:** una mayor proporción de registros de ejecución completos (BO-02).
**If:** los operarios de campo (UA-02, UA-04).
**Attain:** la capacidad de registrar una ejecución aun cuando la conectividad inmediata sea insuficiente (UO-03).
**With:** almacenamiento local temporal y sincronización posterior controlada (FA-05).

#### 1.2.2.4. Lean UX Canvas

El Lean UX Canvas resume el problema de negocio, resultados esperados, usuarios, beneficios, soluciones e hipótesis principales de Service Compliance.

| **1. Business Problem** | **2. Business Outcomes** |
|---|---|
| Las empresas prestadoras pueden perder trazabilidad cuando planificación, obligaciones, ejecución, evidencia y seguimiento quedan distribuidos entre diferentes medios, aumentando el esfuerzo necesario para determinar y explicar el cumplimiento. | Reducir el esfuerzo de reconstrucción y consolidación; aumentar la trazabilidad de las obligaciones; detectar desviaciones con mayor anticipación; reducir el trabajo manual de elaboración de reportes. |
| **3. Users / Customer Segments** | **4. User Outcomes & Benefits** |
| **Cliente organizacional:** empresa prestadora de limpieza.<br><br>**Usuarios objetivo:** supervisores/coordinadores y operarios de limpieza tercerizada. | **Supervisores:** identificar qué requiere atención, consultar historial y explicar el servicio.<br><br>**Operarios:** comprender qué ejecutar, registrar el resultado con baja fricción y comunicar excepciones. |
| **5. Solutions** | **6. Hypotheses** |
| Plan de servicio y obligaciones; registro móvil de ejecución; evidencia asociada a cada obligación; gestión de excepciones y desviaciones; seguimiento de acciones correctivas; estado de cumplimiento y reportes; almacenamiento local y sincronización. | HS-01: plan y obligaciones.<br>HS-02: ejecución y evidencia.<br>HS-03: excepciones, desviaciones y correctivas.<br>HS-04: cumplimiento y reportes.<br>HS-05: continuidad con conectividad limitada. |
| **7. Most Important Thing to Learn First** | **8. Least Amount of Work to Learn It** |
| Determinar si centralizar la trazabilidad del servicio reduce de forma significativa el esfuerzo de supervisión y registro para los dos segmentos objetivo. | Contrastar los flujos principales mediante entrevistas, observación del proceso actual y un prototipo de baja fidelidad centrado en planificación, ejecución, evidencia y cumplimiento. |

<sub>Tabla 3. Lean UX Canvas de Service Compliance.</sub>

<a id="13-segmentos-objetivo"></a>

## 1.3. Segmentos objetivo

Service Compliance considera dos segmentos objetivo: supervisores/coordinadores y operarios de empresas prestadoras de servicios de limpieza tercerizada. Ambos participan directamente en la operación, pero tienen responsabilidades y necesidades diferentes, por lo que se describen de manera independiente.

### 1.3.1. Supervisores y coordinadores de servicios de limpieza tercerizada

Este segmento agrupa a las personas responsables de organizar, coordinar y supervisar la ejecución de actividades de limpieza dentro de las instalaciones atendidas por la empresa prestadora. El Clasificador Nacional de Ocupaciones 2015 identifica la ocupación 3131 — Supervisores de mantenimiento y limpieza en oficinas, hoteles y otros establecimientos, entre cuyas tareas se encuentran supervisar al personal de limpieza, controlar suministros y verificar el correcto desempeño de las actividades asignadas (INEI, 2015).

Para Service Compliance, el supervisor/coordinador es el usuario encargado de revisar el estado operativo del servicio, identificar obligaciones que requieren atención, consultar registros y evidencia y dar seguimiento a desviaciones o acciones correctivas.

**Características del segmento:**

- **Ubicación inicial:** Lima Metropolitana.

- **Rol laboral:** supervisión, coordinación y control del trabajo de limpieza y del personal asignado.

- **Edad:** población adulta en edad laboral; las fuentes oficiales revisadas no ofrecen una distribución reciente específica para la ocupación CNO 3131.

- **Género:** participación de hombres y mujeres; no se atribuye una proporción específica sin estadística ocupacional directa.

- **Formación y experiencia:** variables según la empresa, instalación y complejidad del servicio.

La existencia de una clasificación ocupacional específica para supervisores de mantenimiento y limpieza confirma que se trata de un rol diferenciado dentro del dominio y con responsabilidades distintas a las del personal de ejecución (INEI, 2015).

### 1.3.2. Operarios de limpieza tercerizada

Este segmento comprende a las personas que ejecutan directamente actividades de limpieza en oficinas, establecimientos comerciales, instituciones y otras instalaciones. El Clasificador Nacional de Ocupaciones 2015 identifica la ocupación 9112 — Limpiadores y asistentes de oficinas, hoteles y otros establecimientos, cuyas tareas incluyen limpieza de pisos, mobiliario, servicios higiénicos y otras áreas del establecimiento (INEI, 2015).

En el primer trimestre de 2024, el MTPE reportó un promedio de 49 653 trabajadores formales privados en esta ocupación. Entre los registros con característica identificada, 55 % correspondía a mujeres y 37 % a hombres; 64 % a adultos de 30 a 59 años y 20 % a jóvenes de 15 a 29 años. Además, 98 % fue clasificado como trabajador no calificado según la metodología ocupacional utilizada por la fuente (MTPE, 2024).

**Características del segmento:**

- **Ubicación inicial:** Lima Metropolitana.

- **Edad:** predominio de adultos de 30 a 59 años (64 % de los registros reportados para 2024 T1); 20 % correspondía a jóvenes de 15 a 29 años (MTPE, 2024).

- **Género:** 55 % de mujeres y 37 % de hombres en los registros formales privados analizados; la fuente presenta registros sin característica determinada (MTPE, 2024).

- **Nivel educativo y calificación:** la ocupación fue clasificada en 98 % como trabajo no calificado bajo la metodología del informe. La EDO para Lima Metropolitana proyectó 2 530 nuevos puestos de esta ocupación con secundaria completa como nivel educativo mínimo para 2023 (MTPE, 2023b).

- **Entorno de trabajo:** actividad física y presencial, con desplazamiento entre zonas y cumplimiento de tareas dentro de turnos o ventanas operativas.


## Referencias

Instituto Nacional de Estadística e Informática. (2015). _Clasificador Nacional de Ocupaciones 2015._ https://cdn.www.gob.pe/uploads/document/file/4123438/Clasificador%20Nacional%20de%20Ocupaciones%202015.pdf

Instituto Nacional de Estadística e Informática. (2026a, 20 de marzo). _Sector Servicios Prestados a Empresas aumentó 3,68 % en enero 2026. Plataforma del Estado Peruano._ https://www.gob.pe/es/institucion/inei/noticias/1368667-sector-servicios-prestados-a-empresas-aumento-3-68-en-enero-2026

Instituto Nacional de Estadística e Informática. (s. f.). _Clasificación Industrial Internacional Uniforme, Revisión 4: Clase 8121, Limpieza general de edificios._ https://proyectos.inei.gob.pe/CIIU/frm_lista_notas.asp?wc_cod=8121

Ministerio de Trabajo y Promoción del Empleo. (2023b). _Demanda de ocupaciones en Lima Metropolitana 2023: Encuesta de Demanda Ocupacional._ https://cdn.www.gob.pe/uploads/document/file/4921861/Informe%20EDO%20al%202023%20_%20Lima%20Metro.pdf

Ministerio de Trabajo y Promoción del Empleo. (2024). _Informe trimestral del mercado laboral: primer trimestre de 2024._ https://cdn.www.gob.pe/uploads/document/file/6653196/5783668-ite-2024-t1.pdf