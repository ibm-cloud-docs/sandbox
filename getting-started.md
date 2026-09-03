---

copyright:
  years: 2026
lastupdated: "2026-09-03"

keywords:

subcollection: sandbox

content-type: getting started

---

{{site.data.keyword.attribute-definition-list}}


# Getting Started with {{site.data.keyword.sandbox_full_notm}}
{: #getting-started-sandbox}

The {{site.data.keyword.sandbox_full_notm}} is a secure, scalable, and free-to-use trial environment designed to help customers explore and experience {{site.data.keyword.vpc_short}} and next-generation infrastructure. It helps users understand how the {{site.data.keyword.Bluemix_notm}} infrastructure performs, behaves, and scales for their use cases before making production.
{: shortdesc} 

It gives users a 2-week trial to experiment, test, and assess their applications or workloads using {{site.data.keyword.vpc_short}} features.

The {{site.data.keyword.sandbox_full_notm}} is ideal for:

- **Existing {{site.data.keyword.Bluemix_notm}} Classic customers** running workloads on Classic Virtual Server or Bare Metal Server who want to explore VPC features, validate workload compatibility, and prepare for migration to next-generation VPC infrastructure.

- **Existing {{site.data.keyword.Bluemix_notm}} users** who want hands-on experience with {{site.data.keyword.Bluemix_notm}} services and VPC infrastructure. Users who require a safe, isolated environment to test VPC configurations, evaluate new compute profiles, or deploy workloads without affecting production environments.

Do not use the Sandbox for production workloads. Sensitive or confidential data must not be stored during the two-week Sandbox tenure.
{: important}

To provision the Cloud Sandbox service from the IBM Cloud catalog, the user must have administrator-level permissions to initiate the deployment. Users with minimal permissions cannot provision the service. The administrator should have the below two permissions:

* All Identity and Access enabled services
* All Account Management services

or 

Users should be granted Administrator permissions for the **Cloud Sandbox** policy available in the IBM Cloud account. For more information, see [IAM Permissions](/docs/sandbox?topic=sandbox-manage-user-access-sandbox).

## Before you begin
{: #before-you-begin}

Before accessing the Cloud Sandbox, make sure you have the following:

* An active **{{site.data.keyword.Bluemix_notm}}** account.

* A valid **IBMid** to authenticate to IBM Cloud.

* An **allowlisted email address** associated with your account.

Once you have been allowlisted, you are ready to access Cloud Sandbox and deploy workloads, validate configurations, and explore how IBM Cloud VPC can help you build secure and scalable cloud solutions.

## Monitoring your Cloud Sandbox lifecycle
{: #sandbox-lifecycle}

After Cloud Sandbox access is approved, a welcome email is sent with instructions to access and create the Sandbox environment.

For accounts where a Cloud Sandbox has not yet been created after the welcome email is sent, reminder notifications are issued during the designated period:

    * Day 3 – First reminder
    * Day 6 – Second reminder
    * Day 9 – Final reminder

If a Cloud Sandbox is still not created after the final reminder:

    * The user is removed from Partner Center.
    * The user is removed from the Cloud Sandbox allowlist.
    
Users who create a Cloud Sandbox within the designated timeframe retain their allowlist status.

## Sandbox expiration and extension
{: #sandbox-expire}

A Cloud Sandbox is available for a default period of 14 days and can be extended by an additional 2 days.

Once the Sandbox lifecycle ends, the environment enters a cooling-off period, during which a new Sandbox cannot be created. After expiration, all resources associated with the Sandbox become inactive and are no longer available for use.

Once the account is deleted, all the data also gets deleted. The configuration saved by the user will be in the COS bucket.
{: important} 

## Creating Cloud Sandbox account
{: #sandbox-request}
{: step}

1. An email notification is sent to all the **allow-listed** customers to experience the Cloud Sandbox environment.
2. Click **Request** to open the [Cloud Sandbox provisioning page](https://cloud.ibm.com/sandbox/provision){: external}. Then, provide the required information to begin provisioning your Cloud Sandbox.

This link is available only to users who have been allowlisted.
{: note}

## Accessing the IBM Cloud Catalog
{: #sandbox-catalog}
{: step}

Navigate to the [{{site.data.keyword.Bluemix_notm}} catalog](https://cloud.ibm.com/catalog#highlights){: external} and search for the **Sandbox** offering.

For more information on provisioning, see [Provisioning the {{site.data.keyword.sandbox_full_notm}}](/docs/sandbox?topic=sandbox-deploy) topic.

## Creating your Cloud Sandbox environment
{: #sandbox-create}
{: step}

Only users with **administrator** access in the Cloud Sandbox are authorized to create Sandbox accounts.
{: important}

Perform the following steps to provision the Cloud Sandbox:

1. On the Cloud Sandbox provision page, enter the required details:

   * **Sandbox name** - Provide a unique, descriptive name for your Cloud Sandbox environment (for example, "sandbox-month-date").

   * **Resource group** - Choose an existing resource group or create a new one to organize your Cloud Sandbox resources.

   * **Region** - Select the geographic location where your Cloud Sandbox resources will be provisioned (for example, us-south, eu-de and so on).

   The region cannot be changed after provisioning, and all resources will be created in the selected region.
   {: note}

   * *Optional*: Enter tags to help you organize and find your resources. You can add more tags later. For more information, see [Working with tags](/docs/account?topic=account-tag&interface=ui).

   * **Users** - Select the users who will have access to Cloud Sandbox. All users are granted the same access level and permissions. For more information on creating or adding users, see [Creating or inviting a user and add Cloud Sandbox permission](/docs/sandbox?topic=sandbox-manage-user-access-sandbox#invite-user-sandbox).

    Users can be added during Sandbox account creation or at any time after the account has been provisioned. Once users are added to a Cloud Sandbox account at the time of creation, they remain unchanged until the trial ends. No modifications can be made later, and the roles assigned to them at creation time also remain the same throughout the trial period.
    {: important}

2. Click **Create Sandbox** to submit your request. The Cloud Sandbox provisioning process typically takes 5-10 minutes. You will receive an email when it is ready, or you can refresh and check the **Resource List** to see the instance.

3. After the Cloud Sandbox is created you can find them listed in the resource list of your account. You can edit the name, manage tags, or delete the Cloud Sandbox and all associated resources.

Only one Sandbox creation is allowed per allow-listed customer account.
{: tip}

## Accessing your Cloud Sandbox through email
{: #sandbox-access-profile}
{: step}

After your Cloud Sandbox is provisioned, an email is sent to all users with access details and supporting links to explore the Cloud Sandbox environment.

1. In the email, click the **Access the link and explore the Sandbox** link to open the Sandbox environment.

2. When prompted, provide your {{site.data.keyword.Bluemix_notm}} credentials to authenticate.

3. If two-factor authentication is enabled on your account, complete the verification process by providing the required authentication code.

4. After successful authentication, you are redirected to the Cloud Sandbox trusted profile page.

5. Select the trusted profile account (`sandbox expires mm/dd`) from the page.

6. You are navigated to the Cloud Sandbox trusted profile account.

7. Access the [Sandbox Overview page](http://cloud.ibm.com/sandbox/overview){: external} (which is quickstart) to begin creating resources and exploring VPC capabilities.

The trusted profile provides secure, time-limited access to your Cloud Sandbox environment with appropriate IAM permissions. It automatically expires after the 14-day trial period.
{: important}

## Provisioning resources
{: #sandbox-create-resources}
{: step}

In the Sandbox environment, you can create the resources from the Overview page. For more information, see [Creating resources in Sandbox](/docs/sandbox?topic=sandbox-create-resource) topic.

## Exploring VPC capabilities
{: #sandbox-explore}
{: step}

After provisioning resources, use your Cloud Sandbox environment to explore VPC features and capabilities.

### Testing network features
{: #sandbox-test-networking}

Configure and validate network components by setting up the subnets, security groups, and network ACLs. Establish the public and private connectivity by testing latency and performance and experimenting with VPN and Transit Gateway configurations.

* For more information on transit gateway, see [Creating a Transit Gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway).

* For more information on subnets, see [Working with subnets](/docs/vpc?topic=vpc-subnets-configure&interface=ui).

* For more information on network ACL, see [Creating a network ACL](/docs/vpc?topic=vpc-acl-create-ui&interface=ui).

* For more information on security group, see [Setting up a security group for your resource](/docs/vpc?topic=vpc-configuring-the-security-group&interface=ui).

* For more information on VPN for VPC, see [VPNs for VPC overview](/docs/vpc?topic=vpc-vpn-overview).

### Evaluating compute options
{: #sandbox-test-compute}

Deploy and compare workloads across different compute profiles to evaluating the performance, scalability, bare metal versus VSI capabilities, and auto-scaling behavior.

For more information on bare metal, see [Creating Bare Metal Servers on VPC](/docs/vpc?topic=vpc-creating-bare-metal-servers&interface=ui).

### Accessing storage solutions
{: #sandbox-test-storage}

Manage and evaluate storage by attaching block volumes, integrating {{site.data.keyword.cos_full_notm}} (COS), and testing performance.

* For more information on block volumes, see [Creating Block Storage for VPC volumes](/docs/vpc?topic=vpc-creating-block-storage&interface=ui).

* For more information on IBM Cloud Object Storage, see [Getting started with IBM Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage).

### Configuring load balancing
{: #sandbox-test-loadbalancing}

Configure and test application load balancing by distributing traffic across instances, setting up health checks and monitoring, and validating high availability scenarios.

For more information on load balancer, see [Creating an application load balancer](/docs/vpc?topic=vpc-load-balancers&interface=ui).

## Limitations
{: #sandbox-boundaries}

The Cloud Sandbox environment has specific limitations to ensure fair usage and maintain security.

### Service availability
{: #service-availability}

The Cloud Sandbox provides access to select {{site.data.keyword.Bluemix_notm}} Infrastructure as a Service (IaaS) offerings, including:

* Virtual Server for VPC and Bare Metal Servers for VPC
* Block Storage and Instance Storage for VPC
* {{site.data.keyword.cos_full_notm}}
* Virtual Private Cloud (VPC) networking components
* Load Balancer, Client VPN, and Transit Gateway
* DNS and Secrets Manager

The Cloud Sandbox environment does not provide access to {{site.data.keyword.Bluemix_notm}} services outside of these IaaS offerings.
{: note}

### Resource limitations
{: #resource-limit}

The Cloud Sandbox applies quota limits on compute, network, and storage resources to ensure optimal performance and fair usage. Following are the key limitations:

* **Compute**: Limited vCPU (128) and RAM (1028 GB) for Virtual Servers, and 1 Bare Metal Server
* **Storage**: Block Storage limited to 4096 GB per VSI, Instance Storage to 1024 GB, and {{site.data.keyword.cos_full_notm}} to 4096 GB
* **Network**: Maximum of 2 VPCs, 4 subnets, 4 Floating IPs, and 10 security groups
* **Services**: 1 instance each for Load Balancer, VPN, Transit Gateway, DNS, and Secrets Manager

For more details on quota limits, see [Sandbox quota limits](/docs/sandbox?topic=sandbox-sandbox-quota).

### Terms and conditions
{: #terms-conditions}

By using the Sandbox, you agree to the following:

* Use the environment for evaluation and testing purposes only, not for production workloads.
* Adhere to security best practices and the usage guidelines outlined in the [Limitations](/docs/sandbox?topic=sandbox-limitation) section.
* Accept that all resources will be automatically deleted at the end of the 14-day trial period.
* Comply with {{site.data.keyword.Bluemix_notm}} terms of service and acceptable use policies.

## Learn more
{: #next-steps}

- [VPC networking concepts](/docs/vpc?topic=vpc-about-networking-for-vpc)
- [Managing VPC resources](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console)
