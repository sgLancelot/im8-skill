# AS — Application Security

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `as` | Controls: 14

Controls to prevent application vulnerabilities caused by insecure coding.

## AS-1 — Input Validation

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Validate all application inputs to ensure that they match the expected type, structure, or format.

**Guidance:** Strictly validating inputs against a comprehensive schema prevents injection attacks caused by inserting special characters or content that would cause the application to perform incorrect operations.

**Risk statement:** Without input validation, there's a heightened risk of injection attacks, data manipulation, or system crashes due to unexpected input, potentially leading to unauthorised access or disruption of services.

## AS-2 — Parameterised Interfaces

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use parameterised interfaces for database queries or system commands.

**Guidance:** Parameterised interfaces such Object-Relational Mapping (ORM) libraries ensure that parameters used in database queries or system commands are properly sanitised and prevent injection attacks.

**Risk statement:** Failure to use parameterised interfaces increases the vulnerability to SQL injection or command injection attacks, posing a significant risk of unauthorised access, data manipulation, or even potential system compromise.

## AS-3 — Output Sanitisation

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Sanitise all application outputs that will be used to render a HTML document.

**Guidance:** Any application outputs that are returned to the requester and used to render a HTML document can lead to cross-site scripting (XSS) attacks if they contain special characters that change the rendering of the HTML document by the browser.

**Risk statement:** Lack of sanitisation for application outputs used in rendering HTML documents exposes the system to the risk of cross-site scripting (XSS) attacks, allowing malicious code execution in users' browsers.

## AS-4 — Authentication Mechanism Rate-Limiting

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Apply rate-limiting on all authentication mechanisms to deter brute-force attacks.

**Guidance:** Consider rate-limiting to a maximum of 3 consecutive failed authentication attempts within 15 minutes or other reasonable rate limits. Time delays between log-on attempts reduce the risk of successful brute-forcing attacks. Bot mitigation tools such as CAPTCHA can further reduce this risk.

**Risk statement:** Without rate-limiting, there's an increased risk of unauthorised access as attackers may exploit weak credentials through repeated login attempts.

## AS-5 — Password Requirements

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Where SSO or passwordless is not supported, verify that user-defined passwords are at least [number of characters] characters in length and [policy].

