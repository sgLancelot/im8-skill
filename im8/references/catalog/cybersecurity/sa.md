# SaaS Security (SA)

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/sa/
Page last updated: 10 November 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## SA-1 — Supplier Assessments and Reviews

### Statement

Seek an assessment by [ insert: param, sa-1_prm_1 ] on the risks associated with suppliers or contractors before using or subscribing to the service.

### Recommendations

Submit SaaS usage via the Request for SaaS FormSG and the data residency assessment outcome will be provided within 3 working days.

### Risk statement

Failure to assess suppliers may introduce supply chain risks associated with data residency and jurisdiction.

### Parameters

| **ID** | **Type** | **Description** |
| --- | --- | --- |
| sa-1_prm_1 | Assessing party (str) | The party conducting the assessment. |

## SA-2 — SaaS Account Management Tool Validation Testing

### Statement

Conduct validation tests on systems managed through the account management tool.

### Recommendations

Validation tests should minimally verify that account provisioning can only be performed through the account management tool and not directly on the SaaS platform; accounts on the account management tool are disabled on their last day of authorised use; access to a SaaS is granted only after the account management tool validates that the user is an authorised user; and access rights granted to an account cannot be mapped to another account. Validation tests have to be conducted whenever there are changes that impact the management of accounts on SaaS.

### Risk statement

Failure to conduct validation testing of account management integrations with SaaS may result in unauthorised account provisioning, delayed deactivation, and improper access rights, increasing the likelihood of security breaches and unauthorised data access.

## SA-3 — SaaS WOG Credential Storage Restriction

### Statement

Do not store Agency WOG credentials, such as passwords and private keys, in the SaaS, except for WOG-managed identity management services.

### Recommendations

Implement secure credential management practices. Use approved identity federation.

### Risk statement

Storing WOG credentials in third-party SaaS platforms may result in credentials being exposed or compromised, increasing the risk of unauthorised access, data breaches, and misuse of critical security information.

## SA-4 — SaaS Provider Encryption or Bring Your Own Key (BYOK)

### Statement

Use strong cryptographic algorithms that are industry-recognised.

### Recommendations

Establish cryptographic key management procedures aligned with NIST SP 800-57. Regularly review and update cryptographic implementations based on NIST recommendations and emerging threats.

### Risk statement

Failure to implement proper encryption or manage keys securely may result in unauthorised access to sensitive data, increasing the risk of exposure and breach, particularly if encryption keys are compromised or mismanaged.

## SA-5 — Attestation Report Review

### Statement

Review the [ insert: param, sa-5_prm_1 ] report every [ insert: param, sa-5_prm_2 ] day(s) and ensure that outstanding exceptions or findings are remediated.

### Recommendations

The scope of the attestation report should minimally cover the risk assessment, risk mitigation, logical and physical access controls, system operations and change management and should be perfomed by an independent third party.

### Risk statement

Without reviewing the audit report by an independent third party may pose security and compliance risks as there is no independent verification that the system meets industry standards relating to data management and security controls, which potentially lead to data breaches and reputational damage.

### Parameters

| **ID** | **Type** | **Description** |
| --- | --- | --- |
| sa-5_prm_1 | attestation report type (str) | The type of attestation report. |
| sa-5_prm_2 | time period (days) (int) | The time period in days for report review. |
