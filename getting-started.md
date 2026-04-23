---

copyright:
  years: 2026
lastupdated: "2026-04-23"

keywords:

subcollection: sandbox
content-type: tutorial

---

{{site.data.keyword.attribute-definition-list}}

# Getting Started with IBM Cloud Sandbox
{: #getting-started-sandbox}

The IBM Cloud Sandbox is a secure, scalable, and free-to-use trial environment designed to help customers explore and experience {{site.data.keyword.vpc_short}} and next-generation infrastructure. It helps users understand how the IBM Cloud infrastructure performs, behaves, and scales for their use cases before making production..
{: shortdesc}

It gives users a 2-week trial to experiment with, test, and assess their applications or workloads using {{site.data.keyword.vpc_short}} features.

The IBM Cloud Sandbox is ideal for:

- **Existing IBM Cloud Classic customers** running workloads on Classic Virtual Server or Bare Metal Server who want to explore VPC features, validate workload compatibility, and prepare for migration to next-generation VPC infrastructure.

- **Existing IBM Cloud users** who want hands-on experience with IBM Cloud services and VPC infrastructure. Users who require a safe, isolated environment to test VPC configurations, evaluate new compute profiles, or deploy workloads without affecting production environments.

## Before you begin
{: #before-you-begin}

Before you access the Cloud Sandbox, ensure that the following requirements are met:

* You need to have an active IBM Cloud account.

* You have a valid IBMid for authentication.

## Creating Sandbox account
{: #sandbox-request}
{: step}

1. An email notification is sent to all the allow-listed customers to experience the Cloud Sandbox environment.
2. After clicking **Request**, you will be redirected to the sandbox provisioning page to get started. Update the required information.

You will receive **Welcome to your IBM Cloud Sandbox** email. Now you are ready to deploy workloads, test configurations, and experience how VPC helps you build secure, scalable cloud environments.

## Access the IBM Cloud Catalog
{: #sandbox-catalog}
{: step}

The Cloud Sandbox is available through the IBM Cloud Catalog for the allowlisted customers.

1. Log in to the [IBM Cloud catalog](https://cloud.ibm.com/catalog#all_products){: external} page.
2. Search for **Cloud Sandbox**.
3. Click **Cloud Sandbox** tile to view the service details.

For more information on provisioning, see [Provisioning the IBM Cloud Sandbox](/docs-draft/sandbox?topic=sandbox-deploy) topic.

## Create your sandbox environment
{: #sandbox-create}
{: step}

Only users with **administrator** access in the Cloud Sandbox are authorized to create Sandbox accounts.
{: important}

You need to assign administrator access to yourself or to other users in your account who will be creating the sandbox. Perform the following steps:

1. On the Sandbox provision page, click **Create** tab.

2. Enter the required details:

   * **Sandbox name** - Provide a unique, descriptive name for your Sandbox environment (for example, "sandbox-month-date")

   * **Resource group** - Choose an existing resource group or create a new one to organize your sandbox resources. For more information on creating a new resource group, see [Creating a resource group](/docs/sandbox?topic=sandbox-create-resource-group).

   * **Region** - Select the geographic location where your Sandbox resources will be provisioned (for example, us-south, eu-de and so on). Users and their assigned roles cannot be changed later; any updates made afterward will not reflect in the trusted profile Sandbox account.

   Users should be certain about the region selection, as it cannot be changed later during provisioning or resource creation. All subsequent resources can only be created in the selected region.
   {: note}

   * **Tags** - Use the tags to organize your resources (for example, testing, team-alpha).

   * **Users** - Specify additional users who should have access to collaborate in this Sandbox environment (enter IBMids or email addresses). For more information on creating/adding users, see [Creating a user](/docs/sandbox?topic=sandbox-create-user).

3. Review the Sandbox configuration and trial period information (14 days).
   Before the 14‑day trial period, if no resources are created by day 7, the account is suspended on day 8; abuse reports also result in suspension.

4. Click **Create sandbox** to submit your request. The Sandbox provisioning process typically takes 5-10 minutes. You will receive a notification when your Sandbox environment is ready.

5. After the sandbox is created you can find them listed in the resource list of your account. You can edit the name, manage tags, or delete the Sandbox and all associated resources.

Only one Sandbox creation is allowed per allow-listed customer account.
{: tip}

## Access your sandbox through trusted profile
{: #sandbox-access-profile}
{: step}

After your Sandbox is provisioned, you will receive access for the trusted profile.

1. Check your email for the Sandbox access notification or click on **Trusted profiles** in the left navigation.

2. Locate your Sandbox trusted profile from the account drop-down with the tag `sandbox expires mm/dd`.

3. Switch from current account to the trusted profile.

4. Click **Create Resources** to access the resource creation page. The Quick Start page appears where you can begin provisioning the resources.

   Only user with write access can create the resources (administrator, editor, operator).
   {: note}

The trusted profile provides secure, time-limited access to your Sandbox environment with appropriate IAM permissions. It automatically expires after the 14-day trial period.
{: important}

## Provision resources using Quick Start
{: #sandbox-quickstart}
{: step}

The Sandbox environment includes Quick Start options to help you deploy common infrastructure resources. For more information, see [Quick Start](/docs/sandbox?topic=sandbox-quickstart) topic.

## Explore and test VPC capabilities
{: #sandbox-explore}
{: step}

After provisioning resources, use your Sandbox environment to explore VPC features and capabilities.

### Test networking features
{: #sandbox-test-networking}

- Configure and test subnets, security groups, and network ACLs
- Set up public and private connectivity
- Test network performance and latency
- Experiment with VPN and Transit Gateway configurations

### Evaluate compute options
{: #sandbox-test-compute}

- Deploy workloads on different instance profiles
- Test application performance and scalability
- Compare VSI and Bare Metal Server capabilities
- Evaluate auto-scaling configurations

### Assess storage solutions
{: #sandbox-test-storage}

- Attach and manage block storage volumes
- Test Cloud Object Storage integration
- Evaluate storage performance for your workloads
- Experiment with backup and snapshot capabilities

### Configure load balancing
{: #sandbox-test-loadbalancing}

- Set up application load balancers
- Test traffic distribution across instances
- Configure health checks and monitoring
- Evaluate high availability scenarios

## Collaborate with team members
{: #sandbox-collaborate}
{: step}

Users can be added only during the initial provisioning page, not during resource creation. Once users are added to a sandbox account at the time of creation, they remain unchanged until the trial ends. No modifications can be made later, and the roles assigned to them at creation time also remain the same throughout the trial period.

All sandbox resource usage is tracked under the sandbox account, with no billing during the trial period.

### Best practices for team collaboration
{: #best-collaborate}

- Communicate with your team about the purpose and scope before inviting them
- Assign appropriate permission levels based on each member's role and responsibilities
- Coordinate resource creation to avoid conflicts and stay within Sandbox limits
- Plan your 14-day trial period effectively to maximize team productivity

## Monitor your sandbox lifecycle
{: #sandbox-lifecycle}

Your Sandbox environment has a 14-day trial period. To track your remaining time:

1. View the trial period countdown on the Sandbox landing page.
2. Check your email for reminder notifications (typically sent at 7 days, 3 days, and 1 day before expiry).

After the 14-day trial period expires, all resources in the Sandbox environment are automatically deleted. Ensure you save any important data or configurations before the expiration date.
{: important}

If you need to extend your evaluation, you must save the configuration by downloading the Terraform package and running it in your own customer account

## Next steps
{: #next-steps}

- [Understanding VPC templates](/docs/vpc?topic=vpc-sandbox-templates)
- [Migrating from Classic to VPC](/docs/vpc?topic=vpc-sandbox-migration-guide)
- [VPC networking concepts](/docs/vpc?topic=vpc-about-networking-for-vpc)
- [Managing VPC resources](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console)
