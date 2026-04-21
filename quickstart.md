---

copyright:
  years: 2026
lastupdated: "2026-04-21"

keywords:

subcollection: sandbox

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Quick Start
{: #quickstart}

On this Quick Start page, you can create the resources quickly. You can create virtual server or bare metal instance for compute. You can also add optional services using the default configuration.

## Create servers
{: #sandbox-create-servers}

1. From the sandbox landing page, navigate to **Quick Start > Create resources for Sandbox**.

2. **Choose your server type**

   Click **Servers (Create VSI/BM)** to begin provisioning compute resources. You'll be presented with two server options:

   * **Virtual Server Instances (VSI)** - Ideal for most use cases, VSIs are virtual machines that offer flexibility, quick deployment, and cost-effectiveness. Choose this option for:

     - Development and testing environments
     - Web applications and microservices
     - Learning and experimentation
     - Workloads that don't require dedicated hardware

   * **Bare Metal Servers (BM)** - Physical servers dedicated entirely to your workload, providing maximum performance and isolation. Consider this option for:

     - High-performance computing requirements
     - Database servers with intensive I/O operations
     - Applications requiring consistent performance
     - Workloads with strict compliance or security requirements

3. **Configure your server settings**

   After selecting your server type, you need to configure several important settings. Take your time to review each option:

   **Operating System Selection**

   - Browse available operating systems including Linux distributions (Ubuntu, CentOS, Red Hat Enterprise Linux, Debian) and Windows Server editions.
   - Note that some operating systems may have licensing implications outside the sandbox trial.

   **Compute Profile**

   - **Balanced**: Equal distribution of CPU, memory, and network resources - suitable for general-purpose applications.
   - **Compute-optimized**: Higher CPU-to-memory ratio - ideal for compute-intensive tasks like batch processing or scientific computing.
   - **Memory-optimized**: Higher memory-to-CPU ratio - perfect for databases, caching systems, or in-memory analytics.
   - Review the specific vCPU and RAM allocations for each profile to match your workload needs.

   **Network Configuration**

   - Select the network interface settings for your server.
   - Configure public and private network access based on your security requirements.
   - Public network: Allows internet access for your server (useful for web-facing applications).
   - Private network: Restricts access to within your IBM Cloud environment (recommended for backend services).
   - You can configure firewall rules and security groups to control traffic.

   **Storage Volumes**

   - Choose the boot volume size (primary disk for your operating system).
   - Add additional data volumes if your application requires separate storage for databases, logs, or user data.
   - Consider the storage type (SSD for performance, HDD for capacity) based on your input output requirements.
   - Plan your storage allocation carefully as it affects both performance and resource limits.

4. **Review and create your server**

   - Before finalizing, review all your configuration choices in the summary panel.
   - Verify the server name, location, and specifications match your requirements.
   - Check the estimated resource consumption against your sandbox limits.
   - Click **Create** to begin the provisioning process.
   - The server creation typically takes 5-15 minutes depending on the configuration.
   - You will receive a notification once your server is ready, and it will appear in your resource list with an **Active** status.
   - After creation, you will receive connection details including IP addresses and access credentials via email or in the server details page.

1. On the main **Sandbox Quick Start** page, click **Create** tab.

    You will not be able to change the region once selected during the provisioning.
    {: note}

2. Under **Server Configuration**, select the server instances.

3. Select the image to configure the instances.

    ![Select image - Server instance](images/sandbox-select-image.png "Select image - Server instance"){: caption="Select image - Server instance" caption-side="bottom"}

4. Select the instance profile type.

    ![Select profile - Server instance](images/sandbox-select-instance-profile.png "Select profile - Server instance"){: caption="Select profile - Server instance" caption-side="bottom"}

5. Under **Additional services**, you can enable and customize the services.
    * **Cloud Object Storage** - Deploy scalable object storage for data, backups, and application content

    * **Load Balancer** - Configure load balancers to distribute traffic across multiple server instances for high availability

    * **VPN for VPC** - Set up secure VPN connectivity to access your sandbox environment from on-premises networks or remote locations

    * **Transit Gateway** - Connect multiple VPCs or integrate with on-premises networks for hybrid cloud scenarios

6. Accept the terms and conditions, click **Create resources**.

    ![Sandbox - Quickstart](images/ui-sandbox-quick-start.png "Sandbox - Quickstart"){: caption="Sandbox - Quickstart" caption-side="bottom"}

7. To check the resources, go to the navigation menu > **Resource list**. You can see all the resources that you have created.




### Deploy additional services
{: #sandbox-additional-services}

Enhance your sandbox environment with additional VPC services:

* **Cloud Object Storage** - Deploy scalable object storage for data, backups, and application content

* **Load Balancer** - Configure load balancers to distribute traffic across multiple server instances for high availability

* **VPN for VPC** - Set up secure VPN connectivity to access your sandbox environment from on-premises networks or remote locations

* **Transit Gateway** - Connect multiple VPCs or integrate with on-premises networks for hybrid cloud scenarios

To deploy any of these services:

1. Navigate to **Quick Start > Additional Services**.
2. Select the service you want to deploy.
3. Configure the service parameters.
4. Click **Create** to provision the service.
