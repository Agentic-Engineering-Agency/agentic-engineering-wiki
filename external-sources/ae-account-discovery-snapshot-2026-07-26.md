---
type: source
title: AE account-discovery snapshot — 2026-07-26
description: Point-in-time capture of Opus validation, NotebookLM sector selection, public company evidence, and source-method rules for AE-369.
source_url: local://ae-account-discovery/2026-07-26
date_fetched: 2026-07-26
observed_at: 2026-07-26
preservation: text-only
source_type: multi-provider-and-live-public-web-snapshot
tags: [source, immutable, layer-ingest, sales, gtm, accounts, mexico, 2026-07-26]
---
## Capture method and limits

This record combines a bounded Claude Desktop Opus 5 validation task, a bounded Gemini NotebookLM question against the existing 63-source Agentic Engineering notebook, and live public-web research through TinyFish and parallel read-only research agents.

No personal contact data, login-gated data, CRM writes, prospect messages, sends, deployments, access changes, archival, or deletion occurred. Unknown fields were not inferred.

## Opus 5 validation contract

Opus returned PASS for one internal-only experiment: build a verified, company-level 50-account candidate set for one narrow Mexican mid-market AE-services segment.

Required fields: identity/domain, headquarters, sector/operating model, size, candidate workflow, workflow evidence, decision-owner role only, trigger, systems signal, and disqualifier check.

Required evidence envelope: claim, source URL/path, observed-at time, short snippet, confidence, allowed use, account ID, model route, prompt version, reviewer, and human disposition.

Stop conditions: 50 qualified or source exhaustion; completeness below 90%; link validity below 95%; anti-fit above roughly half; any PII/login/paywall/terms issue; any Curia-fit legal account; temptation to infer; or time/token limit. Expansion to 500, contact research, outreach, CRM mutation, and marking AE-369 complete were not authorized.

## Gemini NotebookLM recommendation

Gemini selected: “Back-office accounting and financial services + payment reconciliation and invoice approval pipelines.”

Fit criteria: weekly-or-more-frequent work, clear owner, observable cost, plausible access, Mexican operations, and expected first-year value at least three times price. Disqualifiers: rare/changing workflows, diffuse ownership, unclear baseline, blocked access, and multinational/pass-through operations.

Notebook sources named: AE_Client_Deck_EN.pdf, AE_Investor_Overview_EN.pdf, and Agentic Engineering — AI-native engineering, shipped.

## Accounting/shared-services cohort

