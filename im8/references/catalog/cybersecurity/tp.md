# TP — Third Party Management

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `tp` | Controls: 6

Controls to govern the shared responsibility between organisations and a third party.

## TP-1 — Software as a Service (SaaS) Service Level Agreement

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Obtain a service level agreement with the SaaS provider.

**Guidance:** Ensure the service level agreement covers uptime, response times, downtime notifications, support channels (such as email or phone), and security resources (access logs, incident reports, incident logs to aid in investigations, SOC 2 Type 2 report). Regularly check for compliance to the agreement.

**Risk statement:** Without a service level agreement the availability of the Software as a Service (SaaS) system may be poorly maintained by the provider.

## TP-2 — Third Party Audit

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Conduct a(n) [type of audit] audit by an independent third-party at least every [time period (days)] day(s).

**Guidance:** The scope of the audit should cover the compliance requirements of the system owner.

**Risk statement:** Failure to conduct an independent third-party audit may reduce visibility of security weaknesses.

**Parameters:**

- `tp-2_prm_1` — type of audit (type: str) — The type of audit.
- `tp-2_prm_2` — time period (days) (type: int) — The time period in days for audit.

## TP-3 — Scope for Offshoring

**Levels:** low-risk: L1, medium-risk: not in baseline

**Statement:** Restrict offshore development to development and maintenance work.

**Guidance:** Organisation can only offshore development and maintenance works in non-production environment to third party.

**Risk statement:** Offshoring systems increases risks such as cybersecurity threats, data breaches, quality issues, and operational disruptions. Therefore, only systems with a lower risk profile should be considered for offshoring.

## TP-4 — Attestation Report Review

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Review the [audit] attestation report every [time period (days)] day(s) and ensure that outstanding exceptions or findings are remediated.

**Guidance:** The scope of the attestation report should minimally cover the risk assessment, risk mitigation, logical and physical access controls, system operations and change management and should be perfomed by an independent third party.

**Risk statement:** Without reviewing the audit report by an independent third party may pose security and compliance risks as there is no independent verification that the system meets industry standards relating to data management and security controls, which potentially lead to data breaches and reputational damage.

**Parameters:**

- `tp-4_prm_1` — audit (type: str) — The audit type.
- `tp-4_prm_2` — time period (days) (type: int) — The time period in days for report review.

## TP-5 — Qualified Offshore Development Centre

**Levels:** low-risk: L1, medium-risk: not in baseline

**Statement:** Engage offshore resources through a local third party that operates a [type].

**Guidance:** Engage offshore resources through a local third party that operates a Overseas Development Centre selected by GovTech or consult GovTech before engaging offshore resources.

**Risk statement:** Not engaging with local Third-Party operating a GovTech qualified ODC, or not engaging GovTech before engaging offshore resources can result in undesirable outcomes where Agencies interests are unprotected.

**Parameters:**

- `tp-5_prm_1` — type (type: str) — The type of offshore development centre.

## TP-6 — Supplier Assessments and Reviews

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Seek an assessment by [Assessing party] on the risks associated with suppliers or contractors before using or subscribing to the service.

**Guidance:** Submit SaaS usage via the [Request for SaaS FormSG](#dd55e2b4-1053-4ba8-9712-26b928b270ec) and the assessment outcome will be provided within 3 working days.

**Risk statement:** Failure to assess suppliers may introduce supply chain risks associated with data residency and jurisdiction.

**Parameters:**

- `tp-6_prm_1` — Assessing party (type: str) — The party conducting the assessment.
