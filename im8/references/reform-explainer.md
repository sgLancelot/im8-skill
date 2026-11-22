# How the IM8 Reform Works

Orientation for answering questions. Every claim traces to the portal or the official GitHub repo; cite those URLs in answers, not this file.

## From black box to open publication

- IM8 — the Instruction Manual for ICT&SS Management — is the Singapore Government's policy framework governing ICT and Smart Systems across agencies. Historically it was internal-only: vendors were expected to comply with rules they could not read directly.
- The **ICT&SS Policy Reform** changed that. Its purpose, in the portal's words: an "effort to transform policy controls to be lean, relevant and effective," enabling "differentiated treatment for systems of different risk impact levels" ([About](https://info.standards.tech.gov.sg/about/)).
- The reform's control requirements are now **openly published**: full control text (statement, recommendations, risk statement) on public portal pages, plus machine-readable OSCAL catalogs and profiles on GitHub under MIT license.
- GovTech's own framing (repo README, verbatim): the repo "is a public reference for industry partners, providing access to similar control requirements used by agencies. This collaborative approach ensures that the industry can learn and even improve the government's policy standards." And: "By making these policies open source, we aim to foster greater collaboration and innovation in securing Singapore's digital infrastructure."
- External recognition (per [Highlights](https://info.standards.tech.gov.sg/highlights/)): ThoughtWorks Technology Radar (Nov 2025) and a NIST OSCAL workshop presentation, "From One-Size-Fits-All to Right-Sizing" (2025).
- Milestones: repo initial commit Jul 2024; first published release 2024.05.30-2 (Sep 2024); MIT license Sep 2024; release 2025.05.13; portal pages actively updated through November 2026 (larger releases on 19 Oct and 10–11 Nov 2026).

## The core mechanics

**Risk banding.** Instead of every system complying with the same rules, systems are categorized — Low-Risk Cloud, Medium-Risk Cloud, High-Risk Cloud CII, Low-Risk On-Premises, Low-Risk SaaS, Medium-Risk SaaS, Generative AI, Digital Services (High Impact / Others), Sandbox — and each category gets a right-sized baseline. Agencies "assess the risks and identify the right level of controls for their systems based on various business and technical considerations" ([About](https://info.standards.tech.gov.sg/about/)).

**System Security Plans (SSP).** Each category has a published SSP template containing its baseline controls. Verbatim, on every SSP page: "Agencies are to customise this template to create their own system-specific System Security Plan or use it as a default System Security Plan." The SSP is the compliance artifact for a system.

**Profile levels** (portal [Glossary](https://info.standards.tech.gov.sg/glossary/), updated 25 Oct 2026). **Level 0** is "a cardinal and non-discretionary requirement"; "Compliance with a Level 0 control cannot be waived", and only in very exceptional circumstances should an agency consult the IM8 Secretariat before any further action. **Level 1** controls set baseline requirements; agencies "have the discretion to adopt alternate means of implementation provided that the approach taken meets the policy intent of the control", but not implementing one "must be formally approved through a tiered governance process commensurate with the risk profile of the system", per the IM8 Compliance Model in SNG (PMO) Circular No. 3/2024 (the circular itself is not on the portal). **Level 2** controls are optional best practice: "Non-implementation of Level 2 controls does not require risk acceptance or deviation and should not be treated as a compliance gap." The [SSP page](https://info.standards.tech.gov.sg/ssp/) gives a shorter version (Level 0: "cardinal and mandatory requirements"). SSP templates carry Level 0 + Level 1 controls by default. A control's level can differ across categories — "A control can be tagged as requirement for low-risk systems but tagged as guideline for systems in sandbox stage" ([Control Catalog](https://info.standards.tech.gov.sg/control-catalog/)).

**Hygiene requirements vs guidelines.** The catalog distinguishes controls that are a mandatory floor ("hygiene requirements") from advisory best practice ("guidelines") ([Control Catalog](https://info.standards.tech.gov.sg/control-catalog/)).

**Agency-configurable parameters.** Many controls contain bracketed parameters with defaults that agencies tune — e.g., vulnerability scan frequency "at least every [90] day(s)" (ST-1), remediation timeframes by severity (ST-5). About 30 of 137 controls in the OSCAL catalog carry parameters; the portal calls these "risk-based options."

**Control anatomy.** Families with 2-letter codes (AC, LM, NS, SC…); IDs `<family>-<n>`; each control has a Statement, Recommendations/Guidance, and Risk Statement — all published in full on the family pages.

**Catalogs.** Cybersecurity (17 families, including SA — SaaS Security, added 10 Nov 2026), Generative AI (GA, its own section), Organisational (Third Party Management, added 10 Nov 2026), and Digital Service Standards (9 families — usability/accessibility, incorporating WCAG A/AA, for government digital services; High Impact = ≥1M visits/year per WOGAA).

## What's public vs what isn't

**Public:** everything above — reform rationale, full control text, SSP baselines, glossary, OSCAL catalogs/profiles, feedback channels (go.gov.sg/ictpolicy, info@tech.gov.sg).

**Not public:** the complete internal IM8 manual and non-reformed content; the detailed agency-side approval and deviation workflows (the portal points to SNG (PMO) Circular No. 3/2024 for Level 1 deviations and to Circular No. 7/2026 for GenAI closed beta/deployment definitions, but neither circular is published there); the portal's system-registration/SSP-generation tooling behind TechPass; agency audit processes. When a question crosses into this column, say so plainly.

## Folklore traps to correct (gently, positively)

- "IM8 requires X" from pre-reform memory — check the current published baseline; several formerly mandatory items are now Level 2 best-practice, and controls differ by system category.
- Treating all controls as equally mandatory — levels and hygiene/guideline tags exist precisely to prevent this.
- Assuming the rules are secret — the reform's headline achievement is that they aren't anymore.
- Citing the GitHub repo as current — it lags the portal; the portal is the source of truth.
