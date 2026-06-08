# ICT Risk Management Portfolio — Musterbank GmbH (DORA)

**Shingirai Marenga** · ISO 27001 Lead Auditor · CISM · CISSP · ICT Risk Management Professional

> A practical, end-to-end ICT risk management portfolio built to demonstrate applied expertise in DORA compliance, ISO 27001:2022, BaFin regulatory requirements, and German banking risk frameworks. All work uses a fictional regulated entity — **Musterbank GmbH** — as a realistic portfolio vehicle.

---

## About This Portfolio

This repository contains a set of interconnected, hiring-manager-ready deliverables covering every major dimension of ICT risk management for a BaFin-regulated German credit institution. The portfolio was built to demonstrate **practical, applied knowledge** rather than theoretical familiarity — using real regulatory thresholds, BaFin-specific terminology, and cross-referenced findings across all documents.

Every artefact is consistent with the others. Risk ratings, control effectiveness scores, gap descriptions, and remediation actions are identical across the ICT Risk Register, Gap Analysis, and Capstone Scenario. This reflects how these documents would be used in a real programme of work.

**Regulatory and framework coverage:**

| Framework | Application |
|---|---|
| DORA (EU) 2022/2554 | Primary regulation — all five pillars |
| ISO 27001:2022 | ISMS controls, risk assessment methodology |
| ISO 27005 / NIST SP 800-30 | Risk scoring model and CE% methodology |
| BaFin BAIT 2021 | IT governance, incident management, outsourcing |
| MaRisk AT 7.2 / AT 7.3 / AT 9 | IT operations, BCM, outsourcing |
| §25b KWG | Material outsourcing, Auslagerungsregister |
| DSGVO / GDPR | Data protection obligations |
| NIS2 (EU) | Applicability assessment and overlap mapping |
| EBA / ESMA ITS & RTS | Register of Information, incident reporting templates, TLPT |

---

## Portfolio Deliverables

### 1. DORA ICT Risk Register — Musterbank GmbH

**File:** `DORA_ICT_Risk_Register_Musterbank_v4.xlsx`

A five-sheet Excel workbook covering 15 ICT risks across all five DORA pillars. Built to be auditor-ready and defensible to BaFin.

**Sheets:**
- **Overview** — Executive dashboard with live COUNTIF/AVERAGEIF formulas pulling risk counts, KRI breach monitoring, and pillar breakdown from the register
- **ICT Risk Register** — Full 15-risk inventory with gross risk (L×I), control effectiveness %, residual risk score, required management action, KRI current value vs breach threshold vs risk tolerance, DORA article references, RTO/RPO targets, and BaFin notification deadlines
- **Risk Matrix** — Two 5×5 heat maps (gross vs residual), colour-coded CE% adequacy scale, and KRI vs tolerance monitoring summary
- **DORA Gap Analysis** (sheet) — 34 requirements across 6 categories mapped against current controls
- **Vendor Risk (Art. 28)** — 8 ICT TPPs assessed against DORA third-party obligations

**Risk scoring model (ISO 27001 / NIST SP 800-30 aligned):**

| Element | Scale |
|---|---|
| Likelihood | 1–5 |
| Impact | 1–5 |
| Gross Risk | L × I |
| Control Effectiveness | 0% / 25% / 50% / 75% / 90% / 95% (capped — residual risk always remains) |
| Residual Risk | Gross × (1 − CE%) |
| Rating bands | 1–5 Low · 6–10 Medium · 11–15 High · 16–25 Critical |

**Required actions by rating:**

| Rating | Action |
|---|---|
| Critical (16–25) | Immediate escalation to senior management / Risk Committee |
| High (11–15) | Treatment plan mandatory — senior management review |
| Medium (6–10) | Management review required — active monitoring |
| Low (1–5) | Accept and monitor — annual review sufficient |

**Key design decisions:**
- CE capped at 95% — a 0% residual risk is never realistic under ISO 27001 or NIST SP 800-30
- Gross likelihood and impact are calibrated to reflect real severity — concentration risk (R-003) and BCP gap (R-015) are both scored 5×5 = 25 Critical
- KRI current values are realistic (e.g. EDR 62%, TLPT: never conducted, notification time: 5.2h vs 4h threshold) rather than placeholder text
- Cross-sheet consistency enforced: every risk rating, description, and KRI in the register matches the Gap Analysis and Vendor Risk sheet exactly

