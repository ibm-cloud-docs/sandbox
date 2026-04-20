---

copyright:
  years: 2026
lastupdated: "2026-04-20"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Verify access policies
{: #sandbox-verify-policy}

IBM Cloud® Identity and Access Management (IAM) policies assigned in the sandbox environment for the customer trusted profile.

## IAM policies
{: #iam-policies}

Following is the list of custom IAM Policies assigned to trusted profile:

   | Service | Resources | Roles |
   | ------- | --------- | ---- |
   | All IAM Account Management services | All | Viewer |
   | Cloud Object Storage | All | SandboxCOSRole |
   | Catalog Management | All | Editor |
   | DNS Services | All | Manager, Editor |
   | Resource group only | All resource groups in the account | Editor |
   | Secrets Manager | Region string equals us-east | Manager, Editor, SecretsReader |
   | Transit Gateway | All | Manager, Editor |
   | User Management | All | Viewer |
   | VPC Infrastructure Services | Region string equals us-east | \n * SandboxVirtualServerforVPCRole, \n * SandboxVirtualPrivateCloudRole, \n * SandboxVNetworkInterfaceRole, \n * SandboxSSHKeyforVPCRole, \n * SandboxSubnetRole, \n * SandboxSecGroupforVPCRole, \n * SandboxFloatingIPforVPCRole, \n * SandboxClientVPNforVPCRole, \n * SandboxBMServersforVPCRole, \n * SandboxNetworkACLRole, \n * SandboxLoadBalancerforVPCRole, \n * SandboxImageServiceforVPCRole, \n * SandboxBlockStorageforVPCRole |
   {: caption="IAM policies" caption-side="bottom"}

## Sandbox IAM policies
{: #sandbox-iam-policies}

Following is the list of IAM policies defined for our Sandbox service:

   | Action | Display name | Roles |
   | ------- | --------- | ---- |
   | sandbox.instance.read | Sandbox Viewer | Administrator, Editor, Operator, Viewer |
   | sandbox.instance.operate | Sandbox Operator | Administrator, Editor, Operator |
   | sandbox.instance.editor | Sandbox Editor | Administrator, Editor |
   | sandbox.instance.admin | Sandbox Administrator | Manager, Administrator |
   {: caption="Sandbox IAM policies" caption-side="bottom"}
