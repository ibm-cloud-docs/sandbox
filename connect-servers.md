---

copyright:
  years: 2026
lastupdated: "2026-04-23"

keywords: transit gateway, classic to vpc, ssh access, rdp access, server connection, data migration

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Connecting to servers and migrating data
{: #connect-migrate}

After your Sandbox environment is active, you can securely access Linux or Windows virtual server instance (VSIs) and migrate data between IBM Classic infrastructure and VPC infrastructure.

When your Sandbox environment is provisioned, an SSH key pair is automatically created for secure server access. The private key is stored in {{site.data.keyword.Bluemix_notm}} Secrets Manager for you to download and use. The following steps guide you through retrieving this key and connecting to your servers.

## Before you begin
{: #before-you-begin}

- Download and install the [{{site.data.keyword.Bluemix_notm}} CLI](/docs/cli?topic=cli-getting-started) and the [VPC infrastructure CLI plug-in](/docs/cli?topic=cli-vpc-reference).
- For Windows servers, have Microsoft Remote Desktop Protocol (RDP) client software available.

Logging into a VSI using an SSH key from Secrets Manager is supported only when the VSI is created through the Quickstart page. If a user creates a VSI from the IBM Cloud UI instead, they must provide their own SSH key. For more information, see [Getting started with SSH keys](/docs/vpc?topic=vpc-ssh-keys&interface=ui).
{: important}

## Connecting to Linux or Windows servers
{: #connecting-servers}

### Step 1: Reserve and identify the Floating IP
{: #reserve-floating-ip}

If you haven't already reserved a floating IP address for your instance, follow the instructions in [Reserving a floating IP address](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console#reserving-a-floating-ip-address).

After reserving the floating IP:

1. In the {{site.data.keyword.Bluemix_notm}} console, go to **Resource List** > **Compute** > **Virtual Server Instances**.
2. Select your VSI and click the **Networking** tab.
3. Copy the **Floating IP** address from the table.

### Download the SSH key from Secrets Manager
{: #download-ssh-key}

1. Go to **Resource List** > **Security** > **Secrets Manager**.
2. Open your Sandbox Secrets Manager instance.
3. Locate your SSH private key secret, click the overflow menu (⋮), and select **View Secret**.
4. Download the secret key and save to a file (for example, `key.pem`).
5. Set appropriate permissions:

   ```text
   chmod 400 key.pem
   ```
   {: codeblock}

### Step 3: Check instance status
{: #check-instance-status}

Before connecting, verify your CLI is targeting the correct region. If needed, see [Targeting a region](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_target).

First, list all your instances to get the instance ID:

```text
ibmcloud is instances
```
{: codeblock}

Then check the instance status using the ID from the previous command:

```text
ibmcloud is instance INSTANCE_ID
```
{: codeblock}

Replace `INSTANCE_ID` with the ID or name of your instance. Wait until the instance status is `running`.

### Step 4: Connect to the server
{: #connect-server}

#### Linux server (SSH)
{: #linux-ssh}

1. Run the following command:

   ```text
   ssh -i <path-to-key.pem> root@<Floating-IP>
   ```
   {: codeblock}

2. Accept the fingerprint when prompted.

3. When prompted, confirm the fingerprint.

1. Retrieve the Windows Administrator password using the private key:

   ```text
   ibmcloud is instance-initialization-values INSTANCE_ID --private-key "@~/.ssh/id_rsa"
   ```
   {: codeblock}
   Replace `INSTANCE_ID` with your instance ID or name.

2. Open Remote Desktop Connection (RDP) on your computer.
3. Enter the Floating IP as the computer address.
4. Log in with username `Administrator` and the retrieved password.

For more information, see [Connecting to Windows instances](/docs/vpc?topic=vpc-vsi_is_connecting_windows).
