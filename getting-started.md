---

copyright:
  years: 2026
lastupdated: "2026-04-21"

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

- **Existing IBM Cloud users** who require a safe, isolated environment to test VPC configurations, evaluate new compute profiles, or deploy workloads without affecting production environments.

## Before you begin
{: #before-you-begin}

Before you access the Cloud Sandbox, ensure that the following requirements are met:

* You need to have an active IBM Cloud account.

* You have a valid IBMid for authentication.

## Request sandbox access
{: #sandbox-request}
{: step}

1. An email notification is sent to all the allow-listed customers to experience the Cloud Sandbox environment.
2. After clicking **Request**, you will be redirected to the dashboard catalog page to get started. Update the required information.
3. Accept the terms and conditions.
4. Click **Join** account.

You will receive **Welcome to your IBM Cloud Sandbox** email. Now you are ready to deploy workloads, test configurations, and experience how VPC helps you build secure, scalable cloud environments.

## Access the IBM Cloud Catalog
{: #sandbox-catalog}
{: step}

The Cloud Sandbox is available through the IBM Cloud Catalog.

1. Log in to the [IBM Cloud catlog](https://cloud.ibm.com){: external} page.
2. Search for **Cloud Sandbox**.
3. Click **Cloud Sandbox** tile to view the service details.

For more information on provisioning, see [Provisioning the IBM Cloud Sandbox](/docs-draft/sandbox?topic=sandbox-deploy) topic.

## Create your sandbox environment
{: #sandbox-create}
{: step}

1. On the Sandbox provision page, click **Create** tab.

2. Enter the required details:

   * **Sandbox name** - Provide a unique, descriptive name for your sandbox environment (for example, "sandbox-month-date")

   * **Resource group** - Choose an existing resource group or create a new one to organize your sandbox resources. For more information on creating a new resource group, see [Creating a resource group](/docs/sandbox?topic=sandbox-create-resource-group).

   * **Region** - Select the geographic location where your sandbox resources will be deployed (for example, us-south, eu-de, jp-tok and so on). User should be clear about the region, once selected you cannot change later during provisioning.

   * **Tags** - Use the tags to organize your resources (for example, testing, team-alpha).

   * **Users** - Specify additional users who should have access to collaborate in this sandbox environment (enter IBMids or email addresses). For more information on creating/adding users, see [Creating a user](/docs/sandbox?topic=sandbox-create-user).

3. Review the sandbox configuration and trial period information (14 days).

4. Click **Create sandbox** to submit your request.

The sandbox provisioning process typically takes 5-10 minutes. You will receive a notification when your sandbox environment is ready.
{: note}

## Access your sandbox through trusted profile
{: #sandbox-access-profile}
{: step}

After your sandbox is provisioned, you will receive access for the trusted profile.

1. Check your email for the sandbox access notification.

2. Click on **Trusted profiles** in the left navigation.

3. Locate your sandbox trusted profile (it will include your sandbox name).

4. Click **Apply** or **Switch to profile** to activate the trusted profile.

5. Click **Create** to access the resource creation page. The **Quick Start** page appears where you can begin provisioning resources.

The trusted profile provides secure, time-limited access to your sandbox environment with appropriate IAM permissions. It automatically expires after the 14-day trial period.
{: important}

## Provision resources using Quick Start
{: #sandbox-quickstart}
{: step}

The sandbox environment includes Quick Start options to help you deploy common infrastructure resources. For more information, see [Quick Start](/docs/sandbox?topic=sandbox-quickstart) topic.

## Explore and test VPC capabilities
{: #sandbox-explore}
{: step}

After provisioning resources, use your sandbox environment to explore VPC features and capabilities.

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

Collaboration in your sandbox environment allows you to work together with team members on projects, share resources, and learn IBM Cloud services collectively. Whether you added users during sandbox creation or need to invite them later, the process is straightforward.

### Understanding collaboration in sandbox environments
{: #understand-collaborate}

If you added users to the sandbox during the initial creation process, they automatically receive email notifications with access instructions. These team members can immediately start collaborating with you in the shared environment.

### Adding collaborators after sandbox creation
{: #adding-collaborate}

You can invite additional team members to your sandbox at any time during the 14-day trial period. Follow these detailed steps:

1. **Access your sandbox details page**
   - From the IBM Cloud dashboard, locate your active sandbox in the resource list
   - Click on the sandbox name to open its details page
   - Alternatively, navigate to **Manage** > **Account** > **Sandboxes** and select your sandbox

2. **Open the user management interface**
   - On the sandbox details page, look for the **Manage users** button in the top-right corner or the **Add collaborators** option in the access management section
   - Click this button to open the user invitation dialog

3. **Enter team member information**
   - In the invitation form, enter the IBMids or email addresses of the team members you want to invite
   - You can add multiple users at once by separating email addresses with commas or adding them one per line
   - Ensure the email addresses are accurate to avoid delivery issues

4. **Configure access levels and permissions**
   - Select the appropriate access level for each user (for example, Viewer, Editor, Administrator)
   - **Viewer**: Can view resources and configurations but cannot make changes
   - **Editor**: Can create, modify, and delete resources within the sandbox
   - **Administrator**: Has full control including user management capabilities
   - Consider your team's needs and assign permissions accordingly to maintain security while enabling productivity

5. **Send the invitations**
   - Review the list of users and their assigned permissions
   - Click **Invite** or **Send invitations** to dispatch access notifications
   - Each invited user will receive an email with instructions on how to access the sandbox environment

### What collaborators can expect?
{: #what-collaborate}

- **Email notification**: Invited users receive an email containing a link to access the sandbox and instructions for getting started
- **Shared trial period**: All collaborators share the same 14-day trial period, which starts from the sandbox creation date
- **Resource access**: Based on their assigned permissions, collaborators can view, create, modify, and manage resources within the sandbox environment
- **Real-time collaboration**: Multiple users can work simultaneously in the sandbox, making it ideal for team training, proof-of-concepts, and collaborative development
- **Unified billing**: All resource usage within the sandbox is tracked under the sandbox account, with no individual billing concerns during the trial period

### Best practices for team collaboration
{: #best-collaborate}

- Communicate with your team about the sandbox's purpose and scope before inviting them
- Assign appropriate permission levels based on each member's role and responsibilities
- Regularly review active collaborators and remove access for users who no longer need it
- Coordinate resource creation to avoid conflicts and stay within sandbox limits
- Plan your 14-day trial period effectively to maximize team productivity

## Monitor your sandbox lifecycle
{: #sandbox-lifecycle}

Your sandbox environment has a 14-day trial period. To track your remaining time:

1. View the trial period countdown on the sandbox landing page.
2. Check your email for reminder notifications (typically sent at 7 days, 3 days, and 1 day before expiry).
3. Review the sandbox details page for expiration date and time.

After the 14-day trial period expires, all resources in the sandbox environment are automatically deleted. Ensure you save any important data or configurations before the expiration date.
{: important}

If you need to extend your evaluation, you can create a new sandbox environment or migrate your workloads to your own IBM Cloud account.

## Next steps
{: #next-steps}

- [Understanding VPC templates](/docs/vpc?topic=vpc-sandbox-templates)
- [Migrating from Classic to VPC](/docs/vpc?topic=vpc-sandbox-migration-guide)
- [VPC networking concepts](/docs/vpc?topic=vpc-about-networking-for-vpc)
- [Managing VPC resources](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console)
