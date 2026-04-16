---

copyright:
  years: 2022, 2023
lastupdated: "2026-04-16"

keywords:

subcollection: sandbox

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:beta: .beta}
{:important: .important}

# Architecture
{: #architecture}

![Architecture diagram](images/sandbox_architecture.svg "IBM Cloud Sandbox architecture diagram"){: caption="IBM Cloud Sandbox architecture diagram" caption-side="bottom"}

## How it works
{: #how-it-works}

The IBM Cloud Sandbox architecture consists of three primary layers that work together to provide a secure and isolated trial environment:

1. **User Access Layer** - Where users authenticate and access the Sandbox
2. **Customers Account** - The provisioning and management interface
3. **Sandbox Enterprise POC Master Account** - The backend infrastructure hosting customer sandbox environments.

### User access
{: #user-access}

Users access the IBM Cloud Sandbox through the IBM Cloud Console. After authentication, users can request access to a sandbox environment, which triggers the provisioning workflow.

### Customers account
{: #customer-account}

The Customer's Account serves as the entry point for sandbox provisioning and management. This layer includes:

#### IBM Cloud catalog
{: #cloud-catalog}

The IBM Cloud Catalog provides the Cloud Sandbox service offering, allowing users to discover and request sandbox environments directly from the catalog interface.

#### Cloud Console
{: #cloud-console}

The Cloud Console provides the user interface for creating and managing sandbox environments. Users interact with the **Create Sandbox Form** to enter the following details:

* **Sandbox Name** - A unique identifier for the sandbox environment
* **Region** - The geographic location where resources will be deployed
* **Resource Group** - The organizational unit for resource management
* **Tags** - Metadata labels for resource organization and tracking
* **Users List** - Collaborators who will have access to the sandbox environment

Once the form is submitted, the sandbox is provisioned in the backend infrastructure.

### Sandbox Enterprise POC Master Account
{: #sandbox-enterprise-master}

The Sandbox Enterprise POC Master Account is the central infrastructure that hosts all customer sandbox environments. It consists of two distinct sub-accounts:

#### Customer Sandbox Sub Account
{: #customer-sandbox-subaccount}

Each customer receives a dedicated sub-account with a trusted profile that provides isolated access to sandbox resources. This sub-account has a 14-day trial period and includes:

* **Quick Start** - Under the Overview page, you can create the resources for Sandbox by clicking **Create Resources**.

* **Servers** - You can provision the Virtual Server Instances (VSIs) or Bare Metal servers for testing workloads.

* **Additional Services** - These are the additional services that are provisioned automatically using default configuration.

    * **Cloud Object Storage** - Scalable object storage for data and backups.
    * **Load Balancer** - Distribute traffic across multiple server instances.
    * **VPN for VPC** - Secure connectivity to the VPC environment.
    * **Transit Gateway** - Securely interconnect Classic and VPC resources.

The trusted profile ensures that customers have appropriate access controls and can only interact with resources within their allocated sandbox environment. All resources are automatically cleaned up after the 14-day trial period expires.

## Key features
{: #key-features}

* **Isolated Environments** - Each customer is provided with a dedicated sub-account that is strictly isolated from all other users.

* **Time-Limited Access** - A 14-day trial period with automatic resource cleanup.

* **Pre-configured Services** - Quick Start templates for common infrastructure patterns
* **Trusted Profile Security** - Fine-grained access control through IBM Cloud IAM
* **Automated Provisioning** - Streamlined onboarding through the Cloud Console
* **Collaborative Access** - Ability to invite team members to the sandbox environment

## Benefits
{: #benefits}

* **Risk-Free Exploration** - Test VPC capabilities without affecting production environments
* **Cost-Effective** - Free trial period with no charges for sandbox usage
* **Rapid Deployment** - Provision resources quickly using pre-configured templates
* **Hands-On Learning** - Gain practical experience with IBM Cloud infrastructure
* **Migration Planning** - Evaluate VPC architecture before committing to migration
* **Team Collaboration** - Share sandbox access with colleagues for joint evaluation
