<a id="capitulo-ii-requirements-development-and-software-solution-design"></a>

# Capítulo II: Requirements Development and Software Solution Design

Este capítulo transforma la investigación del dominio en requisitos y decisiones de diseño de software para **Service Compliance**. La secuencia utilizada es: análisis competitivo → entrevistas → Needfinding → especificación de requisitos → diseño estratégico con Domain-Driven Design → diseño táctico. El objetivo es mantener trazabilidad entre el problema planteado en el Capítulo I, la evidencia recolectada y las decisiones posteriores, evitando convertir hipótesis de producto en requisitos sin sustento.

<a id="21-competidores"></a>

## 2.1. Competidores

Se analizaron tres productos digitales relacionados con el control de servicios en instalaciones, la ejecución en campo y la verificación del trabajo: **eGenya**, **OrangeQC** y **ServiceChannel**. La selección combina un competidor regional cercano al control de servicios tercerizados y dos soluciones internacionales con capacidades de inspección, órdenes de trabajo, evidencias y gestión de proveedores.

La comparación se realiza desde la perspectiva definida para Service Compliance en el Capítulo I: en esta primera iteración, la **empresa prestadora de limpieza** es el cliente organizacional y comprador potencial; los **supervisores/coordinadores** y **operarios** de la prestadora son los segmentos de usuario; la organización que recibe el servicio es un stakeholder que puede formular observaciones o recibir explicaciones y reportes.

<a id="211-analisis-competitivo"></a>

### 2.1.1. Análisis competitivo

**Objetivo del análisis.** Determinar hasta qué punto productos existentes ya resuelven la trazabilidad del servicio y qué espacio de diferenciación puede defender Opervia sin basarse únicamente en funcionalidades genéricas como fotografías, QR, GPS, checklists o dashboards.


#### Competitive Analysis Landscape

| Aspecto | Service Compliance | eGenya | OrangeQC | ServiceChannel |
|---|---|---|---|---|
| **Tipo de competidor** | Startup académica / propuesta propia. | Directo o cercano: gestión de servicios no operacionales y Facility Management con contratistas y equipos propios. | Indirecto especializado: control de calidad, inspecciones y validación de servicios de limpieza. | Indirecto empresarial: Facility Management, proveedores, work orders y cumplimiento en múltiples sedes. |
| **Overview** | Producto orientado a empresas prestadoras de limpieza tercerizada. Busca conservar una cadena trazable desde las condiciones del servicio y el plan operativo hasta la obligación, ejecución, evidencia, evaluación de cumplimiento, desviación y acción correctiva. | Plataforma chilena para gestionar servicios generales y Facility Management. Comunica trazabilidad de servicios ejecutados por prestadores o equipos propios, control por zonas, tareas preventivas y visibilidad operativa. | Plataforma de control de calidad e inspecciones para servicios de limpieza y facilities. Permite formularios configurables, inspecciones, checklists, tickets, acciones correctivas, reportes y operación móvil. | Plataforma empresarial de Facility Management que centraliza órdenes de trabajo, proveedores, mantenimiento, documentación, auditorías, analítica y operaciones de campo. |
| **Valor ofrecido** | Explicar el cumplimiento de un servicio conectando **qué debía cumplirse**, **qué se ejecutó**, **qué evidencia era requerida**, **cómo se evaluó** y **qué ocurrió después de una desviación**, sin borrar el historial original. | Saber si equipos o proveedores cumplen lo comprometido y visualizar el estado de servicios y zonas en tiempo real. | Estandarizar y demostrar calidad mediante inspecciones digitales, evidencias, tickets y seguimiento de acciones correctivas. | Coordinar el ciclo de trabajo con proveedores y sedes, documentar el servicio, controlar desempeño y mantener trazabilidad operativa a escala empresarial. |
| **Mercado objetivo** | Empresas prestadoras de servicios de limpieza tercerizada, inicialmente con operaciones en Lima Metropolitana. Usuarios: supervisores/coordinadores y operarios. | Organizaciones y áreas de servicios generales, Facility Management y operaciones que controlan servicios propios o tercerizados. | Building Service Contractors, instalaciones educativas, salud, municipios, aeropuertos, property/facility managers y equipos de control de calidad. | Operadores multi-sede y equipos de facilities en retail, restaurantes, supermercados, hoteles, educación, salud y otros sectores; también proveedores externos. |
| **Estrategia de marketing** | Validación mediante pilotos con prestadoras, comunicación centrada en reducción de reconstrucción manual, trazabilidad del cumplimiento y simplicidad de uso para campo. | Demostraciones, casos y comunicación enfocada en dejar de operar “a ciegas”, control remoto, datos y cumplimiento de servicios. | Prueba gratuita, demostraciones, contenido especializado y casos orientados a control de calidad, limpieza y auditorías. | Demostraciones, casos empresariales y una propuesta de plataforma integral para optimizar facilities y redes de proveedores. |
| **Productos y servicios** | Dos experiencias móviles: app nativa Android para operarios y app cross-platform para supervisores; REST API; trazabilidad de Service Plan/obligaciones, ejecución, evidencia configurable, compliance, acciones correctivas y reporting. | Registro y seguimiento de actividades, puntos QR, control preventivo/correctivo, monitoreo por zonas, reportes y trazabilidad de prestadores y equipos. | Inspecciones móviles online/offline, checklists, GPS/timestamps, fotografías, tickets, acciones correctivas, programación y reportes. También posee validación de servicio mediante checklists/QR. | Work orders, proveedor móvil, check-in/check-out, fotos y documentación, firmas, auditorías, mantenimiento, proveedores, cumplimiento, analítica y aprobaciones. |
| **Precios y costos** | **Hipótesis pendiente de validación.** No se fija aún un precio final. Debe definirse la unidad de cobro —por sede, usuarios, obligaciones o plan— y la disposición de pago mediante investigación comercial. | La página pública orienta la contratación a contacto comercial y demostración; no se utiliza una tarifa pública estándar en este análisis. | Publica Starter de **US$250/mes** para 2 inspectores, Standard de **US$500/mes** para 10 inspectores y plan Custom; también ofrece un módulo adicional de Service Validation. | La contratación pública revisada se orienta a consulta/demostración y alcance del servicio; no se utiliza una tarifa estándar en este análisis. |
| **Canales de distribución** | Aplicaciones móviles, Landing Page y pilotos directos con empresas prestadoras. | Plataforma web y uso móvil/QR por equipos de terreno; contacto comercial. | Apps iOS/Android, web, prueba gratuita y demostraciones. | Plataforma web, ServiceChannel Mobile y Provider App; venta empresarial y demos. |
| **Fortalezas** | Especialización en trazabilidad de cumplimiento y preservación de la relación entre Service Plan, obligación, ejecución, evidencia y Compliance Result. Alcance pequeño y orientado a un flujo concreto. | Cercanía regional, propuesta en español y fuerte relación con servicios tercerizados, trazabilidad y control de prestadores. | Especialización reconocible en limpieza, inspecciones, offline, evidencia, tickets y acciones correctivas. | Madurez funcional, red de proveedores, operación multi-sede y documentación de trabajo en campo. |
| **Debilidades** | Producto sin clientes, precio, product-market fit ni reglas definitivas de evidencia. La ventaja competitiva todavía debe demostrarse frente a soluciones que ya cubren ejecución e inspección. | Su alcance cubre varios servicios y no evidencia en la información pública revisada una especialización explícita en traducir condiciones/planes de servicio a un historial de Compliance Result. | Su centro de gravedad es inspección y control de calidad; no necesariamente el ciclo completo desde condiciones del servicio y planificación hasta evaluación contractual. | Amplia cobertura y complejidad empresarial que puede exceder las necesidades de una prestadora de limpieza que busca un flujo de cumplimiento más acotado. |
| **Oportunidades** | Especialización vertical, adaptación al contexto peruano, configuración de evidencia por obligación, menor fricción operativa y reporting explicable al cliente. | Expansión regional y digitalización de servicios no operacionales. | Mayor demanda de evidencia, auditoría y transparencia de calidad. | Digitalización de Facility Management, optimización de proveedores y operaciones multi-sede. |
| **Amenazas** | Competidores maduros ya ofrecen fotos, GPS, QR, offline, tickets y reportes; WhatsApp/Excel pueden seguir siendo “suficientes”; la evidencia válida puede variar por contrato; el buyer puede no ser quien inicialmente se supone. | Competidores globales y verticales especializados. | Plataformas de Facility Management más amplias y soluciones regionales en español. | Soluciones verticales más simples y económicas; costo y complejidad de adopción. |

**Conclusión del Landscape.** La oportunidad de Opervia no se sostiene en afirmar que funcionalidades como QR, fotografías, GPS u operación offline sean innovadoras: los competidores revisados ya ofrecen varias de ellas. La diferenciación candidata se concentra en la **trazabilidad de cumplimiento**: conservar una cadena explicable entre condiciones del servicio, Service Plan, Service Obligation, Execution, Evidence Requirement, Compliance Evaluation, Compliance Result y Corrective Action. Esta diferenciación debe validarse comercialmente y con usuarios antes de considerarse una ventaja comprobada.

<a id="212-estrategias-y-tacticas-frente-a-competidores"></a>

### 2.1.2. Estrategias y tácticas frente a competidores

A partir del Landscape y del alcance del Capítulo I, Opervia plantea las siguientes estrategias preliminares:

1. **Especialización en compliance operativo, no en cantidad de módulos.** La solución prioriza explicar el estado de cumplimiento de un servicio por encima de competir como suite general de Facility Management.
   - Táctica: modelar explícitamente **Service Conditions → Service Plan → Service Obligation → Execution → Compliance Result**.
   - Táctica: conservar el estado original de una desviación o incumplimiento aun cuando exista una acción correctiva posterior.
   - Táctica: mantener fuera del MVP nómina, contabilidad, RR. HH., procurement, activos y administración genérica de proyectos.

2. **Evidencia configurable en lugar de un mecanismo universal.** OrangeQC, eGenya y ServiceChannel muestran que QR, GPS y fotografías son tecnologías comunes; por ello Service Compliance no debe depender de una única prueba.
   - Táctica: cada Obligation Definition especifica su **Evidence Requirement** cuando corresponda.
   - Táctica: permitir foto, checklist, firma, observación u otros mecanismos según el Service Plan, sin exigir siempre todos los tipos.
   - Táctica: tratar QR/NFC/GPS como alternativas de implementación, no como la propuesta de valor.

3. **Experiencias móviles diferenciadas por contexto de uso.** El operario necesita baja fricción y continuidad en campo; el supervisor necesita visibilidad, revisión y seguimiento.
   - Táctica: aplicación Android nativa para operarios, con almacenamiento local y acceso a cámara cuando la obligación lo requiera.
   - Táctica: aplicación cross-platform para supervisores/coordinadores, enfocada en planificación operativa, revisión, compliance y reporting.

4. **Adopción por pilotos y medición de outcomes.** El precio y la viabilidad no se fijan por intuición.
   - Táctica: ejecutar pilotos de alcance reducido con una empresa prestadora.
   - Táctica: medir tiempo de reconstrucción, completitud de registros, detección de desviaciones y fricción del registro de campo.
   - Táctica: validar la unidad de cobro y disposición de pago antes de cerrar pricing.

<a id="22-entrevistas"></a>

## 2.2. Entrevistas

La investigación con usuarios se dirige a los dos segmentos definidos en el Capítulo I: **operarios de limpieza tercerizada** y **supervisores/coordinadores de servicios de limpieza tercerizada**. Las entrevistas buscan comprender el proceso actual, las características objetivas y subjetivas necesarias para construir los User Personas y, especialmente, identificar evidencia que confirme o refute los assumptions de Lean UX.

### 2.2.1. Diseño de entrevistas

Las preguntas se plantean de forma semiestructurada. Se privilegian experiencias recientes y comportamientos reales antes que opiniones sobre una solución propuesta. Las preguntas de perfil cubren los elementos requeridos para los arquetipos: edad, distrito, ocupación, biografía, objetivos, frustraciones, personalidad, habilidades, dispositivos, canales digitales, influencias y hábitos tecnológicos.

#### Segmento 1: Operarios de limpieza tercerizada

**Objetivo.** Comprender cómo reciben y ejecutan instrucciones, cómo comunican resultados o excepciones, qué evidencia utilizan hoy, qué fricciones aparecen durante el turno y qué restricciones tecnológicas existen en campo.

**Preguntas principales**

- ¿Cuál es tu nombre, edad, distrito de residencia y ocupación actual?
- ¿Cuánto tiempo llevas trabajando en limpieza y cuánto tiempo llevas en tu sede o empresa actual?
- Cuéntame paso a paso cómo transcurre un turno normal desde que llegas hasta que terminas.
- ¿Cómo sabes qué áreas o actividades te corresponde realizar y en qué momento?
- Cuéntame la última vez que cambiaron tu zona, turno o prioridad durante la jornada. ¿Cómo te enteraste y qué hiciste?
- Cuando terminas una actividad, ¿cómo comunicas que fue realizada?
- ¿En qué situaciones te piden fotografías, firmas, checklists u otra evidencia? ¿Quién decide qué evidencia se necesita?
- Cuéntame una ocasión reciente en la que no pudiste completar una actividad. ¿Cómo explicaste el motivo?
- ¿Alguna vez hubo una discusión sobre si una actividad realmente se había realizado o si estaba bien hecha? ¿Cómo se resolvió?
- ¿Qué partes del proceso actual te quitan más tiempo o generan más confusión?
- ¿Cómo es la conectividad dentro de las instalaciones donde trabajas? ¿En qué zonas suele fallar?
- ¿Utilizas un teléfono propio o de la empresa? ¿Qué aplicaciones y canales digitales utilizas con mayor frecuencia?
- Cuando necesitas aprender algo nuevo, ¿a quién o qué medio recurres normalmente?
- Si pudieras cambiar una sola cosa del proceso actual de coordinación o registro, ¿qué cambiarías y por qué?

