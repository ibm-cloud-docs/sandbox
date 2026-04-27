---

copyright:
  years: 2024, 2026
lastupdated: "2026-04-23"

keywords: transit gateway, classic to vpc, ssh access, rdp access, server connection, data migration

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Connecting to servers and migrating data
{: #connect-migrate}

After your Sandbox environment is active, you can securely access Linux or Windows Virtual Server Instances (VSIs) and migrate data between IBM Classic infrastructure and VPC.

## Before you begin
{: #before-you-begin}

- Ensure you have the private key associated with the public SSH key used to create the server
- Download and install the [IBM Cloud CLI](/docs/cli?topic=cli-getting-started) and the infrastructure-service plug-in
- For Windows servers, have Microsoft Remote Desktop client software available
- Verify security group settings allow required traffic (SSH port 22 for Linux, RDP port 3389 for Windows)
- Reserve and associate a floating IP address to your instance

## Connecting to Linux or Windows servers
{: #connect}

### Step 1: Identify the Floating IP
{: #fp}

1. In the IBM Cloud console, go to **Resource List** → **Compute** → **Virtual Server Instances**.
2. Select your VSI and click the **Networking** tab.
3. Copy the **Floating IP** address from the table.

### Step 2: Download the SSH key from Secrets Manager
{: #secret-manager}

1. Go to **Resource List** → **Security** → **Secrets Manager**.
2. Open your Sandbox Secrets Manager instance.
3. Locate your SSH private key secret, click the overflow menu (⋮), and select **View Secret**.
4. Copy the secret contents and save to a file (for example, `key.pem`).
5. Set appropriate permissions:
   ```sh
   chmod 400 key.pem
   ```

### Step 3: Connect to the server
{: #connect-server}

#### Linux server (SSH)
{: #ssh}

1. Open your terminal.
2. Run the following command:
   ```sh
   ssh -i <path-to-key.pem> root@<Floating-IP>
   ```
3. Accept the fingerprint when prompted.

#### Windows server (RDP)
{: #rdp}

1. Check instance status:
   ```sh
   ibmcloud is instance INSTANCE
   ```
   Wait until the instance status is `running`.

2. Retrieve the Windows Administrator password:
   ```sh
   ibmcloud is instance-initialization-values INSTANCE --private-key "@~/.ssh/id_rsa"
   ```

3. If needed, assign a floating IP:
   ```sh
   ibmcloud is floating-ip-reserve FLOATING_IP_NAME --nic NIC_NAME
   ```

4. Open Remote Desktop Connection (RDP) on your computer.
5. Enter the Floating IP as the computer address.
6. Log in with username `Administrator` and the retrieved password.

For more information, see [Connecting to Windows instances](/docs/vpc?topic=vpc-vsi_is_connecting_windows).

## Creating a Transit Gateway for Classic-to-VPC connectivity
{: #create-tg-overview}

A Transit Gateway enables secure private network communication between IBM Classic infrastructure and VPC environments for application migration and data transfer.

### Step 1: Create the Transit Gateway
{: #create-tg}

1. In the IBM Cloud console, go to **Menu** → **Infrastructure** → **Network** → **Transit Gateway**.
2. Click **Create Transit Gateway**.
3. Enter a name (for example, `sandbox-classic-vpc-tgw`).
4. Select your Sandbox resource group.
5. Choose the location where your VPC exists.
6. Click **Create**.

### Step 2: Attach Classic infrastructure
{: #attach-classic}

1. Open your Transit Gateway.
2. Go to **Connections** → **Add connection**.
3. Select **Classic infrastructure** as the connection type.
4. Choose **Request connection to a network in another account**.
5. Provide the Cloud account ID and connection name.
6. Select the Classic account and required VLAN(s).
7. Click **Add**.

### Step 3: Attach the VPC
{: #attach-vpc}

1. Click **Add connection** again.
2. Select **VPC** as the connection type.
3. With **Add new connection in this account** selected, choose the region and VPC.
4. Optionally, provide a connection name.
5. Click **Add**.

### Step 4: Verify connections
{: #verify-connection}

1. Confirm both connections show **Attached** status.
2. Test connectivity using private IP addresses:
   ```sh
   ping <private-IP-of-other-server>
   ```

For more information, see [Getting started with IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-getting-started).

## Copying data from Classic to VPC using SCP
{: #copy-data}

### Step 1: Identify IP addresses
{: #ip}

You need the private IP addresses of both servers:
- **Classic server**: Go to **Classic Infrastructure** → **Devices** → **Device List** → **Private IP** column
- **VPC server**: Go to **Infrastructure** → **Virtual server instances** → **Reserved IP** column

### Step 2: Get SSH credentials
{: #ssh-cred}

Refer to [Connecting to Linux or Windows servers](#connecting-to-linux-or-windows-servers) for SSH key retrieval.

### Step 3: Transfer data
{: #transfer-data}

Copy from Classic to VPC:
```sh
scp -i /path/to/vpc-key.pem /path/to/file user@<VPC-Private-IP>:/destination/path
```

Copy from VPC to Classic:
```sh
scp -i /path/to/classic-key.pem /path/to/file user@<Classic-Private-IP>:/destination/path
```

To copy entire directories, add the `-r` flag:
```sh
scp -r -i vpc-key.pem /path/to/folder user@<VPC-Private-IP>:/target/location
```

### Step 4: Verify the transfer
{: #verify-data}

Check the destination directory:
```sh
ls -lh /destination/path
```

Verify file size, timestamps, and contents to confirm successful transfer.
