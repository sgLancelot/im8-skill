# AC — Access Control

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `ac` | Controls: 15

Controls to protect against unauthorised access to agency systems.

## AC-1 — Principle of Least Privilege

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Deny access by default and grant only the minimum permissions required for authorised accounts or processes to perform a specific function based on the account inventory implemented.

**Guidance:** Consider attribute- or feature-based access control for greater customisability and granularity. Use automated tools such as AWS IAM Access Advisor or Azure AD Access Review to assist with granular permission management.

**Risk statement:** Violating the principle of least privileges increases the risk of unauthorised access, privilege escalation, and potential security breaches due to unnecessary permissions, compromising the overall security posture.

## AC-2 — Multi-Factor Authentication (MFA)

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Require MFA for privileged accounts at login.

**Guidance:** Ensure that the authentication factors are different and independent of the accessing device. For additional security, consider MFA for privileged actions at the application level (such as step-up MFA challenges via PIM tools).

**Risk statement:** Without requiring phishing-resistant Multi-Factor Authentication (MFA) for remote access, there is an increased risk of unauthorised access, credential theft, and potential compromise of sensitive systems, especially for users with elevated privileges.

## AC-3 — Inactive and Expired Accounts

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Disable or remove [type] accounts within [time period (days)] day(s) from last day of authorised use or have not been used for [time period (days)] day(s).

**Guidance:** Use automated checks to identify accounts and credentials that should be disabled. Consider using automated workflows such as System for Cross-domain Identity Management (SCIM) or identity lifecycle management tools. For cloud service provider accounts, use tools such as AWS Config iam-user-unused-credentials-check to manage Identity and Access Management (IAM) users.

**Risk statement:** Failure to disable or remove unused accounts or credentials with elevated access increases the risk of unauthorised access, as dormant accounts may become targets for exploitation, compromising the security of the system.

**Parameters:**

- `ac-3_prm_1` — time period (days) (type: int) — The time period in days after account expiry.
- `ac-3_prm_2` — time period (days) (type: int) — The time period in days of account inactivity.
- `ac-3_prm_3` — type (type: str) — The type of accounts.

## AC-4 — Access Review

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Perform an access review [organisation-defined frequency] and remove unauthorised or unnecessary access rights within [time period (days)] day(s).

**Guidance:** For user accounts in applications, implement automated review workflows or reports. For cloud service provider accounts and roles, use tools such as AWS IAM Access Advisor or Azure AD Access Review to facilitate and manage access reviews.

**Risk statement:** Without regular access reviews and prompt removal of unauthorised or unnecessary access rights, there is an increased risk of lingering access, potential misuse of privileges, and compromised security, impacting the confidentiality and integrity of sensitive data.

**Parameters:**

- `ac-4_prm_1` — organisation-defined frequency (type: str) — The access review frequency.
- `ac-4_prm_2` — time period (days) (type: int) — The time period in days for access removal.

## AC-5 — Endpoint Device Hardening

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Require hardened endpoint devices for remote developer, maintainer, or administrator access.

**Guidance:** Use Endpoint Management platforms to continuously check and enforce device security posture and deny access if the hardening requirements are not met.

**Risk statement:** Without requiring hardened endpoint devices for remote access, there's an increased risk of compromised endpoints, potential malware infections, and security breaches, which could lead to unauthorised access and compromise the integrity of systems.

## AC-6 — Default Credentials

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Change default credentials prior to first use.

**Guidance:** Identify any default credentials used in any system components before deploying and change them. Configure end-user systems to prompt for password change on first login after account creation or reset.

**Risk statement:** Failure to change default credentials prior to first use increases the risk of unauthorised access, as default credentials are often well-known and targeted by attackers, compromising the security of the system or device.

## AC-7 — Singpass/Corppass for External Users

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use Singpass or Corppass MFA for digital services that require high level of identity assurance for external users.

**Guidance:** For high impact or high risk transactions, use Singpass/Corppass to identify external users (e.g. citizens). Internal users should use Government managed Single Sign-on (SSO) solutions (such as WOG AAD).

**Risk statement:** Leverage on Singpass or Corppass to reduce duplication of effort and provide consistent end user experience.

## AC-8 — Automated Account Lifecycle Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Automate account [process] for internal users using an account lifecycle management tool.

**Guidance:** Consider adopting Single Sign-On (SSO) with just-in-time provisioning or account lifecycle management protocols or tools such as [tool]. Perform validation testing of the integration between systems and tools to ensure that accounts are provisioned and/or deprovisioned in a timely manner. Where applicable, configure the system to enhance management capabilities via automation.