**Preguntas complementarias**

- ¿Qué nivel educativo alcanzaste y qué tipo de capacitaciones has recibido en el trabajo?
- ¿Con quién vives o tienes personas que dependan de ti? *(solo si el participante se siente cómodo respondiendo)*.
- ¿Qué tres palabras usarías para describirte cuando trabajas?
- ¿Qué marcas, aplicaciones o servicios digitales te resultan familiares o confiables?
- ¿Qué te motiva en el trabajo y qué objetivos personales o profesionales tienes?

#### Segmento 2: Supervisores/coordinadores

**Objetivo.** Comprender cómo se planifica y supervisa el servicio, cómo se controla el cumplimiento, cómo se gestionan evidencias y observaciones del cliente, qué información se consolida manualmente y cómo se atienden desviaciones.

**Preguntas principales**

- ¿Cuál es tu nombre, edad, distrito de residencia y cargo actual?
- ¿Cómo llegaste al rol de supervisión y cuánto tiempo llevas trabajando en el rubro?
- ¿Cuántas sedes, turnos o personas supervisas actualmente?
- Cuéntame paso a paso cómo organizas un día normal de supervisión.
- ¿De dónde provienen las instrucciones que finalmente recibe el operario: contrato, plan de trabajo, cronograma, carta de servicio, indicación del cliente u otra fuente?
- ¿Quién decide frecuencia, horario, zona, prioridad y evidencia requerida para una actividad?
- Cuéntame la última vez que una actividad importante quedó pendiente o se realizó de forma incorrecta. ¿Cómo te enteraste?
- ¿Cómo verificas actualmente que una actividad fue realizada y con qué criterios decides si el resultado es aceptable?
- ¿Qué sucede cuando el cliente observa o reclama una actividad que el equipo consideraba completada?
- ¿Cómo recopilas y organizas fotos, firmas, formatos, reportes u otras evidencias?
- ¿Cuánto tiempo empleas en consolidar información o reconstruir un caso cuando necesitas explicarlo?
- ¿Cómo haces seguimiento a una desviación hasta que se atiende? ¿La corrección reemplaza el registro del problema original o ambos quedan documentados?
- ¿Qué información necesitarías para responder rápidamente “qué ocurrió, quién intervino y cómo se cerró”?
- ¿Qué dispositivos, aplicaciones, hojas de cálculo o canales de mensajería utilizas habitualmente?
- Si pudieras eliminar una sola fricción del proceso de supervisión actual, ¿cuál sería y por qué?

**Preguntas complementarias**

- ¿Cuál es tu formación y qué habilidades consideras más importantes para el cargo?
- ¿Cómo describirías tu estilo de trabajo y tu personalidad?
- ¿Qué herramientas o marcas digitales utilizas con frecuencia?
- ¿Dónde aprendes nuevas prácticas o herramientas para tu trabajo?
- ¿Quién decide comprar o implantar software para este proceso en tu empresa?
- ¿Qué tendría que demostrar una nueva herramienta para justificar pagar por ella?

### 2.2.2. Registro de entrevistas

El enunciado requiere **3 a 5 entrevistas por cada segmento**. A continuación se conservan las entrevistas ya realizadas. Las entrevistas restantes deben añadirse con la misma estructura y posteriormente debe actualizarse el análisis estadístico.

#### Segmento 1: Operarios de limpieza tercerizada

##### Entrevista #1 — José Ramírez

<img src="resources/10-chapter-01/Entrevista1.png">

| Campo | Detalle |
|---|---|
| **Entrevistador** | Carlos Franco Blancas Chávez |
| **Entrevistado** | José Ramírez |
| **Edad** | 32 años |
| **Ubicación** | San Juan de Lurigancho / edificio de oficinas |
| **Duración** | 12:50 minutos |
| **Enlace** | https://youtu.be/BublVzjOtw0 |
| **Timing en video consolidado** | |

**Resumen.** José Ramírez tiene 6 años trabajando en servicios de limpieza y actualmente se desempeña como jefe de operarios, participando en la coordinación de su equipo. Describe que la asignación de zonas y cambios operativos se comunica principalmente por WhatsApp, lo que puede provocar mensajes cruzados, duplicidad de asignaciones o zonas sin cubrir. La evidencia de ejecución también se maneja mediante mensajes y fotografías en WhatsApp; José está habituado a este mecanismo y no lo considera necesariamente tedioso, pero el contenido queda mezclado con otras conversaciones y no asociado estructuralmente a una obligación concreta. Ante situaciones fuera de su alcance, como daños en la infraestructura, existe escalamiento hacia responsables de seguridad o riesgos. La conectividad suele ser suficiente, aunque identifica menor señal en el sótano. Al plantearse cómo mejoraría el proceso, propuso centralizar tareas, estado y evidencia en una herramienta consultable. La entrevista aporta evidencia preliminar a FA-01, FA-02 y FA-05, pero también muestra que **WhatsApp puede resultar aceptable para el operario**, por lo que la solución deberá demostrar un beneficio superior a la fricción de adoptar otra herramienta.

##### Entrevista #2 — Juan Antonio Sánchez Cuadrado

<img src="/report/resources/11-chapter-02/evidencia-entrevista-segmento1-juan.jpeg">

| Campo | Detalle |
|---|---|
| **Entrevistador** | Angel Thyago Flores Eusebio |
| **Entrevistado** | Juan Antonio Sánchez Cuadrado |
| **Edad** | 21 años |
| **Ubicación** | Los Olivos / edificio de oficinas |
| **Duración** | 13:37 minutos |
| **Enlace** | [Entrevista a Juan Sánchez Cuadrado](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20231b781_upc_edu_pe/IQCjpy9muvkaT5sGZ22ewJkIAcbVqQm_IYAxXWDR5OwH2AA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=NUm4gC) |
| **Timing en video consolidado** | |

**Resumen.** Juan Antonio Sánchez Cuadrado tiene un año y medio de experiencia en servicios de limpieza. Reporta falta de claridad sobre prioridades, cambios de tareas comunicados por WhatsApp o verbalmente y problemas de coordinación cuando falta un compañero. Las evidencias se registran de manera selectiva: para áreas importantes u observadas toma fotografías y las envía a un grupo de WhatsApp. Explica que las imágenes pueden mezclarse con las de otros trabajadores y perder contexto de lugar o momento. Cuando existe un impedimento —por ejemplo, espacio ocupado o daño ajeno al servicio— avisa al supervisor o registra la situación. También describe conectividad limitada en almacenes, sótanos y estacionamientos, donde mensajes pueden quedar pendientes. Como mejora propone una herramienta sencilla que muestre qué le corresponde hacer, permita registrar la finalización y solicite evidencia solo cuando corresponda. La entrevista aporta evidencia preliminar a UA-02, UA-04, FA-01, FA-02, FA-03 y FA-05.


#### Segmento 2: Supervisores/coordinadores

##### Entrevista #1 — Ivonne Beatriz Ibañez Torres

<img src="resources/10-chapter-01/Entrevista2.png">

| Campo | Detalle |
|---|---|
| **Entrevistador** | Carlos Franco Blancas Chávez |
| **Entrevistado** | Ivonne Beatriz Ibañez Torres |
| **Edad** | 36 años |
| **Ubicación** | San Martín de Porres / supervisa 4 sedes |
| **Duración** | 8:51 minutos |
| **Enlace** | https://youtu.be/9wKQs6Vbq0o |
| **Timing en video consolidado** | |

**Resumen.** Ivonne tiene 8 años de experiencia en limpieza tercerizada y pasó de operaria a encargada de grupo y luego a supervisora. Coordina 4 sedes y aproximadamente 35 personas. Señala una alta dependencia de WhatsApp para conocer el estado de la operación y recopilar fotografías e informes. Describe casos en los que se entera de un problema a partir del reclamo del cliente y debe contactar a responsables para reconstruir qué ocurrió; en el caso relatado, necesitó aproximadamente 30–40 minutos para entender la situación. También estima entre 4 y 5 horas semanales para consolidar información recibida por WhatsApp y trasladarla a Excel, según la cantidad de incidentes. Usa principalmente celular durante su movilidad y laptop para Excel; entre sus herramientas menciona WhatsApp, Excel, Google Drive y Google Calendar. La entrevista aporta evidencia preliminar a BO-01, BO-03 y BO-04 y respalda la necesidad de investigar un estado operativo consolidado y una historia trazable de las obligaciones.

##### Entrevista #2 — Andy

<img src="resources/10-chapter-01/Entrevista3.png">

| Campo | Detalle |
|---|---|
| **Entrevistador** | Arias Tasayco, Jean Pool Alexander |
| **Entrevistado** | Andy |
| **Edad** | 20 años |
| **Ubicación** | San Martín de Porres / conjunto empresarial en Lima |
| **Duración** | 8:21 minutos |
| **Enlace** | https://youtu.be/naAdZEitKRU |
| **Timing en video consolidado** | |

**Resumen.** Andy trabaja como supervisor de limpieza tercerizada. Describe una jornada centrada en asistencia, revisión de novedades, cobertura de ausencias, rondas de inspección, atención de incidencias y actualización de reportes. Sus principales fricciones se relacionan con rotación o ausentismo repentino, reorganización de rutas y la dificultad de reconstruir evidencia histórica cuando el cliente formula una observación. Parte de la validación de actividades se realiza mediante comunicación verbal, formatos firmados y fotografías por WhatsApp, lo que obliga a revisar físicamente zonas y buscar posteriormente información dispersa. La entrevista aporta evidencia preliminar a UA-01, UA-03, BO-01, BO-03, BO-04, FA-02 y FA-04.


### 2.2.3. Análisis de entrevistas

El análisis siguiente corresponde a la **muestra exploratoria actualmente documentada de 2 participantes por segmento**. Los porcentajes describen únicamente esa muestra y deben recalcularse después de completar la tercera entrevista mínima de cada segmento. No deben interpretarse como estimaciones de toda la población de trabajadores o supervisores de limpieza.

#### Segmento 1: Operarios — análisis preliminar (n = 2)

| Característica observada | Tipo | Frecuencia actual | Evidencia |
|---|---|---:|---|
| Utiliza WhatsApp para coordinación o evidencia del trabajo. | Objetiva / operativa | 2/2 (100 % de la muestra parcial) | José, Juan Antonio |
| Ha experimentado cambios o falta de claridad en asignaciones/prioridades. | Objetiva / operativa | 2/2 (100 %) | José, Juan Antonio |
| Reporta al menos una zona con conectividad reducida o problemática. | Objetiva / tecnológica | 2/2 (100 %) | José: sótano; Juan: almacenes/sótanos/estacionamientos |
| Usa fotografía como evidencia en al menos algunos casos. | Objetiva / operativa | 2/2 (100 %) | José, Juan Antonio |
| Considera útil una referencia centralizada de actividades/estado. | Subjetiva / expectativa | 2/2 (100 %) | José, Juan Antonio |
| Considera que WhatsApp es necesariamente “tedioso”. | Subjetiva / frustración | 0/2 como patrón uniforme | José indicó estar habituado; Juan sí identificó pérdida de contexto |

**Interpretación.** La evidencia preliminar respalda que el problema no debe formularse simplemente como “WhatsApp es malo”. Para algunos operarios, WhatsApp resulta familiar y suficientemente sencillo. La oportunidad aparece cuando la información necesita conservar relación con una obligación, una zona, un momento, una excepción o una revisión posterior. La conectividad también aparece como riesgo real, pero con intensidad distinta según la instalación, por lo que FA-05 se mantiene como feature assumption respaldada de forma inicial, no como requisito universal.

#### Segmento 2: Supervisores/coordinadores — análisis preliminar (n = 2)

| Característica observada | Tipo | Frecuencia actual | Evidencia |
|---|---|---:|---|
| Consolida información de forma manual desde mensajería, hojas de cálculo, papel u observación directa. | Objetiva / operativa | 2/2 (100 % de la muestra parcial) | Ivonne, Andy |
| Usa WhatsApp como parte relevante de la operación. | Objetiva / tecnológica | 2/2 (100 %) | Ivonne, Andy |
| Ha debido reconstruir información ante una observación o reclamo del cliente. | Objetiva / operativa | 2/2 (100 %) | Ivonne, Andy |
| Expresa necesidad de mayor visibilidad del estado operativo. | Subjetiva / expectativa | 2/2 (100 %) | Ivonne, Andy |
| Gestiona problemas de personal/ausentismo además del compliance. | Objetiva / operativa | 2/2, con distinta intensidad | Ivonne, Andy |
| El supervisor es necesariamente el comprador del software. | Hipótesis comercial | **No validado** | Ninguna entrevista demuestra por sí sola autoridad de compra |

**Interpretación.** La información recolectada aporta evidencia preliminar a BO-01 y BO-04: reconstruir el estado del servicio y consolidar evidencia puede demandar trabajo manual. También respalda BO-03, dado que ambos supervisores describen escenarios donde la observación del cliente puede revelar o reabrir un problema. Sin embargo, las entrevistas muestran que el supervisor enfrenta también asignación, ausentismo y cobertura de zonas; Service Compliance no debe expandirse automáticamente hacia RR. HH., sino mantener esas tareas visibles como contexto para evitar que el flujo de compliance ignore la operación real.