---

### 2. DORA Gap Analysis — Musterbank GmbH

**File:** `DORA_Gap_Analysis_Musterbank_v2.pdf`

A formal gap analysis report in PDF format, structured as it would be presented to a Risk Committee or BaFin supervisory review. Produced programmatically using Python / ReportLab with precise layout control.

**Coverage:** 34 requirements across 6 categories:

| Category | Requirements | Critical Findings |
|---|---|---|
| Pillar 1 — ICT Risk Management | 8 | 2 (risk appetite, BCP) |
| Pillar 2 — Incident Mgmt & Reporting | 5 | 2 (classification, 4h notification) |
| Pillar 3 — Resilience Testing | 5 | 2 (TLPT, BCP/DRP untested) |
| Pillar 4 — Third-Party Risk Management | 7 | 2 (CIF, Register of Information) |
| Pillar 5 — Information Sharing | 3 | 0 |
| Cross-cutting — Governance & Controls | 7 | 1 (CIF identification) |

**Format features:**
- Dark blue / mid blue / amber / red / purple colour scheme matching the Risk Register
- Status badges: ✔ Met · ◑ Partial · ✘ Missing
- Priority badges: Critical (purple) · High (red) · Medium (amber) · Low (green)
- BAIT / MaRisk / §25b KWG cross-references on every pillar
- Cross-references to Risk Register risk IDs and gross scores (e.g. "consistent with R-015, Gross 25 — Critical; CE 0%")
- Remediation roadmap with 16 prioritised actions including Risk Register cross-references
- 18mm margins throughout — no content overlap

**New gaps added vs original:**
- CIF identification (prerequisite for Register of Information — Critical)
- ICT risk appetite and tolerance statement (Art. 6(8) — Critical)
- ICT third-party risk policy (Art. 28(1) — High)
- DORA management body accountability (Art. 5)
- Digital operational resilience strategy (Art. 6(7))
- DORA training obligations (Art. 13)
- NIS2 applicability assessment
- Cryptographic key management (Art. 9(2))
- IAM controls (Art. 9, cross-referenced to R-008)

---

### 3. DORA Capstone Scenario — Cloud-Hosted Payment Platform (AWS)

**File:** `DORA_Capstone_Solution_Musterbank_v3.pdf`

A full DORA ICT risk management framework applied to a new cloud-hosted SEPA Instant payment platform, built end-to-end using AWS as the sole infrastructure provider. Produced as a structured, 10-page PDF with colour-coded tables and section headers.

**Scenario:** Musterbank GmbH is launching a cloud-hosted instant payment platform on AWS (eu-central-1 primary, eu-west-1 DR) to meet PSD2 SEPA Instant requirements. The platform is a CIF. The document demonstrates all DORA obligations before go-live, including the formally declared AWS concentration risk.

**Eight sections:**

| Section | Coverage |
|---|---|
| 1. CIF Classification | Art. 3(22), Art. 6(1), BAIT §2, §25b KWG — three-criterion CIF assessment |
| 2. ICT Asset Inventory | Art. 8, BAIT §4 — AWS-native services by layer (EC2/ECS, RDS Multi-AZ, S3, KMS, VPC, GuardDuty, CloudTrail, Direct Connect, Route 53) with criticality ratings |
| 3. Protective Controls | Art. 9–10, BAIT §6–§8 — IAM (CyberArk PAM, AWS IAM, YubiKey MFA), cryptography (KMS HSM, TLS 1.3, AES-256), network isolation (WAF, Shield Advanced, VPC), vulnerability management (Inspector, Patch Manager, DAST), logging (CloudTrail, GuardDuty, Splunk) |
| 4. Business Impact Analysis | Art. 11(6), MaRisk AT 7.3 — RTO 1h / RPO 5min / MTPD 4h anchored to SEPA Instant rules and Art. 19 notification threshold |
| 5. Continuity & Recovery Planning | Art. 11, BAIT §9 — BCP, DRP (eu-central-1 → eu-west-1 failover), exit plan (Auslagerungsregister) |
| 6. ICT Third-Party Risk (AWS as CTPP) | Art. 28–30, §25b KWG, RTS Mandates #7 and #9, ITS Mandate #8 — pre-contract due diligence, **all 8 Article 30 mandatory contractual clauses verified**, sub-processor chain, Auslagerungsregister entry, Register of Information, and formal AWS concentration risk declaration |
| 7. Resilience Testing Programme | Art. 24–27, BAIT §8(3), RTS Mandate #6 — 7 test types including Amazon Inspector, DR failover test, TLPT (TIBER-EU), AWS Config compliance, BCP tabletop |
| 8. Five-Step Risk Assessment | Art. 8–13, ISO 27001 Cl. 6.1, NIST SP 800-30 — threat/vulnerability mapping, inherent risk scoring, CE-adjusted residual risk, board risk appetite decision with go/no-go recommendation |