**Guidance:** Latest NIST [SP 800-63B](#e59c5a7c-8b1f-49ca-8de0-6ee0882180ce) guidelines found that password length is a primary factor in determining the strength of a password while composition and complexity rules provide marginal security benefits.

**Risk statement:** Short or commonly used passwords increase the vulnerability to unauthorised access, potentially leading to compromised accounts and unauthorised activities on the system.

**Parameters:**

- `as-5_prm_1` — number of characters (type: int) — The minimum length of a password.
- `as-5_prm_2` — policy (type: str) — The password policy.

## AS-6 — Password Salting and Hashing

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Store passwords as salted hashes using a password hashing scheme that is resistant to offline attacks such as those described in NIST [SP 800-63b](#e59c5a7c-8b1f-49ca-8de0-6ee0882180ce). The salt should be:

1 Generated using a cryptographically secure pseudo-random number generator in accordance with industry standards;

2 At least 32 bits long; and

3 Randomly generated for each account.

**Guidance:** Refer to NIST [SP 800-90Ar1](#64357b22-9868-4453-9b9e-36c2665d12b3) for suitable pseudo-random number generators. Refer to NIST [SP 800-63b](#e59c5a7c-8b1f-49ca-8de0-6ee0882180ce) Memorized Secret Verifiers section for suitable hashing schemes, including Argon2, scrypt, and PBKDF2. For application source code, use a cryptographically secure pseudo-random number generator function instead of an insecure one, such as crypto.randomBytes instead of Math.random in Node.js and java.security.SecureRandom.nextBytes instead of java.util.Random in Java.

**Risk statement:** Without salting and hashing, in case of a data breach, exposed passwords can be easily extracted, leading to potential compromise of user accounts and sensitive information.

## AS-7 — Access Control Check Enforcement

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Perform access control checks on all authenticated requests.

**Guidance:** Utilise authorisation filters or middleware to force all authenticated requests to undergo access control checks.

**Risk statement:** Failure to perform access control checks on authenticated requests increases the risk of unauthorised access to sensitive data or functionalities, potentially leading to data breaches and misuse of system resources.

## AS-8 — Secrets Management

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Securely store secrets in an appropriate secrets management solution with access control enforcement, encryption, and monitoring.

**Guidance:** Secrets include API keys, access keys, and other static credentials. Do not store secrets unencrypted in source code or configuration files. Store secrets in cloud-native solutions like AWS Secrets Manager and Azure Key Vault or cloud-agnostic solutions like HashiCorp Vault and CyberArk Conjur. For SaaS or platforms, ensure that secrets are stored in an appropriate solution. For example, use GitHub Actions secrets instead of variables.

**Risk statement:** Exposure of sensitive information and unauthorised access to system credentials may occur if application secrets are stored insecurely or hard-coded in source code.

## AS-9 — Content Security Policy (CSP)

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Set minimally permissive CSP response headers to mitigate cross-site scripting attacks.

**Guidance:** Utilise the relevant fetch directives such as `default-src`, `script-src`, `style-src`, `connect-src`, `img-src`, `media-src` and `object-src` to prevent loading of scripts from malicious sources. Refer to the [OWASP Secure Headers Project](#3101b27c-d39c-49fc-b227-e77df8c5e358) Best Practices for recommended header values.

**Risk statement:** Without minimally permissive Content Security Policy (CSP) headers, the risk of cross-site scripting attacks, leading to unauthorised script execution and potential data theft, is increased.

## AS-10 — HTTP Strict Transport Security (HSTS)

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Set HTTP Strict Transport Security (HSTS) response headers with a maximum age value of at least 1 year (31536000 seconds) to mitigate protocol downgrade attacks.

**Guidance:** Refer to the [OWASP Secure Headers Project](#3101b27c-d39c-49fc-b227-e77df8c5e358) Best Practices for recommended header values.

**Risk statement:** Failure to implement HTTP Strict Transport Security (HSTS) with a sufficient maximum age may expose the system to protocol downgrade attacks, compromising the security of communication channels.

## AS-11 — Session Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Require users to re-authenticate after their session exceeds [time period (hours)] hour(s) or terminate the session.

**Guidance:** NIST SP 800-63B recommends re-authentication once per 30 days for Authenticator Assurance Level 1, 12 hours or 30 minutes inactivity for Authenticator Assurance Level 2, and 12 hours or 15 minutes inactivity for Authenticator Assurance Level 3. In addition to time period, system can consider re-authentication when roles, authenticators or credentials change or when the execution of privileged functions occurs.

**Risk statement:** Not verifying a user regularly and at suitable checkpoints could allow someone who has access to the user's account to carry out unauthorised actions.

**Parameters:**

- `as-11_prm_1` — time period (hours) (type: int) — The maximum time period in hours of a user's session.

## AS-12 — Malware Scanning of Uploaded Files

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Scan file uploads for malware before further processing by the system or users.

**Guidance:** Consider uploading the files to temporary storage for malware scanning on ephemeral compute like serverless functions before moving safe files to another storage for further processing or unsafe files to quarantine storage.

**Risk statement:** Without scanning uploaded files for malware, there's an increased risk of exploits or infection for consumers of the files.

## AS-13 — Exposure of Internal System Details

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Prevent the unnecessary disclosure of internal system details to end users.

**Guidance:** Ensure all system messages and notifications are informative yet secure. These messages should be contextually appropriate, providing end-users with relevant information without exposing internal system details such as debug information, stack traces, or software versioning.

**Risk statement:** Disclosure of internal system details or debug stack traces can expose vulnerabilities, software versions, and system architecture, potentially leading to targeted attacks, exploitation of known vulnerabilities, and unauthorised access to sensitive systems or data.

## AS-14 — Secure Cryptographic Libraries

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Use reputable and secure cryptographic libraries and functions to handle cryptographic operations.

**Guidance:** Follow the OWASP Cryptographic Storage Cheat Sheet for best practices in securely implementing cryptographic operations. Regularly update libraries and prefer widely recognized ones such as OpenSSL. Consider using libraries that are FIPS 140-2 or FIPS 140-3 compliant for enhanced security assurance.

**Risk statement:** Using insecure cryptographic libraries and functions can expose applications to significant security risks, such as data breaches and unauthorised access, compromising sensitive information.
