# IM8 System Security Plan (SSP) Baselines

Compact index of every published SSP baseline: system category,
sensitivity ceiling, and the controls each baseline requires
(ID, title, profile level). Full control text lives in the
control-catalog reference files, not here.

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## Low-Risk Cloud

Source: https://info.standards.tech.gov.sg/ssp/low-risk-cloud/
Page last updated: 24 March 2026

System category: A generic system hosted on the cloud through a third-party Cloud Service Provider.

Sensitivity ceiling: Up to Restricted, Sensitive Normal

Controls (117):

| ID | Title | Profile level |
| --- | --- | --- |
| **AS: Application Security** | | |
| AS-1 | Input Validation | 1 |
| AS-2 | Parameterised Interfaces | 1 |
| AS-3 | Output Sanitisation | 1 |
| AS-4 | Authentication Mechanism Rate-Limiting | 1 |
| AS-5 | Password Requirements | 1 |
| AS-6 | Password Salting and Hashing | 1 |
| AS-7 | Access Control Check Enforcement | 1 |
| AS-8 | Secrets Management | 1 |
| AS-9 | Content Security Policy (CSP) | 1 |
| AS-10 | HTTP Strict Transport Security (HSTS) | 2 |
| AS-11 | Session Management | 1 |
| AS-12 | Malware Scanning of Uploaded Files | 2 |
| AS-13 | Exposure of Internal System Details | 2 |
| AS-14 | Secure Cryptographic Libraries | 2 |
| AS-15 | Password Change | 1 |
| **SC: Software Supply Chain** | | |
| SC-1 | Code Repository | 1 |
| SC-2 | Commit Signing | 2 |
| SC-3 | Peer Review | 1 |
| SC-4 | Dependency Manifest Version Pinning | 1 |
| SC-5 | Build and Release Process | 1 |
| SC-6 | Dependency Installation during Deployment | 1 |
| SC-7 | Software Artefact Signing | 2 |
| SC-8 | Software Artefact Signature Verification | 2 |
| SC-9 | Internal Code Collaboration and Sharing | 2 |
| **ST: Security Testing** | | |
| ST-1 | Vulnerability Assessment | 1 |
| ST-2 | Cloud Security Posture Management | 1 |
| ST-3 | Public Vulnerability Disclosure Programme | 1 |
| ST-4 | Security Testing Programme | 1 |
| ST-5 | Vulnerability Management | 1 |
| **NS: Network Security** | | |
| NS-1 | Network and System Component Segmentation | 1 |
| NS-2 | Access Restrictions on CSP Resources Outside Virtual Network | 1 |
| NS-3 | Deny by Default - Allow by Exception | 1 |
| NS-4 | Inter-Private Network Connectivity | 1 |
| NS-5 | Network and Application Layer Filtering | 1 |
| NS-6 | Valid and Trusted SSL/TLS Certificates | 1 |
| NS-7 | Secure Inter-Service Communication | 1 |
| NS-8 | Secure Cloud and On-Premises Connectivity | 1 |
| **BR: Backup and Recovery** | | |
| BR-1 | Backup | 1 |
| BR-2 | Recovery Testing | 2 |
| BR-3 | Backup Retention | 1 |
| **DP: Data Protection** | | |
| DP-1 | Data Residency | 0 |
| DP-2 | Data at Rest Encryption | 1 |
| DP-3 | Data in Transit Encryption | 1 |
| DP-4 | Central Cloud Tenant Management | 1 |
| **LM: Logging and Monitoring** | | |
| LM-1 | Separate Log Storage | 1 |
| LM-2 | Tamper-Resistant Log Storage | 1 |
| LM-3 | Network Flow Logging | 1 |
| LM-4 | Audit Logging | 1 |
| LM-5 | Database Logging | 2 |
| LM-6 | Access Logging | 1 |
| LM-7 | Host Security Event Logging | 1 |
| LM-8 | Security Log Retention | 1 |
| LM-9 | Security Monitoring and Alerting | 1 |
| LM-10 | Resource Usage Monitoring and Alerting | 1 |
| LM-11 | Service Level Monitoring and Alerting | 2 |
| LM-12 | Central Security Log Management and Monitoring | 0 |
| LM-13 | Anomalous Database Activity Monitoring | 2 |
| LM-14 | Web Defacement Monitoring | 2 |
| LM-15 | Structured Log Formatting | 2 |
| LM-16 | Key Signals Monitoring | 2 |
| LM-17 | Software delivery performance monitoring | 2 |
| LM-19 | Log Sanitisation | 2 |
| **AC: Access Control** | | |
| AC-1 | Principle of Least Privilege | 1 |
| AC-2 | Multi-Factor Authentication (MFA) | 1 |
| AC-3 | Inactive and Expired Accounts | 1 |
| AC-4 | Access Review | 1 |
| AC-5 | Endpoint Device Hardening | 1 |
| AC-6 | Default Credentials | 1 |
| AC-7 | Singpass/Corppass for Public Users | 1 |
| AC-8 | Automated Account Lifecycle Management | 1 |
| AC-9 | Endpoint Device Management | 1 |
| AC-10 | Identity and Device-Based Access Control | 2 |
| AC-11 | Single User Endpoints | 2 |
| AC-12 | Single Sign-On (SSO) for Internal Services and Accounts | 1 |
| AC-13 | Static Credential Expiry and Rotation | 2 |
| AC-14 | Inventory of Accounts | 1 |
| **CS: Container Security** | | |
| CS-1 | Unique Base Container Image Tags | 2 |
| CS-2 | Minimal Base Container Images | 2 |
| CS-3 | Runtime Container Secrets | 1 |
| CS-4 | Non-Privileged Container User | 1 |
| CS-5 | Dockerfile Linting | 2 |
| CS-6 | Read-Only Container Root Filesystem | 2 |
| CS-7 | Container Image Scanning | 1 |
| CS-8 | Private Container Image Registries | 2 |
| CS-9 | Container Orchestrator API Access Control | 1 |
| CS-10 | Container Workload Segmentation | 1 |
| CS-11 | Container Runtime Security | 2 |
| **PM: Security Programme Management** | | |
| PM-1 | Cybersecurity Incident Management Plan | 1 |
| PM-2 | Risk Assessment | 1 |
| PM-3 | System Security Plan (SSP) Development | 0 |
| PM-4 | Approval of Residual Risks | 0 |
| PM-5 | Central Submission of Approved System Security Plan (SSP) | 0 |
| PM-6 | System Documentation | 1 |
| **IS: Infrastructure Security** | | |
| IS-1 | Management Agents | 1 |
| IS-2 | Automated Patch Management Tools | 1 |
| IS-3 | Restricted Administrator Privileges | 1 |
| IS-4 | Least Functionality | 1 |
| IS-5 | Host System Hardening | 1 |
| IS-6 | Remote Administration | 1 |
| IS-7 | Malware Protection | 1 |
| IS-8 | Endpoint Detection and Response (EDR) | 2 |
| IS-9 | End-of-Support (EOS) Assets | 1 |
| IS-10 | Synchronise time clocks | 1 |
| IS-11 | Central Domain Name Registration | 0 |
| IS-12 | DNS Security Extensions (DNSSEC) | 2 |
| IS-13 | Defensive Domain Name Registration | 2 |
| IS-14 | Singapore SMS Sender ID Registry Registration | 0 |
| **SD: Secure Development** | | |
| SD-1 | Push Protection for Secrets | 1 |
| SD-2 | Default Branch Push Permissions | 1 |
| SD-3 | Continuous Integration (CI) Tests | 2 |
| SD-4 | Static Analysis | 1 |
| SD-5 | Dependency Scanning | 1 |
| SD-6 | Secret Detection | 1 |
| SD-7 | CI Environment Variable Secrets Management | 1 |
| SD-8 | Deployment Environment Segregation | 1 |
| **CK: Cryptography, Encryption and Key Management** | | |
| CK-1 | Cryptographic Key Establishment | 2 |
| CK-2 | Cryptographic Key Rotation | 2 |

