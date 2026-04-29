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

When your Sandbox environment is provisioned, an SSH key pair is automatically created for secure server access. The private key is stored in IBM Cloud Secrets Manager for you to download and use. The following steps guide you through retrieving this key and connecting to your servers.

## Before you begin
{: #before-you-begin}

- Download and install the [IBM Cloud CLI](/docs/cli?topic=cli-getting-started) and the [VPC infrastructure CLI plug-in](/docs/cli?topic=cli-vpc-reference)
- For Windows servers, have Microsoft Remote Desktop Protocol (RDP) client software available

## Connecting to Linux or Windows servers
{: #connecting-servers}

### Step 1: Reserve and identify the Floating IP
{: #reserve-floating-ip}

If you haven't already reserved a floating IP address for your instance, follow the instructions in [Reserving a floating IP address](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console#reserving-a-floating-ip-address).

After reserving the floating IP:

1. In the IBM Cloud console, go to **Resource List** > **Compute** > **Virtual Server Instances**.
2. Select your VSI and click the **Networking** tab.
3. Copy the **Floating IP** address from the table.

### Download the SSH key from Secrets Manager
{: #download-ssh-key}

1. Go to **Resource List** > **Security** > **Secrets Manager**.
2. Open your Sandbox Secrets Manager instance.
3. Locate your SSH private key secret, click the overflow menu (⋮), and select **View Secret**.
4. Download the secret key and save to a file (for example, `key.pem`).
5. Set appropriate permissions:

   ```sh
   $ chmod 400 key.pem
   ```

### Step 3: Check instance status
{: #check-instance-status}

Before connecting, verify your CLI is targeting the correct region. If needed, see [Targeting a region](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_target).

First, list all your instances to get the instance ID:
```sh
$ ibmcloud is instances
```

Then check the instance status using the ID from the previous command:
```sh
$ ibmcloud is instance INSTANCE_ID
```
Replace `INSTANCE_ID` with the ID or name of your instance. Wait until the instance status is `running`.

### Step 4: Connect to the server
{: #connect-server}

#### Linux server (SSH)
{: #linux-ssh}

1. Run the following command:

   ```sh
   $ ssh -i <path-to-key.pem> root@<Floating-IP>
   ```
   
2. Accept the fingerprint when prompted.

3. When prompted, confirm the fingerprint.

1. Retrieve the Windows Administrator password using the private key:

   ```sh
   $ ibmcloud is instance-initialization-values INSTANCE_ID --private-key "@~/.ssh/id_rsa"
   ```
   Replace `INSTANCE_ID` with your instance ID or name.

2. Open Remote Desktop Connection (RDP) on your computer.
3. Enter the Floating IP as the computer address.
4. Log in with username `Administrator` and the retrieved password.

For more information, see [Connecting to Windows instances](/docs/vpc?topic=vpc-vsi_is_connecting_windows).

## Creating a Transit Gateway for Classic-to-VPC connectivity
{: #create-transit-gateway}

A Transit Gateway enables secure private network communication between IBM Classic infrastructure and VPC environments for application migration and data transfer.

### Create the Transit Gateway
{: #create-tgw-step1}

1. In the IBM Cloud console, go to **Menu** > **Infrastructure** > **Network** > **Transit Gateway**.
2. Click **Create Transit Gateway**.
3. Enter a name (for example, `sandbox-classic-vpc-tgw`).
4. Select your Sandbox resource group.
5. Choose the location where your VPC exists.
6. Click **Create**.

### Attach Classic infrastructure
{: #attach-classic}

1. Open your Transit Gateway.
2. Go to **Connections** > **Add connection**.
3. Select **Classic infrastructure** as the connection type.
4. Choose **Request connection to a network in another account**.
5. Provide the Cloud account ID and connection name.
6. Select the Classic account and required VLAN(s).
7. Click **Add**.

### Attach the VPC
{: #attach-vpc}

1. Click **Add connection** again.
2. Select **VPC** as the connection type.
3. With **Add new connection in this account** selected, choose the region and VPC.
4. Optionally, provide a connection name.
5. Click **Add**.

### Verify connections
{: #verify-connections}

1. Confirm both connections show **Attached** status.
2. Test connectivity using private IP addresses:

   ```sh
   $ ping <private-IP-of-other-server>
   ```

For more information, see [Getting started with IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-getting-started).

## Copying data from Classic to VPC using SCP
{: #copy-data-scp}

### Identify IP addresses
{: #ip}

You need the private IP addresses of both servers:

- **Classic server**: Go to **Classic Infrastructure** > **Devices** > **Device List** > **Private IP** column.
- **VPC server**: Go to **Infrastructure** → **Virtual server instances** → **Reserved IP** column.

### Get SSH credentials
{: #get-ssh-credentials}

Refer to [Connecting to Linux or Windows servers](#connecting-to-linux-or-windows-servers) for SSH key retrieval.

### Transfer data
{: #transfer-data}

Copy file from Classic to VPC:

```sh
$ scp -i /path/to/vpc-key.pem /path/to/file user@<VPC-Private-IP>:/destination/path
```

Copy file from VPC to Classic:

```sh
$ scp -i /path/to/classic-key.pem /path/to/file user@<Classic-Private-IP>:/destination/path
```

To copy entire directories, add the `-r` flag:

```sh
$ scp -r -i vpc-key.pem /path/to/folder user@<VPC-Private-IP>:/target/location
```

### Verify the transfer
{: #verify-transfer}

Check the destination directory:

```sh
$ ls -lh /destination/path
$ du -sh /destination/path
```

Verify file size, timestamps, and contents to confirm successful transfer.
