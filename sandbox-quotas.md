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
| Virtual Private Cloud | Creation of 2 VPC in the selected region |  |
| Subnets for VPC | Overall they can create 4 subnets from the two vpc limit |  |
| Floating IPs | Can create 4 Floating ip from the limit |  |
| Load Balancer | Can provision 1 Application LB |  |
| Client VPN | 1 VPN instance |  |
| Transit Gateway | 1 Transit Gateway |  |
| DNS (Cloud DNS Service) | 1 DNS instance |  |
| Secrets Manager | 1 instance |  |
| Security Groups | 10 security groups |  |
{: caption="Sandbox Quota Limits" caption-side="bottom"}
