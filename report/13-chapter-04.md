<div style="page-break-before: always;"></div>

<a id="capitulo-iv-product-implementation-validation"></a>
# Capítulo IV: Product Implementation & Validation

Este capítulo registra el incremento implementado de Service Compliance. El proyecto integra una REST API en Java 17 y Spring Boot 4.1.1, persistencia mediante PostgreSQL, despliegue en Render, una Landing Page publicada mediante GitHub Pages y prototipos de experiencia en Figma.

La API de Sprint 1 cubre el flujo técnico inicial de autenticación/autorización, consulta y registro de obligaciones, ejecución y evidencia. No se atribuyen a ese incremento los futuros módulos completos de Service Planning, Compliance Management, Corrective Actions, Reports, administración empresarial ni sincronización offline. En particular, el registro de una ejecución a través de la API no implica que un supervisor haya determinado su Compliance Result.

<a id="41-software-configuration-management"></a>
## 4.1. Software Configuration Management

<a id="411-software-development-environment-configuration"></a>
### 4.1.1. Software Development Environment Configuration

El equipo organiza documentación, diseño e implementación en herramientas diferentes, vinculadas mediante repositorios y artefactos reproducibles. La configuración constatada en el backend incluye Spring Boot, Gradle, JPA/Hibernate, Flyway, PostgreSQL, Spring Security, JWT, validación de solicitudes y documentación OpenAPI/Swagger. Esta selección corresponde al código del repositorio `serviceComplianceAPI`, no al diseño anterior que mencionaba ASP.NET Core.

| Actividad | Herramienta / producto | Aplicación dentro de Opervia | Referencia |
|---|---|---|---|
| Gestión de historias y Sprint | Trello | Backlog, prioridades y tareas | Enlace del tablero del equipo; comprobar acceso público |
| Versionamiento | Git y GitHub | Report, Landing Page y API en repos independientes | https://github.com/OperviaStartup |
| Diseño UI/UX | Figma | Wireframes, mockups y prototipos | Archivo del equipo «Grupo-3: Service Compliance» |
| Diagramas de flujos | Lucidchart / Overflow | Wireflows y User Flows | Archivo de diagramas del equipo |
| Desarrollo backend | Java 17, Spring Boot 4.1.1 y Gradle | REST API propia | Repositorio `serviceComplianceAPI`, `build.gradle` |
| Persistencia | PostgreSQL, JPA/Hibernate, Flyway | Entidades y migraciones del backend | Repositorio backend y despliegue Render |
| Seguridad de API | Spring Security, JWT y BCrypt | Autenticación, contraseñas y autorización por rol | Repositorio backend |
| Documentación/ensayos | OpenAPI, Swagger UI | Documentación e invocación de endpoints | `/swagger-ui.html` y `/api-docs` de la API |
| Despliegue backend | Docker y Render | Construcción y exposición del servicio | Render, servicio `service-compliance-api` |
| Landing Page | HTML5, CSS3, JavaScript | Web informativa responsiva | `service-compliance-landingpage` |
| Despliegue web | GitHub Pages, GitHub Actions | Publicación del Landing Page | Workflow `pages.yml` |

El `build.gradle` del repositorio incluye Spring Boot `4.1.1`, toolchain Java 17, starters para web, data JPA, security y validation, Flyway y driver PostgreSQL. Los servicios externos de notificación y los mecanismos móviles de captura/sincronización forman parte del diseño posterior y no se presentan como integraciones terminadas.

<img src="resources/13-chapter-04/01-development-environment.png" alt="Entorno de desarrollo del backend" />

*Figura 4.1. Entorno de desarrollo utilizado para los módulos de la REST API.*

<a id="412-source-code-management"></a>
### 4.1.2. Source Code Management

El equipo mantiene repositorios separados para documentación, Landing Page y backend, todos dentro de la organización OperviaStartup. Esta separación distingue la evolución del informe y los artefactos UX/UI de los productos desplegables y permite relacionar cada incremento con sus commits.

