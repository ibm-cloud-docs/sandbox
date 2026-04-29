---

copyright:
  years: 2022, 2023
lastupdated: "2026-04-29"

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
{: #architecture}

The Sandbox platform provides a secure, automated, and scalable environment that enables users to discover IBM Cloud offerings from the IBM Cloud Catalog, provision sandbox environment, deploy workloads, and evaluate IBM Cloud VPC capabilities with minimal setup effort.

IBM Cloud Sandbox enables users to:

* Familiarize with {{site.data.keyword.vpc_short}} features, functions, and deployment workflows.

* Select suitable VPC compute profiles and deploy test workloads.

* Evaluate how VPC architecture supports their technical and business requirements.

* Experience hands-on testing before migrating applications from Classic Virtual Server or Bare Metal Server.

* Explore next-generation infrastructure without impacting existing environments or incurring additional cost.

* Gain practical insights that enhance confidence and readiness for migration to {{site.data.keyword.vpc_short}}.

## Key features
{: #key-features}

Following are the key features:

* **Isolated environments** - Every customer is assigned a separate sub-account, isolated from other users.

* **Time limited access** - A 14‑day trial with automatic cleanup of provisioned resources.

* **Trusted profile security** - Fine-grained access control through IBM Cloud IAM.

* **Collaborative access** - Ability to invite team members to the sandbox environment.

## Architecture diagram
{: #arch-diagram}

![Architecture diagram](images/sandbox_architecture.svg "IBM Cloud Sandbox architecture diagram"){: caption="IBM Cloud Sandbox architecture diagram" caption-side="bottom"}

## How it works
{: #how-it-works}

The IBM Cloud Sandbox architecture consists of few primary layers that work together to provide a secure and isolated trial environment:

1. **Users** - Users access the Cloud Sandbox through the IBM Cloud Console. After authentication, users can create the sandbox environment, which triggers the provisioning workflow.

2. **Customer account** - The customer account serves as the entry point for Sandbox provisioning and management. This layer includes:

    * ***IBM Cloud catalog*** - The IBM Cloud catalog provides the Cloud Sandbox service offering, allowing users to discover and create the Sandbox environment directly from the catalog interface.

    * ***Cloud Console*** - The Cloud Console provides the user interface for creating and managing Sandbox environments.

3. **Sandbox Sub Account** - The Sandbox Sub Account is the central infrastructure that hosts all customer Sandbox environments. Each customer receives a dedicated sub-account with a trusted profile that provides isolated access to Sandbox resources. This sub-account has a 14-day trial period and includes:

* **Sandbox Overview page** - Under the **Overview** page, you can create the resources for Sandbox by clicking **Create Resources**.

* **Servers** - You can provision the virtual server instances (VSIs) or Bare Metal servers for testing workloads.

* **Additional services** - These are additional services that are automatically provisioned with default configurations when you create your Sandbox. They enhance your environments capabilities and are ready to use immediately without additional setup.

    * **Cloud Object Storage** - A highly scalable and durable storage solution designed for unstructured data. You can use this service to:
        - Store and retrieve large amounts of data such as images, videos, documents, and backups.
        - Archive data for long-term retention with cost-effective storage tiers.
        - Serve static content for web applications (HTML, CSS, JavaScript files).
        - Store application logs and analytics data.
        - Create data lakes for big data and analytics workloads.
        - The service provides automatic redundancy and high availability, ensuring your data is protected and accessible when needed.

    * **Load Balancer** - An intelligent traffic distribution service that improves application availability and performance. You can use this service to:
        - Distribute incoming traffic across multiple servers to avoid overloading any single one.
        - Ensure high availability by automatically redirecting traffic away from unhealthy or failed servers.
        - Scale your applications horizontally by adding or removing servers without disrupting service.
        - Improve response times by directing users to the nearest or least-loaded server.
        - Support both HTTP/HTTPS web traffic and TCP-based applications.
        - Monitor server health with automatic health checks and failover capabilities.
        - Ideal for web applications, APIs, and microservices architectures that require reliability and scalability.

    * **VPN for VPC** - A secure Virtual Private Network solution that provides encrypted connectivity to your Virtual Private Cloud environment. You can use this service to:
        - Establish secure, encrypted connections from your on-premises network or remote locations to your VPC resources.
        - Access private resources in your Sandbox environment without exposing them to the public.
        - Extend your corporate network into the cloud securely.
        - Enable remote team members to access sandbox resources safely.
        - Support site-to-site VPN connections for hybrid cloud scenarios.
        - Maintain data privacy and security with industry-standard encryption protocols (IPsec).
        - Essential for development teams working remotely or organizations with strict security requirements.

    * **Transit Gateway** - A centralized network hub that simplifies connectivity between different network environments. You can use this service to:
        - Seamlessly connect Classic Infrastructure and VPC resources within your Sandbox.
        - Create a unified network architecture without complex routing configurations.
        - Enable communication between resources in different network zones.
        - Simplify network management by centralizing connectivity through a single gateway.
        - Scale your network connections as your Sandbox environment grows.
        - Reduce network complexity and potential configuration errors.
        - Particularly useful when you need resources in both Classic and VPC environments to work together, such as legacy applications communicating with modern cloud-native services.

The trusted profile ensures that customers have appropriate access controls and can only interact with resources within their allocated Sandbox environment. All resources are automatically cleaned up after the 14-day trial period expires.
