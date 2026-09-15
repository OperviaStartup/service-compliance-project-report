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

## Fuentes del análisis competitivo

1. [Apicbase, F&B Management System](https://get.apicbase.com/), consulta:
   septiembre de 2026.
2. [MarketMan, Restaurant Procurement Software](https://www.marketman.com/lp/restaurant-procurement-software),
   consulta: septiembre de 2026.
3. [WISK, Restaurant and Bar Inventory Management](https://www.wisk.ai/),
   consulta: septiembre de 2026.
4. [Restaurant365 Documentation](https://docs.restaurant365.com/), consulta:
   septiembre de 2026.
