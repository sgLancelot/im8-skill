# IS — Infrastructure Security

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `is` | Controls: 14

Controls to secure infrastructure that host applications, services, and data.

## IS-1 — Management Agents

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Install CSP management agents on hosts to remotely and securely manage their configurations.

**Guidance:** Most CSP compute instances preinstall management agents (e.g., AWS Systems Manager Agent, Azure Windows VM Agent) by default. If the image does not come with the preinstalled agent, install manually.

**Risk statement:** Without installing management agents on hosts, there is an increased risk of manual misconfigurations, difficulty in maintaining consistent configurations, and potential security vulnerabilities due to reduced visibility and ability to manage hosts effectively.

## IS-2 — Automated Patch Management Tools

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use automated patch management tools to facilitate security patching of operating systems and software included in the operating systems.

**Guidance:** Patch management can be automated as part of the build and deploy phase, such as with golden images for containers and virtual machines. It can also be automated in running instances on the cloud via CSP node management services (such as Azure Update Manager or AWS Systems Manager Patch Manager) and on-premises via patch management services (such as Windows Server Update Services or Configuration Management tools). To minimise risk of disruption due to patching, consider staged rollouts with canary deployments or in non-production environments.

**Risk statement:** Failure to automate security patching of operating systems and included software increases the risk of delayed or missed security updates, leaving systems vulnerable to known exploits and potential security breaches, compromising the overall security of the environment.

## IS-3 — Restricted Administrator Privileges

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Restrict administrator privileges by disabling remote login for the root/administrator user and restricting sudo/administrators group access for other users.

**Guidance:** Further reduce the attack surface by running common services such as the web server or database without root/administrator/system privileges.

**Risk statement:** Without restricting administrator privileges, there is an increased risk of unauthorised access, privilege escalation, and potential security breaches, compromising the integrity and security of the system.

## IS-4 — Least Functionality

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Disable or remove unnecessary functions, system ports, protocols, software, and services on the host.

**Guidance:** Follow the principle of least functionality to configure the host to carry out only its intended purpose. CSP node management services can provide an inventory of software and services (e.g., AWS Systems Manager Inventory). Vulnerability assessment scanners (e.g., AWS Inspector) can also identify software vulnerabilities and network exposure.

**Risk statement:** Failure to disable or remove unnecessary functions, system ports, protocols, software, and services on the host increases the attack surface, potential vulnerabilities, and the risk of exploitation, compromising the overall security and performance of the system.

## IS-5 — Host System Hardening

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Harden the host configuration with reference to industry standards.

**Guidance:** Select the appropriate benchmark for the host such as from the [NIST National Checklist Program](#521952dd-5c57-4277-a069-4dae6bc0c28d) or [CIS Benchmarks](#09ba067b-8923-4f22-bb31-b8619edcaa07). Automate the configuration process or use hardened images instead of manually configuring.

**Risk statement:** Without hardening the operating system configuration according to industry standards, there's an increased risk of security vulnerabilities, unauthorised access, and potential exploitation, compromising the overall security posture and resilience of the operating system.

## IS-6 — Remote Administration

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Use remote administration tools to control and monitor remote access.

**Guidance:** Prioritise remote administration tools (e.g., AWS Systems Manager Session Manager, AWS Systems Manager Fleet Manager) over direct SSH or RDP. If SSH is still required and remote administration tools are not available, use it only within a private non-production environment such as an encrypted tunnel and authenticate with short-lived certificates. Document and remediate gaps in monitoring and automation to minimise the need for remote access.

**Risk statement:** Using remote administration tools enhances security by providing controlled and audited access, reducing the risk of unauthorised activities, and improving overall management of privileged identities.

## IS-7 — Malware Protection

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Detect and quarantine malware on hosts with anti-malware tools.

**Guidance:** Configure anti-malware tools for all compute hosts, preferably leveraging cloud-native services where available. These tools should be kept up-to-date with the latest malware signatures. Regular scans should be scheduled to detect and quarantine potential threats.

**Risk statement:** Without malware protection, there's an increased risk of undetected malicious activities, potential data breaches, and compromise of host systems, highlighting the importance of proactive measures to ensure the security and integrity of the environment.

## IS-8 — Endpoint Detection and Response (EDR)

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Monitor security threats on hosts with an EDR tool.

**Guidance:** Implement EDR tools for all compute hosts. Security incident response should be planned and documented for the tool. EDR tools with built-in malware protection should be favoured to reduce additional agents.

**Risk statement:** Failure to monitor security threats on hosts with an Endpoint Detection and Response (EDR) tool increases the risk of undetected advanced threats, compromises in host security, and delayed response to potential security incidents, highlighting the need for continuous monitoring and proactive threat detection.

## IS-9 — End-of-Support (EOS) Assets

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Ensure deployed [type] assets have not reached end-of-support (EOS). Use of EOS assets will require risk acceptance by approved authority.

**Guidance:** Identify, track and replace EOS assets in a timely manner. Regularly review assets to identify upcoming EOS timeframe and replace them ahead of EOS date.

**Risk statement:** EOS assets can introduce security vulnerabilities as the assets are no longer provided with security fixes.

**Parameters:**

- `is-9_prm_1` — type (type: str) — The type of asset.

## IS-10 — Synchronise time clocks

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Synchronise internal clocks to a common reference time source.

**Guidance:** Use common time source such as Network Time Protocol (NTP). In the cloud, it is recommended to use the default time sources provided by the CSPs.

**Risk statement:** The lack of synchronised clocks introduces significant risks, including increased security vulnerabilities, data integrity issues, and challenges in troubleshooting.

## IS-11 — Central Domain Name Registration

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Register .gov.sg and .edu.sg domain names with GovTech as the sole registrar.

**Guidance:** Use the Whole of Government Domain Name Server (DNS) portal on the IT Service Management (ITSM) portal to register domain names. While the root level of the domain must be registered with ITSM, the use of subdomain delegation to external DNS Services (e.g. AWS Route53, Cloudflare DNS, etc) is allowed.

**Risk statement:** Improper management of domain names increase the risk of phishing attacks or domain takeovers.

## IS-12 — DNS Security Extensions (DNSSEC)

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Implement DNS Security Extensions (DNSSEC) for public DNS records and servers.

**Guidance:** DNS services such as WOG DNS, Amazon Route 53 and Cloudflare support DNSSEC configuration.

**Risk statement:** Insecure domain name resolution can lead to man-in-the-middle attacks caused by DNS spoofing or DNS cache poisoning.

## IS-13 — Defensive Domain Name Registration

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Register second (.sg) and third (.com.sg, .org.sg, .net.sg, .edu.sg) level domain name variants of the system's primary domain name.

**Guidance:** Consider defensive registration of domain names with typographical variants of the system's primary domain name. The Whole of Government Domain Name Server (DNS) portal on the IT Service Management (ITSM) portal automatically includes the second and third level domain names.

**Risk statement:** Malicious use of domain names similar to actual Government domain names increases the risk of phishing and spoofing.

## IS-14 — Singapore SMS Sender ID Registry Registration

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Register and use whitelisted SMS Sender IDs with the Singapore SMS Sender ID Registry for sending SMSes to members of the public.

**Guidance:** Agencies must use the "gov.sg" Sender ID via the Postman tool to send SMSes to members of the public unless exempted. Whitelist Sender IDs used to send SMSes and blacklist Sender IDs which are variants of the whitelisted Sender IDs, agency names, or names of services.

**Risk statement:** Lack of Sender ID registration allows malicious entities to spoof legitimate Government SMSes.
