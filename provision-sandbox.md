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

## Accessing Sandbox
{: #access-sandbox}

The Sandbox instance is displayed in the Resource list. To access the Sandbox environment:

1. Click on the Sandbox instance name in the **Resource list**

2. Select the trusted profile in the account switcher.

3. Click on the link in the welcome email.

    ![Sandbox - Resource list](images/sandbox-resource-list.png "Sandbox - Resource list"){: caption="Sandbox - Resource list" caption-side="bottom"}

## Creating resources in the Sandbox environment
{: #create-resources-sb}

You can create virtual servers or bare metal servers along with other VPC services.

1. On the Sandbox overview page, click on Create resources.

2. Select an image and profile for the instance. To select from all available images, click Change image. To select from all available profiles, click Change profile.

3. Under Additional services, you can enable and customize the services.

    * Cloud Object Storage
    * Load Balancer
    * VPN for VPC
        you are required to enter …..
    * Transit Gateway

4. Accept the terms and conditions, click **Create resources**.

Once resources have been created, you can view them from the Resource list.

## Supported actions
{: #actions-sb}

Following are the supported actions available on the Sandbox Oveview page:

* Extend the Sandbox trial
* End the Sandbox early
* Save the configuration

### Extending Sandbox
{: #extend-sb}

You can optionally extend the Sandbox trial for 2 days (48 hours) by clicking on **Extend Sandbox**. You will get an email confirming extension was granted and the countdown banner will increase by 2 days.

### End Sandbox
{: #end-sb}

You can optionally end the Sandbox trial any time by clicking **End Sandbox**. If you do so, the account will be suspended and you will not be able to access the resources you have created.

It is recommended to save the configuration, so that you can easily replicate your setup in your own account.
{: tip}

## Save configuration
{: #save-config-sb}

The Sandbox environment configuration can be downloaded as a Terraform packaging by clicking on **Save configuration**.
