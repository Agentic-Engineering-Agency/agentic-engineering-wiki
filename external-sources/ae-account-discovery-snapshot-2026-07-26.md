---
type: source
title: AE account-discovery snapshot — 2026-07-26
description: Point-in-time summary adjudication for 28 distinct candidate labels in the Mexican industrial wedge, its 2/7 comparison cohort, enterprise calibration set, and measured trigger-evidence gate.
source_url: local://ae-account-discovery/2026-07-26
date_fetched: 2026-07-26
observed_at: 2026-07-26
preservation: text-only
source_type: multi-provider-and-live-public-web-snapshot
tags:
  - source
  - immutable
  - layer-ingest
  - sales
  - gtm
  - accounts
  - mexico
  - 2026-07-26
---
## Capture scope and limits

This point-in-time summary adjudication consolidates company-level public evidence and the corrected 2026-07-26 discovery-layer review for AE-369. The primary cohort contains 28 distinct candidate labels; legal-entity/domain dedup remains pending. It is not a live CRM, prospect list, qualification record, account-activation record, pipeline record, or traction record.

No personal contact data, login-gated data, CRM writes, prospect messages, sends, deployments, access changes, archival, or deletion occurred. Unknown fields were not inferred.

## Working wedge

> Mexican-controlled industrial manufacturers/distributors, 51–1,000 employees, with direct recurring AP/PO/invoice/reconciliation/approval/close evidence plus ERP/system signal.

Admission requires both a recurring operational trigger and a systems signal. Company identity, Mexican control, industrial operating model, size, and legal-entity/domain dedup remain explicit gates.

## Corrected decision snapshot

| Measure | Status | Boundary |
| --- | --- | --- |
| Accounting/shared-services comparison | 2 of 7 passes | TACTIK CSC and Grupo GSG Mefintax only |
| Primary-cohort denominator | 28 distinct candidate labels | Legal-entity/domain dedup pending |
| Relative research-readiness split | 4 E1, 5 E2, 17 holds, 2 disqualifiers | 4 + 5 + 17 + 2 = 28 |
| Raw strict-trigger verdict | 18 yes, 10 unknown, 0 no | Absence was not inferred |
| Durable-trigger count | 13 yes | Four raw yes rely on transient sources; DIMECA uses a mutable vendor homepage |
| Conservative working set | 10 | Durable trigger plus industrial model, system signal, and no identified outside/control/size blocker |
| Provisional >=15 discovery threshold | NOT CLEARED | 13 durable yes < 15; segment not rejected and no second batch |
| Enterprise calibration | 3 accounts | Separate from the 28; all above 1,000 employees |

The completed [28-row trigger ledger](../research/ae-28-row-trigger-ledger-2026-07-26.md) makes the failed measurement reproducible. The provisional >=15 gate is not cleared under the current evidence contract because 13 durable YES verdicts are below 15. This does not reject the segment.

This does not clear the 50-qualified-account gate, create pipeline or traction, qualify or activate an account, or authorize a second batch, contacts, CRM work, drafting, or outreach.

## Research-readiness labels

E1 and E2 are relative research-readiness labels within this provisional cohort. They never mean qualified account, activated account, approved prospect, or permission to contact.

All four E1 packets remain medium-confidence. Three of four—DIMECA, Dysal, and Productos Helados Milky Mich—are vendor-case dependent; Grupo CIPSA has controlling direct supplier-portal evidence, while its vendor-reported SAP Fiori signal remains supplementary and uncorroborated. E2 means the evidence packet is comparatively useful but still has a named repair gate. Holds have unresolved identity, operating-model, size, trigger, systems, durability, or corroboration gates. Disqualifiers are outside the working wedge on currently cited operating-model evidence.

## Accounting/shared-services comparison

