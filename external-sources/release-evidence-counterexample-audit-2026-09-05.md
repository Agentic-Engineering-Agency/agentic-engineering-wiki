---
type: source
description: "Auditoría interna revisada sobre JFrog, Kosli y la hipótesis comercial de Telar."
source_url:
date_fetched: 2026-09-05
preservation: verbatim-local-text
tags: [ source, immutable, layer-ingest, internal, competition ]
title: Auditoría de contraejemplos — evidencia de release — 2026-09-05
confidentiality: internal
source_origin: Reviewed final-counterexample-audit.md supplied by the coordinating task
---

<!-- markdownlint-disable MD025 MD060 -->

# Auditoría final de contraejemplos — 5 de septiembre de 2026

Alcance: lectura de report-source.md y fuentes públicas primarias; sin APIs autenticadas, ejecución de competidores ni entrevistas. **Sí hay una corrección material de cobertura:** el expediente neutral de release no sólo compite con una plantilla, LangSmith, IBM o ServiceNow. JFrog AppTrust y Kosli ofrecen directamente una cadena de evidencia ligada al release. El informe ya evita exclusividad; debe añadir estos comparadores antes de priorizar construcción.

## Contraejemplos que cambian la decisión

| Fuente primaria / fecha | Qué acredita documentalmente | Qué no acredita / consecuencia |
|---|---|---|
| [JFrog: Every Release Needs a Chain of Custody](https://jfrog.com/blog/prompt-to-release-traceability/), Sophie Starchenko, 2 sep 2026 | Anuncia Prompt to Release Traceability GA: reúne commits, PRs, transiciones Jira y aprobadores, firma y adjunta a la versión antes de gates. Distingue autoaprobación y muestra contador de aprobaciones caducadas. | Es anuncio del proveedor, no prueba propia ni validación de cobertura total. **Agent session evidence y session BOM llegan después en 2026**, no están incluidos en lo declarado GA. Sustituto directo del expediente propuesto, y novedad dentro de la ventana. |
| [AppTrust Quickstart](https://docs.jfrog.com/governance/docs/apptrust-quickstart), documentación consultada hoy, actualización relativa de 3 meses | Versiones inmutables; promoción explícita tras requisitos; evidencia firmada de cuándo, dónde y quién promovió, certificaciones de políticas. Requiere Enterprise+, Artifactory 7.125.x+, Xray 3.130.5+, AppTrust habilitado y CLI 2.81+. | No prueba firma personal independiente ni que una versión represente todos los estados externos de un agente. La fricción enterprise es real documentalmente, pero no demuestra que Telar sea más barato en costo total. |
| [Reglas AppTrust](https://docs.jfrog.com/governance/docs/apptrust-out-of-the-box-rules), documentación consultada hoy | Regla concreta que exige evidencia servicenow-change-approval, además de Sonar, GitHub provenance y Troj.ai. | Existencia de un tipo de evidencia no prueba que su contenido, identidad y vigencia sean suficientes en todas las configuraciones. Hay que comparar reglas concretas y excepciones. |
| [Kosli: release/promotion workflow](https://www.kosli.com/blog/a-release-workflow-in-kosli/), Jon Jagger, 20 mar 2025 | Ejemplo técnico público: fingerprints de artefactos entrantes/salientes, cumplimiento de evidencia SDLC, expediente de release en un Flow y aprobación humana final desde CI; muestra configuración y repositorio demo. | Baseline anterior a la ventana, no lanzamiento reciente. No ejecutado por nosotros. Ya se propone reconciliar evidencia entre repos y entornos dejando aprobación en CI: neutralidad/advisory por sí solos no bastan. |
| [Kosli report approval](https://docs.kosli.com/client_reference/kosli_report_approval/), documentación sin fecha editorial absoluta | Registra aprobación de despliegue asociada a SHA256, entorno y rango de commits. | --approver es un string opcional: no concluir identidad humana criptográficamente autenticada sólo por este endpoint. Distinguir reporte de aprobación de emisión/autorización. |
| [SLSA VSA v1.2](https://slsa.dev/spec/v1.2/verification_summary), estándar Approved consultado hoy | Predicado existente para resumir verificación de artefactos contra un bundle de attestations y política. | No es producto ni decisión humana; sí evita inventar un formato propietario como diferencial. Evaluar compatibilidad de manifest/receipts con in-toto/VSA. |

[Evidence Management](https://docs.jfrog.com/governance/docs/evidence-management) exige Enterprise+ para evidencia externa; Artifactory interna desde Pro y Xray desde Pro X. [Quickstart de evidencia](https://docs.jfrog.com/governance/docs/evidence-quick-start) expone CLI/REST y un subject por attestation DSSE/in-toto. Esto sostiene un posible papel de Telar como productor de evidencia especializada, no la necesidad demostrada de otro registro.

## Evidencia de comprador: reformular con precisión

[Anuncio Kosli/DNB/Firi](https://www.kosli.com/blog/kosli-announces-innovation-partnership-with-dnb-and-firi/), Bruce Johnston, 23 nov 2022, identifica POC con DNB y a Firi como cliente desde 2020, con colaboración operacional en cumplimiento. Es señal comercial nominal del proveedor más fuerte que una issue OSS, pero no revela contrato, precio ni prueba de compra del wedge específico de agentes. No convertirlo en demanda validada para Telar. Tampoco usar las mejoras de tiempo publicadas por JFrog como ROI independiente.

La redacción actual «no se encontró prueba suficiente de disposición a pagar por una capa neutral de recomendación de release» sigue siendo defendible con ese alcance. Añadir: **sí existen clientes identificados en la categoría adyacente de evidencia y compliance SDLC; falta averiguar qué necesidad residual tiene un equipo de AI platform que ya puede comprarla.**

## Fechas y clasificación verificadas

- [Cloudflare OS](https://blog.cloudflare.com/cloudflare-os/): 5 ago 2026, Phillip Jones y Dan Carter. Correcto como anuncio/open source de nueva versión, no nacimiento interno: el artículo dice acceso interno desde mayo.
- [Kiro Crew](https://kiro.dev/blog/introducing-kiro-crew/): 4 ago 2026, Bolin Chen, Zejiang Guo y Zezhen Xu. Correcto como publicación abierta, con antecedente MeshClaw interno. Claims de seguridad/adopción no repetidos en esta auditoría.
- [Cursor Self-Hosted Machines](https://cursor.com/blog/self-hosted-machines): 2 sep 2026, Jack Pertschuk. Correcto como actualización de ejecución; no convierte todo el servicio en self-hosted.
- Añadir JFrog del 2 sep como novedad material. No se revalidaron en este pase todas las fechas restantes del informe; no afirmar auditoría temporal exhaustiva.

## Cambios recomendados al informe y experimento

1. En secciones 1, 5 y 7, añadir JFrog AppTrust y Kosli como comparadores principales del expediente; mantener IBM/ServiceNow pero no como únicos incumbentes.
2. Sustituir cualquier lectura de «expediente neutral = espacio vacío» por «expediente especializado cuya utilidad incremental debe vencer a Kosli/AppTrust o integrarse con ellos».
3. Probar un manifest de agente concreto: código, modelo/configuración, tools/policy, dataset/evaluator, aprobación y receipts. Comparar qué cambios invalidan evidencia tanto en propuesta como en el stack elegido. No afirmar que los incumbentes carezcan de esos campos si aceptan evidencia custom.
4. Pedir al comprador mostrar una decisión bloqueada que siga siendo costosa después de configurar su stack. Si sólo falta un attestation custom o una regla, preferir integración. Si requiere gobernar estado externo mutable, definir ese alcance antes de llamarlo candidato exacto.
5. Para UH, digest y aprobador autenticado son requisitos básicos frente a estos comparadores; cerrarlos mejora corrección, no demuestra moat. El valor comparativo de adaptadores y recuperación debe probarse independientemente.

Confianza alta en la omisión material y las fechas explícitas consultadas; media en suficiencia funcional del sustituto; baja/no establecida en eficacia desplegada, costos integrales y demanda específica. Auditoría terminada, sin cambios en el informe principal ni aplicaciones.
