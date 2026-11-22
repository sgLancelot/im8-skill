# Portal Map — info.standards.tech.gov.sg

> **Update, 10–19 Nov 2026:** two new SSP templates for SaaS (Low-Risk SaaS, 50 controls; Medium-Risk SaaS, 54). New cybersecurity family SA (SaaS Security). New Organisational section with Third Party Management (`/control-catalog/organisational/tp/`, TP-4 only). Generative AI controls replaced: GA-1…GA-8 retired, now GA-9…GA-23. New controls AC-18…AC-24 and DP-10. The existing cloud, on-prem, sandbox and DSS baselines kept the same controls and levels.

> **Update, 19 Oct 2026:** Generative AI moved to its own catalog section (`/control-catalog/gen-ai/ga/`; the old URL redirects). New control IS-15 added to the four main cyber baselines (now 118/118/138/104 controls). Current page dates and counts live in `catalog/SNAPSHOT-PORTAL.md`.

Complete map of the authoritative portal (crawled 2026-08-11 from sitemap.xml; ~50 URLs). Per-page "last updated" dates shown where the page displays one. Fetch the live page before answering — dates move.

## Top-level pages

| URL | Page | Contents | Updated |
|---|---|---|---|
| `/` | Home | Tagline: simplifying ICT&SS policies for "rapid, cost effective and innovative systems with right-fit risk controls" | (site footer 30 Jul 2026) |
| `/about/` | About | Reform purpose; risk-based rationale; differentiated treatment by risk impact level | 26 Mar 2026 |
| `/ssp/` | System Security Plan | What SSPs are; Level 0/1/2 summary; links to all 10 templates | 10 Nov 2026 |
| `/control-catalog/` | Control Catalog | Central pool of controls; hygiene requirements vs guidelines; OSCAL mention | 10 Nov 2026 |
| `/glossary/` | Glossary | Official Level 0/1/2 definitions; Agency Users, Public Users, Digital Service, Host, Transactional/Non-Transactional | 25 Oct 2026 |
| `/highlights/` | Highlights | External recognition: ThoughtWorks Tech Radar (Nov 2025), NIST OSCAL workshop (2025) | 12 May 2026 |
| `/contact-us/` | Contact Us | info@tech.gov.sg; feedback form go.gov.sg/ictpolicy | 16 Apr 2026 |
| `/search/` | Search | Site search | — |
| `/archive/` | Archive | Retired pages (`/archive/about-ssp/`, `/archive/cybersecurity-1/`, `/archive/dss-1/`) — do NOT cite as current | 26 Mar 2026 |

## SSP template pages (10)

| URL | System category | Sensitivity ceiling | Families / ~controls | Notes | Updated |
|---|---|---|---|---|---|
| `/ssp/low-risk-cloud/` | Generic cloud (3rd-party CSP) | Restricted / Sensitive Normal | 13 / 118 | Baseline reference; largest families LM (18), AS (15) | 19 Nov 2026 |
| `/ssp/medium-risk-cloud/` | Generic cloud | Confidential / Sensitive High | 13 / 118 | Same family set as low-risk; differs by level/parameter assignments | 19 Nov 2026 |
| `/ssp/high-risk-cloud/` | High-Risk Cloud **CII** | Confidential / Sensitive High | 15 / 138 | Adds HR and RS families; note: CII owners to inform CSA before cloud migration | 19 Nov 2026 |
| `/ssp/low-risk-on-premises/` | Generic on-premises | Restricted / Sensitive Normal | 13 / 104 | DC (Datacentre) replaces CS (Container Security) | 19 Nov 2026 |
| `/ssp/low-risk-saas/` | Generic system hosted on the cloud by a third-party service provider (SaaS) | Restricted / Sensitive Normal | 10 / 50 | New in the 10–11 Nov 2026 release. Includes the SA (SaaS Security) family, 11 GA controls and TP-4 | 19 Nov 2026 |
| `/ssp/medium-risk-saas/` | Same as above, medium risk | Confidential (Cloud-Eligible) / Sensitive High | 11 / 54 | New in the 10–11 Nov 2026 release. The low-risk SaaS set plus CK-2, CK-3, PM-8 (Level 0) and SA-5 | 19 Nov 2026 |
| `/ssp/gen-ai/` | System using generative AI models | Up to Confidential / Sensitive High | 2 / 15 (14 GA + DP-8) | An overlay, not standalone. GA-1…GA-8 were retired on 11 Nov 2026 and replaced by GA-9…GA-23 (GA-10, external AI SaaS, sits in the SaaS baselines instead). Level 0: GA-9 external AI API data classification, GA-11 self-hosted model environments, GA-21 beta-status disclaimers, GA-23 risk acceptance and approval before closed beta/deployment | 11 Nov 2026 |
| `/ssp/dss-high/` | Digital Services (High Impact): ≥1M visits/year (per WOGAA) | n/a (usability/accessibility) | 9 / ~92 | WCAG families dominate | 19 Oct 2026 |
| `/ssp/dss-others/` | Digital Services (Others): <1M visits/year | n/a | 9 / ~92 | Same families; differs by level assignments | 19 Oct 2026 |
| `/ssp/sandbox/` | Pilot sandbox system | Restricted / Sensitive Normal | 13 / 117 | Pilot template | 19 Nov 2026 |

