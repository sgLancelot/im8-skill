# LM — Logging and Monitoring

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `lm` | Controls: 20

Controls to support detection and response to security and operations incidents.

## LM-1 — Separate Log Storage

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Store logs in a different system or system component than the system component that generated the logs.

**Guidance:** Do not store logs only in the same system component that generated it. For example, an application server on EC2 or ECS should send logs to a separate storage such as an S3 bucket as soon as possible after the logged event instead of only storing it on the server. For cloud audit logs, store them in a separate system or account.

**Risk statement:** Storing logs in a repository separate from the system component reduces the risk of tampering, unauthorised access, and manipulation of logs if the system component is compromised.

## LM-2 — Tamper-Resistant Log Storage

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Protect logs from unauthorised access, modification, and deletion.

**Guidance:** Apply access control policies to logs based on the principle of least privilege. As far as possible, only read access should be granted. Logs sent to GCC Central Logs are tamper-resistant.

**Risk statement:** Without protection measures, logs are susceptible to unauthorised access, modification, or deletion, leading to the risk of tampering, loss of crucial audit information, and compromised forensic analysis capabilities during security incidents.

## LM-3 — Network Flow Logging

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Log network traffic going to and from network interfaces.

**Guidance:** Enable VPC Flow Logs for AWS or its equivalents.

**Risk statement:** Failing to log network traffic going to and from network interfaces increases the risk of overlooking suspicious activities, potential security breaches, and the inability to trace and investigate network-related incidents effectively.

## LM-4 — Audit Logging

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Log management and audit events.

**Guidance:** For cloud, configure CloudTrail for AWS or its equivalents to log management and audit events such as changes to accounts, access, IAM policies and resources. For SaaS and COTS, enable audit logging features.

**Risk statement:** Neglecting to log and manage audit events increases the risk of undetected security incidents, compromises visibility into system activities, and hinders effective forensic analysis and compliance monitoring.

## LM-5 — Database Logging

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Log database audit events.

**Guidance:** Enable RDS logging for AWS or its equivalents.

**Risk statement:** Neglecting to log database audit events raises the risk of overlooking unauthorised activities, compromises in data security, and hinders the ability to track and investigate security incidents or compliance violations within the database environment.

## LM-6 — Access Logging

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Log access requests sent to web application firewalls, load balancers, proxies or web servers.

**Guidance:** Enable AWS WAF logging, Application Load Balancer logging, API Gateways, or their equivalents.

**Risk statement:** Failure to log access requests sent to web application firewalls, load balancers, proxies, or web servers increases the risk of overlooking potential security threats, unauthorised access attempts, and compromises visibility into the traffic that could lead to security incidents.

## LM-7 — Host Security Event Logging

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Log security events on hosts.

**Guidance:** Host security events include operating system security events, authentication, and endpoint detection and response alerts, configuration changes, and account and access rights changes.

**Risk statement:** Neglecting to log security events on hosts increases the risk of undetected security incidents, compromises incident response capabilities, and hinders forensic analysis, limiting the ability to identify and mitigate potential threats.

## LM-8 — Security Log Retention

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Retain security logs for at least [time period (days)] day(s).

**Guidance:** Security logs include network flow logs, cloud management logs, access logs, database logs and host logs. Retain non-security logs (e.g. application, operations and performance logs) as long as needed for incident resolution and debugging. Consider log lifecycle management automation, such as Amazon S3 Lifecycle configurations.

**Risk statement:** Failure to retain security logs increases the risk of losing crucial historical data, hindering investigations, compliance audits, and the ability to identify and respond to security incidents that occurred beyond a limited timeframe.

**Parameters:**

- `lm-8_prm_1` — time period (days) (type: int) — The time period in days of log retention.

## LM-9 — Security Monitoring and Alerting

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Configure security monitoring to identify potential security violations or breaches and send automated alerts, and respond to them accordingly.

**Guidance:** Enable Amazon GuardDuty, Microsoft Azure Security Center, or their equivalents.

**Risk statement:** Without configuring security monitoring to identify potential security violations or breaches and send automated alerts, there's an increased risk of delayed or unnoticed security incidents, hindering timely response and mitigation efforts to protect the system from further compromise.

## LM-10 — Resource Usage Monitoring and Alerting

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Configure resource usage monitoring to identify abnormal usage and send automated alerts.

**Guidance:** Configure Amazon CloudWatch alarms, Azure Monitor alerts, or their equivalents to identify abnormal usage such as spike in usage, access to resources during unexpected hours, and excessive charges.

**Risk statement:** Lack of resource usage monitoring with automated alerts increases the risk of overlooking abnormal usage patterns, potential resource abuse, and compromises in system performance, hindering the ability to proactively address issues and prevent service disruptions.

## LM-11 — Service Level Monitoring and Alerting

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Monitor, maintain and alert on service level objectives (SLOs) and indicators (SLIs) to ensure consistent service performance, availability and reliability.

**Guidance:** Implement a comprehensive monitoring system that tracks key SLIs and evaluates them against defined SLOs. This will help in identifying potential service level breaches early and take proactive measures to maintain service quality. Examples include CloudWatch metrics and alerts, Amazon Route 53 health checks, Azure Monitor Application Insights, or their equivalents.

