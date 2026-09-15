# Capítulo I: Presentación

## 1.1. Startup Profile

### 1.1.1. Descripción de la startup

Opervia es la startup académica que desarrolla **Service Compliance** para el
dominio inicial de servicios de limpieza tercerizada en Perú. El proyecto
explora cómo una organización prestadora puede mantener trazabilidad entre lo
acordado con su cliente y lo que finalmente se ejecuta en cada ubicación de
servicio.

El concepto rector del producto es el siguiente:

> **Service Contract → Service Obligation → Execution → Evidence → Compliance
> Evaluation → Non-compliance → Corrective Action → Compliance Report**

Esta cadena es un **modelo de problema candidato**, no una afirmación de que
todas las empresas del sector trabajen de la misma manera. La investigación
deberá comprobar si las condiciones contractuales se traducen en obligaciones
operativas explícitas, qué prueba se considera aceptable y cuándo un desvío
debe escalarse.

Service Compliance no se plantea como un gestor genérico de tareas: una
actividad operativa solo tendría sentido en el producto si se relaciona con una
condición u obligación de un servicio contratado.

**Misión provisional.** Facilitar la trazabilidad de compromisos de servicio y
su cumplimiento operativo para organizaciones de servicios tercerizados,
siempre que la investigación confirme que esa trazabilidad responde a una
necesidad prioritaria.

**Visión provisional.** Convertirse en una alternativa digital confiable para
consultar y explicar el estado de cumplimiento de servicios tercerizados, sin
presuponer todavía su modelo comercial, alcance funcional ni mercado final.

### 1.1.2. Perfiles de integrantes del equipo

La información de integrantes se conserva del reporte previo y debe
actualizarse por el equipo antes de la entrega final si su composición cambió.

| N.° | Integrante | Código | Carrera | Aporte declarado |
|---:|---|---|---|---|
| 1 | Arias Tasayco, Jean Pool Alexander | U202414054 | Ingeniería de Software | Análisis de requisitos, definición arquitectónica, modelado de dominio, backend, aplicaciones móviles e integración. |

<sub>*Tabla 1. Perfil de integrante disponible en el material revisado.*</sub>

> **TODO — equipo:** confirmar integrantes, códigos, fotografías autorizadas y
> responsabilidades vigentes antes de publicar la versión final.

## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

La hipótesis central del proyecto es que, en algunos servicios de limpieza
tercerizada, la información sobre condiciones contractuales, ejecución en
campo, evidencia, supervisión y respuesta ante desvíos puede estar repartida
en distintos medios. Si esa fragmentación existe, podría dificultar que la
empresa prestadora y su cliente expliquen qué obligación se atendió, con qué
evidencia y bajo qué criterio se evaluó su cumplimiento.

Esta formulación no atribuye aún prácticas, costos, frecuencia de incidentes o
impactos cuantificables a una población. Tales afirmaciones requieren fuentes
sectoriales verificables o entrevistas reales.

#### Análisis 5W+2H

| Dimensión | Formulación actual | Estado de evidencia |
|---|---|---|
| **What — qué ocurre** | Puede existir falta de trazabilidad entre condiciones de servicio, obligaciones, ejecución, evidencia y evaluación de cumplimiento. | **Hypothesis — Pending validation** |
| **Who — quiénes intervienen** | Podrían intervenir la organización prestadora, la organización cliente, quien administra el contrato, quien supervisa y quien ejecuta el servicio. Un mismo rol puede desempeñar más de una función. | **Hypothesis — Pending validation** |
| **Where — dónde ocurre** | En ubicaciones donde una empresa presta servicios de limpieza a otra organización bajo acuerdos de servicio. | Alcance inicial del proyecto; pendiente de delimitar con evidencia. |
| **When — cuándo se vuelve crítico** | Podría hacerse visible al asignar trabajo, registrar ejecución, verificar evidencia, detectar un desvío, recibir un reclamo o consolidar un reporte. | **Hypothesis — Pending validation** |
| **Why — por qué importa** | Una trazabilidad insuficiente podría dificultar coordinación, supervisión, respuesta ante reclamos y explicación del cumplimiento. | **Hypothesis — Pending validation** |
| **How — cómo se manifiesta** | Podría manifestarse mediante registros dispersos, ambigüedad sobre lo acordado, evidencia incompleta, comunicación informal o seguimiento tardío. | **Hypothesis — Pending validation** |
| **How much — cuánto impacta** | No se dispone de línea base, población, periodo, indicador ni fuente local para cuantificar el impacto. | **TODO — fuente o medición requerida** |

<sub>*Tabla 2. Formulación del problema sin presentar hipótesis como evidencia.*</sub>

#### Objetivo de la solución

Explorar una solución que permita relacionar compromisos de servicio con
obligaciones operativas, sus ejecuciones, la evidencia disponible y la
evaluación de cumplimiento. El objetivo no confirma todavía que todas las
relaciones puedan automatizarse ni que una forma de evidencia sea universal.

#### Delimitación inicial del alcance

- Dominio inicial: servicios de limpieza tercerizada en Perú.
- Unidad de análisis inicial: la relación entre un acuerdo de servicio, una
  obligación operativa y su resultado verificable.
- Fuera de alcance hasta contar con evidencia: gestión general de personal,
  nómina, planificación financiera, administración genérica de tareas y
  automatización integral de contratos.
- Capacidades como fotografía, QR, NFC, GPS, timestamps, operación offline,
  alertas o reportes automáticos son **hipótesis de producto** y no requisitos
  aprobados.

### 1.2.2. Lean UX Process

