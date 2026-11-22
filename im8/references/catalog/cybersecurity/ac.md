# AC — Access Control

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `ac` | Controls: 22

Controls to protect against unauthorised access to agency systems.

## AC-1 — Principle of Least Privilege

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Deny access by default and grant only the minimum permissions required for authorised accounts or processes to perform a specific function based on the account inventory implemented.

**Guidance:** Consider attribute- or feature-based access control for greater customisability and granularity. Use automated tools such as AWS IAM Access Advisor or Azure AD Access Review to assist with granular permission management.

**Risk statement:** Violating the principle of least privileges increases the risk of unauthorised access, privilege escalation, and potential security breaches due to unnecessary permissions, compromising the overall security posture.

## AC-2 — Multi-Factor Authentication (MFA)

**Levels:** low-risk cloud: L1, medium-risk cloud: L1, high-risk cloud CII: L1, low-risk on-prem: L1, low-risk SaaS: L1, medium-risk SaaS: L1, sandbox: L2 *(portal text as of 10 November 2026)*

**Statement:** Require MFA for [account type] accounts at login.

**Guidance:** Ensure that the authentication factors are different and independent of the accessing device. For additional security, consider MFA for privileged actions at the application level (such as step-up MFA challenges via PIAM tools).

**Risk statement:** Without requiring phishing-resistant Multi-Factor Authentication (MFA) for remote access, there is an increased risk of unauthorised access, credential theft, and potential compromise of sensitive systems, especially for accounts with elevated privileges.

**Parameters:**

- `ac-2_prm_1` — account type (type: str) — The type of accounts.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-3 — Inactive and Expired Accounts

**Levels:** low-risk cloud: L0, medium-risk cloud: L0, high-risk cloud CII: L0, low-risk on-prem: L0, low-risk SaaS: L1, medium-risk SaaS: L1, sandbox: L2 *(portal text as of 10 November 2026)*

**Statement:** Disable or remove [type] accounts within [time period (days)] day(s) from last day of authorised use or have not been used for [time period (days)] day(s).

**Guidance:** Use automated checks to identify accounts and credentials that should be disabled. Consider using automated workflows such as System for Cross-domain Identity Management (SCIM) or identity lifecycle management tools. For cloud service provider accounts, use tools such as AWS Config iam-user-unused-credentials-check to manage Identity and Access Management (IAM) Users. For accounts belonging to members of public, there is no need to disable accounts after a period of inactivity. For SaaS, in cases where disabled accounts cannot be removed, revoke the access rights of these disabled accounts.

**Risk statement:** Failure to disable or remove unused accounts or credentials with elevated access increases the risk of unauthorised access, as dormant accounts may become targets for exploitation, compromising the security of the system.

**Parameters:**

- `ac-3_prm_1` — time period (days) (type: int) — The time period in days after account expiry.
- `ac-3_prm_2` — time period (days) (type: int) — The time period in days of account inactivity.
- `ac-3_prm_3` — type (type: str) — The type of accounts.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

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

**Levels:** low-risk cloud: L1, medium-risk cloud: L1, high-risk cloud CII: L1, low-risk on-prem: L1, low-risk SaaS: L1, medium-risk SaaS: L1, sandbox: L2 *(portal text as of 10 November 2026)*

**Statement:** Establish and maintain an inventory of all accounts and their access rights managed within the system.

**Guidance:** Regularly review and update the account inventory to ensure accuracy and completeness. Implement automated tools where feasible to assist in tracking and managing accounts and their access rights. For SaaS, document and implement processes for the management of interactive accounts. The documentation shall include the roles and responsibilities of the Access Rights Coordinator, an access control matrix to identify accounts or roles with excessive privileges, processes for identifying privileged accounts, and procedures for creating, enabling, modifying, disabling, removing, and reviewing accounts and their access rights. It shall also cover procedures to handle staff movement scenarios, including resignation or retirement, termination, role changes within the agency, and extended leave.

**Risk statement:** Failure to maintain an accurate inventory of managed accounts increases the risk of unauthorised access, account misuse, and security breaches due to unmonitored or orphaned accounts.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-15 — Validation Testing of Automated Account Lifecycle Management

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Conduct validation tests on the system integrated with account management tools to ensure secure integration.

**Guidance:** Where possible, test cases should include verifying that: account provisioning occurs solely through the account management tool(s), not directly on the SaaS; accounts are deactivated on the final day of authorised use; accounts are provisioned only after validating that access is permitted to the defined boundaries; and access rights match the account's assigned role and functions.

**Risk statement:** Failure to conduct validation tests on the integration of account management tools with SaaS platforms increases the risk of unauthorised access, improper account provisioning, and potential security breaches.

## AC-18 — Unauthorised Accounts

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Immediately disable and remove accounts that are identified as unauthorised and have not been approved for use.

**Guidance:** Integrate account management tools with SaaS platforms to enable centralised visibility and control of user accounts where feasible. or leverage the platform’s native account management features if integration is not available.

For SaaS platforms utilised by public officers, CAM (Centralized Account Management) ensures security and compliance by automatically removing or disabling user accounts whenever there are changes in the officers’ movement records. This includes situations where an officer leaves the service, transfers to a different department, or takes an extended leave of absence.

Perform periodic reviews of user accounts to identify and remove unauthorised or unnecessary access.

Maintain audit logs of account status changes to support monitoring and accountability.

