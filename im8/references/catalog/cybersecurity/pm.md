# PM — Security Programme Management

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `pm` | Controls: 8

Controls to implement cybersecurity governance, risk, and compliance processes and policies.

## PM-1 — Cybersecurity Incident Management Plan

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Develop, document, and disseminate an agency-level cybersecurity incident management plan to respond to cybersecurity incidents.

**Guidance:** Refer to the Government Incident Reporting and Operations Centre (GIROC) ICT and Data Incident Reporting Resources for an incident management plan and best practices template.

**Risk statement:** Lack of a cybersecurity incident management plan increases the risk of ineffective response to cybersecurity incidents, hindering the ability to contain, mitigate, and recover from security breaches, potentially leading to extended downtime and data compromise.

## PM-2 — Risk Assessment

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Develop and document a risk assessment by [system owner] and get it approved by [risk assessment approver] prior to [SaaS subscription / initial full release] and conduct a review every [time period (days)] day(s).

**Guidance:** The Risk Assessment should cover Cyber Risk, Data Risk, Resiliency Risk, Business Risk, Project Risk, Offshore Risk and other types of risk where applicable.

**Risk statement:** Without developing and documenting risk assessment before the initial full release, there's an increased risk of overlooking potential security threats, vulnerabilities, and regulatory compliance issues, compromising the overall security posture of the system.

**Parameters:**

- `pm-2_prm_1` — system owner (type: str) — The owner of the system.
- `pm-2_prm_2` — risk assessment approver (type: str) — The approver of the risk assessment.
- `pm-2_prm_3` — risk assessment use case (type: str) — choose one: SaaS subscription; initial full release The use case of the risk assessment.
- `pm-2_prm_4` — time period (days) (type: int) — The time period in days for risk assessment.

## PM-3 — System Security Plan (SSP) Development

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Develop and maintain a comprehensive System Security Plan (SSP) that accurately reflects the system characteristics and security controls in place for the organisation's systems and environments.

**Guidance:** The SSP should be detailed, covering all aspects of security controls, roles, responsibilities, and operational processes. Regular updates are necessary to reflect changes in the security landscape and system evolution.

**Risk statement:** Failure to develop a comprehensive SSP can result in inadequate documentation and security controls, leading to increased vulnerability to cyber threats and non-compliance with regulatory requirements.

## PM-4 — Approval of Residual Risks

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Get acceptance and approval of the residual risks from agency's [approving authority].

**Guidance:** Agencies should seek acceptance and approval from their [approving authority] on the residual risks based on the SSP and inform GovTech of the approval.

**Risk statement:** Failure to seek the right level of authority to accept and approve the residual risks can lead to misalignment of the business implications and trade-offs from the controls set in the SSP with the Agency IDSC direction.

**Parameters:**

- `pm-4_prm_1` — approving authority (type: str) — The authority for approval of residual risks.

## PM-5 — Central Submission of Approved System Security Plan (SSP)

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Submit approved SSPs centrally to maintain a unified and up-to-date repository of security plans and practices.

**Guidance:** Reference the IM8 Portal for submitting all approved SSPs.

**Risk statement:** Inconsistent or decentralised submission of the SSP can lead to decreased visibility of security and compliance adoption across Government.

## PM-6 — System Documentation

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Maintain detailed, up-to-date documentation of all system information and architecture.

**Guidance:** Example system documentation includes architecture and network diagrams, architecture decision records, hardware and software inventories, data flows, and configurations. This documentation should be regularly reviewed and updated to reflect changes in the environment. Documentation should be accessible to relevant personnel while ensuring sensitive information is protected. Adopt documentation-as-code practices and machine-readable formats (such as Markdown, JSON, YAML, etc), to facilitate version control, collaboration, and automation in maintaining documentation.

**Risk statement:** Comprehensive documentation of system architecture, components, configurations, and dependencies is essential for effective management, troubleshooting, and security auditing.

## PM-7 — Certification

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Ensure that the Software as a Service (SaaS) provider is certified with [certifications].

**Guidance:** Ensure that the certification is up-to-date. Avoid certifications that are only attestations without a pass/fail element.

**Risk statement:** Third-party certification provides assurance that security controls have been properly implemented in the Software as a Service (SaaS) provider.

**Parameters:**

- `pm-7_prm_1` — certifications (type: str) — The required certifications.

## PM-8 — SaaS Whitelisting

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Maintain and enforce a whitelist of authorised software and services.

**Guidance:** Refer to a centrally-maintained whitelist or [whitelisting authority] for authorised SaaS.

**Risk statement:** Failing to whitelist the SaaS may potentially expose sensitive data (e.g., Confidential (Cloud-Eligible) or SENSITIVE-HIGH data) to the risk of data breaches.

**Parameters:**

- `pm-8_prm_1` — whitelisting authority (type: str) — The whitelisting authority.
