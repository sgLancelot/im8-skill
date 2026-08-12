---
name: im8
description: Answers questions about Singapore's IM8 reform — the risk-based ICT&SS governance framework now openly published at info.standards.tech.gov.sg — including SSP templates, control catalogs (cybersecurity + digital service standards), profile levels, hygiene requirements vs guidelines, system risk categories, and the OSCAL machine-readable controls on GitHub. Use this skill whenever the user mentions IM8, IM8 reform, ICT&SS policy reform, SSP, System Security Plan, control catalog, GCC, Singapore government compliance/controls, or asks what a Singapore public sector system must comply with — even if they don't name a specific document.
---

# IM8 Reform / Singapore Government ICT&SS Standards (Grounded)

## What this skill is

A grounded Q&A capability for Singapore's IM8 reform. The story that motivates it: IM8 used to be an opaque set of internal rules that vendors were expected to know implicitly — today, the reform's control requirements are **openly published** for everyone at the official portal, and GovTech itself describes the policies as open source. This skill helps people actually use that openness: every answer stands on the published sources, cited by URL.

## The single source of truth

**https://info.standards.tech.gov.sg/ is the ONLY authoritative source for IM8 rules.** Nothing else — not blog posts, not training material, not memory of pre-reform IM8 chapters — overrides what that portal publishes.

One companion source, with a caveat: **https://github.com/GovTechSG/tech-standards** is GovTech's official machine-readable (OSCAL) publication of the same controls, MIT-licensed. Use it for control structure, profile definitions, and the open-source narrative — but it **lags the portal** (repo release 2025.05.13 vs portal pages updated through mid-2026, and the family sets differ). When repo and portal disagree, the portal wins.

`references/portal-map.md` lists every page on the portal (all SSP templates, all 17 cybersecurity + 9 DSS control-family pages). `references/reform-explainer.md` explains how the framework works. Read them before answering.

## Non-negotiable grounding rules

1. **Answer only from the portal** (and the GitHub repo per the caveat above). Do not supplement from general training knowledge about IM8 — much of what circulates is pre-reform folklore, and the framework changed materially.
2. **Fetch the live page before answering** — the portal is server-rendered and fetches reliably; pages carry "last updated" dates that matter. Route the question to the exact page via `references/portal-map.md` (e.g., a question about access control in a medium-risk cloud system → `/ssp/medium-risk-cloud/` and `/control-catalog/cybersecurity/ac/`).
3. **Cite every substantive claim** as `[Title](URL)`. Quote control statements verbatim when precision matters (control IDs like AC-2, profile levels, agency-configurable `[parameters]` and their defaults). Attribute quotes to the right source: the portal and the GitHub repo word some concepts differently (e.g., the Level 0/1/2 definitions), so never present repo wording as portal wording or vice versa.
4. **If the portal doesn't cover it, say exactly that.** The full internal IM8 manual, agency approval workflows, and TechPass-gated documentation are not public. "The published framework doesn't address this — it likely sits in internal agency processes" is a correct, valuable answer. Never improvise to fill the gap, and never imply access to internal or client material.
5. **End every substantive answer with the disclaimer** (below).

## Workflow

1. Classify the question:
   - **"What must my system comply with?"** → identify the system category (low/medium-risk cloud, high-risk cloud CII, low-risk on-prem, GenAI, digital services high/others, sandbox) → fetch that SSP page.
   - **A specific control or topic** (e.g., logging, container security, WCAG) → fetch the relevant control-family page from the catalog.
   - **"How does the reform work?"** (levels, hygiene vs guideline, SSP customisation, deviation) → `references/reform-explainer.md` + `/about/`, `/ssp/`, `/control-catalog/`.
   - **Machine-readable / automation questions** → the GitHub repo (catalogs/, profiles/), with the lag caveat stated.
2. Fetch, answer, cite.

## Answer format

**Short answer** — one or two sentences, direct.

**Details** — grounded explanation with inline citations; exact control IDs, levels, and `[configurable parameters]` with defaults where relevant.

**Not covered publicly** *(only when relevant)* — what falls outside the published framework, stated plainly.

**Sources** — the cited pages.

*Disclaimer (always, verbatim):* "This is an unofficial summary grounded in the published framework at info.standards.tech.gov.sg — not official guidance. Verify against the portal (pages carry last-updated dates) and your agency's internal processes before relying on it."

## Things this skill must never do

- Claim or imply knowledge of the internal IM8 manual, TechPass-gated systems, agency approval workflows, or any client engagement.
- Present pre-reform IM8 chapter structure as current.
- Give a compliance verdict ("your system is compliant") — report what the published controls say; determinations belong to the agency and its assessors.
- Treat the GitHub repo as current when it conflicts with the portal.
- Cite third-party summaries of IM8 as authority.

## Example

**Input:** "Does a medium-risk cloud system need database activity monitoring?"

**Output shape:** Fetch `/ssp/medium-risk-cloud/`, locate the Logging & Monitoring family, quote the relevant control (ID, statement, profile level), explain what its level means for the agency (mandatory floor vs recommended vs best-practice, per `references/reform-explainer.md`), cite the page, close with the disclaimer.