| Account | Identity and size evidence | Direct workflow and systems evidence | Disposition |
| --- | --- | --- | --- |
| [TACTIK CSC](https://tactik.net/quienes-somos.html) | Monterrey; Mexican shared services; [51–200 secondary size signal](https://mx.linkedin.com/company/tactikcsc) | [Accounts payable through portals, ERP AP/AR, and reconciliation](https://tactik.net/contabilidad.html) | Pass; comparison cohort |
| [Grupo GSG Mefintax](https://www.gsgconsultores.com.mx/wp-content/uploads/2024/06/Brochure-Grupo-GSG-Mefintax-Mayo-24.pdf) | CDMX; Mexican accounting/BPO; [51–200 secondary size signal](https://www.linkedin.com/company/gsgmefintax) | [Cash flow, reconciliation, reporting, budget control, ERP, SAP, Oracle, QuickBooks, BI, and RPA](https://www.gsgconsultores.com.mx/servicios/business-advisory-services/compartidos-integrales-shared-services/) | Pass; comparison cohort |
| [Humanitak](https://humanitak.com/) | Mexican HR/admin BPO; [11–50 secondary size signal](https://mx.linkedin.com/company/humanitak-staffing-group) | Bank reconciliation, accounting entries and reports, CFDI payroll integration | Hold; below size floor |
| [MGM Consultores](https://mgmconsultores.mx/) | Mexican back-office provider; size unknown | Banks and cash flow, accounts receivable, inventory, accounts payable | Hold; size and current-operation gate |
| [Sixcal](https://www.sixcal.com.mx/) | Mexican accounting firm; size unknown | E-invoicing and bank reconciliation; [automation article](https://www.sixcal.com.mx/articulo.php?n=112) | Hold; size gate |
| [Nominex Pro](https://www.nominexpro.com/) | Mexican payroll/accounting BPO; size unknown | [Recurring payroll](https://www.nominexpro.com/servicios-1), configurable ERP, and government integrations | Hold; size and workflow gate |
| [SCF](https://scf.mx/) | Mexican accounting consultancy; size unknown | Accounting processing, financial analysis, and treasury | Hold; size and current-stack gate |

Strict comparison yield remains 2 of 7.

## Primary-cohort summary adjudication

### E1 — strongest relative research-readiness

| Account | Preserved evidence signal | Evidence condition |
| --- | --- | --- |
| Grupo CIPSA | [Supplier portal for purchase orders, invoices, credit notes, payment dates, and complements](https://proveedores.cipsa.com.mx/) plus vendor-reported SAP Fiori signal | Medium-confidence; direct supplier portal is controlling evidence, while the SAP Fiori detail is supplementary and uncorroborated |
| DIMECA | [Tangente vendor case](https://tangentemexico.com/) covering requisitions, eight systems integrated with SAP Business One, and automatic invoicing | Medium-confidence; independently corroborate vendor case |
| Dysal | [SAP/Xamai multi-company vendor case](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) retained as the systems source | Medium-confidence; corroborate account mapping and control |
| Productos Helados Milky Mich | [Odoo customer review](https://www.odoo.com/es/blog/customer-reviews-6/revolucion-helada-helados-milky-mich-y-odoo-1314) | Medium-confidence; independently corroborate vendor case |

### E2 — provisional relative research-readiness

| Account | Preserved evidence signal | Required repair |
| --- | --- | --- |
| Raloy Lubricantes | [Odoo/Fixdoo partner case](https://www.odoo.com/es_ES/partners/fixdoo-solutions-5328547) | Cite current size evidence; independently corroborate vendor case |
| Grugar Industrial | [Supplier policy requiring invoice, purchase-order, quantity, and price match](https://www.grugar.com.mx/grugar/descargables/proveedores.pdf) plus Odoo AP signal | Refresh Mexican control and size |
| Pinturas Adhler | [Accounting role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-en-los-reyes-la-paz-estado-de-mexico-en-la-paz-FC6C895428CF76B461373E686DCF3405) covering AP/AR, reconciliation, ERP/Odoo, and close | Transient secondary job-board evidence; replace with durable direct evidence and refresh control/size |
| MEXDEN | [Accounting role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-auxiliar-contable-en-san-pedro-tlaquepaque-97BF1E9E5102644E61373E686DCF3405) covering ERP, bank reconciliation, entries, and invoicing | Transient secondary job-board evidence; replace with durable direct evidence and refresh control/size |
| ODISA | [Odoo customer review](https://www.odoo.com/es_ES/blog/customer-reviews-6/odisa-y-odoo-transforman-el-sector-de-maquinaria-para-concreto-1161) | Refresh control/size and independently corroborate vendor case |

### Holds

| Account | Preserved evidence or blocking gate |
| --- | --- |
| ENVESTA | [Billing/collections role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-analista-contable-facturacion-y-cobranza-en-toluca-FD9478A34DC83BC761373E686DCF3405) is transient secondary evidence; size remains unresolved |
| Grupo Formex | Control, size, or evidence gate remains open |
| Poly Rafia | Control, size, or evidence gate remains open |
| Quimica Delta | Control, size, or evidence gate remains open |
| Promaquina | Control, size, or evidence gate remains open |
| IPISA | [Odoo customer review](https://www.odoo.com/es_ES/blog/customer-reviews-6/ipisa-lleva-su-desempeno-a-otro-nivel-con-odoo-1171); control/size and independent-corroboration gates remain open |
| DIFATSA | Control, size, or evidence gate remains open |
| Alianza Electrica | Control, size, or evidence gate remains open |
| Azerty de Mexico | Control, size, or evidence gate remains open |
| YINSA | Control, size, or evidence gate remains open |
| Nobazul | [SAP cloud-automation case naming Mieles Campos Azules alongside IMAG Organics](https://news.sap.com/latinamerica/2022/12/sap-apoya-a-empresas-agaveras-en-su-automatizacion-y-procesos-en-la-nube/); hold because the identity mapping between Nobazul and Mieles Campos Azules remains unverified; control/size and independent corroboration also remain open |
| UniSeal | [SAP customer document](https://www.sap.com/documents/2025/06/589653ff-0c7f-0010-bca6-c68f7e60039b.html); control/size and independent-corroboration gates remain open |
| DIDCOM | [Treasury/accounting role](https://mx.computrabajo.com/ofertas-de-trabajo/oferta-de-trabajo-de-auxiliar-de-tesoreria-y-contabilidad-en-hermosillo-0B4567F4271918C961373E686DCF3405) is a transient secondary anti-bot job-board source; hold pending industrial operating-model evidence and a durable replacement |
| JAKO | [SAP/Xamai multi-company case](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) remains systems calibration; hold until old size evidence is refreshed and account mapping is corroborated |
| Ah Cacao | [Odoo customer review](https://www.odoo.com/es/blog/customer-reviews-6/sabiduria-ancestral-y-el-poder-del-cacao-el-salto-digital-de-ah-cacao-con-odoo-1755); hold pending B2B/industrial operating-model adjudication |
| IMAG Organics | [SAP cloud-automation case](https://news.sap.com/latinamerica/2022/12/sap-apoya-a-empresas-agaveras-en-su-automatizacion-y-procesos-en-la-nube/); hold pending identity mapping to “Inulina y Miel de Agave” and frozen-workflow trigger proof |
| Grupo Pochteca | [Supplier manual with internal 2024 revision](https://mexico.pochteca.net/wp-content/uploads/2025/04/manual-proveedores-2025.pdf); hold until the more-than-1,000-employee size claim is directly sourced |

### Disqualifiers

| Account | Direct evidence | Disqualifier |
| --- | --- | --- |
| Maison Paulette | [SAP customer document](https://www.sap.com/documents/2025/11/da8443d1-2a7f-0010-bca6-c68f7e60039b.html) | B2C pastry/bistro chain; outside the industrial wedge |
| Super Tiendas Esquer | [SAP/Xamai multi-company case](https://assets.dm.ux.sap.com/iedt2020/pdfs/microxamaibook.pdf) documents its retail operating model | B2C retailer; outside the industrial wedge |

## Enterprise calibration only

These accounts are not part of the 28-label primary cohort and cannot qualify under the current size ceiling.

| Account | Observable workflow signal | Calibration reason |
| --- | --- | --- |
| [Super Kiosko](https://mikiosko.mx) | [Supplier manual](https://portalproveedores.mikiosko.mx/Home/PdfUsuarios) for invoices, statements, payment complements, and ERP | More than 1,000 employees |
| [ALMER](https://www.almer.com.mx) | [Inventory, status, and billing systems](https://www.almer.com.mx/soluciones-logisticas), including ERP/WMS/SISAL/COMPRAS | More than 1,000 employees |
| [Grupo Castores](https://www.castores.com.mx) | [Payment-requisition and approval roles](https://innovacion.castores.com.mx/bolsa-trabajo/) plus [invoice reception](https://cyber.castores.com.mx/RecepcionFacturasCyber/) | More than 1,000 employees |

## Next gate — 28-row trigger ledger

Build one row for every distinct candidate label with all of these fields:

| Required field | Completion rule |
| --- | --- |
| Candidate label | Preserve the current cohort label |
| Legal entity/domain dedupe status | Explicit matched, distinct, or unknown status |
| Operating-model verdict | Industrial manufacturer/distributor, outside wedge, or unknown |
| Direct trigger verdict and rule | Yes, no, or unknown for the recurring AP/PO/invoice/reconciliation/approval/close rule |
| System signal | ERP/system evidence or unknown |
| Durable source | Direct, durable URL or local source path |
| Source class | Primary, vendor case, secondary, or transient secondary |
| Observed-at | Explicit observation date |
| Reviewer | Explicit reviewer |
| Human disposition | Explicit E1, E2, Hold, or Disqualify decision |

Only after all 28 rows carry these fields may direct-trigger “yes” verdicts be counted against the provisional >=15 discovery threshold.

## Evidence-repair priority

1. Build and review the 28-row trigger ledger before calculating any direct-trigger count.
2. Replace transient secondary job-board evidence for DIDCOM, Pinturas Adhler, and MEXDEN with durable direct sources while preserving the current URLs as provenance.
3. Refresh Mexican control and size for every E2 account; refresh JAKO’s old size evidence.
4. Independently corroborate vendor-published Odoo, SAP, SAP/Xamai, Tangente, and partner cases.
5. Complete role-only, allowed-use, duplicate, reviewer, and human-disposition fields.
6. Keep personal contact fields excluded; reject search-result snippets as evidence.

## Source method and operating boundary

Discover through CLAUT, CANIETI, ANTP, ANTAD, regional INDEX, and IMMEX lists. Verify identity and size with [DENUE](https://www.inegi.org.mx/app/mapa/denue/), [SIEM](https://siem.gob.mx/), and primary company sources. Enrich only with supplier portals, current careers, public job records, ERP cases, [PSM](https://psm.economia.gob.mx/PSM/), and public procurement. Vendor cases remain medium-confidence until independently corroborated.

This summary adjudication authorizes no personal-contact research or retention, CRM creation or mutation, drafting, outreach, second batch, qualification, account activation, sends, deployments, merges, access changes, archival, or deletion.
