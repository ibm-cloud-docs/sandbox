---

copyright:
  years: 2026
lastupdated: "2026-08-26"

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

Yes, the Sandbox is completely free to use for 2 weeks trial period. There are no charges for the preconfigured resources provided within the Sandbox environment.

## How long can I use the Sandbox?
{: #faq-content-include}
{: faq}

The Sandbox is available for 14 days by default. With an extension, the total duration can be up to 16 days (14 days + 2-day extension).

## What is the mapping between {{site.data.keyword.Bluemix_notm}} Classic resources and equivalent VPC resources?
{: #faq-content-include}
{: faq}

{{site.data.keyword.vpc_short}} provides modern equivalents for many Classic infrastructure components. Here is a [quick reference mapping](/docs/classic-to-vpc?topic=classic-to-vpc-migrate-classic-to-vpc&utm_source=chatgpt.com#map-resources) to understand how Classic infrastructure capabilities translate into the VPC.

## Which operating system images are supported by the Sandbox?
{: #faq-content-include}
{: faq}

The Sandbox environment supports a predefined set of operating system images for Virtual Server Instances (VSIs) and Bare Metal Servers. These are the only OS images available for use within the Sandbox for pre-provisioning:

- ibm-debian-13-2-minimal-amd64
- ibm-ubuntu-24-04-4-minimal-amd64-2
- ibm-ubuntu-22-04-5-minimal-amd64
- ibm-windows-server-2019-full-standard-amd64
- ibm-debian-11-11-minimal-amd64
- ibm-rocky-linux-9-7-minimal-amd64-3
- ibm-centos-stream-10-amd64
- ibm-centos-stream-9-amd64
- ibm-rocky-linux-10-1-minimal-amd64-3

## Can I extend my Sandbox trial period beyond 14 days?
{: #faq-extend-trial}
{: faq}

Yes, you can request a one-time extension of up to 2 days(48 hours) for your Sandbox environment.

## Is it possible to provision the VPC infrastructure on all available cloud regions?
{: #faq-vpc-cr}
{: faq}

No, the Sandbox VPC infrastructure resources could be provisioned only at a single region that was selected during the Sandbox service provisioning through {{site.data.keyword.Bluemix_notm}} Catalog.

## Can users with least permissions provision Sandbox environment?
{: #faq-permissions}
{: faq}

No, to provision the Sandbox service through IBM cloud catalog the user should have administrator permission to trigger the deployment. A user with minimal permissions will not be able to provision the service.

## What happens to my resources when the Sandbox trial period ends?
{: #faq-trial-expiry}
{: faq}

When your 14-day trial period expires, all resources within your Sandbox environment are automatically cleaned up and deleted. This includes Virtual Server Instances, Bare Metal Servers, {{site.data.keyword.cos_full_notm}} buckets, Load Balancers, VPN configurations, and Transit Gateways. Make sure to export any important data, configurations, or learnings before the trial period ends, as this cleanup process is irreversible.

## Can I invite team members to collaborate in my Sandbox?
{: #faq-collaboration}
{: faq}

Yes, you can invite team members to collaborate in your Sandbox environment. You can add users during the initial Sandbox creation or invite them later through the Sandbox details page.

* Navigate to **Manage users** or **Add collaborators**.
* Enter their IBMids or email addresses.
* Assign appropriate permission levels (Viewer, Editor, or Administrator)
* Send the invitations. All collaborators share the same 14-day trial period.

Invited users must have an {{site.data.keyword.Bluemix_notm}} account.
{: note}

## Can I save my Sandbox configuration?
{: #faq-save}
{: faq}

Yes, you can save your Sandbox configuration by downloading it as a ZIP file.

## What happens if I do not create any resources?
{: #faq-create}
{: faq}

If no resources are created by the end of day 7, your account will be suspended on day 8.

## Can I delete my Sandbox early?
{: #faq-delete}
{: faq}

Yes, you can delete your Sandbox account at any time using the **Delete Sandbox** or **End Sandbox** option.

## Can I create multiple Sandboxes?
{: #faq-multiple}
{: faq}

No, only one active Sandbox is allowed per allow-listed customer account.

## Can I deploy Bare Metal (BM) in all regions?
{: #faq-bm}
{: faq}

No, Bare Metal servers are not available in all regions. You must select a region where Bare Metal is available during Sandbox creation.

## What is the difference between Virtual Server Instances (VSI) and Bare Metal Servers in the Sandbox?
{: #faq-vsi-vs-baremetal}
{: faq}

Virtual Server Instances (VSI) are virtual machines that offer flexibility, quick deployment, and are ideal for most use cases including development, testing, and web applications. Bare Metal Servers are dedicated physical servers that provide maximum performance, consistent resources, and complete isolation. They're best suited for high-performance computing, intensive database operations, or workloads with strict compliance requirements. VSIs are recommended for most Sandbox users due to their faster provisioning and flexibility.

## What additional services are automatically provisioned with my Sandbox?
{: #faq-additional-services}
{: faq}

Your Sandbox environment automatically includes four complementary services with default configurations: {{site.data.keyword.cos_full_notm}} for scalable data storage and backups, Load Balancer for distributing traffic across server instances, VPN for VPC for secure encrypted connectivity to your environment, and Transit Gateway for connecting Classic and VPC resources. These services are ready to use immediately without additional setup.

## Can I choose which region my Sandbox is deployed in?
{: #faq-region-selection}
{: faq}

Yes, during Sandbox creation you can select the geographic region where your resources will be deployed, such as us-south, eu-de, jp-tok, and others. However, once you select a region and create the Sandbox, you cannot change it later. Choose your region carefully based on your location, latency requirements, and the specific {{site.data.keyword.Bluemix_notm}} services you want to test.

## What compute profiles are available in the Sandbox?
{: #faq-compute-profiles}
{: faq}

The Sandbox offers three types of compute profiles: Balanced profiles provide equal distribution of CPU, memory, and network resources suitable for general-purpose applications; Compute-optimized profiles offer higher CPU-to-memory ratios ideal for compute-intensive tasks like batch processing; and Memory-optimized profiles provide higher memory-to-CPU ratios perfect for databases, caching systems, or in-memory analytics. Review the specific vCPU and RAM allocations for each profile to match your workload needs.

## Is there a limit to how many resources I can create in the Sandbox?
{: #faq-resource-limits}
{: faq}

Yes, Sandbox environments have resource quotas to ensure fair usage and system stability. While specific limits may vary, they typically include restrictions on the number of Virtual Server Instances, Bare Metal Servers, storage volumes, and network resources you can provision. These limits are designed to provide sufficient resources for testing and evaluation while maintaining system performance. If you encounter resource limits, prioritize your most critical testing scenarios.

## Can I access my Sandbox resources from outside IBM Cloud?
{: #faq-external-access}
{: faq}

Yes, you can access your Sandbox resources from outside IBM Cloud using several methods. For web-facing applications, you can configure public network access during server creation. For secure remote access to private resources, use the automatically provisioned VPN for VPC service, which provides encrypted connectivity from your on-premises network or remote locations. You can also configure firewall rules and security groups to control inbound and outbound traffic based on your security requirements.

## What happens if I need to migrate my Sandbox workload to a production environment?
{: #faq-migration-to-production}
{: faq}

The Sandbox is designed for testing and evaluation, not as a production environment. If you want to migrate your workload to production, you'll need to recreate your infrastructure in your own IBM Cloud account. Document your configurations, export any data or code, and note the resource specifications you used. You can then provision similar resources in your production account. The Sandbox experience helps you understand what you'll need, but resources cannot be directly transferred from the Sandbox to production accounts.

## Can I install custom software or applications on Sandbox servers?
{: #faq-custom-software}
{: faq}

Yes, you have full administrative access to the servers you provision in your Sandbox environment. You can install custom software, applications, development tools, and configure them according to your needs. For Virtual Server Instances, you can install software on the supported operating systems (CentOS, Ubuntu, RHEL, Rocky Linux, Debian, Windows Server). For Bare Metal Servers, you also have the option to install customer-provided operating systems, giving you even more flexibility.

## How do I monitor resource usage in my Sandbox?
{: #faq-monitoring}
{: faq}

You can monitor your Sandbox resources through the IBM Cloud Console. Navigate to your Sandbox environment details page to view active resources, their status, and basic metrics. Each provisioned resource (servers, storage, networking) can be accessed individually to view more detailed information. The console provides visibility into running instances, storage consumption, network traffic, and service health. This helps you understand resource utilization and optimize your testing scenarios.

## What security features are included in the Sandbox?
{: #faq-security-features}
{: faq}

The Sandbox includes several security features: Each customer receives a dedicated, isolated sub-account ensuring complete separation from other users; Access control is managed through IBM Cloud IAM with trusted profiles providing fine-grained permissions; The VPN for VPC service offers encrypted connectivity using industry-standard IPsec protocols; You can configure security groups and firewall rules to control network traffic; and all resources are contained within your private Sandbox environment. These features allow you to test security configurations and understand IBM Cloud's security capabilities.

## Can I use the Sandbox for production workloads or customer-facing applications?
{: #faq-production-use}
{: faq}

No, the Sandbox is strictly for testing, evaluation, and learning purposes only. It should not be used for production workloads, customer-facing applications, or storing sensitive production data. The 14-day trial period, automatic resource cleanup, and resource limitations make it unsuitable for production use. Use the Sandbox to evaluate {{site.data.keyword.Bluemix_notm}} capabilities, test configurations, and validate your architecture before deploying to a production environment in your own {{site.data.keyword.Bluemix_notm}} account.

## What support is available if I encounter issues in the Sandbox?
{: #faq-support}
{: faq}

{{site.data.keyword.Bluemix_notm}} provides documentation, tutorials, and FAQs to help you navigate the Sandbox environment. If you encounter technical issues or have questions, you can access {{site.data.keyword.Bluemix_notm}} support resources through the console. For Sandbox-specific questions about provisioning, access, or trial period extensions, contact {{site.data.keyword.Bluemix_notm}} support. Keep in mind that the Sandbox is a trial environment, so support focuses on helping you successfully evaluate {{site.data.keyword.Bluemix_notm}} capabilities rather than production-level SLAs.

## Which bucket type should I select?
{: #faq-bucket-type}
{: faq}

Select **Create a Custom Bucket** to create and configure a bucket based on your specific storage requirements.

## Is it possible to create an image from a VSI file in a Sandbox account?
{: #faq-vsi}
{: faq}

Yes, it is possible. You need to ensure that the VSI is stopped by clicking on **Actions > Stop**, as the “Create Image” option is only available when the VSI is in a stopped state.

## How do I find my VPCs address prefix?
{: #faq-vpcs}
{: faq}

Verify your VPC configuration in the IBM Cloud Console under **VPC > Address Prefixes**.

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

## Is IBM Aspera download and upload supported in Sandbox environments?
{: #faq-aspera}
{: faq}

IBM Aspera downloads and uploads are currently not supported in Sandbox environments. Use the **Standard Transfer** for all the download and upload operations in Sandbox environments.

## Why am I unable to create a bucket using Quickly Get Started, Archive Your Data, or Host a Static Website?
{: #faq-account}
{: faq}

Our IBM Cloud Sandbox offering allows users to create buckets only using the **Custom Bucket** option. The following predefined options are currently unavailable in Sandbox environments:

* Quickly get started
* Archive your data
* Host a static website

## Is it expected behavior that I can create buckets in other regions?
{: #faq-region}
{: faq}

Yes. This is an expected behavior and a special capability available in the Sandbox offering. Users are allowed to create buckets across different supported regions even when operating within a Sandbox account.

## How much data can I store in a single bucket?
{: #faq-data}
{: faq}

In the IBM Cloud Sandbox environment, a Cloud Object Storage (COS) bucket supports storing objects with a maximum file size of up to 4096 GB (4 TB).
