# SD — Secure Development

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `sd` | Controls: 8

Controls to secure the development pipeline and perform source code quality assurance.

## SD-1 — Push Protection for Secrets

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Configure the code repository to prevent secrets from being pushed to the repository.

**Guidance:** Use GitLab's push rules or GitHub's push protection to reject secrets on push.

**Risk statement:** Failure to configure the code repository to prevent secrets from being pushed introduces the risk of inadvertent exposure, unauthorised access, and potential misuse of sensitive information, compromising the security of the codebase and associated systems.

## SD-2 — Default Branch Push Permissions

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Configure the code repository to prevent pushes (including force pushes) to the default branch.

**Guidance:** Use GitLab's protected branch and merge request settings or GitHub's branch protection settings to enforce this.

**Risk statement:** Without configuring the code repository to prevent pushes, including force pushes, to the default branch, there's an increased risk of unintentional or malicious changes, potential loss of code history, and compromised version control, impacting the integrity and reliability of the software development process.

## SD-3 — Continuous Integration (CI) Tests

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Require Continuous Integration (CI) tests to pass before merging into the default branch.

**Guidance:** Use GitLab's protected branch and merge request settings or GitHub's branch protection settings to enforce this.

**Risk statement:** Failing to require passing Continuous Integration (CI) tests before merging into the default branch increases the risk of introducing faulty code, potential regressions, and compromise of code quality.

## SD-4 — Static Analysis

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Set up a static analysis job in the [CI/CD pipeline / static analysis platform], and remediate or risk accept true positive vulnerability findings before deploying to production.

**Guidance:** Static analysis tools (such as SAST or IaC security scanners) check source code for common vulnerabilities and misconfigurations. By running static analysis tools earlier in the DevSecOps cycle, vulnerabilities can be detected and prevented from being deployed to production.

**Risk statement:** Without setting up static analysis in the CI/CD pipeline for each merge request and addressing true positive vulnerability findings, there is an increased risk of deploying insecure code to the production branch, potentially leading to security breaches and compromise of the overall system.

**Parameters:**

- `sd-4_prm_1` — location (type: str) — choose one-or-more: CI/CD pipeline; static analysis platform The location where static analysis occurs.

## SD-5 — Dependency Scanning

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Schedule a scan at least every [time period (days)] day(s) in the [CI/CD pipeline / code repository / dependency scanning platform] to identify the use of vulnerable software libraries.

**Guidance:** Dependency scanning checks the source code for dependencies with known vulnerabilities. By running scans regularly using bots or software composition analysis (SCA) tools, vulnerabilities arising from outdated dependencies can be quickly detected and patched. Software composition analysis can be performed using tools such as Gitlab, Nexus IQ, or their equivalent, with output in a common SBOM format such as SPDX or CycloneDX.

**Risk statement:** Failing to schedule regular dependency scanning to identify vulnerable software libraries and address findings in a timely manner increases the risk of deploying applications with known vulnerabilities, potentially exposing the system to security exploits and compromise.

**Parameters:**

- `sd-5_prm_1` — time period (days) (type: int) — The time period in days of dependency scanning frequency.
- `sd-5_prm_2` — location (type: str) — choose one-or-more: CI/CD pipeline; code repository; dependency scanning platform The location where dependency scanning occurs.

## SD-6 — Secret Detection

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Set up secret detection in the [CI/CD pipeline / code repository / secret detection platform] and remediate true positives within [time period (days)] day(s).

**Guidance:** Ensure that the exposed secret is revoked and purged from the Git history.

**Risk statement:** Without setting up secret detection and addressing true positive findings promptly, there's an increased risk of exposing sensitive information, potential unauthorised access, and compromised security.

**Parameters:**

- `sd-6_prm_1` — location (type: str) — choose one-or-more: CI/CD pipeline; code repository; secret detection platform The location where secret detection occurs.
- `sd-6_prm_2` — time period (days) (type: int) — Number of days within which to remediate a secret detection true positive.

## SD-7 — CI Environment Variable Secrets Management

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Protect environment variable secrets used in CI jobs by limiting them to protected pipelines and masking them in job logs.

**Guidance:** Use GitLab's CI/CD variable security settings or GitHub's encrypted secrets with the add-mask workflow command.

**Risk statement:** Failing to protect environment variable secrets in CI jobs by limiting them to protected pipelines and masking them in job logs increases the risk of unauthorised access and exposure of sensitive information.

## SD-8 — Deployment Environment Segregation

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Segregate production and non-production environments including applications, services, data, secrets, roles, and networks.

**Guidance:** Achieve segregation using separate cloud tenant accounts for environments such as production, development, test, and staging. Account segregation enhances security by limiting exposure, simplifies resource and cost management, maintains configuration integrity, facilitates compliance and auditing and streamlines operational tasks. Deploy and operate environments as similarly as possible to enhance debugging and time-to-market.

**Risk statement:** Failure to segregate production and non-production environments increases the risk of unauthorised access, data leaks, and denial of service attacks, as compromises in non-production environments may lead to cascading impacts on production systems.