## Medium-Risk Cloud

Source: https://info.standards.tech.gov.sg/ssp/medium-risk-cloud/
Page last updated: 24 March 2026

System category: A generic system hosted on the cloud through a third-party Cloud Service Provider.

Sensitivity ceiling: Confidential, Sensitive High

Controls (117):

| ID | Title | Profile level |
| --- | --- | --- |
| **AS: Application Security** | | |
| AS-1 | Input Validation | 0 |
| AS-2 | Parameterised Interfaces | 1 |
| AS-3 | Output Sanitisation | 0 |
| AS-4 | Authentication Mechanism Rate-Limiting | 1 |
| AS-5 | Password Requirements | 1 |
| AS-6 | Password Salting and Hashing | 1 |
| AS-7 | Access Control Check Enforcement | 0 |
| AS-8 | Secrets Management | 0 |
| AS-9 | Content Security Policy (CSP) | 1 |
| AS-10 | HTTP Strict Transport Security (HSTS) | 2 |
| AS-11 | Session Management | 1 |
| AS-12 | Malware Scanning of Uploaded Files | 2 |
| AS-13 | Exposure of Internal System Details | 2 |
| AS-14 | Secure Cryptographic Libraries | 2 |
| AS-15 | Password Change | 1 |
| **SC: Software Supply Chain** | | |
| SC-1 | Code Repository | 1 |
| SC-2 | Commit Signing | 2 |
| SC-3 | Peer Review | 1 |
| SC-4 | Dependency Manifest Version Pinning | 1 |
| SC-5 | Build and Release Process | 1 |
| SC-6 | Dependency Installation during Deployment | 1 |
| SC-7 | Software Artefact Signing | 2 |
| SC-8 | Software Artefact Signature Verification | 2 |
| SC-9 | Internal Code Collaboration and Sharing | 2 |
| **ST: Security Testing** | | |
| ST-1 | Vulnerability Assessment | 0 |
| ST-2 | Cloud Security Posture Management | 1 |
| ST-3 | Public Vulnerability Disclosure Programme | 0 |
| ST-4 | Security Testing Programme | 0 |
| ST-5 | Vulnerability Management | 1 |
| **NS: Network Security** | | |
| NS-1 | Network and System Component Segmentation | 0 |
| NS-2 | Access Restrictions on CSP Resources Outside Virtual Network | 1 |
| NS-3 | Deny by Default - Allow by Exception | 1 |
| NS-4 | Inter-Private Network Connectivity | 1 |
| NS-5 | Network and Application Layer Filtering | 0 |
| NS-6 | Valid and Trusted SSL/TLS Certificates | 1 |
| NS-7 | Secure Inter-Service Communication | 1 |
| NS-8 | Secure Cloud and On-Premises Connectivity | 1 |
| **BR: Backup and Recovery** | | |
| BR-1 | Backup | 0 |
| BR-2 | Recovery Testing | 1 |
| BR-3 | Backup Retention | 1 |
| **DP: Data Protection** | | |
| DP-1 | Data Residency | 0 |
| DP-2 | Data at Rest Encryption | 1 |
| DP-3 | Data in Transit Encryption | 1 |
| DP-4 | Central Cloud Tenant Management | 1 |
| **LM: Logging and Monitoring** | | |
| LM-1 | Separate Log Storage | 1 |
| LM-2 | Tamper-Resistant Log Storage | 1 |
| LM-3 | Network Flow Logging | 0 |
| LM-4 | Audit Logging | 0 |
| LM-5 | Database Logging | 1 |
| LM-6 | Access Logging | 0 |
| LM-7 | Host Security Event Logging | 1 |
| LM-8 | Security Log Retention | 1 |
| LM-9 | Security Monitoring and Alerting | 0 |
| LM-10 | Resource Usage Monitoring and Alerting | 1 |
| LM-11 | Service Level Monitoring and Alerting | 2 |
| LM-12 | Central Security Log Management and Monitoring | 0 |
| LM-13 | Anomalous Database Activity Monitoring | 2 |
| LM-14 | Web Defacement Monitoring | 2 |
| LM-15 | Structured Log Formatting | 2 |
| LM-16 | Key Signals Monitoring | 2 |
| LM-17 | Software delivery performance monitoring | 2 |
| LM-19 | Log Sanitisation | 1 |
| **AC: Access Control** | | |
| AC-1 | Principle of Least Privilege | 1 |
| AC-2 | Multi-Factor Authentication (MFA) | 0 |
| AC-3 | Inactive and Expired Accounts | 0 |
| AC-4 | Access Review | 1 |
| AC-5 | Endpoint Device Hardening | 0 |
| AC-6 | Default Credentials | 0 |
| AC-7 | Singpass/Corppass for Public Users | 1 |
| AC-8 | Automated Account Lifecycle Management | 1 |
| AC-9 | Endpoint Device Management | 1 |
| AC-10 | Identity and Device-Based Access Control | 2 |
| AC-11 | Single User Endpoints | 2 |
| AC-12 | Single Sign-On (SSO) for Internal Services and Accounts | 1 |
| AC-13 | Static Credential Expiry and Rotation | 2 |
| AC-14 | Inventory of Accounts | 1 |
| **CS: Container Security** | | |
| CS-1 | Unique Base Container Image Tags | 2 |
| CS-2 | Minimal Base Container Images | 2 |
| CS-3 | Runtime Container Secrets | 1 |
| CS-4 | Non-Privileged Container User | 1 |
| CS-5 | Dockerfile Linting | 2 |
| CS-6 | Read-Only Container Root Filesystem | 2 |
| CS-7 | Container Image Scanning | 1 |
| CS-8 | Private Container Image Registries | 1 |
| CS-9 | Container Orchestrator API Access Control | 1 |
| CS-10 | Container Workload Segmentation | 1 |
| CS-11 | Container Runtime Security | 2 |
| **PM: Security Programme Management** | | |
| PM-1 | Cybersecurity Incident Management Plan | 1 |
| PM-2 | Risk Assessment | 1 |
| PM-3 | System Security Plan (SSP) Development | 0 |
| PM-4 | Approval of Residual Risks | 0 |
| PM-5 | Central Submission of Approved System Security Plan (SSP) | 0 |
| PM-6 | System Documentation | 1 |
| **IS: Infrastructure Security** | | |
| IS-1 | Management Agents | 1 |
| IS-2 | Automated Patch Management Tools | 1 |
| IS-3 | Restricted Administrator Privileges | 1 |
| IS-4 | Least Functionality | 1 |
| IS-5 | Host System Hardening | 1 |
| IS-6 | Remote Administration | 1 |
| IS-7 | Malware Protection | 1 |
| IS-8 | Endpoint Detection and Response (EDR) | 2 |
| IS-9 | End-of-Support (EOS) Assets | 1 |
| IS-10 | Synchronise time clocks | 1 |
| IS-11 | Central Domain Name Registration | 0 |
| IS-12 | DNS Security Extensions (DNSSEC) | 1 |
| IS-13 | Defensive Domain Name Registration | 1 |
| IS-14 | Singapore SMS Sender ID Registry Registration | 0 |
| **SD: Secure Development** | | |
| SD-1 | Push Protection for Secrets | 1 |
| SD-2 | Default Branch Push Permissions | 1 |
| SD-3 | Continuous Integration (CI) Tests | 1 |
| SD-4 | Static Analysis | 1 |
| SD-5 | Dependency Scanning | 1 |
| SD-6 | Secret Detection | 1 |
| SD-7 | CI Environment Variable Secrets Management | 1 |
| SD-8 | Deployment Environment Segregation | 0 |
| **CK: Cryptography, Encryption and Key Management** | | |
| CK-1 | Cryptographic Key Establishment | 1 |
| CK-2 | Cryptographic Key Rotation | 1 |

