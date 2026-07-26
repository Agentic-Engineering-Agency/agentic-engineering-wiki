---
type: research-note
title: AE 28-row trigger ledger — 2026-07-26
description: Row-level company evidence ledger for the frozen 28-label AE cohort, separating raw, durable, and conservative working-wedge counts.
status: provisional
created: 2026-07-26
author: Codex with parallel GPT-5.6 Sol research lanes
human_review: pending
tags:
  - research
  - gtm
  - sales
  - accounts
  - mexico
  - evidence-ledger
  - 2026-07-26
sources:
  - external-sources/ae-account-discovery-snapshot-2026-07-26.md
  - research/ae-50-account-pilot-seed-2026-07-26.md
  - articles/account-discovery-evidence-rules.md
---
## Question and scope

What does the frozen 28-label AE cohort support when the [account-discovery evidence rules](../articles/account-discovery-evidence-rules.md) are applied row by row and raw, durable, and conservative working-wedge counts are kept separate?

This provisional ledger adds no company. It makes the existing evidence packet in the [source snapshot](../external-sources/ae-account-discovery-snapshot-2026-07-26.md) and [50-account pilot seed](./ae-50-account-pilot-seed-2026-07-26.md) countable. Fifteen frozen UNKNOWN or non-durable records were reviewed; only DIDCOM and Poly Rafia were upgraded. Every row remains pending human review.

## Controlling result

- Frozen cohort: 28 rows and no new company.
- Raw strict-trigger verdicts: 20 YES, 8 UNKNOWN, 0 NO. Absence is never inferred.
- Four raw YES verdicts rely on transient trigger sources: ENVESTA, Grupo Formex, Pinturas Adhler, and MEXDEN.
- DIMECA is raw YES from a mutable vendor homepage, not a durable case permalink.
- Durable-trigger result: 15 YES.
- Conservative working set: 11 — Grupo CIPSA, Dysal, Grugar Industrial, ODISA, Poly Rafia, Promaquina, IPISA, Alianza Eléctrica, Azerty de México, YINSA, and JAKO.
- The conservative set excludes DIDCOM because its system signal remains UNKNOWN; Química Delta because control adjudication after the announced acquisition and its system signal remain open; Grupo Pochteca because the size band is unresolved; and Maison Paulette because its operating model is outside the wedge.
- Identity: 24 MATCHED, 1 DISTINCT, 3 UNKNOWN.
- Operating model: 25 INDUSTRIAL, 2 OUTSIDE, 1 UNKNOWN.
- System signal: 24 PRESENT, 4 UNKNOWN.
- Existing human dispositions remain 4 E1, 5 E2, 17 Hold, and 2 DQ.

> [!IMPORTANT]
> The numerical >=15 evidence gate is **CLEARED exactly** at 15 durable YES verdicts, pending human review. This numerical result does not authorize a second batch, named-person or contact research, CRM mutation, qualification or activation, drafting, outreach or sends, deployments or merges, access changes, archival, or deletion.

## Counting rule

A strict YES requires explicit recurring accounts-payable, purchase-order, invoice, reconciliation, approval, or financial-close workflow evidence. ERP or module presence alone is UNKNOWN, not YES. Missing evidence is UNKNOWN, never NO.

A durable YES requires the trigger itself on a primary or government source, a specific vendor case page, or a static vendor PDF. A durable identity page cannot rescue a transient trigger. A mutable vendor homepage can support a raw YES but not a durable YES.

The conservative working set requires a durable YES, an industrial operating-model verdict, a system signal, and no explicit outside-wedge, control, or size blocker identified in this pass. It is not a qualified-account list; control and size remain unresolved on many rows.

## Core row ledger

