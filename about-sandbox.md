---

copyright:
  years: 2022, 2023
lastupdated: "2026-04-13"

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

## How it works
{: #how-it-works}

The Sandbox user experience is structured into four key domains:

1. Sandbox Enterprise POC Master Account
2. Customer Sandbox Sub Account (Trusted Profile)
3. Console Microservice
4. Sandbox Enterprise IBM Internal Sub Account (Control Plane)

### Sandbox Enterprise POC Master Account
{: #sandbox-poc-master-accnt}

The Sandbox Enterprise POC Master Account acts as the central governance and enterprise root for the Sandbox ecosystem. It is used to create sandbox environments for customers and set the catalog settings. It also helps in monitoring the child accounts.

Following are the key responsibilties:

* Managing enterprise hierarchy and account lifecycle
* Enforcing organization-wide policies and compliance controls
* Acting as the trust anchor for Sandbox Enterprise Trusted Profiles
* No customer workloads or control plane services run here

This account serves purely as the governance foundation and does not host runtime Sandbox services.
{: note}

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

### Console Microservice
{: #sandbox-console-ms}

The Console Microservice is responsible for deploying and serving the Sandbox UI, enabling users to interact with the Sandbox platform through the IBM Cloud Console.

Following are the key components:

* Sandbox UI (Console Microservice)
* Cloud logs for debugging
* Cloud monitoring for health and performance

### Sandbox Enterprise IBM Internal Sub Account (Control Plane)
{: #sandbox-internal-sub-accnt}

The Sandbox Enterprise IBM Internal Sub Account functions as the control plane for the Sandbox platform. This account resides within the Sandbox Enterprise IBM Internal Master Account.

This account hosts all API services, service broker, automation pipelines, and operational services required to manage customer sandbox environments.

Following are the key responsibilties:

* Handles user requests coming from IBM Cloud Catalog
* Exposes Sandbox APIs and Service Broker endpoints
* Orchestrates account provisioning and onboarding
* Manages lifecycle automation (trial, reminders, cleanup)
* Integrates with IBM Cloud services and customer sandbox

Sandbox UI is hosted on IBM Cloud Console.
{: note}

Following are the key components of Sandbox Enterprise IBM Internal Sub Account:

* VPC with Private Subnet - This secures the network boundary for control plane services.

* Red Hat OpenShift on IBM Cloud (ROKS) - This consists of:

    * Sandbox API
    * Sandbox maintenance services (part of API service)
    * Console microservice
    * Service broker

* Ingress Controller and Load Balancer (ALB) - This securely exposes Sandbox APIs and service broker endpoints.

* IBM Cloud Internet Services (CIS) - This provides secure public ingress, traffic routing, TLS termination, and protection.

* IBM IAM Token Endpoint - This is used for authentication and authorization of users and services.

* PostgreSQL - This stores:

    * User and invite metadata
    * Registration and lifecycle state
    * Trial status and operational data
    * Service Broker registration and binding metadata

* Cloud Object Storage (COS) - This stores configuration artifacts, templates, and generated outputs.

* Cloud Logs - This provides centralized logging for API, onboarding, service broker, and maintenance services.

* Cloud Monitoring - This provides observability into platform health and performance.

* Event Notifications- This handles the email notifications such as invites, reminders, and expiration notices.

* Secrets Manager- This safely stores the credentials, tokens, and sensitive configuration information.
