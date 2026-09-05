---
type: research-note
description: "Síntesis interna provisional para decisiones de producto, verificación y cartera."
status: provisional
sources: [ external-sources/squad-product-research-report-2026-09-05.md, external-sources/ultimate-harness-capability-verification.md, external-sources/notion-operating-authority-snapshot-2026-09-05.md, external-sources/jfrog-prompt-to-release-traceability-2026-09-05.md, external-sources/release-evidence-counterexample-audit-2026-09-05.md ]
created: 2026-09-05
author: codex-mcp-client
tags: [ research, provisional, internal, strategy, telar, ultimate-harness, prism ]
title: Squad, Telar y Ultimate Harness — evidencia y próximos experimentos — 2026-09-05
authored: 2026-09-05
confidentiality: internal
---

**Uso interno · investigación provisional · corte: 5 de septiembre de 2026.** Las recomendaciones son propuestas para discusión. Este documento no ratifica estrategia, no autoriza implementación y no asigna responsables ni fechas.

## Qué decisión conviene preparar

**Un expediente neutral de release no constituye por sí solo una oportunidad exclusiva para Telar.** JFrog AppTrust y Kosli documentan directamente cadenas de evidencia ligadas al release. La hipótesis propuesta para Telar-Demo debe ser más específica: resolver un caso que siga descubierto después de configurar el proceso o producto del comprador, con menor esfuerzo de integración o revisión demostrado. No se estableció disposición a pagar ni superioridad de Telar. [Auditoría final de contraejemplos](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

El expediente propuesto reúne evidencia vigente, señala faltantes y conserva el contexto de decisión humana. Su baseline debe incluir exportaciones, CI y documentos, además de AppTrust, Kosli y el stack realmente instalado. Si una regla o una attestation personalizada resuelve el problema, se propone favorecer esa integración antes que otro registro. Es una recomendación de investigación, no una decisión de arquitectura ni de construcción. [Informe inicial](../external-sources/squad-product-research-report-2026-09-05.md) y [reconciliación competitiva](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

Squad sirve como referencia de experiencia: misiones, cola de atención, contexto y permisos se presentan de forma integrada. La recomendación es estudiar esos patrones y medir su utilidad; tener memoria, aprobación y varios runtimes no basta como diferenciación genérica. [Informe revisado, secciones 2–6](../external-sources/squad-product-research-report-2026-09-05.md).

## Autoridad y arquitectura que siguen vigentes

La [verificación de Notion](../external-sources/notion-operating-authority-snapshot-2026-09-05.md) registra el Agentic Delivery Operating Model de 2 de septiembre como ACTIVE, con estos límites aprobados:

| Componente | Límite aprobado | Distinción necesaria |
| --- | --- | --- |
| Telar | Intención, políticas, identidades estables, routing, gates humanos y ledger normalizado | La disponibilidad figura LOCAL-ONLY; planning only no autoriza implementación de producto |
| Ultimate Harness | Único RunControl | Tener una responsabilidad asignada no prueba todas sus garantías |
| SpecSafe | Verificación dentro del repositorio | No se amplía a un plano de control compartido |
| Hermes | Observatorio de solo lectura | Observación no concede autoridad de ejecución |

La recomendación advisory del demo es un experimento acotado dentro de esa arquitectura. No sustituye la intención, las políticas ni los gates humanos de Telar. La investigación encontró implementación del demo y notas históricas de entregas, pero no estableció su readiness completo mediante una prueba actual. [Informe revisado, sección 9](../external-sources/squad-product-research-report-2026-09-05.md).

La [estrategia de cartera](../articles/portfolio-and-platform-strategy.md), el [modelo de negocio](../articles/business-model.md) y el [sistema de crecimiento](../articles/founder-led-growth-operating-system.md) conservan sus decisiones y procedencia histórica. Las nuevas propuestas requieren reconciliación con Operating Partner Shift y el modelo operativo vigente en Notion. La [elección de harness OSS](../articles/oss-golden-path-decision.md) sigue OPEN; esta investigación no elige ni archiva repositorios.

## Matriz de evidencia

| Área | Estado | Hallazgo y alcance |
| --- | --- | --- |
| Squad | Documentado y observado en demo | Publica US$99 al mes, más ruta de AI y extras. El demo contiene datos sembrados y navegación real; no prueba ejecución de nuevas misiones ni resultados comerciales |
| Squad: permisos | Documentado | Describe restricciones por agente y cuenta; una VM por workspace no demuestra aislamiento de sistema operativo por agente |
| Paperclip | Inspeccionado en código y documentado | v2026.817.0 contiene HMAC, snapshots, staleness e idempotencia por efecto interno. Las actualizaciones de 31 de agosto y 2 de septiembre se revisaron documentalmente; no se probó firma humana ni transacción universal sobre servicios externos |
| Ultimate Harness | Probado en alcance focalizado | 82/82 pruebas pasaron; un probe temporal aceptó una etiqueta de aprobador no autenticada y un diff cambiado después de verificar, aunque había un review gate declarado |
| JFrog AppTrust | Documentado; GA anunciado el 2 de septiembre | Evidencia firmada ligada al release; sesiones de agentes y session BOM previstos para después en 2026. [Fuente](../external-sources/jfrog-prompt-to-release-traceability-2026-09-05.md) |
| Kosli | Documentado; baseline del 20 de marzo de 2025 | Release Flow con fingerprints y evidencia SDLC; go/no-go humano en CI. No ejecutado. [Auditoría](../external-sources/release-evidence-counterexample-audit-2026-09-05.md) |
| APIs de integración | Documentado; integración no probada | LangSmith, AgentCore y attachments de ServiceNow ofrecen rutas plausibles; no se ejecutaron APIs autenticadas |
| Spark / Prism | Inspeccionado y propuesto | La lectura de Spark v2.1.0 no permite tratar un await genérico como barrera global de LoD y paging; no se ejecutó benchmark |
| Demanda y precio de Telar | Desconocido | No se estableció un comprador dispuesto a pagar por el expediente propuesto |

Fuentes: [informe revisado, secciones 2–12](../external-sources/squad-product-research-report-2026-09-05.md) y [anexo reproducible de UH](../external-sources/ultimate-harness-capability-verification.md). Documentado no significa probado, y un resultado focalizado no certifica el producto completo.

## Contraejemplos directos: JFrog y Kosli

El anuncio oficial de JFrog del 2 de septiembre de 2026 presenta Prompt to Release Traceability como generalmente disponible. Describe recolección de commits, PRs y aprobadores de GitHub, y transiciones de Jira; firma y adjunta esa evidencia a la versión de aplicación antes de los gates de promoción. La evidencia de sesiones de agentes y el session bill of materials están previstos para más adelante en 2026: no se cuentan como entregados. Es evidencia documental del proveedor, sin prueba propia de ejecución. [Extractos oficiales fechados](../external-sources/jfrog-prompt-to-release-traceability-2026-09-05.md) y [auditoría de alcance](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

Kosli documentó el 20 de marzo de 2025 un release Flow que compara fingerprints de artefactos entrantes y salientes, reúne evidencia del ciclo de desarrollo y deja el go/no-go humano en CI. Es un baseline previo, no un lanzamiento de las últimas seis semanas. Su endpoint de reporte de aprobación asocia SHA256, entorno y commits; el aprobador opcional es una cadena y no prueba por sí solo una firma criptográfica humana. No se ejecutó el flujo. [Auditoría y fuentes primarias de Kosli](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

La documentación inspeccionada de AppTrust también contempla evidencia externa y reglas de aprobación de ServiceNow; SLSA VSA aporta un formato existente de resumen de verificación. Antes de inventar un registro o formato nuevo se propone evaluar una attestation o integración compatible. La auditoría no estableció menor costo total de Telar ni ausencia universal de campos en los incumbentes. [Auditoría final](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

Kosli identifica a Firi como cliente y a DNB en un POC. Es señal nominal de demanda en la categoría adyacente de evidencia y compliance SDLC, no prueba de compra del caso específico de Telar. Los ahorros que publica JFrog no se adoptan como ROI independiente. [Alcance de la evidencia comercial](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

## Ultimate Harness: qué se probó y qué falta

La revisión se realizó en HEAD `d4e7753bb4dc115fb4c526499e9bf49ef3cdb70b`. Seis archivos y 82 pruebas focalizadas pasaron; typecheck pasó. La suite general fresca terminó con 877 pruebas aprobadas y dos fallidas por plantillas de especificación ausentes. No corresponde describir el repositorio como completamente verde. [Verificación reproducible](../external-sources/ultimate-harness-capability-verification.md).

El probe separó identidad, candidato y revisión: una cadena no vacía fue aceptada como aprobador; la verificación correspondía a la misión y tenía estado passed, pero no quedaba vinculada al digest del candidato; cambiar el diff no invalidó la promoción; un review gate declarado no exigió un recibo de revisión. El resultado sólo establece esas propiedades en el recorrido probado. [Precondiciones, resultado y referencias de código](../external-sources/ultimate-harness-capability-verification.md).

La prioridad técnica propuesta es autenticar al aprobador, vincular aprobación y evidencia al candidato exacto, comprobar recibos de revisión, deduplicar peticiones y probar recuperación y cancelación después de reinicio. El anexo diferencia las limitaciones observadas de una inferencia estática sobre escrituras terminales, que todavía necesita inyección de fallos. Ninguna corrección de producto se efectuó en esta investigación. [Alcance y límites](../external-sources/ultimate-harness-capability-verification.md).

## Telar: propuesta de validación comercial

La oferta inicial del demo permanece como release assurance externo y recomendación advisory con escenarios sintéticos. La arquitectura aprobada de Telar tiene un alcance mayor; ambas afirmaciones describen niveles distintos y no deben confundirse. [Informe, sección 9](../external-sources/squad-product-research-report-2026-09-05.md) y [autoridad operativa](../external-sources/notion-operating-authority-snapshot-2026-09-05.md).

Se propone preparar estas fases para discusión, sin fechas ni propietarios inventados:

| Fase propuesta | Evidencia que permitiría decidir |
| --- | --- |
| Baseline de una decisión real de release | Quién reúne la evidencia, cuánto tarda y qué sigue sin resolverse después de configurar el proceso o producto existente, incluidos AppTrust o Kosli cuando apliquen |
| Fixture sintético | Evidencia faltante, caducada o ligada a un candidato que cambió; resultado explícito de evidencia insuficiente |
| Un origen y un destino elegidos por el comprador | Permisos, versiones y metadatos suficientes; integración sólo tras autorización de implementación |
| Comparación en una decisión de release autorizada | Tiempo de preparación y revisión, faltantes relevantes, decisión que cambia y disposición a contratar un piloto |

La propuesta mantiene la aprobación y el deployment en sus sistemas actuales. Elegir un origen y un destino precede a multiplicar conectores; una API de adjuntos no prueba una relación inmutable entre expediente y release. [Fundamento y límites, secciones 7–10](../external-sources/squad-product-research-report-2026-09-05.md).

## Prism Arena: experimento separado con Spark

Se propone un track versionado de splats o escenas híbridas con catálogo fijo, nombres neutrales, licencias y hashes comunes para todos los modelos. Debe preservar el [baseline histórico de Prism SceneSpec](../external-sources/prism-scenespec-snapshot-2026-07-26.md). Componer un asset capturado cambia lo que se evalúa respecto de generar primitivas; no debe alterar silenciosamente el ranking existente. [Informe, sección 11](../external-sources/squad-product-research-report-2026-09-05.md).

El primer fixture propuesto usa un splat residente, sin paging ni LoD, captura serial y reloj explícito. Antes de ampliar el track se medirían repetibilidad, seek hacia delante y atrás, oclusión entre mesh y splat, inicialización en contexto nuevo y separación entre buffers. Streaming, deformación y tolerancias se decidirían a partir de mediciones, no de pausas fijas o umbrales inventados. Estos experimentos están diseñados, no ejecutados. [Informe, secciones 11–12](../external-sources/squad-product-research-report-2026-09-05.md).

## Cartera, secuencia y registros existentes

La lectura actual de Notion registra esta secuencia: cerrar bloqueadores de tres repositorios, resolver la publicación o archivo del planning de Telar por su proceso autorizado, unir recibos de Curia, observación de solo lectura, benchmarks, gates en sombra, aprendizaje gobernado y validación de oferta pagada. Operating Partner Shift registra 90d-cash como plan autorizado que sustituye al de cinco semanas. Esta página describe esa autoridad; no ejecuta archivo ni cambia hitos. [Verificación de autoridad](../external-sources/notion-operating-authority-snapshot-2026-09-05.md).

El inventario completo de pendientes de Linear no está certificado: los totales anteriores de 88, 89, 531 y 546 no están auditados y las listas previas son parciales. Linear Agent informó paginación por offsets sin cursor, cambios de orden y solapamientos; es su explicación del comportamiento de sus herramientas, no una auditoría independiente de la API. No entregó un conjunto completo y estable de claves ni una exportación nueva. Para certificar cobertura se requiere una exportación estable con claves de issues, equipo, estado y proyecto. Esta aclaración no modificó issues. Los horizontes propuestos siguen sin constituir compromisos; Telar aparece activo en cartera, pero no fue recuperado por ese nombre como equipo o proyecto. [Aclaración final de Linear Agent](https://linear.app/agentic-engineering-company/agent/revisar-tareas-pendientes-de-agentic-engineering-d8783840222ca).

Twenty fue reportado como disponible en la evidencia más reciente; la acción propuesta era rotar la clave y resincronizar. Apagarlo estaba condicionado a una exportación verificada. El titular antiguo que lo describía caído no debe presentarse como estado actual. [Informe, sección 13](../external-sources/squad-product-research-report-2026-09-05.md) y [verificación de Notion](../external-sources/notion-operating-authority-snapshot-2026-09-05.md).

## Dónde continuar la decisión

La página [Investigación y coordinación — Squad, Telar, Ultimate Harness y Prism — 2026-09-05](https://app.notion.com/p/3d2135974884805db8dac1eb204668ac) reúne la investigación y coordinación relacionada. La tarea de Notion verificó el 5 de septiembre de 2026 que su contenido completo estaba persistido y la revisión de formato estaba terminada. Este enlace es navegación a investigación, no una decisión aprobada ni evidencia de ejecución probada de competidores.

Los enlaces siguientes son navegación a los registros vigentes, verificados por la tarea de Notion y preservados en la [captura de autoridad](../external-sources/notion-operating-authority-snapshot-2026-09-05.md):

- [Agentic Engineering OS](https://app.notion.com/p/Agentic-Engineering-OS-d86c64792a0f474f8918364c39e98d9d): hub de estrategia y gobierno.
- [Company Wiki](https://app.notion.com/p/Company-Wiki-a6d81aab0ea040e49b88c5d263c71012): conocimiento de compañía.
- [Decision Hub](https://app.notion.com/p/Decision-Hub-ab5b6053cd4744dfa326137a961ca1a7): opciones propuestas, sin registrarlas como decisiones tomadas.
- [Evidence & Claims](https://app.notion.com/p/8c9bfbeb286840c89034a8aea9b82d2d): evidencia, límites y estados de claims.
- [Milestones](https://app.notion.com/p/a005bcd5c8864681a7b4952a88a528e2): reconciliación con resultados existentes, sin bases paralelas ni fechas inventadas.
- [Agentic Delivery Operating Model — 2026-09-02](https://app.notion.com/p/Agentic-Delivery-Operating-Model-2026-09-02-3d013597488480d2a642c1e9098a54cc): límites aprobados y disponibilidad.
- [Telar — Planning Release v3](https://app.notion.com/p/Telar-Planning-Release-v3-3c013597488481dc98f5e426e843c816): planning only.

## Conclusión para el siguiente experimento

Se propone continuar sólo con una necesidad residual concreta y comparar el esfuerzo de integración y revisión contra el stack que el comprador puede usar. Un expediente más completo, neutralidad o un hash no establecen una ventaja por sí solos. Si basta una regla o attestation personalizada, favorecer esa integración. Si el caso requiere gobernar estado externo mutable, definir ese alcance antes de llamarlo candidato exacto. Para UH, autenticar al aprobador y vincular evidencia al candidato mejora corrección, pero no demuestra diferenciación comercial. [Auditoría final de contraejemplos](../external-sources/release-evidence-counterexample-audit-2026-09-05.md).

## Preguntas abiertas y límite de uso

Faltan comprador y pago, integraciones reales, readiness actual completo de Telar-Demo, inventario exhaustivo de Linear, pruebas prácticas de Spark y mediciones propias de permisos, costo y recuperación de Squad. Las dos rondas de crítica en Claude ayudaron a retirar overclaims; no fueron una evaluación ciega ni prueba comercial. Command Code no produjo inferencia de validación. [Método y límites del informe](../external-sources/squad-product-research-report-2026-09-05.md).

Este material es interno. Su publicación en la wiki no aprueba claims externos: rigen el [registro de claims](../articles/claims-registry.md) y la [frontera de publicación](../articles/public-wiki-boundary.md). La oferta pagada, titulares comerciales y autoridad de outreach que siguen abiertos requieren decisión de los fundadores; esta síntesis no los resuelve.