| Producto | Repositorio | Estado en esta versión |
|---|---|---|
| Project Report | https://github.com/OperviaStartup/service-compliance-project-report | Documentación y recursos de diseño |
| Landing Page | https://github.com/OperviaStartup/service-compliance-landingpage | Código web y publicación GitHub Pages |
| REST API | https://github.com/OperviaStartup/serviceComplianceAPI | Código de Spring Boot, migraciones y endpoints |

El backend documentado trabaja sobre la rama `main`. La práctica observada de uso de `main` y Conventional Commits no permite afirmar, por sí sola, que GitFlow esté implementado completamente. La política propuesta contempla `main` para versiones estables, `develop` para integración, `feature/<tema>` para cambios aislados, `release/<versión>` para preparar versiones y `hotfix/<tema>` para correcciones urgentes.

Los mensajes de commit siguen la convención `tipo: descripción`, con tipos tales como `feat`, `fix`, `docs`, `test` y `chore`. Semantic Versioning se reserva para versiones identificables de los productos: `MAJOR.MINOR.PATCH`, sin confundir `0.0.1-SNAPSHOT` del build de Gradle con una release publicada de la API.

<img src="resources/13-chapter-04/02-backend-commits.png" alt="Historial de commits del backend" />

*Figura 4.2. Commits del repositorio de REST API, como evidencia de cambios registrados en GitHub.*

<img src="resources/13-chapter-04/03-report-commits.png" alt="Historial de commits de documentación" />

*Figura 4.3. Commits del Project Report; su participación se interpreta separadamente de la autoría del backend.*

<a id="413-source-code-style-guide--conventions"></a>
### 4.1.3. Source Code Style Guide & Conventions

Las convenciones se adaptan a las tecnologías realmente utilizadas y mantienen nombres técnicos en inglés para recursos, archivos y código fuente. En Java, se utilizan clases y enums en `PascalCase`, métodos y variables en `camelCase`, constantes en `UPPER_SNAKE_CASE` y nombres de paquetes en minúsculas. Los endpoints REST identifican recursos del negocio mediante sustantivos, y los códigos HTTP distinguen creación, consulta, rechazo por permisos y solicitudes inválidas.

El backend separa paquetes `authentication`, `obligations`, `executions` y `shared`. En los módulos observados se distinguen `application`, `domain` y `interface.rest`, con infraestructura de persistencia/seguridad según corresponda. Esta separación es una organización de código inspirada en DDD; no implica que los paquetes actuales implementen por completo los Bounded Contexts estratégicos definidos para el producto futuro.

<img src="resources/13-chapter-04/04-ddd-package-structure.png" alt="Paquetes de código de Service Compliance API" />

*Figura 4.4. Paquetes de módulos existentes en la API durante Sprint 1.*

Para la Landing Page se utilizan nombres semánticos de elementos HTML, estilos agrupados por función y JavaScript para interacciones del sitio. Los idiomas se representan mediante identificadores de mensaje en lugar de duplicar toda la estructura HTML.

La validación de entradas, el control de permisos en servidor y la protección de credenciales son responsabilidades de la API. La ocultación de un botón por rol nunca reemplaza la autorización del endpoint. Las pruebas de comportamiento deberían relacionarse con Acceptance Criteria y, cuando aplique BDD, emplear Gherkin con pasos verificables.

<a id="414-software-deployment-configuration"></a>
### 4.1.4. Software Deployment Configuration

El backend utiliza un servicio de Render configurado para ejecutar la aplicación Spring Boot y conectarla con PostgreSQL mediante variables de entorno. El flujo de despliegue documentado emplea Docker y Gradle para construir y ejecutar el artefacto Java. Flyway gestiona las migraciones del esquema y `ddl-auto=validate` contrasta el mapeo con las tablas existentes, evitando presentar Hibernate como mecanismo principal de creación del esquema en producción.

| Componente | Destino / mecanismo | Estado actual |
|---|---|---|
| REST API | Render, servicio Docker | Desplegado por el equipo |
| Database | PostgreSQL en Render | Desplegada y conectada a la API, según el equipo |
| Landing Page | GitHub Pages por GitHub Actions | Publicada |

