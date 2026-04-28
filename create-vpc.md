---

copyright:
  years: 2024, 2026
lastupdated: "2026-04-23"

keywords: transit gateway, classic to vpc, ssh access, rdp access, server connection, data migration

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Creating a VPC
{: #create-vpc}

A virtual private cloud (VPC) is a secure, isolated virtual network that combines the security of a private cloud with the availability and scalability of IBM's public cloud.

To create and configure your VPC in the Cloud Sandbox account, perform the folowing steps:

1. In the [IBM Cloud console](/catalog#highlights), navigate to **Menu** > **Infrastructure** > **Network** > **VPCs**.

2. Click **Create**.

3. Under the **Create** tab, update the following details:

    * Under **Location**, you need to select the **Geography** and **Region** same as the one updated during the Sandbox provisioning.

    The provisioning fails if the regions do not match.
    {: note}

    * Under **Details**, provide a unique name. Use lowercase alphanumeric characters and hyphens only (without spaces).

    * Under **Resource group**, you can select the existing resource groups from the drop-down or create a new one.

    * Tags (Optional)

4. Under **Subnets**, you can view the subnet created.

    ![VPC subnet](images/vpc-subnet.png "VPC subnet"){: caption="VPC subnet" caption-side="bottom"}

5. Click **Create virtual private cloud**.

You will be redirected to the page where your VPC is created.
