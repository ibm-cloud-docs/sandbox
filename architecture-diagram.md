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

### Service catalog
{: #sandbox-service-catalog}

Allowlisted customers access the Sandbox offering through the IBM Cloud Catalog within their IBM Cloud account. By selecting the offering from the **Service Catalog** initiates the Sandbox experience in the IBM Cloud Console.

### Creating Sandbox
{: #create-sandbox}

After you login to [IBM Cloud catalog](https://cloud.ibm.com/catalog), search for Sandbox and provide the following details to create the Sandbox.

* Sandbox name
* Region
* Resource group
* Tags (optional)
* Users list - required for working with the Sandbox environment.

### Quick Start
{: #sandbox-quickstart}

Customers can access the Sandbox using a trusted profile. When a customer switches to the trusted profile, they can view the Sandbox landing page and provision resources. The trusted profile also enables fine-grained control over what customers can view and which resources they can provision through IAM access policies.

Create the resources on the Overview page by clicking on **Create Resources**.


Some of the additional services are:

* Cloud Object Storage (COS) - This stores configuration artifacts, templates, and generated outputs.

* Cloud Logs - This provides centralized logging for API, onboarding, service broker, and maintenance services.

* Cloud Monitoring - This provides observability into platform health and performance.

* Event Notifications- This handles the email notifications such as invites, reminders, and expiration notices.

* Secrets Manager- This safely stores the credentials, tokens, and sensitive configuration information.
