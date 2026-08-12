# Portal Map — info.standards.tech.gov.sg

Complete map of the authoritative portal (crawled 2026-08-11 from sitemap.xml; ~50 URLs). Per-page "last updated" dates shown where the page displays one. Fetch the live page before answering — dates move.

## Top-level pages

| URL | Page | Contents | Updated |
|---|---|---|---|
| `/` | Home | Tagline: simplifying ICT&SS policies for "rapid, cost effective and innovative systems with right-fit risk controls" | (site footer 30 Jul 2026) |
| `/about/` | About | Reform purpose; risk-based rationale; differentiated treatment by risk impact level | 26 Mar 2026 |
| `/ssp/` | System Security Plan | What SSPs are; links to all 8 templates | 26 Mar 2026 |
| `/control-catalog/` | Control Catalog | Central pool of controls; hygiene requirements vs guidelines; OSCAL mention | 12 May 2026 |
| `/glossary/` | Glossary | Agency Users, Public Users, Digital Service, Transactional/Non-Transactional definitions | 26 Mar 2026 |
| `/highlights/` | Highlights | External recognition: ThoughtWorks Tech Radar (Nov 2025), NIST OSCAL workshop (2025) | 12 May 2026 |
| `/contact-us/` | Contact Us | info@tech.gov.sg; feedback form go.gov.sg/ictpolicy | 16 Apr 2026 |
| `/search/` | Search | Site search | — |
| `/archive/` | Archive | Retired pages (`/archive/about-ssp/`, `/archive/cybersecurity-1/`, `/archive/dss-1/`) — do NOT cite as current | 26 Mar 2026 |

## SSP template pages (8)

| URL | System category | Sensitivity ceiling | Families / ~controls | Notes | Updated |
|---|---|---|---|---|---|
| `/ssp/low-risk-cloud/` | Generic cloud (3rd-party CSP) | Restricted / Sensitive Normal | 13 / ~117 | Baseline reference; largest families LM (18), AS (15) | 24 Mar 2026 |
| `/ssp/medium-risk-cloud/` | Generic cloud | Confidential / Sensitive High | 13 / ~117 | Same family set as low-risk; differs by level/parameter assignments | 24 Mar 2026 |
| `/ssp/high-risk-cloud/` | High-Risk Cloud **CII** | Confidential / Sensitive High | 14 / ~134 | Adds HR family; note: CII owners to inform CSA before cloud migration | 24 Mar 2026 |
| `/ssp/low-risk-on-premises/` | Generic on-premises | Restricted / Sensitive Normal | 13 / ~103 | DC (Datacentre) replaces CS (Container Security) | 24 Mar 2026 |
| `/ssp/gen-ai/` | System using generative AI models | Confidential / Sensitive High | 2 / 9 (DP-1 + GA-1…8) | An overlay, not standalone: GA-1/GA-2 hosting-location vs classification ceilings, GA-3 no-logging/no-training agreements, GA-5 model formats/secure loaders, GA-6 upload safeguards, GA-7 output evaluation, GA-8 hallucination awareness | 24 Mar 2026 |
| `/ssp/dss-high/` | Digital Services (High Impact): ≥1M visits/year (per WOGAA) | n/a (usability/accessibility) | 9 / ~92 | WCAG families dominate | 26 Mar 2026 |
| `/ssp/dss-others/` | Digital Services (Others): <1M visits/year | n/a | 9 / ~92 | Same families; differs by level assignments | 26 Mar 2026 |
| `/ssp/sandbox/` | Pilot sandbox system | Restricted / Sensitive Normal | 13 / ~117 | Pilot template | 24 Mar 2026 |

Every SSP page states (verbatim): "Agencies are to customise this template to create their own system-specific System Security Plan or use it as a default System Security Plan."

## Cybersecurity control-family pages (17)

Hub: `/control-catalog/cybersecurity/` (updated 26 Mar 2026). Each family page publishes full control text: Statement, Recommendations/Guidance, Risk Statement. Pattern: `/control-catalog/cybersecurity/<family>/`

| Code | Family | Code | Family |
|---|---|---|---|
| ac | Access Control (AC-1…16) | is | Infrastructure Security |
| as | Application Security | lm | Logging & Monitoring |
| br | Backup & Recovery | ns | Network Security |
| ck | Cryptography | pm | Security Programme Management |
| cs | Container Security | rs | Resiliency (family page exists; absent from sampled SSP baselines) |
| dc | Datacentre | sc | Software Supply Chain |
| dp | Data Protection | sd | Secure Development |
| ga | Generative AI | st | Security Testing |
| hr | High-Risk (CII-specific) | | |

## DSS control-family pages (9)

Hub: `/control-catalog/dss/` (updated 26 Mar 2026). "Sets the baseline for usability and accessibility across all Singapore Government digital services"; incorporates WCAG A and AA. Pattern: `/control-catalog/dss/<family>/`

Families: `bd` (e.g., BD-1…9), `pr`, `tx`, `tl`, `uu`, `wo`, `wp`, `wr`, `wu`.

## Companion repo — github.com/GovTechSG/tech-standards

- `catalogs/im8-reform.json` — OSCAL catalog, title "Instruction Manual 8 Reform"; version `2025.05.13`; 137 controls in 15 families (includes `tp` Third Party Management, which the portal does not show; lacks GA/HR/RS which the portal has).
- `profiles/{low,medium}-risk-level-{0,1,2}.json` — OSCAL profiles importing the catalog by control ID (low-risk: L0=6, L1=86, L2=35; medium-risk: L0=26, L1=73, L2=25).
- MIT License, © 2024 Government Technology Agency of Singapore. No releases/tags; versioning via catalog metadata and commit messages.
- **Lag warning:** repo (2025.05.13, last commit Sep 2025) trails the portal (pages updated through mid-2026). Portal wins on conflict.

## Change-detection signals (for the tracker, v2)

- Portal: per-page "Last updated" stamps; site-wide footer date; sitemap.xml for page inventory. No public changelog — diffing page content is the mechanism.
- Repo: catalog `metadata.version` / `last-modified`; per-control `published` and `last-modified` props; commit messages encode releases.