#### Trazabilidad preliminar de investigación con Lean UX

| Assumption / Outcome | Evidencia actual | Estado preliminar |
|---|---|---|
| **BO-01** Reducir esfuerzo de reconstrucción. | Ivonne reporta 30–40 min para reconstruir un caso; Andy describe búsqueda manual de papeles/fotos. | Apoyado preliminarmente. |
| **BO-03** Detectar desviaciones antes de reclamos tardíos. | Ivonne y Andy describen observaciones del cliente como disparadores relevantes. | Apoyado preliminarmente. |
| **BO-04** Reducir consolidación manual. | Ivonne reporta 4–5 h semanales; Andy usa registros físicos y WhatsApp. | Apoyado preliminarmente. |
| **FA-01** Obligaciones estructuradas. | Operarios describen zonas/prioridades y cambios comunicados por canales informales. | Apoyado preliminarmente. |
| **FA-02** Registro móvil vinculado a obligación/evidencia. | Todos utilizan móvil; fotos y mensajes pierden contexto. | Apoyado preliminarmente. |
| **FA-03** Excepciones y correctivas con historial. | Se reportan impedimentos, reclamos y escalamiento, pero falta profundizar en cierre/correctivas. | Parcial; requiere más evidencia. |
| **FA-04** Estado de cumplimiento y reporting. | Supervisores describen consolidación y falta de visibilidad. | Apoyado preliminarmente. |
| **FA-05** Almacenamiento local/sync. | Ambos operarios reportan algún problema de conectividad, con severidad distinta. | Apoyado de forma contextual, no universal. |
| **BA-02** Buyer distinto del usuario. | No se entrevistó aún al decisor de compra. | Pendiente de validación comercial. |

<a id="23-needfinding"></a>

## 2.3. Needfinding

Los artefactos de Needfinding sintetizan el proceso actual de los dos segmentos. Deben conservar trazabilidad con las entrevistas y evitar introducir funcionalidades que no se hayan derivado de necesidades o restricciones del proyecto.

### 2.3.1. User Personas

Se mantiene un User Persona por cada segmento objetivo. Las fichas deben reflejar únicamente características que puedan rastrearse a las entrevistas y al análisis competitivo; después de completar la tercera entrevista de cada segmento, las fichas deben actualizarse si cambian los patrones dominantes.

- **Segmento 1: Operarios de limpieza tercerizada**

<img src="resources/11-chapter-02/user-persona-1.png">

- **Segmento 2: Supervisores/coordinadores**

<img src="resources/11-chapter-02/user-persona-2.png">

### 2.3.2. User Task Matrix

La matriz incluye tareas que los segmentos realizan **independientemente de Service Compliance**. No se incluyen como tareas “escanear QR”, “usar GPS”, “sincronizar” o “abrir dashboard”, porque esas serían decisiones de solución.

| Tarea actual | Operario — Frecuencia | Operario — Importancia | Supervisor — Frecuencia | Supervisor — Importancia |
|---|---|---|---|---|
| Consultar o recibir las áreas/actividades asignadas. | Alta | Alta | Media | Alta |
| Ejecutar actividades de limpieza. | Alta | Alta | Baja | Media |
| Comunicar o confirmar la finalización de una actividad. | Alta | Alta | Media | Alta |
| Presentar evidencia cuando el proceso o cliente la requiere. | Media/Alta | Alta | Media | Alta |
| Comunicar un impedimento, daño o excepción. | Media | Alta | Media | Alta |
| Adaptarse a cambios de zona, turno o prioridad. | Media | Alta | Alta | Alta |
| Verificar la calidad o finalización del trabajo. | Baja | Baja | Alta | Alta |
| Reasignar cobertura ante ausencias o cambios operativos. | Baja | Baja | Alta | Alta |
| Recopilar y organizar evidencias/registros. | Baja | Baja | Alta | Alta |
| Atender observaciones o reclamos del cliente. | Baja | Baja | Media/Alta | Alta |
| Dar seguimiento a desviaciones hasta su atención. | Baja | Media | Media/Alta | Alta |
| Consolidar el estado del servicio y elaborar reportes. | Baja | Baja | Media | Alta |

**Lectura de la matriz.** Ambos segmentos coinciden en la necesidad de compartir una referencia sobre qué actividad se espera y qué ocurrió. El operario concentra frecuencia e importancia en ejecución y comunicación del resultado; el supervisor concentra importancia en coordinación, verificación, reconstrucción del estado y atención de desviaciones. Esto justifica experiencias móviles diferentes sin convertir al operario en responsable de interpretar reglas contractuales.

### 2.3.3. User Journey Mapping

Los Journey Maps representan el proceso **As-Is**, es decir, la situación actual antes de Service Compliance.

- **Operario**

<img src="resources/11-chapter-02/journey-map-1.png">

- **Supervisor/coordinador**

<img src="resources/11-chapter-02/journey-map-2.png">

#### 2.3.3.1. As-Is Scenario Mapping

La rúbrica exige también As-Is Scenario Mapping. La siguiente especificación resume los escenarios actuales y puede trasladarse a la herramienta indicada por el curso.

##### As-Is — Operario

| Etapa | Qué hace | Información/canal actual | Pain point / riesgo |
|---|---|---|---|
| Inicio del turno | Recibe zona, rutina o cambio de prioridad. | Indicación verbal, WhatsApp, carta/cronograma. | Mensajes cruzados, prioridad ambigua o cambio tardío. |
| Ejecución | Realiza la actividad en el espacio asignado. | Conocimiento operativo e instrucciones. | El espacio puede estar ocupado o presentar un impedimento. |
| Confirmación | Comunica que terminó. | Aviso verbal, mensaje, foto o formato. | El resultado puede quedar sin referencia estructurada a la actividad. |
| Excepción | Reporta daño, imposibilidad o situación fuera de alcance. | Supervisor, WhatsApp o escalamiento local. | Puede perderse el contexto o interpretarse como incumplimiento. |
| Cierre | Continúa con otra actividad. | Confirmación informal. | No siempre conoce si el registro fue recibido, aceptado o requiere corrección. |

##### As-Is — Supervisor

| Etapa | Qué hace | Información/canal actual | Pain point / riesgo |
|---|---|---|---|
| Planificación diaria | Revisa personal, novedades, zonas y prioridades. | WhatsApp, papel, Excel, experiencia propia. | Ausencias y cambios obligan a reorganizar. |
| Seguimiento | Consulta encargados, realiza rondas y recibe evidencia. | WhatsApp, llamadas, observación física. | Estado distribuido y difícil de consolidar. |
| Verificación | Decide si una actividad parece completada. | Foto, firma, inspección o comunicación. | Evidencia y criterio pueden no estar ligados a la obligación original. |
| Observación/reclamo | Reconstruye qué ocurrió. | Chats, archivos, Excel, llamadas. | Tiempo alto para localizar responsables y evidencia. |
| Corrección | Coordina solución y vuelve a verificar. | Mensajes, llamadas, ronda física. | El historial original y la corrección pueden quedar separados. |
| Reporte | Consolida información del periodo. | Excel, fotos, informes. | Trabajo manual y dificultad para comparar sedes/periodos. |

### 2.3.4. Empathy Mapping

Los Empathy Maps deben construirse a partir de los User Personas y entrevistas, registrando qué ve, oye, dice, hace, piensa y siente cada arquetipo, junto con pains y gains.

- **Operarios de limpieza tercerizada**

<img src="resources/11-chapter-02/Operarios%20de%20Campo.png">

- **Supervisores/coordinadores**

<img src="resources/11-chapter-02/Supervisores.png">

### 2.3.5. Big Picture EventStorming

El Big Picture EventStorming debe representar el **dominio del negocio actual**, no la interfaz ni la arquitectura de Service Compliance. Por ello los eventos se expresan en pasado y se excluyen términos como API, base de datos, sincronización, QR o GPS como si fueran eventos de dominio.

La sesión colaborativa debe documentar al menos: exploración sin estructura, ordenamiento en timeline, identificación de pain points/hotspots y consolidación de eventos significativos.

#### Eventos de dominio propuestos para la sesión

| Orden | Domain Event candidato | Hotspot / pregunta |
|---:|---|---|
| 1 | **Service Contract was agreed** | ¿El contrato es la única fuente del trabajo operativo? |
| 2 | **Service Conditions were identified** | ¿Quién interpreta qué condiciones son operables? |
| 3 | **Service Plan was defined** | ¿Existe plan, cronograma, carta de trabajo u otro artefacto intermedio? |
| 4 | **Service Obligation was scheduled** | ¿Cómo se determina frecuencia, ventana y sitio? |
| 5 | **Service Obligation was assigned** | ¿Quién asigna y cuándo cambia el responsable? |
| 6 | **Service Obligation became due** | ¿Qué significa “a tiempo” en cada servicio? |
| 7 | **Execution was started** | ¿Es necesario registrar inicio en todos los casos? |
| 8 | **Execution result was recorded** | ¿Qué resultados posibles existen además de “completado”? |
| 9 | **Evidence was provided** | ¿Qué evidencia es suficiente para cada obligación? |
| 10 | **Exception was reported** | ¿Qué diferencia una excepción aceptable de una desviación? |
| 11 | **Execution was submitted for review** | ¿Siempre existe revisión humana? |
| 12 | **Compliance was evaluated** | ¿Qué reglas y actor participan en la evaluación? |
| 13 | **Compliance Result was determined** | ¿Cumplido, excepción aceptada, desviación o incumplimiento? |
| 14 | **Client Observation was received** | ¿Puede reabrir o cuestionar una evaluación previa? |
| 15 | **Non-compliance was confirmed** | ¿Toda desviación se convierte en incumplimiento? |
| 16 | **Corrective Action was assigned** | ¿Quién decide que hace falta una acción correctiva? |
| 17 | **Corrective Action was completed** | ¿Cómo se verifica que la acción fue suficiente? |
| 18 | **Compliance Case was closed** | ¿Qué debe conservarse del estado original? |
| 19 | **Compliance Report was generated** | ¿Por sede, servicio, cliente o periodo? |

#### Pain points a contrastar durante la sesión

- información distribuida entre mensajes, hojas de cálculo, formatos y observación directa;
- cambios de prioridad y asignación durante el turno;
- evidencia sin contexto suficiente;
- conectividad limitada en determinadas zonas;
- observaciones del cliente que obligan a reconstruir el caso;
- ambigüedad entre excepción, desviación e incumplimiento;
- corrección realizada sin un historial común del problema original;
- consolidación manual para reportes.

### 2.3.6. Ubiquitous Language

El glosario utiliza términos del negocio en inglés y evita términos de ingeniería de software.

| Término | Definición de trabajo |
|---|---|
| **Service Contract** | Acuerdo entre la empresa prestadora y la organización cliente que establece el marco del servicio. |
| **Service Condition** | Condición relevante del acuerdo que debe ser considerada al planificar u operar el servicio. |
| **Service Plan** | Interpretación operativa aprobada del servicio, donde se organizan sitios, condiciones, obligaciones, frecuencia, ventanas y requisitos. |
| **Service Site** | Instalación o ubicación donde se presta el servicio. |
| **Obligation Definition** | Regla del Service Plan que describe qué actividad debe cumplirse, dónde, con qué frecuencia/ventana y bajo qué criterio. |
| **Service Obligation** | Instancia operativa que debe ser atendida en un periodo o ventana específica. |
| **Assignment** | Relación entre una Service Obligation y el operario responsable de atenderla. |
| **Execution** | Registro de lo que efectivamente se realizó o intentó realizar para una Service Obligation. |
| **Evidence Requirement** | Condición que establece qué respaldo debe acompañar una ejecución cuando sea necesario. |
| **Evidence** | Información presentada para respaldar una afirmación sobre la ejecución; su validez depende del Evidence Requirement y del contexto. |
| **Exception** | Circunstancia que impide o modifica la ejecución esperada y que puede ser aceptada según las reglas aplicables. |
| **Deviation** | Diferencia detectada entre el resultado esperado y el observado. No implica automáticamente Non-compliance. |
| **Compliance Evaluation** | Proceso de comparar la Service Obligation y sus criterios con la Execution, Evidence y Exception disponibles. |
| **Compliance Result** | Resultado de la evaluación: puede indicar cumplimiento, excepción aceptada, desviación o incumplimiento. |
| **Non-compliance** | Compliance Result que confirma que una obligación no cumplió un criterio aplicable y que no existe una excepción aceptada que lo justifique. |
| **Client Observation** | Cuestionamiento o comentario de la organización cliente acerca del resultado de un servicio. |
| **Corrective Action** | Acción acordada para responder a un Non-compliance o situación que requiere corrección. No elimina el resultado original. |
| **Compliance Case** | Conjunto trazable que conserva evaluación, resultado, observaciones y acciones posteriores relacionadas con una ejecución. |
| **Compliance Report** | Consolidación del estado de cumplimiento para un servicio, sitio y periodo definidos. |

<a id="24-requirements-specification"></a>

## 2.4. Requirements Specification

Los requisitos se derivan de Lean UX, entrevistas y Needfinding, junto con restricciones académicas explícitas del curso. Se distinguen las necesidades del dominio de decisiones tecnológicas obligatorias: el curso exige experiencia móvil nativa y cross-platform, almacenamiento local, acceso a un recurso interno del dispositivo, RESTful API propia y un servicio externo de terceros.

