---

copyright:
  years: 2026
lastupdated: "2026-05-07"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

The resource capacity and quota limits that apply to {{site.data.keyword.sandbox_full_notm}} environments, including restrictions for compute, storage, networking, and security resources.
{: shortdesc}

# Sandbox quota limits
{: #sandbox-quota}

Following is the table list of Sandbox resource capacity and Quota limits:

| Resource name | Supported capacity | Impact |
| ------- | --------- | ---- |
| Virtual Server for VPC | vCPU: 128 \n RAM:1028GB | Instance provisioning may fail or stay in a pending state due to insufficient quota. |
| Bare Metal Servers for VPC | 1 | No additional bare metal can be provisioned once the limit is reached. |
| Block Storage for VPC | Allowed is 4096GB of data volume per VSI | Any volume larger than 4096 GB will be deleted. |
| Instance Storage for VPC | 1024 GB of instance storage | New volume creation may fail and existing workloads could face storage constraints. |
| {{site.data.keyword.cos_full_notm}} | 4096 GB \n 1 COS instance | Approaching capacity limits may cause upload failures or degraded performance. Monitor bucket usage, archive or delete unused data, apply lifecycle policies, and scale the storage plan if needed. Any COS storage exceeding 4096 GB will be deleted. |
| Virtual Private Cloud | Creation of 2 VPC in the selected region | Additional VPCs cannot be provisioned, preventing new environment creation. Verify the current VPC count and reuse existing VPCs or remove unused ones. |
| Subnets for VPC | 2 subnets per VPC, total count is 4 | Additional subnets cannot be created, which may block network segmentation. Plan subnet allocation in advance and reuse existing subnets. |
| Floating IPs | 4 FIP | Additional FIPs cannot be created, preventing public access for required instances and causing connectivity issues. Review FIP usage, release unused IPs, and reassign existing ones where possible. |
| Load Balancer | 1 load balancer | Additional load balancers cannot be provisioned, limiting traffic distribution and high‑availability setups. Reuse existing load balancers with multiple listeners or pools and optimize configurations. |
| Client VPN | 1 VPN instance | Additional VPNs cannot be provisioned, preventing secure access for new users or environments. Review existing VPN usage and reuse the current VPN by adding users or configurations. |
| Transit Gateway | 1 Transit Gateway | Additional TGWs cannot be provisioned, limiting multi‑VPC or hybrid connectivity expansion. |
| DNS (Cloud DNS Service) | 1 DNS instance | Additional DNS instances cannot be created, limiting domain segregation and environment isolation. |
| Secrets Manager | 1 instance | Additional instances cannot be provisioned, requiring environments to share a single Secrets Manager instance. |
| Security Groups | 10 security groups | Additional security groups cannot be created, potentially blocking new rules or instance launches. Review existing groups, reuse or update rules where possible, and remove unused groups. |
{: caption="Sandbox Quota Limits" caption-side="bottom"}
