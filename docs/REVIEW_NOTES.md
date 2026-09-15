# Review Notes — Service Compliance AV1

**Estado de la revisión:** 15 de septiembre de 2026.
**Alcance revisado:** `docs/PROJECT_CONTEXT.md`, `report/10-chapter-01.md`,
`report/11-chapter-02.md` y los recursos de `report/resources/10-chapter-01/`.

## Alcance y criterio de evidencia

Los capítulos oficiales del proyecto son los ubicados en `report/`. Los
archivos de SupplyWok en `docs/10-chapter-1.md` y `docs/20-chapter-2.md` son
material de referencia histórico y no forman parte del entregable de Service
Compliance.

No se encontró evidencia de entrevistas reales en el material revisado. Por
ello, una hipótesis plausible no debe presentarse como hallazgo, y ningún
diagrama actual prueba por sí mismo que una práctica, regla o necesidad haya
sido validada por usuarios.

## Problemas detectados en Chapter 1

- El encuadre del problema y la cadena de trazabilidad contractual son
  recuperables, pero el texto afirma prácticas operativas, beneficios y
  segmentos como si estuvieran validados.
- El análisis 5W+2H mezcla contexto del dominio con resultados que requerirían
  evidencia local. En especial, **How much** no define una línea base, unidad,
  fuente, población ni periodo de medición.
- Las personas operarias y supervisoras se nombran como segmentos objetivo sin
  distinguir entre organización compradora, cliente contractual, decisor,
  pagador y usuario del producto.
- Las características demográficas se presentan sin que existan entrevistas
  que las sustenten. Deben eliminarse o quedar explícitamente pendientes de
  validación.
- El Lean UX Canvas contiene QR, ubicación, foto, offline, alertas y reportes
  como solución preseleccionada. Son hipótesis de producto, no requisitos.
- Las métricas numéricas de adopción y éxito no cuentan con línea base ni plan
  de medición. Deben sustituirse por criterios de aprendizaje o dejarse como
  TODO de investigación.

## Problemas detectados en Chapter 2

- Las secciones 2.1 a 2.4 están vacías mientras el capítulo ya describe
  EventStorming, contextos y arquitectura. Esto invierte la cadena
  investigación → needfinding → requirements → DDD → arquitectura.
- Se afirma que hubo una sesión de EventStorming de dos horas y que se utilizó
  Miro sin evidencia que deba o pueda presentarse como investigación formal.
  La documentación debe describir los artefactos como preliminares hasta que
  el equipo los revise y apruebe.
- La investigación competitiva, el diseño de entrevistas, el registro de
  entrevistas y el análisis de entrevistas aún no están documentados.
- No existe un vínculo trazable entre hallazgos, tareas reales, requisitos,
  límites de dominio y contenedores de software.

## Revisión de artefactos de dominio y arquitectura

