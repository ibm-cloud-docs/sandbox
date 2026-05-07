---

copyright:
  years: 2026
lastupdated: "2026-05-07"

keywords: save configuration, terraform, export configuration, download terraform, infrastructure as code, terraform files

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Accessing Sandbox - CLI
{: #access-cli}

To access and manage {{site.data.keyword.sandbox_full_notm}} resources using the {{site.data.keyword.Bluemix_notm}} CLI, including installation steps, authentication, and essential commands for VPC infrastructure management.
{: shortdesc}


To access Sandbox using CLI, you need the following commands:

1. Log into the {{site.data.keyword.Bluemix_notm}} console at https://cloud.ibm.com.

2. On your profile icon, click **Log in to CLI and API** from the drop-down.

3. A pop-up window appears with **One-time passcode**. Copy the {{site.data.keyword.Bluemix_notm}} CLI login command:

    ```text
    ibmcloud login -a https://cloud.ibm.com --sso -r <enter the region> -g Default
    ```
    {: codeblock}

4. Install VPC Plugin using the command:

    ```text
    ibmcloud plugin install vpc-infrastructure
    ```
    {: codeblock}

5. Verify the installed plugins using the command:

    ```text
    ibmcloud plugin list
    ```
    {: codeblock}

6. Set the resource group using the command:

    ```text
    ibmcloud target -g <<enter the resource group>>
    ```
    {: codeblock}

The following are the commands to list and check the resources:

    | Command | Description |
    | ------- | --------- |
    | ibmcloud is vpcs | List the VPCs |
    | ibmcloud is subnets | List the subnets |
    | ibmcloud is instances | List the virtual server instances |
    | ibmcloud is regions | Check the region |
    | ibmcloud is zones | Check the zones |
    {: caption="Commands" caption-side="bottom"}

7. Following are the basic CLI verification commands:

    ```text
    ibmcloud --version
    ```
    {: codeblock}

    ```text
    ibmcloud help
    ```
    {: codeblock}

    ```text
    ibmcloud target
    ```
    {: codeblock}
