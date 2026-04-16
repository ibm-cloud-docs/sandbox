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

# About IBM Cloud Sandbox
{: #about-sandbox}

The IBM Cloud Sandbox is a secure, scalable, and free-to-use trial environment designed to help customers explore and experience {{site.data.keyword.vpc_short}} and next-generation infrastructure.
It allows users to test, explore, and evaluate their applications or workloads using {{site.data.keyword.vpc_short}} capabilities within a limited trial period of 2 weeks.

It enables users to:

* Familiarize themselves with {{site.data.keyword.vpc_short}} features, functions, and deployment workflows.

* Select suitable VPC compute profiles and deploy test workloads.

* Evaluate how VPC architecture supports their technical and business requirements.

* Experience hands-on testing before migrating applications from Classic Virtual Server or Bare Metal Server.

* Explore next-generation infrastructure without impacting existing environments or incurring additional cost.

* Gain practical insights that enhance confidence and readiness for migration to {{site.data.keyword.vpc_short}}.

## Architecture
{: #architecture}

![Architecture diagram](images/sandbox_architecture.svg "IBM Cloud Sandbox architecture diagram"){: caption="IBM Cloud Sandbox architecture diagram" caption-side="bottom"}

### Service catalog
{: #sandbox-service-catalog}

Allowlisted customers access the Sandbox offering through the IBM Cloud Catalog within their IBM Cloud account. By selecting the offering from the **Service Catalog** initiates the Sandbox experience in the IBM Cloud Console.

### Create Sandbox form
{: #create-sandbox-form}

On the IBM Sandbox provisioning page, enter the required information:

* Sandbox name
* Region
* Resource group
* Tags (optional)
* Users list - required for working with the Sandbox environment.

### Customer Sandbox Sub Account (Trusted Profile)
{: #sandbox-sub-accnt}

Customers can access the Sandbox using a trusted profile. When a customer switches to the trusted profile, they can view the Sandbox landing page and provision resources. The trusted profile also enables fine-grained control over what customers can view and which resources they can provision through IAM access policies.

Following are the core responsibilities of customer Sandbox sub account:

* Hosts all customer sandbox workloads
* Enforces strict isolation between users
* Supports automated cleanup after trial expiry

Following are the key characteristics:

* Each sandbox request provisions a new sub account with trusted profile
* On-demand resources are provisioned into a dedicated VPC with private subnets
* Customer can create resources as per the quota and access policies defined in trusted profile.
* Lifecycle is fully automated



* Cloud Object Storage (COS) - This stores configuration artifacts, templates, and generated outputs.

* Cloud Logs - This provides centralized logging for API, onboarding, service broker, and maintenance services.

* Cloud Monitoring - This provides observability into platform health and performance.

* Event Notifications- This handles the email notifications such as invites, reminders, and expiration notices.

* Secrets Manager- This safely stores the credentials, tokens, and sensitive configuration information.