## High-Risk Cloud CII

Source: https://info.standards.tech.gov.sg/ssp/high-risk-cloud/
Page last updated: 24 March 2026

System category: A generic system hosted on the cloud through a third-party Cloud Service Provider.

Sensitivity ceiling: Confidential, Sensitive High

Controls (137):

| ID | Title | Profile level |
| --- | --- | --- |
| **AS: Application Security** | | |
| AS-1 | Input Validation | 0 |
| AS-2 | Parameterised Interfaces | 1 |
| AS-3 | Output Sanitisation | 0 |
| AS-4 | Authentication Mechanism Rate-Limiting | 0 |
| AS-5 | Password Requirements | 0 |
| AS-6 | Password Salting and Hashing | 0 |
| AS-7 | Access Control Check Enforcement | 0 |
| AS-8 | Secrets Management | 0 |
| AS-9 | Content Security Policy (CSP) | 1 |
| AS-10 | HTTP Strict Transport Security (HSTS) | 2 |
| AS-11 | Session Management | 0 |
| AS-12 | Malware Scanning of Uploaded Files | 0 |
| AS-13 | Exposure of Internal System Details | 1 |
| AS-14 | Secure Cryptographic Libraries | 0 |
| AS-15 | Password Change | 1 |
| **SC: Software Supply Chain** | | |
| SC-1 | Code Repository | 1 |
| SC-2 | Commit Signing | 2 |
| SC-3 | Peer Review | 0 |
| SC-4 | Dependency Manifest Version Pinning | 1 |
| SC-5 | Build and Release Process | 1 |
| SC-6 | Dependency Installation during Deployment | 1 |
| SC-7 | Software Artefact Signing | 2 |
| SC-8 | Software Artefact Signature Verification | 2 |
| SC-9 | Internal Code Collaboration and Sharing | 2 |
| **ST: Security Testing** | | |
| ST-1 | Vulnerability Assessment | 0 |
| ST-2 | Cloud Security Posture Management | 0 |
| ST-3 | Public Vulnerability Disclosure Programme | 0 |
| ST-4 | Security Testing Programme | 0 |
| ST-5 | Vulnerability Management | 0 |
| **NS: Network Security** | | |
| NS-1 | Network and System Component Segmentation | 0 |
| NS-2 | Access Restrictions on CSP Resources Outside Virtual Network | 1 |
| NS-3 | Deny by Default - Allow by Exception | 1 |
| NS-4 | Inter-Private Network Connectivity | 1 |
| NS-5 | Network and Application Layer Filtering | 0 |
| NS-6 | Valid and Trusted SSL/TLS Certificates | 1 |
| NS-7 | Secure Inter-Service Communication | 1 |
| NS-8 | Secure Cloud and On-Premises Connectivity | 0 |
| NS-9 | Intrusion Prevention System (IPS)/Intrusion Detection System (IDS) | 1 |
| NS-10 | Private Network Connectivity | 1 |
| NS-11 | Alerts on Firewall Configuration Changes | 0 |
| **BR: Backup and Recovery** | | |
| BR-1 | Backup | 0 |
| BR-2 | Recovery Testing | 0 |
| BR-3 | Backup Retention | 0 |
| BR-4 | Disaster Recovery Plan | 0 |
| BR-5 | Business Continuity Plan | 0 |
| BR-6 | Business Continuity Exercise | 0 |
| **DP: Data Protection** | | |
| DP-1 | Data Residency | 0 |
| DP-2 | Data at Rest Encryption | 1 |
| DP-3 | Data in Transit Encryption | 1 |
| DP-4 | Central Cloud Tenant Management | 1 |
| **LM: Logging and Monitoring** | | |
| LM-1 | Separate Log Storage | 0 |
| LM-2 | Tamper-Resistant Log Storage | 0 |
| LM-3 | Network Flow Logging | 0 |
| LM-4 | Audit Logging | 0 |
| LM-5 | Database Logging | 0 |
| LM-6 | Access Logging | 0 |
| LM-7 | Host Security Event Logging | 0 |
| LM-8 | Security Log Retention | 0 |
| LM-9 | Security Monitoring and Alerting | 0 |
| LM-10 | Resource Usage Monitoring and Alerting | 1 |
| LM-11 | Service Level Monitoring and Alerting | 1 |
| LM-12 | Central Security Log Management and Monitoring | 0 |
| LM-13 | Anomalous Database Activity Monitoring | 0 |
| LM-14 | Web Defacement Monitoring | 1 |
| LM-15 | Structured Log Formatting | 1 |
| LM-16 | Key Signals Monitoring | 2 |
| LM-17 | Software delivery performance monitoring | 2 |
| LM-19 | Log Sanitisation | 1 |
| LM-21 | Detection Updates | 1 |
| **AC: Access Control** | | |
| AC-1 | Principle of Least Privilege | 0 |
| AC-2 | Multi-Factor Authentication (MFA) | 0 |
| AC-3 | Inactive and Expired Accounts | 0 |
| AC-4 | Access Review | 1 |
| AC-5 | Endpoint Device Hardening | 0 |
| AC-6 | Default Credentials | 0 |
| AC-7 | Singpass/Corppass for Public Users | 1 |
| AC-8 | Automated Account Lifecycle Management | 1 |
| AC-9 | Endpoint Device Management | 1 |
| AC-10 | Identity and Device-Based Access Control | 2 |
| AC-11 | Single User Endpoints | 1 |
| AC-12 | Single Sign-On (SSO) for Internal Services and Accounts | 1 |
| AC-13 | Static Credential Expiry and Rotation | 1 |
| AC-14 | Inventory of Accounts | 1 |
| AC-16 | Separation of Duties | 1 |
| **CS: Container Security** | | |
| CS-1 | Unique Base Container Image Tags | 2 |
| CS-2 | Minimal Base Container Images | 2 |
| CS-3 | Runtime Container Secrets | 1 |
| CS-4 | Non-Privileged Container User | 1 |
| CS-5 | Dockerfile Linting | 2 |
| CS-6 | Read-Only Container Root Filesystem | 2 |
| CS-7 | Container Image Scanning | 1 |
| CS-8 | Private Container Image Registries | 1 |
| CS-9 | Container Orchestrator API Access Control | 1 |
| CS-10 | Container Workload Segmentation | 1 |
| CS-11 | Container Runtime Security | 2 |
| **PM: Security Programme Management** | | |
| PM-1 | Cybersecurity Incident Management Plan | 0 |
| PM-2 | Risk Assessment | 0 |
| PM-3 | System Security Plan (SSP) Development | 0 |
| PM-4 | Approval of Residual Risks | 0 |
| PM-5 | Central Submission of Approved System Security Plan (SSP) | 0 |
| PM-6 | System Documentation | 0 |
| PM-9 | Cybersecurity Incident Response Testing | 0 |
| PM-10 | Cybersecurity Leadership and Oversight | 0 |
| **IS: Infrastructure Security** | | |
| IS-1 | Management Agents | 1 |
| IS-2 | Automated Patch Management Tools | 1 |
| IS-3 | Restricted Administrator Privileges | 0 |
| IS-4 | Least Functionality | 1 |
| IS-5 | Host System Hardening | 0 |
| IS-6 | Remote Administration | 1 |
| IS-7 | Malware Protection | 0 |
| IS-8 | Endpoint Detection and Response (EDR) | 1 |
| IS-9 | End-of-Support (EOS) Assets | 1 |
| IS-10 | Synchronise time clocks | 1 |
| IS-11 | Central Domain Name Registration | 0 |
| IS-12 | DNS Security Extensions (DNSSEC) | 1 |
| IS-13 | Defensive Domain Name Registration | 1 |
| IS-14 | Singapore SMS Sender ID Registry Registration | 2 |
| **SD: Secure Development** | | |
| SD-1 | Push Protection for Secrets | 1 |
| SD-2 | Default Branch Push Permissions | 1 |
| SD-3 | Continuous Integration (CI) Tests | 1 |
| SD-4 | Static Analysis | 1 |
| SD-5 | Dependency Scanning | 1 |
| SD-6 | Secret Detection | 0 |
| SD-7 | CI Environment Variable Secrets Management | 1 |
| SD-8 | Deployment Environment Segregation | 0 |
| SD-9 | Dynamic Analysis | 2 |
| SD-10 | Secure Software Development Lifecycle (SSDLC) | 1 |
| **CK: Cryptography, Encryption and Key Management** | | |
| CK-1 | Cryptographic Key Establishment | 0 |
| CK-2 | Cryptographic Key Rotation | 1 |
| CK-3 | Cryptographic Key Management | 1 |
| CK-4 | Cryptographic Key Storage | 0 |
| **HR: Human Resource** | | |
| HR-1 | Security Awareness Training | 0 |
| HR-2 | Security Screening of Employees | 1 |
| HR-3 | Employee Termination Process | 1 |
| **RS: Resiliency** | | |
| RS-1 | Multi-AZ Deployment | 0 |
| RS-2 | Dynamic Resource Scaling | 1 |
| RS-3 | Load Testing | 2 |

