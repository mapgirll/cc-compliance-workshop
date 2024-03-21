# 0. Getting Started

## Welcome
The intent of this workshop is to provide an introduction to the Calico features that support SOC 2 compliance.
For PCI examples, [see this workshop](https://github.com/tigera-solutions/cc-aks-security-compliance-workshop).

## SOC 2  Trust Services Criteria
SOC 2 is based on five overarching Trust Services Criteria (TSC): security, availability, processing integrity,
confidentiality, and privacy. Specifically, the security criteria are broken down into nine sections called common criteria (CC):

* CC1: Control Environment
* CC2: Communication and Information
* CC3: Risk Assessment
* CC4: Monitoring Activities
* CC5: Control Activities
* CC6: Logical and Physical Access Controls
* CC7: System Operations
* CC8: Change Management
* CC9: Risk Mitigation

## SOC 2 compliance rules mapping to Calico capabilities
Running Kubernetes clusters often presents challenges for CC6 (logical and physical access), CC7 (systems
operations), and CC8 (change management) when trying to comply with SOC 2 standards. 

| Control# | Requirement(s) | Calico control(s) |
| :--------------- | :---------------: | :--------------- |
|CC 6.1, 6.6, 6.7, 6.8| Implement logical access security measures to authorized systems only, implement controls to prevent or detect and act upon introduction of malicious software| <ul><li>Calico can control ingress and egress between microservices and external databases, cloud services, APIs, and other applications.</li><li>Calico can apply least privilege access controls to a cluster, denying all network traffic by default and allowing only those connections that have been authorized.</li><li>Calico can encrypt data in transit for added protection against data tampering</li><li>Calico can organize all SOC 2 endpoints in one or more namespaces.</li><li>Calico configures the namespace for default-deny and whitelists all ingress and egress traffic|
|CC 7.1| Monitor and detect configuration changes and capable of vulnerability management|<ul><li>Calico continuously monitors and logs all workloads for compliance against existing security policies</li><li>Calico alerts on any configuration changes that may impact existing security policies</li><li>Calico scans containers images for vulnerabilities and assigns pass, warn, or fail label to automatically deploy or block the image from deployment|
|CC 7.2, 7.3, 7.4|Monitor systems and components for anomalies and indicators of compromise|<ul><li>Calico anomaly and threat detection capabilities:</li><li>Monitor and analyze threats<li>Automatically quarantine compromised workloads<li>Review network flow logs for statistical and behavioral anomalies</li>|
|CC 8.1|Change Management: Authorize, Track, Approve changes to the system| <ul><li>Calico records all policy changes and provides a change history for audit<li>Calico provides granular control over who is authorized to make changes to policies,endpoints, and namespaces</li>|



## Prerequisites 

The following are the basic requirements to **start** the workshop.

[AWS set up instructions](../aws.md) <br>
 
[Azure set up instructions](../azure.md)

## How Calico supports compliance requirements

Tigera’s solutions, Calico Cloud and Calico Enterprise, enable north-south controls such as egress access, east-west controls such as microsegmentation, and enterprise security controls, policy enforcement, and compliance reporting across all Kubernetes distributions in both hybrid and multi-cloud environments. 

- [Download the whitepaper: PCI compliance for Hosts, VMs, containers, and Kubernetes](https://www.tigera.io/lp/kubernetes-pci-compliance/)
- [Download the PCI DSS v4.0 Quick Reference Guide](https://docs-prv.pcisecuritystandards.org/PCI%20DSS/Supporting%20Document/PCI_DSS-QRG-v4_0.pdf)

---

[:arrow_right: 1. Deploy EKS](../1.%20Deploy%20EKS/readme.md) <br>
 
[:leftwards_arrow_with_hook: Back to Main](../README.md)