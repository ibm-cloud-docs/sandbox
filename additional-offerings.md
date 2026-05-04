---

copyright:
  years: 2026
lastupdated: "2026-05-04"

keywords: sandbox best practices, vpc best practices, cloud sandbox optimization, sandbox security, resource management

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Additional offerings
{: #sandbox-add-offerings}

{{site.data.keyword.sandbox_full_notm}} offers some additional services that are automatically provisioned with default configurations when you create your Sandbox. They enhance your environments capabilities and are ready to use immediately without additional setup.
Following are the additional services offered:

## {{site.data.keyword.cos_full_notm}}
{: #cos}

A highly scalable and durable storage solution designed for unstructured data. You can use this service to:

* Store and retrieve large amounts of data such as images, videos, documents, and backups.
* Archive data for long-term retention with cost-effective storage tiers.

You can create a {{site.data.keyword.cos_full_notm}} (COS) instance either from the **{{site.data.keyword.Bluemix_notm}} UI** or through the **Sandbox Overview** page.

1. **{{site.data.keyword.Bluemix_notm}} UI** - Refer [Creating a service instance](/docs/cloud-object-storage?topic=cloud-object-storage-provision#provision-instance) topic.

2. **Sandbox Overview** page: All steps remain the same mentioned in [Creating a service instance](/docs/cloud-object-storage?topic=cloud-object-storage-provision#provision-instance) topic, but when selecting a resource group, you can either choose Default or any available resource group.

The supported capacity for {{site.data.keyword.cos_full_notm}} for Sandbox is 1 instance.

### Learn more
{: #learnmore-cos}

* [Getting started with {{site.data.keyword.cos_full_notm}}](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage)

* [Creating a bucket on COS](/docs/cloud-object-storage?topic=cloud-object-storage-secure-content-store#create-cos-bucket-step)

* [Choosing a plan and creating an instance](/docs/cloud-object-storage?topic=cloud-object-storage-provision)

* [Deleting a service instance](/docs/cloud-object-storage?topic=cloud-object-storage-provision#delete-instance)


## Load Balancer
{: #lb}

An intelligent traffic distribution service that improves application availability and performance. You can use this service to:

* Distribute incoming traffic across multiple servers to avoid overloading any single one.

* Improve response times by directing users to the nearest or least-loaded server.

You can create a load balancer either from the **{{site.data.keyword.Bluemix_notm}} UI** or through the **Sandbox Overview** page.

1. **{{site.data.keyword.Bluemix_notm}} UI** - Refer [Creating a load balancer](/docs/loadbalancer-service?topic=loadbalancer-service-configuring-ibm-cloud-load-balancer-basic-parameters) topic.

2. **Sandbox Overview** page: All steps remain the same mentioned in [Creating a load balancer](/docs/loadbalancer-service?topic=loadbalancer-service-configuring-ibm-cloud-load-balancer-basic-parameters) topic, but when selecting a resource group, you can either choose Default or any available resource group.

The supported capacity for Load Balancer for Sandbox is 1.

### Learn more
{: #learnmore-lb}

* [About IBM Cloud Load Balancer](/docs/loadbalancer-service?topic=loadbalancer-service-about-ibm-cloud-load-balancer)

* [Load balancer basics](/docs/loadbalancer-service?topic=loadbalancer-service-ibm-cloud-load-balancer-basics)

* [Exploring IBM Cloud load balancers](/docs/loadbalancer-service?topic=loadbalancer-service-explore)

* [Logging for IBM Cloud Load Balancer](/docs/loadbalancer-service?topic=loadbalancer-service-ibm-cloud-logging)

## VPN for VPC
{: #vpn-vpc}

A secure Virtual Private Network solution that provides encrypted connectivity to your Virtual Private Cloud environment. You can use this service to:

* Establish secure, encrypted connections from your on-premises network or remote locations to your VPC resources.

* Access private resources in your Sandbox environment without exposing them to the public.

* Enable remote team members to access sandbox resources safely.

You can create a load balancer either from the **{{site.data.keyword.Bluemix_notm}} UI** or through the **Sandbox Overview** page.

1. **{{site.data.keyword.Bluemix_notm}} UI** - Refer [Setting up VPC VPN connectivity](/docs/containers?topic=containers-vpc-vpnaas) topic.

2. **Sandbox Overview** page: All steps remain the same mentioned in [Setting up VPC VPN connectivity](/docs/containers?topic=containers-vpc-vpnaas) topic, but when selecting a resource group, you can either choose Default or any available resource group.

The supported capacity for VPN for VPC for Sandbox is 1 instance.

By default, the `Full-tunnel` VPN mode is selected. You need to change it to `Split-tunnel` mode.
{: important}

### Learn more
{: #learnmore-vpn}

* [VPNs for VPC overview](/docs/vpc?topic=vpc-vpn-overview)

* [About site-to-site VPN gateways](/docs/vpc?topic=vpc-using-vpn)

* [About client-to-site VPN servers](/docs/vpc?topic=vpc-vpn-client-to-site-overview)

## Transit Gateway
{: #tg}

A centralized network hub that simplifies connectivity between different network environments. You can use this service to:

* Seamlessly connect Classic Infrastructure and VPC resources within your Sandbox.

* Scale your network connections as your Sandbox environment grows.

You can create a load balancer either from the **{{site.data.keyword.Bluemix_notm}} UI** or through the **Sandbox Overview** page.

1. **{{site.data.keyword.Bluemix_notm}} UI** - Refer [Creating a transit gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui) topic.

2. **Sandbox Overview** page: All steps remain the same mentioned in [Creating a transit gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui) topic, but when selecting a resource group, you can either choose Default or any available resource group.

The supported capacity for Transit Gateway for Sandbox is 1.

### Learn more
{: #learnmore-tg}

* [Getting started with IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-getting-started&interface=ui)

* [Planning for IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui)

* [Adding a connection](/docs/transit-gateway?topic=transit-gateway-adding-connections&interface=ui)

* [Editing a connection](/docs/transit-gateway?topic=transit-gateway-editing-connections&interface=ui)

* [Deleting a connection](/docs/transit-gateway?topic=transit-gateway-deleting-connections&interface=ui)

* [Deleting a transit gateway](/docs/transit-gateway?topic=transit-gateway-delete-gateway&interface=ui)