Las variables `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USERNAME`, `DB_PASSWORD`, `JWT_SECRET` y otras credenciales o parámetros sensibles se inyectan mediante la configuración del servicio, sin incluir valores secretos en el repositorio ni en el informe. Las capturas de la configuración deben revisarse antes de publicar el PDF para asegurar que no revelen contraseñas o tokens.

<img src="resources/13-chapter-04/05-render-blueprint.png" alt="Configuración de despliegue de servicio en Render" />

*Figura 4.5. Servicio backend registrado en Render.*

<img src="resources/13-chapter-04/06-render-environment-variables.png" alt="Variables de entorno del backend en Render" />

*Figura 4.6. Sección de variables de entorno utilizada para la conexión y configuración del despliegue, con valores sensibles ocultos.*

URLs de referencia documentadas por el equipo:

- API health: https://service-compliance-api.onrender.com/health
- Swagger UI: https://service-compliance-api.onrender.com/swagger-ui.html
- OpenAPI: https://service-compliance-api.onrender.com/api-docs
- Landing Page: https://operviastartup.github.io/service-compliance-landingpage/

Estas direcciones identifican los despliegues actuales del proyecto.

Deployment Diagram (C4). Para la documentación del despliegue real, el modelo debe representar: navegador del visitante, GitHub Pages; cliente de API/Swagger, servicio Java en Render, PostgreSQL. Las aplicaciones Android/Flutter no se mostrarán como contenedores desplegados: podrán aparecer únicamente identificadas como clientes futuros, diferenciados gráficamente. Este diagrama debe ser coherente con Spring Boot, no con un stack anterior de ASP.NET Core o MySQL.


<a id="42-landing-page-mobile-application-implementation"></a>
## 4.2. Landing Page & Mobile Application Implementation

El Sprint 1 estuvo orientado a disponer de un backend demostrable y un Landing Page publicado. El backend permite exponer y documentar servicios REST para el flujo inicial entre supervisor y operario; la publicación web habilita la presentación pública de la propuesta. La incorporación del administrador organizacional y las aplicaciones móviles completas corresponden a trabajo posterior al incremento verificado. El Landing Page publicado incluye acceso al prototipo mediante Figma, sin checkout ni captación de datos comerciales.

<a id="421-sprint-1"></a>
### 4.2.1. Sprint 1: Backend inicial y publicación del Landing Page

<a id="4211-sprint-planning-1"></a>
#### 4.2.1.1. Sprint Planning 1

El objetivo del Sprint fue exponer, mediante una API documentada y persistente, una primera secuencia técnica de operación del servicio: autenticar, consultar obligaciones, registrar ejecuciones y asociar evidencias. En paralelo se publicó el Landing Page de Opervia.

| Elemento de Sprint Planning | Registro de Sprint 1 |
|---|---|
| Sprint | 1 |
| Sprint anterior / retrospectiva | No aplica: primer Sprint de implementación descrito |
| Sprint Goal | Disponer de API REST accesible, documentada y persistente para un flujo inicial supervisor a operario y publicar un Landing Page informativo |
| Capacidad planificada | 26 Story Points en la tabla original; no equivale a velocidad efectivamente alcanzada |
| Medida de logro | Endpoints invocables, despliegue documentado, datos persistentes y Landing Page accesible; los resultados deben respaldarse con pruebas |

El Sprint Planning relaciona los compromisos US-17 (5 SP), US-02 (5 SP), US-04 (3 SP), US-05 (5 SP), US-06 (3 SP) y TS-01 (5 SP), con un total de 26 Story Points.

| Historia | Compromiso descrito | Evidencia de capacidad técnica |
|---|---|---|
| US-17 | Autenticarse y acceder según rol | Endpoints de autenticación, seguridad y autorización documentados |
| US-02 | Definir obligación | API para crear obligaciones |
| US-04 | Consultar obligaciones asignadas | Endpoint de consulta |
| US-05 | Registrar Execution | Endpoint de registro de ejecución |
| US-06 | Registrar evidencia | Endpoint de evidencia |
| TS-01 | REST API documentada | Swagger/OpenAPI documentado |
| US-18/US-19 | Presentación web y exploración del prototipo | Landing Page publicada con enlace a Figma |

