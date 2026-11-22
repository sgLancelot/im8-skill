# DP — Data Protection

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `dp` | Controls: 9

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

**Levels:** low-risk cloud: L1, medium-risk cloud: L1, high-risk cloud CII: L1, low-risk on-prem: L1, low-risk SaaS: L1, medium-risk SaaS: L1, sandbox: L2 *(portal text as of 10 November 2026)*

**Statement:** Encrypt data in transit.

**Guidance:** While some CSP services transparently encrypt data in transit at the network layer, data at the application layer should be encrypted using protocols such as Transport Layer Security (TLS) 1.2 and above

**Risk statement:** Failure to encrypt data in transit increases the risk of unauthorised interception and eavesdropping, potentially leading to data breaches, unauthorised access, and compromise of sensitive information during transmission.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/dp/

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

## DP-8 — Data Classification Disclosure

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1, GenAI: L1 *(portal; portal control, not in the OSCAL release)*

**Statement:** For internal applications serving public officers, specify the highest permitted security and sensitivity classification for input data, such as text, audio, or multimedia/file uploads, in the system's user interface and guides.

**Guidance:** Indicate with a clear message, either at or near the input field, the relevant data classification that may be used with the system. For GenAI systems, note that any proposed deviations to this control must be submitted to and approved by NAIG.

**Risk statement:** Users who are not informed of the maximum allowed data classification may submit sensitive information the system is not permitted to process, risking data breaches, legal violations, and reputational harm.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/dp/

## DP-10 — Secure Data Wipe and Verification

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Ensure that all government information in resources assigned to Third party are destroyed or securely wiped.

**Guidance:** Use secure data wiping tools meeting international standards (NIST SP 800-88 or ISO/IEC 27040) for complete data destruction. Obtain documented evidence confirming secure destruction of government information and conduct periodic compliance audit

**Risk statement:** Ensuring resources destroy or securely wipe government information reduces the risk of unauthorised access, data leakage, and ensures compliance with data protection and residency requirement.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/dp/