## Low-Risk On Premises

Source: https://info.standards.tech.gov.sg/ssp/low-risk-on-premises/
Page last updated: 24 March 2026

System category: A generic system hosted on-premises.

Sensitivity ceiling: Up to Restricted, Sensitive Normal

Controls (103):

| ID | Title | Profile level |
| --- | --- | --- |
| **AS: Application Security** | | |
| AS-1 | Input Validation | 1 |
| AS-2 | Parameterised Interfaces | 1 |
| AS-3 | Output Sanitisation | 1 |
| AS-4 | Authentication Mechanism Rate-Limiting | 1 |
| AS-5 | Password Requirements | 1 |
| AS-6 | Password Salting and Hashing | 1 |
| AS-7 | Access Control Check Enforcement | 1 |
| AS-8 | Secrets Management | 1 |
| AS-9 | Content Security Policy (CSP) | 1 |
| AS-10 | HTTP Strict Transport Security (HSTS) | 2 |
| AS-11 | Session Management | 1 |
| AS-12 | Malware Scanning of Uploaded Files | 2 |
| AS-13 | Exposure of Internal System Details | 2 |
| AS-14 | Secure Cryptographic Libraries | 2 |
| AS-15 | Password Change | 1 |
| **SC: Software Supply Chain** | | |
| SC-1 | Code Repository | 1 |
| SC-2 | Commit Signing | 2 |
| SC-3 | Peer Review | 1 |
| SC-4 | Dependency Manifest Version Pinning | 1 |
| SC-5 | Build and Release Process | 1 |
| SC-6 | Dependency Installation during Deployment | 1 |
| SC-7 | Software Artefact Signing | 2 |
| SC-8 | Software Artefact Signature Verification | 2 |
| SC-9 | Internal Code Collaboration and Sharing | 2 |
| **ST: Security Testing** | | |
| ST-1 | Vulnerability Assessment | 1 |
| ST-3 | Public Vulnerability Disclosure Programme | 1 |
| ST-4 | Security Testing Programme | 1 |
| ST-5 | Vulnerability Management | 1 |
| **NS: Network Security** | | |
| NS-1 | Network and System Component Segmentation | 1 |
| NS-3 | Deny by Default - Allow by Exception | 1 |
| NS-5 | Network and Application Layer Filtering | 1 |
| NS-6 | Valid and Trusted SSL/TLS Certificates | 1 |
| NS-8 | Secure Cloud and On-Premises Connectivity | 1 |
| NS-9 | Intrusion Prevention System (IPS)/Intrusion Detection System (IDS) | 1 |
| NS-10 | Private Network Connectivity | 1 |
| NS-11 | Alerts on Firewall Configuration Changes | 2 |
| **BR: Backup and Recovery** | | |
| BR-1 | Backup | 1 |
| BR-2 | Recovery Testing | 2 |
| BR-3 | Backup Retention | 1 |
| **DP: Data Protection** | | |
| DP-1 | Data Residency | 0 |
| DP-2 | Data at Rest Encryption | 1 |
| DP-3 | Data in Transit Encryption | 1 |
| DP-5 | Sanitisation | 1 |
| DP-6 | Witness Sanitisation and Destruction of Storage Devices | 2 |
| **LM: Logging and Monitoring** | | |
| LM-1 | Separate Log Storage | 1 |
| LM-2 | Tamper-Resistant Log Storage | 1 |
| LM-5 | Database Logging | 2 |
| LM-6 | Access Logging | 1 |
| LM-7 | Host Security Event Logging | 1 |
| LM-8 | Security Log Retention | 1 |
| LM-9 | Security Monitoring and Alerting | 1 |
| LM-11 | Service Level Monitoring and Alerting | 2 |
| LM-12 | Central Security Log Management and Monitoring | 0 |
| LM-13 | Anomalous Database Activity Monitoring | 2 |
| LM-14 | Web Defacement Monitoring | 2 |
| LM-15 | Structured Log Formatting | 2 |
| LM-16 | Key Signals Monitoring | 2 |
| LM-17 | Software delivery performance monitoring | 2 |
| LM-19 | Log Sanitisation | 2 |
| **AC: Access Control** | | |
| AC-1 | Principle of Least Privilege | 1 |
| AC-2 | Multi-Factor Authentication (MFA) | 1 |
| AC-3 | Inactive and Expired Accounts | 1 |
| AC-4 | Access Review | 1 |
| AC-5 | Endpoint Device Hardening | 1 |
| AC-6 | Default Credentials | 1 |
| AC-7 | Singpass/Corppass for Public Users | 1 |
| AC-8 | Automated Account Lifecycle Management | 1 |
| AC-9 | Endpoint Device Management | 1 |
| AC-10 | Identity and Device-Based Access Control | 2 |
| AC-11 | Single User Endpoints | 2 |
| AC-12 | Single Sign-On (SSO) for Internal Services and Accounts | 1 |
| AC-13 | Static Credential Expiry and Rotation | 2 |
| AC-14 | Inventory of Accounts | 1 |
| **PM: Security Programme Management** | | |
| PM-1 | Cybersecurity Incident Management Plan | 1 |
| PM-2 | Risk Assessment | 1 |
| PM-3 | System Security Plan (SSP) Development | 0 |
| PM-4 | Approval of Residual Risks | 0 |
| PM-5 | Central Submission of Approved System Security Plan (SSP) | 0 |
| PM-6 | System Documentation | 1 |
| **IS: Infrastructure Security** | | |
| IS-2 | Automated Patch Management Tools | 1 |
| IS-3 | Restricted Administrator Privileges | 1 |
| IS-4 | Least Functionality | 1 |
| IS-5 | Host System Hardening | 1 |
| IS-7 | Malware Protection | 1 |
| IS-8 | Endpoint Detection and Response (EDR) | 2 |
| IS-9 | End-of-Support (EOS) Assets | 1 |
| IS-10 | Synchronise time clocks | 1 |
| IS-11 | Central Domain Name Registration | 0 |
| IS-12 | DNS Security Extensions (DNSSEC) | 2 |
| IS-13 | Defensive Domain Name Registration | 2 |
| IS-14 | Singapore SMS Sender ID Registry Registration | 0 |
| **SD: Secure Development** | | |
| SD-1 | Push Protection for Secrets | 1 |
| SD-2 | Default Branch Push Permissions | 1 |
| SD-3 | Continuous Integration (CI) Tests | 2 |
| SD-4 | Static Analysis | 1 |
| SD-5 | Dependency Scanning | 1 |
| SD-6 | Secret Detection | 1 |
| SD-7 | CI Environment Variable Secrets Management | 1 |
| SD-8 | Deployment Environment Segregation | 1 |
| **DC: Datacentre** | | |
| DC-1 | Separate hosting | 1 |
| DC-2 | Physical Access Controls | 1 |
| **CK: Cryptography, Encryption and Key Management** | | |
| CK-1 | Cryptographic Key Establishment | 2 |
| CK-2 | Cryptographic Key Rotation | 2 |