<a id="4212-aspect-leaders-and-collaborators"></a>
#### 4.2.1.2. Aspect Leaders and Collaborators

La participación se presenta respetando los aportes declarados por el equipo. Jean Pool Alexander Arias Tasayco desarrolló tanto el backend como la versión inicial del Landing Page. Los seis integrantes participaron en Figma y documentación. La validación fue coordinada y realizada por Ángel Thyago Flores Eusebio y Carlos Franco Blancas Chávez, según la confirmación del equipo. Esta distribución no se debe reinterpretar como si cada miembro hubiera escrito código de la API o del Landing Page.

| Aspecto | Responsabilidad documentada | Evidencia adecuada |
|---|---|---|
| API REST, persistencia y despliegue | Jean Pool Alexander Arias Tasayco | Código, commits, configuración, screenshots y ensayos |
| Landing Page inicial y publicación | Jean Pool Alexander Arias Tasayco | Código web, commits y GitHub Pages |
| Diseño UX/UI | Participación de los seis integrantes | Version history de Figma y frames atribuidos |
| Project Report | Participación de los seis integrantes | Commits/PRs y Registro de Versiones |
| Sesiones de validación | Ángel Thyago Flores Eusebio y Carlos Franco Blancas Chávez | Grabaciones, participantes, actas y fichas heurísticas |
| Aplicaciones móviles | Ningún integrante ha implementado aún una app ejecutable | No se atribuyen commits ni evidencias inexistentes |

<img src="resources/13-chapter-04/07-sprint-responsibilities.png" alt="Tablero de tareas de Sprint 1" />

*Figura 4.7. Tablero de trabajo del Sprint. La asignación mostrada debe interpretarse junto con la autoría real confirmada de los entregables.*

<a id="4213-sprint-backlog-1"></a>
#### 4.2.1.3. Sprint Backlog 1

La siguiente matriz organiza las Engineering Tasks identificadas en el Sprint 1. El registro documental disponible no permite reconstruir estimaciones históricas en horas; por tanto, no se presentan cifras creadas a posteriori como si hubieran sido acordadas en Sprint Planning.

| Task ID | Relación | Engineering Task identificada | Responsable del producto implementado | Horas | Estado sustentado |
|---|---|---|---|---|---|
| S1-T01 | TS-01 | Configurar Spring Boot, Gradle y estructura modular | Jean | No registrada | Código presente |
| S1-T02 | US-17 | Implementar registro/login y JWT | Jean | No registrada | Código/endpoints presentes |
| S1-T03 | US-17 | Aplicar permisos SUPERVISOR/OPERATOR | Jean | No registrada | Código y rechazo por rol documentados |
| S1-T04 | TS-01 | Configurar PostgreSQL y migración Flyway | Jean | No registrada | Migración/despliegue evidenciados |
| S1-T05 | US-02/US-04 | Crear y consultar obligaciones | Jean | No registrada | Endpoints documentados |
| S1-T06 | US-05 | Registrar ejecuciones | Jean | No registrada | Endpoint documentado |
| S1-T07 | US-06 | Registrar y consultar evidencia | Jean | No registrada | Endpoints documentados |
| S1-T08 | TS-01 | Aplicar validaciones y respuestas de error | Jean | No registrada | Contrato/error evidenciado parcialmente |
| S1-T09 | TS-01 | Publicar Swagger/OpenAPI | Jean | No registrada | Captura de Swagger disponible |
| S1-T10 | US/TS | Diseñar/ejecutar pruebas unitarias, integración y flujo | Jean; validar participantes | No registrada | Evidencia de ejecución insuficiente para certificar suite completa |
| S1-T11 | UX | Diseñar pantallas core | Equipo de Figma | No registrada | Mockups de acceso, operario y supervisor disponibles; app no implementada |
| S1-T12 | SP-01 | Investigación de aprendizaje autónomo | No confirmada | No registrada | No ejecutada según el equipo; no computar como Done |
| S1-T13 | US-18/US-19 | Implementar Landing Page y acceso al prototipo | Jean | No registrada | Sitio publicado con enlace de prototipo |

