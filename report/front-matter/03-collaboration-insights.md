<div style="page-break-before: always;"></div>

## Project Report Collaboration Insights

### Repositorio del Project Report

El informe de Service Compliance, desarrollado por el equipo Opervia, se mantiene en el siguiente repositorio de GitHub:

**Repositorio:**  
https://github.com/OperviaStartup/service-compliance-project-report

Durante la elaboración de AV1, el equipo distribuyó el trabajo entre la definición y revisión del Capítulo I, investigación con usuarios, Needfinding, Requirements Specification y artefactos de diseño de software del Capítulo II. Los aportes fueron integrados progresivamente en el repositorio mediante commits y, en determinados trabajos de reconstrucción documental, mediante ramas y Pull Requests hacia `main`.

### Evidencia de colaboración — AV1

<img src="../resources/front-matter/commits-general.png" alt="Contribuciones de los integrantes al Project Report">

*Figura 1. Analíticos de contribución del repositorio del Project Report durante AV1.*

Al cierre de la elaboración de AV1, el historial del repositorio registra contribuciones de los seis integrantes del equipo.

| Integrante | Usuario de GitHub | Principales aportes en AV1 |
|---|---|---|
| Arias Tasayco, Jean Pool Alexander | `Jean-AT` | Capítulo I, revisión e integración del informe, EventStorming y preparación del documento final. |
| Ayasta Martel, Zayd Jaffar | `ZaydAyasta` | Requirements Specification, revisión del Capítulo I y Capitulo II, front matter, tabla de contenidos y documentación general del repositorio. |
| Blancas Chávez, Carlos Franco | `CarlosBlancas969` | Strategic-Level Domain-Driven Design y artefactos relacionados del Capítulo II. |
| Flores Eusebio, Angel Thyago | `angelfdevs` | Análisis competitivo, entrevistas y actualización de evidencias y contenido del Capítulo II. |
| Montes Maza, Augusto Sebastian | `asmmaza` | User Personas, Journey Mapping, Empathy Mapping y otros artefactos de Needfinding. |
| Sánchez Espinoza, Mathias Enrique | `Nounz27` | Diseño y actualización de entrevistas, análisis asociado y recursos del Capítulo II. |

La evidencia mostrada corresponde al historial de commits del repositorio y es consistente con las modificaciones relevantes resumidas en el Registro de Versiones del Informe.

<div style="page-break-before: always;"></div>

### Evidencia de colaboración — TP (TB1)

Para la entrega parcial correspondiente al **TB1 – Stage Review**, el equipo organizó la implementación en dos líneas de trabajo relacionadas: primero la Landing Page y luego el backend REST. La documentación, los artefactos y las evidencias se integraron posteriormente en el Project Report.

La colaboración del equipo se evidencia mediante los repositorios públicos, el historial de commits, la organización del Sprint 1 y la distribución de responsabilidades entre producto, UX, arquitectura, backend, validación y documentación.

#### Repositorios utilizados

| Producto | Repositorio | Alcance de la entrega |
|---|---|---|
| Landing Page | https://github.com/OperviaStartup/service-compliance-landingpage | Sitio estático responsive, i18n, accesibilidad y despliegue mediante GitHub Pages. |
| Web Service | https://github.com/OperviaStartup/serviceComplianceAPI | API REST, autenticación, PostgreSQL, DDD, Swagger, pruebas, Docker y Render. |
| Project Report | https://github.com/OperviaStartup/service-compliance-project-report | Integración del informe, evidencias y trazabilidad documental. |

#### Evidencia visual de colaboración

<!-- Reemplazar esta ruta por la captura real de GitHub Insights/Contributors y del historial de commits de los repositorios. -->
<img src="../resources/front-matter/collaboration-tb1.png" alt="Analíticos de colaboración y commits correspondientes al TB1">

*Figura 2. Analíticos de colaboración y commits del equipo durante la entrega parcial TB1.*

La captura debe mostrar, como mínimo, los analíticos de contribución y una vista del historial de commits. Si se utilizan capturas separadas, agregarlas en las siguientes rutas:

- `../resources/front-matter/landing-collaboration-tb1.png`
- `../resources/front-matter/backend-collaboration-tb1.png`
- `../resources/front-matter/report-collaboration-tb1.png`

#### Desarrollo de la Landing Page

La primera línea de trabajo correspondió a la Landing Page de Opervia / Service Compliance. Se organizó el sitio estático conservando su lenguaje visual y se añadieron mejoras estructurales, accesibilidad semántica, meta description, navegación interna, internacionalización español-inglés y workflow de despliegue a GitHub Pages.

Los commits principales identificados en el repositorio de la Landing Page son:

