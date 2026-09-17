<style>
@page {
  size: A4;
  margin: 2.54cm;
}

html,
body {
  max-width: 100%;
  overflow-x: hidden;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 11pt;
  line-height: 1.5;
  text-align: left;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  break-after: avoid-page;
  page-break-after: avoid;
  overflow-wrap: anywhere;
}

p,
li {
  orphans: 3;
  widows: 3;
  overflow-wrap: anywhere;
  word-break: normal;
}

ul,
ol {
  max-width: 100%;
  padding-left: 1.5em;
}

a {
  overflow-wrap: anywhere;
  word-break: normal;
}

img,
svg {
  max-width: 100%;
  height: auto;
}

table {
  width: 100%;
  max-width: 100%;
  table-layout: fixed;
  border-collapse: collapse;
}

th,
td {
  overflow-wrap: anywhere;
  word-break: normal;
}

pre,
code {
  white-space: pre-wrap;
  overflow-wrap: anywhere;
  word-break: break-word;
  max-width: 100%;
}
</style>

<div style="page-break-before: always;"></div>

Contenido

La tabla de contenido utiliza tres niveles de esquema, tal como solicita el enunciado oficial.
Las subsecciones de mayor profundidad se mantienen en la estructura del documento, pero no se agregan al índice para evitar un contenido excesivamente ancho o fragmentado al exportar a PDF.

[Capítulo I: Presentación](#capitulo-i-presentacion)

[1.1. Startup Profile](#11-startup-profile)

[1.1.1. Descripción de la Startup](#111-descripcion-de-la-startup)

[1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)

[1.2. Solution Profile](#12-solution-profile)

[1.2.1. Antecedentes y problemática](#121-antecedentes-y-problematica)

[1.2.2. Lean UX Process](#122-lean-ux-process)

[1.3. Segmentos objetivo](#13-segmentos-objetivo)

[Capítulo II: Requirements Development and Software Solution Design](#capitulo-ii-requirements-development-and-software-solution-design)

[2.1. Competidores](#21-competidores)

[2.1.1. Análisis competitivo](#211-analisis-competitivo)

[2.1.2. Estrategias y tácticas frente a competidores](#212-estrategias-y-tacticas-frente-a-competidores)

[2.2. Entrevistas](#22-entrevistas)

[2.2.1. Diseño de entrevistas](#221-diseno-de-entrevistas)

[2.2.2. Registro de entrevistas](#222-registro-de-entrevistas)

[2.2.3. Análisis de entrevistas](#223-analisis-de-entrevistas)

[2.3. Needfinding](#23-needfinding)

[2.3.1. User Personas](#231-user-personas)

[2.3.2. User Task Matrix](#232-user-task-matrix)

[2.3.3. User Journey Mapping](#233-user-journey-mapping)

[2.3.4. Empathy Mapping](#234-empathy-mapping)

[2.3.5. Big Picture EventStorming](#235-big-picture-eventstorming)

[2.3.6. Ubiquitous Language](#236-ubiquitous-language)

[2.4. Requirements specification](#24-requirements-specification)

[2.4.1. User Stories](#241-user-stories)

[2.4.2. Impact Mapping](#242-impact-mapping)

[2.4.3. Product Backlog](#243-product-backlog)

[2.5. Strategic-Level Domain-Driven Design](#25-strategic-level-domain-driven-design)

[2.5.1. EventStorming](#251-eventstorming)

[2.5.2. Context Mapping](#252-context-mapping)

[2.5.3. Software Architecture](#253-software-architecture)

[2.6. Tactical-Level Domain-Driven Design](#26-tactical-level-domain-driven-design)

[2.6.1. Bounded Context: Authentication](#261-bounded-context-authentication)

[2.6.2. Bounded Context: Contract & Obligation Management](#262-bounded-context-contract--obligation-management)

[2.6.3. Bounded Context: Field Execution & Evidence](#263-bounded-context-field-execution--evidence)

[2.6.4. Bounded Context: Incident & Corrective Action](#264-bounded-context-incident--corrective-action)

[2.6.5. Bounded Context: Compliance Reporting](#265-bounded-context-compliance-reporting)

Capítulo III: Solution UI/UX Design

3.1. Product design

3.1.1. Style Guidelines

3.1.2. Information Architecture

3.1.3. Landing Page UI Design

3.1.4. Mobile Applications UX/UI Design

Capítulo IV: Product Implementation & Validation

4. Product Implementation & Validation

4.1. Software Configuration Management

4.1.1. Software Development Environment Configuration

4.1.2. Source Code Management

4.1.3. Source Code Style Guide & Conventions

4.1.4. Software Deployment Configuration

4.2. Landing Page & Mobile Application Implementation

4.2.1. Sprint n

4.3. Validation Interviews

4.3.1. Diseño de Entrevistas

4.3.2. Registro de Entrevistas

4.3.3. Evaluaciones según heurísticas

<div style="page-break-before: always;"></div>