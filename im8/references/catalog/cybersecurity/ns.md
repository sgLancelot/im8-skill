# NS — Network Security

<!-- generated-by: scripts/sync_oscal.py (OSCAL sync, GovTechSG/tech-standards) -->

Family code: `ns` | Controls: 11

Controls to secure the network boundaries of a system.

## NS-1 — Public and Private Subnet Segmentation

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Place private resources (e.g., databases) in private subnets and public resources (e.g., reverse proxies, web servers) in public subnets within a virtual network.

**Guidance:** This control does not apply to serverless resources (API Gateways), static sites or assets fronted by CDNs (e.g., CloudFlare, CloudFront) which are located outside of the virtual network. Private subnets do not allow direct connections from the internet while public subnets do. However, resources in private segments can connect to the internet via NAT Gateways in public subnets in the same virtual network.

**Risk statement:** Failure to segregate private and public resources within distinct subnets in a virtual network increases the risk of unauthorised access to sensitive data, as private resources may be exposed to the public internet, compromising the overall security of the infrastructure.

## NS-2 — Access Restrictions on CSP Resources Outside Virtual Network

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Restrict access to CSP resources outside of a virtual network (e.g., Lambda, DynamoDb, API Gateways, S3, CloudFront) using access controls or application layer authorisation.

**Guidance:** Apply access restrictions appropriate to the resource type. Access through interface VPC endpoints is only required if the client is hosted in a private subnet. For example:

* Restrict access to DynamoDB with IAM policies.

* Restrict access to API Gateway with Lambda authorizers or authorisation middlewares at the application layer. If the API Gateway is exposed to private subnets, create a private API.

* Restrict access to S3 Buckets with IAM policies and block public access from the internet.

**Risk statement:** Lack of access restrictions raises the risk of unauthorised access, data exposure, and potential misuse of critical services, compromising the overall security posture.

## NS-3 — Deny by Default - Allow by Exception

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Deny network communications traffic by default and allow network communications traffic by exception at managed interfaces.

**Guidance:** Configure network access control lists and security groups to deny all traffic by default. Only allow traffic to and from specific hosts and ports by exception. For egress traffic to the internet, consider whitelisting domains at the application layer or DNS resolver rather than just hosts or ports at the transport layer.

**Risk statement:** Without network access controls, there's an increased risk of unauthorised or malicious network access, leading to potential security breaches and compromise of system integrity.

## NS-4 — Inter-Private Network Connectivity

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Route network traffic between private networks without going through the internet.

**Guidance:** Use CSP Private endpoint services (e.g., AWS PrivateLink with VPC endpoints) when you want to allow one or more consumer VPCs unidirectional access to a specific service or set of instances in the service provider VPC. Otherwise, use VPC peering and Transit Gateway when you want to enable layer-3 IP connectivity between VPCs. Refer to the [Multi-VPC AWS Network Infrastructure Whitepaper](#9022563f-00b5-48d1-99a6-187503e7f869) for further guidance.

**Risk statement:** When routing through the internet, there's an increased risk of man-in-the-middle and spoofing attacks. Allowing bidirectional access between networks without fine-grained access controls increases the risk of unauthorised access, potential data exfiltration, and compromise of network security compared to unidirectional access to specific resources.

## NS-5 — Network and Application Layer Filtering

**Levels:** low-risk: L1, medium-risk: L0

**Statement:** Filter direct traffic from the internet to protect against network and application layer attacks.

**Guidance:** Deploy the following mechanisms as appropriate for the system and network architecture:

* Web Application Firewall

* Distributed Denial of Service Protection (e.g., AWS Shield)

* Content Delivery Network (e.g., CloudFront)

**Risk statement:** Lack of filtering for direct traffic from the internet exposes the system to the risk of network and application layer attacks, increasing the likelihood of unauthorised access, denial-of-service incidents, and compromise of sensitive data.

## NS-6 — Valid and Trusted SSL/TLS Certificates

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Ensure that deployed SSL/TLS certificates are:

1 signed by a trusted root Certificate Authority;

2 match the domain name of the service they are issued for;

3 not expired; and

4 not revoked.

**Guidance:** Configure a certificate manager that auto-renews certificates and sends alerts before expiry (e.g., AWS Certificate Manager). Otherwise, automate these functions separately.

**Risk statement:** Using invalid SSL/TLS certificates introduces the risk of compromised encryption, man-in-the-middle attacks, and potential unauthorised access to sensitive information.

## NS-7 — Secure Inter-Service Communication

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Ensure communications between services are secure by making them authenticated, authorised and encrypted.

**Guidance:** Design and build inter-service communications (e.g., databases, microservices) to be authenticated, authorised and encrypted (e.g., via API gateways, proxies, private endpoint services, message queues, or service meshes). It is recommended to log communication (such as access logs, transaction logs or payloads) between services for detection, monitoring and investigation of incidents.

**Risk statement:** Failure to ensure secure communications between services increases the risk of unauthorised access, data breaches, and potential manipulation of sensitive information during transit.

## NS-8 — Secure Government Enterprise Network (GEN) connectivity

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Route network traffic between on-premises systems and GCC systems through a secure intermediary.

**Guidance:** Design and build secure communications to or from on-premises systems (e.g. Government Enterprise Network (GEN)) through a Gateway rather than direct connectivity (e.g. via API gateways, Application proxies or private endpoint services).

**Risk statement:** Routing network traffic through a secure intermediary mitigates the risk of unauthorised access and cross-network compromise in the case of bridging or direct connectivity.

## NS-9 — Intrusion Prevention System (IPS)/Intrusion Detection System (IDS)

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Set up and configure an Intrusion Prevention System (IPS)/Intrusion Detection System (IDS) in the network.

**Guidance:** Configure network or host IPS/IDS to detect malicious traffic to/from public or untrusted networks.

**Risk statement:** Absence of network or host IPS or IDS in the network increases the likelihood of undetected intrusions, putting sensitive data and system integrity at risk.

## NS-10 — Private Network Connectivity

**Levels:** low-risk: L1, medium-risk: L1

**Statement:** Implement strong access controls, encryption, and logging for remote developer, maintainer, or administrator access to private network resources.

**Guidance:** Use strong authentication and MFA. Layered security mechanisms and controls include:

* Inspect traffic from gateway to private network;

* Terminate all remote access connections in a dedicated network segment within the network and restrict access to only systems and services allowed by the organisation;

* Implement strong encryption for remote access into internal networks;

* Only allow authorised devices to remotely access internal networks;

* Ensure that remote access connections are not perpetual and re-authenticate remote users to the VPN gateway on a periodic basis (such as every four hours);

* Set the maximum number of consecutive failed authentication attempts before account lockout for remote access to internal networks; and

* Make sure that split tunnelling is not implemented.

**Risk statement:** Weak private network security may expose the network to malicious activities, jeopardising the confidentiality, integrity, and availability of critical resources.

## NS-11 — Alerts on Firewall Configuration Changes

**Levels:** low-risk: L2, medium-risk: L2

**Statement:** Generate alerts to inform appointed administrators on changes to firewall rules, including the enabling or disabling of rules.

**Guidance:** Implement real time alerts to inform administrators of creation, deletion, modification, enabling and disabling of firewall rules. Also alert administrators when unusual or sudden spike/drop in utilisation of firewall's system resources.

**Risk statement:** Any unintended changes to firewall rules can significantly lower the perimeter defence of a network.