**Risk statement:** Manual account and access lifecycle management can introduce errors and weaknesses, thus making access control measures ineffective and unreliable.

**Parameters:**

- `ac-8_prm_1` — process (type: str) — The account lifecycle management processes to automate.
- `ac-8_prm_2` — tool (type: str) — Recommended account lifecycle management tool.

## AC-9 — Endpoint Device Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Implement and maintain an endpoint device management solution to ensure the security and integrity of endpoint devices used within the organisation.

**Guidance:** Mobile Device Management (MDM) platforms enable management, monitoring, and secure configuration of endpoint devices. This includes enforcing disk encryption, managing configuration, ensuring regular updates, and providing the ability to remotely wipe data in case of device loss or theft.

**Risk statement:** Unmanaged endpoint devices increase the risk of unauthorised access and potential loss of sensitive information due to the compromise of devices.

## AC-10 — Identity and Device-Based Access Control

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Adopt Identity and Device-Based Access Control for secure and context-aware connectivity to private organisational resources.

**Guidance:** Use solutions such as Secure Service Edge (SSE), Identity Aware Proxies (IAP) or other Zero Trust services (Entra ID Conditional Access, Okta Device Trust, etc) that integrate identity and device management systems to provide granular access control to resources based on user identity and device posture.

**Risk statement:** Relying on direct connections or traditional VPNs for remote access can lead to vulnerabilities, as they do not always incorporate strong identity and device-based security measures. This increases the risk of unauthorised access and potential data breaches.

## AC-11 — Single User Endpoints

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Assign each endpoint device to a single designated primary user and enforce the assignment to ensure accountability and enhance security monitoring.

**Guidance:** Implement measures such as user authentication and endpoint management with device enrolment to enforce the single primary user per endpoint. If secondary accounts for local device support or maintenance activities are used, consider securing them with endpoint privilege management tools.

**Risk statement:** Allowing multiple users to access a single endpoint device can lead to security risks such as data leakage, difficulty in tracking user activities, and increased vulnerability to insider threats.

## AC-12 — Single Sign-On (SSO) for Internal Services and Accounts

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use Single Sign-On (SSO) for internal services and accounts.

**Guidance:** Configure multi-factor authentication (MFA) at the Single-Sign On (SSO) identity provider (IdP) and ensure that access to the system is only granted after the IdP authenticates the user. WOG AAD is recommended for public officers and TechPass AAD for developers.

**Risk statement:** Without Single Sign-On (SSO), there is an increased risk of unauthorised access and compromised user credentials, as users may resort to using weak passwords or reusing credentials across multiple systems, thereby exposing sensitive information to potential security breaches.

## AC-13 — Static Credential Expiry and Rotation

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Rotate long-lived static credentials such as API keys, user access keys, and personal access tokens every [time period (days)] day(s) or use short-lived credentials.

**Guidance:** Automate credential rotation where possible. Consider short-lived alternatives to long-lived static credentials, such as AWS Security Token Service and IAM Identity Center authentication instead of IAM user access keys.

**Risk statement:** Failure to regularly rotate long-lived credentials or use short-lived credentials increases the risk of unauthorised access from stolen or unrevoked credentials.

**Parameters:**

- `ac-13_prm_1` — time period (days) (type: int) — The time period in days for credential rotation.

## AC-14 — Inventory of Accounts

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Establish and maintain an inventory of all accounts and their access rights managed within the system.

**Guidance:** Regularly review and update the account inventory to ensure accuracy and completeness. Implement automated tools where feasible to assist in tracking and managing accounts and their access rights.

**Risk statement:** Failure to maintain an accurate inventory of managed accounts increases the risk of unauthorised access, account misuse, and security breaches due to unmonitored or orphaned accounts.

## AC-15 — Validation Testing of Automated Account Lifecycle Management

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Conduct validation tests on the system integrated with account management tools to ensure secure integration.

**Guidance:** Where possible, test cases should include verifying that: account provisioning occurs solely through the account management tool(s), not directly on the SaaS; accounts are deactivated on the final day of authorised use; accounts are provisioned only after validating that access is permitted to the defined boundaries; and access rights match the account's assigned role and functions.

**Risk statement:** Failure to conduct validation tests on the integration of account management tools with SaaS platforms increases the risk of unauthorised access, improper account provisioning, and potential security breaches.
