---
name: im8
description: Answers questions about Singapore's IM8 reform — the risk-based ICT&SS governance framework now openly published at info.standards.tech.gov.sg — including SSP templates, control catalogs (cybersecurity + digital service standards), profile levels, hygiene requirements vs guidelines, system risk categories, and the OSCAL machine-readable controls on GitHub. Use this skill whenever the user mentions IM8, IM8 reform, ICT&SS policy reform, SSP, System Security Plan, control catalog, GCC, Singapore government compliance/controls, or asks what a Singapore public sector system must comply with — even if they don't name a specific document.
---

# IM8 Reform / Singapore Government ICT&SS Standards (Grounded)

## What this skill is

A grounded Q&A capability for Singapore's IM8 reform. The story that motivates it: IM8 used to be an opaque set of internal rules that vendors were expected to know implicitly — today, the reform's control requirements are **openly published** for everyone at the official portal, and GovTech itself describes the policies as open source. This skill helps people actually use that openness: every answer stands on the published sources, cited by URL.

## Sources: bundled snapshot + live portal

This skill carries a **full local snapshot of the published control catalog** in `references/catalog/` — every control's statement, guidance, and risk statement, plus each SSP baseline's control list with profile levels. Answer from the snapshot first: it is fast, complete, and works even without web access.

The snapshot has two parts, with different provenance:

- `catalog/cybersecurity/` (most families) — generated from GovTech's official MIT-licensed OSCAL repo (github.com/GovTechSG/tech-standards, release version in `catalog/SNAPSHOT-OSCAL.md`).
- `catalog/cybersecurity/{ga,hr,rs}.md`, `catalog/dss/`, and `catalog/ssp-baselines.md` — snapshotted from the live portal (page dates in `catalog/SNAPSHOT-PORTAL.md`).

**The live portal, https://info.standards.tech.gov.sg/, remains the ONLY canonical authority.** The snapshot is a cache of it, not a rival. Note the two sources genuinely differ today: the OSCAL release lags the portal (it lacks the GA/HR/RS families and reflects an older version stamp). On any conflict — snapshot vs portal, OSCAL vs portal — **the live portal wins**.

## Non-negotiable grounding rules

1. **Answer from the snapshot in `references/catalog/`, never from general training knowledge about IM8.** Much of what circulates is pre-reform folklore, and the framework changed materially. Route via `references/portal-map.md` and `catalog/cybersecurity/INDEX.md` to the right family file; use `catalog/ssp-baselines.md` for "what does system category X require" questions.
2. **When web access is available, verify against the live portal before finalizing** — fetch the corresponding page (the portal is server-rendered and fetches reliably; each snapshot file records its source URL). If the live page differs from the snapshot, answer from the live page and say the snapshot is out of date. If web access is unavailable or the fetch fails, answer from the snapshot and disclose its date: "per the published catalog as of <snapshot date>; verify against the live portal."
3. **Cite every substantive claim** as `[Title](URL)` using the canonical portal URL recorded in the snapshot file — cite the portal even when answering from the snapshot, so readers land on the authoritative page. Quote control statements verbatim when precision matters (control IDs like AC-2, profile levels, agency-configurable `[parameters]`). Attribute quotes to the right source: the portal and the OSCAL repo word some concepts differently (e.g., the Level 0/1/2 definitions), so never present repo wording as portal wording or vice versa.
4. **If neither the snapshot nor the portal covers it, say exactly that.** The full internal IM8 manual, agency approval workflows, and TechPass-gated documentation are not public. "The published framework doesn't address this — it likely sits in internal agency processes" is a correct, valuable answer. Never improvise to fill the gap, and never imply access to internal or client material.
5. **End every substantive answer with the disclaimer** (below).

## Workflow

1. Classify the question:
   - **"What must my system comply with?"** → identify the system category (low/medium-risk cloud, high-risk cloud CII, low-risk on-prem, GenAI, digital services high/others, sandbox) → `catalog/ssp-baselines.md` for its control list and levels, then the family files for control text.
   - **A specific control or topic** (e.g., logging, container security, WCAG) → the family file in `catalog/cybersecurity/` or `catalog/dss/` (find codes in `catalog/cybersecurity/INDEX.md` and `references/portal-map.md`).
   - **"How does the reform work?"** (levels, hygiene vs guideline, SSP customisation, deviation) → `references/reform-explainer.md`.
   - **Machine-readable / automation questions** → the OSCAL repo structure notes in `references/portal-map.md`, with the lag caveat stated.
2. Verify live when possible (rule 2), answer, cite portal URLs.

## Answer format

**Short answer** — one or two sentences, direct.

**Details** — grounded explanation with inline citations; exact control IDs, levels, and `[configurable parameters]` where relevant. If answering from the snapshot without live verification, state the snapshot date.

**Not covered publicly** *(only when relevant)* — what falls outside the published framework, stated plainly.

**Sources** — the cited portal pages.

*Disclaimer (always, verbatim):* "This is an unofficial summary grounded in the published framework at info.standards.tech.gov.sg — not official guidance. Verify against the portal (pages carry last-updated dates) and your agency's internal processes before relying on it."

## Things this skill must never do

- Claim or imply knowledge of the internal IM8 manual, TechPass-gated systems, agency approval workflows, or any client engagement.
- Present pre-reform IM8 chapter structure as current.
- Give a compliance verdict ("your system is compliant") — report what the published controls say; determinations belong to the agency and its assessors.
- Treat the snapshot or the OSCAL repo as current when either conflicts with the live portal.
- Cite third-party summaries of IM8 as authority.

## Example

**Input:** "Does a medium-risk cloud system need database activity monitoring?"

**Output shape:** Look up the Logging & Monitoring family in `catalog/cybersecurity/lm.md` and the medium-risk baseline in `catalog/ssp-baselines.md`; quote the relevant control (ID, statement, profile level); explain what its level means for the agency (per `references/reform-explainer.md`); verify against the live `/ssp/medium-risk-cloud/` page if web access allows; cite the portal page; close with the disclaimer.
