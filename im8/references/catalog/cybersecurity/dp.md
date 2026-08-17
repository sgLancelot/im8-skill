# DP — Data Protection

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `dp` | Controls: 7

Controls to protect the data of a system.

## DP-1 — Data Residency

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Enforce data residency of primary data in [country].

**Guidance:** Use the appropriate region of cloud service providers for compute and storage of data, such as ap-southeast-1 for Singapore in AWS.

**Risk statement:** Failure to enforce data residency of primary data in the appropriate country may lead to legal and regulatory compliance issues, privacy concerns, and potential unauthorised access or storage of sensitive data outside the jurisdiction, increasing the risk of legal consequences and data breaches.

**Parameters:**

- `dp-1_prm_1` — country (type: str) — The country the primary data resides in.

## DP-2 — Data at Rest Encryption

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Encrypt data at rest.

**Guidance:** Many CSP services encrypt data at rest by default but this should be confirmed and validated depending on service usage.

**Risk statement:** Without encrypting data at rest, there's an increased risk of unauthorised access and data exposure in the event of physical theft, unauthorised access to storage media, or compromised security controls, compromising the confidentiality of stored information.

## DP-3 — Data in Transit Encryption

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Encrypt data in transit.

**Guidance:** While some CSP services transparently encrypt data in transit at the network layer, data at the application layer should be encrypted using protocols such as Transport Layer Security (TLS) and Secure Socket Layer (SSL).

**Risk statement:** Failure to encrypt data in transit increases the risk of unauthorised interception and eavesdropping, potentially leading to data breaches, unauthorised access, and compromise of sensitive information during transmission.

## DP-4 — Government on Commercial Cloud (GCC)

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Host systems classified as CONFIDENTIAL (CLOUD-ELIGIBLE), RESTRICTED, or OFFICIAL-CLOSED on Commercial Cloud hosting environments in GCC.

**Guidance:** GCC allows oversight to be maintained at the Whole-of-Government level and implements several controls by default.

**Risk statement:** Hosting higher-sensitivity systems in Government on Commercial Cloud (GCC) ensures compliance with security classifications, reducing the risk of unauthorised access and maintaining data confidentiality according to government security standards.

## DP-5 — Sanitisation

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Sanitise all hardware that stores data at rest. Shred or incinerate data storage meant for retirement.

**Guidance:** Use industry standards such as
a) Peter Gutmann Secure Deletion;
b) Bruce Schneier Algorithm
c) US Department of Defence's Standards (DoD 5220.22-M).

**Risk statement:** Violating this control can expose government data to unauthorised users.

## DP-6 — Witness Sanitisation and Destruction of Storage Devices

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Witness the sanitisation and destruction process to ensure data is removed from storage.

**Guidance:** Establish a SOP to ensure sanitisation and destruction are witnessed by an agency staff.

**Risk statement:** Ensuring storage devices are sanitised or destroyed will eliminate the possibility of unauthorised or unintended data retention.

## DP-7 — Data Loss Prevention

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Implement data loss prevention mechanisms that monitor data flows, detect sensitive data transfers, and block unauthorised sharing of sensitive data.

**Guidance:** Where possible, use built-in solutions such as Microsoft Purview or Google Workspace data loss prevention rules. Regularly review and update data loss prevention policies to adapt to evolving threats and organisational needs.

**Risk statement:** Failure to implement data loss prevention measures increases the risk of unauthorised data exfiltration, accidental data leaks, and data breaches, compromising sensitive information and organisational integrity.