## Generative AI

Source: https://info.standards.tech.gov.sg/ssp/gen-ai/
Page last updated: 24 March 2026

System category: A generic system that utilises generative AI models.

Sensitivity ceiling: Up to Confidential, Sensitive High

Controls (9):

| ID | Title | Profile level |
| --- | --- | --- |
| **DP: Data Protection** | | |
| DP-8 | Data Classification Disclosure | 1 |
| **GA: Generative AI** | | |
| GA-1 | Overseas-hosted GenAI API services | 0 |
| GA-2 | Singapore-hosted GenAI API services | 0 |
| GA-3 | Non-logging and non-training Agreement | 0 |
| GA-4 | Data classification for self-hosted GenAI models | 0 |
| GA-5 | GenAI model formats and loaders | 1 |
| GA-6 | File upload safeguards | 1 |
| GA-7 | Evaluation of GenAI accuracy, safety, and output quality | 1 |
| GA-8 | Inform users about GenAI risks and limitations | 1 |

## Digital Services (High Impact)

Source: https://info.standards.tech.gov.sg/ssp/dss-high/
Page last updated: 26 March 2026

System category: A system that has digital services with high impact.

Sensitivity ceiling: NA

Controls (92):

| ID | Title | Profile level |
| --- | --- | --- |
| **UU: Understand Users** | | |
| UU-1 | Understand user needs | 1 |
| UU-2 | Test with users | 1 |
| **BD: Baseline Design Practices** | | |
| BD-1 | Responsive Web Design | 1 |
| BD-2 | Site Search | 1 |
| BD-3 | Support multiple languages | 2 |
| BD-4 | Clear and Concise Content | 2 |
| BD-5 | Search Engine Optimisation | 2 |
| BD-6 | Consistent UI Design | 1 |
| BD-7 | Mandatory and Optional Fields | 1 |
| BD-8 | Log-in Indication | 1 |
| BD-9 | Contact Channels | 1 |
| **TX: Transactions and Payments** | | |
| TX-1 | Digital-First Approach | 1 |
| TX-2 | Transaction Prerequisites | 1 |
| TX-3 | Break Down Long Transactions | 2 |
| TX-4 | Progress Indicators | 2 |
| TX-5 | Save Draft Function | 2 |
| TX-6 | Pre-fill Data | 1 |
| TX-7 | Payment and Refund | 1 |
| TX-8 | Managing Stored Payment Details | 1 |
| TX-9 | Success or failure message | 1 |
| TX-10 | Failed Transaction Details | 1 |
| TX-11 | Payment details | 1 |
| TX-12 | Transaction Outcome | 1 |
| TX-13 | Post-transaction Acknowledgement | 1 |
| TX-14 | Transaction Status Updates | 1 |
| TX-15 | Tracking Transaction Status | 2 |
| **PR: Performance and Reliability** | | |
| PR-1 | Digital Service Review | 1 |
| PR-2 | Digital Service Registration | 0 |
| PR-3 | Digital Service Availability | 1 |
| PR-4 | Notify of Scheduled Downtime | 1 |
| PR-5 | Manage Broken Links | 1 |
| PR-6 | Browser Compatibility | 1 |
| PR-7 | Optimise Load Times | 1 |
| **TL: Trust and Legitimacy** | | |
| TL-1 | Official Government Domain | 1 |
| TL-2 | Agency or Initiative Logo | 1 |
| TL-3 | Official Government Banner | 0 |
| TL-4 | Official Government Footer | 1 |
| TL-5 | Mobile App Ownership and Distribution | 0 |
| TL-6 | Application Store Listings | 1 |
| **WP: WCAG - Perceivable** | | |
| WP-1 | Text Alternatives for Non-Text content | 1 |
| WP-2 | Captions for Prerecorded Media | 1 |
| WP-3 | Text or Audio Alternatives for Prerecorded Media | 1 |
| WP-4 | Live Captions | 1 |
| WP-5 | Audio Description for Prerecorded Video Content | 1 |
| WP-6 | Presentation of Info and Relationships | 1 |
| WP-7 | Meaningful Content Order | 1 |
| WP-8 | Describing Displayed Controls | 1 |
| WP-9 | Display Orientation | 1 |
| WP-10 | Identify Input Purpose | 1 |
| WP-11 | Use of Color | 1 |
| WP-12 | Audio Control | 1 |
| WP-13 | Minimum Contrast | 1 |
| WP-14 | Text Scaling | 1 |
| WP-15 | Images of Text | 1 |
| WP-16 | Content Reflow | 1 |
| WP-17 | Non-text Contrast | 1 |
| WP-18 | Text Spacing | 1 |
| WP-19 | Content on Hover or Focus | 1 |
| **WO: WCAG - Operable** | | |
| WO-1 | Keyboard equivalent | 1 |
| WO-2 | No Keyboard Trap | 1 |
| WO-3 | Character Key Shortcuts | 1 |
| WO-4 | Adjustable Timings | 1 |
| WO-5 | Pause, Stop, Hide | 1 |
| WO-6 | Reduce Flash Triggers | 1 |
| WO-7 | Bypass Repeating Content | 1 |
| WO-8 | Page Title And Purpose | 1 |
| WO-9 | Sequential Focus Order | 1 |
| WO-10 | Link Text And Purpose | 1 |
| WO-11 | Multiple Ways | 1 |
| WO-12 | Headings and Labels | 1 |
| WO-13 | Focus Visible and Not Obscured | 1 |
| WO-14 | Simple Pointer Alternatives | 1 |
| WO-15 | Pointer Cancellation | 1 |
| WO-16 | Label In Name | 1 |
| WO-17 | Motion Actuation | 1 |
| WO-18 | Minimum Pointer Target Size | 1 |
| **WU: WCAG - Understandable** | | |
| WU-1 | Language of Page | 1 |
| WU-2 | Language of Parts | 1 |
| WU-3 | Unusual Words | 1 |
| WU-4 | Abbreviations | 1 |
| WU-5 | Changes On Focus | 1 |
| WU-6 | Changes On Input | 1 |
| WU-7 | Consistent Navigation | 1 |
| WU-8 | Consistent Identification | 1 |
| WU-9 | Consistent Help | 1 |
| WU-10 | Error Identification | 1 |
| WU-11 | Error Suggestion | 1 |
| WU-12 | Error Prevention | 1 |
| WU-13 | Redundant Entry | 1 |
| WU-14 | Accessible Authentication (Minimum) | 1 |
| **WR: WCAG - Robust** | | |
| WR-1 | Name, Role, Value | 1 |
| WR-2 | Status Messages | 1 |