| Account | Identity/size | Workflow/system evidence | Disposition |
| --- | --- | --- | --- |
| [TACTIK CSC](https://tactik.net/quienes-somos.html) | Monterrey; Mexican shared services; [51–200](https://mx.linkedin.com/company/tactikcsc) | [“Registro de Cuentas por Pagar a través de Portales”](https://tactik.net/contabilidad.html); AP/AR in ERP and platform reconciliation | Strict pass; High |
| [Grupo GSG Mefintax](https://www.gsgconsultores.com.mx/wp-content/uploads/2024/06/Brochure-Grupo-GSG-Mefintax-Mayo-24.pdf) | CDMX; Mexican accounting/BPO; [51–200](https://www.linkedin.com/company/gsgmefintax) | [Cash-flow, reconciliation, reporting, budget control](https://www.gsgconsultores.com.mx/servicios/business-advisory-services/compartidos-integrales-shared-services/); ERP, SAP, Oracle, QuickBooks, BI, RPA | Strict pass; High |
| [Humanitak](https://humanitak.com/) | Mexican HR/admin BPO; [11–50](https://mx.linkedin.com/company/humanitak-staffing-group) | Bank reconciliation, accounting entries/reports, CFDI payroll integration | Hold: below size floor |
| [MGM Consultores](https://mgmconsultores.mx/) | Mexican back-office provider; size unknown | Banks/cash flow, AR, inventory, AP | Hold: size/current-operation gate |
| [Sixcal](https://www.sixcal.com.mx/) | Mexican accounting firm; size unknown | E-invoicing, bank reconciliation; [automation article](https://www.sixcal.com.mx/articulo.php?n=112) | Hold: size gate |
| [Nominex Pro](https://www.nominexpro.com/) | Mexican payroll/accounting BPO; size unknown | [Recurring payroll](https://www.nominexpro.com/servicios-1); configurable ERP and government integrations | Hold: size/workflow gate |
| [SCF](https://scf.mx/) | Mexican accounting consultancy; size unknown | Accounting processing, financial analysis, treasury | Hold: size/current-stack gate |

Strict yield: 2 of 7 reviewed, or 29%.

## Industrial-operations cohort

| Account | Identity/size | Workflow/system evidence | Disposition |
| --- | --- | --- | --- |
| [Grupo CIPSA](https://www.cipsa.com.mx) | Puebla; family industrial group; 201–500 | [Portal](https://proveedores.cipsa.com.mx/) supports POs, invoices, credit notes, payment dates/complements; SAP Fiori | Pass; High |
| [DIMECA](https://www.dimeca.com.mx) | Saltillo; Mexican metal/logistics; 501–1,000 | [Tangente case](https://tangentemexico.com/): requisitions plus eight systems integrated to SAP Business One; automatic invoicing | Pass; High; vendor case |
| [Grugar Industrial](https://www.grugar.com.mx) | CDMX/Edo. Méx.; manufacturing; 51–200 | [Dec-2025 policy](https://www.grugar.com.mx/grugar/descargables/proveedores.pdf) requires invoice/PO/quantity/price match; Odoo AP | Pass; High workflow, Medium control |
| [DIDCOM](https://didcom.com.mx/) | Hermosillo; Mexican technology; [51–200](https://www.linkedin.com/company/didcom) | [Role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-auxiliar-de-tesoreria-y-contabilidad-en-hermosillo-0B4567F4271918C961373E686DCF3405): ERP payment application, authorizations, reconciliation; Odoo/SAP/CONTPAQi | Pass; Medium-high |
| [Pinturas Adhler](https://www.pinturasadhler.com.mx/) | Estado de México; paint manufacturing; [51–200](https://mx.linkedin.com/company/www.pinturasadhler.com.mx) | [Role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-en-los-reyes-la-paz-estado-de-mexico-en-la-paz-FC6C895428CF76B461373E686DCF3405): AP/AR, reconciliation, ERP/Odoo, closes | Pass; Medium-high |
| [MEXDEN](https://www.mexden.com/) | Tlaquepaque; packaging; [201–500](https://mx.linkedin.com/company/mexdenoficial) | [Role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-auxiliar-contable-en-san-pedro-tlaquepaque-97BF1E9E5102644E61373E686DCF3405): ERP, bank reconciliation, entries, invoicing | Pass; Medium-high |
| [ENVESTA](https://envesta.com.mx/) | Toluca; Mexican aluminum extrusion; size unknown | [Role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-facturacion-y-cobranza-en-toluca-FD9478A34DC83BC761373E686DCF3405): payment application in ERP, billing, collections | Hold: size gate |
| [Super Kiosko](https://mikiosko.mx) | Colima; retail; 1,001–5,000; 890+ stores | [Manual](https://portalproveedores.mikiosko.mx/Home/PdfUsuarios): invoices, statements, payment complements, ERP | Hold: above size ceiling |
| [ALMER](https://www.almer.com.mx) | Zapopan; Mexican agrologistics; 1,001–5,000 | [Systems](https://www.almer.com.mx/soluciones-logisticas): inventory/status/billing; ERP/WMS/SISAL/COMPRAS | Hold: size/regulated-operation gate |
| [Grupo Castores](https://www.castores.com.mx) | León; Mexican freight; 1,001–5,000 | [Careers](https://innovacion.castores.com.mx/bolsa-trabajo/): payment requisitions, files, approval signatures; [invoice reception](https://cyber.castores.com.mx/RecepcionFacturasCyber/) | Hold: size gate |

## Source method

Discover via CLAUT, CANIETI, ANTP, ANTAD, regional INDEX, and IMMEX lists. Verify identity/size with [DENUE](https://www.inegi.org.mx/app/mapa/denue/), [SIEM](https://siem.gob.mx/), and primary company sources. Enrich with supplier portals, current careers, public jobs, ERP cases, [PSM](https://psm.economia.gob.mx/PSM/), and public procurement. Never retain personal contact fields.

Vendor case studies are medium-confidence until independently corroborated. Search-result snippets alone are rejected.
