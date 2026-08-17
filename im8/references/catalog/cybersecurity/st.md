# ST — Security Testing

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `st` | Controls: 5

Controls to validate the security of a system via internal and external testing.

## ST-1 — Vulnerability Assessment

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Run regular [type] vulnerability assessment scans for eligible hosts at least every [time period (days)] day(s).

**Guidance:** Select agent-based or network-based scans as necessary. Implement authenticated scans where possible for greater coverage. Use scanners such as Amazon Inspector or Microsoft Defender for Cloud for continuous scanning of cloud systems. For on-premises systems or systems that require periodic scans, subscribe to Vulnerability Management System (VMS). For SaaS, refer to past vulnerability scanning reports done by the SaaS provider, if any.

**Risk statement:** Without regular vulnerability assessment scans, hosts remain exposed to undetected security vulnerabilities or misconfigurations, increasing the risk of exploitation and unauthorised access to critical systems.

**Parameters:**

- `st-1_prm_1` — type (type: str) — The type of vulnerability assessment scanning.
- `st-1_prm_2` — time period (days) (type: int) — The time period in days for vulnerability assessment scans.

## ST-2 — Cloud Security Posture Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Set up cloud security posture management that performs continuous configuration scans on cloud assets.

**Guidance:** Use cloud security posture management tools such as AWS Security Hub, Azure Defender for Cloud, and Google Security Command Center.

**Risk statement:** Lack of continuous configuration scans through cloud security posture management increases the risk of misconfigurations in cloud assets, leading to security vulnerabilities, data breaches, and unauthorised access.

## ST-3 — Public Vulnerability Disclosure Programme

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Establish a public reporting channel for disclosing vulnerabilities in public-facing systems via [type].

**Guidance:** Use the [security.txt standard](#4cace601-3794-4a83-93ac-a77ffe8c10ee) or add a link to the vulnerability reporting channel on all pages, such as in the footer.

**Risk statement:** Lack of a reporting channel for vulnerabilities increases the risk of undetected and unmitigated vulnerabilities.

**Parameters:**

- `st-3_prm_1` — type (type: str) — The type of public vulnerability reporting channel.

## ST-4 — Security Testing Programme

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Conduct and document a [type] by internal teams or independent external parties every [time period (days)] day(s).

**Guidance:** Refer to the WOG Security Testing Guidelines for recommendations on the conduct of security testing engagements. For systems that are permitted to use Government Bug Bounty Programme as an alternative, obtain a passing rating based on the Agency Readiness Scorecard. For SaaS, refer to past penetration testing reports done by the SaaS provider, if any.

**Risk statement:** Without undergoing security testing, there's an increased risk of undetected security weaknesses, leaving the application susceptible to exploitation, data breaches, and unauthorised access.

**Parameters:**

- `st-4_prm_1` — type (type: str) — The type of security testing programme.
- `st-4_prm_2` — time period (days) (type: int) — The time period in days of penetration testing frequency.

## ST-5 — Vulnerability Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Triage, prioritise and then remediate or risk accept vulnerabilities that materially impact security within the following timeframe based on severity:

1 Critical: [time period (days)] day(s)

2 High: [time period (days)] day(s)

3 Medium: [time period (days)] day(s)

4 Low: [time period (days)] day(s)

**Guidance:** Vulnerabilities that materially impact security include vulnerabilities that have a high likelihood of exploitability, or are known to be exploited. Refer to resources such as the [Known Exploited Vulnerabilities Catalog](#3241e497-518c-4034-8072-e0e1ef14b435) to prioritise vulnerabilities that should be remediated. Seek approval from the appropriate approving authority for risk acceptance. Document the actions taken.

**Risk statement:** Failure to promptly remediate vulnerabilities increases the risk of potential exploits, security breaches, and prolonged exposure to known vulnerabilities in the system.

**Parameters:**

- `st-5_prm_1` — time period (days) (type: int) — The time period in days to remediate or risk accept critical vulnerability findings.
- `st-5_prm_2` — time period (days) (type: int) — The time period in days to remediate or risk accept high vulnerability findings.
- `st-5_prm_3` — time period (days) (type: int) — The time period in days to remediate or risk accept medium vulnerability findings.
- `st-5_prm_4` — time period (days) (type: int) — The time period in days to remediate or risk accept low vulnerability findings.
