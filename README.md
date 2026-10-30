# SAP SCM Week 5 — Supply Chain Integration and Collaboration

**Internship assessment | Hrudhai Prem Kumar | 22 October 2026**

## Six-Assessment Portfolio Navigation

This assessment is part of my six-assessment SAP SCM internship portfolio. The series is structured as one connected learning journey from network planning through performance improvement.

| Week | Assessment | Repository |
|---|---|---|
| 1 | Supply Chain Network Planning | [Open Week 1](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Supply-Chain-Network-Planning) |
| 2 | Master Data & Inventory Optimization | [Open Week 2](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Master-Data-Inventory-Optimization) |
| 3 | Logistics & Distribution Network Design | [Open Week 3](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Logistics-Distribution-Network-Design) |
| 4 | Production Planning & Scheduling Analysis | [Open Week 4](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Week4-Production-Planning-Scheduling-Analysis) |
| 5 | Supply Chain Integration & Collaboration | [Open Week 5](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Week5-Supply-Chain-Integration-Collaboration) |
| 6 | Performance Evaluation & Continuous Improvement | [Open Week 6](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Week6-Performance-Evaluation-Continuous-Improvement) |

**Central portfolio hub:** [SAP-SCM-Internship-Portfolio](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Internship-Portfolio) — the central index for the complete series.



This repository contains a documented, illustrative supply-chain integration case study for the fictional Deccan Harvest Foods Pvt. Ltd. It examines how procurement, supply planning, production, inventory, quality, warehouse operations, transportation, sales, and external partners should exchange reliable status information when a supplier commitment changes.

## Project objectives

- Map the integration touchpoints across MM/procurement, PP and PP/DS planning, inventory management, QM, SD, EWM, TM, and external suppliers/carriers.
- Establish ownership and validation rules for master data and business documents.
- Work through a 24-hour packaging-material delay and show the dependent planning and delivery decisions.
- Distinguish a legacy SAP APO landscape using CIF from an SAP S/4HANA landscape where PP/DS may be embedded.
- Define monitoring, KPIs, risk controls, validation tests, and a staged improvement roadmap.

## Scenario and worked numbers

The case uses three fictional 500-gram millet-based ready-to-cook products with total weekly demand of **138.5 tonnes**.

| Measure | Illustrative value |
|---|---:|
| Packaging conversion assumption | 2,000 pouches per finished tonne |
| Total pouch requirement | 277,000 pouches |
| Opening pouch stock | 215,000 pouches |
| Supplier receipt due at start of planning week | 62,000 pouches |
| Production volume supported by opening pouch stock | 107.5 tonnes |
| Temporary output coverage gap if the receipt is delayed | 31.0 tonnes equivalent |
| Opening-stock share of total pouch requirement | 77.6% |
| Nominal packaging capacity | 145 tonnes/week |
| Packaging capacity after the modeled changeover allowance | 141.25 tonnes/week |
| Headroom against 138.5 tonnes of demand, when all material is available | 2.75 tonnes |

The scenario assumes one usable pouch per saleable 500-gram pack and is a simplified illustration. Real SKU-specific printed pouches, labels, bills of material, scrap factors, stock status, and unit conversions must be validated separately.

## Repository contents

- **docs/** — the final Word assessment, supporting case analysis, validation/risk register, and a standalone portal description.
- **diagrams/** — editable Mermaid diagrams for the target integration landscape, supplier-delay workflow, and exception management.
- **README.md** — project overview, worked calculations, and navigation.

## SAP SCM topics covered

- Legacy SAP APO and ERP integration using CIF where applicable.
- SAP S/4HANA PP/DS as an alternative landscape, subject to the deployed product/version.
- Master-data ownership and validation for material, supplier, location, unit of measure, production structure, resource, order, stock/quality status, and delivery/freight objects.
- End-to-end event propagation, acknowledgements, queue monitoring, idempotent retries, reconciliation, and business exception ownership.
- KPI examples: event propagation, planning reassessment, master-data first-pass validity, warehouse readiness, carrier ETA acknowledgement, order OTIF, and reconciliation accuracy.

## Review order

1. Open the final Word report in **docs/** for the full assessment.
2. Read **docs/integration-case-analysis.md** for the numerical example, event timeline, data ownership, and KPI definitions.
3. Read **docs/risk-and-validation.md** for the ten main risks and the twelve proposed integration test cases.
4. Review **diagrams/** for the editable architecture and workflow logic.
5. Use **docs/portal-submission-description.md** as a copy-ready summary for the internship portal.

## Public context and limitations

The report cites APEDA's Annual Administrative Report 2024–25 for public context on India's cereal-preparation export category. The report notes export value of USD 842 million in FY 2023–24 and USD 934 million in FY 2024–25, with reported growth of 10.92%. This sector context is not a demand forecast for the fictional business.

All company-specific demand, inventory, supplier-delay, capacity, KPI target, timeline, and dashboard examples are illustrative. They are not represented as live SAP output, completed production configuration, or executed integration tests. Any real implementation must confirm the SAP release, deployed components, integration technology, interfaces, master data, authorizations, and business controls.

## Portfolio Data Alignment

This assessment is part of a connected learning sequence, but retains its own scenario scope, assumptions, units, and reporting period. Figures should not be combined with another assessment unless the population, time window, units, KPI definitions, and scenario basis have first been reconciled. See the [Portfolio Data and Comparability Guide](https://github.com/hrudhaipremkumarpatwari/SAP-SCM-Internship-Portfolio/blob/main/PORTFOLIO_DATA_GUIDE.md) for the cross-project map and comparison checklist.
