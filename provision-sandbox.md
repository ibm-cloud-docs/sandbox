---

copyright:
  years: 2026
lastupdated: "2026-04-27"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Provisioning the IBM Cloud Sandbox
{: #deploy}

The solution uses the IBM Cloud Catalog service to ensure a unified and consistent approach.

## Creating the account using UI
{: #create-ui}

Only one sandbox is allowed per allowlisted customer account.
{: note}

1. Navigate to the [IBM Cloud catalog](https://cloud.ibm.com/catalog#highlights){: external} and search for the **Sandbox** offering.

    ![Sandbox - Catalog page](images/sandbox-catalog-page.png "Sandbox - Catalog page"){: caption="Sandbox - Catalog page" caption-side="bottom"}

2. In the **Create** tab, provide the following information under **Details**:

    * **Sandbox name** - Name of the sandbox instance.

    * **Region** - Region where the instance is provisioned.

    You will not be able to change the region once selected during the provisioning.
    {: note}

    * **Resource group** - Name from your IBM Cloud account where the Sandbox resource will be deployed.

    * **Tags** (optional) - Use the tags to organize your resources.

    ![Sandbox - Create](images/sandbox-create.png "Sandbox - Create"){: caption="Sandbox - Create" caption-side="bottom"}

3. In the **Users** section, you can select users from your account. For more information, see [Creating a user](/docs/sandbox?topic=sandbox-create-user).

6. Accept the terms and conditions, click **Create Sandbox**.

    Sandbox account is provisioned now. This includes a 14-day trial period with a 2 days (48 hours) extension. User access is limited to the region selected during provisioning.

    ![Sandbox - Create account](images/sandbox-create-account.png "Sandbox - Create account"){: caption="Sandbox - Create account" caption-side="bottom"}

6. Sandbox account is created for provisioning. This includes a 14-day trial period with a 2 days(48 hours) extension. User access is limited to the region selected during provisioning.

    ![Sandbox - Create account](images/sandbox-create-account.png "Sandbox - Create account"){: caption="Sandbox - Create account" caption-side="bottom"}

7. The Sandbox instance is displayed for provisioning in the **Resource list**.

    ![Sandbox - Resource list](images/sandbox-resource-list.png "Sandbox - Resource list"){: caption="Sandbox - Resource list" caption-side="bottom"}

8. A welcome email is sent and you can successfully log in to the Sandbox account.

9. Sandbox account is created for provisioning. This includes a 14-day trial period with a 2 days(48 hours) extension. User access is limited to the region selected during provisioning.

11. You will be redirected to the trusted profile by clicking **Continue**.

12. On the main **Sandbox Quick Start** page, click **Create** tab.

13. Under **Server Configuration**, select the server instances.

14. Select the image to configure the instances.

    ![Select image - Server instance](images/sandbox-select-image.png "Select image - Server instance"){: caption="Select image - Server instance" caption-side="bottom"}

15. Select the instance profile type.

    ![Select profile - Server instance](images/sandbox-select-instance-profile.png "Select profile - Server instance"){: caption="Select profile - Server instance" caption-side="bottom"}

16. Under **Additional services**, you can enable and customize the services.
    * Cloud Object Storage
    * Load Balancer
    * VPN for VPC
    * Transit Gateway

17. Accept the terms and conditions, click **Create resources**.

    ![Sandbox - Quickstart](images/ui-sandbox-quick-start.png "Sandbox - Quickstart"){: caption="Sandbox - Quickstart" caption-side="bottom"}

18. In the Resource list, you can see all the resources that you have created.

19. On the **Sandbox Overview** page, you can also:

    * **Manage Sandbox** - save the configuration by downloading the Terraform package and running it in your customer account. To run Terraform, the saved configuration must be run in the customer’s account with the necessary permissions for the required resources, and the account must have a Pay‑As‑You‑Go subscription type.

    ![Sandbox - Manage](images/sandbox-save-config.png "Sandbox - Manage"){: caption="Sandbox - Manage" caption-side="bottom"}

    * **Extend Sandbox** - extend the duration of the Sandbox trial environment. The extension is for 2 days(48 hours).

    ![Sandbox - Extend](images/sandbox-extend.png "Sandbox - Extend"){: caption="Sandbox - Extend" caption-side="bottom"}

    * **End Sandbox** - manually delete the Sandbox environment and all the associated resources. Once the sandbox is ended from the sandbox account, the corresponding resources must be manually deleted from the resource list for the changes to be reflected.

    ![Sandbox - End](images/sandbox-end.png "Sandbox - End"){: caption="Sandbox - End" caption-side="bottom"}