**Risk statement:** Without effective service level monitoring to identify potential application or service degradation and send automated alerts, there is a risk of failing to meet service availability standards, which could result in user dissatisfaction and reduced reliability.

## LM-12 — Central Security Log Management and Monitoring

**Levels:** low-risk: L0, medium-risk: L0

**Statement:** Centralise security log management and monitoring with [service].

**Guidance:** Tenants on Government Commercial Cloud (GCC) already have Cloud Service Provider (CSP) tenant security logs stored centrally and available for forwarding to Government Cyber Security Operations Centre (GCSOC). Contact GCSOC for subscription and additional services.

**Risk statement:** Lack of central security log management and monitoring increases the risk of delayed or unnoticed security incidents, hindering effective response, and compromising the overall cybersecurity posture.

**Parameters:**

- `lm-12_prm_1` — service (type: str) — The central security log management and monitoring service.

## LM-13 — Anomalous Database Activity Monitoring

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Monitor database activities for anomalous activity.

**Guidance:** Configure database activity monitoring tools, such as RDS Activity Streams or similar mechanisms, to detect and alert on unusual authentication attempts, abnormal read or write operations, or other anomalous database activity.

**Risk statement:** Neglecting to monitor database activities for anomalous behaviour increases the risk of undetected security threats, unauthorised access, and compromises in data integrity, hindering the ability to identify and respond to potential database-related incidents.

## LM-14 — Web Defacement Monitoring

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Plan for and implement measures to detect and recover from web defacements.

**Guidance:** The Government Cyber Security Operations Centre (GCSOC) offers centralised monitoring of web defacements of internet-facing systems.

**Risk statement:** Failure to detect and respond to web defacement promptly will lead to prolonged disruption to services.

## LM-15 — Structured Log Formatting

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Publish logs in a consistent, structured format that aligns with industry standards for easy parsing and analysis.

**Guidance:** For security logs, implement or transform to OCSF (Open Cybersecurity Schema Framework), ECS (Elastic Common Schema) or similar schemas to standardise log formats for better threat detection and analysis. For operational logs, adopt OpenTelemetry or structured JSON formats to facilitate clear, structured, and efficient log analysis for system performance and diagnostics. Consistent log formatting aids in automated parsing and helps in integrating logs from various sources.

**Risk statement:** Inconsistent or unstructured log formatting can lead to difficulties in log analysis and monitoring, potentially resulting in missed critical events or delayed response to system anomalies.

## LM-16 — Key Signals Monitoring

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Monitor key user-facing signals to maintain robust service health and performance.

**Guidance:** Implement monitoring of key signals such as latency, traffic, errors, and saturation (the 4 Golden Signals). Regularly track and analyse these indicators for proactive issue detection and resolution. Use this data to identify trends and areas for system improvement, ensuring continuous enhancement in service quality and reliability.

**Risk statement:** Inadequate monitoring of key user-facing signals such as latency, traffic, errors, and saturation can lead to suboptimal service performance, adversely impacting user experience, system efficiency, and increasing the likelihood of system failures. This oversight can significantly detract from service reliability and user satisfaction.

## LM-17 — Software delivery performance monitoring

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Measure and analyse software delivery performance to optimise development velocity and operational efficiency.

**Guidance:** Implement tools and processes to track Deployment Frequency, Lead Time for Changes, Change Failure Rate, and Time to Restore Service (the DORA 4 Key metrics). Use these metrics as benchmarks to drive continuous improvement in the software development and deployment process, enhancing agility, reliability, and responsiveness to changes.

**Risk statement:** Failing to measure and improve the software delivery performance can lead to inefficient development processes, reduced software quality and longer recovery times.

## LM-18 — Whole of Government Application Analytics (WOGAA)

**Levels:** low-risk: not in baseline, medium-risk: not in baseline

**Statement:** Implement Whole of Government Application Analytics (WOGAA) in public facing digital services.

**Guidance:** Register at the WOGAA portal at https://wogaa.sg/ and follow the implementation documentation at https://docs.wogaa.sg/.

**Risk statement:** Lack of performance tracking can lead to gaps in service delivery.

## LM-19 — Log Sanitisation

**Levels:** low-risk: L2, medium-risk: L1

**Statement:** Sanitise logs to protect classified and sensitive data before it is recorded in any logging system or shared to any third party.

**Guidance:** Identify types of classified and sensitive data that may appear in logs. When logging, consider using sanitisation techniques like masking or tokenisation. This ensures that sensitive information — such as PII, credentials, API keys, and payment details — are not stored in plaintext during log collection.

**Risk statement:** Failing to sanitise logs increases the risk of unauthorised exposure or misuse of sensitive information and other confidential data. This exposure could lead to privacy breaches, financial losses, compliance violations and damage to national reputation.

## LM-20 — User and Entity Behaviour Analytics

**Levels:** low-risk: L2, medium-risk: not in baseline

**Statement:** Implement User and Entity Behaviour Analytics (UEBA) to monitor and analyse user activities for suspicious behaviour and potential threats.

**Guidance:** Select a UEBA tool that integrates with existing security information and event management (SIEM) solutions and provides real-time alerts for anomalous activities. Ensure regular updates and tuning of the tool to enhance detection capabilities.

**Risk statement:** Lack of monitoring for potentially malicious user and entity behaviour increases the risk of insider threats and undetected malicious activities, potentially leading to data breaches and system compromise.