## Digital Services (Others)

Source: https://info.standards.tech.gov.sg/ssp/dss-others/
Page last updated: 26 March 2026

System category: A system that has digital services.

Sensitivity ceiling: NA

Controls (92):

| ID | Title | Profile level |
| --- | --- | --- |
| **UU: Understand Users** | | |
| UU-1 | Understand user needs | 1 |
| UU-2 | Test with users | 1 |
| **BD: Baseline Design Practices** | | |
| BD-1 | Responsive Web Design | 1 |
| BD-2 | Site Search | 1 |
| BD-3 | Support multiple languages | 2 |
| BD-4 | Clear and Concise Content | 2 |
| BD-5 | Search Engine Optimisation | 2 |
| BD-6 | Consistent UI Design | 1 |
| BD-7 | Mandatory and Optional Fields | 1 |
| BD-8 | Log-in Indication | 1 |
| BD-9 | Contact Channels | 1 |
| **TX: Transactions and Payments** | | |
| TX-1 | Digital-First Approach | 1 |
| TX-2 | Transaction Prerequisites | 1 |
| TX-3 | Break Down Long Transactions | 2 |
| TX-4 | Progress Indicators | 2 |
| TX-5 | Save Draft Function | 2 |
| TX-6 | Pre-fill Data | 1 |
| TX-7 | Payment and Refund | 1 |
| TX-8 | Managing Stored Payment Details | 1 |
| TX-9 | Success or failure message | 1 |
| TX-10 | Failed Transaction Details | 1 |
| TX-11 | Payment details | 1 |
| TX-12 | Transaction Outcome | 1 |
| TX-13 | Post-transaction Acknowledgement | 1 |
| TX-14 | Transaction Status Updates | 1 |
| TX-15 | Tracking Transaction Status | 2 |
| **PR: Performance and Reliability** | | |
| PR-1 | Digital Service Review | 1 |
| PR-2 | Digital Service Registration | 0 |
| PR-3 | Digital Service Availability | 1 |
| PR-4 | Notify of Scheduled Downtime | 1 |
| PR-5 | Manage Broken Links | 1 |
| PR-6 | Browser Compatibility | 1 |
| PR-7 | Optimise Load Times | 1 |
| **TL: Trust and Legitimacy** | | |
| TL-1 | Official Government Domain | 1 |
| TL-2 | Agency or Initiative Logo | 1 |
| TL-3 | Official Government Banner | 0 |
| TL-4 | Official Government Footer | 1 |
| TL-5 | Mobile App Ownership and Distribution | 0 |
| TL-6 | Application Store Listings | 1 |
| **WP: WCAG - Perceivable** | | |
| WP-1 | Text Alternatives for Non-Text content | 1 |
| WP-2 | Captions for Prerecorded Media | 1 |
| WP-3 | Text or Audio Alternatives for Prerecorded Media | 1 |
| WP-4 | Live Captions | 2 |
| WP-5 | Audio Description for Prerecorded Video Content | 2 |
| WP-6 | Presentation of Info and Relationships | 1 |
| WP-7 | Meaningful Content Order | 1 |
| WP-8 | Describing Displayed Controls | 1 |
| WP-9 | Display Orientation | 2 |
| WP-10 | Identify Input Purpose | 1 |
| WP-11 | Use of Color | 1 |
| WP-12 | Audio Control | 1 |
| WP-13 | Minimum Contrast | 1 |
| WP-14 | Text Scaling | 1 |
| WP-15 | Images of Text | 2 |
| WP-16 | Content Reflow | 1 |
| WP-17 | Non-text Contrast | 1 |
| WP-18 | Text Spacing | 1 |
| WP-19 | Content on Hover or Focus | 1 |
| **WO: WCAG - Operable** | | |
| WO-1 | Keyboard equivalent | 1 |
| WO-2 | No Keyboard Trap | 1 |
| WO-3 | Character Key Shortcuts | 2 |
| WO-4 | Adjustable Timings | 1 |
| WO-5 | Pause, Stop, Hide | 1 |
| WO-6 | Reduce Flash Triggers | 1 |
| WO-7 | Bypass Repeating Content | 1 |
| WO-8 | Page Title And Purpose | 1 |
| WO-9 | Sequential Focus Order | 1 |
| WO-10 | Link Text And Purpose | 1 |
| WO-11 | Multiple Ways | 2 |
| WO-12 | Headings and Labels | 1 |
| WO-13 | Focus Visible and Not Obscured | 1 |
| WO-14 | Simple Pointer Alternatives | 2 |
| WO-15 | Pointer Cancellation | 2 |
| WO-16 | Label In Name | 1 |
| WO-17 | Motion Actuation | 1 |
| WO-18 | Minimum Pointer Target Size | 1 |
| **WU: WCAG - Understandable** | | |
| WU-1 | Language of Page | 1 |
| WU-2 | Language of Parts | 1 |
| WU-3 | Unusual Words | 2 |
| WU-4 | Abbreviations | 1 |
| WU-5 | Changes On Focus | 1 |
| WU-6 | Changes On Input | 1 |
| WU-7 | Consistent Navigation | 1 |
| WU-8 | Consistent Identification | 1 |
| WU-9 | Consistent Help | 1 |
| WU-10 | Error Identification | 1 |
| WU-11 | Error Suggestion | 1 |
| WU-12 | Error Prevention | 1 |
| WU-13 | Redundant Entry | 1 |
| WU-14 | Accessible Authentication (Minimum) | 1 |
| **WR: WCAG - Robust** | | |
| WR-1 | Name, Role, Value | 1 |
| WR-2 | Status Messages | 1 |