**Risk statement:** Failure to remove unauthorised accounts may result in such accounts remaining active and being exploited, increasing the risk of unauthorised access and data breaches.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-19 — Account Provisioning Control Validation

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Where an account management tool is deployed, validate that accounts can only be provisioned through the tool.

**Guidance:** For Agency that implements account management tool to manage accounts for its system/platform, configure the system/platform to disable or remove all direct account provisioning capabilities, so that accounts cannot be created outside of the account management tool. Validation testing should attempt to provision an account directly on the SaaS platform without invoking the account management tool and confirm that the attempt is blocked or results in a non-functional account. Reassessment is required whenever changes are made to the SaaS integration or account management tool configuration.

Exception: Direct account provisioning on the system/platform may be permitted for designated break-glass or emergency accounts, where such accounts are required to recover or administer the system/platform in the event that the account management tool, single sign-on (SSO), or supporting identity services are unavailable. Such accounts should be limited in number, subject to enhanced monitoring and controls, and used only for emergency recovery or administrative purposes.

**Risk statement:** Direct provisioning on a system/platform bypasses centralised identity governance, creating unmanaged accounts that are invisible to the account management tool. Such shadow accounts cannot be subject to lifecycle controls (e.g., timely disablement, access reviews), increasing the risk of unauthorised access, privilege accumulation, and undetected account misuse.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-20 — Account Deprovisioning Control Validation

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Where an account management tool is deployed, validate that accounts are disabled through on the last day of authorised use.

**Guidance:** For Agency that implements account management tool to manage accounts for its system/platform, simulate an account reaching its last day of authorised use and confirm that the account is disabled on the account management tool by end of that day, with the corresponding system/platform access revoked. Test cases should cover staff movement scenarios including resignation, termination, role change, and extended leave.

**Risk statement:** Accounts that remain active beyond their authorised period create a window for unauthorised access, whether through continued use by the departing user or exploitation by a third party. Where the account management tool governs access, failure to disable accounts promptly at the point of authorisation expiry undermines the entire access lifecycle control. This risk is heightened for privileged accounts and systems processing sensitive government data.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-21 — Access Authorisation Control Validation

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Where an account management tool is deployed, validate that access to the system/platform is granted only after the account management tool validates that the user is an authorised user.

**Guidance:** For Agency that implements account management tool to manage accounts for its system/platform, simulate access attempts under the following scenarios and confirm that access is denied in all cases where the account management tool has not validated the user as authorised. This can include: (i) A user whose account exists on the system/platform but has not been provisioned through the account management tool. (ii) A user whose account has been disabled through the account management tool. Confirm that all authentication methods associated with the account, including interactive login, API tokens, personal access tokens (PATs), OAuth credentials, and other persistent authentication credentials, are revoked or rendered unusable (iii) A user attempts to authenticate through an unauthorised authentication path (e.g. direct local system/platform authentication where SSO is mandated or another authentication mechanism outside the approved identity management workflow), and confirm that access is denied.

**Risk statement:** Granting system/platform access without validation by the account management tool breaks the authorisation chain, allowing users who may have had their access revoked, modified, or never formally approved to gain entry. This creates a direct risk of unauthorised access to government data and services, and undermines the integrity of the entire identity and access management framework governing the system/platform.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-22 — Access Rights Binding Control Validation

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Where an account management tool is deployed, validate that access rights assigned to an account cannot be mapped or inherited by another account.

**Guidance:** For Agency that implements account management tool to manage accounts for its system/platform, verify that access grants to any account must originate from the account management tool’s authorisation workflow and no system/platform mechanism (clone, copy, bulk-assign, API) may be used to grant access that hasn’t been authorised through the tool.

**Risk statement:** Allowing access rights to be mapped from one account to another creates a pathway for unintended privilege escalation, where a lower-privileged account could inherit elevated rights from another. This undermines the principle of least privilege and breaks the traceability of access rights to individually authorised users. In a SaaS context, this risk is compounded by the difficulty of detecting such mappings without centralised visibility through the account management tool.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-23 — Password Reuse Restrictions

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Prohibit password reuse for a minimum of [minimum password generations] generations.

**Guidance:** Configure password policies to enforce a minimum password history of at least three previous passwords.

Prevent users from reusing recent passwords when setting or resetting passwords.

Apply password history settings consistently across all systems and identity providers.

Monitor password policy enforcement to ensure compliance with defined requirements.

**Risk statement:** Failure to enforce password reuse restrictions increases the risk of account compromise due to repeated use of previously exposed or weak passwords.

**Parameters:**

- `ac-23_prm_1` — minimum password generations (type: int) — The minimum number of previous passwords that cannot be reused.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/

## AC-24 — Account Lockout on Failed Authentication Attempts

**Levels:** low-risk SaaS: L1, medium-risk SaaS: L1 *(portal; added 10 Nov 2026)*

**Statement:** Lock the system account upon [consecutive failed attempts threshold] consecutive failed authentication attempts.

**Guidance:** Configure account lockout policies to enforce lockout after a defined number of consecutive failed authentication attempts.

Define appropriate lockout duration and reset conditions to balance security and usability.

Apply lockout policies consistently across all systems and identity providers.

Monitor authentication attempts and account lockouts to detect potential brute force or credential stuffing attacks.

**Risk statement:** Failure to enforce account lockout controls increases the risk of account compromise due to brute force or repeated unauthorised authentication attempts.

**Parameters:**

- `ac-24_prm_1` — consecutive failed attempts threshold (type: str) — The number of consecutive failed authentication attempts before account lockout.

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ac/
