# im8 — a grounded Q&A skill for Singapore's IM8 reform

A [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills) that answers questions about Singapore's IM8 reform — the risk-based ICT&SS governance framework — **grounded in the officially published control catalog, with citations on every answer.**

## Why this exists

For years, IM8 was a black box: vendors were expected to comply with rules they couldn't read. The IM8 reform changed that in a big way. The control requirements are now **openly published** at [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) — full control text, SSP baselines per system risk category, the works — and GovTech publishes the same controls in machine-readable OSCAL form on [GitHub](https://github.com/GovTechSG/tech-standards) under an MIT license, explicitly inviting industry to "learn and even improve the government's policy standards."

That openness is a genuinely significant shift, and this skill is built to help people make the most of it: ask a question, get an answer grounded in the published framework, with links to the exact pages so you can verify before you rely.

## How it works

The skill ships with a **complete snapshot of the published catalog** in [`im8/references/catalog/`](im8/references/catalog/) — every control's statement, guidance, and risk statement across the cybersecurity and digital-service-standards catalogs, plus each SSP baseline's control list with profile levels. Answers come from this snapshot first, which makes them fast and reliable even where live web access is limited.

The snapshot is a cache, not a rival authority. When the skill *can* reach the web, it verifies against the live portal before answering — and **the live portal always wins on conflict**. When it can't, it says so, and tells you the snapshot's date. Provenance for every file is recorded in the two `SNAPSHOT-*.md` manifests: most cybersecurity families derive from GovTech's MIT-licensed OSCAL release, and the remainder (plus the DSS catalog and SSP baselines) from the public portal pages, each tagged with its on-page "last updated" date. The snapshot is refreshed as the official sources change.

## Design principles

- **One source of truth.** [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) is the sole authority for IM8 rules; the bundled snapshot is a dated cache of it, and the skill discloses which one answered you.
- **Citations on every answer** — control IDs, profile levels, configurable parameters, and the canonical portal page they came from.
- **Honest boundaries.** What isn't published (internal manual content, agency workflows, TechPass-gated tooling) gets "the published framework doesn't cover this," not a guess.
- **No compliance verdicts.** The skill reports what the published controls say; compliance determinations belong to your agency and its assessors.

## Install

**Claude app:** download [`im8.skill`](../../releases) (or package the `im8/` folder as a zip renamed to `.skill`) and add it under Settings → Capabilities → Skills.

**Claude Code:** copy the skill folder into your skills directory:

```bash
git clone https://github.com/<owner>/im8-reform.git
cp -r im8-reform/im8 ~/.claude/skills/
```

Then ask: *"What does the medium-risk cloud baseline say about database activity monitoring?"* — or invoke it directly with `/im8`.

## Contributing

The most valuable issues you can open: a portal page that's missing from the skill's map, a page that moved or 404s, or a place where the snapshot has drifted from the live portal. The source map is the product.

## Disclaimer

This is an unofficial, personal project grounded in the publicly published framework only. It is **not official guidance** and is not affiliated with GovTech or any government agency or employer. Verify answers against [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) and your agency's internal processes before relying on them.

## License and attribution

The skill's instruction files are MIT-licensed. Control content in the snapshot derives from the [GovTechSG/tech-standards](https://github.com/GovTechSG/tech-standards) OSCAL catalog (MIT, © Government Technology Agency of Singapore) and from the public portal (© Government Technology Agency of Singapore); the canonical source is always the live portal.
