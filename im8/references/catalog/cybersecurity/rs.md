# Resiliency (RS)

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/rs/
Page last updated: 24 March 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## RS-1 — Multi-AZ Deployment

### Statement

Deploy the system in [ insert: param, rs-1_prm_1 ] availability zones (AZs) within the region.

### Recommendations

Utilise cloud-native services for load-balancing and auto-scaling across multiple AZs. Implement health checks and automated failover mechanisms to redirect traffic. Ensure data is replicated across multiple AZs.

### Risk statement

Failure to deploy services across multiple availability zones increases the risk of extended service outages due to a single point of failure.

### Parameters

| ID | Type | Description |
| --- | --- | --- |
| rs-1_prm_1 | number of zones (str) | The number of availability zones to deploy to. |

## RS-2 — Dynamic Resource Scaling

### Statement

Implement and utilise dynamic resource scaling techniques in the system.

### Recommendations

Resource optimisation techniques such as load balancing and auto-scaling should be employed to maximise resource utilisation and minimise idle resources by adjusting to real-time demand fluctuations.

Refer to the AWS Well-Architected Framework's 'Reliability' pillar for further guidance on implementing resilient systems.

### Risk statement

Failure to implement dynamic resource scaling may lead to inefficient resource utilisation and potential service degradation during spikes in demand. This can lead to system outages during peak loads, reducing overall system performance and reliability.

## RS-3 — Load Testing

### Statement

Perform load testing every [ insert: param, rs-3_prm_1 ] days.

### Recommendations

Load testing should be conducted on a replica of the production system. The load should mimic real user traffic.

### Risk statement

Inadequate load testing may lead to unexpected system failures during periods of high demand, leading to service interruptions.

### Parameters

| ID | Type | Description |
| --- | --- | --- |
| rs-3_prm_1 | time period (days) (int) | The frequency at which load testing should be performed. |