La descomposición se limita a tareas identificadas en el incremento. Sin las estimaciones originales ni capturas de la evolución del tablero no es posible comprobar su duración o transición entre estados. Las tareas móviles corresponden a diseño y no se describen como entrega de APK.

<a id="4214-development-evidence-for-sprint-review"></a>
#### 4.2.1.4. Development Evidence for Sprint Review

La evidencia de desarrollo muestra configuración y código relacionados con las capacidades declaradas. El backend sigue una separación modular: seguridad/autenticación, obligaciones y ejecuciones, con piezas compartidas de infraestructura y contratos. Este avance constituye una implementación inicial del dominio; no significa que el código actual modele todos los BC de Strategic DDD.

| Evidencia | Relación con Sprint | Lectura correcta |
|---|---|---|
| E1: Paquetes modularizados | TS-01 | Organización del código Java/DDD |
| E2: Autenticación | US-17 | Implementación de seguridad y acceso |
| E3: Restricciones por rol | US-17 | Autorización de acciones según role |
| E4: Obligaciones | US-02 / US-04 | Registrar/consultar obligaciones de Sprint 1 |
| E5: Ejecuciones y evidencia | US-05 / US-06 | Persistencia asociada a ejecución |
| E6: Flyway y PostgreSQL | TS-01 | Esquema persistente y migraciones |
| E7: Docker y Render | TS-01 | Configuración y despliegue backend |

<img src="resources/13-chapter-04/08-ddd-source-tree.png" alt="Estructura de módulos Java" />

*Figura 4.8. Organización modular observada en el código fuente.*

<img src="resources/13-chapter-04/09-authentication-implementation.png" alt="Captura de autenticación del backend" />

*Figura 4.9. Evidencia técnica de autenticación.*

<img src="resources/13-chapter-04/10-role-authorization.png" alt="Captura de autorización por roles" />

*Figura 4.10. Evidencia de permisos y restricciones por rol.*

<img src="resources/13-chapter-04/11-obligation-implementation.png" alt="Captura de módulo de obligaciones" />

*Figura 4.11. Endpoints o código del módulo de obligaciones.*

<img src="resources/13-chapter-04/12-execution-evidence-implementation.png" alt="Captura de módulo de ejecución y evidencia" />

*Figura 4.12. Endpoints o código de ejecución y evidencia.*

<img src="resources/13-chapter-04/13-postgresql-flyway.png" alt="Captura de PostgreSQL y Flyway" />

*Figura 4.13. Configuración de persistencia en PostgreSQL y Flyway.*

Los commits enlazados a continuación ofrecen referencias verificables a los cambios del repositorio.