**Article 30 contractual clause coverage (Section 6b):**
All 8 DORA Art. 30 mandatory clauses verified in the Musterbank–AWS Enterprise Agreement:
service description and SLAs · availability and continuity obligations · security and confidentiality · incident management assistance · audit and inspection rights (extending through sub-processor chain per RTS Mandate #9) · subcontracting conditions and change notification · termination rights and exit assistance · CTPP oversight cooperation

**AWS concentration risk (formally declared):**
- 70% of critical ICT services on a single provider — exceeds DORA Art. 29 guidance
- Formal concentration risk statement submitted to BaFin (BaFin cloud outsourcing Merkblatt)
- Cross-referenced to Risk Register R-003 (Gross 25 — Critical; CE 25%)
- Mitigation: multi-cloud roadmap (Azure EU pilot Q3 2026); target ≤55% concentration by end 2027

**Go/No-Go recommendation:** Platform NOT promoted to production until 4 TREAT items closed — API WAF full deployment, dev/test data masking, PAM 100%, DR failover test passed.

---

## Cross-Document Consistency

A key design principle of this portfolio is that findings are **traceable across all three documents**. The table below shows selected cross-references:

| Risk | Register ID | Gross Score | Gap Analysis | Capstone |
|---|---|---|---|---|
| Cloud concentration (AWS) | R-003 | 25 — Critical · CE 25% | Pillar 4 — CIF/concentration | Section 2, 6c — declared, Art. 29 |
| BCP/DRP untested 18 months | R-015 | 25 — Critical · CE 0% | Pillar 3 — BCP/DRP ✘ Missing | Section 5 — test programme |
| TLPT never conducted | R-004 | 16 — Critical · CE 0% | Pillar 3 — TLPT ✘ Missing | Section 7 — TLPT scoped |
| Incident notification >4h | R-002 | 16 — Critical · CE 25% | Pillar 2 — 4h notification ✘ Missing | Section 8 — risk appetite |
| Vendor exit plan (Temenos) | R-010 | 20 — Critical · CE 25% | Pillar 4 — exit plans ✘ Missing | Section 5 — exit plan structure |
| Mobile API vulnerability | R-009 | 16 — Critical · CE 50% | Pillar 3 — testing ◑ Partial | Section 3 — DAST gap |

---

## Technical Production

| Deliverable | Tooling |
|---|---|
| ICT Risk Register | Python / openpyxl — programmatic Excel generation with live cross-sheet formulas |
| Gap Analysis PDF | Python / ReportLab — precise A4 layout, 18mm margins, custom header/footer |
| Capstone PDF | Python / ReportLab — 10-page structured report with colour-coded tables |

All PDFs are produced programmatically for layout precision and reproducibility. Formatting is not post-processed in Word or Acrobat — the Python source files are the single source of truth.

---

## Credentials

- **ISO 27001 Lead Auditor** — information security management system audit and implementation
- **CISM** (Certified Information Security Manager) — ISACA
- **CISSP** (Certified Information Systems Security Professional) — ISC²
- **ICT Risk Management Professional** — regulation-dora.eu / DORA Academy (in progress)

---

## Regulatory Disclaimer

All entities, scenarios, risk scores, and findings in this portfolio are fictional and created for professional portfolio demonstration purposes. Musterbank GmbH does not exist. DORA article references are based on Regulation (EU) 2022/2554 and applicable EBA/ESMA technical standards as of June 2026. Nothing in this repository constitutes legal or regulatory advice.

---

*Shingirai Marenga · Salzgitter, Germany · June 2026*
*[LinkedIn](https://www.linkedin.com/in/shingiraimarenga) · [GitHub](https://github.com/shingiraimarenga/it-risk-portfolio)*
