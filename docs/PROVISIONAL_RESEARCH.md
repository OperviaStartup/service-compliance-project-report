# Provisional Research Assumptions — Service Compliance

## Propósito y límites

Este documento sirve para preparar investigación y artefactos preliminares de
Service Compliance cuando aún no existen entrevistas reales. **No forma parte
de la evidencia oficial del proyecto** y no debe citarse como resultado
empírico, testimonio, estadística ni validación de requisitos.

Cada escenario de este documento es una combinación plausible, no una
descripción de una empresa, persona o proceso real. Debe reemplazarse o
contrastar con evidencia autorizada antes de decidir requisitos, límites de
dominio o arquitectura.

## Hipótesis que podrían apoyar la idea

| ID | Supuesto provisional | Estado |
|---|---|---|
| P-01 | La información necesaria para explicar un servicio puede quedar distribuida entre contrato, plan de trabajo, mensajes, listas y registros de supervisión. | **Hypothesis — Provisional — Pending validation** |
| P-02 | Un supervisor podría invertir tiempo en reconstruir qué se esperaba, qué se ejecutó y qué evidencia existe. | **Hypothesis — Provisional — Pending validation** |
| P-03 | Un cliente podría requerir una explicación estructurada al consultar un posible incumplimiento. | **Hypothesis — Provisional — Pending validation** |
| P-04 | Una organización prestadora podría valorar consolidar el estado de varias ubicaciones o contratos. | **Hypothesis — Provisional — Pending validation** |

## Hipótesis que cuestionan la idea

| ID | Supuesto provisional | Estado |
|---|---|---|
| C-01 | El problema principal puede ser comunicación o asignación, no trazabilidad de evidencia. | **Hypothesis — Provisional — Pending validation** |
| C-02 | La supervisión presencial, una hoja de cálculo o un canal de mensajería podrían ser suficientes para ciertas operaciones. | **Hypothesis — Provisional — Pending validation** |
| C-03 | Una obligación contractual puede ser demasiado ambigua, variable o negociada para transformarse automáticamente en una tarea. | **Hypothesis — Provisional — Pending validation** |
| C-04 | El comprador puede no percibir retorno suficiente para pagar por una herramienta adicional. | **Hypothesis — Provisional — Pending validation** |
| C-05 | Registrar información adicional puede aumentar la carga de trabajo y reducir la adopción. | **Hypothesis — Provisional — Pending validation** |

## Procesos actuales posibles

| Escenario provisional | Posible secuencia | Pregunta de validación |
|---|---|---|
| A: coordinación informal | Un responsable comunica instrucciones por llamada o mensajería; el operario confirma verbalmente; el supervisor registra excepciones aparte. | ¿Qué información se pierde entre instrucción, ejecución y supervisión? |
| B: control documental | El contrato se convierte manualmente en listas o cronogramas; se archivan registros y se consolidan reportes al cierre. | ¿Quién interpreta cada condición y cómo se gestionan cambios? |
| C: supervisión por excepción | El trabajo se ejecuta rutinariamente; solo se documentan reclamos, hallazgos o incumplimientos. | ¿Cómo se demuestra el cumplimiento cuando no hubo un incidente? |
| D: operación distribuida | Cada ubicación gestiona sus propios registros; la organización consolida cuando un cliente lo solicita. | ¿Qué se duplica y qué impide una consolidación confiable? |

Todos los escenarios son **Hypothesis — Provisional — Pending validation**.

## Evidencia aceptable posible

- Firma, checklist, parte físico, correo, mensaje, llamada registrada o
  confirmación de un responsable.
- Fotografía, solo cuando la política contractual, el contexto y la calidad de
  la imagen permitan interpretarla.
- Registro de hora o ubicación, solo si existe autorización, propósito claro y
  proporcionalidad.
- Inspección o conformidad del cliente.
- Ninguna evidencia adicional para actividades rutinarias de bajo riesgo.

No se presupone que una fotografía sea suficiente, que QR/NFC agregue valor ni
que GPS sea aceptado. Todos los elementos son **Hypothesis — Provisional —
Pending validation**.

## Conflictos contractuales posibles

- Una condición del contrato carece de criterio observable o responsable claro.
- El cliente solicita una actividad no incluida originalmente.
- La frecuencia o ventana horaria cambia sin actualización formal.
- La evidencia se captura, pero no satisface el estándar esperado por el
  cliente.
- Se disputa si un desvío constituye incumplimiento, una excepción autorizada
  o un problema atribuible a terceros.
- Una acción correctiva se ejecuta, pero no resuelve la causa del reclamo.

## Necesidades y fricciones posibles por actor

| Actor candidato | Necesidad o fricción provisional |
|---|---|
| Supervisor | Puede necesitar priorizar qué revisar, interpretar excepciones y responder a consultas sin reconstruir información de múltiples canales. |
| Operario | Puede necesitar instrucciones comprensibles, una forma viable de comunicar una excepción y una carga de registro compatible con su trabajo real. |
| Organización cliente | Puede necesitar conocer el estado de compromisos, aceptar o cuestionar evidencia y escalar reclamos con contexto. |
| Organización prestadora | Puede necesitar coordinar contratos, sedes, responsables y respuestas sin comprometer la operación. |
| Decisor o pagador | Puede necesitar justificar inversión, adopción y cambio operativo frente a alternativas ya existentes. |

Estas necesidades son **Hypothesis — Provisional — Pending validation**. No
determinan funcionalidades.

## Riesgos de producto a comprobar

1. QR puede no resolver la principal fuente de incertidumbre.
2. GPS puede ser innecesario, impreciso, costoso o rechazado por trabajadores,
   clientes o políticas internas.
3. Las fotografías pueden resultar insuficientes, sensibles o difíciles de
   interpretar.
4. La falta de conectividad puede ser irrelevante, ocasional o tan frecuente
   que exija un flujo distinto al previsto.
5. El problema prioritario puede ser comunicación, asignación, reclamos o
   interpretación contractual, no la captura de evidencia.
6. El modelo comercial y la separación entre comprador y usuario pueden variar
   por tipo de contrato.

## Reemplazo por evidencia real

Para retirar el estado provisional, el equipo debe conservar de manera
autorizada: perfil organizacional y rol de cada participante, guía aplicada,
notas o transcripción, consentimiento cuando corresponda, ejemplos
anonimizados y una síntesis que trace cada hallazgo a la evidencia disponible.