### To-Be Scenario Mapping

#### To-Be — Operario

| Etapa | Comportamiento esperado | Resultado buscado |
|---|---|---|
| Recibir trabajo | Consulta sus Service Obligations asignadas con sitio, ventana e instrucciones necesarias. | Menor ambigüedad sobre qué debe ejecutar. |
| Ejecutar | Inicia/atiende la obligación sin interpretar cláusulas contractuales. | Mantener foco en trabajo físico. |
| Registrar resultado | Registra completed, partial, blocked u otro resultado permitido. | Explicar qué ocurrió, no solo marcar una tarea. |
| Adjuntar evidencia | Presenta únicamente la Evidence requerida para esa obligación. | Evitar evidencia innecesaria y conservar contexto. |
| Reportar excepción | Registra impedimento/exception con motivo. | Evitar que una ejecución imposible quede como incumplimiento sin explicación. |
| Trabajar con conectividad limitada | Guarda temporalmente el registro y sincroniza posteriormente. | Reducir pérdida de información sin detener el trabajo. |
| Recibir corrección | Consulta una Corrective Action cuando le corresponde y registra su atención. | Cerrar el ciclo sin borrar el Non-compliance original. |

#### To-Be — Supervisor/coordinador

| Etapa | Comportamiento esperado | Resultado buscado |
|---|---|---|
| Preparar servicio | Define/activa un Service Plan y sus Obligation Definitions a partir de condiciones operativas aprobadas. | Separar contrato de interpretación operativa. |
| Coordinar | Asigna obligaciones y consulta estado por sitio/periodo. | Visibilidad compartida de la operación. |
| Revisar | Consulta Execution, Evidence y Exceptions. | Evitar reconstrucción desde múltiples canales. |
| Evaluar | Registra o confirma Compliance Result conforme a reglas aplicables. | Distinguir cumplimiento, excepción, desviación e incumplimiento. |
| Corregir | Asigna y sigue Corrective Action cuando corresponde. | Mantener historial del problema y de su respuesta. |
| Responder observaciones | Consulta el Compliance Case completo. | Explicar qué ocurrió con trazabilidad. |
| Reportar | Genera Compliance Report e indicadores por periodo/sitio. | Reducir consolidación manual. |

### 2.4.1. User Stories

#### Epics

| Epic ID | Epic | Propósito |
|---|---|---|
| **EP01** | Service Planning | Definir Service Plan, sitios, Obligation Definitions y Evidence Requirements. |
| **EP02** | Field Operations | Asignar y ejecutar Service Obligations en campo con evidencia/excepciones. |
| **EP03** | Compliance Management | Evaluar cumplimiento, registrar Compliance Result y gestionar correctivas/observaciones. |
| **EP04** | Reporting & Follow-up | Consultar estado, alertas, indicadores e informes trazables. |
| **EP05** | Identity & Access | Autenticar usuarios y aplicar roles/permisos. |
| **EP06** | Landing Page | Comunicar propuesta de valor y captar contacto para pilotos/demos. |
| **EP07** | Technical Foundation | REST API, almacenamiento local, servicios externos y capacidades técnicas. |

#### User Stories funcionales

##### US-01 — Crear Service Plan

| Campo | Contenido |
|---|---|
| **Story ID** | US-01 |
| **User** | Supervisor/coordinador autorizado |
| **Priority** | High |
| **Epic** | EP01 — Service Planning |
| **Title** | Crear un Service Plan |
| **Description** | Como supervisor/coordinador autorizado, deseo registrar un Service Plan para un servicio y sitio, para disponer de una referencia operativa común sin interpretar el contrato durante cada ejecución. |
| **Acceptance Criteria** | **Scenario 1:** Given que el supervisor cuenta con datos mínimos del servicio y sitio, When registra el Service Plan, Then el sistema conserva un identificador, periodo de vigencia, sitio y estado Draft. **Scenario 2:** Given un Service Plan Draft, When faltan datos obligatorios, Then el sistema no permite activarlo e informa qué información falta. |

##### US-02 — Definir Obligation Definition y Evidence Requirement

| Campo | Contenido |
|---|---|
| **Story ID** | US-02 |
| **User** | Supervisor/coordinador autorizado |
| **Priority** | High |
| **Epic** | EP01 |
| **Title** | Definir una obligación operativa |
| **Description** | Como supervisor/coordinador, deseo definir qué actividad debe realizarse, dónde, con qué frecuencia/ventana y qué evidencia requiere, para que cada ejecución tenga criterios claros. |
| **Acceptance Criteria** | **Scenario 1:** Given un Service Plan Draft, When se añade una Obligation Definition válida, Then queda asociada al plan con sitio, descripción, schedule rule y criterio de aceptación. **Scenario 2:** Given una obligación que requiere evidencia, When se configura su Evidence Requirement, Then el requisito queda explícitamente asociado y no se aplica automáticamente a otras obligaciones. |

##### US-03 — Activar Service Plan

| Campo | Contenido |
|---|---|
| **Story ID** | US-03 |
| **User** | Supervisor/coordinador autorizado |
| **Priority** | High |
| **Epic** | EP01 |
| **Title** | Activar el Service Plan |
| **Description** | Como supervisor/coordinador, deseo activar un Service Plan revisado para que sus obligaciones puedan ser programadas para la operación. |
| **Acceptance Criteria** | **Scenario 1:** Given un plan con al menos una Obligation Definition válida, When el supervisor lo activa, Then el estado cambia a Active y queda registrada la fecha de activación. **Scenario 2:** Given un plan Active, When se intenta modificar una regla que afectaría obligaciones ya emitidas, Then el sistema exige una nueva versión o cambio con trazabilidad. |

##### US-04 — Consultar obligaciones asignadas

| Campo | Contenido |
|---|---|
| **Story ID** | US-04 |
| **User** | Operario |
| **Priority** | High |
| **Epic** | EP02 — Field Operations |
| **Title** | Consultar Service Obligations asignadas |
| **Description** | Como operario, deseo consultar las obligaciones que me corresponden, para conocer qué debo realizar, dónde y dentro de qué ventana. |
| **Acceptance Criteria** | **Scenario 1:** Given que existen obligaciones asignadas al operario, When consulta su trabajo, Then recibe únicamente obligaciones dentro de su alcance con sitio, actividad, ventana e instrucciones necesarias. **Scenario 2:** Given que una obligación cambia antes de iniciarse, When el operario vuelve a consultar o sincroniza, Then visualiza la versión vigente. |

##### US-05 — Registrar Execution

| Campo | Contenido |
|---|---|
| **Story ID** | US-05 |
| **User** | Operario |
| **Priority** | High |
| **Epic** | EP02 |
| **Title** | Registrar el resultado de una ejecución |
| **Description** | Como operario, deseo registrar qué ocurrió al atender una Service Obligation, para que supervisión conozca el resultado real de la actividad. |
| **Acceptance Criteria** | **Scenario 1:** Given una obligación asignada, When el operario inicia y registra su resultado, Then la Execution queda vinculada a la obligación, operario y timestamps correspondientes. **Scenario 2:** Given una obligación no asignada al operario, When intenta registrar una ejecución, Then el sistema rechaza la operación. |

##### US-06 — Adjuntar Evidence requerida

| Campo | Contenido |
|---|---|
| **Story ID** | US-06 |
| **User** | Operario |
| **Priority** | High |
| **Epic** | EP02 |
| **Title** | Adjuntar evidencia cuando corresponde |
| **Description** | Como operario, deseo presentar la evidencia solicitada por la obligación para respaldar el resultado sin capturar información innecesaria. |
| **Acceptance Criteria** | **Scenario 1:** Given una obligación con Evidence Requirement, When el operario registra la evidencia del tipo permitido, Then queda vinculada a la Execution. **Scenario 2:** Given una obligación que no exige una evidencia específica, When el operario registra el resultado, Then el sistema no bloquea el envío por ausencia de foto/QR/GPS no requeridos. |

##### US-07 — Reportar Exception

| Campo | Contenido |
|---|---|
| **Story ID** | US-07 |
| **User** | Operario |
| **Priority** | High |
| **Epic** | EP02 |
| **Title** | Reportar un impedimento o excepción |
| **Description** | Como operario, deseo registrar una Exception cuando una obligación no puede ejecutarse como estaba prevista, para que el resultado sea revisado con contexto. |
| **Acceptance Criteria** | **Scenario 1:** Given una obligación asignada, When el operario reporta una excepción con motivo, Then la excepción queda asociada a la Execution y disponible para revisión. **Scenario 2:** Given una Exception registrada, When se evalúa el cumplimiento, Then no se convierte automáticamente en Non-compliance sin aplicar las reglas correspondientes. |

##### US-08 — Guardar y sincronizar con conectividad limitada

| Campo | Contenido |
|---|---|
| **Story ID** | US-08 |
| **User** | Operario |
| **Priority** | High |
| **Epic** | EP02 |
| **Title** | Continuar el registro sin conexión inmediata |
| **Description** | Como operario, deseo guardar temporalmente mis registros cuando no tengo conectividad para no perder el trabajo realizado y sincronizarlo después. |
| **Acceptance Criteria** | **Scenario 1:** Given que el dispositivo no tiene conexión, When el operario guarda una Execution o Evidence, Then el registro queda almacenado localmente con estado pendiente de sincronización. **Scenario 2:** Given registros pendientes y conectividad recuperada, When se ejecuta la sincronización, Then los registros se envían de forma idempotente y el usuario conoce si quedaron sincronizados o requieren atención. |

##### US-09 — Consultar estado operativo

| Campo | Contenido |
|---|---|
| **Story ID** | US-09 |
| **User** | Supervisor/coordinador |
| **Priority** | High |
| **Epic** | EP04 — Reporting & Follow-up |
| **Title** | Consultar el estado de las obligaciones |
| **Description** | Como supervisor, deseo consultar obligaciones por sitio, periodo y estado para identificar qué requiere mi atención sin revisar múltiples canales. |
| **Acceptance Criteria** | **Scenario 1:** Given obligaciones del alcance del supervisor, When consulta el estado operativo, Then puede distinguir assigned, in progress, submitted, excepted y overdue según las reglas vigentes. **Scenario 2:** Given una obligación fuera de su alcance, When intenta consultarla, Then el sistema no expone información no autorizada. |

##### US-10 — Revisar Execution y Evidence

| Campo | Contenido |
|---|---|
| **Story ID** | US-10 |
| **User** | Supervisor/coordinador |
| **Priority** | High |
| **Epic** | EP03 — Compliance Management |
| **Title** | Revisar la ejecución de una obligación |
| **Description** | Como supervisor, deseo revisar Execution, Evidence y Exceptions juntas para comprender qué ocurrió antes de evaluar el cumplimiento. |
| **Acceptance Criteria** | **Scenario 1:** Given una Execution submitted, When el supervisor abre el caso, Then visualiza obligación, resultado, evidencias, excepciones y timestamps relacionados. **Scenario 2:** Given que falta información exigida por el Service Plan, When revisa el caso, Then la ausencia queda indicada sin inventar automáticamente un Compliance Result. |

##### US-11 — Registrar Compliance Result

| Campo | Contenido |
|---|---|
| **Story ID** | US-11 |
| **User** | Supervisor/coordinador |
| **Priority** | High |
| **Epic** | EP03 |
| **Title** | Evaluar el cumplimiento |
| **Description** | Como supervisor, deseo registrar el Compliance Result aplicando los criterios del Service Plan para distinguir cumplimiento, excepción aceptada, desviación e incumplimiento. |
| **Acceptance Criteria** | **Scenario 1:** Given una Execution revisable, When se aplican criterios y evidencia disponibles, Then el caso registra un Compliance Result válido con actor y timestamp. **Scenario 2:** Given una Exception aceptada por la regla aplicable, When se evalúa el caso, Then el resultado puede ser Exception Accepted sin convertirla en Non-compliance. |

##### US-12 — Gestionar Corrective Action

| Campo | Contenido |
|---|---|
| **Story ID** | US-12 |
| **User** | Supervisor/coordinador |
| **Priority** | High |
| **Epic** | EP03 |
| **Title** | Asignar y dar seguimiento a una acción correctiva |
| **Description** | Como supervisor, deseo asignar una Corrective Action cuando corresponde para dar seguimiento a la respuesta sin borrar el Non-compliance original. |
| **Acceptance Criteria** | **Scenario 1:** Given un Compliance Case que requiere corrección, When el supervisor asigna una Corrective Action, Then queda registrada con responsable, descripción, fecha objetivo y estado. **Scenario 2:** Given una acción completada, When el supervisor verifica el cierre, Then el historial conserva tanto el Compliance Result original como la acción realizada. |

##### US-13 — Registrar Client Observation

| Campo | Contenido |
|---|---|
| **Story ID** | US-13 |
| **User** | Supervisor/coordinador |
| **Priority** | Medium |
| **Epic** | EP03 |
| **Title** | Registrar una observación del cliente |
| **Description** | Como supervisor, deseo registrar una Client Observation asociada a un caso para conservar el contexto de un cuestionamiento posterior a la ejecución. |
| **Acceptance Criteria** | **Scenario 1:** Given una observación relacionada con una obligación, When se registra, Then queda vinculada al Compliance Case con fecha, descripción y origen. **Scenario 2:** Given un resultado previamente registrado, When llega una observación, Then el sistema conserva el resultado original y registra cualquier reevaluación como una nueva decisión trazable. |

##### US-14 — Consultar historial del Compliance Case

