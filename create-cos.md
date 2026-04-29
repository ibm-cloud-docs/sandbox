---

copyright:
  years: 2026
lastupdated: "2026-04-29"

keywords:

subcollection: sandbox
content-type: tutorial

---

{{site.data.keyword.attribute-definition-list}}

# Creating a Cloud Object Storage (COS) instance
{: #create-cos}

IBM Cloud Object Storage is strongly consistent for all data operations, and eventually consistent for bucket configuration operations. For more information, see [Getting started with IBM Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage).

Following are the steps to create an instance of IBM Cloud Object Storage:

1. Navigate to **Menu** > **Infrastructure** > **Storage** > **Object storage**.

2. Click **Create an instance**.

3. Configure the instance:

    * Select a pricing plan.
    * Review the instance name.

4. Click **Create**.

    ![Create Cloud Object Storage (COS)](images/create-cos.png "Create Cloud Object Storage (COS)"){: caption="Create Cloud Object Storage (COS)" caption-side="bottom"}

5. From the instance, go to the **Service Credentials** tab and click **New Credential** so that your applications or services can access the COS instance.

6. Configure the credentials:

    - If you do not wish to use Secrets Manager, turn off the toggle or click **Create** to create a secret manager.
    - Enter the credential information.

    ![COS credentials](images/add-credentials.png "COS credentials"){: caption="COS credentials" caption-side="bottom"}

7. Click **Add**.

## Creating a COS bucket
{: #create-cos-bucket}

Following are the steps to create a COS bucket:

1. Navigate to **Menu** > **Infrastructure** > **Storage** > **Object storage**.

2. In the left navigation, select an instance.

3. Click **Create Bucket**.

4. You may choose a template or create a custom bucket.

5. For a custom bucket, configure:

    - A unique name is provided. Review or enter a new name.

    - Choose the Resiliency and Location.

    The location should be same as the one selected during Sandbox provisioning.
    {: important}

    - Select the Storage Class (Standard, Vault, Cold Vault, Flex)

    - Configure any other options as required.

6. Click **Create bucket**.
