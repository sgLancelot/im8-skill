# SC — Software Supply Chain

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `sc` | Controls: 9

Controls to prevent tampering and improve the integrity of the software supply chain.

## SC-1 — Code Repository

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Manage the codebase in a central code repository with version control.

**Guidance:** Use common internal platforms that provide Git repository services.

**Risk statement:** Absence of centralised code repository and version control increases the risk of code inconsistencies, loss of code history, and difficulties in collaboration, potentially leading to errors and security vulnerabilities.

## SC-2 — Commit Signing

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Configure the code repository to reject unsigned commits.

**Guidance:** Use GitLab's push rules, GitHub's branch protection rules or similar code repository controls to reject unsigned commits on push.

**Risk statement:** Allowing unsigned commits in the code repository introduces the risk of unauthorised or malicious code changes, compromising the integrity and security of the software development process.

## SC-3 — Peer Review

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Require peer review and approval by a designated reviewer before merging into the default branch.

**Guidance:** Use GitLab's protected branch and merge request settings, GitHub's branch protection settings or similar code repository controls to enforce this.

**Risk statement:** Without peer review and approval before merging, there is an increased risk of introducing undetected coding errors, security vulnerabilities, and maintaining codebase consistency may become challenging.

## SC-4 — Dependency Manifest Version Pinning

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Pin direct and transitive dependency versions in the application's dependency manifest.

**Guidance:** Dependency manifests such as package-lock.json for npm and Pipfile.lock for pipenv allow you to pin dependency versions.

**Risk statement:** Failure to pin direct and transitive dependency versions in the application's manifest may lead to version drift, introducing compatibility issues, security vulnerabilities, and unpredictability in the software environment.

## SC-5 — Build and Release Process

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use a consistent build and release process that generates a record of how the release artefact was built and deployed.

**Guidance:** Consider automated build and deploy tools such as CI/CD Pipelines, Infrastructure as Code (IaC) and other scripts, which allow for signing and validation of build artefacts. If automation is not possible, develop and implement release management processes.

**Risk statement:** Inconsistent and unmanaged releases may lead to configuration drift, increased likelihood of errors, and unapproved changes to releases.

## SC-6 — Dependency Installation during Deployment

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Only install pinned versions in the manifest when installing dependencies during deployment.

**Guidance:** Use package manager commands such as npm ci for npm and pipenv sync for pipenv that ensure only versions specified in the manifest are installed rather than the latest version.

**Risk statement:** Failure to install only pinned versions of dependencies during deployment increases the risk of introducing unforeseen changes, compatibility issues, and potential security vulnerabilities into the deployed environment.

## SC-7 — Software Artefact Signing

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Sign software artefacts such as code and container images using a trusted source during build.

**Guidance:** Use tools or services like Cosign or AWS Signer to sign and verify code.

**Risk statement:** Unsigned code and container images pose a risk of tampering, impersonation, and the injection of malicious code during the build process, compromising the integrity and security of the deployed software.

## SC-8 — Software Artefact Signature Verification

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Verify the signatures of code and artefacts before deployment or runtime.

**Guidance:** Implement a signature verification step such as a pipeline stage or Kubernetes Admission Controller.

**Risk statement:** Without verifying the signatures of code and artefacts before deployment or runtime, there's an increased risk of deploying tampered or malicious software, compromising the integrity and security of the system.

## SC-9 — Internal Code Collaboration and Sharing

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Share source code internally to enhance code quality, accelerate innovation, and improve problem-solving efficiency.

**Guidance:** Adopt InnerSource practices for internal collaboration, utilising Git platforms to manage and share code repositories internally. Source code should be evaluated for suitability for InnerSourcing, such as the use of confidential algorithms or embedded sensitive data. The InnerSource guidelines published in the Singapore Government Developer Portal provide a useful framework for code sharing.

**Risk statement:** Restricting code repositories to closed source can result in duplicated efforts, hinder collaborative learning, and lead to missed bugs or vulnerabilities.
