---

copyright:
  years: 2026
lastupdated: "2026-04-20"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Sandbox Quota Limits
{: #sandbox-quota}

Following is the table list of Sandbox resource capacity and Quota limits:

| Resource Name | Supported capacity | Impact |
| ------- | --------- | ---- |
| Virtual Server for VPC | vCPU: 128 RAM:1028GB | Instance provisioning may fail or stay in a pending state due to insufficient quota. Verify the available quota using the CLI or API before provisioning. |
| Bare Metal Servers for VPC | 1 Baremetal provisioning | No additional bare metal can be provisioned once the limit is reached. Check usage before provisioning; if at capacity, decommission unused instances or request a quota increase. Update the runbook to promote reuse. |
| Block Storage for VPC | Allowed is 4096GB of data volume per VSI | Any volume larger than 4096 GB will be deleted by the service team. |
| Instance Storage for VPC | 1024 GB of Instance storage | New volume creation may fail and existing workloads could face storage constraints. Monitor usage, remove unused volumes, and add alerts for threshold breaches. |
| Cloud Object Storage | 4096 GB | Approaching capacity limits may cause upload failures or degraded performance. Monitor bucket usage, archive or delete unused data, apply lifecycle policies, and scale the storage plan if needed. Any COS storage exceeding 4096 GB will be deleted by the service team. |
| Virtual Private Cloud | Creation of 2 VPC in the selected region | Additional VPCs cannot be provisioned, preventing new environment creation. Verify the current VPC count and reuse existing VPCs or remove unused ones. |
| Subnets for VPC | Overall they can create 4 subnets from the two vpc limit | Additional subnets cannot be created, which may block network segmentation. Plan subnet allocation in advance, reuse existing subnets, or request a quota increase. |
| Floating IPs | Can create 4 Floating ip from the limit | Additional FIPs cannot be created, preventing public access for required instances and causing connectivity issues. Review FIP usage, release unused IPs, and reassign existing ones where possible. |
| Load Balancer | Can provision 1 Application LB | Additional load balancers cannot be provisioned, limiting traffic distribution and high‑availability setups. Reuse existing load balancers with multiple listeners or pools and optimize configurations. |
| Client VPN | 1 VPN instance | Additional VPNs cannot be provisioned, preventing secure access for new users or environments. Review existing VPN usage and reuse the current VPN by adding users or configurations. |
| Transit Gateway | 1 Transit Gateway | Additional TGWs cannot be provisioned, limiting multi‑VPC or hybrid connectivity expansion. Remove duplicate TGWs created by multiple teams, assess reuse of existing TGWs, attach new VPCs if capacity permits, and monitor connection limits. |
| DNS (Cloud DNS Service) | 1 DNS instance | Additional DNS instances cannot be created, limiting domain segregation and environment isolation. Remove duplicate DNS instances across teams, reuse existing instances by adding zones or records, and follow proper naming conventions. |
| Secrets Manager | 1 instance | Additional instances cannot be provisioned, requiring environments to share a single Secrets Manager instance. Remove duplicates, organize secrets with groups and access policies, and validate access controls. |
| Security Groups | 10 security groups | Additional security groups cannot be created, potentially blocking new rules or instance launches. Review existing groups, reuse or update rules where possible, and remove unused groups. |
{: caption="Sandbox Quota Limits" caption-side="bottom"}
