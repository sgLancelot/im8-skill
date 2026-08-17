# CK — Cryptography, Encryption and Key Management

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `ck` | Controls: 3

Controls to secure cryptographic protocols.

## CK-1 — Cryptographic Key Establishment

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Use industry-standard cryptographic key establishment schemes and key derivation methods.

**Guidance:** Refer to [SP 800-56A](#ae501bfa-d6e9-4f29-990b-11b3bf82c606), [SP 800-56B](#c5aa6da6-83ac-41e6-b4b7-fa898461e761), and [SP 800-56C](#1208c023-833f-40be-a901-5a271adcae2f) for updated industry-standard cryptographic key establishment schemes and key derivation methods. Cloud services such as AWS Key Management Service and Azure Key Vault can be used for generating and managing cryptographic keys.

**Risk statement:** Insecure cryptographic key establishment can lead to weak or broken encryption.

## CK-2 — Cryptographic Key Rotation

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Rotate cryptographic keys every [time period (days)] days.

**Guidance:** Cloud services such as AWS Key Management Service and Azure Key Vault enable automatic rotation of cryptographic keys.

**Risk statement:** Failing to rotate cryptographic keys increases the risk of broken encryption.

**Parameters:**

- `ck-2_prm_1` — time period (days) (type: int) — The time period in days of cryptographic key rotation frequency.

## CK-3 — Cryptographic Key Management

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Implement cryptographic key management processes to ensure cryptographic keys are well-managed and safeguarded throughout their lifecycle.

**Guidance:** Follow key management practices such as those described in NIST SP 800-57 or ISO/IEC 27017 to cover aspects including generation, registration, storage, distribution, installation, use, rotation, backup, recovery, revocation, suspension, and destruction of keys.

**Risk statement:** Inadequate key management increase the risk of unauthorised access, data breaches, and compromised cryptographic operations due to poorly managed or safeguarded cryptographic keys.
