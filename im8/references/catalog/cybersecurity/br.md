# BR — Backup and Recovery

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `br` | Controls: 4

Controls to support backup and disaster recovery.

## BR-1 — Backup

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Backup all important data and systems at least every [time period (days)] day(s), and store backups in a secure and separate location.

**Guidance:** Use default CSP-managed backup services (e.g., AWS Backup, Azure Backup, GCP Backup and DR Service). Consider alternative backup services only when default CSP services cannot be used. Store backups and snapshots separately to primary data storage with data encrypted-at-rest. For SaaS, ensure that SaaS provider is able to restore last backup.

**Risk statement:** Without regular backups stored in a secure and separate location, there is an increased risk of data loss, system failures, and extended downtime in the event of accidental deletion, hardware failures, or malicious attacks.

**Parameters:**

- `br-1_prm_1` — time period (days) (type: int) — The time period in days for backup.

## BR-2 — Recovery Testing

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Conduct testing of recovery processes at least every [time period (days)] day(s) to ensure their effectiveness.

**Guidance:** Ensure each test verifies the system's ability to fully restore all data and services.

**Risk statement:** Failure to regularly test recovery processes may result in ineffective response during actual incidents, increasing the risk of prolonged downtime, data loss, and compromised business continuity in the event of a disaster or system failure.

**Parameters:**

- `br-2_prm_1` — time period (days) (type: int) — The time period in days for recovery testing.

## BR-3 — Backup Retention

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Prevent backups from being modified or deleted for [time period (days)] day(s) or as stipulated in the agency's data retention policies.

**Guidance:** Use S3 Object Lock or Azure Blob Storage with immutability enabled to enforce time-based retention policies.

**Risk statement:** Lack of prevention measures against the modification or deletion of backups for the specified duration increases the risk of data loss, unauthorised alterations, and potential inability to recover from incidents, compromising the integrity and availability of critical information.

**Parameters:**

- `br-3_prm_1` — time period (days) (type: int) — The time period in days of backup retention.

## BR-4 — Disaster Recovery Plan

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Develop, maintain, and regularly test a disaster recovery plan that ensures critical functions and data can be restored within the Recovery Time Objective (RTO) and Recovery Point Objective (RPO) as determined by business requirements and risk assessments.

**Guidance:** The disaster recovery plan should include clearly defined roles and responsibilities, step-by-step recovery procedures, communication protocols during a disaster, and integration with the overall business continuity plan. Assess the effectiveness of the existing disaster recovery plan during disaster recovery exercises.

**Risk statement:** Absence of a comprehensive disaster recovery plan increases the risk of prolonged system downtime, data loss, and inability to maintain business continuity in the event of a disaster, potentially leading to significant financial losses and damage to organisational reputation.
