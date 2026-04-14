---

copyright:
  years: 2026
lastupdated: "2026-04-14"

keywords:

subcollection: sandbox
content-type: tutorial

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with IBM Cloud Sandbox
{: #getting-started-sandbox}

The IBM Cloud Sandbox enables users to explore and evaluate {{site.data.keyword.vpc_short}} capabilities in a realistic environment—without cost or long‑term commitment. It helps users understand how the IBM Cloud infrastructure performs, behaves, and scales for their use cases before making production or migration decisions.
{: shortdesc}

The Sandbox platform provides a secure, automated, and scalable environment that enables users to discover IBM Cloud offerings from the IBM Cloud Catalog, provision sandbox environment, deploy workloads, and evaluate {{site.data.keyword.vpc_short}} capabilities with minimal setup effort.

The IBM Cloud Sandbox is ideal for:

- Existing IBM Cloud Classic customers running workloads on Classic Virtual Server or Bare Metal Server who want to explore VPC features, validate workload compatibility, and prepare for migration to next-generation VPC infrastructure.

- Existing IBM Cloud users who require a safe, isolated environment to test VPC configurations, evaluate new compute profiles, or deploy workloads without affecting production environments.

- New IBM Cloud users who want hands-on experience with IBM Cloud services, VPC capabilities, deployment models, and the next-generation infrastructure—available free of charge for 14 days before implementation in their own account.

## Before you begin
{: #before-you-begin}

Before you access the IBM Cloud Sandbox, ensure that the following requirements are met:

* You have an active IBM Cloud account with Classic infrastructure resources.
* You are enrolled in the IBM Cloud Sandbox program (Phase 1 requires allow-list approval).
* You have the necessary IAM permissions to create and manage VPC resources.
* You have reviewed the [IBM Cloud Sandbox overview](/docs/vpc?topic=vpc-sandbox-overview).

## Request sandbox access
{: #sandbox-request}
{: step}

For phase 1, IBM Cloud Sandbox uses an allow-listed process to manage access.

1. Contact your IBM Cloud account representative or the Classic to VPC Migration Program team to request sandbox access.
2. Provide information about your current Classic infrastructure configuration and migration goals.
3. Wait for approval notification, which typically takes 3-5 business days.

After approval, you will receive an email with instructions to access your sandbox environment.

## Choose a VPC template
{: #sandbox-template}
{: step}

IBM Cloud Sandbox provides 8 standard VPC templates that match common Classic infrastructure configurations. Review the available templates and select the one that most closely matches your current setup.

1. Log in to the [IBM Cloud console](https://cloud.ibm.com){: external}.
2. Navigate to the IBM Cloud Sandbox section.
3. Review and select the appropriate template.

If none of the standard templates meet your requirements, select the "Other" option to create a custom configuration.
{: tip}

## Deploy your sandbox environment
{: #sandbox-deploy}
{: step}

After you select a template, deploy your sandbox environment.

1. Review the template configuration details, including:

    - Virtual server instances
    - Subnets and network configuration
    - Security groups and network ACLs
    - Storage volumes
    - Load balancers (if applicable)

2. Customize the configuration if needed:

    - Adjust instance sizes
    - Modify network settings
    - Add or remove components

3. Click **Deploy sandbox environment**.
4. Wait for the deployment to complete. This process typically takes 10-15 minutes.

You receive a notification when your sandbox environment is ready to use.

## Explore VPC features
{: #sandbox-explore}
{: step}

After your sandbox environment is deployed, you can begin exploring VPC features and capabilities.

### Access your sandbox environment
{: #sandbox-access-environment}

1. In the IBM Cloud console, navigate to your sandbox environment.
2. Review the deployed resources in the VPC dashboard.
3. Access virtual server instances using SSH or the web console.

For more information, see [Deploying the IBM Cloud Sandbox](/docs/sandbox?topic=sandbox-deploy).

### Test VPC capabilities
{: #sandbox-test-capabilities}

Use your sandbox environment to test the following VPC capabilities:

- **Networking**: Configure subnets, security groups, and network ACLs
- **Compute**: Deploy and manage virtual server instances
- **Storage**: Attach and manage block storage volumes
- **Load balancing**: Configure application and network load balancers
- **VPN connectivity**: Set up VPN connections for hybrid cloud scenarios

### Compare with Classic infrastructure
{: #sandbox-compare-classic}

As you explore VPC features, compare them with your existing classic infrastructure:

- Note differences in networking models (VPC vs. Classic VLANs)
- Compare security approaches (security groups vs. Classic firewalls)
- Evaluate performance and scalability differences
- Identify any gaps or challenges for your specific use case

## Next steps
{: #next-steps}

- [Understanding VPC templates](/docs/vpc?topic=vpc-sandbox-templates)
- [Migrating from Classic to VPC](/docs/vpc?topic=vpc-sandbox-migration-guide)
- [VPC networking concepts](/docs/vpc?topic=vpc-about-networking-for-vpc)
- [Managing VPC resources](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console)