| Campo | Contenido |
|---|---|
| **Story ID** | US-14 |
| **User** | Supervisor/coordinador |
| **Priority** | High |
| **Epic** | EP03 |
| **Title** | Consultar el historial completo de un caso |
| **Description** | Como supervisor, deseo consultar la secuencia de ejecución, evaluación, observaciones y correctivas para explicar qué ocurrió sin reconstruir datos dispersos. |
| **Acceptance Criteria** | **Scenario 1:** Given un Compliance Case con cambios, When se consulta su historial, Then se muestran los eventos relevantes en orden temporal. **Scenario 2:** Given una Corrective Action cerrada, When se consulta el historial, Then el Non-compliance original sigue visible y no aparece reescrito como si nunca hubiera ocurrido. |

##### US-15 — Generar Compliance Report

| Campo | Contenido |
|---|---|
| **Story ID** | US-15 |
| **User** | Supervisor/coordinador |
| **Priority** | Medium |
| **Epic** | EP04 |
| **Title** | Generar un reporte de cumplimiento |
| **Description** | Como supervisor, deseo generar un Compliance Report por servicio, sitio y periodo para comunicar el estado sin consolidar manualmente múltiples fuentes. |
| **Acceptance Criteria** | **Scenario 1:** Given un periodo con información disponible, When el supervisor solicita el reporte, Then se consolidan obligaciones, resultados, excepciones, incumplimientos y correctivas del alcance seleccionado. **Scenario 2:** Given que existen casos sin evaluación, When se genera el reporte, Then se muestran como pendientes y no se asumen cumplidos. |

##### US-16 — Recibir alertas relevantes

| Campo | Contenido |
|---|---|
| **Story ID** | US-16 |
| **User** | Supervisor/coordinador |
| **Priority** | Medium |
| **Epic** | EP04 |
| **Title** | Recibir alertas de obligaciones o casos que requieren atención |
| **Description** | Como supervisor, deseo recibir alertas configuradas para situaciones relevantes para actuar antes de que el problema dependa exclusivamente de un reclamo del cliente. |
| **Acceptance Criteria** | **Scenario 1:** Given una obligación próxima o vencida según una regla configurada, When se cumple la condición de alerta, Then el supervisor recibe una notificación una sola vez por el evento relevante. **Scenario 2:** Given una situación que no requiere alerta, When cambia de estado, Then el sistema no genera notificaciones innecesarias. |

##### US-17 — Autenticarse y acceder según rol

| Campo | Contenido |
|---|---|
| **Story ID** | US-17 |
| **User** | Operario / Supervisor |
| **Priority** | Medium |
| **Epic** | EP05 — Identity & Access |
| **Title** | Acceder con un rol autorizado |
| **Description** | Como usuario de la empresa prestadora, deseo autenticarme para acceder únicamente a las capacidades y datos permitidos para mi rol. |
| **Acceptance Criteria** | **Scenario 1:** Given credenciales válidas y cuenta activa, When el usuario se autentica, Then obtiene una sesión con su rol y empresa. **Scenario 2:** Given un operario autenticado, When intenta ejecutar una operación exclusiva de supervisor, Then la solicitud es rechazada. |

##### US-18 — Landing Page: comprender la propuesta

| Campo | Contenido |
|---|---|
| **Story ID** | US-18 |
| **User** | Visitante / potencial comprador |
| **Priority** | Medium |
| **Epic** | EP06 — Landing Page |
| **Title** | Comprender qué problema resuelve Service Compliance |
| **Description** | Como responsable de una empresa prestadora, deseo comprender la propuesta de valor de Service Compliance para decidir si vale la pena solicitar una demostración. |
| **Acceptance Criteria** | **Scenario 1:** Given un visitante en la Landing Page, When revisa la propuesta principal, Then puede identificar público objetivo, problema, beneficios y alcance inicial. **Scenario 2:** Given la página publicada, When se accede desde móvil o escritorio, Then el contenido principal permanece legible y navegable. |

##### US-19 — Landing Page: solicitar contacto

| Campo | Contenido |
|---|---|
| **Story ID** | US-19 |
| **User** | Visitante / potencial comprador |
| **Priority** | Medium |
| **Epic** | EP06 |
| **Title** | Solicitar una demostración o piloto |
| **Description** | Como potencial comprador, deseo disponer de un canal de contacto para manifestar interés en una demostración o piloto. |
| **Acceptance Criteria** | **Scenario 1:** Given un visitante interesado, When utiliza el mecanismo de contacto, Then puede enviar sus datos mínimos y motivo de interés. **Scenario 2:** Given datos obligatorios incompletos, When intenta enviarlos, Then el sistema informa qué información falta. |

#### Technical Stories

##### TS-01 — RESTful API propia

| Campo | Contenido |
|---|---|
| **Story ID** | TS-01 |
| **User** | Developer |
| **Priority** | High |
| **Epic** | EP07 — Technical Foundation |
| **Title** | Exponer capacidades mediante RESTful API documentada |
| **Description** | Como Developer, deseo exponer las capacidades del dominio mediante una RESTful API propia para que ambas aplicaciones móviles consuman el mismo modelo de negocio. |
| **Acceptance Criteria** | **Scenario 1:** Given una operación válida, When un cliente autorizado envía un request al endpoint correspondiente, Then la API responde con código HTTP y contrato JSON documentados en OpenAPI. **Scenario 2:** Given un request inválido, When la validación falla, Then la API retorna Problem Details sin filtrar información sensible. |

##### TS-02 — Persistencia local y sincronización

| Campo | Contenido |
|---|---|
| **Story ID** | TS-02 |
| **User** | Developer |
| **Priority** | High |
| **Epic** | EP07 |
| **Title** | Implementar cola local e idempotencia de sincronización |
| **Description** | Como Developer, deseo persistir localmente ejecuciones pendientes y sincronizarlas de forma idempotente para soportar conectividad intermitente en la app nativa del operario. |
| **Acceptance Criteria** | **Scenario 1:** Given un registro creado offline, When la aplicación se reinicia, Then el registro pendiente continúa disponible localmente. **Scenario 2:** Given que el mismo registro se envía más de una vez por reintento, When la API lo procesa, Then no se crean duplicados. |

##### TS-03 — Servicio externo de notificaciones

| Campo | Contenido |
|---|---|
| **Story ID** | TS-03 |
| **User** | Developer |
| **Priority** | Medium |
| **Epic** | EP07 |
| **Title** | Integrar notificaciones push con Firebase Cloud Messaging |
| **Description** | Como Developer, deseo integrar un servicio externo de notificaciones para enviar alertas relevantes a supervisores sin implementar infraestructura push propia. |
| **Acceptance Criteria** | **Scenario 1:** Given un evento configurado para notificación, When el backend lo procesa, Then se solicita a FCM el envío al usuario objetivo. **Scenario 2:** Given un token inválido o expirado, When FCM rechaza el envío, Then el error se registra y no se repite indefinidamente. |

##### TS-04 — Almacenamiento externo de evidencia multimedia

| Campo | Contenido |
|---|---|
| **Story ID** | TS-04 |
| **User** | Developer |
| **Priority** | Medium |
| **Epic** | EP07 |
| **Title** | Almacenar evidencia multimedia fuera de la base relacional |
| **Description** | Como Developer, deseo almacenar archivos de evidencia en un servicio de objetos para conservar en PostgreSQL solo metadatos y referencias controladas. |
| **Acceptance Criteria** | **Scenario 1:** Given una fotografía válida, When se confirma su registro, Then el archivo se almacena en el servicio configurado y la Evidence conserva una referencia. **Scenario 2:** Given un archivo no permitido o demasiado grande, When se intenta almacenar, Then la operación se rechaza antes de crear una Evidence válida. |

#### Spike Story de aprendizaje autónomo

##### SP-01 — Investigar tecnología para sincronización offline robusta

| Campo | Contenido |
|---|---|
| **Story ID** | SP-01 |
| **User** | Development Team |
| **Priority** | High |
| **Epic** | EP07 |
| **Title** | Investigar y prototipar una tecnología no utilizada en clase para sincronización offline/conflict handling |
| **Description** | Como equipo de desarrollo, deseamos investigar, comparar y prototipar una tecnología, biblioteca o servicio no utilizado en clase que permita robustecer la sincronización offline o resolución de conflictos, para cumplir el feature de aprendizaje autónomo y reducir riesgo técnico antes de implementar US-08. |
| **Acceptance Criteria** | **Scenario 1:** Given al menos dos alternativas candidatas, When el equipo las evalúa, Then documenta compatibilidad, limitaciones, curva de aprendizaje, costo y relación con el problema. **Scenario 2:** Given una alternativa seleccionada que no fue utilizada en clase, When se completa un proof of concept, Then existe evidencia ejecutable y conclusiones sobre su viabilidad. **Scenario 3:** Given los resultados del spike, When se cierra la investigación, Then la decisión y el aprendizaje se documentan para el Student Outcome y arquitectura. |

### 2.4.2. Impact Mapping

El Impact Map conecta Business Goals SMART con los User Personas, los cambios de comportamiento esperados, Deliverables y User Stories.

#### Business Goals propuestos

- **BG-01.** Durante un piloto de **8 semanas**, reducir al menos **30 %** el tiempo mediano que los supervisores participantes necesitan para reconstruir el estado completo de una obligación, comparado con la línea base medida durante la primera semana del piloto.
- **BG-02.** Durante el mismo piloto, lograr que al menos **90 %** de las ejecuciones que tengan Evidence Requirement finalicen con registro completo o Exception explícita antes de cerrar el periodo correspondiente.
- **BG-03.** Al finalizar el piloto, lograr que **100 %** de los Non-compliance identificados dentro de Service Compliance conserven una decisión explícita sobre seguimiento/correctiva y un historial consultable, evitando cierres sin trazabilidad.

| Goal | Actor / Persona | Impact buscado | Deliverables | User Stories |
|---|---|---|---|---|
| BG-01 | Supervisor | Consulta una fuente común en lugar de reconstruir chats, hojas y papeles. | Estado operativo, Compliance Case, historial y filtros. | US-09, US-10, US-14 |
| BG-01 | Operario | Registra el resultado directamente sobre su obligación. | Obligaciones asignadas, Execution, Evidence/Exception. | US-04, US-05, US-06, US-07 |
| BG-02 | Operario | Completa el registro requerido con mínima fricción incluso con conectividad limitada. | Evidence Requirement configurable, almacenamiento local y sync. | US-06, US-08, TS-02 |
| BG-02 | Supervisor | Define qué evidencia corresponde a cada obligación en vez de exigirla de forma uniforme. | Service Plan y Obligation Definition. | US-01, US-02, US-03 |
| BG-03 | Supervisor | Distingue Compliance Result y conserva la respuesta posterior. | Compliance Evaluation, Corrective Action, historial. | US-11, US-12, US-13, US-14 |
| BG-01 / BG-03 | Supervisor | Comunica el estado mediante reportes consistentes. | Reporting & Insights. | US-15, US-16 |

### 2.4.3. Product Backlog

El orden prioriza valor de negocio y reducción de riesgo. Authentication no se coloca en primer lugar. Las historias de Landing Page se consideran desde Sprint 1, como exige el enunciado. Los Story Points son una **estimación inicial** y deben ser ratificados por el equipo en la herramienta de gestión.

| Orden | Story ID | Título | Story Points | Sprint propuesto |
|---:|---|---|---:|---:|
| 1 | US-02 | Definir una obligación operativa y Evidence Requirement | 5 | 1 |
| 2 | US-04 | Consultar obligaciones asignadas | 3 | 1 |
| 3 | US-05 | Registrar el resultado de una Execution | 5 | 1 |
| 4 | US-06 | Adjuntar Evidence requerida | 3 | 1 |
| 5 | US-09 | Consultar estado operativo | 5 | 1 |
| 6 | US-18 | Landing Page: comprender propuesta | 3 | 1 |
| 7 | US-19 | Landing Page: solicitar contacto | 2 | 1 |
| 8 | SP-01 | Investigar tecnología de aprendizaje autónomo | 5 | 1 |
| 9 | TS-01 | RESTful API propia documentada | 5 | 1 |
| 10 | US-01 | Crear Service Plan | 5 | 1 |
| 11 | US-03 | Activar Service Plan | 3 | 1 |
| 12 | US-07 | Reportar Exception | 3 | 1 |
| 13 | US-10 | Revisar Execution y Evidence | 5 | 2 |
| 14 | US-11 | Registrar Compliance Result | 8 | 2 |
| 15 | US-12 | Gestionar Corrective Action | 5 | 2 |
| 16 | US-14 | Consultar historial de Compliance Case | 5 | 2 |
| 17 | US-08 | Guardar y sincronizar con conectividad limitada | 8 | 2 |
| 18 | TS-02 | Persistencia local e idempotencia de sync | 8 | 2 |
| 19 | US-17 | Autenticarse y acceder según rol | 5 | 2 |
| 20 | US-13 | Registrar Client Observation | 3 | 3 |
| 21 | US-15 | Generar Compliance Report | 8 | 3 |
| 22 | US-16 | Recibir alertas relevantes | 5 | 3 |
| 23 | TS-03 | Integrar FCM | 3 | 3 |
| 24 | TS-04 | Almacenar evidencia multimedia | 5 | 2 |

<a id="25-strategic-level-domain-driven-design"></a>

## 2.5. Strategic-Level Domain-Driven Design