## Sandbox

Source: https://info.standards.tech.gov.sg/ssp/sandbox/
Page last updated: 24 March 2026

System category: A generic pilot sandbox system.

Sensitivity ceiling: Restricted, Sensitive Normal

Controls (117):

| ID | Title | Profile level |
| --- | --- | --- |
| **AS: Application Security** | | |
| AS-1 | Input Validation | 2 |
| AS-2 | Parameterised Interfaces | 2 |
| AS-3 | Output Sanitisation | 2 |
| AS-4 | Authentication Mechanism Rate-Limiting | 2 |
| AS-5 | Password Requirements | 2 |
| AS-6 | Password Salting and Hashing | 2 |
| AS-7 | Access Control Check Enforcement | 2 |
| AS-8 | Secrets Management | 2 |
| AS-9 | Content Security Policy (CSP) | 2 |
| AS-10 | HTTP Strict Transport Security (HSTS) | 2 |
| AS-11 | Session Management | 2 |
| AS-12 | Malware Scanning of Uploaded Files | 2 |
| AS-13 | Exposure of Internal System Details | 2 |
| AS-14 | Secure Cryptographic Libraries | 2 |
| AS-15 | Password Change | 2 |
| **SC: Software Supply Chain** | | |
| SC-1 | Code Repository | 2 |
| SC-2 | Commit Signing | 2 |
| SC-3 | Peer Review | 2 |
| SC-4 | Dependency Manifest Version Pinning | 2 |
| SC-5 | Build and Release Process | 2 |
| SC-6 | Dependency Installation during Deployment | 2 |
| SC-7 | Software Artefact Signing | 2 |
| SC-8 | Software Artefact Signature Verification | 2 |
| SC-9 | Internal Code Collaboration and Sharing | 2 |
| **ST: Security Testing** | | |
| ST-1 | Vulnerability Assessment | 2 |
| ST-2 | Cloud Security Posture Management | 2 |
| ST-3 | Public Vulnerability Disclosure Programme | 2 |
| ST-4 | Security Testing Programme | 2 |
| ST-5 | Vulnerability Management | 2 |
| **NS: Network Security** | | |
| NS-1 | Network and System Component Segmentation | 2 |
| NS-2 | Access Restrictions on CSP Resources Outside Virtual Network | 2 |
| NS-3 | Deny by Default - Allow by Exception | 2 |
| NS-4 | Inter-Private Network Connectivity | 2 |
| NS-5 | Network and Application Layer Filtering | 2 |
| NS-6 | Valid and Trusted SSL/TLS Certificates | 2 |
| NS-7 | Secure Inter-Service Communication | 2 |
| NS-8 | Secure Cloud and On-Premises Connectivity | 2 |
| **BR: Backup and Recovery** | | |
| BR-1 | Backup | 2 |
| BR-2 | Recovery Testing | 2 |
| BR-3 | Backup Retention | 2 |
| **DP: Data Protection** | | |
| DP-1 | Data Residency | 2 |
| DP-2 | Data at Rest Encryption | 2 |
| DP-3 | Data in Transit Encryption | 2 |
| DP-4 | Central Cloud Tenant Management | 2 |
| **LM: Logging and Monitoring** | | |
| LM-1 | Separate Log Storage | 2 |
| LM-2 | Tamper-Resistant Log Storage | 2 |
| LM-3 | Network Flow Logging | 2 |
| LM-4 | Audit Logging | 2 |
| LM-5 | Database Logging | 2 |
| LM-6 | Access Logging | 2 |
| LM-7 | Host Security Event Logging | 2 |
| LM-8 | Security Log Retention | 2 |
| LM-9 | Security Monitoring and Alerting | 2 |
| LM-10 | Resource Usage Monitoring and Alerting | 2 |
| LM-11 | Service Level Monitoring and Alerting | 2 |
| LM-12 | Central Security Log Management and Monitoring | 2 |
| LM-13 | Anomalous Database Activity Monitoring | 2 |
| LM-14 | Web Defacement Monitoring | 2 |
| LM-15 | Structured Log Formatting | 2 |
| LM-16 | Key Signals Monitoring | 2 |
| LM-17 | Software delivery performance monitoring | 2 |
| LM-19 | Log Sanitisation | 2 |
| **AC: Access Control** | | |
| AC-1 | Principle of Least Privilege | 2 |
| AC-2 | Multi-Factor Authentication (MFA) | 2 |
| AC-3 | Inactive and Expired Accounts | 2 |
| AC-4 | Access Review | 2 |
| AC-5 | Endpoint Device Hardening | 2 |
| AC-6 | Default Credentials | 2 |
| AC-7 | Singpass/Corppass for Public Users | 2 |
| AC-8 | Automated Account Lifecycle Management | 2 |
| AC-9 | Endpoint Device Management | 2 |
| AC-10 | Identity and Device-Based Access Control | 2 |
| AC-11 | Single User Endpoints | 2 |
| AC-12 | Single Sign-On (SSO) for Internal Services and Accounts | 2 |
| AC-13 | Static Credential Expiry and Rotation | 2 |
| AC-14 | Inventory of Accounts | 2 |
| **CS: Container Security** | | |
| CS-1 | Unique Base Container Image Tags | 2 |
| CS-2 | Minimal Base Container Images | 2 |
| CS-3 | Runtime Container Secrets | 2 |
| CS-4 | Non-Privileged Container User | 2 |
| CS-5 | Dockerfile Linting | 2 |
| CS-6 | Read-Only Container Root Filesystem | 2 |
| CS-7 | Container Image Scanning | 2 |
| CS-8 | Private Container Image Registries | 2 |
| CS-9 | Container Orchestrator API Access Control | 2 |
| CS-10 | Container Workload Segmentation | 2 |
| CS-11 | Container Runtime Security | 2 |
| **PM: Security Programme Management** | | |
| PM-1 | Cybersecurity Incident Management Plan | 2 |
| PM-2 | Risk Assessment | 2 |
| PM-3 | System Security Plan (SSP) Development | 0 |
| PM-4 | Approval of Residual Risks | 0 |
| PM-5 | Central Submission of Approved System Security Plan (SSP) | 0 |
| PM-6 | System Documentation | 2 |
| **IS: Infrastructure Security** | | |
| IS-1 | Management Agents | 2 |
| IS-2 | Automated Patch Management Tools | 2 |
| IS-3 | Restricted Administrator Privileges | 2 |
| IS-4 | Least Functionality | 2 |
| IS-5 | Host System Hardening | 2 |
| IS-6 | Remote Administration | 2 |
| IS-7 | Malware Protection | 2 |
| IS-8 | Endpoint Detection and Response (EDR) | 2 |
| IS-9 | End-of-Support (EOS) Assets | 2 |
| IS-10 | Synchronise time clocks | 2 |
| IS-11 | Central Domain Name Registration | 2 |
| IS-12 | DNS Security Extensions (DNSSEC) | 2 |
| IS-13 | Defensive Domain Name Registration | 2 |
| IS-14 | Singapore SMS Sender ID Registry Registration | 2 |
| **SD: Secure Development** | | |
| SD-1 | Push Protection for Secrets | 2 |
| SD-2 | Default Branch Push Permissions | 2 |
| SD-3 | Continuous Integration (CI) Tests | 2 |
| SD-4 | Static Analysis | 2 |
| SD-5 | Dependency Scanning | 2 |
| SD-6 | Secret Detection | 2 |
| SD-7 | CI Environment Variable Secrets Management | 2 |
| SD-8 | Deployment Environment Segregation | 2 |
| **CK: Cryptography, Encryption and Key Management** | | |
| CK-1 | Cryptographic Key Establishment | 2 |
| CK-2 | Cryptographic Key Rotation | 2 |