| Commit | Mensaje | Evidencia del aporte |
|---|---|---|
| `05ff650` | `feat: landing` | Primera implementación de la Landing Page. |
| `1dea1be` | `feat: add workflow` | Incorporación del workflow de GitHub Pages. |
| `4bc7803` | `docs: update` | Actualización documental del sitio. |
| `0066407` | `feat: html update i18n` | Organización HTML, internacionalización y mejoras de accesibilidad. |

La interpretación de esta evidencia es que el producto web avanzó desde una primera implementación visual hasta una versión organizada y publicable, manteniendo la separación entre contenido, navegación y despliegue estático.

#### Desarrollo del backend REST

Después de establecer la experiencia de presentación del producto, el equipo implementó el backend requerido para el flujo operativo del Sprint 1. Los aportes técnicos comprenden autenticación JWT, autorización por roles, persistencia PostgreSQL, migraciones Flyway, obligaciones, ejecuciones, evidencias, validaciones, errores manejables, OpenAPI/Swagger, pruebas automatizadas, pruebas E2E y configuración Docker/Render.

Los commits principales relacionados con el backend son:

| Commit | Mensaje | Evidencia del aporte |
|---|---|---|
| `d6f2097` | `feat: add DDD backend foundation` | Estructura inicial DDD y base del backend. |
| `10dcc86` | `feat: add execution evidence flow` | Flujo de ejecución y evidencias. |
| `b1d4c13` | `feat: add versioned database migration` | Migración versionada para PostgreSQL. |
| `b2402a4` | `test: cover authentication and execution flows` | Pruebas de autenticación y ejecución. |
| `e520bb1` | `feat: secure supervisor bootstrap and role tests` | Bootstrap seguro y pruebas de roles. |
| `c9cf3e2` | `feat: validate API request payloads` | Validación de requests. |
| `8e11172` | `docs: document REST API with OpenAPI` | Documentación OpenAPI y Swagger. |
| `cab408b` | `feat: standardize API error responses` | Contrato común de errores manejables. |
| `33c84d4` | `test: verify real PostgreSQL user workflow` | Flujo HTTP E2E contra PostgreSQL real. |
| `7b3fad8` | `fix: build application in Render Docker image` | Corrección del build Docker para Render. |

La interpretación de estos commits es que el backend evolucionó incrementalmente desde la fundación DDD hasta un servicio desplegable. El historial muestra una secuencia coherente: estructura, funcionalidad, persistencia, seguridad, validación, documentación, pruebas y despliegue.

#### Distribución de responsabilidades del equipo

| Integrante | Responsabilidad en TP/TB1 | Evidencia que debe asociarse |
|---|---|---|
| Arias Tasayco, Jean Pool Alexander | Backend e integración: API REST, PostgreSQL, Docker, Render y pruebas E2E. | Commits del backend, resultados de pruebas y captura del despliegue. |
| Ayasta Martel, Zayd Jaffar | Product Backlog, trazabilidad de historias, front matter y revisión de la entrega. | Tablero del Sprint, commits documentales y revisión del informe. |
| Blancas Chávez, Carlos Franco | Arquitectura DDD, Bounded Contexts, diagramas y revisión técnica. | Diagramas, estructura de paquetes y revisión de arquitectura. |
| Flores Eusebio, Angel Thyago | Validación de negocio y escenarios supervisor-operador. | Matriz de aceptación y evidencias de validación. |
| Montes Maza, Augusto Sebastian | UX móvil, pantallas core y revisión de experiencia. | Capturas de pantallas y flujo móvil. |
| Sánchez Espinoza, Mathias Enrique | Entrevistas, validación con usuarios y análisis heurístico. | Guion, registros y resultados de entrevistas. |

La distribución se relaciona con el Sprint 1 documentado en el Capítulo IV. Cada integrante debe adjuntar la evidencia concreta de su participación, incluso cuando el aporte haya sido de revisión, validación, diseño o documentación y no únicamente de programación.

#### Interpretación de la colaboración

La colaboración del TP/TB1 se desarrolló de manera incremental. Primero se consolidó la Landing Page y su workflow de publicación; luego se implementó el backend REST y finalmente se integraron las evidencias en el informe. La participación combinó desarrollo, arquitectura, producto, UX, validación y documentación.

Los analíticos y commits deben interpretarse junto con el reparto de responsabilidades: el volumen de commits no representa por sí solo toda la colaboración, porque la rúbrica también considera artefactos, revisiones, entrevistas, diseño, pruebas y participación en los productos de la solución. La evidencia final debe coincidir con el Registro de Versiones del Informe y con el Sprint Backlog.
