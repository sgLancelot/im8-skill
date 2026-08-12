# im8-reform — a grounded Q&A skill for Singapore's IM8 reform

A [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills) that answers questions about Singapore's IM8 reform — the risk-based ICT&SS governance framework — **grounded exclusively in the official public portal, with citations on every answer.**

## Why this exists

For years, IM8 was a black box: vendors were expected to comply with rules they couldn't read. The IM8 reform changed that in a big way. The control requirements are now **openly published** at [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) — full control text, SSP baselines per system risk category, the works — and GovTech publishes the same controls in machine-readable OSCAL form on [GitHub](https://github.com/GovTechSG/tech-standards) under an MIT license, explicitly inviting industry to "learn and even improve the government's policy standards."

That openness is a genuinely significant shift, and this skill is built to help people make the most of it: ask a question, get an answer grounded in the published framework, with links to the exact pages so you can verify before you rely.

## Design principles

- **One source of truth.** [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) is the sole authority for IM8 rules; the [OSCAL repo](https://github.com/GovTechSG/tech-standards) is the machine-readable companion (the skill knows it lags the portal and says so).
- **Citations on every answer** — control IDs, profile levels, configurable parameters, and the page they came from.
- **Honest boundaries.** What isn't published (internal manual content, agency workflows, TechPass-gated tooling) gets "the published framework doesn't cover this," not a guess.
- **No compliance verdicts.** The skill reports what the published controls say; compliance determinations belong to your agency and its assessors.

## Install

1. Download or clone this repo.
2. Add the `im8` folder to your Claude skills (Claude Code: `~/.claude/skills/`; Claude.ai/Cowork: upload the `.skill` package).
3. Ask: *"What does the medium-risk cloud baseline say about database activity monitoring?"*

## Contributing

Spotted a portal page the skill's map is missing, or a page that moved? That's the most valuable issue you can open — the portal map is the product.

## Disclaimer

This is an unofficial, personal project grounded in the publicly published framework only. It is **not official guidance** and is not affiliated with GovTech or any government agency or employer. Verify answers against [info.standards.tech.gov.sg](https://info.standards.tech.gov.sg/) and your agency's internal processes before relying on them.

## License

MIT for the skill's instruction files. The linked framework content remains © Government Technology Agency of Singapore (the OSCAL repo is itself MIT-licensed).
