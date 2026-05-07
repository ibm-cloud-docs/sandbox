---

copyright:
  years: 2026
lastupdated: "2026-05-06"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Creating resources in Sandbox
{: #create-resource}

Create and configure compute resources such as Virtual Server Instances or Bare Metal servers in your {{site.data.keyword.sandbox_full_notm}} environment, along with optional services like {{site.data.keyword.cos_short}}, Load Balancer, VPN, and Transit Gateway.
{: shortdesc}

Before you create resources, switch to the trusted profile by using the account switcher in the console menu bar.
   {: note}

On the **Sandbox Overview** page, you can create compute resources such as Virtual Server Instances or Bare Metal servers. You can also add optional services using the default configuration.

1. From the Sandbox Overview page, click **Create resources**.

    ![Sandbox - Overview](images/ui-sandbox-quick-start.png "Sandbox - Overview"){: caption="Sandbox - Overview" caption-side="bottom"}

2. Under **Server Configuration**:

    * The image is selected by default. But you can change if required by clicking **Change image**.

    ![Select image - Server instance](images/sandbox-select-image.png "Select image - Server instance"){: caption="Select image - Server instance" caption-side="bottom"}

    * The profile type is selected by default. But you can change if required by clicking **Change profile**.

    ![Select profile - Server instance](images/sandbox-select-instance-profile.png "Select profile - Server instance"){: caption="Select profile - Server instance" caption-side="bottom"}

    Users can choose from different images and profiles apart from those included in the Quickstart.
    {: note}


3. Under **Additional services**, you can enable and customize the services.

    * **{{site.data.keyword.cos_full_notm}}** - Deploy scalable object storage for data, backups, and application content.

    * **Load Balancer** - Configure load balancers to distribute traffic across multiple server instances for high availability.

    * **VPN for VPC** - Set up secure VPN connectivity to access your sandbox environment from on-premises networks or remote locations.

    * **Transit Gateway** - Connect multiple VPCs or integrate with on-premises networks for hybrid cloud scenarios.

4. You can verify the resources to be created in the **Summary** and accept the terms and conditions.

5. Click **Create resources**.

You can view the created resources under **Resource list**.
