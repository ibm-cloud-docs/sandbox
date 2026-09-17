---

copyright:
  years: 2026
lastupdated: "2026-09-17"

keywords:

subcollection: sandbox

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQs
{: #my-service-faq}

This document provides a list of frequently asked questions and answers about {{site.data.keyword.sandbox_full_notm}}.
{: shortdesc}

## Is the {{site.data.keyword.sandbox_full_notm}} free?
{: #faq-page-setup}
{: faq}

Yes, the Cloud Sandbox is completely free to use for 2 weeks trial period. There are no charges for the preconfigured resources provided within the environment.

## How long can I use the Cloud Sandbox?
{: #faq-use}
{: faq}

The Cloud Sandbox is available for 14 days by default. With an extension, the total duration can be up to 16 days (14 days + 2-day extension).

## What is the mapping between {{site.data.keyword.Bluemix_notm}} Classic resources and equivalent VPC resources?
{: #faq-mapping}
{: faq}

{{site.data.keyword.vpc_short}} provides modern equivalents for many Classic infrastructure components. Here is a [quick reference mapping](/docs/classic-to-vpc?topic=classic-to-vpc-migrate-classic-to-vpc&utm_source=chatgpt.com#map-resources) to understand how Classic infrastructure capabilities translate into the VPC.

## Which operating system images are supported by the Cloud Sandbox?
{: #faq-os}
{: faq}

The environment supports a predefined set of operating system images for Virtual Server Instances (VSIs) and Bare Metal Servers. These are the only OS images available for use within the Cloud Sandbox for pre-provisioning:

- ibm-centos-stream-10-amd64-10
- ibm-centos-stream-9-amd64-17
- ibm-debian-13-6-minimal-amd64-1
- ibm-rocky-linux-10-2-minimal-amd64-1
- ibm-rocky-linux-9-7-minimal-amd64-6
- ibm-ubuntu-22-04-5-minimal-amd64-18
- ibm-ubuntu-24-04-4-minimal-amd64-7
- ibm-windows-server-2019-full-standard-amd64-47

## Is it possible to provision the VPC infrastructure on all available cloud regions?
{: #faq-vpc-cr}
{: faq}

No, the Cloud Sandbox VPC infrastructure resources could be provisioned only at a single region that was selected during the Sandbox service provisioning through {{site.data.keyword.Bluemix_notm}} Catalog.

## Can users with least permissions provision Cloud Sandbox environment?
{: #faq-permissions}
{: faq}

No, to provision the Cloud Sandbox service through IBM cloud catalog the user should have **administrator permission** to trigger the deployment. A user with minimal permissions will not be able to provision the service. For more information, see [IAM Permissions](/docs/sandbox?topic=sandbox-manage-user-access-sandbox).

## What happens to my resources when the Cloud Sandbox trial period ends?
{: #faq-trial-expiry}
{: faq}

When your 14-day trial period expires, all resources within your Cloud Sandbox environment are automatically cleaned up and deleted. This includes Virtual Server Instances, Bare Metal Servers, {{site.data.keyword.cos_full_notm}} buckets, Load Balancers, VPN configurations, and Transit Gateways. Make sure to export any important data, configurations, or learnings before the trial period ends, as this cleanup process is irreversible.

## Can I invite team members to collaborate in my Cloud Sandbox?
{: #faq-collaboration}
{: faq}

Yes, you can invite team members to collaborate in your environment. You can add users during the initial Cloud Sandbox creation or invite them later through the Sandbox details page.

* Navigate to **Manage users** or **Add collaborators**.
* Enter their IBMids or email addresses.
* Assign appropriate permission levels (Viewer, Editor, or Administrator)
* Send the invitations. All collaborators share the same 14-day trial period.
* If the user is already part of the account, you can use the **User Management** page to add them to the Cloud Sandbox Account.
* If the user is not part of the account, first invite them to join the account. Once they have been added, use the User Management page to add them to the Cloud Sandbox Account.

Invited users must have an {{site.data.keyword.Bluemix_notm}} account.
{: note}

## Can I save my Cloud Sandbox configuration?
{: #faq-save}
{: faq}

Yes, you can save your Cloud Sandbox configuration by downloading it as a ZIP file.

## What happens if I do not create any resources?
{: #faq-create}
{: faq}

If no resources are created by the end of day 7, your account will be suspended on day 8.

## Can I delete my Cloud Sandbox early?
{: #faq-delete}
{: faq}

Yes, you can delete your Cloud Sandbox account at any time using the **Delete Sandbox** or **End Sandbox** option.

## Can I create multiple Cloud Sandbox's?
{: #faq-multiple}
{: faq}

User can create up to three Sandbox instances per year. However, a 21-day cooling period is enforced by default between Sandbox provisions. Once the cooling period has elapsed, a new Sandbox account can be provisioned.

By default, multiple Sandbox accounts cannot be created simultaneously.

## Can I deploy Bare Metal (BM) in all regions?
{: #faq-bm}
{: faq}

No, Bare Metal servers are not available in all regions. You must select a region where Bare Metal is available during Cloud Sandbox creation.

## What is the difference between Virtual Server Instances (VSI) and Bare Metal Servers in the Cloud Sandbox?
{: #faq-vsi-vs-baremetal}
{: faq}

Virtual Server Instances (VSI) are virtual machines that offer flexibility, quick deployment, and are ideal for most use cases including development, testing, and web applications. Bare Metal Servers are dedicated physical servers that provide maximum performance, consistent resources, and complete isolation. They're best suited for high-performance computing, intensive database operations, or workloads with strict compliance requirements. VSIs are recommended for most Cloud Sandbox users due to their faster provisioning and flexibility.

## Which resource types are supported within a Cloud Sandbox environment?
{: #faq-additional-services}
{: faq}

The following resource types are supported for creation within a Cloud Sandbox environment:
* Virtual Server Instance (VSI)
* Bare Metal Server (BM)
* Virtual Private Cloud (VPC)
* Transit Gateway
* Load Balancer
* Cloud Object Storage (COS)
* Secrets Manager (Trial plan only)
* VPN

## Can I choose which region my Cloud Sandbox is deployed in?
{: #faq-region-selection}
{: faq}

Yes, during Cloud Sandbox creation you can select the geographic region where your resources will be deployed, such as us-south, eu-de, jp-tok, and others. However, once you select a region and create the Cloud Sandbox, you cannot change it later. Choose your region carefully based on your location, latency requirements, and the specific {{site.data.keyword.Bluemix_notm}} services you want to test.

## What compute profiles are available in the Cloud Sandbox?
{: #faq-compute-profiles}
{: faq}

The Cloud Sandbox offers three types of compute profiles: Balanced profiles provide equal distribution of CPU, memory, and network resources suitable for general-purpose applications; Compute-optimized profiles offer higher CPU-to-memory ratios ideal for compute-intensive tasks like batch processing; and Memory-optimized profiles provide higher memory-to-CPU ratios perfect for databases, caching systems, or in-memory analytics. Review the specific vCPU and RAM allocations for each profile to match your workload needs.

## Is there a limit to how many resources I can create in the Cloud Sandbox?
{: #faq-resource-limits}
{: faq}

Yes, Cloud Sandbox environments have resource quotas to ensure fair usage and system stability. While specific limits may vary, they typically include restrictions on the number of Virtual Server Instances, Bare Metal Servers, storage volumes, and network resources you can provision. These limits are designed to provide sufficient resources for testing and evaluation while maintaining system performance. If you encounter resource limits, prioritize your most critical testing scenarios. For more information, see [Cloud Sandbox quota limits](/docs/sandbox?topic=sandbox-sandbox-quota).

## Can I access my Cloud Sandbox resources from outside IBM Cloud?
{: #faq-external-access}
{: faq}

Yes, you can access your Cloud Sandbox resources from outside IBM Cloud using several methods. For web-facing applications, you can configure public network access during server creation. If you require private connectivity, create a VPN within the Cloud Sandbox environment. You can also configure firewall rules and security groups to control inbound and outbound traffic based on your security requirements.

## What happens if I need to migrate my Cloud Sandbox workload to a production environment?
{: #faq-migration-to-production}
{: faq}

The Cloud Sandbox is designed for testing and evaluation, not as a production environment. If you want to migrate your workload to production, you'll need to recreate your infrastructure in your own IBM Cloud account. Document your configurations, export any data or code, and note the resource specifications you used. You can then provision similar resources in your production account. The Cloud Sandbox experience helps you understand what you'll need, but resources cannot be directly transferred from the Cloud Sandbox to production accounts.

## Can I install custom software or applications on Cloud Sandbox servers?
{: #faq-custom-software}
{: faq}

Yes, you have full administrative access to the servers you provision in your Cloud Sandbox environment. You can install custom software, applications, development tools, and configure them according to your needs. For Virtual Server Instances, you can install software on the supported operating systems (CentOS, Ubuntu, RHEL, Rocky Linux, Debian, Windows Server). For Bare Metal Servers, you also have the option to install customer-provided operating systems, giving you even more flexibility.

## How do I monitor resource usage in my Cloud Sandbox?
{: #faq-monitoring}
{: faq}

You can monitor your Cloud Sandbox resources through the IBM Cloud Console. Navigate to your Cloud Sandbox environment details page to view active resources, their status, and basic metrics. Each provisioned resource (servers, storage, networking) can be accessed individually to view more detailed information. The console provides visibility into running instances, storage consumption, network traffic, and service health. This helps you understand resource utilization and optimize your testing scenarios.

## What security features are included in the Cloud Sandbox?
{: #faq-security-features}
{: faq}

The Cloud Sandbox includes several security features: 

* Each customer receives a dedicated, isolated sub-account ensuring complete separation from other users.
* Access control is managed through IBM Cloud IAM with trusted profiles providing fine-grained permissions.
* The VPN for VPC service offers encrypted connectivity using industry-standard IPsec protocols.
* You can configure security groups and firewall rules to control network traffic.
* All resources are contained within your private Cloud Sandbox environment. These features allow you to test security configurations and understand IBM Cloud's security capabilities.

## Can I use the Cloud Sandbox for production workloads or customer-facing applications?
{: #faq-production-use}
{: faq}

No, the Cloud Sandbox is strictly for testing, evaluation, and learning purposes only. It should not be used for production workloads, customer-facing applications, or storing sensitive production data. The 14-day trial period, automatic resource cleanup, and resource limitations make it unsuitable for production use. Use the Cloud Sandbox to evaluate {{site.data.keyword.Bluemix_notm}} capabilities, test configurations, and validate your architecture before deploying to a production environment in your own {{site.data.keyword.Bluemix_notm}} account.

## What support is available if I encounter issues in the Cloud Sandbox?
{: #faq-support}
{: faq}

{{site.data.keyword.Bluemix_notm}} provides documentation, tutorials, and FAQs to help you navigate the Cloud Sandbox environment. If you encounter technical issues or have questions, you can access {{site.data.keyword.Bluemix_notm}} support resources through the console. For Cloud Sandbox-specific questions about provisioning, access, or trial period extensions, we have advanced level of Support from {{site.data.keyword.Bluemix_notm}}. Cloud Sandbox is intended for evaluation and testing purposes, so support focuses on helping you successfully evaluate {{site.data.keyword.Bluemix_notm}} capabilities rather than production-level SLAs.

## Is it possible to create an image from a VSI file in a Cloud Sandbox account?
{: #faq-vsi}
{: faq}

Yes, it is possible. You need to ensure that the VSI is stopped by clicking on **Actions > Stop**, as the “Create Image” option is only available when the VSI is in a stopped state.

## Can I change the client IP pool after creation?
{: #faq-ippool}
{: faq}

You cannot update the existing configuration, delete the VPN server and recreate it with a new client IP pool.

## What happens if I use an overlapping range?
{: #faq-overlap}
{: faq}

The VPN server creation will fail due to an address overlap error, and no resources will be provisioned.

## Why does my client IP pool need to be between /9 and /22?
{: #faq-ip}
{: faq}

This range provides sufficient IP addresses for VPN clients (at least 1,024 with a /22) while remaining manageable in size (up to a /9).

## What if I need more than 1,024 VPN connections?
{: #faq-vpn}
{: faq}

Use a larger CIDR block within the allowed range, such as `/21` (2,048 IPs) or `/20` (4,096 IPs).

## Why is my environment provisioning taking longer than the expected 10–15 minutes?
{: #faq-provision}
{: faq}

In some cases, provisioning may take longer due to backend processing delays, infrastructure dependencies, or resource availability. While most environments are set up within 10–15 minutes, occasional delays can occur and may not be directly controllable from the UI or user side.

## Is IBM Aspera download and upload supported in Cloud Sandbox environments?
{: #faq-aspera}
{: faq}

IBM Aspera downloads and uploads are currently not supported in Cloud Sandbox environments. Use the **Standard Transfer** for all the download and upload operations in Cloud Sandbox environments.

## Why am I unable to create a bucket using Quickly Get Started, Archive Your Data, or Host a Static Website?
{: #faq-account}
{: faq}

Our IBM Cloud Sandbox offering allows users to create buckets only using the **Custom Bucket** option. The following predefined options are currently unavailable in the environments:

* Quickly get started
* Archive your data
* Host a static website

## Is it expected behavior that I can create buckets in other regions?
{: #faq-region}
{: faq}

Yes. This is an expected behavior and a special capability available in the Cloud Sandbox offering. Users are allowed to create buckets across different supported regions even when operating within a Cloud Sandbox account.

## How much data can I store in a single bucket?
{: #faq-data}
{: faq}

In the IBM Cloud Sandbox environment, a Cloud Object Storage (COS) bucket supports storing objects with a maximum file size of up to 4096 GB (4 TB).

## Can you reclaim resources created in a Cloud Sandbox account?
{: #faq-reclaim}
{: faq}

No. Cloud Sandbox is not responsible for reclaiming resources that have been deleted accidentally.

If you accidentally delete a resource, you can reclaim only those resources that are supported by the IBM Cloud.

## Why are my Cloud Sandbox resources not appearing in the resource list?
{: #faq-rl}
{: faq}

This can happen for the following reasons:

* Some **Bare Metal Server (BM) profiles** are available only in specific regions and zones. The profile might be unavailable due to regional or zone-specific restrictions, or because of capacity limitations in the selected location.
* The selected **Flex VSI profile** might be unavailable because of capacity constraints. In such cases, choose a different Flex VSI profile from the list of available profiles.

## Can I reclaim resources and Cloud Sandbox account?
{: #faq-reclaim}
{: faq}

Yes, but only for supported resource types.

If you accidentally delete your Sandbox account from the resource list, you can reclaim only the resources that are supported in IBM Cloud Sandbox.
If you click **End Early** before your trial expires and later decide to continue using the remaining trial period, you can reclaim only the supported resources during the **trial reclamation period**.

## Why is my manually created SSH key not listed on the Quick Start page?
{: #faq-ssh-key}
{: faq}

The **Quick Start** page displays only the SSH keys that are created in the `sandbox-rg` resource group. SSH keys created in the **Default** resource group or any other resource group are not displayed on the Quick Start page.