Every SSP page states (verbatim): "Agencies are to customise this template to create their own system-specific System Security Plan or use it as a default System Security Plan."

## Cybersecurity control-family pages (17)

Hub: `/control-catalog/cybersecurity/` (updated 26 Mar 2026). Each family page publishes full control text: Statement, Recommendations/Guidance, Risk Statement. Pattern: `/control-catalog/cybersecurity/<family>/`

| Code | Family | Code | Family |
|---|---|---|---|
| ac | Access Control (AC-1…16, AC-18…24) | is | Infrastructure Security |
| as | Application Security | lm | Logging & Monitoring |
| br | Backup & Recovery | ns | Network Security |
| ck | Cryptography | pm | Security Programme Management |
| cs | Container Security | rs | Resiliency |
| dc | Datacentre | sc | Software Supply Chain |
| dp | Data Protection | sd | Secure Development |
| sa | SaaS Security (new, 10 Nov 2026) | st | Security Testing |
| hr | Human Resource | | |

## Generative AI section

Hub: `/control-catalog/gen-ai/` (19 Oct 2026). Family page `/control-catalog/gen-ai/ga/` (11 Nov 2026): GA-9…GA-23. GA-1…GA-8 no longer exist.

## Organisational section

Hub: `/control-catalog/organisational/` (11 Nov 2026), "Controls that are applicable to organisation-level". Family page `/control-catalog/organisational/tp/` (10 Nov 2026): Third Party Management, currently TP-4 only.

## DSS control-family pages (9)

Hub: `/control-catalog/dss/` (updated 26 Mar 2026). "Sets the baseline for usability and accessibility across all Singapore Government digital services"; incorporates WCAG A and AA. Pattern: `/control-catalog/dss/<family>/`

Families: `bd` (e.g., BD-1…9), `pr`, `tx`, `tl`, `uu`, `wo`, `wp`, `wr`, `wu`.

## Companion repo — github.com/GovTechSG/tech-standards

- `catalogs/im8-reform.json` — OSCAL catalog, title "Instruction Manual 8 Reform"; version `2025.05.13`; 137 controls in 15 families (lacks the GA, HR, RS and SA families; its `tp` controls are numbered differently from the portal: its TP-4 "Attestation Report Review" and TP-6 "Supplier Assessments and Reviews" have the same titles and statements as the portal's SA-5 and SA-1, while the portal's TP-4 is a different control).
- `profiles/{low,medium}-risk-level-{0,1,2}.json` — OSCAL profiles importing the catalog by control ID (low-risk: L0=6, L1=86, L2=35; medium-risk: L0=26, L1=73, L2=25).
- MIT License, © 2024 Government Technology Agency of Singapore. No releases/tags; versioning via catalog metadata and commit messages.
- **Lag warning:** repo (2025.05.13, last commit Sep 2025) trails the portal (pages updated through Nov 2026; repo not updated since Sep 2025). Portal wins on conflict.

## Change-detection signals (for the tracker, v2)

- Portal: per-page "Last updated" stamps; site-wide footer date; sitemap.xml for page inventory. No public changelog — diffing page content is the mechanism.
- Repo: catalog `metadata.version` / `last-modified`; per-control `published` and `last-modified` props; commit messages encode releases.
