---
type: source
description: "Informe interno revisado sobre Squad, Telar, Ultimate Harness y Prism Arena."
source_url:
date_fetched: 2026-09-05
preservation: verbatim-local-text
tags: [ source, immutable, layer-ingest, internal, research ]
title: Squad y la próxima decisión de producto — informe fuente
confidentiality: internal
source_origin: Reviewed report-source.md supplied by the coordinating task
---

<!-- markdownlint-disable MD025 MD060 -->

# Squad y la próxima decisión de producto

Investigación interna para Agentic Engineering · 5 de septiembre de 2026

Telar · Ultimate Harness · Prism Arena · Roadmap de cartera

Este informe separa documentación pública, lectura de código, pruebas actuales y propuestas. Los nombres y planes internos no están preparados para distribución externa. La revisión no modificó tareas de Linear ni desplegó productos.

## 1. La decisión principal

**Squad es una referencia seria de experiencia de usuario y distribución. La oportunidad de Telar todavía necesita una prueba comercial más estrecha que “gobernar agentes”.** Aprobaciones, memoria, trazas y múltiples modelos ya aparecen en numerosos productos. El valor defendible debe expresarse como un resultado verificable para un comprador concreto.

La hipótesis que merece probarse primero es preparar un expediente de release que reúna evidencia de varios sistemas, distinga qué sigue vigente, señale lo que falta y conserve el contexto de una decisión humana. Debe entrar en el workflow que el cliente ya utiliza. Esta es una recomendación de investigación, no una capacidad exclusiva confirmada ni una demanda demostrada.

Tres decisiones distintas evitan mezclar productos:

- **Squad:** cuánto trabajo operativo útil puede completar un equipo de agentes y cuánta atención humana exige.
- **Telar:** cuánto cuesta hoy preparar y revisar una decisión de paso a producción, y qué evidencia se pierde entre sistemas.
- **Ultimate Harness:** qué contratos de ejecución, verificación y recuperación se cumplen realmente entre adaptadores.

Para Telar, el rival más difícil puede ser una exportación de LangSmith, un pipeline y una plantilla que el cliente ya entiende. IBM y ServiceNow también poseen registros y workflows instalados. Para Ultimate Harness, los proyectos abiertos que ya implementan decisiones, idempotencia y controles de ejecución son comparadores más útiles que una lista de promesas.

**Qué haría ahora:** demostrar una decisión con evidencia incompleta o caducada; medirla contra el proceso actual; integrar un origen y un destino elegidos por el comprador. Mantener la aprobación y el deployment donde hoy pertenecen. Ampliar el producto sólo después de observar una necesidad repetida.

**Qué evitaría prometer:** gobierno universal, ejecución aislada por agente, aprobación criptográfica humana, recuperación de cualquier efecto externo o disposición a pagar. La investigación no estableció esas propiedades para nuestros productos ni su ausencia general en competidores.

## 2. Qué ofrece Squad y a qué tenemos acceso

