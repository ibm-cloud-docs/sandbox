---

copyright:
  years: 2026
lastupdated: "2026-04-23"

keywords: transit gateway, classic to vpc, ssh access, rdp access, server connection, data migration

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}


# Creating a Transit Gateway for Classic-to-VPC connectivity
{: #create-transit-gateway}

A Transit Gateway enables secure private network communication between IBM Classic infrastructure and VPC environments for application migration and data transfer.

## Create the Transit Gateway
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
