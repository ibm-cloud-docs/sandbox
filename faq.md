---

copyright:
  years: 2026
lastupdated: "2026-04-21"

keywords:

subcollection: sandbox

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQs
{: #my-service-faq}

This document provides a list of frequently asked questions and answers about a specific topic for IBM Cloud Sandbox.
{: shortdesc}

## Is the IBM Cloud Sandbox free?
{: #faq-page-setup}
{: faq}

Yes, the Sandbox is completely free to use for 2 weeks trial period. There are no charges for the preconfigured resources provided within the Sandbox environment.

## How long can I use the Sandbox?
{: #faq-content-include}
{: faq}

The Sandbox is available for a limited trial period of 2 weeks. Extensions may be possible based on availability and use case requirements and for only 2 days.

## What is the mapping between IBM Cloud Classic resources and equivalent VPC resources?
{: #faq-content-include}
{: faq}

{{site.data.keyword.vpc_short}} provides modern equivalents for many Classic infrastructure components. Here is a quick reference mapping to understand how Classic infrastructure capabilities translate into the VPC.

## Which operating system images are supported in the IBM Cloud Sandbox?
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

## Can I extend my sandbox trial period beyond 14 days?
{: #faq-extend-trial}
{: faq}

Yes, you can request a one-time extension of up to 2 days for your sandbox environment. Extensions are granted based on availability and use case requirements. To request an extension, contact IBM Cloud support before your trial period expires. Note that extensions are not guaranteed and are evaluated on a case-by-case basis.

## What happens to my resources when the sandbox trial period ends?
{: #faq-trial-expiry}
{: faq}

When your 14-day trial period expires, all resources within your sandbox environment are automatically cleaned up and deleted. This includes Virtual Server Instances, Bare Metal Servers, Cloud Object Storage buckets, Load Balancers, VPN configurations, and Transit Gateways. Make sure to export any important data, configurations, or learnings before the trial period ends, as this cleanup process is irreversible.

## Can I invite team members to collaborate in my sandbox?
{: #faq-collaboration}
{: faq}

Yes, you can invite team members to collaborate in your sandbox environment. You can add users during the initial sandbox creation or invite them later through the sandbox details page. Simply navigate to **Manage users** or **Add collaborators**, enter their IBMids or email addresses, assign appropriate permission levels (Viewer, Editor, or Administrator), and send invitations. All collaborators share the same 14-day trial period.

## What is the difference between Virtual Server Instances (VSI) and Bare Metal Servers in the sandbox?
{: #faq-vsi-vs-baremetal}
{: faq}

Virtual Server Instances (VSI) are virtual machines that offer flexibility, quick deployment, and are ideal for most use cases including development, testing, and web applications. Bare Metal Servers are dedicated physical servers that provide maximum performance, consistent resources, and complete isolation. They're best suited for high-performance computing, intensive database operations, or workloads with strict compliance requirements. VSIs are recommended for most sandbox users due to their faster provisioning and flexibility.

## What additional services are automatically provisioned with my sandbox?
{: #faq-additional-services}
{: faq}

Your sandbox environment automatically includes four complementary services with default configurations: Cloud Object Storage for scalable data storage and backups, Load Balancer for distributing traffic across server instances, VPN for VPC for secure encrypted connectivity to your environment, and Transit Gateway for connecting Classic and VPC resources. These services are ready to use immediately without additional setup.

## Can I choose which region my sandbox is deployed in?
{: #faq-region-selection}
{: faq}

Yes, during sandbox creation you can select the geographic region where your resources will be deployed, such as us-south, eu-de, jp-tok, and others. However, once you select a region and create the sandbox, you cannot change it later. Choose your region carefully based on your location, latency requirements, and the specific IBM Cloud services you want to test.

## What compute profiles are available in the sandbox?
{: #faq-compute-profiles}
{: faq}

The sandbox offers three types of compute profiles: Balanced profiles provide equal distribution of CPU, memory, and network resources suitable for general-purpose applications; Compute-optimized profiles offer higher CPU-to-memory ratios ideal for compute-intensive tasks like batch processing; and Memory-optimized profiles provide higher memory-to-CPU ratios perfect for databases, caching systems, or in-memory analytics. Review the specific vCPU and RAM allocations for each profile to match your workload needs.

## Is there a limit to how many resources I can create in the sandbox?
{: #faq-resource-limits}
{: faq}

Yes, sandbox environments have resource quotas to ensure fair usage and system stability. While specific limits may vary, they typically include restrictions on the number of Virtual Server Instances, Bare Metal Servers, storage volumes, and network resources you can provision. These limits are designed to provide sufficient resources for testing and evaluation while maintaining system performance. If you encounter resource limits, prioritize your most critical testing scenarios.

## Can I access my sandbox resources from outside IBM Cloud?
{: #faq-external-access}
{: faq}

Yes, you can access your sandbox resources from outside IBM Cloud using several methods. For web-facing applications, you can configure public network access during server creation. For secure remote access to private resources, use the automatically provisioned VPN for VPC service, which provides encrypted connectivity from your on-premises network or remote locations. You can also configure firewall rules and security groups to control inbound and outbound traffic based on your security requirements.

## What happens if I need to migrate my sandbox workload to a production environment?
{: #faq-migration-to-production}
{: faq}

The sandbox is designed for testing and evaluation, not as a production environment. If you want to migrate your workload to production, you'll need to recreate your infrastructure in your own IBM Cloud account. Document your configurations, export any data or code, and note the resource specifications you used. You can then provision similar resources in your production account. The sandbox experience helps you understand what you'll need, but resources cannot be directly transferred from the sandbox to production accounts.

## Can I install custom software or applications on sandbox servers?
{: #faq-custom-software}
{: faq}

Yes, you have full administrative access to the servers you provision in your sandbox environment. You can install custom software, applications, development tools, and configure them according to your needs. For Virtual Server Instances, you can install software on the supported operating systems (CentOS, Ubuntu, RHEL, Rocky Linux, Debian, Windows Server). For Bare Metal Servers, you also have the option to install customer-provided operating systems, giving you even more flexibility.

## How do I monitor resource usage in my sandbox?
{: #faq-monitoring}
{: faq}

You can monitor your sandbox resources through the IBM Cloud Console. Navigate to your sandbox environment details page to view active resources, their status, and basic metrics. Each provisioned resource (servers, storage, networking) can be accessed individually to view more detailed information. The console provides visibility into running instances, storage consumption, network traffic, and service health. This helps you understand resource utilization and optimize your testing scenarios.

## What security features are included in the sandbox?
{: #faq-security-features}
{: faq}

The sandbox includes several security features: Each customer receives a dedicated, isolated sub-account ensuring complete separation from other users; Access control is managed through IBM Cloud IAM with trusted profiles providing fine-grained permissions; The VPN for VPC service offers encrypted connectivity using industry-standard IPsec protocols; You can configure security groups and firewall rules to control network traffic; and all resources are contained within your private sandbox environment. These features allow you to test security configurations and understand IBM Cloud's security capabilities.

## Can I use the sandbox for production workloads or customer-facing applications?
{: #faq-production-use}
{: faq}

No, the sandbox is strictly for testing, evaluation, and learning purposes only. It should not be used for production workloads, customer-facing applications, or storing sensitive production data. The 14-day trial period, automatic resource cleanup, and resource limitations make it unsuitable for production use. Use the sandbox to evaluate IBM Cloud capabilities, test configurations, and validate your architecture before deploying to a production environment in your own IBM Cloud account.

## What support is available if I encounter issues in the sandbox?
{: #faq-support}
{: faq}

IBM Cloud provides documentation, tutorials, and FAQs to help you navigate the sandbox environment. If you encounter technical issues or have questions, you can access IBM Cloud support resources through the console. For sandbox-specific questions about provisioning, access, or trial period extensions, contact IBM Cloud support. Keep in mind that the sandbox is a trial environment, so support focuses on helping you successfully evaluate IBM Cloud capabilities rather than production-level SLAs.