| # | Label | Entity/domain dedupe | Operating model | Strict trigger | System | Current human disposition |
| ---: | --- | --- | --- | --- | --- | --- |
| 1 | Grupo CIPSA | MATCHED — trade/domain cipsa.com.mx; first-party legal mapping pending | INDUSTRIAL | YES — PO, invoice/credit-note upload, checks, payment complements, scheduled payment | PRESENT — supplier portal; SAP Fiori supplementary and uncorroborated | E1 |
| 2 | DIMECA | MATCHED — trade/domain dimeca.com.mx; exact legal entity unknown | INDUSTRIAL | YES — requisitions and automatic invoicing | PRESENT — SAP Business One plus eight integrated systems | E1 |
| 3 | Dysal | MATCHED — DYSAL SAPI de CV; dysal.mx | INDUSTRIAL | YES — inefficient accounting closes across functions | PRESENT — SAP Business One | E1 |
| 4 | Productos Helados Milky Mich | MATCHED — Productos Helados Milky Mich SA de CV; milkymich.mx | INDUSTRIAL | UNKNOWN — modules listed without an explicit recurring trigger | PRESENT — Odoo Online | E1 |
| 5 | Raloy Lubricantes | MATCHED — Raloy Lubricantes SA de CV; raloylubricantes.mx / raloy.com.mx | INDUSTRIAL | UNKNOWN — modules only | PRESENT — Odoo 10 | E2 |
| 6 | Grugar Industrial | MATCHED — Grugar Industrial SA de CV; grugar.com.mx | INDUSTRIAL | YES — PO/warehouse-entry references, price/quantity match, invoice cutoff, scheduled payment | PRESENT — Odoo accounts payable | E2 |
| 7 | Pinturas Adhler | MATCHED — Pinturas Adhler SA de CV; pinturasadhler.com.mx | INDUSTRIAL | YES — AP/AR, reconciliation, and close | PRESENT — ERP/Odoo | E2 |
| 8 | MEXDEN | MATCHED — Mexicana de Envases ZZ SA de CV; mexden.com | INDUSTRIAL | YES — bank reconciliation, entries, and invoicing in ERP | PRESENT — ERP unspecified | E2 |
| 9 | ODISA | MATCHED — ODISA Concrete Equipment SA de CV; odisa.com | INDUSTRIAL | YES — automatic purchase orders by project need | PRESENT — Odoo Online | E2 |
| 10 | ENVESTA | MATCHED — Extrusiones Nacionales Vesta SAPI de CV; envesta.com.mx | INDUSTRIAL | YES — recurring billing and collections workflow | PRESENT — CONTPAQi plus ERP | Hold |
| 11 | Grupo Formex | UNKNOWN — group legal grain spans Formularios de México, Cargraphics, and Grupo Bloei; formex.com.mx | INDUSTRIAL | YES — recurring invoicing/accounting workflow in transient job evidence | PRESENT — Monarch/SAP signal plus first-party supplier portal | Hold |
| 12 | Poly Rafia | MATCHED — Poly Rafia SA de CV; polyrafia.com.mx | INDUSTRIAL | YES — monthly orders plus an invoice package for each delivery, electronic CFDI/PDF/XML, and correction/resubmission | PRESENT — [first-party integrated-management-system/technology signal](https://www.polyrafia.com.mx/nosotros/); not ERP | Hold |
| 13 | Química Delta | MATCHED — Química Delta SA de CV; qdelta.com.mx | INDUSTRIAL | YES — orders, payment files, and CFDI | UNKNOWN | Hold |
| 14 | Promaquina | MATCHED — Promaquina SA de CV; promaquina.com | INDUSTRIAL | YES — ongoing orders and invoices | PRESENT — STRUMIS primary signal plus SAP Business One vendor signal | Hold |
| 15 | IPISA | DISTINCT — Instrumentos y Productos Industriales SA de CV; ipisa.com.mx; not the ipisa.mx homonym | INDUSTRIAL | YES — invoicing, collections, provider payments, orders, and invoices | PRESENT — first-party Odoo | Hold |
| 16 | DIFATSA | UNKNOWN — exact entity/domain binding unresolved; difatsa.mx | INDUSTRIAL | UNKNOWN — system evidence without a strict recurring trigger | PRESENT — SAP Business One vendor signal | Hold |
| 17 | Alianza Eléctrica | MATCHED — Alianza Eléctrica SA de CV; alianzaelectrica.com; affiliate boundary remains | INDUSTRIAL | YES — invoice workflow | PRESENT — SAP Business One | Hold |
| 18 | Azerty de México | MATCHED — Azerty de México SA de CV; azerty.com.mx / azerty.mx | INDUSTRIAL | YES — authenticated order and invoice portal | PRESENT — portal system; ERP unknown | Hold |
| 19 | YINSA | MATCHED — Yeso Industrial de Navojoa SA de CV; yinsa.com.mx | INDUSTRIAL | YES — AP, PO, invoice, review, approval, and payment | PRESENT — first-party portal plus SAP Business One vendor signal | Hold |
| 20 | Nobazul | MATCHED — Noble Nutrición en Agave SA de CV; nobazul.com; Mieles Campos Azules mapping unknown | INDUSTRIAL | UNKNOWN — no strict recurring trigger for the verified entity | UNKNOWN | Hold |
| 21 | UniSeal | MATCHED — American Healthcare Products SA de CV; uniseal.com.mx | INDUSTRIAL | UNKNOWN — system evidence without a strict recurring trigger | PRESENT — SAP Business One | Hold |
| 22 | DIDCOM | MATCHED — Grupo Tecnológico DIDCOM SA de CV; didcom.com.mx | INDUSTRIAL | YES — invoice/payment communications, billing management, and collections | UNKNOWN | Hold |
| 23 | JAKO | MATCHED — Productos JAKO SA de CV; jako.mx | INDUSTRIAL | YES — slow invoicing, accounting, reporting, and financial processes | PRESENT — SAP Business One | Hold |
| 24 | Ah Cacao | MATCHED — Ah Cacao Real Chocolate SA de CV; ahcacao.com | UNKNOWN — cafés plus factory require adjudication | UNKNOWN — modules only | PRESENT — Odoo | Hold |
| 25 | IMAG Organics | MATCHED — Inulina y Miel de Agave SA de CV / IMAG Organic; domain confirmation pending | INDUSTRIAL | UNKNOWN — system evidence only | PRESENT — SAP Business One | Hold |
| 26 | Grupo Pochteca | MATCHED — Grupo Pochteca SAB de CV; mexico.pochteca.net | INDUSTRIAL | YES — PO, invoice, match, payment, and approval | PRESENT — Coupa | Hold |
| 27 | Maison Paulette | MATCHED — Repostería Paulette S de RL de CV; paulette.com.mx | OUTSIDE — B2C pastry/bistro chain | YES — monthly financial close | PRESENT — SAP Business One plus Retail One | DQ |
| 28 | Super Tiendas Esquer | UNKNOWN — legal Super Tiendas Esquer S de RL de CV; trade domain observed but legal mapping unresolved | OUTSIDE — retail | UNKNOWN — one audited procurement does not establish a recurring trigger | UNKNOWN | DQ |

## Evidence and treatment

| # | Label | Durable source / trigger evidence | Source class | Durable-trigger treatment | Conservative set | Observed-at | Reviewer | Human review | Remaining gaps |
| ---: | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Grupo CIPSA | [Supplier portal](https://proveedores.cipsa.com.mx/) states PO, invoice/credit-note upload, checks, payment complements, and scheduled payment | Primary supplier portal | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Legal mapping, control, size, and SAP Fiori corroboration |
| 2 | DIMECA | [Tangente homepage](https://tangentemexico.com/) states requisitions and automatic invoicing | Mutable vendor homepage | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Durable case permalink, exact legal entity, control, size, and corroboration |
| 3 | Dysal | [SAP/Xamai PDF](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) states inefficient accounting closes across functions | Static vendor PDF | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and independent vendor-case corroboration |
| 4 | Productos Helados Milky Mich | [Odoo case](https://www.odoo.com/es/blog/customer-reviews-6/revolucion-helada-helados-milky-mich-y-odoo-1314) lists modules without a strict trigger | Specific vendor page; system only | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Explicit trigger, control, size, and corroboration |
| 5 | Raloy Lubricantes | [Odoo/Fixdoo partner page](https://www.odoo.com/partners/fixdoo-solutions-5328547) lists modules only | Vendor partner page; system only | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Explicit trigger, current size, control, and corroboration |
| 6 | Grugar Industrial | [Supplier PDF](https://www.grugar.com.mx/grugar/descargables/proveedores.pdf) requires PO/warehouse-entry references, price/quantity match, invoice cutoff, and scheduled payment | Primary static supplier PDF | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Mexican control, size, and Odoo corroboration |
| 7 | Pinturas Adhler | [Transient accounting role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-en-los-reyes-la-paz-estado-de-mexico-en-la-paz-FC6C895428CF76B461373E686DCF3405) covers AP/AR, reconciliation, and close; [identity page](https://pinturasadhler.com.mx/index.html) | Transient job board plus primary identity | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Durable trigger source, control, and size |
| 8 | MEXDEN | [Transient accounting role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-auxiliar-contable-en-san-pedro-tlaquepaque-97BF1E9E5102644E61373E686DCF3405) covers ERP, reconciliation, entries, and invoicing; [identity page](https://mexden.com/) | Transient job board plus primary identity | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Durable trigger source, control, size, and ERP identification |
| 9 | ODISA | [Odoo case](https://www.odoo.com/es_ES/blog/customer-reviews-6/odisa-y-odoo-transforman-el-sector-de-maquinaria-para-concreto-1161) states automatic POs by project need | Specific vendor case page | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and independent corroboration |
| 10 | ENVESTA | [Transient billing/collections role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-facturacion-y-cobranza-en-toluca-fd9478a34dc83bc761373e686dcf3405); [identity page](https://envesta.com.mx/) | Transient job board plus primary identity | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Durable trigger source, control, and size |
| 11 | Grupo Formex | [Transient job index](https://mx.indeed.com/q-formex-empleos.html); [identity](https://formex.com.mx/); [privacy notice](https://formex.com.mx/wp-content/uploads/2022/10/Aviso-de-Privacidad-Grupo-Formex-oct22.pdf); [supplier portal](https://proveedores.grupoformex.mx/login) | Transient job source plus primary identity/privacy/portal | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Legal grain, durable trigger, control, size, and system corroboration |
| 12 | Poly Rafia | [Liconsa contract with Poly Rafia](https://repositorio.liconsa.gob.mx/files/DC/SADM/2022/CONTRATOS%201/CADQ-635-2022%20POLIESTER%20BOPP%20POLY%20RAFIA%20VP%202022.pdf) records monthly orders to Poly and requires Poly, for each delivery, to submit an invoice package, electronic CFDI/PDF/XML, and corrections/resubmission when required. This is Poly-side recurring order/invoice evidence; it does not attribute Liconsa AP controls to Poly. Poly’s live [first-party company page](https://www.polyrafia.com.mx/nosotros/) explicitly states its Sistema de Gestión Integral and technology/management-process posture; this is a first-party integrated-management-system/technology signal, not ERP evidence. | Government contract for recurring supplier-side trigger plus first-party system/change page | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and ERP identification |
| 13 | Química Delta | [Government audit PDF](https://www.asf.gob.mx/Trans/Informes/IR2023c/Documentos/Auditorias/2023_0427_a.pdf) documents orders, payment files, and CFDI; [acquisition announcement](https://corporate.brenntag.com/en/media/news/brenntag-announces-the-acquisition-of-quimica-delta-in-mexico-growing-its-market-presence-with-access-to-important-tollgate-infrastructure.html) | Government audit plus corporate acquisition notice | YES | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Post-acquisition control adjudication, system signal, and size |
| 14 | Promaquina | [Primary privacy notice](https://promaquina.com/documents/Aviso%20de%20privacidad.pdf) states ongoing orders/invoices; [technology page](https://promaquina.com/edificios-prefabricados.html) | Primary privacy and technology pages | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and SAP Business One corroboration |
| 15 | IPISA | [Primary privacy policy](https://ipisa.com.mx/politica-de-privacidad/) states invoicing, collections, provider payments, orders, and invoices; [first-party store](https://tienda.ipisa.com.mx/website/info) | Primary privacy and first-party application | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and continued homonym separation |
| 16 | DIFATSA | [Primary site](https://www.difatsa.mx/) plus [SAP vendor article](https://news.sap.com/latinamerica/2020/02/grupo-xcaret-grupo-gayosso-y-difatsa-avanzan-en-transformacion-digital/) establish identity/model and system, not a strict trigger | Primary identity plus vendor system page | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Exact entity/domain binding, trigger, control, size, and corroboration |
| 17 | Alianza Eléctrica | [Primary privacy notice](https://alianzaelectrica.com/Alianza-Electrica-aviso-de-privacidad.php) plus [SAP/Xamai PDF](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) support invoice workflow and SAP Business One | Primary privacy plus static vendor PDF | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Affiliate boundary, control, size, and corroboration |
| 18 | Azerty de México | [Primary FAQ](https://azerty.com.mx/preguntas-frecuentes/) and [static catalog](https://azerty.com.mx/wp-content/uploads/Catalogo2024.pdf) support authenticated orders/invoices | Primary FAQ and static catalog | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and ERP identification |
| 19 | YINSA | [Primary terms](https://www.yinsa.com.mx/terminos-condiciones.html) require invoice plus reviewed/signed PO before payment | Primary terms page plus vendor system corroboration | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Control, size, and SAP Business One corroboration |
| 20 | Nobazul | [Primary privacy PDF](https://nobazul.com/wp-content/uploads/2025/08/NOBAZUL_Aviso-de-Privacidad-Integral-may25.pdf) and [site](https://nobazul.com/) support verified identity/model, not a strict trigger | Primary identity/model only | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Mieles Campos Azules mapping, trigger, system, control, and size |
| 21 | UniSeal | [SAP customer document](https://www.sap.com/documents/2025/06/589653ff-0c7f-0010-bca6-c68f7e60039b.html) plus [primary site](https://www.uniseal.com.mx/) establish system/model, not a strict trigger | Specific vendor document plus primary identity | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Explicit trigger, control, size, and corroboration |
| 22 | DIDCOM | [DIDCOM privacy notice](https://didcom.com.mx/wp-content/uploads/2021/09/Aviso-de-Privacidad-Didcom.pdf) names Grupo Tecnológico DIDCOM SA de CV and didcom.com.mx and covers invoice/payment communications, billing management, and collections. | Primary static privacy PDF; recurring trigger | YES | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | System signal, control, and size |
| 23 | JAKO | [SAP/Xamai PDF](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) states slow invoicing/accounting/reporting/financial processes; [primary identity](https://www.jako.mx/nosotros) | Static vendor PDF plus primary identity | YES | IN | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Current size, control, and independent corroboration |
| 24 | Ah Cacao | [Odoo case](https://www.odoo.com/es/blog/customer-reviews-6/sabiduria-ancestral-y-el-poder-del-cacao-el-salto-digital-de-ah-cacao-con-odoo-1755) lists modules only | Specific vendor page; system only | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Operating-model adjudication, trigger, control, size, and corroboration |
| 25 | IMAG Organics | [FDA primary PDF](https://www.fda.gov/media/158262/download) supports identity/model; [SAP vendor article](https://news.sap.com/latinamerica/2022/12/sap-apoya-a-empresas-agaveras-en-su-automatizacion-y-procesos-en-la-nube/) supports system only | Government primary identity/model plus vendor system page | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Domain confirmation, trigger, control, size, and corroboration; prior acronym-only identity gap repaired |
| 26 | Grupo Pochteca | [Primary supplier manual](https://mexico.pochteca.net/wp-content/uploads/2025/04/manual-proveedores-2025.pdf) states PO, invoice, match, payment, and approval | Primary static supplier manual | YES | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Direct current size-band evidence |
| 27 | Maison Paulette | [SAP customer document](https://www.sap.com/documents/2025/11/da8443d1-2a7f-0010-bca6-c68f7e60039b.html) states monthly close and retail system | Specific vendor customer document | YES | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | None for current outside-wedge DQ; retain human review |
| 28 | Super Tiendas Esquer | [Audited Chihuahua procurement report](https://ihacienda.chihuahua.gob.mx/tfiscal/indtfisc/InformeTecnicoASE2021.pdf) records one audited procurement involving Super Tiendas Esquer, not a recurring workflow. A trade domain was observed, but its legal-entity mapping remains unresolved. | Government audit; one procurement only | NOT COUNTED | OUT | 2026-07-26 | GPT-5.6 Sol research lanes | Pending | Legal entity/domain mapping; recurring trigger and system only if ever reconsidered |

## Interpretation and operating boundary

The durable count of 15 clears the numerical >=15 gate exactly, pending human review. The conservative set of 11 is a narrower working subset, not a qualification count. Existing E1, E2, Hold, and DQ dispositions do not change.

This ledger does not create pipeline, traction, customers, or revenue evidence. It does not clear the 50-qualified-account gate or authorize a second batch, named-person or personal-contact research, CRM creation or mutation, drafting, outreach, sends, qualification, account activation, deployment, merge, access change, archival, or deletion.

## Related

- [Account-discovery snapshot](../external-sources/ae-account-discovery-snapshot-2026-07-26.md)
- [50-account pilot seed](./ae-50-account-pilot-seed-2026-07-26.md)
- [Account-discovery evidence rules](../articles/account-discovery-evidence-rules.md)