El diseño estratégico parte del dominio y de los requisitos anteriores. Se evita considerar Authentication, QR, GPS, API o una base de datos como el centro del modelo de negocio. La ventaja candidata de Opervia se concentra en **Compliance Management**: determinar y explicar el estado de cumplimiento sin perder la relación con lo planificado, lo ejecutado y las acciones posteriores.

### 2.5.1. EventStorming

El EventStorming estratégico toma como entrada el Big Picture EventStorming As-Is y el To-Be Scenario Mapping. Su objetivo es detallar Commands, Policies, Aggregates y Domain Events necesarios para identificar límites naturales entre responsabilidades.


| Actor | Command | Aggregate / objeto de decisión | Domain Event | Policy / regla relevante |
|---|---|---|---|---|
| Supervisor | Create Service Plan | Service Plan | Service Plan Created | El plan inicia Draft. |
| Supervisor | Add Obligation Definition | Service Plan | Obligation Definition Added | Debe existir sitio, schedule y criterio. |
| Supervisor | Activate Service Plan | Service Plan | Service Plan Activated | Un plan activo debe ser operativo y versionado. |
| Sistema/planificación | Schedule Service Obligation | Obligation Definition | Service Obligation Scheduled | Se instancia conforme a Schedule Rule. |
| Supervisor | Assign Service Obligation | Assignment | Service Obligation Assigned | El operario debe pertenecer al alcance autorizado. |
| Operario | Start Execution | Service Execution | Execution Started | Solo puede iniciar una obligación asignada. |
| Operario | Attach Evidence | Service Execution | Evidence Attached | Solo se exige Evidence indicada por el requisito. |
| Operario | Report Exception | Service Execution | Exception Reported | Exception no equivale automáticamente a Non-compliance. |
| Operario | Submit Execution | Service Execution | Execution Submitted | Debe existir un resultado explícito. |
| Supervisor / Policy | Evaluate Compliance | Compliance Case | Compliance Evaluated | Se aplican criterios vigentes del Service Plan. |
| Supervisor / Policy | Determine Compliance Result | Compliance Case | Compliance Result Recorded | Resultado ∈ compliant / exception accepted / deviation / non-compliant. |
| Supervisor | Register Client Observation | Compliance Case | Client Observation Registered | No borra el resultado previo. |
| Supervisor | Assign Corrective Action | Compliance Case | Corrective Action Assigned | Solo cuando la decisión lo requiere. |
| Operario | Complete Corrective Action | Compliance Case | Corrective Action Completed | Debe conservarse historial. |
| Supervisor | Close Compliance Case | Compliance Case | Compliance Case Closed | Cierre no reescribe el Non-compliance original. |
| Supervisor | Generate Compliance Report | Compliance Report | Compliance Report Generated | Incluye pendientes como pendientes. |

#### 2.5.1.1. Candidate Context Discovery

Para la sesión de Candidate Context Discovery se proponen las técnicas **start-with-value** y **look-for-pivotal-events**. Los pivotal events que sugieren cambios de responsabilidad son: `Service Plan Activated`, `Service Obligation Assigned`, `Execution Submitted`, `Compliance Result Recorded` y `Compliance Report Generated`.

##### Candidate Bounded Contexts

| Candidate Bounded Context | Clasificación estratégica | Responsabilidad principal | Eventos de entrada/salida relevantes |
|---|---|---|---|
| **Identity & Access** | Generic | Identidad, empresa, rol y autorización. | User Authenticated, Account Deactivated. |
| **Service Planning** | Supporting | Service Plan, Service Conditions, sites, Obligation Definitions, Evidence Requirements y reglas de planificación. | Service Plan Activated, Obligation Definition Published. |
| **Field Operations** | Supporting | Service Obligations operativas, asignación, Execution, Evidence y Exception; continuidad offline a nivel de aplicación. | Service Obligation Assigned, Execution Submitted, Exception Reported. |
| **Compliance Management** | **Core Domain** | Compliance Evaluation, Compliance Result, Deviation, Non-compliance, Client Observation y Corrective Action con historial inmutable. | Execution Submitted → Compliance Result Recorded / Non-compliance Confirmed / Compliance Case Closed. |
| **Reporting & Insights** | Supporting | Proyecciones, indicadores y Compliance Reports para periodos/sitios/servicios. | Consume eventos de Planning/Compliance; produce Compliance Report Generated. |

**Justificación del Core Domain.** Field Operations es importante pero existen competidores maduros que ya resuelven work orders, inspecciones y captura de evidencia. La diferenciación candidata de Service Compliance se encuentra en **cómo el producto conserva y explica el Compliance Result a partir del Service Plan, Execution, Evidence y acciones posteriores**, por lo que Compliance Management se considera el Core Domain.

##### Decisiones de boundary

- **Evidence Requirement** pertenece a Service Planning porque define qué respaldo se espera.
- **Evidence capturada** pertenece a Field Operations porque forma parte del registro de una Execution.
- **Interpretar si la Evidence y Execution satisfacen el criterio** pertenece a Compliance Management.
- **Offline synchronization** es una capability técnica de las aplicaciones/infraestructura, no un dominio independiente.
- **Authentication** es Generic; no se considera Core Domain.
- **Reporting** consume proyecciones propias y no debe consultar directamente tablas internas de otros contextos.

#### 2.5.1.2. Domain Message Flows Modeling

Los Domain Stories deben representar colaboración entre actores y objetos del negocio, no entre Mobile App, API y Database.

##### Domain Story DS-01 — Preparar un servicio

1. **Supervisor/coordinador** interpreta condiciones operativas aprobadas del **Service Contract**.
2. El supervisor registra/actualiza el **Service Plan**.
3. El supervisor añade **Obligation Definitions** y sus **Evidence Requirements**.
4. El **Service Plan** queda activo y disponible para generar/planificar **Service Obligations**.
5. **Field Operations** recibe la información necesaria para coordinar las obligaciones del periodo.

##### Domain Story DS-02 — Ejecutar una obligación

1. **Supervisor** asigna una **Service Obligation** a un **Operario**.
2. El operario consulta la obligación y realiza la actividad.
3. El operario registra una **Execution**.
4. Cuando corresponde, añade **Evidence** o informa una **Exception**.
5. La Execution queda disponible para **Compliance Evaluation**.

##### Domain Story DS-03 — Evaluar y corregir

1. **Supervisor** revisa Service Obligation, Execution, Evidence y Exception.
2. **Compliance Management** aplica los criterios vigentes y registra el **Compliance Result**.
3. Si existe Non-compliance que requiere corrección, el supervisor asigna una **Corrective Action**.
4. **Operario** atiende la Corrective Action.
5. **Supervisor** verifica el resultado y cierra el **Compliance Case** sin eliminar la evaluación original.

##### Domain Story DS-04 — Responder una observación y reportar

1. **Organización cliente** comunica una **Client Observation** al supervisor.
2. **Supervisor** consulta el **Compliance Case** y su historial.
3. Si corresponde, registra una nueva evaluación o Corrective Action sin sobrescribir decisiones anteriores.
4. **Reporting & Insights** consolida resultados del periodo.
5. **Supervisor** genera o comparte un **Compliance Report**.

#### 2.5.1.3. Bounded Context Canvases

Los canvases se especifican siguiendo: Context Overview Definition → Business Rules & Ubiquitous Language → Capability Analysis → Capability Layering → Dependencies Capture → Design Critique.

##### Canvas — Identity & Access

| Paso | Contenido |
|---|---|
| **Context Overview** | Gestiona cuentas, pertenencia a empresa prestadora, roles y autorización. |
| **Business Rules / Language** | User Account, Role, Provider Company, Account Status. Una cuenta inactiva no accede. |
| **Capabilities** | Login, token/session, role authorization, account lifecycle. |
| **Layering** | Generic subdomain. No contiene reglas de compliance. |
| **Dependencies** | Expone identidad/claims a los demás contextos mediante interfaz estable. |
| **Design Critique** | Se mantiene separado porque identidad cambia por razones técnicas/seguridad distintas al dominio de servicio. |

##### Canvas — Service Planning

| Paso | Contenido |
|---|---|
| **Context Overview** | Convierte condiciones operativas aprobadas en un Service Plan versionado con Obligation Definitions. |
| **Business Rules / Language** | Service Plan, Service Condition, Service Site, Obligation Definition, Schedule Rule, Evidence Requirement, Acceptance Criterion. |
| **Capabilities** | Crear/versionar plan, definir sitios, obligaciones, frecuencia/ventana, evidencia requerida y activar plan. |
| **Layering** | Supporting subdomain. |
| **Dependencies** | Usa identidad; publica definiciones/plan activo a Field Operations y reglas relevantes a Compliance. |
| **Design Critique** | Se evita “interpretar automáticamente contratos”. El plan es una decisión humana/operativa explícita. |

##### Canvas — Field Operations

| Paso | Contenido |
|---|---|
| **Context Overview** | Coordina obligaciones operativas y registra lo ocurrido en campo. |
| **Business Rules / Language** | Service Obligation, Assignment, Execution, Evidence, Exception. |
| **Capabilities** | Asignar, consultar trabajo, iniciar/registrar ejecución, adjuntar evidencia, reportar excepción, enviar Execution. |
| **Layering** | Supporting subdomain con fuerte interacción móvil. |
| **Dependencies** | Consume plan/obligaciones de Service Planning; publica Execution Submitted y Exception Reported a Compliance. |
| **Design Critique** | Offline y cámara se resuelven en aplicación/infraestructura; no se modelan como objetos del dominio. |

##### Canvas — Compliance Management

| Paso | Contenido |
|---|---|
| **Context Overview** | Determina y explica el cumplimiento de una ejecución y conserva su historial. |
| **Business Rules / Language** | Compliance Evaluation, Compliance Result, Deviation, Non-compliance, Client Observation, Corrective Action, Compliance Case. |
| **Capabilities** | Evaluar, registrar resultado, aceptar excepción, confirmar Non-compliance, registrar observación, asignar/seguir correctiva, cerrar caso. |
| **Layering** | **Core Domain**. |
| **Dependencies** | Consume criterios de Service Planning y Execution/Evidence de Field Operations; publica resultados a Reporting. |
| **Design Critique** | Mantener separado evita mezclar sync/captura de campo con las reglas que constituyen la ventaja competitiva. El resultado original nunca se sobrescribe por una corrección. |

##### Canvas — Reporting & Insights

| Paso | Contenido |
|---|---|
| **Context Overview** | Construye proyecciones e informes de cumplimiento por servicio, sitio y periodo. |
| **Business Rules / Language** | Compliance Report, Report Period, Report Metric, Reporting Projection. |
| **Capabilities** | Consolidar proyecciones, calcular indicadores, generar/publicar reportes, filtrar por sitio/periodo. |
| **Layering** | Supporting subdomain / read-heavy. |
| **Dependencies** | Consume eventos publicados por Planning, Field Operations y Compliance. |
| **Design Critique** | Se separa del Core porque su ritmo de cambio y modelo de lectura difieren de las reglas de evaluación. |

### 2.5.2. Context Mapping

#### Proceso y alternativas consideradas

1. **Separar Evidence como Bounded Context independiente.** Rechazado para el MVP: el requirement pertenece a Planning, la captura a Field Operations y la interpretación a Compliance; un contexto de Evidence aislado generaría dependencias excesivamente conversacionales.
2. **Fusionar Field Operations y Compliance Management.** Rechazado: mezclaría problemas de asignación/sincronización con las reglas diferenciales de compliance y dificultaría aislar el Core Domain.
3. **Fusionar Reporting con Compliance.** Rechazado: reporting es principalmente lectura/proyección y puede evolucionar sin modificar las reglas de evaluación.
4. **Usar Shared Kernel entre contextos.** Rechazado inicialmente: aumenta acoplamiento. Se prefieren IDs, contratos de integración y Published Language.
5. **Desplegar cada contexto como microservicio.** Rechazado para el MVP académico: la complejidad operativa no aporta valor suficiente. Se adopta **Modular Monolith** con límites lógicos estrictos.

#### Relaciones seleccionadas

| Upstream | Downstream | Relación | Integración prevista |
|---|---|---|---|
| **Identity & Access** | Planning / Field / Compliance / Reporting | Open Host Service + Published Language; downstreams conforman a claims/roles mínimos. | Autenticación/claims mediante interfaz estable. OHS es un patrón, no un contexto adicional. |
| **Service Planning** | **Field Operations** | Customer/Supplier | Publica Service Plan/Obligation Definition necesarios para operación; Field Operations influye en datos mínimos requeridos. |
| **Service Planning** | **Compliance Management** | Customer/Supplier + Published Language | Provee criterios/versiones de obligación relevantes para evaluación. |
| **Field Operations** | **Compliance Management** | Customer/Supplier | Publica Execution Submitted / Exception Reported; Compliance define qué datos necesita para evaluar. |
| **Compliance Management** | **Reporting & Insights** | Customer/Supplier + Published Language | Publica Compliance Result, Non-compliance y Corrective Action status. |
| **Service Planning** | **Reporting & Insights** | Published Language | Publica metadatos de servicio/sitio necesarios para proyecciones. |

### 2.5.3. Software Architecture

La arquitectura se implementa inicialmente como **Modular Monolith** para mantener límites DDD sin introducir la complejidad operativa de microservicios. El backend usa ASP.NET Core REST API y PostgreSQL; los módulos del backend corresponden a los Bounded Contexts definidos. Se distinguen dos aplicaciones móviles porque el enunciado exige experiencia nativa y cross-platform y los segmentos tienen contextos de uso distintos.