El producto confirmado es [Squad](https://squad.so/), antes MissionControlHQ. Publica una tarifa de **US$99 al mes**, más la ruta de modelo que conecta el usuario. Ofrece un Lead con especialistas, contexto compartido, misiones, tickets, documentos y conexiones a servicios. El atractivo es convertir actividades dispersas en un equipo operativo visible desde una sola experiencia.

El [demo público](https://squad.so/demo) permite examinar un negocio de ejemplo, Harbor & Pine. Es evidencia de una interfaz de demostración; no demuestra que se hayan ejecutado tareas nuevas, conectado cuentas reales o obtenido los resultados comerciales mostrados. No se contrató un workspace de pago durante esta investigación.

La explicación de arquitectura publicada vincula el runtime a **OpenClaw**; la página de Convex identifica MissionControl como una aplicación construida con React y Convex. Esto ayuda a entender la composición, pero no equivale a una auditoría del servicio desplegado. [Arquitectura publicada](https://squad.so/resources/why-missioncontrolhq), [referencia de Convex](https://www.convex.dev/claw).

La política de privacidad describe una máquina virtual por workspace o cliente. Un perfil de navegador por agente es otra capa de separación: no demuestra una máquina o filesystem independiente para cada agente. Esta distinción importa al comparar aislamiento. [Privacidad](https://squad.so/privacy).

Existe una [ficha oficial de iOS bajo MissionControlHQ](https://apps.apple.com/sv/app/missioncontrolhq-ai-squad/id6789877389). La coexistencia de esa ficha con textos de “coming soon” en el sitio muestra desalineación documental; no permite concluir que la aplicación esté universalmente disponible o ausente. No se verificó acceso móvil con una cuenta propia.

No se encontró un repositorio público oficial del producto completo. La ausencia en la búsqueda no prueba que no exista código compartido con clientes. Para evaluar implementación, el siguiente nivel de acceso sería una prueba autorizada con datos sintéticos y un workspace apropiado, no extrapolar del tour.

## 3. Controles de Squad: tomar en serio el alcance

La documentación de [integraciones y secretos](https://squad.so/resources/docs/integrations-secrets) afirma que las restricciones por agente y cuenta se comprueban en cada llamada, que los secretos no pueden releerse desde el vault y que se puede restringir o bloquear acceso por agente y cuenta. Esto es más concreto que una instrucción al modelo. No se verificó la implementación ni una cobertura común de navegador, shell y MCP.

[Safety & Control](https://squad.so/resources/docs/safety-control) describe aprobación al enviar correo, límites y pausa. [Tickets](https://squad.so/resources/docs/tickets) estructura preguntas que bloquean una misión hasta recibir respuesta. Retirar una respuesta comunica un cambio; no revierte un efecto externo ya realizado. No hay base para presentar ese comportamiento como un bypass demostrado.

El dashboard publicado concentra configuración y facturación en el propietario; la colaboración incluye una lista permitida de Telegram y vistas compartidas. Esto describe el flujo público, no prueba inexistencia de otros roles o rechazo universal por compradores enterprise. [Public team](https://squad.so/resources/docs/public-team), [FAQ](https://squad.so/resources/docs/faq).

Los [runs](https://squad.so/resources/docs/runs-guide) exponen disparador, modelo, tiempos, consumo y actividad de herramientas. Una vista de cuatro semanas no establece por sí sola el plazo total de retención. Tampoco se documentó aquí un contrato de exportación inmutable o reproducción completa.

La [memoria](https://squad.so/resources/docs/memory-guide) hace visible qué contexto se cargó y qué quedó fuera del presupuesto. Es una idea útil para depurar decisiones. Las [skills](https://squad.so/resources/docs/skills-guide) sirven como procedimientos reutilizables, pero esta revisión no estableció una cadena completa de publicación, promoción y rollback aprobados por humanos.

La documentación de [recuperación](https://squad.so/resources/docs/agent-stuck) ofrece diagnósticos, reconexión y pausa/reanudación. [Backup & Export](https://squad.so/resources/docs/getting-help) aparece como opción, sin un contrato público suficiente para afirmar restauración completa. La prueba pendiente debe distinguir reintentar una tarea de reconciliar un efecto ya ocurrido.

**Preguntas decisivas para una prueba:** ¿qué cambia invalida una aprobación?, ¿qué canal cubre cada permiso?, ¿cómo distingue un retry de un segundo efecto?, ¿qué información permite reconstruir la decisión después de exportar?

## 4. Economía, dependencia y patrones que conviene adoptar

El costo total relevante es **plataforma + inferencia o suscripción compatible + extras + tiempo de supervisión**. El precio de entrada no permite calcular costo por resultado sin observar cargas de trabajo reales.

[Connect your AI](https://squad.so/resources/docs/connect-your-ai) diferencia rutas: ChatGPT mediante OAuth de dispositivo; proveedores con API; y Claude con facturación directa o mediante el runtime de Claude Code. “Trae tu suscripción” no significa que cualquier plan funcione igual en todas las rutas. Cuotas, reautenticación y disponibilidad del proveedor forman parte de la operación.

[Costs & Credits](https://squad.so/resources/docs/costs-credits) documenta 1.000 créditos mensuales incluidos, US$5 por 5.000 adicionales y US$10 al mes por inbox. Las llamadas de investigación fallidas y los aciertos de caché no consumen créditos; la tarifa de una investigación concreta debe confirmarse en facturación. Los textos sobre buzones incluidos y adicionales no quedaron completamente reconciliados. Antes de comparar costos, fijar la configuración de cuentas, buzones y tareas.

La garantía de devolución de siete días no es lo mismo que una prueba gratuita. Las condiciones de cancelación y borrado difieren entre páginas; no se verificó la ventana efectiva de recuperación. No se realizó una interpretación legal ni una contratación. [Términos](https://squad.so/terms).

Los resultados de ahorro publicados por un cofundador no son una medición independiente de retorno. El relato y la portada usan porcentajes distintos para disputas, sin una cohorte comparable suficiente. No se adoptan como expectativa de nuestros clientes. [Testimonio de Tibo](https://www.tmaker.io/blog/ai-just-saved-me-10-000).

Patrones que sí merecen un experimento de diseño:

- **Cola de atención:** mostrar qué decisión humana desbloquea trabajo, con suficiente contexto para resolverla.
- **Contexto visible:** explicar qué información recibió el agente y qué quedó fuera.
- **Estado por conexión:** hacer comprensible cuenta, permisos, pausa y necesidad de reautenticación.
- **Progreso con evidencia:** unir misión, intentos y resultados sin confundir texto generado con efectos confirmados.
- **Recuperación honesta:** señalar estados desconocidos y permitir reconciliación, sin prometer deshacer efectos irreversibles.

Estas son recomendaciones propias derivadas de patrones observados; no requieren copiar marca, textos o flujos protegidos del servicio.

## 5. Novedades recientes que cambian la comparación

Ventana principal: últimas seis semanas hasta el 5 de septiembre de 2026. “Nuevo” puede significar lanzamiento, rebranding o actualización; se indica la diferencia. Las capacidades siguientes son documentales salvo donde se señala lectura de código.

| Producto | Evidencia fechada | Qué cambia en la comparación |
|---|---|---|
| Paperclip | Anuncio 20 de agosto; actualizaciones 31 de agosto y 2 de septiembre | Decisiones con snapshots, control de cambios y ejecución de efectos internos; base abierta con sustancia técnica. |
| Cloudflare OS | Anuncio 5 de agosto | Gatekeepers y capacidades ligadas a recursos; un competidor serio para gobierno de ejecución. |
| AgentZ | Anuncio 27 de agosto | Ofrece controles de runtime, credenciales y despliegues enterprise; claims de ejecución pendientes de prueba propia. |
| Kiro Crew | Anuncio 4 de agosto | Memoria persistente, skills, checkpoints y aprobación alrededor de agentes de desarrollo. |
| Warp Agent CLI / Oz | CLI 4 de agosto; estudio 26 de agosto | Ejecución local/cloud y orquestación de herramientas; Oz no nació en esta ventana. |
| Cursor Cloud Agents | Actualización 2 de septiembre | Workers en infraestructura del cliente; el loop e inferencia siguen en Cursor Cloud. |
| Replit Enterprise | Anuncio 16 de agosto, actualizado 18 | Logs y APIs de administración; distinguir disponibilidad actual de fechas prometidas en el anuncio. |

Fuentes: [Paperclip](https://paperclip.ing/blog/v2026-817-0/), [Cloudflare OS](https://blog.cloudflare.com/cloudflare-os/), [AgentZ](https://www.globenewswire.com/news-release/2026/08/27/3351759/0/en/accuknox-launches-agentz-to-help-enterprises-build-run-and-govern-ai-agents-at-scale.html), [Kiro Crew](https://kiro.dev/blog/introducing-kiro-crew/), [Warp CLI](https://www.warp.dev/blog/introducing-the-warp-agent-cli-coding-agent), [estudio de Warp](https://claude.com/blog/how-warp-builds-self-improving-agents-on-claude), [Cursor](https://cursor.com/blog/self-hosted-machines), [Replit](https://replit.com/blog/new-enterprise-governance-tools).

No deben compararse como una categoría homogénea. Squad vende un equipo operativo; los harnesses venden ejecución de desarrollo; los proveedores enterprise venden control e integración con su plataforma. La presión común es que “multiagente con memoria y aprobación” se está convirtiendo en un punto de partida.

## 6. Paperclip: un contraejemplo técnico importante

Se inspeccionó código de **v2026.817.0**, además de documentación. La [actualización del 31 de agosto](https://paperclip.ing/changelog/v2026.831.0/) documenta rechazo de credenciales inválidas, entrega de skills al runtime y cambios de recuperación; el [parche del 2 de septiembre](https://paperclip.ing/changelog/v2026.831.1/) corrige onboarding. No se reinspeccionó todo el código de esas versiones. Esta revisión no ejecutó Paperclip ni constituye una auditoría de seguridad.

El [módulo de firma](https://github.com/paperclipai/paperclip/blob/v2026.817.0/server/src/services/decision-signing.ts#L132) canoniza JSON y calcula HMAC-SHA256 con un secreto del servidor. Eso aporta integridad bajo ese secreto; no es una firma humana ni prueba pública independiente.

El [servicio de decisiones](https://github.com/paperclipai/paperclip/blob/v2026.817.0/server/src/services/decisions.ts) vincula opciones y snapshots, verifica referencias bajo política estricta y registra ejecución por efecto. Contempla idempotencia y resultados parciales. Los inputs humanos se validan y almacenan posteriormente; no debe describirse todo el documento final como parte del objeto inicialmente firmado.

La [unión de efectos](https://github.com/paperclipai/paperclip/blob/v2026.817.0/packages/shared/src/validators/decision.ts#L54) inspeccionada incluye comentarios, creación y cambios de issues, asignación, cancelación y bloqueadores. No incluye una transacción universal para pagos, correo o despliegues. Esta delimitación no determina la cobertura de todos los demás subsistemas.

La documentación de [Decision Training](https://docs.paperclip.ing/reference/api/decision-training/) también contempla snapshots etiquetados por humanos y exportación. Por tanto, ni decisiones verificables ni curación humana de aprendizaje pueden presentarse genéricamente como exclusivas.

**Implicación para Ultimate Harness:** comparar casos de extremo a extremo y no nombres de features. Por ejemplo, qué versión exacta se autorizó, qué cambió después, qué actor está autenticado, qué sucede al repetir la operación y qué se puede recuperar tras una interrupción.

**Implicación para Telar:** un expediente neutral puede tener valor por reconciliar fuentes y hacer visible evidencia incompleta, pero necesita demostrarlo frente a mecanismos ya existentes. Una lista más larga de campos o un hash aislado no establece una ventaja comercial.

## 7. El sustituto enterprise ya instalado

| Alternativa | Cobertura documentada | Consecuencia para Telar |
|---|---|---|
| LangSmith + CI/CD | Datasets, evaluaciones, revisión y gates en un pipeline | Evaluar antes de desplegar ya existe. Medir el trabajo adicional de reconciliar otras fuentes. |
| Arize AX + Airflow | Comparación candidato/baseline y bloqueo de promoción ante regresiones | Un go/no-go basado sólo en scores tiene poco espacio. |
| AWS AgentCore + CodePipeline | Arquitectura con evaluación, políticas y promoción gradual | La neutralidad importa si el cliente sufre fragmentación real entre proveedores. |
| IBM watsonx.governance | Métricas de Orchestrate vinculadas a controles y resultados pass/breach | “Políticas a evidencia” ya es una oferta concreta. El nombre Enforcement Tracking no prueba bloqueo inline. |
| ServiceNow AI Control Tower | Inventario, relaciones y workflows de activos; actualización enterprise de agosto | Otro sistema de registro puede duplicar lo instalado. Considerar ser una integración especializada. |

Fuentes: [LangSmith CI/CD](https://docs.langchain.com/langsmith/cicd-pipeline-example), [Arize, mayo de 2026](https://arize.com/blog/from-production-traces-to-better-ai-agents-automating-the-llmops-feedback-loop/), [AWS, 26 de agosto](https://aws.amazon.com/blogs/architecture/closing-the-ai-agent-trust-gap-with-graduated-autonomy/), [IBM, 11 de agosto](https://www.ibm.com/new/announcements/from-governance-policies-to-governance-proof-with-enforcement-tracking-for-watsonx-orchestrate), [ServiceNow, actualización 6 de agosto](https://www.servicenow.com/docs/r/store-release-notes/store-integrationhub-rn-ai-control-tower.html?contentId=V0oIjCGql2UcYmBR6BCbpw).

Hay incluso una oferta adyacente que describe un paquete de handoff con owners, evaluación, rollback y veredicto de readiness: [Use Case Foundry](https://www.usecasefoundry.com/production-agent-handoff). Es evidencia de oferta pública, sin fecha de lanzamiento ni adopción verificadas. No demuestra que haya clientes pagando por el concepto ni que su implementación satisfaga nuestro caso.

La pregunta comercial debe ser específica: ¿qué decisión reciente se demoró porque la evidencia estaba repartida?, ¿quién hizo el trabajo de reunirla?, ¿qué información faltó?, ¿qué pudo resolver con herramientas existentes? Si no aparece un costo o una decisión real, conviene mantener la propuesta como integración experimental.

## 8. Integrar antes de multiplicar conectores

Un primer flujo es técnicamente plausible sin reemplazar los sistemas del comprador:

**Origen de evaluación → manifest del candidato y sus evidencias → expediente con faltantes → registro de aprobación existente.**

[LangSmith](https://docs.langchain.com/langsmith/export-traces) permite consultas selectivas de runs. Sus [datasets versionados](https://docs.langchain.com/langsmith/manage-datasets) pueden recuperarse en un punto determinado; conservar versión y metadatos es más útil que descargar sólo ejemplos. La [exportación masiva](https://docs.langchain.com/langsmith/data-export) está limitada a planes Plus/Enterprise, por lo que no debería ser requisito inicial de un piloto pequeño.

[GetAgentRuntime](https://docs.aws.amazon.com/bedrock-agentcore-control/latest/APIReference/API_GetAgentRuntime.html) acepta una versión y expone metadatos del artefacto y configuración. [GetEvaluator](https://docs.aws.amazon.com/bedrock-agentcore-control/latest/APIReference/API_GetEvaluator.html) diferencia información completa y sólo metadatos según permisos. Si faltan instrucciones o escala, el expediente debe declararlo. Invocar [Evaluate](https://docs.aws.amazon.com/bedrock-agentcore/latest/APIReference/API_Evaluate.html) ejecutaría una evaluación nueva; no es una lectura gratuita de un resultado anterior.

IBM dispone de [custom facts](https://s3.us.cloud-object-storage.appdomain.cloud/aifactsheets-client/doc_files/asset_model/Model/Model%20Custom%20Facts.html) y [attachments](https://s3.us.cloud-object-storage.appdomain.cloud/aifactsheets-client/doc_files/asset_model/Model/Model%20Attachments.html). La [Attachment API de ServiceNow](https://www.servicenow.com/docs/r/api-reference/rest-apis/c_AttachmentAPI.html) ofrece otra vía para entregar un paquete a un registro autorizado. Esto no demuestra una API específica de decisiones de AI Control Tower ni una relación inmutable entre adjunto y release.

La primera construcción debería concentrarse en correspondencia entre candidato y evidencia, versiones disponibles, faltantes y referencias. Las principales fricciones serán permisos, calidad de metadatos, versiones del cliente y costo de integración. Un ID no garantiza procedencia completa.

No se llamaron APIs autenticadas ni se crearon integraciones. La recomendación es elegir **un origen y un destino según un comprador real**, y comprobar si la mejora supera a una exportación y una plantilla.

## 9. Lo nuestro: implementación, evidencia y brechas

**Telar planificación** contiene una arquitectura amplia de intención, políticas, identidad y ledger. Sus contratos propuestos no deben contarse como runtime disponible. La [página vigente de planning en Notion](https://app.notion.com/p/Telar-Planning-Release-v3-3c013597488481dc98f5e426e843c816) conserva el estado planning only y no autoriza implementación de producto. El enfoque comercial propuesto aquí no modifica esa autorización ni sustituye por sí solo la arquitectura. **Telar-Demo** tiene implementación real en dominio, aplicación y UI; la revisión encontró código y un estado reciente de misión con 12 de 14 entregas integradas. Un PLAN antiguo que dice que no comenzó la implementación está desactualizado frente a esa evidencia.

El contrato actual del demo mantiene la oferta inicial como **release assurance externo y recomendación advisory**, con escenarios sintéticos. Las notas históricas de pruebas no equivalen a pruebas repetidas hoy; la preparación completa para ejecutar el demo sigue sin quedar establecida en esta investigación. Otra tarea mantiene un escritor activo en ese proyecto, por lo que no se inició una verificación concurrente.

**Ultimate Harness sí recibió una verificación focalizada actual**, a cargo de la tarea propietaria de arquitectura. En la revisión d4e7753, seis archivos y **82 pruebas pasaron**: promoción, verificación, cancelación, directorios por run, pruning y reparación de drift. Eso prueba sus casos existentes, no las propiedades ausentes de esos casos.

Una prueba negativa temporal confirmó lo siguiente:

- El aprobador es una cadena no vacía; ese recorrido no autentica un principal ni comprueba una firma.
- La promoción exige una verificación válida de la misma misión y estado passed, pero no la vincula al digest del diff o a la revisión exacta.
- Se cambió el diff después de verificar y la promoción siguió aceptándose.
- Un review gate declarado no impidió esa promoción: en el recorrido inspeccionado es metadato, no una comprobación ejecutada.

La recuperación local incluye directorios por run, eventos, watchdogs y reparación de runs huérfanos. Sin embargo, la cancelación del plugin depende de procesos en memoria; tras reiniciar el servidor, un run no terminal en disco puede quedar fuera de ese mapa. Arranques concurrentes de una misma misión se aceptan; no se estableció deduplicación por identidad de petición. El índice usa read/modify/write sin bloqueo y sus pruebas no garantizan conservación de todas las entradas concurrentes.

**Prioridad propuesta para UH:** identidad autenticada del aprobador; binding a candidato exacto; receipt de revisión realmente evaluado; idempotencia de petición; recuperación y cancelación tras reinicio. Es trabajo futuro, no cambios efectuados por esta investigación.

Evidencia interna: `src/harness/promote.ts`, `verify.ts`, `src/schema/artifacts.ts` y los tests focalizados; informe de la tarea “Core agentic delivery architecture”. Typecheck pasó según su informe. La suite general también se ejecutó en esta revisión: 877 passed / 2 failed por plantillas de especificación ausentes; no se presenta el repositorio como totalmente verde. El anexo reproducible conserva comandos, precondiciones, resultado y referencias de línea: [verificación de Ultimate Harness](ultimate-harness-capability-verification.md).

## 10. Demanda observada y crítica independiente

La búsqueda encontró problemas técnicos concretos. No encontró una prueba suficiente de disposición a pagar por una capa neutral de recomendación de release.

En julio, un usuario de dcode pidió exportar herramientas y procedencia de aprobación porque revisar la sesión exigía interfaz, LangSmith o decodificar SQLite. El seguimiento de agosto reconoció límites del transcript. La issue [se cerró por inactividad el 28 de agosto](https://github.com/langchain-ai/deepagents/issues/4843#issuecomment-5447051775), no como entrega de la función. Es una señal cercana al problema de evidencia, pero propone una solución OSS. [Solicitud y discusión](https://github.com/langchain-ai/deepagents/issues/4843).

En agosto, un reporte reproducible de OpenAI Agents SDK describió un fallo de persistencia después de aprobación y handoff: el estado conservaba resultados que faltaban en el historial. No repetía el efecto de la herramienta; sí dejaba versiones contradictorias de la conversación. Hubo una corrección integrada. Esto demuestra tanto el problema de reconciliación como el avance de las soluciones nativas. [Issue](https://github.com/openai/openai-agents-python/issues/4685), [corrección](https://github.com/openai/openai-agents-python/pull/4725).

Otros reportes muestran aprobaciones móviles que bloquean trabajo y dificultades de reanudación. No equivalen a incidentes empresariales, pérdidas verificadas o demanda de go/no-go entre proveedores. [Codex Remote, corroboración reciente](https://github.com/openai/codex/issues/39346#issuecomment-5501675905), [LangGraph, caso anterior con seguimiento posterior](https://github.com/langchain-ai/langgraph/issues/6792).

La validación en Claude local completó dos rondas con la etiqueta visible **Fable 5.1 Medium**. No fue una evaluación ciega ni una verificación del backend del proveedor. La segunda ronda retiró afirmaciones excesivas de la primera sobre vulnerabilidades o funciones ausentes en Squad. El aporte útil fue cuestionar cuatro sustitutos: consolidar proveedores, usar un documento del integrador, esperar funciones nativas o pedir enforcement real en vez de advisory.

En Command Code, el catálogo web incluye las variantes Flash solicitadas pero el CLI local no las mostró. Quedaba un saldo mínimo y no se encontró una cota comprobable de costo/salida; no se ejecutó inferencia ni se recargó. Esa validación adicional permanece sin realizar. [Catálogo](https://commandcode.ai/docs/reference/cli/models), [modo headless](https://commandcode.ai/docs/headless).

**Experimento comercial propuesto:** comparar un expediente manual y el proceso actual con el paquete propuesto en una decisión real autorizada. Medir tiempo de preparación y de revisión, faltantes encontrados, decisión que cambia, esfuerzo de integración y disposición a contratar un piloto. No sustituir pago por estrellas, interés verbal o umbrales arbitrarios de una landing.

## 11. Spark para Prism Arena: un track distinto

[Spark](https://sparkjs.dev/) es un renderizador de Gaussian splats para Three.js, con licencia MIT. Puede enriquecer escenas con apariencia capturada, pero modifica lo que se está midiendo: seleccionar y componer un asset no es lo mismo que construir geometría y materiales desde un contrato restringido.

Prism Arena hoy usa SceneSpec v1 con primitivas, materiales limitados y un renderer compartido. La inspección encontró un registro de THREE.Mesh, reloj Anime.js con seek explícito y una evaluación visual con identidad del modelo ocultada. Una integración requiere modificar el contrato de tareas y captura, no simplemente añadir una dependencia.

**Propuesta:** conservar el benchmark primitivo y abrir una versión separada de splats/híbridos. Dar a todos los modelos el mismo catálogo, nombres neutrales, licencias y hashes. Evaluar composición, relaciones espaciales y cumplimiento temporal por separado de estética del asset y rendimiento del renderer.

[SplatMesh](https://sparkjs.dev/docs/splat-mesh/) hereda de Object3D; opacidad y transformaciones no deben tratarse como si fueran el material de un Mesh ordinario. Empezar con posición, rotación, escala uniforme y opacidad. La deformación y el escalado anisotrópico requieren otra evaluación.

La [documentación del renderer](https://sparkjs.dev/docs/spark-renderer/) permite controlar tiempo y actualizaciones, pero también contiene parámetros que cambian la imagen: color, orden radial/Z, blur, radios, profundidad y supersampling. Deben quedar fijados junto con Spark, Three, navegador, GPU y viewport. No se promete igualdad de píxeles entre dispositivos.

La inspección de [SparkRenderer v2.1.0](https://github.com/sparkjsdev/spark/blob/v2.1.0/src/SparkRenderer.ts#L808) encontró que una actualización puede disparar LoD sin esperarlo, y que sorting puede devolver control si otro trabajo está activo o se agenda por intervalo. Por tanto, un await genérico no basta como certificado global de escena lista.

El primer experimento debe usar un asset residente, sin paging/LoD, actualizaciones seriales y reloj explícito. Inicialización no implica convergencia de streaming; precargar bytes tampoco elimina todo decoding asíncrono. El streaming necesita un criterio observable de residencia y ordenamiento, no una pausa fija.

## 12. Experimentos mínimos de Prism y de evidencia

Estos experimentos están diseñados, **no ejecutados**. No se realizaron sweeps de modelos ni cambios en rankings.

| Experimento | Qué permite decidir |
|---|---|
| Captura serial de un splat pequeño residente | Si la ruta básica produce imágenes repetibles bajo un entorno fijado. Comparar hashes y diferencias de píxel. |
| Salto directo, avance y retroceso al mismo tiempo | Si el estado depende sólo del tiempo objetivo o arrastra acumulación de callbacks. |
| Mesh opaco delante, detrás y cruzando un splat | Si oclusión y transparencia híbrida son aceptables y estables. |
| Captura en contexto nuevo y copia de buffers | Si la inicialización o reutilización de buffers contamina imágenes anteriores. |
| Paging frío/caliente con distinta trayectoria | Si puede definirse una barrera de captura verificable antes de abrir streaming al benchmark. |
| Revisión del juez con assets idénticos | Si la nota refleja el trabajo del modelo y no sólo el atractivo de un asset prefabricado. |

Las tolerancias visuales y presupuestos de rendimiento deben derivarse de mediciones iniciales. Fijarlas sin fixtures sería inventar un criterio. El rendimiento se reportaría aparte: carga, memoria y estabilidad de frames, con el hardware explícito.

Para Telar y UH, la matriz de conformance inicial debería incluir:

- Cambiar un campo relevante del candidato después de evaluar y comprobar que la evidencia anterior deja de contar.
- Retirar una fuente o versión obligatoria y producir “evidencia insuficiente”, sin promediar el hueco como aprobado.
- Diferenciar identidad autenticada, rol y delegación de una etiqueta de nombre.
- Interrumpir entre efecto confirmado y registro; reconciliar intentos con el resultado externo.
- Reconstruir el contexto que vio el revisor, conservando referencias y desconocidos sin afirmar almacenamiento inviolable.

La discrepancia observada en el demo de Squad ofrece un fixture sencillo: el resumen de misión y el documento a aprobar indican importes distintos. Nuestro experimento debe detectar el conflicto y pedir resolución. La inconsistencia era de datos sembrados; no se observó dinero movido ni un fallo de producción.

## 13. Roadmap propuesto desde Linear

La revisión se hizo **con Linear Agent en la aplicación local**, mediante conversación. No se editaron tareas ni se pidió al agente modificarlas. [Conversación de revisión](https://linear.app/agentic-engineering-company/agent/revisar-tareas-pendientes-de-agentic-engineering-d8783840222ca).

La tabla siguiente resume exclusivamente la propuesta de Linear Agent; no es un calendario comprometido. Las recomendaciones propias se separan después. El agente terminó con un inventario de 43 + 45 = **88 tareas directas de AE**, pero reconoció discrepancias por paginación. No es un total auditado. Los conteos anteriores de 89 y de toda la jerarquía no deben usarse como denominador fiable. Tampoco se comprobaron individualmente todas las fechas o capacidad de responsables.

| Horizonte propuesto | Resultado que debería desbloquearse |
|---|---|
| Próximas dos semanas | Cerrar decisiones de oferta y verdad financiera; desbloquear dominio/outbound y aprobaciones de Apollo. |
| Curia/KLGV | Secuencia CI → definición de demo lista → OCR/PostHog/smoke → readiness y firmas. |
| PriceGenius / ShesMine | Decisiones explícitas de continuidad antes de ampliar trabajo. |
| Semanas tres y cuatro | Ejecutar oportunidades una vez cerrados bloqueos; concentrar expansión en una ruta de caja. |
| Code Colony / UH / Landing | Priorizar bloqueos de entrega; mantenimiento de landing; evitar competir con todas las funciones recién anunciadas. |

El límite de dos tareas activas por responsable fue una propuesta del agente y requiere confirmar capacidad. No es una regla aplicada.

Dos correcciones importan: **Twenty está operativo** según la tarea actual; la acción indicada es rotar la clave y resincronizar. El apagado estaba condicionado a una exportación verificada, no era una decisión inmediata. **Telar figura activo en cartera**, pero el agente no encontró un proyecto/equipo con ese nombre; su roadmap específico no quedó cubierto.

La recomendación de esta investigación es añadir a la planeación de Telar una decisión de validación, no una lista masiva de features: comprador, release real atascado, baseline y experimento de expediente. Para UH, convertir las brechas verificadas en criterios de aceptación cuando se autorice implementación. Para Prism, limitar el siguiente paso a un spike de captura residente en track separado.

No se asignaron responsables ni fechas de compromiso sin evidencia de capacidad. La propuesta requiere una revisión de cartera antes de convertirse en calendario.

## 14. Conversaciones de San Francisco y próximos pasos

Este es un guion interno de descubrimiento, no un pitch externo aprobado para Telar.

La pregunta inicial más útil sería: **“Cuéntame del último release de un agente que necesitó aprobación: qué evidencia tuvieron que reunir, quién la revisó y qué atrasó la decisión.”** Después pedir un ejemplo del proceso actual, evitando sugerir de entrada que hace falta otra plataforma.

Preguntas de seguimiento:

- ¿Qué parte de esa evidencia proviene de dos o más sistemas? ¿Se pierde una versión o una excepción al pasarla entre equipos?
- ¿Qué cambio obliga a repetir evaluación o aprobación? ¿Cómo saben que el release final es el que revisaron?
- ¿Qué resuelven hoy con su pipeline, LangSmith, documentos o sistema de cambios?
- ¿Quién prepara el paquete y quién puede autorizar presupuesto? ¿Son personas diferentes?
- Si sólo entregáramos el expediente en su workflow actual, ¿qué seguiría faltando?
- ¿Necesitan una recomendación o exigen bloqueo operativo? La respuesta cambia el producto.

Una demostración útil tendría dos estados: candidato con evidencia completa y el mismo candidato después de cambiar un elemento relevante o retirar una fuente. Mostrar el faltante, la procedencia y la decisión humana permite una conversación más concreta que una promesa de “control total”.

Criterios para continuar: problema repetido, decisión o demora observable, ventaja frente al método actual y posibilidad de un piloto autorizado. Criterios para reducir o reformular: sólo mejora estética, integración más costosa que el problema, suficiencia del stack existente o necesidad de enforcement fuera del alcance inicial.

**Secuencia sugerida:** primero descubrimiento y baseline; después un expediente con fuentes sintéticas; luego un origen real y un destino del comprador; finalmente un release autorizado. Cada paso debe producir una decisión sobre el siguiente. No se contactó a clientes ni se ejecutaron estos experimentos durante la investigación.

## 15. Método, límites y trazabilidad

Se utilizaron carriles de investigación independientes para producto, mercado, Linear y crítica externa; después se hicieron seguimientos dirigidos sobre código público, APIs, señales de dolor y demo. Las fuentes primarias están enlazadas junto a las afirmaciones. La fecha de consulta es el 5 de septiembre de 2026; precios y disponibilidad pueden cambiar.

Estados de evidencia usados:

- **Documentado:** descrito por el proveedor, no probado en ejecución.
- **Inspeccionado en código:** observado en una revisión concreta; no prueba todo el producto desplegado.
- **Probado ahora:** sólo las pruebas focalizadas y el probe de UH reportados por la tarea propietaria.
- **Histórico:** resultados recogidos en notas del proyecto, sin repetición en esta sesión.
- **Propuesto o desconocido:** no se eleva a capacidad disponible ni a ausencia de capacidad del competidor.

La revisión del demo de Squad comprobó navegación, diálogos y contenido sembrado. No guardó permisos, respondió tickets, conectó cuentas o envió mensajes. La prueba financiera de la UI era ficticia. La lectura de Paperclip y Spark no ejecutó sus suites ni certificó seguridad o determinismo.

No se realizaron pruebas pagadas de Squad, benchmark con modelos, deployments, instalaciones ni cambios permanentes de producto o issues. UH sí recibió un probe temporal de promoción, separado del código del producto. Command Code no produjo una respuesta de validación; Claude sí completó dos rondas con corrección de afirmaciones. La revisión externa no recibió código ni backlog privados.

Límites pendientes: inventario completo de Linear y mapa de Telar; readiness actual de Telar-Demo; integración real de APIs; costos por tarea de Squad; pruebas de recuperación externa y permisos; demanda y precio aceptado por un comprador; determinismo práctico del nuevo track de Prism.

El informe recomienda próximos experimentos y prioridades. No declara un moat probado ni una certificación técnica. El resultado más importante es hacer comparables las promesas con casos observables y con los sustitutos que el cliente ya tiene.