#### 1.2.2.1. Lean UX Problem Statement

**Estado actual candidato.** Algunas organizaciones de servicios tercerizados
podrían coordinar obligaciones, ejecución y evidencia mediante medios
separados.

**Brecha a investigar.** Aún no se conoce si las herramientas disponibles y
las prácticas actuales permiten explicar el cumplimiento de una condición
contractual de manera suficiente para cada actor involucrado.

**Dirección de producto candidata.** Service Compliance podría aportar una
trazabilidad consultable entre contrato, obligación, ejecución, evidencia,
evaluación y respuesta a un desvío.

**Aprendizaje inicial buscado.** Identificar cómo se traduce hoy un contrato
en trabajo, quién decide qué constituye evidencia aceptable, qué información
se pierde, quién pagaría por resolver el problema y quién utilizaría una
eventual solución.

#### 1.2.2.2. Lean UX Assumptions

| ID | Suposición | Tipo | Estado |
|---|---|---|---|
| BA-01 | Existe una organización dispuesta a pagar por mejorar la trazabilidad de cumplimiento. | Comercial | **Hypothesis — Pending validation** |
| BA-02 | El pagador puede ser distinto del usuario operativo. | Segmentación | **Hypothesis — Pending validation** |
| UA-01 | Una persona que ejecuta el servicio necesita conocer qué se espera de su trabajo. | Usuario | **Hypothesis — Pending validation** |
| UA-02 | La supervisión requiere comparar expectativa, ejecución y evidencia. | Usuario | **Hypothesis — Pending validation** |
| FA-01 | El registro móvil podría reducir fricción en campo. | Producto | **Hypothesis — Pending validation** |
| FA-02 | Una evidencia digital podría resultar útil para ciertos acuerdos. | Producto | **Hypothesis — Pending validation** |
| FA-03 | QR, NFC, GPS, fotografías y modo offline podrían no aportar valor o no ser aceptados. | Riesgo de producto | **Hypothesis — Pending validation** |

<sub>*Tabla 3. Suposiciones que orientan investigación; no son requisitos.*</sub>

#### 1.2.2.3. Lean UX Hypothesis Statements

| ID | Hipótesis de aprendizaje | Señal que se buscará en investigación real |
|---|---|---|
| H-01 | Creemos que algunos responsables necesitan explicar el cumplimiento de un servicio a partir de condiciones previamente acordadas. | Relatos concretos sobre contratos, supervisión, reclamos y reportes. |
| H-02 | Creemos que algunos operarios necesitan una referencia operativa clara para ejecutar un servicio. | Descripción del proceso actual de asignación, dudas y resolución. |
| H-03 | Creemos que el principal problema podría ser la evidencia, la comunicación, la asignación o el reclamo; no se presume cuál predomina. | Comparación de situaciones reales y sus consecuencias. |
| H-04 | Creemos que una obligación no siempre puede derivarse automáticamente del contrato. | Casos de interpretación humana, excepciones y acuerdos verbales. |

#### 1.2.2.4. Criterios de aprendizaje y medición

No se fijan porcentajes de adopción ni metas de impacto sin línea base. Antes
de definir métricas de resultado, el equipo debe registrar:

1. población y criterio de selección de participantes;
2. proceso observado y frecuencia de la situación;
3. definición operacional de evidencia, cumplimiento, no conformidad y acción
   correctiva;
4. unidad y periodo de medición; y
5. consentimiento y resguardo de datos cuando correspondan.

## 1.3. Segmentos y actores candidatos

La segmentación no se basará en edad, distrito ni otros atributos demográficos
hasta contar con entrevistas u otra fuente válida. En esta etapa se distinguen
relaciones de negocio y roles de uso, que no son equivalentes.

| Categoría | Actor candidato | Posible relación con el problema | Estado |
|---|---|---|---|
| Organización proveedora | Empresa que presta el servicio | Puede operar, administrar contratos y eventualmente pagar por la solución. | **Candidate — Pending validation** |
| Organización cliente | Empresa que contrata el servicio | Puede definir condiciones, recibir el servicio o presentar reclamos. | **Candidate — Pending validation** |
| Decisor / pagador | Responsable de comprar o aprobar una solución | Puede pertenecer a cualquiera de las organizaciones. | **Candidate — Pending validation** |
| Administrador contractual | Persona que interpreta o acuerda condiciones de servicio | Puede convertir acuerdos en criterios operativos. | **Candidate — Pending validation** |
| Supervisor | Persona que verifica o coordina el servicio | Puede revisar ejecuciones, evidencias, desvíos y acciones. | **Candidate — Pending validation** |
| Operario de campo | Persona que realiza una actividad de servicio | Puede recibir instrucciones, ejecutar y comunicar resultados. | **Candidate — Pending validation** |

<sub>*Tabla 4. Segmentos y actores candidatos; no son personas ni perfiles validados.*</sub>

### 1.3.1. Plan de investigación UX

El siguiente paso no es validar funcionalidades, sino descubrir el proceso
actual. El plan se desarrolla en Chapter 2 e incluye análisis competitivo,
entrevistas abiertas, registro de evidencia real, síntesis de hallazgos y
needfinding. Mientras no existan entrevistas, los escenarios provisionales se
mantienen separados en `docs/PROVISIONAL_RESEARCH.md`.

## Referencias y fuentes pendientes

> **TODO — fuentes:** incorporar fuentes públicas y verificables sobre el
> sector únicamente cuando respalden una afirmación concreta. No usar una
> fuente general para inferir prácticas, costos o comportamiento de las
> organizaciones entrevistadas.