#### 2.5.3.1. Software Architecture Context Level Diagrams

##### System Context — especificación

| Persona / sistema | Relación con Service Compliance |
|---|---|
| **Operario de limpieza** | Consulta obligaciones, registra Execution, Evidence y Exception; atiende Corrective Actions. |
| **Supervisor/coordinador** | Gestiona Service Plan, coordina operación, revisa Execution, registra Compliance Result, correctivas y reportes. |
| **Responsable de operaciones de la prestadora** | Stakeholder/comprador potencial; consulta resultados agregados cuando su rol lo permite. |
| **Organización cliente** | Stakeholder externo; recibe explicaciones/reportes por los canales definidos, sin considerarse segmento objetivo inicial. |
| **Firebase Cloud Messaging** | Servicio externo para notificaciones push. |
| **Object Storage / Media Service** | Servicio externo para archivos de evidencia cuando corresponda. |

#### 2.5.3.2. Software Architecture Container Level Diagrams

| Container | Tecnología propuesta | Responsabilidad |
|---|---|---|
| **Operator Native Android App** | Kotlin + Android SDK | Experiencia del operario: obligaciones, Execution, Evidence/Exception, cámara y almacenamiento local/offline. |
| **Supervisor Cross-Platform App** | Flutter + Dart | Experiencia del supervisor: Service Planning, estado operativo, Compliance Management, correctivas y reporting. |
| **Landing Page** | HTML5 + CSS3 + JavaScript | Presentar el modelo de negocio y captar contactos/pilotos. |
| **Service Compliance API** | ASP.NET Core (.NET 10) + OpenAPI | Modular Monolith con Identity, Planning, Field Operations, Compliance y Reporting. |
| **PostgreSQL Database** | PostgreSQL | Persistencia transaccional con separación lógica por schemas/contextos. |
| **Firebase Cloud Messaging** | Servicio externo | Push notifications. |
| **Evidence Object Storage** | Servicio externo compatible con object storage | Archivos de evidencia; API conserva metadatos/referencias. |

**Comunicación principal.** Ambas apps consumen la REST API mediante HTTPS/JSON. La app nativa utiliza almacenamiento local para registros pendientes y sincroniza posteriormente. La API mantiene el modelo de negocio, persiste datos en PostgreSQL y utiliza servicios externos únicamente a través de adapters de Infrastructure.

#### 2.5.3.3. Software Architecture Deployment Diagrams

| Deployment Node | Artefacto / servicio |
|---|---|
| **Android physical device — Operario** | Operator Native Android App (Kotlin), Room/SQLite local, cámara del dispositivo. |
| **Android/iOS physical device — Supervisor** | Supervisor Cross-Platform App (Flutter/Dart). |
| **Static Web Hosting** | Landing Page. |
| **Cloud Application Host** | ASP.NET Core REST API. |
| **Managed PostgreSQL** | Base de datos de Service Compliance. |
| **Firebase infrastructure** | FCM. |
| **Object Storage provider** | Archivos multimedia de evidencia. |

El despliegue final debe demostrar las aplicaciones en dispositivos físicos. El almacenamiento local y la cámara satisfacen necesidades de campo y, además, corresponden a restricciones explícitas del curso.

<a id="26-tactical-level-domain-driven-design"></a>

## 2.6. Tactical-Level Domain-Driven Design

El diseño táctico implementa los cinco Bounded Contexts como módulos del backend, evitando compartir directamente entidades de dominio. La base de datos puede ser una única instancia PostgreSQL en el MVP, pero se propone separación lógica por schemas (`identity`, `planning`, `field_ops`, `compliance`, `reporting`). Los contextos intercambian identificadores y eventos de integración, no referencias ORM entre agregados de contextos distintos.

### 2.6.1. Bounded Context: Identity & Access

#### 2.6.1.1. Domain Layer

| Clase | Categoría | Propósito | Miembros principales |
|---|---|---|---|
| `UserAccount` | Aggregate Root | Representa una cuenta perteneciente a una empresa prestadora. | `UserId`, `ProviderCompanyId`, `Email`, `Role`, `Status`; `Activate()`, `Deactivate()`, `ChangeRole()` |
| `Role` | Value Object / Enum | Rol funcional autorizado. | `OPERATOR`, `SUPERVISOR`, `OPERATIONS_MANAGER` |
| `AccountStatus` | Enum | Estado de acceso. | `ACTIVE`, `INACTIVE`, `SUSPENDED` |
| `AccessPolicy` | Domain Service | Evalúa reglas de rol/empresa que no corresponden a un único método de entidad. | `CanManagePlan()`, `CanExecute()`, `CanEvaluateCompliance()` |
| `IUserAccountRepository` | Repository interface | Persistencia abstracta de cuentas. | `FindById()`, `FindByEmail()`, `Save()` |

#### 2.6.1.2. Interface Layer

| Clase | Tipo | Operaciones |
|---|---|---|
| `AuthController` | Controller | `POST /api/v1/auth/login`, `POST /api/v1/auth/refresh` |
| `AccountController` | Controller | `GET /api/v1/accounts/me` |

#### 2.6.1.3. Application Layer

| Clase | Tipo | Responsabilidad / eventos |
|---|---|---|
| `LoginCommandHandler` | Command Handler | Valida credenciales, emite sesión/token. |
| `RefreshTokenCommandHandler` | Command Handler | Renueva sesión válida. |
| `DeactivateAccountCommandHandler` | Command Handler | Cambia estado y publica `AccountDeactivated`. |
| `AccountDeactivatedEventHandler` | Event Handler | Invalida sesiones asociadas. |

#### 2.6.1.4. Infrastructure Layer

| Clase | Responsabilidad | Implementación propuesta |
|---|---|---|
| `UserAccountRepository` | Implementa repositorio. | EF Core + PostgreSQL schema `identity`. |
| `PasswordHasher` | Hash/verify de credenciales. | ASP.NET Core PasswordHasher o equivalente. |
| `JwtTokenService` | Emisión/validación de tokens. | JWT. |

#### 2.6.1.5. Bounded Context Software Architecture Component Level Diagrams

Componentes: `AuthController`, `AccountController`, `IdentityApplication`, `AccessPolicy`, `UserAccountRepository`, `JwtTokenService`.

#### 2.6.1.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.1.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.1.6.2. Bounded Context Database Design Diagram

| Tabla | Campos principales | Constraints |
|---|---|---|
| `identity.user_accounts` | `user_id`, `provider_company_id`, `email`, `password_hash`, `role`, `status`, `created_at` | PK `user_id`, UQ `email`. |
| `identity.refresh_tokens` | `token_id`, `user_id`, `token_hash`, `expires_at`, `revoked_at` | FK lógico a `user_accounts`, UQ `token_hash`. |

### 2.6.2. Bounded Context: Service Planning

#### 2.6.2.1. Domain Layer

| Clase | Categoría | Propósito | Miembros principales |
|---|---|---|---|
| `ServicePlan` | Aggregate Root | Representa la interpretación operativa versionada del servicio. | `PlanId`, `ProviderCompanyId`, `ClientReference`, `Version`, `Status`; `AddCondition()`, `AddObligationDefinition()`, `Activate()`, `CreateRevision()` |
| `ServiceCondition` | Entity | Condición relevante que sirve de contexto al plan. | `ConditionId`, `Description`, `SourceReference` |
| `ServiceSite` | Entity | Instalación donde se presta el servicio. | `SiteId`, `Name`, `Address`, `ClientReference` |
| `ObligationDefinition` | Entity | Describe actividad, sitio, schedule, criterio y evidencia esperada. | `DefinitionId`, `Activity`, `SiteId`, `ScheduleRule`, `AcceptanceCriterion`, `EvidenceRequirements` |
| `ScheduleRule` | Value Object | Frecuencia/ventana operacional. | `Frequency`, `Days`, `WindowStart`, `WindowEnd` |
| `AcceptanceCriterion` | Value Object | Criterio con el cual se evaluará la obligación. | `Description`, `CriterionType` |
| `EvidenceRequirement` | Value Object | Tipo de respaldo requerido cuando corresponda. | `Type`, `Required`, `Instructions` |
| `ServicePlanStatus` | Enum | Ciclo de vida del plan. | `DRAFT`, `ACTIVE`, `SUPERSEDED`, `CLOSED` |
| `ServicePlanPolicy` | Domain Service | Valida activación/versionado. | `CanActivate(plan)`, `RequiresRevision(change)` |
| `IServicePlanRepository` | Repository interface | Persistencia del agregado. | `FindById()`, `Save()`, `FindActiveByService()` |

#### 2.6.2.2. Interface Layer

| Clase | Tipo | Operaciones |
|---|---|---|
| `ServicePlanController` | Controller | `POST /plans`, `GET /plans/{id}`, `POST /plans/{id}/activate`, `POST /plans/{id}/revisions` |
| `ObligationDefinitionController` | Controller | `POST /plans/{id}/obligations`, `PUT /plans/{id}/obligations/{definitionId}` |

#### 2.6.2.3. Application Layer

| Clase | Tipo | Responsabilidad / eventos |
|---|---|---|
| `CreateServicePlanCommandHandler` | Command Handler | Crea plan Draft; publica `ServicePlanCreated`. |
| `AddObligationDefinitionCommandHandler` | Command Handler | Añade definición válida. |
| `ActivateServicePlanCommandHandler` | Command Handler | Valida y activa; publica `ServicePlanActivated` y definiciones necesarias. |
| `CreateServicePlanRevisionCommandHandler` | Command Handler | Crea nueva versión sin reescribir la activa históricamente. |
| `ServicePlanActivatedEventHandler` | Event Handler | Publica integración para Field Operations/Compliance. |

#### 2.6.2.4. Infrastructure Layer

| Clase | Responsabilidad | Implementación |
|---|---|---|
| `ServicePlanRepository` | Persistencia del agregado. | EF Core + PostgreSQL schema `planning`. |
| `PlanningIntegrationPublisher` | Publica contracts/events internos del modular monolith. | In-process dispatcher / integration events. |

#### 2.6.2.5. Bounded Context Software Architecture Component Level Diagrams

Componentes: `ServicePlanController`, `ObligationDefinitionController`, `PlanningApplication`, `ServicePlanPolicy`, `ServicePlanRepository`, `PlanningIntegrationPublisher`.

#### 2.6.2.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.2.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.2.6.2. Bounded Context Database Design Diagram

| Tabla | Campos principales | Constraints |
|---|---|---|
| `planning.service_plans` | `plan_id`, `provider_company_id`, `client_reference`, `version`, `status`, `valid_from`, `valid_to` | PK; UQ servicio+versión. |
| `planning.service_conditions` | `condition_id`, `plan_id`, `description`, `source_reference` | FK dentro del schema Planning. |
| `planning.service_sites` | `site_id`, `plan_id`, `name`, `address`, `client_reference` | FK `plan_id`. |
| `planning.obligation_definitions` | `definition_id`, `plan_id`, `site_id`, `activity`, `frequency`, `window_start`, `window_end`, `acceptance_criterion` | FK plan/site. |
| `planning.evidence_requirements` | `requirement_id`, `definition_id`, `type`, `required`, `instructions` | FK definition. |

### 2.6.3. Bounded Context: Field Operations

#### 2.6.3.1. Domain Layer

| Clase | Categoría | Propósito | Miembros principales |
|---|---|---|---|
| `ServiceExecution` | Aggregate Root | Representa la atención de una Service Obligation por un operario. | `ExecutionId`, `ObligationId`, `OperatorId`, `Status`, `StartedAt`, `SubmittedAt`; `Start()`, `AttachEvidence()`, `ReportException()`, `Submit()` |
| `ObligationSnapshot` | Value Object | Copia mínima/versionada de la obligación necesaria para ejecutar sin acoplar el agregado a Planning. | `ObligationId`, `DefinitionVersion`, `Site`, `Window`, `EvidenceRequirements` |
| `Evidence` | Entity | Respaldo asociado a la ejecución. | `EvidenceId`, `Type`, `Reference`, `CapturedAt`, `Metadata` |
| `ExecutionException` | Entity | Impedimento/contexto reportado por el operario. | `ExceptionId`, `ReasonCode`, `Description`, `ReportedAt` |
| `ExecutionStatus` | Enum | Estado de la ejecución. | `ASSIGNED`, `IN_PROGRESS`, `SUBMITTED`, `CANCELLED` |
| `EvidenceType` | Enum/extensible | Tipos iniciales de evidencia. | `PHOTO`, `CHECKLIST`, `SIGNATURE`, `OTHER` |
| `ExecutionSubmissionPolicy` | Domain Service | Valida que exista resultado y requisitos mínimos antes de submit. | `CanSubmit(execution, snapshot)` |
| `IExecutionRepository` | Repository interface | Persistencia del agregado. | `FindById()`, `FindAssignedTo()`, `Save()` |

> **Nota de diseño:** QR, GPS o NFC no son obligatorios ni forman parte fija de `EvidenceType`. Pueden incorporarse como mecanismos concretos si un Evidence Requirement validado los necesita. La conectividad tampoco se almacena como “verdad de negocio”; la cola offline pertenece a infraestructura de la app.

#### 2.6.3.2. Interface Layer

| Clase | Tipo | Operaciones |
|---|---|---|
| `ExecutionController` | Controller | `GET /executions/me`, `POST /executions/{id}/start`, `POST /executions/{id}/submit` |
| `EvidenceController` | Controller | `POST /executions/{id}/evidence` |
| `ExceptionController` | Controller | `POST /executions/{id}/exceptions` |
| `SyncController` | Controller | `POST /sync/executions` con idempotency key. |

