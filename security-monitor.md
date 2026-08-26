---

copyright:
  years: 2026
lastupdated: "2026-08-26"

keywords: security group, security group rules, delete rules, sandbox, violation, compliance

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Security group rule violations
{: #delete-security-group-rules}

When you receive a security group violation notification in your {{site.data.keyword.cloud}} Sandbox environment, you need to remove or modify the violating security group rules to maintain compliance with security policies.
{: shortdesc}

## Understanding security group violations
{: #understanding-violations}

Security group violations occur when inbound rules allow unrestricted access from any IP address (0.0.0.0/0) on sensitive ports. These configurations expose your resources to potential security risks and must be remediated within 96 hours.

Common violations include unrestricted access on:

* **Port 22** - SSH access

* **Port 3389** - RDP access

* **All ports** - Any port configuration

## Before you begin
{: #prereqs}

- Ensure you have access to the [{{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com){: external}.
- Have your account ID and security group ID from the violation notification email.
- Review the violating rules listed in your notification email.

Deleting a security group rule immediately blocks traffic matching that rule. Ensure you have alternative access methods configured before deletion.
{: important}

## Locating and deleting security group rules in the console
{: #delete-rules-console}

Following are the steps to locate and delete the security group rules in the console:

### Navigate to security groups
{: #navigate-security-groups}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com){: external}.
2. Go to **Navigation Menu** > **VPC Infrastructure** > **Security groups**.
3. If prompted, select the region where your Sandbox environment is located.

### Identify the violating security group
{: #identify-security-group}

1. In the **Security groups** list, locate the security group mentioned in your violation notification:
   - You can search by security group name or ID.
   - The security group ID is provided in your notification email.
2. Click the security group name to open its details page.

### Review the rules
{: #review-rules}

1. On the security group details page, click the **Rules** tab.
2. Review the **Inbound rules** section.
3. Identify rules that match the violation details from your notification.

Look for rules with the following characteristics:

| Characteristic | Violating value |
| -------------- | --------------- |
| Direction | Inbound |
| Source | 0.0.0.0/0 (or "Any" in the UI) |
| Port | 22, 3389, or All ports |
{: caption="Characteristics of violating security group rules" caption-side="bottom"}

### Delete the violating rule
{: #delete-rule}

1. Locate the specific rule that matches the violation.
2. Click the **overflow** menu icon at the end of the rule row.
3. Select **Delete**.
4. Confirm the deletion when prompted.

Example of a violating rule:

```text
Direction: Inbound
Protocol: TCP
Source: 0.0.0.0/0
Port: 22
```
{: screen}

### Verify the deletion
{: #verify-deletion}

1. Refresh the **Rules** tab to confirm that the rule no longer appears in the list.
2. Check that no other rules violate the security policy.
3. The violation is automatically resolved in the next security scan (typically within 15 minutes).

## Creating secure replacement rules
{: #create-secure-rules}

After deleting a violating rule, you might need to create a new rule that follows security best practices. Following are the steps to restrict specific IP addresses:

1. In the **Rules** tab, click **Create**.
2. Configure the rule with the following settings:
   - **Direction**: Inbound
   - **Protocol**: TCP (or UDP as needed)
   - **Source type**: IP address or CIDR
   - **Source**: Enter your specific IP address or CIDR block (for example, 203.0.113.0/24)
   - **Port**: Specify the exact port needed (for example, 22 for SSH)
3. Click **Create**.

## Deleting security group rules with the CLI
{: #delete-rules-cli}

You can also delete security group rules by using the {{site.data.keyword.cloud_notm}} CLI.

### Step 1: Install and configure the CLI
{: #install-cli}

Install the {{site.data.keyword.cloud_notm}} CLI and VPC infrastructure plug-in, if not installed already:

```bash
# Install IBM Cloud CLI (if not already installed)
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh

# Install VPC infrastructure plug-in
ibmcloud plugin install vpc-infrastructure
```
{: pre}

### Step 2: Log in and target your region
{: #login-cli}

```bash
# Log in to IBM Cloud
ibmcloud login --sso

# Target your region (for example, us-south)
ibmcloud target -r us-south
```
{: pre}

### Step 3: List security group rules
{: #list-rules-cli}

```bash
# List all rules for a security group
ibmcloud is security-group-rules SECURITY_GROUP_ID
```
{: pre}

Replace `SECURITY_GROUP_ID` with your security group ID from the notification email.

### Step 4: Delete the violating rule
{: #delete-rule-cli}

```bash
# Delete a specific rule
ibmcloud is security-group-rule-delete SECURITY_GROUP_ID RULE_ID
```
{: pre}

Replace the following values:

- `SECURITY_GROUP_ID` with your security group ID
- `RULE_ID` with the rule ID from the previous command

Confirm the deletion when prompted.

### Step 5: Verify the deletion with the CLI
{: #verify-deletion-cli}

```bash
# List rules again to confirm deletion
ibmcloud is security-group-rules SECURITY_GROUP_ID
```
{: pre}

## Timeline and automated enforcement
{: #timeline-enforcement}

You have 96 hours from the initial notification to remediate the violation. If not remediated, the violating rule is automatically deleted by the Sandbox team.
{: important}

The notification timeline is as follows:

* **T+0 hours** - Initial violation notification sent

* **T+48 hours** - Reminder notification sent

* **T+96 hours** - If not remediated, the violating rule is automatically deleted

* **Confirmation** - Email sent after resolution (whether by you or automation)

## Best practices
{: #best-practices}

Follow these best practices when managing security group rules:

- **Use specific IP ranges**: Always specify the exact IP addresses or CIDR blocks that need access.
- **Limit port ranges**: Only open the specific ports required for your application.
- **Use security group references**: For inter-VPC communication, reference security groups instead of IP addresses.
- **Regular audits**: Periodically review your security group rules to ensure they follow best practices.

## Getting help
{: #getting-help}

If you have questions or need assistance:

- Review the [Sandbox documentation](/docs/sandbox) for more information.
- Incase of any queries, [open a support case](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}
- Contact the Sandbox team using the email address provided in your violation notification.

## References
{: #references}

- [Learn more about security groups](/docs/vpc?topic=vpc-using-security-groups)
- [Review VPC security best practices](/docs/vpc?topic=vpc-security-in-your-vpc)

This documentation applies specifically to IBM Cloud Sandbox environments, where security group violation monitoring and automated enforcement are integrated into the Sandbox security compliance framework.
{: important}
