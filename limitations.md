---

copyright:
  years: 2026
lastupdated: "2026-04-28"

keywords: sandbox troubleshooting, sandbox provisioning issues, sandbox access problems, sandbox connectivity, sandbox resources

subcollection: sandbox

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Limitations
{: #limitation}

This section describes known constraints and limitations of IBM Cloud Sandbox. The Sandbox is designed for safe evaluation and testing of IBM Cloud VPC capabilities. Follow the guidelines below to safeguard your account and data, ensure responsible resource usage, and maintain security:

## Security guidelines
{: #security-guidlines}

Following are the do's and dont's for the Security guidelines:

### Do's
{: #sg-dos}

* **Secure your network configuration:**
    Restrict inbound and outbound rules to the minimum required IP ranges and ports. Follow the principle of least privilege.

* **Use security groups and ACLs effectively:**
    Allow only necessary application ports (for example, 22 for SSH, 3389 for RDP, 443 for HTTPS).

* **Limit Floating IP access:**
    Assign Floating IPs only when needed for testing and remove them afterward.

* **Patch vulnerabilities:**
    Keep your environment up to date by applying security patches. If patches are not applied, the Sandbox may be decommissioned to protect your account.

### Don'ts
{: #sg-dont}

* Do not open all ports (0–65535) in Security Groups or ACLs. This exposes your environment to risk.

* Do not share Floating IP addresses publicly or with untrusted users. Treat them as access points to your test environment

## Protection of credentials and access keys
{: #cred}

Following are the do's and dont's for the protection of credentials and access keys:

### Do's
{: #cred-dos}

* Store SSH keys, API keys, and service credentials securely.

* Use Secrets Manager for managing sensitive information.

### Don'ts
{: #cred-dont}

* Do not share SSH keys, API keys, passwords, or invite links with others.

* Do not upload private keys to GitHub, Slack, shared drives, or ticketing systems.

* Avoid distributing screenshots containing sensitive account information.

## Compute infrastructure guidelines
{: #compute-infra}

Following are the do's and dont's for the compute infrastructure guidelines:

### Do's
{: #compute-dos}

For Bare Metal servers (if enabled), follow recommended lifecycle actions and allow provisioning tasks to complete before rebooting.

### Don'ts
{: #compute-dont}

* Do not force-stop Bare Metal servers during provisioning, operating system installation, or maintenance actions.

* Do not attach unauthorized storage or network interfaces that violate your Sandbox limits.

## General usage conduct
{: #general}

Following are the do's and dont's for the general usage conduct:

### Do's
{: #compute-dos}

* Follow Sandbox usage limits and trial timelines.

* Notify IBM if suspicious activity or unauthorized access is detected.

### Don'ts
{: #compute-dont}

* Do not use the Sandbox for production workloads.

* Do not perform stress testing, penetration testing, or high-risk security scans unless explicitly approved by IBM.

* Do not deploy sensitive or regulated production data inside the Sandbox.