#### 2.6.3.3. Application Layer

| Clase | Tipo | Responsabilidad / eventos |
|---|---|---|
| `AssignServiceObligationCommandHandler` | Command Handler | Crea/actualiza asignación y publica `ServiceObligationAssigned`. |
| `StartExecutionCommandHandler` | Command Handler | Inicia ejecución; publica `ExecutionStarted`. |
| `AttachEvidenceCommandHandler` | Command Handler | Registra metadata/referencia; publica `EvidenceAttached`. |
| `ReportExceptionCommandHandler` | Command Handler | Añade excepción; publica `ExceptionReported`. |
| `SubmitExecutionCommandHandler` | Command Handler | Aplica policy y publica `ExecutionSubmitted`. |
| `SyncExecutionCommandHandler` | Command Handler | Procesa requests idempotentes originados offline. |

#### 2.6.3.4. Infrastructure Layer

| Clase | Responsabilidad | Implementación propuesta |
|---|---|---|
| `ExecutionRepository` | Persistencia backend. | EF Core + PostgreSQL schema `field_ops`. |
| `EvidenceStorageClient` | Almacena/recupera archivos. | Adapter a object storage externo. |
| `RoomExecutionQueue` | Persistencia local en app nativa. | Room/SQLite. |
| `ExecutionSyncCoordinator` | Reintentos/sync de registros locales. | Kotlin + tecnología a decidir tras SP-01. |
| `CameraEvidenceAdapter` | Acceso a cámara cuando el requirement exige foto. | Android Camera/CameraX. |
| `ConnectivityMonitor` | Detecta disponibilidad de red para scheduling de sync. | Android connectivity APIs. |

#### 2.6.3.5. Bounded Context Software Architecture Component Level Diagrams

**Operator Native Android App:** `AssignedWork`, `ExecutionRecorder`, `EvidenceCapture`, `LocalQueue`, `SyncCoordinator`, `ApiClient`.

**API:** `ExecutionController`, `EvidenceController`, `ExceptionController`, `FieldOperationsApplication`, `ExecutionRepository`, `EvidenceStorageClient`.

#### 2.6.3.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.3.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.3.6.2. Bounded Context Database Design Diagram

| Tabla | Campos principales | Constraints |
|---|---|---|
| `field_ops.executions` | `execution_id`, `obligation_id`, `operator_id`, `status`, `started_at`, `submitted_at`, `obligation_version` | PK, UQ/idempotency según integración. |
| `field_ops.evidence` | `evidence_id`, `execution_id`, `type`, `reference`, `captured_at`, `metadata_json` | FK execution. |
| `field_ops.execution_exceptions` | `exception_id`, `execution_id`, `reason_code`, `description`, `reported_at` | FK execution. |
| `field_ops.assignments` | `assignment_id`, `obligation_id`, `operator_id`, `assigned_at`, `status` | UQ obligación activa. |

**Almacenamiento local Android**

| Tabla local | Propósito |
|---|---|
| `pending_execution_commands` | Comandos creados sin conexión pendientes de sync. |
| `cached_assigned_obligations` | Copia local del trabajo asignado necesario para el turno. |
| `pending_evidence_files` | Referencias locales de archivos pendientes de upload. |

### 2.6.4. Bounded Context: Compliance Management

#### 2.6.4.1. Domain Layer

| Clase | Categoría | Propósito | Miembros principales |
|---|---|---|---|
| `ComplianceCase` | Aggregate Root | Mantiene evaluación, resultado, observaciones y correctivas de una Execution. | `CaseId`, `ExecutionId`, `ObligationId`, `Status`, `Evaluations`, `Deviations`, `CorrectiveActions`, `Observations`; `RecordEvaluation()`, `ConfirmNonCompliance()`, `RegisterObservation()`, `AssignCorrectiveAction()`, `Close()` |
| `ComplianceEvaluation` | Entity | Registro de una evaluación realizada con reglas/versiones concretas. | `EvaluationId`, `CriteriaVersion`, `EvaluatedBy`, `EvaluatedAt`, `Result` |
| `ComplianceResult` | Value Object | Resultado de evaluación. | `Type`, `Reason`, `RuleReferences` |
| `ComplianceResultType` | Enum | Tipos de resultado. | `COMPLIANT`, `EXCEPTION_ACCEPTED`, `DEVIATION`, `NON_COMPLIANT` |
| `Deviation` | Entity | Diferencia identificada antes o sin necesidad de confirmar Non-compliance. | `DeviationId`, `Description`, `Severity` |
| `CorrectiveAction` | Entity | Acción posterior a una decisión que requiere corrección. | `ActionId`, `AssignedTo`, `DueAt`, `Status`, `CompletedAt` |
| `ClientObservation` | Entity | Observación posterior formulada por cliente. | `ObservationId`, `Description`, `ReceivedAt`, `SourceReference` |
| `ComplianceCriteriaSnapshot` | Value Object | Criterios versionados provenientes de Planning. | `ObligationDefinitionId`, `Version`, `AcceptanceCriterion`, `EvidenceRequirements` |
| `ComplianceEvaluator` | Domain Service | Aplica criterios sobre Execution/Evidence/Exception. | `Evaluate(caseInput, criteria)` |
| `IComplianceCaseRepository` | Repository interface | Persistencia. | `FindByExecution()`, `FindById()`, `Save()` |

**Regla crítica.** Una Corrective Action completada **no cambia retroactivamente** un `NON_COMPLIANT` a `COMPLIANT`. Si procede una reevaluación, se añade una nueva `ComplianceEvaluation` conservando las anteriores.

#### 2.6.4.2. Interface Layer

| Clase | Tipo | Operaciones |
|---|---|---|
| `ComplianceController` | Controller | `GET /compliance/cases/{id}`, `POST /compliance/cases/{id}/evaluate`, `GET /compliance/cases` |
| `CorrectiveActionController` | Controller | `POST /compliance/cases/{id}/actions`, `POST /actions/{id}/complete`, `POST /actions/{id}/verify` |
| `ClientObservationController` | Controller | `POST /compliance/cases/{id}/observations` |

#### 2.6.4.3. Application Layer

| Clase | Tipo | Responsabilidad / eventos |
|---|---|---|
| `EvaluateComplianceCommandHandler` | Command Handler | Construye input y ejecuta `ComplianceEvaluator`; publica `ComplianceResultRecorded`. |
| `RegisterClientObservationCommandHandler` | Command Handler | Añade observación; publica `ClientObservationRegistered`. |
| `AssignCorrectiveActionCommandHandler` | Command Handler | Añade acción; publica `CorrectiveActionAssigned`. |
| `CompleteCorrectiveActionCommandHandler` | Command Handler | Marca atención; publica `CorrectiveActionCompleted`. |
| `CloseComplianceCaseCommandHandler` | Command Handler | Cierra bajo reglas válidas; publica `ComplianceCaseClosed`. |
| `ExecutionSubmittedEventHandler` | Event Handler | Crea/prepara Compliance Case sin asumir automáticamente resultado. |
| `ComplianceResultRecordedEventHandler` | Event Handler | Publica integración hacia Reporting y notificación cuando corresponde. |

#### 2.6.4.4. Infrastructure Layer

| Clase | Responsabilidad | Implementación |
|---|---|---|
| `ComplianceCaseRepository` | Persistencia del agregado. | EF Core + PostgreSQL schema `compliance`. |
| `PlanningCriteriaReader` | Adapter para obtener snapshot/version del criterio publicado por Planning. | Contrato de integración interno. |
| `ExecutionReader` | Adapter para leer snapshot de Execution/Evidence publicada por Field Operations. | Contrato de integración interno. |
| `FcmNotificationGateway` | Notifica situaciones configuradas. | Firebase Cloud Messaging. |

#### 2.6.4.5. Bounded Context Software Architecture Component Level Diagrams

**Supervisor Cross-Platform App:** `ComplianceCases`, `ComplianceReview`, `CorrectiveActions`, `ApiClient`.

**API:** `ComplianceController`, `CorrectiveActionController`, `ComplianceApplication`, `ComplianceEvaluator`, `ComplianceCaseRepository`, `FcmNotificationGateway`.

#### 2.6.4.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.4.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.4.6.2. Bounded Context Database Design Diagram

| Tabla | Campos principales | Constraints |
|---|---|---|
| `compliance.compliance_cases` | `case_id`, `execution_id`, `obligation_id`, `status`, `opened_at`, `closed_at` | PK; UQ execution si solo existe un caso principal. |
| `compliance.evaluations` | `evaluation_id`, `case_id`, `criteria_version`, `result_type`, `reason`, `evaluated_by`, `evaluated_at` | FK case; append-oriented. |
| `compliance.deviations` | `deviation_id`, `case_id`, `description`, `severity`, `created_at` | FK case. |
| `compliance.corrective_actions` | `action_id`, `case_id`, `assigned_to`, `description`, `due_at`, `status`, `completed_at` | FK case. |
| `compliance.client_observations` | `observation_id`, `case_id`, `description`, `source_reference`, `received_at` | FK case. |

### 2.6.5. Bounded Context: Reporting & Insights

#### 2.6.5.1. Domain Layer

| Clase | Categoría | Propósito | Miembros principales |
|---|---|---|---|
| `ComplianceReport` | Aggregate Root | Representa un reporte generado para un alcance y periodo. | `ReportId`, `ServiceReference`, `SiteId?`, `Period`, `GeneratedAt`, `Status`, `Indicators`; `Generate()`, `Publish()` |
| `ReportPeriod` | Value Object | Intervalo temporal válido. | `StartDate`, `EndDate` |
| `ReportIndicator` | Entity / Value | Indicador consolidado. | `Name`, `Value`, `Unit`, `Definition` |
| `ReportStatus` | Enum | Estado del reporte. | `GENERATING`, `READY`, `PUBLISHED` |
| `ReportingProjection` | Read Model | Proyección local derivada de eventos de otros contexts. | Estado por obligación/sitio/periodo. |
| `ReportAssembler` | Domain/Application Service | Convierte proyección en Compliance Report. | `Build(scope, period)` |
| `IComplianceReportRepository` | Repository interface | Persistencia de reportes. | `Save()`, `FindById()`, `FindByPeriod()` |

#### 2.6.5.2. Interface Layer

| Clase | Tipo | Operaciones |
|---|---|---|
| `ReportController` | Controller | `POST /reports`, `GET /reports/{id}`, `GET /reports` |
| `DashboardController` | Controller | `GET /reporting/summary`, `GET /reporting/trends` |

#### 2.6.5.3. Application Layer

| Clase | Tipo | Responsabilidad / eventos |
|---|---|---|
| `GenerateComplianceReportCommandHandler` | Command Handler | Genera reporte desde proyección local; publica `ComplianceReportGenerated`. |
| `PublishComplianceReportCommandHandler` | Command Handler | Marca/publica reporte. |
| `PlanningEventProjectionHandler` | Event Handler | Actualiza metadatos de servicio/sitio. |
| `ExecutionEventProjectionHandler` | Event Handler | Actualiza estado de ejecución. |
| `ComplianceEventProjectionHandler` | Event Handler | Actualiza resultados y correctivas. |

#### 2.6.5.4. Infrastructure Layer

| Clase | Responsabilidad | Implementación |
|---|---|---|
| `ComplianceReportRepository` | Persistencia del agregado. | EF Core + PostgreSQL schema `reporting`. |
| `ReportingProjectionRepository` | Persistencia/read model. | PostgreSQL optimizado para lectura. |
| `ReportExporter` | Exporta representación compartible cuando se implemente. | PDF/CSV library según alcance. |

#### 2.6.5.5. Bounded Context Software Architecture Component Level Diagrams

**Supervisor Cross-Platform App:** `OperationalSummary`, `Reports`, `Trends`, `ApiClient`.

**API:** `ReportController`, `DashboardController`, `ReportingApplication`, `ReportAssembler`, `ReportingProjectionRepository`, `ComplianceReportRepository`.

#### 2.6.5.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.5.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.5.6.2. Bounded Context Database Design Diagram

| Tabla | Campos principales | Constraints |
|---|---|---|
| `reporting.compliance_reports` | `report_id`, `service_reference`, `site_id`, `period_start`, `period_end`, `generated_at`, `status` | PK; valid period. |
| `reporting.report_indicators` | `indicator_id`, `report_id`, `name`, `value`, `unit`, `definition` | FK report. |
| `reporting.reporting_projection` | `projection_id`, `service_reference`, `site_id`, `obligation_id`, `execution_status`, `compliance_result`, `period_key`, `updated_at` | Índices por service/site/period. |


## Referencias del capítulo

eGenya. (s. f.). *Gestión de servicios no operacionales con IA*. https://egenya.cl/

OrangeQC. (s. f.). *Janitorial inspection software with all the features you need*. https://www.orangeqc.com/features/

OrangeQC. (s. f.). *OrangeQC Pricing and Free Trial*. https://www.orangeqc.com/pricing/

OrangeQC. (s. f.). *Service checklists & employee visit tracking app*. https://www.orangeqc.com/features/service-checklists-employee-visit-tracking-app/

ServiceChannel. (s. f.). *ServiceChannel Provider App*. https://servicechannel.com/products/provider-app/

ServiceChannel. (s. f.). *Work Orders*. https://servicechannel.com/products/work-orders/

ServiceChannel. (s. f.). *ServiceChannel Mobile*. https://servicechannel.com/products/servicechannel-mobile/