| Repositorio | Referencia comprobable | Alcance de la evidencia |
|---|---|---|
| `serviceComplianceAPI` | [Commit `7b3fad8`](https://github.com/OperviaStartup/serviceComplianceAPI/commit/7b3fad80fe1fa2991409dc53ec6b559a6d1432cb) | Cambio registrado en el historial de GitHub. |
| `service-compliance-landingpage` | [Commit `58bd0a0`](https://github.com/OperviaStartup/service-compliance-landingpage/commit/58bd0a02a1ba7a4e7bd69a80b6bd51b43ee77877) | Cambio registrado en el historial de GitHub. |

<a id="4215-testing-suite-evidence-for-sprint-review"></a>
#### 4.2.1.5. Testing Suite Evidence for Sprint Review

La verificación funcional documentada para el backend se centra en autenticación, permisos y relación obligación a ejecución a evidencia. La siguiente matriz resume los escenarios funcionales del incremento.

| Tipo de prueba | Historia | Escenario verificable | Resultado esperado |
|---|---|---|---|
| Integración / API | US-17 | Registro de usuario permitido por backend actual | `201 Created` si request es válida |
| Integración / API | US-17 | Credenciales válidas | `200 OK` y mecanismo de sesión/token |
| Autorización | US-17 | Operador intenta crear obligación | `403 Forbidden` |
| Integración / API | US-02 | Supervisor registra obligación válida | `201 Created` |
| Integración / API | US-04 | Usuario autorizado consulta obligaciones | `200 OK` |
| Integración / API | US-05 | Operario registra ejecución vinculada | `201 Created` |
| Integración / API | US-06 | Operario registra evidencia de ejecución | `201 Created` |
| Validación | US/TS | Request incompleto o inválido | `400 Bad Request` |
| Autenticación | US-17 | Token inválido/ausente | `401 Unauthorized` |

<a id="4216-execution-evidence-for-sprint-review"></a>
#### 4.2.1.6. Execution Evidence for Sprint Review

El flujo técnico propuesto para el Sprint puede recorrerse mediante Swagger: un supervisor autenticado registra una obligación; un operario autorizado consulta el trabajo, registra una ejecución y asocia evidencia; la API rechaza acciones reservadas al supervisor cuando las solicita un operador. El resultado demuestra una secuencia de operaciones REST, no una navegación real en Android/iOS.

<img src="resources/13-chapter-04/25-e2e-user-flow.png" alt="Diagrama del flujo de operaciones REST entre supervisor, sistema y operario" />

*Figura 4.14. Diagrama del flujo E2E documentado para backend. Es una representación de interacciones, no un screenshot de la ejecución de pruebas.*

<a id="4217-services-documentation-evidence-for-sprint-review"></a>
#### 4.2.1.7. Services Documentation Evidence for Sprint Review

La API publica un contrato OpenAPI consultable mediante Swagger UI. La relación de endpoints documentados para el incremento incluye autenticación, obligaciones, ejecución, evidencia y health check.

| Método | Ruta | Rol/restricción documentada | Resultado esperado principal |
|---|---|---|---|
| `POST` | `/api/v1/auth/register` | Público en backend actual | Crear cuenta (`201`) |
| `POST` | `/api/v1/auth/login` | Público | Autenticación (`200`) |
| `GET` | `/api/v1/auth/me` | Usuario autenticado | Datos del principal (`200`) |
| `POST` | `/api/v1/obligations` | Supervisor | Crear obligación (`201`) |
| `GET` | `/api/v1/obligations` | Autenticado; verificar filtro de alcance | Listar obligaciones (`200`) |
| `POST` | `/api/v1/executions` | Operario | Registrar ejecución (`201`) |
| `GET` | `/api/v1/executions/{id}` | Autenticado y autorizado | Consultar ejecución (`200`) |
| `POST` | `/api/v1/executions/{id}/evidence` | Operario | Registrar evidencia (`201`) |
| `GET` | `/api/v1/executions/{id}/evidence` | Autenticado y autorizado | Consultar evidencia (`200`) |
| `GET` | `/health` | Público | Comprobación de disponibilidad |

Consideración funcional. El endpoint público `/auth/register` documenta lo que existe en la API actual. No coincide todavía con la decisión comercial más reciente de que el administrador de la empresa prestadora cree o invite usuarios dentro de cupos contratados. El servicio tendrá que evolucionar; esta diferencia se registra como brecha real y no se oculta atribuyendo comportamiento de administrador al endpoint presente.

Los códigos `400`, `401`, `403`, `404` y `500` forman parte de la convención de respuesta del servicio.

<img src="resources/13-chapter-04/26-swagger-ui.png" alt="Interfaz Swagger UI del backend" />

*Figura 4.15. Swagger UI y grupos de recursos publicados para la REST API.*

Referencias: [Swagger UI](https://service-compliance-api.onrender.com/swagger-ui.html) · [OpenAPI Specification](https://service-compliance-api.onrender.com/api-docs) · [Código fuente](https://github.com/OperviaStartup/serviceComplianceAPI).


<a id="4218-software-deployment-evidence-for-sprint-review"></a>
#### 4.2.1.8. Software Deployment Evidence for Sprint Review

El equipo publicó la API y PostgreSQL en Render y el Landing Page en GitHub Pages. La API ejecuta las migraciones de Flyway antes de atender solicitudes. La publicación del Landing Page se realiza desde el repositorio de código mediante workflow GitHub Actions, lo que separa la autoría del HTML del mecanismo de despliegue.

<img src="resources/13-chapter-04/14-docker-render-configuration.png" alt="Configuración Docker y Render del backend" />

*Figura 4.16. Configuración del backend para ejecución en Render.*

<img src="resources/13-chapter-04/41-github-pages-workflow.png" alt="Workflow de publicación de Landing Page" />

*Figura 4.17. Workflow GitHub Actions para la publicación del sitio informativo.*

La versión vigente del sitio se encuentra publicada en [Service Compliance | Opervia](https://operviastartup.github.io/service-compliance-landingpage/). El Landing Page presenta la propuesta de valor, la cadena de trazabilidad y las experiencias de operario y supervisión. La publicación incluye un selector de idioma, con inglés como contenido predeterminado y español como alternativa.

<p align="center"><img src="resources/12-chapter-03/landing-page/landing-hero.png" alt="Captura de la sección principal de la landing page publicada de Service Compliance" width="800"></p>

*Figura 4.18. Sección principal de la landing page publicada de Service Compliance.*

<p align="center"><img src="resources/12-chapter-03/landing-page/landing-product-flow.png" alt="Captura de la sección de producto de la landing page publicada de Service Compliance" width="800"></p>

*Figura 4.19. Sección de producto de la landing page publicada, con ejecución, evidencia e historial de caso.*

La Landing Page comunica la propuesta de valor, el flujo de trazabilidad y el acceso al prototipo de producto.

<a id="4219-team-collaboration-insights-during-sprint"></a>
#### 4.2.1.9. Team Collaboration Insights during Sprint

La colaboración durante el Sprint tuvo dos tipos distintos de aportes: implementación directa de productos y trabajo de diseño/documentación/validación. El backend y la versión inicial de la Landing Page fueron desarrollados por Jean; todos los integrantes trabajaron en Figma y Project Report, mientras que Ángel y Carlos realizaron las validaciones, según lo informado por el equipo. Esta distribución debe reflejarse con precisión en los gráficos de GitHub y en los historiales de Figma, sin presentar como commits de backend contribuciones que se hicieron únicamente en documentación.

<img src="resources/13-chapter-04/30-sprint-collaboration.png" alt="Gráfico GitHub de contribuciones" />

*Figura 4.20. Vista de analíticos de colaboración disponible. El gráfico debe interpretarse por repositorio y periodo analizado.*

Los commits del Project Report no miden por sí solos la participación en diseño de pantallas, entrevistas o revisión de artefactos. Las contribuciones de Figma y validación necesitan evidencia específica (historial de cambios, responsables del artefacto, archivos y grabaciones), además de la tabla de participación del equipo.

<a id="43-validation-interviews"></a>
## 4.3. Validation Interviews

Las entrevistas de validación complementan las entrevistas de descubrimiento documentadas en el Capítulo II y se orientan a la comprensión de los flujos y la información presentada por el producto.

<a id="431-diseno-de-entrevistas"></a>
### 4.3.1. Diseño de entrevistas

Las sesiones de validación se orientan a comprobar si el usuario comprende el contexto de una obligación, distingue ejecución de cumplimiento y puede seguir los flujos sin interpretar mensajes técnicos o estados ambiguos. La evaluación utiliza el Landing Page y los prototipos disponibles.

| Segmento | User Goal / tarea | Indicador observable | Preguntas posteriores |
|---|---|---|---|
| Operario | Identificar qué actividad debe realizar | Encuentra obligación, zona y horario sin ayuda | ¿Qué harías ahora?, ¿qué información falta? |
| Operario | Registrar ejecución o Exception | Distingue completado, parcial e impedido; comprende evidencias | ¿El sistema confirma registro o cumplimiento? |
| Operario | Atender una Corrective Action | Reconoce que registrar atención no significa cerrar | ¿Quién revisa tu atención? |
| Supervisor | Revisar Execution y Evidence | Localiza criterio, resultados y evidencia relevante | ¿Qué necesitas antes de decidir? |
| Supervisor | Evaluar y verificar | Distingue Exception, Non-compliance y cierre correctivo | ¿Qué hecho debe conservarse en el historial? |
| Supervisor | Consultar caso y reporte | Reconstruye secuencia, filtros y estado de evaluación | ¿Qué responderías ante una observación del cliente? |
| Visitante comprador | Comprender Landing Page | Identifica propósito, destinatarios y acceso al prototipo | ¿Qué ofrece el producto y cómo abrirías el prototipo desde esta página? |

La evaluación debe observar un happy path y al menos una alternativa significativa por meta, registrar cuándo el participante necesita ayuda y recoger hallazgos negativos además de comentarios favorables. No se atribuye comprensión exitosa únicamente porque el participante exprese interés en la idea.

<a id="432-registro-de-entrevistas"></a>
### 4.3.2. Registro de entrevistas

El registro de validación organiza las tareas de los participantes, las observaciones de uso y los hallazgos vinculados a cada recorrido evaluado.

<a id="433-evaluaciones-segun-heuristicas"></a>
### 4.3.3. Evaluaciones según heurísticas

La evaluación toma como objeto pantallas y recorridos específicos del prototipo. La tabla registra los problemas observables en los mockups y relaciona cada hallazgo con su evidencia y recomendación.

| Heurística / principio | Hallazgo sobre artefacto visual disponible | Impacto potencial | Recomendación de diseño |
|---|---|---|---|
| Consistencia y estándares | Los mockups recientes del operario muestran navegación propia, mientras la supervisión conserva un menú anterior de cinco destinos | Incoherencia entre flujo aprobado y navegación del supervisor | Aplicar `Resumen/Actividades/Casos/Reportes`; conservar `Inicio/Trabajo/Historial/Perfil` en operario |
| Visibilidad del estado | Etiquetas de ejecución y cumplimiento se mezclan en algunas vistas | El usuario puede interpretar «enviado» como «cumplido» | Diferenciar estados operativos, revisión y SyncState |
| Correspondencia con el mundo real | Parte de los wireframes menciona mantenimiento y telemetría | No se ajusta a limpieza tercerizada | Sustituir por obligación, ejecución, evidencia y caso |
| Prevención de errores | La creación de Corrective Action muestra un estado seleccionable | Posibilidad de declarar cierre sin verificación | Estado inicial controlado y cierre exclusivo del supervisor |
| Reconocimiento antes que memoria | El historial US-22 se concentra en correctivas | Operario no puede reconstruir trabajo habitual | Incluir ejecuciones previas y resultados de revisión |
| Integridad de información | Los mockups de reportes de supervisor mantienen totales y barras inconsistentes | Reporte difícil de interpretar | Usar mismo conjunto de datos para KPI, leyenda y gráfico |
| Correspondencia estado a realidad | La confirmación de Exception incluye «Turno protegido», y ciertos previews sugieren validación automática de nitidez o protocolo | Se prometen decisiones no definidas ni implementadas | Confirmar solo registro del impedimento; no asumir evaluación automática |
| Visibilidad del estado | Se dispone de variantes de envío online y registro local offline del operario | Riesgo de confundir «actividad completada» con dato sincronizado y conforme | Diferenciar guardado local, envío confirmado y Compliance Result |
| Diseño inclusivo | Capturas disponibles no demuestran escala de texto ni foco accesible | Dificultades de lectura o interacción | Evaluar contraste, lector de pantalla y tamaño dinámico | No evaluado en dispositivo |

Estas observaciones proceden de una auditoría de diseño, no de puntuaciones atribuidas a personas entrevistadas. La evaluación heurística formal requiere registrar tarea, heurística, gravedad, recomendación, evaluador y evidencia; las puntuaciones solo deben consignarse cuando exista una revisión aplicada en el formato oficial.


El balance actual es concreto: Opervia cuenta con un backend REST persistente y publicado, un Landing Page operativo y artefactos UI/UX que orientan los productos móviles. Las aplicaciones móviles, la evidencia de pruebas y las validaciones de usuarios continúan como trabajo posterior.