| Artefacto | Diagnóstico | Acción requerida |
|---|---|---|
| Big Picture EventStorming | Mezcla eventos de negocio con sesión, autenticación, QR, GPS, foto, sincronización y notificaciones. Varios eventos describen efectos técnicos, no hechos del dominio. | Revisar los eventos con el equipo; conservar solo candidatos marcados como provisionales hasta validación. |
| Candidate Context Discovery | Los diagramas contienen páginas, API, manejo de datos, inicio/fin y decisiones de interfaz. No evidencian límites emergentes desde eventos pivote. | Redecidir límites usando eventos y lenguaje ubicuo aprobados por el equipo. |
| Domain Storytelling | Los flujos usan API, Mobile App, Database y Sistema como actores principales. Esto no representa la colaboración actor → actividad → objeto de trabajo → actor. | Redefinir historias con actores del dominio y objetos de trabajo; producir diagramas reproducibles tras aprobación conceptual. |
| Bounded Context Canvases | Los cinco contextos actuales pueden orientar la discusión, pero sus capacidades, reglas y dependencias presuponen requisitos aún no validados. Authentication aparece como contexto de negocio. | Mantenerlos solo como candidatos; reevaluar Authentication como capacidad genérica/de soporte y separar evaluación de cumplimiento de incidentes si el dominio lo exige. |
| Context Mapping | No identifica con precisión upstream/downstream, contratos publicados ni motivos de los patrones. Modela Open Host Service como si fuera un contexto. | Diseñar el mapa solo tras estabilizar candidate contexts; justificar Customer/Supplier, ACL, Partnership, Conformist, Shared Kernel, Published Language u OHS cuando correspondan. |
| C4 Context | Es legible como hipótesis, pero asume servicios externos y usuarios finales sin requisitos aprobados. | Revisar actores, límites del sistema e integraciones luego del dominio. |
| C4 Container | Agrupa Kotlin y Flutter en una sola Mobile App y anticipa tecnología, base de datos y servicios. | Representar aplicaciones nativa y cross-platform como contenedores/productos distintos si el alcance académico confirma ambos. |
| Deployment | Presupone Railway, Firebase y la topología de despliegue. | Decidir infraestructura solo después de confirmar los contenedores e integraciones necesarias. |

## Artefactos que pueden conservarse

- La proposición de que un contrato puede originar obligaciones de servicio.
- La cadena conceptual desde contrato hasta reporte de cumplimiento.
- La distinción inicial entre ejecución, evidencia, evaluación de cumplimiento,
  no conformidad y acción correctiva, siempre como vocabulario candidato.
- La intención de soportar una experiencia móvil para trabajo de campo, sujeta
  a que la investigación confirme la necesidad y las restricciones operativas.
- Los recursos visuales históricos como referencia de formato, no de contenido
  validado ni de sesiones efectivamente realizadas.

## Artefactos que deben corregirse o rehacerse conceptualmente

- 5W+2H, Lean UX Problem Statements, Assumptions, Hypotheses y Canvas.
- Segmentación: comprador, cliente, decisor, supervisor, operario y otros
  posibles roles.
- Competidores, estrategia y diseño de entrevistas.
- Needfinding: candidate personas, tareas existentes, journey As-Is, empathy
  findings, EventStorming y lenguaje ubicuo.
- Requirements y trazabilidad hacia DDD.
- Candidate contexts, Domain Stories, canvases, Context Map y niveles C4.

## Decisiones tratadas incorrectamente como hechos

- Que QR, NFC, GPS, fotografías, timestamps, operación offline, alertas push
  o reportes automáticos sean necesarios o aceptados.
- Que una obligación contractual pueda transformarse automáticamente en una
  tarea ejecutable en todos los contratos.
- Que toda fotografía sea evidencia suficiente o que toda evidencia deba
  almacenarse en un servicio externo.
- Que el incumplimiento se detecte exclusivamente por vencimiento temporal o
  que siempre genere un incidente y una acción correctiva.
- Que Opervia cobre a una empresa proveedora, al cliente contratante o a otra
  parte; y que operarios y supervisores sean los únicos usuarios relevantes.
- Que los límites `Contract & Obligation Management`, `Field Execution &
  Evidence`, `Incident & Corrective Action` y `Compliance Reporting` sean los
  límites correctos del dominio.
- Que Firebase, Railway, Spring Boot, MySQL, Kotlin o Flutter formen parte de
  la arquitectura final.

## Información necesaria para sustituir lo provisional

1. Entrevistas reales con consentimiento, rol organizacional y notas o
   transcripción autorizada.
2. Ejemplos autorizados de contratos, formatos de ejecución, evidencias y
   reportes, con datos sensibles anonimizados.
3. Fuentes verificables para dimensionar el problema y comparar competidores.
4. Decisiones académicas confirmadas sobre aplicaciones móviles, integraciones
   de dispositivo y restricciones de despliegue.
5. Revisión y aprobación humana de cada modelo de dominio antes de traducirlo
   a Mermaid, PlantUML o Structurizr DSL.
