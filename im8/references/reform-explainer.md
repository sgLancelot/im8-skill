# How the IM8 Reform Works

Orientation for answering questions. Every claim traces to the portal or the official GitHub repo; cite those URLs in answers, not this file.

## From black box to open publication

- IM8 — the Instruction Manual for ICT&SS Management — is the Singapore Government's policy framework governing ICT and Smart Systems across agencies. Historically it was internal-only: vendors were expected to comply with rules they could not read directly.
- The **ICT&SS Policy Reform** changed that. Its purpose, in the portal's words: an "effort to transform policy controls to be lean, relevant and effective," enabling "differentiated treatment for systems of different risk impact levels" ([About](https://info.standards.tech.gov.sg/about/)).
- The reform's control requirements are now **openly published**: full control text (statement, recommendations, risk statement) on public portal pages, plus machine-readable OSCAL catalogs and profiles on GitHub under MIT license.
- GovTech's own framing (repo README, verbatim): the repo "is a public reference for industry partners, providing access to similar control requirements used by agencies. This collaborative approach ensures that the industry can learn and even improve the government's policy standards." And: "By making these policies open source, we aim to foster greater collaboration and innovation in securing Singapore's digital infrastructure."
- External recognition (per [Highlights](https://info.standards.tech.gov.sg/highlights/)): ThoughtWorks Technology Radar (Nov 2025) and a NIST OSCAL workshop presentation, "From One-Size-Fits-All to Right-Sizing" (2025).
- Milestones: repo initial commit Jul 2024; first published release 2024.05.30-2 (Sep 2024); MIT license Sep 2024; release 2025.05.13; portal pages actively updated through mid-2026.

## The core mechanics

**Risk banding.** Instead of every system complying with the same rules, systems are categorized — Low-Risk Cloud, Medium-Risk Cloud, High-Risk Cloud CII, Low-Risk On-Premises, Generative AI, Digital Services (High Impact / Others), Sandbox — and each category gets a right-sized baseline. Agencies "assess the risks and identify the right level of controls for their systems based on various business and technical considerations" ([About](https://info.standards.tech.gov.sg/about/)).

**System Security Plans (SSP).** Each category has a published SSP template containing its baseline controls. Verbatim, on every SSP page: "Agencies are to customise this template to create their own system-specific System Security Plan or use it as a default System Security Plan." The SSP is the compliance artifact for a system.

**Profile levels** (repo README, verbatim): "Level 0 (Must-Haves): essential controls that must be implemented for all systems"; "Level 1 (Should-Haves): strongly recommended and should be implemented where feasible"; "Level 2 (Good-to-Haves): best-practices… not mandatory." SSP templates carry Level 0 + Level 1 controls by default. A control's level can differ across categories — "a control may be tagged as a requirement for low-risk systems but classified differently for systems with higher risk."

**Hygiene requirements vs guidelines.** The catalog distinguishes controls that are a mandatory floor ("hygiene requirements") from advisory best practice ("guidelines") ([Control Catalog](https://info.standards.tech.gov.sg/control-catalog/)).

**Agency-configurable parameters.** Many controls contain bracketed parameters with defaults that agencies tune — e.g., vulnerability scan frequency "at least every [90] day(s)" (ST-1), remediation timeframes by severity (ST-5). About 30 of 137 controls in the OSCAL catalog carry parameters; the portal calls these "risk-based options."

**Control anatomy.** Families with 2-letter codes (AC, LM, NS, SC…); IDs `<family>-<n>`; each control has a Statement, Recommendations/Guidance, and Risk Statement — all published in full on the family pages.

**Two catalogs.** Cybersecurity (17 families) and Digital Service Standards (9 families — usability/accessibility, incorporating WCAG A/AA, for government digital services; High Impact = ≥1M visits/year per WOGAA).

## What's public vs what isn't

**Public:** everything above — reform rationale, full control text, SSP baselines, glossary, OSCAL catalogs/profiles, feedback channels (go.gov.sg/ictpolicy, info@tech.gov.sg).

**Not public:** the complete internal IM8 manual and non-reformed content; agency-side approval and deviation workflows; the portal's system-registration/SSP-generation tooling behind TechPass; agency audit processes. When a question crosses into this column, say so plainly.

## Folklore traps to correct (gently, positively)

- "IM8 requires X" from pre-reform memory — check the current published baseline; several formerly mandatory items are now Level 2 best-practice, and controls differ by system category.
- Treating all controls as equally mandatory — levels and hygiene/guideline tags exist precisely to prevent this.
- Assuming the rules are secret — the reform's headline achievement is that they aren't anymore.
- Citing the GitHub repo as current — it lags the portal; the portal is the source of truth.
